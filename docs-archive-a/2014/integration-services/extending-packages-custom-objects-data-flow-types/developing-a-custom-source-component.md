---
title: Desarrollar un componente de origen personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [Integration Services], components
- external data sources [Integration Services]
- data flow components [Integration Services], source components
- output columns [Integration Services]
- custom data flow components [Integration Services], source components
- custom sources [Integration Services]
- source components [Integration Services]
ms.assetid: 4dc0f631-8fd6-4007-b573-ca67f58ca068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6679b28463a09efe069235a5aef9dca54a381d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748203"
---
# <a name="developing-a-custom-source-component"></a><span data-ttu-id="d8637-102">Desarrollar un componente de origen personalizado</span><span class="sxs-lookup"><span data-stu-id="d8637-102">Developing a Custom Source Component</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d8637-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] permite que los desarrolladores escriban componentes de origen que se puedan conectar a los orígenes de datos personalizados y proporcionar datos de estos orígenes a otros componentes en una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d8637-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write source components that can connect to custom data sources and supply data from those sources to other components in a data flow task.</span></span> <span data-ttu-id="d8637-104">La capacidad para crear orígenes personalizados es importante cuando es necesario conectar a orígenes de datos a los que no se puede tener acceso utilizando uno de los orígenes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] existentes.</span><span class="sxs-lookup"><span data-stu-id="d8637-104">The ability to create custom sources is valuable when you must connect to data sources that cannot be accessed by using one of the existing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources.</span></span>

 <span data-ttu-id="d8637-105">Los componentes de origen tienen una o más salidas y ninguna entrada.</span><span class="sxs-lookup"><span data-stu-id="d8637-105">Source components have one or more outputs and zero inputs.</span></span> <span data-ttu-id="d8637-106">En tiempo de diseño, los componentes de origen se utilizan para crear y configurar conexiones, leer metadatos de columna del origen de datos externo y configurar las columnas de salida del origen en función del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d8637-106">At design time, source components are used to create and configure connections, read column metadata from the external data source, and configure the source's output columns based on the external data source.</span></span> <span data-ttu-id="d8637-107">Durante la ejecución, conectan al origen de datos externo y agregan filas a un búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="d8637-107">During execution they connect to the external data source and add rows to an output buffer.</span></span> <span data-ttu-id="d8637-108">A continuación, la tarea de flujo de datos proporciona este búfer de filas de datos a componentes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="d8637-108">The data flow task then provides this buffer of data rows to downstream components.</span></span>

 <span data-ttu-id="d8637-109">Para obtener información general sobre el desarrollo de componentes de flujo de datos, vea [Developing a Custom Data Flow Componen](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) (Desarrollo de un componente de flujo de datos personalizado).</span><span class="sxs-lookup"><span data-stu-id="d8637-109">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="d8637-110">Tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d8637-110">Design Time</span></span>
 <span data-ttu-id="d8637-111">La implementación de la funcionalidad en tiempo de diseño de un componente de origen implica especificar una conexión a un origen de datos externo, agregar y configurar columnas de salida que reflejen el origen de datos y validar que el componente esté listo para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d8637-111">Implementing the design-time functionality of a source component involves specifying a connection to an external data source, adding and configuring output columns that reflect the data source, and validating that the component is ready to execute.</span></span> <span data-ttu-id="d8637-112">Por definición, un componente de origen no tiene ninguna entrada y una o más salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="d8637-112">By definition, a source component has zero inputs and one or more asynchronous outputs.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="d8637-113">Crear el componente</span><span class="sxs-lookup"><span data-stu-id="d8637-113">Creating the Component</span></span>
 <span data-ttu-id="d8637-114">Los componentes de origen se conectan a los orígenes de datos externos utilizando objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> definidos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="d8637-114">Source components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="d8637-115">Indican su requisito de un administrador de conexiones agregando un elemento a la colección <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-115">They indicate their requirement for a connection manager by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="d8637-116">Esta colección tiene dos finalidades: incluir referencias a administradores de conexiones del paquete que usa el componente y anunciar la necesidad de un administrador de conexiones al diseñador.</span><span class="sxs-lookup"><span data-stu-id="d8637-116">This collection serves two purposes-to hold references to connection managers in the package used by the component, and to advertise the need for a connection manager to the designer.</span></span> <span data-ttu-id="d8637-117">Cuando se agrega <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> a la colección, el **Editor avanzado** muestra la pestaña **Propiedades de conexión**, que permite a los usuarios seleccionar o crear una conexión en el paquete.</span><span class="sxs-lookup"><span data-stu-id="d8637-117">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> has been added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, which lets users select or create a connection in the package.</span></span>

 <span data-ttu-id="d8637-118">En el ejemplo de código siguiente se muestra una implementación de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> que agrega una salida y agrega un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an output, and adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using System.Collections;
using System.Data;
using System.Data.SqlClient;
using System.Data.OleDb;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "MySourceComponent",ComponentType = ComponentType.SourceAdapter)]
    public class MyComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
            output.Name = "Output";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.NET";
        }
```

```vb
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Runtime
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper

<DtsPipelineComponent(DisplayName:="MySourceComponent", ComponentType:=ComponentType.SourceAdapter)> _
Public Class MySourceComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Allow for resetting the component.
        RemoveAllInputsOutputsAndCustomProperties()
        ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()
        output.Name = "Output"

        Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
        connection.Name = "ADO.NET"

    End Sub
End Class
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="d8637-119">Conectar a un origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="d8637-119">Connecting to an External Data Source</span></span>
 <span data-ttu-id="d8637-120">Una vez agregada una conexión a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> para establecer una conexión al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d8637-120">After a connection has been added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="d8637-121">A este método se le llama en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d8637-121">This method is called during both design and execution time.</span></span> <span data-ttu-id="d8637-122">El componente debería establecer una conexión con el administrador de conexiones especificado por la conexión en tiempo de ejecución y, como consecuencia, con el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d8637-122">The component should establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span>

 <span data-ttu-id="d8637-123">Una vez establecida la conexión, el componente debe almacenarla en caché y liberarla al llamar al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-123">After the connection is established, it should be cached internally by the component and released when the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called.</span></span> <span data-ttu-id="d8637-124">Al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> se le llama en tiempo de diseño y en tiempo de ejecución, como el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-124">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called at design and execution time, like the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method.</span></span> <span data-ttu-id="d8637-125">Los programadores invalidan este método y liberan la conexión establecida por el componente durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span>

 <span data-ttu-id="d8637-126">En el ejemplo de código siguiente se muestra un componente que conecta a una conexión de ADO.NET en el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> y cierra la conexión en el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-126">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method and closes the connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method.</span></span>

```csharp
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
Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If Not IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) Then

        Dim cm As ConnectionManager = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject, ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If Not IsNothing(sqlConnection) And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="d8637-127">Crear y configurar columnas de salida</span><span class="sxs-lookup"><span data-stu-id="d8637-127">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="d8637-128">Las columnas de salida de un componente de origen reflejan las columnas del origen de datos externo que el componente agrega al flujo de datos durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="d8637-128">The output columns of a source component reflect the columns from the external data source that the component adds to the data flow during execution.</span></span> <span data-ttu-id="d8637-129">En tiempo de diseño, agrega columnas de salida una vez configurado el componente para que se conecte a un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d8637-129">At design time, you add output columns after the component has been configured to connect to an external data source.</span></span> <span data-ttu-id="d8637-130">El método en tiempo de diseño que un componente utiliza para agregar las columnas a su colección de salida puede variar en función de las necesidades del componente, aunque no se deben agregar durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-130">The design-time method that a component uses to add the columns to its output collection can vary based on the needs of the component, although they should not be added during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="d8637-131">Por ejemplo, un componente que contiene una instrucción SQL en una propiedad personalizada que controla el conjunto de datos para el componente puede agregar sus columnas de salida durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-131">For example, a component that contains a SQL statement in a custom property that controls the data set for the component may add its output columns during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A> method.</span></span> <span data-ttu-id="d8637-132">El componente comprueba si incluye una conexión almacenada en la caché, y, si es así, se conecta al origen de datos y genera sus columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="d8637-132">The component checks to see whether it has a cached connection, and, if it does, connects to the data source and generates its output columns.</span></span>

 <span data-ttu-id="d8637-133">Una vez creada una columna de salida, establezca sus propiedades de tipo de datos llamando al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-133">After an output column has been created, set its data type properties by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="d8637-134">Este método es necesario porque las propiedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> son de solo lectura y cada propiedad depende de los valores de la otra.</span><span class="sxs-lookup"><span data-stu-id="d8637-134">This method is necessary because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are read-only and each property is dependent on the settings of the other.</span></span> <span data-ttu-id="d8637-135">Este método impone la necesidad de que estos valores se establezcan de forma coherente y la tarea de flujo de datos valida que se establezcan correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8637-135">This method enforces the need for these values to be set consistently, and the data flow task validates that they are set correctly.</span></span>

 <span data-ttu-id="d8637-136">El <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> de la columna determina los valores que se establecen para otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="d8637-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="d8637-137">En la tabla siguiente se muestran los requisitos de las propiedades dependientes para cada <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-137">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="d8637-138">En los tipos de datos no enumerados, sus propiedades dependientes se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="d8637-138">The data types not listed have their dependent properties set to zero.</span></span>

|<span data-ttu-id="d8637-139">DataType</span><span class="sxs-lookup"><span data-stu-id="d8637-139">DataType</span></span>|<span data-ttu-id="d8637-140">Length</span><span class="sxs-lookup"><span data-stu-id="d8637-140">Length</span></span>|<span data-ttu-id="d8637-141">Escala</span><span class="sxs-lookup"><span data-stu-id="d8637-141">Scale</span></span>|<span data-ttu-id="d8637-142">Precision</span><span class="sxs-lookup"><span data-stu-id="d8637-142">Precision</span></span>|<span data-ttu-id="d8637-143">CodePage</span><span class="sxs-lookup"><span data-stu-id="d8637-143">CodePage</span></span>|
|--------------|------------|-----------|---------------|--------------|
|<span data-ttu-id="d8637-144">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="d8637-144">DT_DECIMAL</span></span>|<span data-ttu-id="d8637-145">0</span><span class="sxs-lookup"><span data-stu-id="d8637-145">0</span></span>|<span data-ttu-id="d8637-146">Mayor que 0 y menor o igual que 28.</span><span class="sxs-lookup"><span data-stu-id="d8637-146">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="d8637-147">0</span><span class="sxs-lookup"><span data-stu-id="d8637-147">0</span></span>|<span data-ttu-id="d8637-148">0</span><span class="sxs-lookup"><span data-stu-id="d8637-148">0</span></span>|
|<span data-ttu-id="d8637-149">DT_CY</span><span class="sxs-lookup"><span data-stu-id="d8637-149">DT_CY</span></span>|<span data-ttu-id="d8637-150">0</span><span class="sxs-lookup"><span data-stu-id="d8637-150">0</span></span>|<span data-ttu-id="d8637-151">0</span><span class="sxs-lookup"><span data-stu-id="d8637-151">0</span></span>|<span data-ttu-id="d8637-152">0</span><span class="sxs-lookup"><span data-stu-id="d8637-152">0</span></span>|<span data-ttu-id="d8637-153">0</span><span class="sxs-lookup"><span data-stu-id="d8637-153">0</span></span>|
|<span data-ttu-id="d8637-154">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="d8637-154">DT_NUMERIC</span></span>|<span data-ttu-id="d8637-155">0</span><span class="sxs-lookup"><span data-stu-id="d8637-155">0</span></span>|<span data-ttu-id="d8637-156">Mayor que 0 y menor o igual que 28 y menor que Precisión.</span><span class="sxs-lookup"><span data-stu-id="d8637-156">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="d8637-157">Mayor o igual que 1 y menor o igual que 38.</span><span class="sxs-lookup"><span data-stu-id="d8637-157">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="d8637-158">0</span><span class="sxs-lookup"><span data-stu-id="d8637-158">0</span></span>|
|<span data-ttu-id="d8637-159">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="d8637-159">DT_BYTES</span></span>|<span data-ttu-id="d8637-160">Mayor que 0.</span><span class="sxs-lookup"><span data-stu-id="d8637-160">Greater than 0.</span></span>|<span data-ttu-id="d8637-161">0</span><span class="sxs-lookup"><span data-stu-id="d8637-161">0</span></span>|<span data-ttu-id="d8637-162">0</span><span class="sxs-lookup"><span data-stu-id="d8637-162">0</span></span>|<span data-ttu-id="d8637-163">0</span><span class="sxs-lookup"><span data-stu-id="d8637-163">0</span></span>|
|<span data-ttu-id="d8637-164">DT_STR</span><span class="sxs-lookup"><span data-stu-id="d8637-164">DT_STR</span></span>|<span data-ttu-id="d8637-165">Mayor que 0 y menor que 8000.</span><span class="sxs-lookup"><span data-stu-id="d8637-165">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="d8637-166">0</span><span class="sxs-lookup"><span data-stu-id="d8637-166">0</span></span>|<span data-ttu-id="d8637-167">0</span><span class="sxs-lookup"><span data-stu-id="d8637-167">0</span></span>|<span data-ttu-id="d8637-168">Distinto de 0 y una página de códigos válida.</span><span class="sxs-lookup"><span data-stu-id="d8637-168">Not 0, and a valid code page.</span></span>|
|<span data-ttu-id="d8637-169">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="d8637-169">DT_WSTR</span></span>|<span data-ttu-id="d8637-170">Mayor que 0 y menor que 4.000.</span><span class="sxs-lookup"><span data-stu-id="d8637-170">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="d8637-171">0</span><span class="sxs-lookup"><span data-stu-id="d8637-171">0</span></span>|<span data-ttu-id="d8637-172">0</span><span class="sxs-lookup"><span data-stu-id="d8637-172">0</span></span>|<span data-ttu-id="d8637-173">0</span><span class="sxs-lookup"><span data-stu-id="d8637-173">0</span></span>|

 <span data-ttu-id="d8637-174">Puesto que las restricciones en las propiedades de tipo de datos se basan en el tipo de datos de la columna de salida, debe elegir el tipo de datos de [!INCLUDE[ssIS](../../includes/ssis-md.md)] correcto al trabajar con tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="d8637-174">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="d8637-175">La clase base proporciona tres métodos del asistente, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, para ayudar a los programadores de componentes administrados a seleccionar un tipo de datos de [!INCLUDE[ssIS](../../includes/ssis-md.md)] dado un tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="d8637-175">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, to assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="d8637-176">Estos métodos convierten los tipos de datos administrados en tipos de datos de [!INCLUDE[ssIS](../../includes/ssis-md.md)] y viceversa.</span><span class="sxs-lookup"><span data-stu-id="d8637-176">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>

 <span data-ttu-id="d8637-177">En el ejemplo de código siguiente se muestra cómo se rellena la colección de columnas de salida de un componente en función del esquema de una tabla.</span><span class="sxs-lookup"><span data-stu-id="d8637-177">The following code example shows how the output column collection of a component is populated based on the schema of a table.</span></span> <span data-ttu-id="d8637-178">Los métodos del asistente de la clase base se utilizan para establecer el tipo de datos de la columna; las propiedades dependientes se establecen en función del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d8637-178">The helper methods of the base class are used to set the data type of the column, and the dependent properties are set based on the data type.</span></span>

```csharp
SqlCommand sqlCommand;

private void CreateColumnsFromDataTable()
{
    // Get the output.
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    // Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll();
    output.ExternalMetadataColumnCollection.RemoveAll();

    this.sqlCommand = sqlConnection.CreateCommand();
    this.sqlCommand.CommandType = CommandType.Text;
    this.sqlCommand.CommandText = (string)ComponentMetaData.CustomPropertyCollection["SqlStatement"].Value;
    SqlDataReader schemaReader = this.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly);
    DataTable dataTable = schemaReader.GetSchemaTable();

    // Walk the columns in the schema, 
    // and for each data column create an output column and an external metadata column.
    foreach (DataRow row in dataTable.Rows)
    {
        IDTSOutputColumn100 outColumn = output.OutputColumnCollection.New();
        IDTSExternalMetadataColumn100 exColumn = output.ExternalMetadataColumnCollection.New();

        // Set column data type properties.
        bool isLong = false;
        DataType dt = DataRecordTypeToBufferType((Type)row["DataType"]);
        dt = ConvertBufferDataTypeToFitManaged(dt, ref isLong);
        int length = 0;
        int precision = (short)row["NumericPrecision"];
        int scale = (short)row["NumericScale"];
        int codepage = dataTable.Locale.TextInfo.ANSICodePage;

        switch (dt)
        {
            // The length cannot be zero, and the code page property must contain a valid code page.
            case DataType.DT_STR:
            case DataType.DT_TEXT:
                length = precision;
                precision = 0;
                scale = 0;
                break;

            case DataType.DT_WSTR:
                length = precision;
                codepage = 0;
                scale = 0;
                precision = 0;
                break;

            case DataType.DT_BYTES:
                precision = 0;
                scale = 0;
                codepage = 0;
                break;

            case DataType.DT_NUMERIC:
                length = 0;
                codepage = 0;

                if (precision > 38)
                    precision = 38;

                if (scale > 6)
                    scale = 6;
                break;

            case DataType.DT_DECIMAL:
                length = 0;
                precision = 0;
                codepage = 0;
                break;

            default:
                length = 0;
                precision = 0;
                codepage = 0;
                scale = 0;
                break;

        }

        // Set the properties of the output column.
        outColumn.Name = (string)row["ColumnName"];
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage);
    }
}
```

```vb
Private sqlCommand As SqlCommand

Private Sub CreateColumnsFromDataTable()

    ' Get the output.
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    ' Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll()
    output.ExternalMetadataColumnCollection.RemoveAll()

    Me.sqlCommand = sqlConnection.CreateCommand()
    Me.sqlCommand.CommandType = CommandType.Text
    Me.sqlCommand.CommandText = CStr(ComponentMetaData.CustomPropertyCollection("SqlStatement").Value)

    Dim schemaReader As SqlDataReader = Me.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly)
    Dim dataTable As DataTable = schemaReader.GetSchemaTable()

    ' Walk the columns in the schema, 
    ' and for each data column create an output column and an external metadata column.
    For Each row As DataRow In dataTable.Rows

        Dim outColumn As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        Dim exColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()

        ' Set column data type properties.
        Dim isLong As Boolean = False
        Dim dt As DataType = DataRecordTypeToBufferType(CType(row("DataType"), Type))
        dt = ConvertBufferDataTypeToFitManaged(dt, isLong)
        Dim length As Integer = 0
        Dim precision As Integer = CType(row("NumericPrecision"), Short)
        Dim scale As Integer = CType(row("NumericScale"), Short)
        Dim codepage As Integer = dataTable.Locale.TextInfo.ANSICodePage

        Select Case dt

            ' The length cannot be zero, and the code page property must contain a valid code page.
            Case DataType.DT_STR
            Case DataType.DT_TEXT
                length = precision
                precision = 0
                scale = 0

            Case DataType.DT_WSTR
                length = precision
                codepage = 0
                scale = 0
                precision = 0

            Case DataType.DT_BYTES
                precision = 0
                scale = 0
                codepage = 0

            Case DataType.DT_NUMERIC
                length = 0
                codepage = 0

                If precision > 38 Then
                    precision = 38
                End If

                If scale > 6 Then
                    scale = 6
                End If

            Case DataType.DT_DECIMAL
                length = 0
                precision = 0
                codepage = 0

            Case Else
                length = 0
                precision = 0
                codepage = 0
                scale = 0
        End Select

        ' Set the properties of the output column.
        outColumn.Name = CStr(row("ColumnName"))
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage)
    Next
End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="d8637-179">Validar el componente</span><span class="sxs-lookup"><span data-stu-id="d8637-179">Validating the Component</span></span>
 <span data-ttu-id="d8637-180">Debe validar un componente de origen y comprobar que las columnas definidas en sus colecciones de columnas de salida coinciden con las columnas del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d8637-180">You should validate a source component and verify that the columns defined in its output column collections match the columns at the external data source.</span></span> <span data-ttu-id="d8637-181">En ocasiones, la comprobación de las columnas de salida en el origen de datos externo puede resultar imposible, como en un estado desconectado, o cuando es preferible evitar largos viajes de ida y vuelta (round trip) al servidor.</span><span class="sxs-lookup"><span data-stu-id="d8637-181">Sometimes, verifying the output columns against the external data source can be impossible, such as in a disconnected state, or when it is preferable to avoid lengthy round trips to the server.</span></span> <span data-ttu-id="d8637-182">En estas situaciones, las columnas de la salida se pueden seguir validando mediante la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> del objeto de salida.</span><span class="sxs-lookup"><span data-stu-id="d8637-182">In these situations, the columns in the output can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> of the output object.</span></span> <span data-ttu-id="d8637-183">Para obtener más información, vea [Validating a Data Flow Component](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md) (Validación de un componente de flujo de datos).</span><span class="sxs-lookup"><span data-stu-id="d8637-183">For more information, see [Validating a Data Flow Component](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span>

 <span data-ttu-id="d8637-184">Esta colección existe tanto en los objetos de entrada como en los objetos de salida, y se puede rellenar con las columnas del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d8637-184">This collection exists on both input and output objects and you can populate it with the columns from the external data source.</span></span> <span data-ttu-id="d8637-185">Puede utilizar esta colección para validar las columnas de salida cuando el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] está en modo sin conexión, cuando el componente está desconectado o cuando la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="d8637-185">You can use this collection to validate the output columns when [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span> <span data-ttu-id="d8637-186">La colección se debe rellenar por primera vez al mismo tiempo que se crean las columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="d8637-186">The collection should be first populated at the same time that the output columns are created.</span></span> <span data-ttu-id="d8637-187">Agregar columnas de metadatos externas a la colección resulta relativamente fácil porque la columna de metadatos externa debe coincidir inicialmente con la columna de salida.</span><span class="sxs-lookup"><span data-stu-id="d8637-187">Adding external metadata columns to the collection is relatively easy because the external metadata column should initially match the output column.</span></span> <span data-ttu-id="d8637-188">Las propiedades de tipo de datos se deberán haber establecido correctamente y se pueden copiar directamente en el objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100>.</span><span class="sxs-lookup"><span data-stu-id="d8637-188">The data type properties of the column should have already been set correctly, and the properties can be copied directly to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100> object.</span></span>

 <span data-ttu-id="d8637-189">En el siguiente código de ejemplo se agrega una columna de metadatos externa basada en una columna de salida recién creada.</span><span class="sxs-lookup"><span data-stu-id="d8637-189">The following sample code adds an external metadata column that is based on a newly created output column.</span></span> <span data-ttu-id="d8637-190">Se supone que la columna de salida ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="d8637-190">It assumes that the output column has already been created.</span></span>

```csharp
private void CreateExternalMetaDataColumn(IDTSOutput100 output, IDTSOutputColumn100 outputColumn)
{

    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = output.ExternalMetadataColumnCollection.New();
    externalColumn.Name = outputColumn.Name;
    externalColumn.Precision = outputColumn.Precision;
    externalColumn.Length = outputColumn.Length;
    externalColumn.DataType = outputColumn.DataType;
    externalColumn.Scale = outputColumn.Scale;

    // Map the external column to the output column.
    outputColumn.ExternalMetadataColumnID = externalColumn.ID;

}
```

```vb
Private Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumn As IDTSOutputColumn100)

        ' Set the properties of the external metadata column.
        Dim externalColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()
        externalColumn.Name = outputColumn.Name
        externalColumn.Precision = outputColumn.Precision
        externalColumn.Length = outputColumn.Length
        externalColumn.DataType = outputColumn.DataType
        externalColumn.Scale = outputColumn.Scale

        ' Map the external column to the output column.
        outputColumn.ExternalMetadataColumnID = externalColumn.ID

    End Sub
```

## <a name="run-time"></a><span data-ttu-id="d8637-191">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d8637-191">Run Time</span></span>
 <span data-ttu-id="d8637-192">Durante la ejecución, los componentes agregan filas a los búferes de salida que crea la tarea de flujo de datos y que se proporcionan al componente en <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-192">During execution, components add rows to output buffers that are created by the data flow task and provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="d8637-193">El método, al que se llama una vez para los componentes de origen, recibe un búfer de salida para cada objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> del componente conectado a un componente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="d8637-193">Called once for source components, the method receives an output buffer for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the component that is connected to a downstream component.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="d8637-194">Localizar columnas en el búfer</span><span class="sxs-lookup"><span data-stu-id="d8637-194">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="d8637-195">El búfer de salida de un componente contiene las columnas definidas por el componente y cualquier columna agregada a la salida de un componente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="d8637-195">The output buffer for a component contains the columns defined by the component and any columns added to the output of a downstream component.</span></span> <span data-ttu-id="d8637-196">Por ejemplo, si un componente de origen proporciona tres columnas en su salida y el componente siguiente agrega una cuarta columna de salida, el búfer de salida que proporciona el componente de origen contiene estas cuatro columnas.</span><span class="sxs-lookup"><span data-stu-id="d8637-196">For example, if a source component provides three columns in its output, and the next component adds a fourth output column, the output buffer provided for use by the source component contains these four columns.</span></span>

 <span data-ttu-id="d8637-197">El índice de la columna de salida de la colección de columnas de salida no define el orden de las columnas de una fila de búfer.</span><span class="sxs-lookup"><span data-stu-id="d8637-197">The order of the columns in a buffer row is not defined by the index of the output column in the output column collection.</span></span> <span data-ttu-id="d8637-198">Una columna de salida solo se puede localizar de forma precisa en una fila de búfer mediante el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-198">An output column can only be accurately located in a buffer row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="d8637-199">Este método localiza la columna con el identificador de linaje especificado en el búfer especificado y devuelve su ubicación en la fila.</span><span class="sxs-lookup"><span data-stu-id="d8637-199">This method locates the column with the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="d8637-200">Los índices de las columnas de salida se encuentran normalmente en el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> y se almacenan para su uso durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-200">The indexes of the output columns are typically located in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and stored for use during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span>

 <span data-ttu-id="d8637-201">En el ejemplo de código siguiente se busca la ubicación de las columnas de salida del búfer de salida durante una llamada a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> y se almacenan en una estructura interna.</span><span class="sxs-lookup"><span data-stu-id="d8637-201">The following code example finds the location of the output columns in the output buffer during a call to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, and stores them in an internal structure.</span></span> <span data-ttu-id="d8637-202">El nombre de la columna también se almacena en la estructura y se utiliza en el ejemplo de código para el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> en la sección siguiente de este tema.</span><span class="sxs-lookup"><span data-stu-id="d8637-202">The name of the column is also stored in the structure and is used in the code example for the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method in the next section of this topic.</span></span>

```csharp
ArrayList columnInformation;

private struct ColumnInfo
{
    public int BufferColumnIndex;
    public string ColumnName;
}

public override void PreExecute()
{
    this.columnInformation = new ArrayList();
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    foreach (IDTSOutputColumn100 col in output.OutputColumnCollection)
    {
        ColumnInfo ci = new ColumnInfo();
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID);
        ci.ColumnName = col.Name;
        columnInformation.Add(ci);
    }
}
```

```vb
Public Overrides Sub PreExecute()

    Me.columnInformation = New ArrayList()
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    For Each col As IDTSOutputColumn100 In output.OutputColumnCollection

        Dim ci As ColumnInfo = New ColumnInfo()
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID)
        ci.ColumnName = col.Name
        columnInformation.Add(ci)
    Next
End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="d8637-203">Procesar las filas</span><span class="sxs-lookup"><span data-stu-id="d8637-203">Processing Rows</span></span>
 <span data-ttu-id="d8637-204">Las filas se agregan al búfer de salida llamando al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A>, que crea una nueva fila de búfer con valores vacíos en sus columnas.</span><span class="sxs-lookup"><span data-stu-id="d8637-204">Rows are added to the output buffer by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method, which creates a new buffer row with empty values in its columns.</span></span> <span data-ttu-id="d8637-205">A continuación, el componente asigna los valores a las columnas individuales.</span><span class="sxs-lookup"><span data-stu-id="d8637-205">The component then assigns values to the individual columns.</span></span> <span data-ttu-id="d8637-206">La tarea de flujo de datos crea y supervisa los búferes de salida que se proporcionan a un componente.</span><span class="sxs-lookup"><span data-stu-id="d8637-206">The output buffers provided to a component are created and monitored by the data flow task.</span></span> <span data-ttu-id="d8637-207">Cuando se llenan, las filas del búfer se mueven al componente siguiente.</span><span class="sxs-lookup"><span data-stu-id="d8637-207">As they become full, the rows in the buffer are moved to the next component.</span></span> <span data-ttu-id="d8637-208">No hay ninguna manera de determinar cuándo se ha enviado un lote de filas al componente siguiente porque el movimiento de filas de la tarea de flujo de datos es transparente para el programador de componentes y la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> siempre es cero en los búferes de salida.</span><span class="sxs-lookup"><span data-stu-id="d8637-208">There is no way to determine when a batch of rows has been sent to the next component because the movement of rows by the data flow task is transparent to the component developer, and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> property is always zero on output buffers.</span></span> <span data-ttu-id="d8637-209">Cuando un componente de origen ha terminado de agregar filas a su búfer de salida, lo notifica a la tarea de flujo de datos mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> y las filas restantes del búfer se pasan al componente siguiente.</span><span class="sxs-lookup"><span data-stu-id="d8637-209">When a source component is finished adding rows to its output buffer, it notifies the data flow task by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, and the remaining rows in the buffer are passed to the next component.</span></span>

 <span data-ttu-id="d8637-210">Mientras el componente de origen lee las filas del origen de datos externo, puede actualizar los contadores de rendimiento "Filas leídas" o "Bytes BLOB leídos" mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-210">While the source component reads rows from the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="d8637-211">Para más información, consulte [Performance Counters](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d8637-211">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="d8637-212">En el ejemplo de código siguiente se muestra un componente que agrega filas a un búfer de salida en <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8637-212">The following code example shows a component that adds rows to an output buffer in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="d8637-213">Los índices de las columnas de salida del búfer se localizaron con <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> del ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="d8637-213">The indexes of the output columns in the buffer were located using <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the previous code example.</span></span>

```csharp
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
{
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
    PipelineBuffer buffer = buffers[0];

    SqlDataReader dataReader = sqlCommand.ExecuteReader();

    // Loop over the rows in the DataReader, 
    // and add them to the output buffer.
    while (dataReader.Read())
    {
        // Add a row to the output buffer.
        buffer.AddRow();

        for (int x = 0; x < columnInformation.Count; x++)
        {
            ColumnInfo ci = (ColumnInfo)columnInformation[x];
            int ordinal = dataReader.GetOrdinal(ci.ColumnName);

            if (dataReader.IsDBNull(ordinal))
                buffer.SetNull(ci.BufferColumnIndex);
            else
            {
                buffer[ci.BufferColumnIndex] = dataReader[ci.ColumnName];
            }
        }
    }
    buffer.SetEndOfRowset();
}
```

```vb
Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim buffer As PipelineBuffer = buffers(0)

    Dim dataReader As SqlDataReader = sqlCommand.ExecuteReader()

    ' Loop over the rows in the DataReader, 
    ' and add them to the output buffer.
    While (dataReader.Read())

        ' Add a row to the output buffer.
        buffer.AddRow()

        For x As Integer = 0 To columnInformation.Count

            Dim ci As ColumnInfo = CType(columnInformation(x), ColumnInfo)

            Dim ordinal As Integer = dataReader.GetOrdinal(ci.ColumnName)

            If (dataReader.IsDBNull(ordinal)) Then
                buffer.SetNull(ci.BufferColumnIndex)
            Else
                buffer(ci.BufferColumnIndex) = dataReader(ci.ColumnName)

            End If
        Next

    End While

    buffer.SetEndOfRowset()
End Sub
```

## <a name="sample"></a><span data-ttu-id="d8637-214">Muestra</span><span class="sxs-lookup"><span data-stu-id="d8637-214">Sample</span></span>
 <span data-ttu-id="d8637-215">En el ejemplo siguiente se muestra un componente de origen simple que utiliza un administrador de conexiones de archivos para cargar el contenido binario de los archivos en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d8637-215">The following sample shows a simple source component that uses a File connection manager to load the binary contents of files into the data flow.</span></span> <span data-ttu-id="d8637-216">En este ejemplo no se muestran todos los métodos ni funcionalidad tratados en este tema.</span><span class="sxs-lookup"><span data-stu-id="d8637-216">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="d8637-217">Muestra los métodos importantes que cada componente de origen personalizado debe invalidar, pero no contiene código para la validación en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="d8637-217">It demonstrates the important methods that every custom source component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace BlobSrc
{
  [DtsPipelineComponent(DisplayName = "BLOB Inserter Source", Description = "Inserts files into the data flow as BLOBs")]
  public class BlobSrc : PipelineComponent
  {
    IDTSConnectionManager100 m_ConnMgr;
    int m_FileNameColumnIndex = -1;
    int m_FileBlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
      output.Name = "BLOB File Inserter Output";

      IDTSOutputColumn100 column = output.OutputColumnCollection.New();
      column.Name = "FileName";
      column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0);

      column = output.OutputColumnCollection.New();
      column.Name = "FileBLOB";
      column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0);

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_ConnMgr = conn.ConnectionManager;
    }

    public override void ReleaseConnections()
    {
      m_ConnMgr = null;
    }

    public override void PreExecute()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

      m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[0].LineageID);
      m_FileBlobColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[1].LineageID);
    }

    public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
    {
      string strFileName = (string)m_ConnMgr.AcquireConnection(null);

      while (strFileName != null)
      {
        buffers[0].AddRow();

        buffers[0].SetString(m_FileNameColumnIndex, strFileName);

        FileInfo fileInfo = new FileInfo(strFileName);
        byte[] fileData = new byte[fileInfo.Length];
        FileStream fs = new FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read);
        fs.Read(fileData, 0, fileData.Length);

        buffers[0].AddBlobData(m_FileBlobColumnIndex, fileData);

        strFileName = (string)m_ConnMgr.AcquireConnection(null);
      }

      buffers[0].SetEndOfRowset();
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper 
Namespace BlobSrc 

 <DtsPipelineComponent(DisplayName="BLOB Inserter Source", Description="Inserts files into the data flow as BLOBs")> _ 
 Public Class BlobSrc 
 Inherits PipelineComponent 
   Private m_ConnMgr As IDTSConnectionManager100 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_FileBlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New 
     output.Name = "BLOB File Inserter Output" 
     Dim column As IDTSOutputColumn100 = output.OutputColumnCollection.New 
     column.Name = "FileName" 
     column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0) 
     column = output.OutputColumnCollection.New 
     column.Name = "FileBLOB" 
     column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0) 
     Dim conn As IDTSRuntimeConnection90 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_ConnMgr = conn.ConnectionManager 
   End Sub 

   Public  Overrides Sub ReleaseConnections() 
     m_ConnMgr = Nothing 
   End Sub 

   Public  Overrides Sub PreExecute() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0) 
     m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(0).LineageID), Integer) 
     m_FileBlobColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(1).LineageID), Integer) 
   End Sub 

   Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer()) 
     Dim strFileName As String = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     While Not (strFileName Is Nothing) 
       buffers(0).AddRow 
       buffers(0).SetString(m_FileNameColumnIndex, strFileName) 
       Dim fileInfo As FileInfo = New FileInfo(strFileName) 
       Dim fileData(fileInfo.Length) As Byte 
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read) 
       fs.Read(fileData, 0, fileData.Length) 
       buffers(0).AddBlobData(m_FileBlobColumnIndex, fileData) 
       strFileName = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     End While 
     buffers(0).SetEndOfRowset 
   End Sub 
 End Class 
End Namespace
```

<span data-ttu-id="d8637-218">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d8637-218">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d8637-219">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="d8637-219">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d8637-220">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="d8637-220">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d8637-221">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="d8637-221">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8637-222">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8637-222">See Also</span></span>
 <span data-ttu-id="d8637-223">[Desarrollar un componente de destino personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [crear un origen con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="d8637-223">[Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span></span>


