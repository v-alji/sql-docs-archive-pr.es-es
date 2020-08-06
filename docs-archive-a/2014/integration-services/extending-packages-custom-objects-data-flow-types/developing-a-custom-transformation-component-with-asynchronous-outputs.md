---
title: Desarrollar un componente de transformación personalizado con salidas asincrónicas | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom data flow components [Integration Services], transformation components
- asynchronous outputs [Integration Services]
- ProcessInput method
- cache [Integration Services]
- buffer allocations [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], transformation components
ms.assetid: 1c3e92c7-a4fa-4fdd-b9ca-ac3069536274
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41e2ecdf9f90765e75ff2b8c9c0681a25366e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748200"
---
# <a name="developing-a-custom-transformation-component-with-asynchronous-outputs"></a><span data-ttu-id="27f4e-102">Desarrollar un componente de transformación personalizado con salidas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="27f4e-102">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>
  <span data-ttu-id="27f4e-103">Cuando una transformación no puede generar filas hasta que un componente ha recibido todas sus filas de entrada o no genera exactamente una fila de salida por cada fila recibida como entrada, se utiliza un componente con salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-103">You use a component with asynchronous outputs when a transform cannot output rows until the component has received all its input rows, or when the transformation does not produce exactly one output row for each row received as input.</span></span> <span data-ttu-id="27f4e-104">Por ejemplo, la transformación Agregado no puede calcular una suma de las filas hasta que las ha leído todas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-104">The Aggregate transformation, for example, cannot calculate a sum across rows until it has read all the rows.</span></span> <span data-ttu-id="27f4e-105">En cambio, puede utilizar un componente con salidas sincrónicas en cualquier momento al modificar cada fila de datos a medida que las atraviesa.</span><span class="sxs-lookup"><span data-stu-id="27f4e-105">In contrast, you can use a component with synchronous outputs any time when you modify each row of data as it passes through.</span></span> <span data-ttu-id="27f4e-106">Puede modificar los datos para cada fila en su lugar o bien crear una o más columnas nuevas, cada una de las cuales tiene un valor para cada una de las filas de entrada.</span><span class="sxs-lookup"><span data-stu-id="27f4e-106">You can modify the data for each row in place, or you can create one or more new columns, each of which has a value for every one of the input rows.</span></span> <span data-ttu-id="27f4e-107">Para obtener más información acerca de la diferencia entre los componentes sincrónicos y asincrónicos, vea [Descripción de las transformaciones sincrónicas y asincrónicas](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="27f4e-107">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>

 <span data-ttu-id="27f4e-108">Los componentes de transformación con salidas asincrónicas son únicos porque actúan como componentes de destino y componentes de origen.</span><span class="sxs-lookup"><span data-stu-id="27f4e-108">Transformation components with asynchronous outputs are unique because they act as both destination and source components.</span></span> <span data-ttu-id="27f4e-109">Este tipo de componente recibe filas de componentes de nivel superior y agrega filas que consumen los componentes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="27f4e-109">This kind of component receives rows from upstream components, and adds rows that are consumed by downstream components.</span></span> <span data-ttu-id="27f4e-110">Ningún otro componente de flujo de datos realiza estas dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="27f4e-110">No other data flow component performs both of these operations.</span></span>

 <span data-ttu-id="27f4e-111">Las columnas de los componentes de nivel superior disponibles en un componente con salidas sincrónicas están automáticamente disponibles para los componentes de nivel inferior del componente.</span><span class="sxs-lookup"><span data-stu-id="27f4e-111">The columns from upstream components that are available to a component with synchronous outputs are automatically available to components downstream from the component.</span></span> <span data-ttu-id="27f4e-112">Por tanto, un componente con salidas sincrónicas no tiene que definir ninguna columna de salida para proporcionar columnas y filas al componente siguiente.</span><span class="sxs-lookup"><span data-stu-id="27f4e-112">Therefore, a component with synchronous outputs does not have to define any output columns to provide columns and rows to the next component.</span></span> <span data-ttu-id="27f4e-113">Los componentes con salidas asincrónicas, por otro lado, deben definir columnas de salida y proporcionar filas a los componentes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="27f4e-113">Components with asynchronous outputs, on the other hand, must define output columns and provide rows to downstream components.</span></span> <span data-ttu-id="27f4e-114">Así, un componente con salidas asincrónicas tiene más tareas que realizar durante el tiempo de diseño y el tiempo de ejecución y el programador de componentes tiene más código que implementar.</span><span class="sxs-lookup"><span data-stu-id="27f4e-114">Therefore a component with asynchronous outputs has more tasks to perform during both design and execution time, and the component developer has more code to implement.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="27f4e-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contiene varias transformaciones con salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contains several transformations with asynchronous outputs.</span></span> <span data-ttu-id="27f4e-116">Por ejemplo, la transformación Ordenar requiere todas sus filas antes de poder ordenarlas y lo consigue mediante salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-116">For example, the Sort transformation requires all its rows before it can sort them, and achieves this by using asynchronous outputs.</span></span> <span data-ttu-id="27f4e-117">Después de recibir todas sus filas, las ordena y las agrega a su salida.</span><span class="sxs-lookup"><span data-stu-id="27f4e-117">After it has received all its rows, it sorts them and adds them to its output.</span></span>

 <span data-ttu-id="27f4e-118">En esta sección se explica en detalle cómo desarrollar transformaciones con salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-118">This section explains in detail how to develop transformations with asynchronous outputs.</span></span> <span data-ttu-id="27f4e-119">Para obtener más información acerca del desarrollo de componentes de origen, vea [Desarrollar un componente de origen personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="27f4e-119">For more information about source component development, see [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="27f4e-120">Tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="27f4e-120">Design Time</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="27f4e-121">Crear el componente</span><span class="sxs-lookup"><span data-stu-id="27f4e-121">Creating the Component</span></span>
 <span data-ttu-id="27f4e-122">La propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> en el objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> identifica si una salida es sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="27f4e-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property on the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object identifies whether an output is synchronous or asynchronous.</span></span> <span data-ttu-id="27f4e-123">Para crear una salida asincrónica, agregue la salida al componente y establezca <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> en cero.</span><span class="sxs-lookup"><span data-stu-id="27f4e-123">To create an asynchronous output, add the output to the component and set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> to zero.</span></span> <span data-ttu-id="27f4e-124">Al establecer esta propiedad también se determina si la tarea de flujo de datos asigna objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> tanto a la entrada como a la salida del componente o si se asigna y se comparte un único búfer entre los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="27f4e-124">Setting this property also determines whether the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects for both the input and output of the component, or whether a single buffer is allocated and shared between the two objects.</span></span>

 <span data-ttu-id="27f4e-125">En el código de ejemplo siguiente se muestra un componente que crea una salida asincrónica en su implementación <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="27f4e-125">The following sample code shows a component that creates an asynchronous output in its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> implementation.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "AsyncComponent",ComponentType = ComponentType.Transform)]
    public class AsyncComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Call the base class, which adds a synchronous input
            // and output.
            base.ProvideComponentProperties();

            // Make the output asynchronous.
            IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
            output.SynchronousInputID = 0;
        }
    }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

<DtsPipelineComponent(DisplayName:="AsyncComponent", ComponentType:=ComponentType.Transform)> _
Public Class AsyncComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Call the base class, which adds a synchronous input
        ' and output.
        Me.ProvideComponentProperties()

        ' Make the output asynchronous.
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
        output.SynchronousInputID = 0

    End Sub

End Class
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="27f4e-126">Crear y configurar columnas de salida</span><span class="sxs-lookup"><span data-stu-id="27f4e-126">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="27f4e-127">Tal y como se ha mencionado anteriormente, un componente asincrónico agrega columnas a su colección de columnas de salida para proporcionar columnas a los componentes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="27f4e-127">As mentioned earlier, an asynchronous component adds columns to its output column collection to provide columns to downstream components.</span></span> <span data-ttu-id="27f4e-128">Existen varios métodos en tiempo de diseño entre los que elegir, en función de las necesidades del componente.</span><span class="sxs-lookup"><span data-stu-id="27f4e-128">There are several design-time methods to choose from, depending on the needs of the component.</span></span> <span data-ttu-id="27f4e-129">Por ejemplo, si desea pasar todas las columnas de los componentes de nivel superior a los componentes de nivel inferior, debería invalidar el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> para agregar las columnas, porque se trata del primer método en el que las columnas de entrada están disponibles para el componente.</span><span class="sxs-lookup"><span data-stu-id="27f4e-129">For example, if you want to pass all the columns from the upstream components to the downstream components, you would override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> method to add the columns, because this is the first method in which the input columns are available to the component.</span></span>

 <span data-ttu-id="27f4e-130">Si el componente crea columnas de salida basándose en las columnas seleccionadas para su entrada, invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> para seleccionar las columnas de salida e indicar cómo se utilizarán.</span><span class="sxs-lookup"><span data-stu-id="27f4e-130">If the component creates output columns based on the columns selected for its input, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> method to select the output columns and to indicate how they will be used.</span></span>

 <span data-ttu-id="27f4e-131">Si un componente con salidas asincrónicas crea columnas de salida basándose en las columnas de los componentes de nivel superior y cambian las columnas de nivel superior disponibles, el componente debe actualizar su colección de columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="27f4e-131">If a component with asynchronous outputs creates output columns based on the columns from upstream components, and the available upstream columns change, the component should update its output column collection.</span></span> <span data-ttu-id="27f4e-132">El componente debe detectar estos cambios durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> y corregirlos durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="27f4e-132">These changes should be detected by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and fixed during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span></span>

> [!NOTE]
>  <span data-ttu-id="27f4e-133">Cuando una columna de resultados se quita de la colección de columnas de salida, los componentes de nivel inferior del flujo de datos que hacen referencia a la columna se ven afectados negativamente.</span><span class="sxs-lookup"><span data-stu-id="27f4e-133">When an output column is removed from the output column collection, downstream components in the data flow that reference the column are adversely affected.</span></span> <span data-ttu-id="27f4e-134">La columna de salida se debe reparar sin quitar y volver a crear la columna para evitar la ruptura de los componentes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="27f4e-134">The output column must be repaired without removing and recreating the column to prevent breaking the downstream components.</span></span> <span data-ttu-id="27f4e-135">Por ejemplo, si el tipo de datos de la columna ha cambiado, debe actualizar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="27f4e-135">For example, if the data type of the column has changed, you must update the data type.</span></span>

 <span data-ttu-id="27f4e-136">En el ejemplo de código siguiente se muestra un componente que agrega una columna de salida a su colección de columnas de salida para cada columna disponible del componente de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="27f4e-136">The following code example shows a component that adds an output column to its output column collection for each column available from the upstream component.</span></span>

```csharp
public override void OnInputPathAttached(int inputID)
{
   IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);
   IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
   IDTSVirtualInput100 vInput = input.GetVirtualInput();

   foreach (IDTSVirtualInputColumn100 vCol in vInput.VirtualInputColumnCollection)
   {
      IDTSOutputColumn100 outCol = output.OutputColumnCollection.New();
      outCol.Name = vCol.Name;
      outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage);
   }
}
```

```vb
Public Overrides Sub OnInputPathAttached(ByVal inputID As Integer)

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput()

    For Each vCol As IDTSVirtualInputColumn100 In vInput.VirtualInputColumnCollection

        Dim outCol As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        outCol.Name = vCol.Name
        outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage)

    Next
End Sub
```

## <a name="run-time"></a><span data-ttu-id="27f4e-137">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="27f4e-137">Run Time</span></span>
 <span data-ttu-id="27f4e-138">Los componentes con salidas asincrónicas también ejecutan una secuencia diferente de métodos en tiempo de ejecución que otros tipos de componentes.</span><span class="sxs-lookup"><span data-stu-id="27f4e-138">Components with asynchronous outputs also execute a different sequence of methods at run time than other types of components.</span></span> <span data-ttu-id="27f4e-139">En primer lugar, son los únicos componentes que reciben una llamada tanto a los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> como a los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="27f4e-139">First, they are the only components that receive a call to both the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="27f4e-140">Los componentes con salidas asincrónicas también requieren acceso a todas las filas entrantes antes de poder iniciar el procesamiento; por tanto, deben almacenar internamente en memoria caché las filas de entrada hasta que se hayan leído todas las filas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-140">Components with asynchronous outputs also require access to all the incoming rows before they can start processing; therefore, they must cache the input rows internally until all rows have been read.</span></span> <span data-ttu-id="27f4e-141">Por último, a diferencia de los demás componentes, los componentes con salidas asincrónicas reciben un búfer de entrada y un búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="27f4e-141">Finally, unlike other components, components with asynchronous outputs receive both an input buffer and an output buffer.</span></span>

### <a name="understanding-the-buffers"></a><span data-ttu-id="27f4e-142">Descripción de los búferes</span><span class="sxs-lookup"><span data-stu-id="27f4e-142">Understanding the Buffers</span></span>
 <span data-ttu-id="27f4e-143">El componente recibe el búfer de entrada durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="27f4e-143">The input buffer is received by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="27f4e-144">Este búfer contiene las filas agregadas al búfer por componentes de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="27f4e-144">This buffer contains the rows added to the buffer by upstream components.</span></span> <span data-ttu-id="27f4e-145">El búfer también contiene las columnas de la entrada del componente, además de las columnas proporcionadas en la salida de un componente de nivel superior pero que no se agregaron a la colección de entradas del componente asincrónico.</span><span class="sxs-lookup"><span data-stu-id="27f4e-145">The buffer also contains the columns of the component's input, in addition to the columns that were provided in the output of an upstream component but were not added to the asynchronous component's input collection.</span></span>

 <span data-ttu-id="27f4e-146">El búfer de salida, que se proporciona al componente en <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, no contiene inicialmente ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="27f4e-146">The output buffer, which is provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, does not initially contain rows.</span></span> <span data-ttu-id="27f4e-147">El componente agrega filas a este búfer y proporciona el búfer a los componentes de nivel inferior cuando está lleno.</span><span class="sxs-lookup"><span data-stu-id="27f4e-147">The component adds rows to this buffer and provides the buffer to downstream components when it is full.</span></span> <span data-ttu-id="27f4e-148">El búfer de salida contiene las columnas definidas en la colección de columnas de salida del componente, además de cualquier columna que otros componentes de nivel inferior hayan agregado a sus salidas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-148">The output buffer contains the columns defined in the component's output column collection, in addition to any columns that other downstream components have added to their outputs.</span></span>

 <span data-ttu-id="27f4e-149">Éste es un comportamiento diferente del que sucede en los componentes con salidas sincrónicas, que reciben un único búfer compartido.</span><span class="sxs-lookup"><span data-stu-id="27f4e-149">This is different behavior from that of components with synchronous outputs, which receive a single shared buffer.</span></span> <span data-ttu-id="27f4e-150">El búfer compartido de un componente con salidas sincrónicas contiene las columnas de entrada y salida del componente, además de las columnas agregadas a las salidas de los componentes de nivel superior y de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="27f4e-150">The shared buffer of a component with synchronous outputs contains both the input and output columns of the component, in addition to columns added to the outputs of upstream and downstream components.</span></span>

### <a name="processing-rows"></a><span data-ttu-id="27f4e-151">Procesar las filas</span><span class="sxs-lookup"><span data-stu-id="27f4e-151">Processing Rows</span></span>

#### <a name="caching-input-rows"></a><span data-ttu-id="27f4e-152">Almacenar en memoria caché las filas de entrada</span><span class="sxs-lookup"><span data-stu-id="27f4e-152">Caching Input Rows</span></span>
 <span data-ttu-id="27f4e-153">Al escribir un componente con salidas asincrónicas, existen tres opciones para agregar filas al búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="27f4e-153">When you write a component with asynchronous outputs, you have three options for adding rows to the output buffer.</span></span> <span data-ttu-id="27f4e-154">Puede agregarlas cuando se reciben las filas de entrada, puede almacenarlas en caché hasta que el componente haya recibido todas las filas del componente de nivel superior o puede agregarlas cuando sea adecuado realizarlo para el componente.</span><span class="sxs-lookup"><span data-stu-id="27f4e-154">You can add them as input rows are received, you can cache them until the component has received all the rows from the upstream component, or you can add them when it is appropriate to do so for the component.</span></span> <span data-ttu-id="27f4e-155">El método que elija dependerá de los requisitos del componente.</span><span class="sxs-lookup"><span data-stu-id="27f4e-155">The method that you choose depends on the requirements of the component.</span></span> <span data-ttu-id="27f4e-156">Por ejemplo, el componente Sort requiere que se reciban todas las filas de nivel superior antes de ordenarlas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-156">For example, the Sort component requires that all the upstream rows be received before they can be sorted.</span></span> <span data-ttu-id="27f4e-157">Por tanto, espera hasta que se han leído todas las filas antes de agregarlas al búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="27f4e-157">Therefore, it waits until all rows have been read before adding rows to the output buffer.</span></span>

 <span data-ttu-id="27f4e-158">El componente debe almacenar internamente en la memoria caché las filas que se reciben en el búfer de entrada hasta estar listo para procesarlas.</span><span class="sxs-lookup"><span data-stu-id="27f4e-158">The rows that are received in the input buffer must be cached internally by the component until it is ready to process them.</span></span> <span data-ttu-id="27f4e-159">Las filas del búfer de entrada se pueden almacenar en caché en una tabla de datos, una matriz multidimensional o cualquier otra estructura interna.</span><span class="sxs-lookup"><span data-stu-id="27f4e-159">The incoming buffer rows can be cached in a data table, a multidimensional array, or any other internal structure.</span></span>

#### <a name="adding-output-rows"></a><span data-ttu-id="27f4e-160">Agregar las filas de salida</span><span class="sxs-lookup"><span data-stu-id="27f4e-160">Adding Output Rows</span></span>
 <span data-ttu-id="27f4e-161">Tanto si agrega las filas al búfer de salida a medida que se reciben como si lo hace después de recibir todas las filas, esta operación se lleva a cabo mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> en el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="27f4e-161">Whether you add rows to the output buffer as they are received or after receiving all of the rows, you do so by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method on the output buffer.</span></span> <span data-ttu-id="27f4e-162">Después de agregar la fila, establece los valores de las columnas de la nueva fila.</span><span class="sxs-lookup"><span data-stu-id="27f4e-162">After you have added the row, you set the values of each column in the new row.</span></span>

 <span data-ttu-id="27f4e-163">En ocasiones existen más columnas en el búfer de salida que en la colección de columnas de salida del componente, por lo que debe localizar el índice de la columna correspondiente en el búfer antes de establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="27f4e-163">Because there are sometimes more columns in the output buffer than in the output column collection of the component, you must locate the index of the appropriate column in the buffer before you can set its value.</span></span> <span data-ttu-id="27f4e-164">El método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> devuelve el índice de la columna en la fila del búfer con el identificador de linaje especificado, que se utiliza a continuación para asignar el valor a la columna de búfer.</span><span class="sxs-lookup"><span data-stu-id="27f4e-164">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property returns the index of the column in the buffer row with the specified lineage ID, which is then used to assign the value to the buffer column.</span></span>

 <span data-ttu-id="27f4e-165">El método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, al que se llama antes del método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> o el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, es el primer método donde está disponible la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> y la primera oportunidad para localizar los índices de las columnas en los búferes de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="27f4e-165">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, which is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method or the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, is the first method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property is available, and the first opportunity to locate the indexes of the columns in the input and output buffers.</span></span>

## <a name="sample"></a><span data-ttu-id="27f4e-166">Muestra</span><span class="sxs-lookup"><span data-stu-id="27f4e-166">Sample</span></span>
 <span data-ttu-id="27f4e-167">En el ejemplo siguiente se muestra un componente de transformación simple con salidas asincrónicas que agrega filas al búfer de salida a medida que se reciben.</span><span class="sxs-lookup"><span data-stu-id="27f4e-167">The following sample shows a simple transformation component with asynchronous outputs that adds rows to the output buffer as they are received.</span></span> <span data-ttu-id="27f4e-168">En este ejemplo no se muestran todos los métodos ni funcionalidad tratados en este tema.</span><span class="sxs-lookup"><span data-stu-id="27f4e-168">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="27f4e-169">Muestra los métodos importantes que cada componente de transformación personalizado con salidas asincrónicas debe invalidar, pero no contiene código para la validación en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="27f4e-169">It demonstrates the important methods that every custom transformation component with asynchronous outputs must override, but does not contain code for design-time validation.</span></span> <span data-ttu-id="27f4e-170">Además, el código de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> supone que la colección de columnas de salida incluye una columna por cada columna de la colección de columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="27f4e-170">Also, the code in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> assumes that the output column collection has one column for each column in the input column collection.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
   [DtsPipelineComponent(DisplayName = "AsynchronousOutput")]
   public class AsynchronousOutput : PipelineComponent
   {
      PipelineBuffer outputBuffer;
      int[] inputColumnBufferIndexes;
      int[] outputColumnBufferIndexes;

      public override void ProvideComponentProperties()
      {
         // Let the base class add the input and output objects.
         base.ProvideComponentProperties();

         // Name the input and output, and make the
         // output asynchronous.
         ComponentMetaData.InputCollection[0].Name = "Input";
         ComponentMetaData.OutputCollection[0].Name = "AsyncOutput";
         ComponentMetaData.OutputCollection[0].SynchronousInputID = 0;
      }
      public override void PreExecute()
      {
         IDTSInput100 input = ComponentMetaData.InputCollection[0];
         IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

         inputColumnBufferIndexes = new int[input.InputColumnCollection.Count];
         outputColumnBufferIndexes = new int[output.OutputColumnCollection.Count];

         for (int col = 0; col < input.InputColumnCollection.Count; col++)
            inputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[col].LineageID);

         for (int col = 0; col < output.OutputColumnCollection.Count; col++)
            outputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[col].LineageID);

      }

      public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
      {
         if (buffers.Length != 0)
            outputBuffer = buffers[0];
      }
      public override void ProcessInput(int inputID, PipelineBuffer buffer)
      {
            // Advance the buffer to the next row.
            while (buffer.NextRow())
            {
               // Add a row to the output buffer.
               outputBuffer.AddRow();
               for (int x = 0; x < inputColumnBufferIndexes.Length; x++)
               {
                  // Copy the data from the input buffer column to the output buffer column.
                  outputBuffer[outputColumnBufferIndexes[x]] = buffer[inputColumnBufferIndexes[x]];
               }
            }
         if (buffer.EndOfRowset)
         {
            // EndOfRowset on the input buffer is true.
            // Set EndOfRowset on the output buffer.
            outputBuffer.SetEndOfRowset();
         }
      }
   }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="AsynchronousOutput")> _
    Public Class AsynchronousOutput

        Inherits PipelineComponent

        Private outputBuffer As PipelineBuffer
        Private inputColumnBufferIndexes As Integer()
        Private outputColumnBufferIndexes As Integer()

        Public Overrides Sub ProvideComponentProperties()

            ' Let the base class add the input and output objects.
            Me.ProvideComponentProperties()

            ' Name the input and output, and make the
            ' output asynchronous.
            ComponentMetaData.InputCollection(0).Name = "Input"
            ComponentMetaData.OutputCollection(0).Name = "AsyncOutput"
            ComponentMetaData.OutputCollection(0).SynchronousInputID = 0
        End Sub

        Public Overrides Sub PreExecute()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)
            Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

            ReDim inputColumnBufferIndexes(input.InputColumnCollection.Count)
            ReDim outputColumnBufferIndexes(output.OutputColumnCollection.Count)

            For col As Integer = 0 To input.InputColumnCollection.Count
                inputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(col).LineageID)
            Next

            For col As Integer = 0 To output.OutputColumnCollection.Count
                outputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(col).LineageID)
            Next

        End Sub
        Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

            If buffers.Length <> 0 Then
                outputBuffer = buffers(0)
            End If

        End Sub

        Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

                ' Advance the buffer to the next row.
                While (buffer.NextRow())

                    ' Add a row to the output buffer.
                    outputBuffer.AddRow()
                    For x As Integer = 0 To inputColumnBufferIndexes.Length

                        ' Copy the data from the input buffer column to the output buffer column.
                        outputBuffer(outputColumnBufferIndexes(x)) = buffer(inputColumnBufferIndexes(x))

                    Next
                End While

            If buffer.EndOfRowset = True Then
                ' EndOfRowset on the input buffer is true.
                ' Set the end of row set on the output buffer.
                outputBuffer.SetEndOfRowset()
            End If
        End Sub
    End Class
End Namespace
```

<span data-ttu-id="27f4e-171">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="27f4e-171">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="27f4e-172">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="27f4e-172">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="27f4e-173">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="27f4e-173">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="27f4e-174">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="27f4e-174">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="27f4e-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27f4e-175">See Also</span></span>
 <span data-ttu-id="27f4e-176">[Desarrollar un componente de transformación personalizado con salidas sincrónicas](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Descripción de las transformaciones sincrónicas y asincrónicas](../understanding-synchronous-and-asynchronous-transformations.md) [crear una transformación asincrónica con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="27f4e-176">[Developing a Custom Transformation Component with Synchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span></span>


