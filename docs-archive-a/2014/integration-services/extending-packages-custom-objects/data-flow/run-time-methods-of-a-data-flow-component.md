---
title: Métodos en tiempo de ejecución de un componente de flujo de datos | Microsoft Docs
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
- run-time [Integration Services]
- data flow components [Integration Services], run-time methods
ms.assetid: fd9e4317-18dd-43af-bbdc-79db32183ac4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df0afe4c29044541c5a57aa3a466283ab4fe4fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747143"
---
# <a name="run-time-methods-of-a-data-flow-component"></a><span data-ttu-id="b6534-102">Métodos en tiempo de ejecución de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="b6534-102">Run-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="b6534-103">En tiempo de ejecución, la tarea de flujo de datos examina la secuencia de componentes, prepara un plan de ejecución y administra un grupo de subprocesos de trabajo que ejecutan el plan de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6534-103">At run time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="b6534-104">La tarea carga filas de datos de los orígenes, las procesa a través de las transformaciones y, a continuación, las guarda en los destinos.</span><span class="sxs-lookup"><span data-stu-id="b6534-104">The task loads rows of data from sources, processes them through transformations, then saves them to destinations.</span></span>  
  
## <a name="sequence-of-method-execution"></a><span data-ttu-id="b6534-105">Secuencia de ejecución del método</span><span class="sxs-lookup"><span data-stu-id="b6534-105">Sequence of Method Execution</span></span>  
 <span data-ttu-id="b6534-106">Durante la ejecución de un componente de flujo de datos, se llama a un subconjunto de métodos en la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="b6534-106">During the execution of a data flow component, a subset of the methods in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is called.</span></span> <span data-ttu-id="b6534-107">Los métodos, y la secuencia en la que se llaman, siempre son los mismos, con la excepción de los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-107">The methods, and the sequence in which they are called, are always the same, with the exception of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="b6534-108">Se llama a estos dos métodos dependiendo de la existencia y configuración de los objetos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> y <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> de un componente.</span><span class="sxs-lookup"><span data-stu-id="b6534-108">These two methods are called based on the existence and configuration of a component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects.</span></span>  
  
 <span data-ttu-id="b6534-109">La lista siguiente muestra los métodos en el orden en el que se llaman durante la ejecución del componente.</span><span class="sxs-lookup"><span data-stu-id="b6534-109">The following list shows the methods in the order in which they are called during component execution.</span></span> <span data-ttu-id="b6534-110">Tenga en cuenta que cuando se llama a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, siempre se llama antes de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-110">Note that <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, when called, is always called before <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrepareForExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PostExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Cleanup%2A>  
  
### <a name="primeoutput-method"></a><span data-ttu-id="b6534-111">Método PrimeOutput</span><span class="sxs-lookup"><span data-stu-id="b6534-111">PrimeOutput Method</span></span>  
 <span data-ttu-id="b6534-112">Se llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> cuando un componente tiene por lo menos una salida, adjuntada a un componente de nivel inferior a través de un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>, y la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> de la salida es cero.</span><span class="sxs-lookup"><span data-stu-id="b6534-112">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called when a component has at least one output, attached to a downstream component through an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, and the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property of the output is zero.</span></span> <span data-ttu-id="b6534-113">Se llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> para los componentes de origen y para las transformaciones con salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="b6534-113">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called for source components and for transformations with asynchronous outputs.</span></span> <span data-ttu-id="b6534-114">A diferencia del método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> que se describe a continuación, cada componente que lo requiere llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> una sola vez.</span><span class="sxs-lookup"><span data-stu-id="b6534-114">Unlike the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method described below, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is only called once for each component that requires it.</span></span>  
  
### <a name="processinput-method"></a><span data-ttu-id="b6534-115">Método ProcessInput</span><span class="sxs-lookup"><span data-stu-id="b6534-115">ProcessInput Method</span></span>  
 <span data-ttu-id="b6534-116">Un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> para los componentes que tienen al menos una salida adjuntada a un componente de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b6534-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for components that have at least one input attached to an upstream component by an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object.</span></span> <span data-ttu-id="b6534-117">Se llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> para los componentes de destino y para las transformaciones con salidas sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="b6534-117">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for destination components and for transformations with synchronous outputs.</span></span> <span data-ttu-id="b6534-118">Se llama a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> varias veces hasta que no hay más filas de componentes de nivel superior que procesar.</span><span class="sxs-lookup"><span data-stu-id="b6534-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> is called repeatedly until there are no more rows to process from upstream components.</span></span>  
  
## <a name="working-with-inputs-and-outputs"></a><span data-ttu-id="b6534-119">Trabajar con entradas y salidas</span><span class="sxs-lookup"><span data-stu-id="b6534-119">Working with Inputs and Outputs</span></span>  
 <span data-ttu-id="b6534-120">En tiempo de ejecución, los componentes de flujo de datos realizan las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6534-120">At run time, data flow components perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b6534-121">Los componentes de origen agregan filas.</span><span class="sxs-lookup"><span data-stu-id="b6534-121">Source components add rows.</span></span>  
  
-   <span data-ttu-id="b6534-122">Los componentes de transformación con salidas sincrónicas reciben las filas que proporcionan los componentes de origen.</span><span class="sxs-lookup"><span data-stu-id="b6534-122">Transformation components with synchronous outputs receive rows provided by source components.</span></span>  
  
-   <span data-ttu-id="b6534-123">Los componentes de transformación con salidas asincrónicas reciben filas y agregan filas.</span><span class="sxs-lookup"><span data-stu-id="b6534-123">Transformation components with asynchronous outputs receive rows and add rows.</span></span>  
  
-   <span data-ttu-id="b6534-124">Los componentes de destino reciben filas y, a continuación, las cargan en un destino.</span><span class="sxs-lookup"><span data-stu-id="b6534-124">Destination components receive rows and then load them into a destination.</span></span>  
  
 <span data-ttu-id="b6534-125">Durante la ejecución, la tarea de flujo de datos asigna los objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> que contienen todas las columnas definidas en las colecciones de columna de salida de una secuencia de componentes.</span><span class="sxs-lookup"><span data-stu-id="b6534-125">During execution, the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain all the columns defined in the output column collections of a sequence of components.</span></span> <span data-ttu-id="b6534-126">Por ejemplo, si uno de cada cuatro componentes en una secuencia del flujo de datos agrega una columna de salida a su colección de columna de salida, el búfer que se proporciona a cada componente contiene cuatro columnas, una por cada columna de salida por componente.</span><span class="sxs-lookup"><span data-stu-id="b6534-126">For example, if each of four components in a data flow sequence adds one output column to its output column collection,the buffer that is provided to each component contains four columns, one for each output column per component.</span></span> <span data-ttu-id="b6534-127">Debido a este comportamiento, un componente recibe a veces búferes que contienen columnas que no usará el componente.</span><span class="sxs-lookup"><span data-stu-id="b6534-127">Because of this behavior, a component sometimes receives buffers that contain columns it does not use.</span></span>  
  
 <span data-ttu-id="b6534-128">Puesto que los búferes que recibe su componente pueden contener columnas que el componente no usará, busque las columnas que desea usar en las colecciones de columna de entrada y salida de su componente en el búfer que la tarea de flujo de datos proporciona al componente.</span><span class="sxs-lookup"><span data-stu-id="b6534-128">Since the buffers received by your component may contain columns that the component will not use, you must locate the columns that you want to use in your component's input and output column collections in the buffer provided to the component by the data flow task.</span></span> <span data-ttu-id="b6534-129">Para ello, use el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-129">You do this by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property.</span></span> <span data-ttu-id="b6534-130">Por razones de rendimiento, esta tarea normalmente se realiza durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, en lugar de en <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-130">For performance reasons, this task is ordinarily performed during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, rather than in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
 <span data-ttu-id="b6534-131">Se llama a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> antes que a los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, y es la primera oportunidad para que un componente realice esta tarea después de que <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> pase a estar disponible para el componente.</span><span class="sxs-lookup"><span data-stu-id="b6534-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods, and is the first opportunity for a component to perform this work after the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> becomes available to the component.</span></span> <span data-ttu-id="b6534-132">Durante este método, el componente debería buscar sus columnas en los búferes y almacenar internamente esta información, de manera que las columnas se puedan usar en cualquiera de los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-132">During this method, the component should locate its columns in the buffers and store this information internally so the columns can be used in either the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span>  
  
 <span data-ttu-id="b6534-133">En el siguiente ejemplo de código se muestra cómo un componente de transformación con una salida sincrónica busca sus columnas de entrada en el búfer durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-133">The following code example demonstrates how a transformation component with a synchronous output locates its input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span>  
  
```csharp  
private int []bufferColumnIndex;  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    bufferColumnIndex = new int[input.InputColumnCollection.Count];  
  
    for( int x=0; x < input.InputColumnCollection.Count; x++)  
    {  
        IDTSInputColumn100 column = input.InputColumnCollection[x];  
        bufferColumnIndex[x] = BufferManager.FindColumnByLineageID( input.Buffer, column.LineageID);  
    }  
}  
```  
  
```vb  
Dim bufferColumnIndex As Integer()  
  
    Public Overrides Sub PreExecute()  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
  
        ReDim bufferColumnIndex(input.InputColumnCollection.Count)  
  
        For x As Integer = 0 To input.InputColumnCollection.Count  
  
            Dim column As IDTSInputColumn100 = input.InputColumnCollection(x)  
            bufferColumnIndex(x) = BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID)  
  
        Next  
  
    End Sub  
```  
  
### <a name="adding-rows"></a><span data-ttu-id="b6534-134">Agregar filas</span><span class="sxs-lookup"><span data-stu-id="b6534-134">Adding Rows</span></span>  
 <span data-ttu-id="b6534-135">Los componentes proporcionan filas a los componentes de nivel inferior agregándolas a los objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="b6534-135">Components supply rows to downstream components by adding rows to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="b6534-136">La tarea de flujo de datos proporciona una matriz de búferes de salida, uno para cada objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> que está conectado a un componente de nivel inferior, como un parámetro al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-136">The data flow task provides an array of output buffers - one for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that is connected to a downstream component - as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="b6534-137">Los componentes de origen y componentes de transformación con salidas asincrónicas agregan filas a los búferes y llaman al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> cuando terminan de agregar filas.</span><span class="sxs-lookup"><span data-stu-id="b6534-137">Source components and transformation components with asynchronous outputs add rows to the buffers and call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method when they are finished adding rows.</span></span> <span data-ttu-id="b6534-138">La tarea de flujo de datos administra los búferes de salida que proporciona a los componentes y, cuando un búfer se llena, automáticamente mueve las filas del búfer al componente siguiente.</span><span class="sxs-lookup"><span data-stu-id="b6534-138">The data flow task manages the output buffers that it supplies to components and, as a buffer becomes full, automatically moves the rows in the buffer to the next component.</span></span> <span data-ttu-id="b6534-139">Se llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> una vez por componente, a diferencia del método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, al que se llama varias veces.</span><span class="sxs-lookup"><span data-stu-id="b6534-139">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is called one time per component, unlike  the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, which is called repeatedly.</span></span>  
  
 <span data-ttu-id="b6534-140">En el siguiente ejemplo de código se muestra cómo un componente agrega filas a sus búferes de salida durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> y, a continuación, llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-140">The following code example demonstrates how a component adds rows to its output buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method, then calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method.</span></span>  
  
```csharp  
public override void PrimeOutput( int outputs, int []outputIDs,PipelineBuffer []buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        IDTSOutput100 output = ComponentMetaData.OutputCollection.GetObjectByID( outputIDs[x]);  
        PipelineBuffer buffer = buffers[x];  
  
        // TODO: Add rows to the output buffer.  
    }  
    foreach( PipelineBuffer buffer in buffers )  
    {  
        /// Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset();  
    }  
}  
```  
  
```vb  
public overrides sub PrimeOutput( outputs as Integer , outputIDs() as Integer ,buffers() as PipelineBuffer buffers)  
  
    For x As Integer = 0 To outputs.MaxValue  
  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.GetObjectByID(outputIDs(x))  
        Dim buffer As PipelineBuffer = buffers(x)  
  
        ' TODO: Add rows to the output buffer.  
  
    Next  
  
    For Each buffer As PipelineBuffer In buffers  
  
        ' Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset()  
  
    Next  
  
End Sub  
```  
  
 <span data-ttu-id="b6534-141">Para obtener más información sobre el desarrollo de componentes que agregan filas a los búferes de salida, vea [Desarrollar un componente de origen personalizado](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) y [Desarrollar un componente de transformación personalizado con salidas asincrónicas](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="b6534-141">For more information about developing components that add rows to output buffers, see [Developing a Custom Source Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) and [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span>  
  
### <a name="receiving-rows"></a><span data-ttu-id="b6534-142">Recibir filas</span><span class="sxs-lookup"><span data-stu-id="b6534-142">Receiving Rows</span></span>  
 <span data-ttu-id="b6534-143">Los componentes reciben filas de los componentes de nivel superior en objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="b6534-143">Components receive rows from upstream components in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="b6534-144">La tarea de flujo de datos proporciona un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> que contiene las filas agregadas al flujo de datos por componentes de nivel superior como un parámetro al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-144">The data flow task provides a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> object that contains the rows added to the data flow by upstream components as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="b6534-145">Este búfer de entrada se puede usar para examinar y modificar filas y columnas en el búfer, pero no se puede usar para agregar o quitar filas.</span><span class="sxs-lookup"><span data-stu-id="b6534-145">This input buffer can be used to examine and modify the rows and columns in the buffer, but cannot be used to add or remove rows.</span></span> <span data-ttu-id="b6534-146">Se llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> varias veces hasta que no hay más búferes disponibles.</span><span class="sxs-lookup"><span data-stu-id="b6534-146">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method is called repeatedly until there are no more available buffers.</span></span> <span data-ttu-id="b6534-147">En la última llamada, la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="b6534-147">The last time it is called, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="b6534-148">Puede iterar sobre la colección de filas en el búfer mediante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A>, que hace avanzar el búfer a la siguiente fila.</span><span class="sxs-lookup"><span data-stu-id="b6534-148">You can iterate over the collection of rows in the buffer by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method, which advances the buffer to the next row.</span></span> <span data-ttu-id="b6534-149">Este método devuelve `false` cuando el búfer está activado en la última fila de la colección.</span><span class="sxs-lookup"><span data-stu-id="b6534-149">This method returns `false` when the buffer is on the last row in the collection.</span></span> <span data-ttu-id="b6534-150">No tiene que comprobar la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>, a menos que tenga que realizar una acción adicional después de que las últimas filas de datos se hayan procesado.</span><span class="sxs-lookup"><span data-stu-id="b6534-150">You do not have to check the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property unless you have to perform an additional action after the last rows of data have been processed.</span></span>  
  
 <span data-ttu-id="b6534-151">El texto siguiente muestra el patrón correcto para usar el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> y la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>:</span><span class="sxs-lookup"><span data-stu-id="b6534-151">The following text shows the correct pattern for using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property:</span></span>  
  
 `while (buffer.NextRow())`  
  
 `{`  
  
 `// Do something with each row.`  
  
 `}`  
  
 `if (buffer.EndOfRowset)`  
  
 `{`  
  
 `// Optionally, do something after all rows have been processed.`  
  
 `}`  
  
 <span data-ttu-id="b6534-152">En el siguiente ejemplo de código se muestra cómo un componente procesa filas en búferes de entrada durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6534-152">The following code example demonstrates how a component processes the rows in input buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput( int inputID, PipelineBuffer buffer )  
{  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
        while( buffer.NextRow())  
        {  
            // TODO: Examine the columns in the current row.  
        }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)  
        While buffer.NextRow() = True  
  
            ' TODO: Examine the columns in the current row.  
        End While  
  
End Sub  
```  
  
 <span data-ttu-id="b6534-153">Para obtener más información sobre el desarrollo de componentes que reciben filas en los búferes de entrada, vea [Desarrollar un componente de destino personalizado](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) y [Desarrollar un componente de transformación personalizado con salidas sincrónicas](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="b6534-153">For more information about developing components that receive rows in input buffers, see [Developing a Custom Destination Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) and [Developing a Custom Transformation Component with Synchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span></span>  
  
<span data-ttu-id="b6534-154">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b6534-154">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b6534-155">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="b6534-155">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b6534-156">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="b6534-156">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b6534-157">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="b6534-157">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6534-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6534-158">See Also</span></span>  
 [<span data-ttu-id="b6534-159">Métodos en tiempo de diseño de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="b6534-159">Design-time Methods of a Data Flow Component</span></span>](design-time-methods-of-a-data-flow-component.md)  
  
  
