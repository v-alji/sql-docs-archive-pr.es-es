---
title: Implementar metadatos externos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disconnected validation [Integration Services]
- connected validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- metadata [Integration Services]
- data flow components [Integration Services], validating
- data flow components [Integration Services], external metadata
- custom data flow components [Integration Services], external metadata
- external metadata [Integration Services]
ms.assetid: 8f5bd3ed-3e79-43a4-b6c1-435e4c2cc8cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a6b77229c528bc08057e662a4b3761d1daf732f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744789"
---
# <a name="implementing-external-metadata"></a><span data-ttu-id="eb3ba-102">Implementar metadatos externos</span><span class="sxs-lookup"><span data-stu-id="eb3ba-102">Implementing External Metadata</span></span>
  <span data-ttu-id="eb3ba-103">Cuando un componente está desconectado de su origen de datos, puede validar las columnas de las colecciones de columnas de entrada y de resultados con las columnas en su origen de datos externo mediante la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100>.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-103">When a component is disconnected from its data source, you can validate the columns in the input and output column collections against the columns at its external data source by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100> interface.</span></span> <span data-ttu-id="eb3ba-104">Esta interfaz permite mantener una instantánea de las columnas en el origen de datos externo y asignar estas columnas a las columnas de la colección de columnas de entrada y de resultados del componente.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-104">This interface lets you maintain a snapshot of the columns at the external data source and map these columns to the columns in the input and output column collection of the component.</span></span>  
  
 <span data-ttu-id="eb3ba-105">La implementación de columnas de metadatos externos agrega un nivel de sobrecarga y complejidad al desarrollo del componente, porque debe mantener y validar una colección de columnas adicional, pero la capacidad de evitar los caros viajes de ida y vuelta (round trip) al servidor para la validación puede hacer que este trabajo de desarrollo valga la pena.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-105">Implementing external metadata columns adds a layer of overhead and complexity to component development, because you must maintain and validate against an additional column collection, but the ability to avoid expensive round trips to the server for validation may make this development work worthwhile.</span></span>  
  
## <a name="populating-external-metadata-columns"></a><span data-ttu-id="eb3ba-106">Rellenar columnas de metadatos externos</span><span class="sxs-lookup"><span data-stu-id="eb3ba-106">Populating External Metadata Columns</span></span>  
 <span data-ttu-id="eb3ba-107">Las columnas de metadatos externos se agregan normalmente a la colección cuando se crea la columna de entrada o de resultados correspondiente.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-107">External metadata columns are typically added to the collection when the corresponding input or output column is created.</span></span> <span data-ttu-id="eb3ba-108">Para crear una nueva columna se llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-108">New columns are created by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A> method.</span></span> <span data-ttu-id="eb3ba-109">Las propiedades de la columna se establecen después para coincidir con el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-109">The properties of the column are then set to match the external data source.</span></span>  
  
 <span data-ttu-id="eb3ba-110">Para asignar la columna de metadatos externos a la columna de entrada o de resultados correspondiente se asigna el identificador de la columna de metadatos externos a la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> de la columna de entrada o de resultados.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-110">The external metadata column is mapped to the corresponding input or output column by assigning the ID of the external metadata column to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property of the input or output column.</span></span> <span data-ttu-id="eb3ba-111">Esto le permite buscar con facilidad la columna de metadatos externos para una columna de entrada o de resultados concreta utilizando el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> de la colección.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-111">This lets you locate the external metadata column easily for a specific input or output column by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> method of the collection.</span></span>  
  
 <span data-ttu-id="eb3ba-112">En el ejemplo siguiente se muestra cómo crear una columna de metadatos externos y después asignar la columna a una columna de resultados estableciendo la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-112">The following example shows how to create an external metadata column and then map the column to an output column by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property.</span></span>  
  
```csharp  
public void CreateExternalMetaDataColumn(IDTSOutput100 output, int outputColumnID )  
{  
    IDTSOutputColumn100 oColumn = output.OutputColumnCollection.GetObjectByID(outputColumnID);  
    IDTSExternalMetadataColumn100 eColumn = output.ExternalMetadataColumnCollection.New();  
  
    eColumn.DataType = oColumn.DataType;  
    eColumn.Precision = oColumn.Precision;  
    eColumn.Scale = oColumn.Scale;  
    eColumn.Length = oColumn.Length;  
    eColumn.CodePage = oColumn.CodePage;  
  
    oColumn.ExternalMetadataColumnID = eColumn.ID;  
}  
```  
  
```vb  
Public Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumnID As Integer)   
 Dim oColumn As IDTSOutputColumn100 = output.OutputColumnCollection.GetObjectByID(outputColumnID)   
 Dim eColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New   
 eColumn.DataType = oColumn.DataType   
 eColumn.Precision = oColumn.Precision   
 eColumn.Scale = oColumn.Scale   
 eColumn.Length = oColumn.Length   
 eColumn.CodePage = oColumn.CodePage   
 oColumn.ExternalMetadataColumnID = eColumn.ID   
End Sub  
```  
  
## <a name="validating-with-external-metadata-columns"></a><span data-ttu-id="eb3ba-113">Validar con columnas de metadatos externos</span><span class="sxs-lookup"><span data-stu-id="eb3ba-113">Validating with External Metadata Columns</span></span>  
 <span data-ttu-id="eb3ba-114">La validación requiere pasos adicionales para los componentes que mantienen una colección de columnas de metadatos externos, porque debe validar una colección de columnas adicional.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-114">Validation requires additional steps for components that maintain an external metadata column collection, because you must validate against an additional collection of columns.</span></span> <span data-ttu-id="eb3ba-115">La validación se puede dividir en validación con conexión o validación sin conexión.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-115">Validation can be divided into connected validation or disconnected validation.</span></span>  
  
### <a name="connected-validation"></a><span data-ttu-id="eb3ba-116">Validación con conexión</span><span class="sxs-lookup"><span data-stu-id="eb3ba-116">Connected Validation</span></span>  
 <span data-ttu-id="eb3ba-117">Cuando un componente está conectado a un origen de datos externo, las columnas de las colecciones de entrada o de salida se comprueban directamente con el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-117">When a component is connected to an external data source, the columns in the input or output collections are verified directly against the external data source.</span></span> <span data-ttu-id="eb3ba-118">Además, se deben validar las columnas de la recopilación de metadatos externos.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-118">Additionally, the columns in the external metadata collection must be validated.</span></span> <span data-ttu-id="eb3ba-119">Esto es necesario porque la colección de metadatos externos se puede modificar utilizando el **Editor avanzado** de [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], y los cambios realizados en la colección no son detectables.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-119">This is required because the external metadata collection can be modified by using the **Advanced Editor** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and changes made to the collection are not detectable.</span></span> <span data-ttu-id="eb3ba-120">Por consiguiente, cuando se está conectado, los componentes deben asegurarse de que las columnas de la colección de columnas de metadatos externos continúan reflejando las columnas en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-120">Therefore, when connected, components must make sure that the columns in the external metadata column collection continue to reflect the columns at the external data source.</span></span>  
  
 <span data-ttu-id="eb3ba-121">Puede ocultar la colección de metadatos externos en el **editor avanzado** estableciendo la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> propiedad de la colección en `false` .</span><span class="sxs-lookup"><span data-stu-id="eb3ba-121">You may choose to hide the external metadata collection in the **Advanced Editor** by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> property of the collection to `false`.</span></span> <span data-ttu-id="eb3ba-122">No obstante, esto también oculta la pestaña **Asignación de columnas** del editor, que permite a los usuarios asignar las columnas de la colección de entrada o de salida a las columnas de la colección de columnas de metadatos externos.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-122">However this also hides the **Column Mapping** tab of the editor, which lets users map columns from the input or output collection to the columns in the external metadata column collection.</span></span> <span data-ttu-id="eb3ba-123">El establecimiento de esta propiedad en `false` no impide que los desarrolladores modifiquen la colección mediante programación, pero proporciona un nivel de protección para la colección de columnas de metadatos externos de un componente que se utiliza exclusivamente en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb3ba-123">Setting this property to `false` does not prevent developers from programmatically modifying the collection, but it does provide a level of protection for the external metadata column collection of a component that is used exclusively in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="disconnected-validation"></a><span data-ttu-id="eb3ba-124">Validación sin conexión</span><span class="sxs-lookup"><span data-stu-id="eb3ba-124">Disconnected Validation</span></span>  
 <span data-ttu-id="eb3ba-125">Cuando un componente está desconectado de un origen de datos externo, se simplifica la validación porque las columnas de la colección de entrada o de salida se comprueban directamente con las columnas de la recopilación de metadatos externos y no con el origen externo.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-125">When a component is disconnected from an external data source, validation is simplified because the columns in the input or output collection are verified directly against the columns in the external metadata collection and not against the external source.</span></span> <span data-ttu-id="eb3ba-126">Un componente debe realizar la validación sin conexión cuando no se ha establecido la conexión a su origen de datos externo o cuando la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-126">A component should perform disconnected validation when the connection to its external data source has not been established, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="eb3ba-127">En el ejemplo de código siguiente se muestra una implementación de un componente que realiza la validación con su colección de columnas de metadatos externos.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-127">The following code example demonstrates an implementation of a component that performs validation against its external metadata column collection.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    if( this.isConnected && ComponentMetaData.ValidateExternalMetaData )  
    {  
        // TODO: Perform connected validation.  
    }  
    else  
    {  
        // TODO: Perform disconnected validation.  
    }  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
 If Me.isConnected AndAlso ComponentMetaData.ValidateExternalMetaData Then   
  ' TODO: Perform connected validation.  
 Else   
  ' TODO: Perform disconnected validation.  
 End If   
End Function  
```  
  
<span data-ttu-id="eb3ba-128">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="eb3ba-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="eb3ba-129">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="eb3ba-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="eb3ba-130">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="eb3ba-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="eb3ba-131">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="eb3ba-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3ba-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb3ba-132">See Also</span></span>  
 [<span data-ttu-id="eb3ba-133">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="eb3ba-133">Data Flow</span></span>](../../data-flow/data-flow.md)  
  
  
