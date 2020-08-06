---
title: Desarrollar un componente de destino personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [Integration Services], components
- destinations [Integration Services], components
- ProcessInput method
- external data sources [Integration Services]
- custom data flow components [Integration Services], destination components
- data flow components [Integration Services], destination components
ms.assetid: 24619363-9535-4c0e-8b62-1d22c6630e40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6979d14afa0490638162c35bb660f15506803484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743606"
---
# <a name="developing-a-custom-destination-component"></a><span data-ttu-id="c8343-102">Desarrollar un componente de destino personalizado</span><span class="sxs-lookup"><span data-stu-id="c8343-102">Developing a Custom Destination Component</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="c8343-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] permite a los desarrolladores escribir componentes de destino personalizados que pueden conectarse a cualquier origen de datos personalizado y almacenar datos en él.</span><span class="sxs-lookup"><span data-stu-id="c8343-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write custom destination components that can connect to and store data in any custom data source.</span></span> <span data-ttu-id="c8343-104">Los componentes de destino personalizados resultan útiles si necesitar conectarse a orígenes de datos a los que no se puede tener acceso mediante uno de los componentes de origen existentes incluidos con [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8343-104">Custom destination components are useful when you need to connect to data sources that cannot be accessed by using one of the existing source components included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="c8343-105">Los componentes de destino tienen una o más entradas y ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="c8343-105">Destination components have one or more inputs and zero outputs.</span></span> <span data-ttu-id="c8343-106">En tiempo de diseño, crean y configuran conexiones y leen metadatos de columna del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-106">At design time, they create and configure connections and read column metadata from the external data source.</span></span> <span data-ttu-id="c8343-107">Durante la ejecución, conectan a su origen de datos externo y agregan filas que se reciben de los componentes de nivel superior en el flujo de datos al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-107">During execution, they connect to their external data source and add rows that are received from the components upstream in the data flow to the external data source.</span></span> <span data-ttu-id="c8343-108">Si el origen de datos externo existe antes de la ejecución del componente, el componente de destino también debe asegurarse de que los tipos de datos de las columnas que recibe el componente coinciden con los tipos de datos de las columnas en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-108">If the external data source exists prior to execution of the component, the destination component must also ensure that the data types of the columns that the component receives match the data types of the columns at the external data source.</span></span>

 <span data-ttu-id="c8343-109">En esta sección se tratan los detalles de cómo desarrollar componentes de destino y se proporcionan ejemplos de código para aclarar conceptos importantes.</span><span class="sxs-lookup"><span data-stu-id="c8343-109">This section discusses the details of how to develop destination components, and provides code examples to clarify important concepts.</span></span> <span data-ttu-id="c8343-110">Para obtener información general sobre el desarrollo de componentes de flujo de datos, vea [Developing a Custom Data Flow Componen](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) (Desarrollo de un componente de flujo de datos personalizado).</span><span class="sxs-lookup"><span data-stu-id="c8343-110">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="c8343-111">Tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c8343-111">Design Time</span></span>
 <span data-ttu-id="c8343-112">La implementación de la funcionalidad en tiempo de diseño de un componente de destino implica especificar una conexión a un origen de datos externo y validar que el componente se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8343-112">Implementing the design-time functionality of a destination component involves specifying a connection to an external data source and validating that the component has been correctly configured.</span></span> <span data-ttu-id="c8343-113">Por definición, un componente de destino tiene una entrada y posiblemente una salida de error.</span><span class="sxs-lookup"><span data-stu-id="c8343-113">By definition, a destination component has one input and possibly one error output.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="c8343-114">Crear el componente</span><span class="sxs-lookup"><span data-stu-id="c8343-114">Creating the Component</span></span>
 <span data-ttu-id="c8343-115">Los componentes de destino se conectan a los orígenes de datos externos utilizando objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> definidos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="c8343-115">Destination components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="c8343-116">El componente de destino indica su requisito de un administrador de conexiones al Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] y a los usuarios del componente mediante la adición de un elemento a la colección <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-116">The destination component indicates its requirement for a connection manager to the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, and to users of the component, by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="c8343-117">Esta colección sirve a dos fines: anuncia la necesidad de un administrador de conexiones al Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] y, después de que el usuario ha seleccionado o creado un administrador de conexiones, incluye una referencia al administrador de conexiones en el paquete que utiliza el componente.</span><span class="sxs-lookup"><span data-stu-id="c8343-117">This collection serves two purposes: first, it advertises the need for a connection manager to [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer; then, after the user has selected or created a connection manager, it holds a reference to the connection manager in the package that is being used by the component.</span></span> <span data-ttu-id="c8343-118">Cuando se agrega un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> a la colección, el **Editor avanzado** muestra la pestaña **Propiedades de conexión**, para solicitar al usuario que seleccione o cree en el paquete una conexión para que la use el componente.</span><span class="sxs-lookup"><span data-stu-id="c8343-118">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> is added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, to prompt the user to select or create a connection in the package for use by the component.</span></span>

 <span data-ttu-id="c8343-119">En el ejemplo de código siguiente se muestra una implementación de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> que agrega una entrada y, a continuación, agrega un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-119">The following code sample shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an input, and then adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "Destination Component",ComponentType =ComponentType.DestinationAdapter)]
    public class DestinationComponent : PipelineComponent 
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSInput100 input = ComponentMetaData.InputCollection.New();
            input.Name = "Input";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.net";
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="Destination Component", ComponentType:=ComponentType.DestinationAdapter)> _
    Public Class DestinationComponent
        Inherits PipelineComponent

        Public Overrides Sub ProvideComponentProperties()

            ' Reset the component.
            Me.RemoveAllInputsOutputsAndCustomProperties()
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()
            input.Name = "Input"

            Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
            connection.Name = "ADO.net"

        End Sub
    End Class
End Namespace
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="c8343-120">Conectar a un origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="c8343-120">Connecting to an External Data Source</span></span>
 <span data-ttu-id="c8343-121">Una vez agregada una conexión a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> para establecer una conexión al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-121">After a connection is added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="c8343-122">La llamada a este método se realiza en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c8343-122">This method is called at design time and at run time.</span></span> <span data-ttu-id="c8343-123">El componente debe establecer una conexión al administrador de conexiones especificado por la conexión en tiempo de ejecución y, como consecuencia, al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-123">The component must establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span> <span data-ttu-id="c8343-124">Una vez establecida, el componente debe almacenar internamente en la memoria caché la conexión y liberarla cuando se llame a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-124">Once established, the component should cache the connection internally and release it when <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> is called.</span></span> <span data-ttu-id="c8343-125">Los programadores invalidan este método y liberan la conexión establecida por el componente durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="c8343-126">Se llama a ambos métodos, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c8343-126">Both of these methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, are called at design time and at run time.</span></span>

 <span data-ttu-id="c8343-127">En el ejemplo de código siguiente se muestra un componente que conecta a una conexión de ADO.NET en el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> y, a continuación, cierra la conexión en el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-127">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method, and then closes the connection in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

private SqlConnection sqlConnection;

public override void AcquireConnections(object transaction)
{
    if (ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager != null)
    {
        ConnectionManager cm = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager);
        ConnectionManagerAdoNet cmado = cm.InnerObject as ConnectionManagerAdoNet;

        if (cmado == null)
            throw new Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.");

        sqlConnection = cmado.AcquireConnection(transaction) as SqlConnection;
        sqlConnection.Open();
    }
}

public override void ReleaseConnections()
{
    if (sqlConnection != null && sqlConnection.State != ConnectionState.Closed)
        sqlConnection.Close();
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) = False Then

        Dim cm As ConnectionManager = DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject,ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If IsNothing(sqlConnection) = False And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="c8343-128">Validar el componente</span><span class="sxs-lookup"><span data-stu-id="c8343-128">Validating the Component</span></span>
 <span data-ttu-id="c8343-129">Los programadores de componentes de destino deben realizar la validación tal como se describe en [Component Validation](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md) (Validación de componentes).</span><span class="sxs-lookup"><span data-stu-id="c8343-129">Destination component developers should perform validation as described in [Component Validation](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span> <span data-ttu-id="c8343-130">Además, deben comprobar que las propiedades de tipo de datos de las columnas definidas en la colección de columnas de entrada del componente coinciden con las columnas en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-130">In addition, they should verify that the data type properties of the columns defined in the component's input column collection match the columns at the external data source.</span></span> <span data-ttu-id="c8343-131">En ocasiones, la comprobación de las columnas de entrada con respecto al origen de datos externo puede resultar imposible o no ser deseable; por ejemplo si el componente o el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] están en un estado desconectado o si no resultan aceptables los viajes de ida y vuelta (round trip) al servidor.</span><span class="sxs-lookup"><span data-stu-id="c8343-131">At times, verifying the input columns against the external data source can be impossible or undesirable, such as when the component or the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is in a disconnected state, or when round trips to the server are not acceptable.</span></span> <span data-ttu-id="c8343-132">En estas situaciones, las columnas de la colección de columnas de entrada se pueden validar mediante la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> del objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="c8343-132">In these situations, the columns in the input column collection can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> of the input object.</span></span>

 <span data-ttu-id="c8343-133">Esta colección existe en los objetos de entrada y salida; el programador del componente debe rellenarla a partir de las columnas del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-133">This collection exists on both input and output objects and must be populated by the component developer from the columns at the external data source.</span></span> <span data-ttu-id="c8343-134">Esta colección se puede utilizar para validar las columnas de entrada cuando el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] está en modo sin conexión, cuando el componente está desconectado o cuando la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="c8343-134">This collection can be used to validate the input columns when the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>

 <span data-ttu-id="c8343-135">En el siguiente código de ejemplo se agrega una columna de metadatos externa basada en una columna de entrada existente.</span><span class="sxs-lookup"><span data-stu-id="c8343-135">The following sample code adds an external metadata column based on an existing input column.</span></span>

```csharp
private void AddExternalMetaDataColumn(IDTSInput100 input,IDTSInputColumn100 inputColumn)
{
    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = input.ExternalMetadataColumnCollection.New();
    externalColumn.Name = inputColumn.Name;
    externalColumn.Precision = inputColumn.Precision;
    externalColumn.Length = inputColumn.Length;
    externalColumn.DataType = inputColumn.DataType;
    externalColumn.Scale = inputColumn.Scale;

    // Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID;
}
```

```vb
Private Sub AddExternalMetaDataColumn(ByVal input As IDTSInput100, ByVal inputColumn As IDTSInputColumn100)

    ' Set the properties of the external metadata column.
    Dim externalColumn As IDTSExternalMetadataColumn100 = input.ExternalMetadataColumnCollection.New()
    externalColumn.Name = inputColumn.Name
    externalColumn.Precision = inputColumn.Precision
    externalColumn.Length = inputColumn.Length
    externalColumn.DataType = inputColumn.DataType
    externalColumn.Scale = inputColumn.Scale

    ' Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID

End Sub
```

## <a name="run-time"></a><span data-ttu-id="c8343-136">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c8343-136">Run Time</span></span>
 <span data-ttu-id="c8343-137">Durante la ejecución, el componente de destino recibe una llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> cada vez que está disponible un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> completo del componente de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="c8343-137">During execution, the destination component receives a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method each time a full <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> is available from the upstream component.</span></span> <span data-ttu-id="c8343-138">Se llama a este método repetidamente hasta que no existen más búferes disponibles y la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="c8343-138">This method is called repeatedly until there are no more buffers available and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="c8343-139">Durante este método, los componentes de destino leen las columnas y filas del búfer y las agregan al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-139">During this method, destination components read columns and rows in the buffer, and add them to the external data source.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="c8343-140">Localizar columnas en el búfer</span><span class="sxs-lookup"><span data-stu-id="c8343-140">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="c8343-141">El búfer de entrada para un componente contiene todas las columnas definidas en las colecciones de columnas de salida de los componentes de nivel superior del componente en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="c8343-141">The input buffer for a component contains all the columns defined in the output column collections of the components upstream from the component in the data flow.</span></span> <span data-ttu-id="c8343-142">Por ejemplo, si un componente de origen proporciona tres columnas en su salida y el componente siguiente agrega una columna de salida adicional, el búfer proporcionado al componente de destino contiene cuatro columnas, aunque el componente de destino escriba solamente dos columnas.</span><span class="sxs-lookup"><span data-stu-id="c8343-142">For example, if a source component provides three columns in its output, and the next component adds an additional output column, the buffer provided to the destination component contains four columns, even if the destination component will write only two columns.</span></span>

 <span data-ttu-id="c8343-143">El índice de la columna de la colección de columnas de entrada del componente de destino no define el orden de las columnas del búfer de entrada.</span><span class="sxs-lookup"><span data-stu-id="c8343-143">The order of the columns in the input buffer is not defined by the index of the column in the input column collection of the destination component.</span></span> <span data-ttu-id="c8343-144">Las columnas solo se pueden localizar en un búfer de manera confiable mediante el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-144">Columns can be reliably located in a buffer row only by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="c8343-145">Este método localiza la columna con el identificador de linaje especificado en el búfer especificado y devuelve su ubicación en la fila.</span><span class="sxs-lookup"><span data-stu-id="c8343-145">This method locates the column that has the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="c8343-146">Normalmente los índices de las columnas de entrada se encuentran durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> y el programador los almacena en memoria caché para su uso posterior durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-146">The indexes of the input columns are typically located during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and cached by the developer for use later during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>

 <span data-ttu-id="c8343-147">En el ejemplo de código siguiente se busca la ubicación de las columnas de entrada en el búfer durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> y se almacenan en una matriz.</span><span class="sxs-lookup"><span data-stu-id="c8343-147">The following code example finds the location of the input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> and stores them in an array.</span></span> <span data-ttu-id="c8343-148">Posteriormente, la matriz se utiliza durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> para leer los valores de las columnas en el búfer.</span><span class="sxs-lookup"><span data-stu-id="c8343-148">The array is subsequently used during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> to read the values of the columns in the buffer.</span></span>

```csharp
int[] cols;

public override void PreExecute()
{
    IDTSInput100 input = ComponentMetaData.InputCollection[0];

    cols = new int[input.InputColumnCollection.Count];

    for (int x = 0; x < input.InputColumnCollection.Count; x++)
    {
        cols[x] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[x].LineageID);
    }
}
```

```vb
Private cols As Integer()

Public Overrides Sub PreExecute()

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)

    ReDim cols(input.InputColumnCollection.Count)

    For x As Integer = 0 To input.InputColumnCollection.Count

        cols(x) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(x).LineageID)
    Next x

End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="c8343-149">Procesar las filas</span><span class="sxs-lookup"><span data-stu-id="c8343-149">Processing Rows</span></span>
 <span data-ttu-id="c8343-150">Una vez localizadas en el búfer las columnas de entrada, se pueden leer y escribir en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c8343-150">Once the input columns have been located in the buffer, they can be read and written to the external data source.</span></span>

 <span data-ttu-id="c8343-151">Mientras el componente de destino escribe las filas del origen de datos externo, puede actualizar los contadores de rendimiento "Filas leídas" o "Bytes BLOB leídos" mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-151">While the destination component writes rows to the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="c8343-152">Para más información, consulte [Performance Counters](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="c8343-152">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="c8343-153">En el ejemplo siguiente se muestra un componente que lee las filas del búfer proporcionado en <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8343-153">The following example shows a component that reads rows from the buffer provided in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="c8343-154">Los índices de las columnas en el búfer se localizaron durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> en el ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="c8343-154">The indexes of the columns in the buffer were located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the preceding code example.</span></span>

```csharp
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
        while (buffer.NextRow())
        {
            foreach (int col in cols)
            {
                if (!buffer.IsNull(col))
                {
                    //  TODO: Read the column data.
                }
            }
        }
}
```

```vb
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

        While (buffer.NextRow())

            For Each col As Integer In cols

                If buffer.IsNull(col) = False Then

                    '  TODO: Read the column data.
                End If

            Next col
        End While
End Sub
```

## <a name="sample"></a><span data-ttu-id="c8343-155">Muestra</span><span class="sxs-lookup"><span data-stu-id="c8343-155">Sample</span></span>
 <span data-ttu-id="c8343-156">En el ejemplo siguiente se muestra un componente de destino simple que utiliza un administrador de conexiones de archivos para guardar los datos binarios del flujo de datos en archivos.</span><span class="sxs-lookup"><span data-stu-id="c8343-156">The following sample shows a simple destination component that uses a File connection manager to save binary data from the data flow into files.</span></span> <span data-ttu-id="c8343-157">En este ejemplo no se muestran todos los métodos ni funcionalidad tratados en este tema.</span><span class="sxs-lookup"><span data-stu-id="c8343-157">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="c8343-158">Muestra los métodos importantes que cada componente de destino personalizado debe invalidar, pero no contiene código para la validación en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="c8343-158">It demonstrates the important methods that every custom destination component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace BlobDst
{
  [DtsPipelineComponent(DisplayName = "BLOB Extractor Destination", Description = "Writes values of BLOB columns to files")]
  public class BlobDst : PipelineComponent
  {
    string m_DestDir;
    int m_FileNameColumnIndex = -1;
    int m_BlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection.New();
      input.Name = "BLOB Extractor Destination Input";
      input.HasSideEffects = true;

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_DestDir = (string)conn.ConnectionManager.AcquireConnection(null);

      if (m_DestDir.Length > 0 && m_DestDir[m_DestDir.Length - 1] != '\\')
        m_DestDir += "\\";
    }

    public override IDTSInputColumn100 SetUsageType(int inputID, IDTSVirtualInput100 virtualInput, int lineageID, DTSUsageType usageType)
    {
      IDTSInputColumn100 inputColumn = base.SetUsageType(inputID, virtualInput, lineageID, usageType);
      IDTSCustomProperty100 custProp;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsFileName";
      custProp.Value = (object)false;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsBLOB";
      custProp.Value = (object)false;

      return inputColumn;
    }

    public override void PreExecute()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection[0];
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;
      IDTSCustomProperty100 custProp;

      foreach (IDTSInputColumn100 column in inputColumns)
      {
        custProp = column.CustomPropertyCollection["IsFileName"];
        if ((bool)custProp.Value == true)
        {
          m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }

        custProp = column.CustomPropertyCollection["IsBLOB"];
        if ((bool)custProp.Value == true)
        {
          m_BlobColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }
      }
    }

    public override void ProcessInput(int inputID, PipelineBuffer buffer)
    {
      while (buffer.NextRow())
      {
        string strFileName = buffer.GetString(m_FileNameColumnIndex);
        int blobLength = (int)buffer.GetBlobLength(m_BlobColumnIndex);
        byte[] blobData = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength);

        strFileName = TranslateFileName(strFileName);

        // Make sure directory exists before creating file.
        FileInfo fi = new FileInfo(strFileName);
        if (!fi.Directory.Exists)
          fi.Directory.Create();

        // Write the data to the file.
        FileStream fs = new FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None);
        fs.Write(blobData, 0, blobLength);
        fs.Close();
      }
    }

    private string TranslateFileName(string fileName)
    {
      if (fileName.Length > 2 && fileName[1] == ':')
        return m_DestDir + fileName.Substring(3, fileName.Length - 3);
      else
        return m_DestDir + fileName;
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Namespace BlobDst 

 <DtsPipelineComponent(DisplayName="BLOB Extractor Destination", Description="Writes values of BLOB columns to files")> _ 
 Public Class BlobDst 
 Inherits PipelineComponent 
   Private m_DestDir As String 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_BlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New 
     input.Name = "BLOB Extractor Destination Input" 
     input.HasSideEffects = True 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_DestDir = CType(conn.ConnectionManager.AcquireConnection(Nothing), String) 
     If m_DestDir.Length > 0 AndAlso Not (m_DestDir(m_DestDir.Length - 1) = "\"C) Then 
       m_DestDir += "\" 
     End If 
   End Sub 

   Public  Overrides Function SetUsageType(ByVal inputID As Integer, ByVal virtualInput As IDTSVirtualInput100, ByVal lineageID As Integer, ByVal usageType As DTSUsageType) As IDTSInputColumn100 
     Dim inputColumn As IDTSInputColumn100 = MyBase.SetUsageType(inputID, virtualInput, lineageID, usageType) 
     Dim custProp As IDTSCustomProperty100 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsFileName" 
     custProp.Value = CType(False, Object) 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsBLOB" 
     custProp.Value = CType(False, Object) 
     Return inputColumn 
   End Function 

   Public  Overrides Sub PreExecute() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0) 
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection 
     Dim custProp As IDTSCustomProperty100 
     For Each column As IDTSInputColumn100 In inputColumns 
       custProp = column.CustomPropertyCollection("IsFileName") 
       If CType(custProp.Value, Boolean) = True Then 
         m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
       custProp = column.CustomPropertyCollection("IsBLOB") 
       If CType(custProp.Value, Boolean) = True Then 
         m_BlobColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
     Next 
   End Sub 

   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
     While buffer.NextRow 
       Dim strFileName As String = buffer.GetString(m_FileNameColumnIndex) 
       Dim blobLength As Integer = CType(buffer.GetBlobLength(m_BlobColumnIndex), Integer) 
       Dim blobData As Byte() = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength) 
       strFileName = TranslateFileName(strFileName) 
       Dim fi As FileInfo = New FileInfo(strFileName) 
       ' Make sure directory exists before creating file.
       If Not fi.Directory.Exists Then 
         fi.Directory.Create 
       End If 
       ' Write the data to the file.
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None) 
       fs.Write(blobData, 0, blobLength) 
       fs.Close 
     End While 
   End Sub 

   Private Function TranslateFileName(ByVal fileName As String) As String 
     If fileName.Length > 2 AndAlso fileName(1) = ":"C Then 
       Return m_DestDir + fileName.Substring(3, fileName.Length - 3) 
     Else 
       Return m_DestDir + fileName 
     End If 
   End Function 
 End Class 
End Namespace
```

<span data-ttu-id="c8343-159">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c8343-159">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c8343-160">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="c8343-160">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c8343-161">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="c8343-161">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c8343-162">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="c8343-162">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8343-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8343-163">See Also</span></span>
 <span data-ttu-id="c8343-164">[Desarrollar un componente de origen personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [crear un destino con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="c8343-164">[Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span></span>


