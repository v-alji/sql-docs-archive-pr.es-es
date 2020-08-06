---
title: Desarrollar un componente de transformación personalizado mediante salidas sincrónicas | Microsoft Docs
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
- ProcessInput method
- buffer allocations [Integration Services]
- synchronous outputs [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- data flow components [Integration Services], transformation components
ms.assetid: b694d21f-9919-402d-9192-666c6449b0b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 94d78872570103d3df7e1cb96aecb144fafe4257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748201"
---
# <a name="developing-a-custom-transformation-component-with-synchronous-outputs"></a><span data-ttu-id="e146b-102">Desarrollar un componente de transformación personalizado con salidas sincrónicas</span><span class="sxs-lookup"><span data-stu-id="e146b-102">Developing a Custom Transformation Component with Synchronous Outputs</span></span>
  <span data-ttu-id="e146b-103">Los componentes de transformación con salidas sincrónicas reciben filas de los componentes de nivel superior y leen o modifican los valores de las columnas de estas filas al pasarlas a los componentes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="e146b-103">Transformation components with synchronous outputs receive rows from upstream components, and read or modify the values in the columns of these rows as they pass the rows to downstream components.</span></span> <span data-ttu-id="e146b-104">También pueden definir columnas de salida adicionales que se derivan de las columnas que proporcionan los componentes de nivel superior, pero no agregan filas al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="e146b-104">They may also define additional output columns that are derived from the columns provided by upstream components, but they do not add rows to the data flow.</span></span> <span data-ttu-id="e146b-105">Para obtener más información acerca de la diferencia entre los componentes sincrónicos y asincrónicos, vea [Descripción de las transformaciones sincrónicas y asincrónicas](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="e146b-105">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>  
  
 <span data-ttu-id="e146b-106">Este tipo de componente es el adecuado para las tareas en las que se modifican los datos insertados cuando se proporcionan al componente, y donde el componente no tiene que ver todas las filas antes de procesarlas.</span><span class="sxs-lookup"><span data-stu-id="e146b-106">This kind of component is suited for tasks where the data is modified inline as it is provided to the component and where the component does not have to see all the rows before processing them.</span></span> <span data-ttu-id="e146b-107">Se trata de desarrollar el componente más sencillo debido a que las transformaciones con salidas sincrónicas no conectan normalmente a orígenes de datos externos, administran columnas de metadatos externas o agregan filas a búferes de salida.</span><span class="sxs-lookup"><span data-stu-id="e146b-107">It is the easiest component to develop because transformations with synchronous outputs typically do not connect to external data sources, manage external metadata columns, or add rows to output buffers.</span></span>  
  
 <span data-ttu-id="e146b-108">Crear un componente de transformación con salidas sincrónicas implica agregar un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> que contendrá las columnas de nivel superior seleccionadas para el componente, así como un objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> que puede contener las columnas derivadas creadas por el componente.</span><span class="sxs-lookup"><span data-stu-id="e146b-108">Creating a transformation component with synchronous outputs involves adding an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> that will contain the upstream columns selected for the component, and a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that may contain derived columns created by the component.</span></span> <span data-ttu-id="e146b-109">También incluye implementar métodos en tiempo de diseño y proporcionar código que lee o modifica las columnas en las filas del búfer de entrada durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="e146b-109">It also includes implementing the design-time methods, and providing code that reads or modifies the columns in the incoming buffer rows during execution.</span></span>  
  
 <span data-ttu-id="e146b-110">En esta sección se facilita la información necesaria para implementar un componente de transformación personalizado y se proporcionan ejemplos de código que sirven de ayuda para comprender mejor los conceptos.</span><span class="sxs-lookup"><span data-stu-id="e146b-110">This section provides the information that is required to implement a custom transformation component, and provides code examples to help you better understand the concepts.</span></span>  
  
## <a name="design-time"></a><span data-ttu-id="e146b-111">Tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="e146b-111">Design Time</span></span>  
 <span data-ttu-id="e146b-112">El código en tiempo de diseño para este componente implica crear entradas y salidas, agregar cualquier columna de salida adicional que genere el componente y validar la configuración del componente.</span><span class="sxs-lookup"><span data-stu-id="e146b-112">The design-time code for this component involves creating the inputs and outputs, adding any additional output columns that the component generates, and validating the configuration of the component.</span></span>  
  
### <a name="creating-the-component"></a><span data-ttu-id="e146b-113">Crear el componente</span><span class="sxs-lookup"><span data-stu-id="e146b-113">Creating the Component</span></span>  
 <span data-ttu-id="e146b-114">Las entradas, salidas y las propiedades personalizadas del componente se crean normalmente durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="e146b-114">The inputs, outputs, and custom properties of the component are typically created during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="e146b-115">Hay dos maneras para agregar la entrada y salida de un componente de transformación con salidas sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="e146b-115">There are two ways that you can add the input and the output of a transformation component with synchronous outputs.</span></span> <span data-ttu-id="e146b-116">Puede usar la implementación de la clase base del método y, a continuación, modificar la entrada y salida predeterminada que se crea o puede agregar explícitamente usted mismo la entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="e146b-116">You can use the base class implementation of the method and then modify the default input and output that it creates, or you can explicitly add the input and output yourself.</span></span>  
  
 <span data-ttu-id="e146b-117">En el ejemplo de código siguiente se muestra una implementación de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> que agrega explícitamente los objetos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="e146b-117">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that explicitly adds the input and output objects.</span></span> <span data-ttu-id="e146b-118">La llamada a la clase base que realizaría la misma acción se incluye en un comentario.</span><span class="sxs-lookup"><span data-stu-id="e146b-118">The call to the base class that would accomplish the same thing is included in a comment.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SynchronousComponent", ComponentType = ComponentType.Transform)]  
    public class SyncComponent : PipelineComponent  
    {  
  
        public override void ProvideComponentProperties()  
        {  
            // Add the input.  
            IDTSInput100 input = ComponentMetaData.InputCollection.New();  
            input.Name = "Input";  
  
            // Add the output.  
            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
            output.Name = "Output";  
            output.SynchronousInputID = input.ID;  
  
            // Alternatively, you can let the base class add the input and output  
            // and set the SynchronousInputID of the output to the ID of the input.  
            // base.ProvideComponentProperties();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsPipelineComponent(DisplayName:="SynchronousComponent", ComponentType:=ComponentType.Transform)> _  
Public Class SyncComponent  
    Inherits PipelineComponent  
  
    Public Overrides Sub ProvideComponentProperties()  
  
        ' Add the input.  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()  
        input.Name = "Input"  
  
        ' Add the output.  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()  
        output.Name = "Output"  
        output.SynchronousInputID = Input.ID  
  
        ' Alternatively, you can let the base class add the input and output  
        ' and set the SynchronousInputID of the output to the ID of the input.  
        ' base.ProvideComponentProperties();  
  
    End Sub  
  
End Class  
```  
  
### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="e146b-119">Crear y configurar columnas de salida</span><span class="sxs-lookup"><span data-stu-id="e146b-119">Creating and Configuring Output Columns</span></span>  
 <span data-ttu-id="e146b-120">Aunque los componentes de transformación con salidas sincrónicas no agregan filas a los búferes, pueden agregar columnas de salidas adicionales a su salida.</span><span class="sxs-lookup"><span data-stu-id="e146b-120">Although transformation components with synchronous outputs do not add rows to buffers, they may add extra output columns to their output.</span></span> <span data-ttu-id="e146b-121">Normalmente, cuando un componente agrega una columna de salida, los valores de la nueva columna de salida se derivan en tiempo de ejecución de los datos contenidos en una o varias de las columnas que el componente de nivel superior proporciona al componente.</span><span class="sxs-lookup"><span data-stu-id="e146b-121">Typically, when a component adds an output column, the values for the new output column are derived at run time from the data that is contained in one or more of the columns provided to the component by an upstream component.</span></span>  
  
 <span data-ttu-id="e146b-122">Una vez creada una columna de salida, se deben establecer sus propiedades de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="e146b-122">After an output column has been created, its data type properties must be set.</span></span> <span data-ttu-id="e146b-123">Para establecer las propiedades de tipo de datos de una columna de salida se requiere un tratamiento especial y se realiza llamando al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="e146b-123">Setting the data type properties of an output column requires special handling and is performed by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="e146b-124">Este método es obligatorio porque las propiedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> son de solo lectura individualmente, debido a que cada propiedad depende de los valores de la otra.</span><span class="sxs-lookup"><span data-stu-id="e146b-124">This method is required because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are individually read-only, because each depends on the settings of the other.</span></span> <span data-ttu-id="e146b-125">Este método garantiza que los valores de las propiedades se establezcan de forma coherente y que la tarea de flujo de datos valide que se establezcan correctamente.</span><span class="sxs-lookup"><span data-stu-id="e146b-125">This method guarantees that the values of the properties are set consistently, and the data flow task validates that they are set correctly.</span></span>  
  
 <span data-ttu-id="e146b-126">El <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> de la columna determina los valores que se establecen para otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="e146b-126">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="e146b-127">En la tabla siguiente se muestran los requisitos de las propiedades dependientes para cada <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="e146b-127">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="e146b-128">En los tipos de datos no enumerados, sus propiedades dependientes se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="e146b-128">The data types not listed have their dependent properties set to zero.</span></span>  
  
|<span data-ttu-id="e146b-129">DataType</span><span class="sxs-lookup"><span data-stu-id="e146b-129">DataType</span></span>|<span data-ttu-id="e146b-130">Length</span><span class="sxs-lookup"><span data-stu-id="e146b-130">Length</span></span>|<span data-ttu-id="e146b-131">Escala</span><span class="sxs-lookup"><span data-stu-id="e146b-131">Scale</span></span>|<span data-ttu-id="e146b-132">Precision</span><span class="sxs-lookup"><span data-stu-id="e146b-132">Precision</span></span>|<span data-ttu-id="e146b-133">CodePage</span><span class="sxs-lookup"><span data-stu-id="e146b-133">CodePage</span></span>|  
|--------------|------------|-----------|---------------|--------------|  
|<span data-ttu-id="e146b-134">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="e146b-134">DT_DECIMAL</span></span>|<span data-ttu-id="e146b-135">0</span><span class="sxs-lookup"><span data-stu-id="e146b-135">0</span></span>|<span data-ttu-id="e146b-136">Mayor que 0 y menor o igual que 28.</span><span class="sxs-lookup"><span data-stu-id="e146b-136">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="e146b-137">0</span><span class="sxs-lookup"><span data-stu-id="e146b-137">0</span></span>|<span data-ttu-id="e146b-138">0</span><span class="sxs-lookup"><span data-stu-id="e146b-138">0</span></span>|  
|<span data-ttu-id="e146b-139">DT_CY</span><span class="sxs-lookup"><span data-stu-id="e146b-139">DT_CY</span></span>|<span data-ttu-id="e146b-140">0</span><span class="sxs-lookup"><span data-stu-id="e146b-140">0</span></span>|<span data-ttu-id="e146b-141">0</span><span class="sxs-lookup"><span data-stu-id="e146b-141">0</span></span>|<span data-ttu-id="e146b-142">0</span><span class="sxs-lookup"><span data-stu-id="e146b-142">0</span></span>|<span data-ttu-id="e146b-143">0</span><span class="sxs-lookup"><span data-stu-id="e146b-143">0</span></span>|  
|<span data-ttu-id="e146b-144">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="e146b-144">DT_NUMERIC</span></span>|<span data-ttu-id="e146b-145">0</span><span class="sxs-lookup"><span data-stu-id="e146b-145">0</span></span>|<span data-ttu-id="e146b-146">Mayor que 0 y menor o igual que 28 y menor que Precisión.</span><span class="sxs-lookup"><span data-stu-id="e146b-146">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="e146b-147">Mayor o igual que 1 y menor o igual que 38.</span><span class="sxs-lookup"><span data-stu-id="e146b-147">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="e146b-148">0</span><span class="sxs-lookup"><span data-stu-id="e146b-148">0</span></span>|  
|<span data-ttu-id="e146b-149">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="e146b-149">DT_BYTES</span></span>|<span data-ttu-id="e146b-150">Mayor que 0.</span><span class="sxs-lookup"><span data-stu-id="e146b-150">Greater than 0.</span></span>|<span data-ttu-id="e146b-151">0</span><span class="sxs-lookup"><span data-stu-id="e146b-151">0</span></span>|<span data-ttu-id="e146b-152">0</span><span class="sxs-lookup"><span data-stu-id="e146b-152">0</span></span>|<span data-ttu-id="e146b-153">0</span><span class="sxs-lookup"><span data-stu-id="e146b-153">0</span></span>|  
|<span data-ttu-id="e146b-154">DT_STR</span><span class="sxs-lookup"><span data-stu-id="e146b-154">DT_STR</span></span>|<span data-ttu-id="e146b-155">Mayor que 0 y menor que 8000.</span><span class="sxs-lookup"><span data-stu-id="e146b-155">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="e146b-156">0</span><span class="sxs-lookup"><span data-stu-id="e146b-156">0</span></span>|<span data-ttu-id="e146b-157">0</span><span class="sxs-lookup"><span data-stu-id="e146b-157">0</span></span>|<span data-ttu-id="e146b-158">Distinto de 0 y una página de códigos válida.</span><span class="sxs-lookup"><span data-stu-id="e146b-158">Not 0, and a valid code page.</span></span>|  
|<span data-ttu-id="e146b-159">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="e146b-159">DT_WSTR</span></span>|<span data-ttu-id="e146b-160">Mayor que 0 y menor que 4.000.</span><span class="sxs-lookup"><span data-stu-id="e146b-160">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="e146b-161">0</span><span class="sxs-lookup"><span data-stu-id="e146b-161">0</span></span>|<span data-ttu-id="e146b-162">0</span><span class="sxs-lookup"><span data-stu-id="e146b-162">0</span></span>|<span data-ttu-id="e146b-163">0</span><span class="sxs-lookup"><span data-stu-id="e146b-163">0</span></span>|  
  
 <span data-ttu-id="e146b-164">Puesto que las restricciones en las propiedades de tipo de datos se basan en el tipo de datos de la columna de salida, debe elegir el tipo de datos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] correcto al trabajar con tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="e146b-164">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="e146b-165">La clase base proporciona tres métodos del asistente, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, que ayudan a los programadores de componentes administrados a seleccionar un tipo de datos de [!INCLUDE[ssIS](../../includes/ssis-md.md)] dado un tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="e146b-165">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A> that assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="e146b-166">Estos métodos convierten los tipos de datos administrados en tipos de datos de [!INCLUDE[ssIS](../../includes/ssis-md.md)] y viceversa.</span><span class="sxs-lookup"><span data-stu-id="e146b-166">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="e146b-167">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e146b-167">Run Time</span></span>  
 <span data-ttu-id="e146b-168">En general, la implementación en tiempo de ejecución de un elemento del componente se divide en dos tareas: búsqueda de las columnas de entrada y salida del componente en el búfer, y lectura o escritura de los valores de estas columnas en las filas del búfer de entrada.</span><span class="sxs-lookup"><span data-stu-id="e146b-168">Generally, the implementation of the run-time part of the component is categorized into two tasks-locating the input and output columns of the component in the buffer, and reading or writing the values of these columns in the incoming buffer rows.</span></span>  
  
### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="e146b-169">Localizar columnas en el búfer</span><span class="sxs-lookup"><span data-stu-id="e146b-169">Locating Columns in the Buffer</span></span>  
 <span data-ttu-id="e146b-170">El número de columnas en los búferes que se proporcionan a un componente durante la ejecución, superará probablemente el número de columnas en las colecciones de entrada o salida del componente.</span><span class="sxs-lookup"><span data-stu-id="e146b-170">The number of columns in the buffers that are provided to a component during execution will likely exceed the number of columns in the input or output collections of the component.</span></span> <span data-ttu-id="e146b-171">Esto se debe a que cada búfer contiene todas las columnas de salida definidas en los componentes de un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="e146b-171">This is because each buffer contains all the output columns defined in the components in a data flow.</span></span> <span data-ttu-id="e146b-172">Para asegurarse de que las columnas de búfer coinciden correctamente con las columnas de entrada o salida, los programadores de componentes deben usar el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="e146b-172">To ensure that the buffer columns are correctly matched to the columns of the input or output, component developers must use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="e146b-173">Este método busca una columna en el búfer especificado por su identificador de linaje.</span><span class="sxs-lookup"><span data-stu-id="e146b-173">This method locates a column in the specified buffer by its lineage ID.</span></span> <span data-ttu-id="e146b-174">Normalmente, las columnas se encuentran durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> porque se trata del primer método en tiempo de ejecución donde la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> pasa a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="e146b-174">Typically columns are located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> because this is the first run-time method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property becomes available.</span></span>  
  
 <span data-ttu-id="e146b-175">En el siguiente ejemplo de código se muestra un componente que busca índices de columnas en su columna de colección de columnas de entrada y salida durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="e146b-175">The following code example shows a component that locates indexes of the columns in its input and output column collection during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span> <span data-ttu-id="e146b-176">Los índices de columna se almacenan en una matriz entera y el componente puede tener acceso a ellos durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="e146b-176">The column indexes are stored in an integer array, and can be accessed by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
```csharp  
int []inputColumns;  
int []outputColumns;  
  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];  
  
    inputColumns = new int[input.InputColumnCollection.Count];  
    outputColumns = new int[output.OutputColumnCollection.Count];  
  
    for(int col=0; col < input.InputColumnCollection.Count; col++)  
    {  
        IDTSInputColumn100 inputColumn = input.InputColumnCollection[col];  
        inputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID);  
    }  
  
    for(int col=0; col < output.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 outputColumn = output.OutputColumnCollection[col];  
        outputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID);  
    }  
  
}  
```  
  
```vb  
Public Overrides Sub PreExecute()  
  
    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)  
  
    ReDim inputColumns(input.InputColumnCollection.Count)  
    ReDim outputColumns(output.OutputColumnCollection.Count)  
  
    For col As Integer = 0 To input.InputColumnCollection.Count  
  
        Dim inputColumn As IDTSInputColumn100 = input.InputColumnCollection(col)  
        inputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID)  
    Next  
  
    For col As Integer = 0 To output.OutputColumnCollection.Count  
  
        Dim outputColumn As IDTSOutputColumn100 = output.OutputColumnCollection(col)  
        outputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID)  
    Next  
  
End Sub  
```  
  
### <a name="processing-rows"></a><span data-ttu-id="e146b-177">Procesar las filas</span><span class="sxs-lookup"><span data-stu-id="e146b-177">Processing Rows</span></span>  
 <span data-ttu-id="e146b-178">Los componentes reciben objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> que contienen filas y columnas del método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="e146b-178">Components receive <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain rows and columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="e146b-179">Durante este método las filas en el búfer se iteran y las columnas identificadas durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> se pueden leer y modificar.</span><span class="sxs-lookup"><span data-stu-id="e146b-179">During this method the rows in the buffer are iterated, and the columns identified during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> are read and modified.</span></span> <span data-ttu-id="e146b-180">La tarea de flujo de datos llama repetidamente al método hasta que el componente de nivel superior no proporciona más filas.</span><span class="sxs-lookup"><span data-stu-id="e146b-180">The method is called repeatedly by the data flow task until no more rows are provided from the upstream component.</span></span>  
  
 <span data-ttu-id="e146b-181">Se lee o se escribe una columna individual en el búfer mediante el método de acceso al indizador de matrices o mediante uno de los métodos `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="e146b-181">An individual column in the buffer is read or written by using the array indexer access method, or by using one of the `Get` or `Set` methods.</span></span> <span data-ttu-id="e146b-182">Los métodos `Get` y `Set` son más eficaces y se deben usar cuando se conoce el tipo de datos de la columna en el búfer.</span><span class="sxs-lookup"><span data-stu-id="e146b-182">The `Get` and `Set` methods are more efficient and should be used when the data type of the column in the buffer is known.</span></span>  
  
 <span data-ttu-id="e146b-183">En el siguiente ejemplo de código se muestra una implementación del método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> que procesa las filas entrantes.</span><span class="sxs-lookup"><span data-stu-id="e146b-183">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method that processes incoming rows.</span></span>  
  
```csharp  
public override void ProcessInput( int InputID, PipelineBuffer buffer)  
{  
       while( buffer.NextRow())  
       {  
            for(int x=0; x < inputColumns.Length;x++)  
            {  
                if(!buffer.IsNull(inputColumns[x]))  
                {  
                    object columnData = buffer[inputColumns[x]];  
                    // TODO: Modify the column data.  
                    buffer[inputColumns[x]] = columnData;  
                }  
            }  
  
      }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal InputID As Integer, ByVal buffer As PipelineBuffer)  
  
        While (buffer.NextRow())  
  
            For x As Integer = 0 To inputColumns.Length  
  
                if buffer.IsNull(inputColumns(x)) = false then  
  
                    Dim columnData As Object = buffer(inputColumns(x))  
                    ' TODO: Modify the column data.  
                    buffer(inputColumns(x)) = columnData  
  
                End If  
            Next  
  
        End While  
End Sub  
```  
  
## <a name="sample"></a><span data-ttu-id="e146b-184">Muestra</span><span class="sxs-lookup"><span data-stu-id="e146b-184">Sample</span></span>  
 <span data-ttu-id="e146b-185">En el ejemplo siguiente se muestra un componente de transformación simple con salidas sincrónicas que convierte en mayúsculas los valores de todas las columnas de cadena.</span><span class="sxs-lookup"><span data-stu-id="e146b-185">The following sample shows a simple transformation component with synchronous outputs that converts the values of all string columns to uppercase.</span></span> <span data-ttu-id="e146b-186">En este ejemplo no se muestran todos los métodos ni funcionalidad tratados en este tema.</span><span class="sxs-lookup"><span data-stu-id="e146b-186">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="e146b-187">Muestra los métodos importantes que cada componente de transformación personalizado con salidas sincrónicas debe invalidar, pero no contiene código para la validación en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="e146b-187">It demonstrates the important methods that every custom transformation component with synchronous outputs must override, but does not contain code for design-time validation.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
  
namespace Uppercase  
{  
  [DtsPipelineComponent(DisplayName = "Uppercase")]  
  public class Uppercase : PipelineComponent  
  {  
    ArrayList m_ColumnIndexList = new ArrayList();  
  
    public override void ProvideComponentProperties()  
    {  
      base.ProvideComponentProperties();  
      ComponentMetaData.InputCollection[0].Name = "Uppercase Input";  
      ComponentMetaData.OutputCollection[0].Name = "Uppercase Output";  
    }  
  
    public override void PreExecute()  
    {  
      IDTSInput100 input = ComponentMetaData.InputCollection[0];  
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;  
  
      foreach (IDTSInputColumn100 column in inputColumns)  
      {  
        if (column.DataType == DataType.DT_STR || column.DataType == DataType.DT_WSTR)  
        {  
          m_ColumnIndexList.Add((int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID));  
        }  
      }  
    }  
  
    public override void ProcessInput(int inputID, PipelineBuffer buffer)  
    {  
      while (buffer.NextRow())  
      {  
        foreach (int columnIndex in m_ColumnIndexList)  
        {  
          string str = buffer.GetString(columnIndex);  
          buffer.SetString(columnIndex, str.ToUpper());  
        }  
      }  
    }  
  }  
}  
```  
  
```vb  
Imports System   
Imports System.Collections   
Imports Microsoft.SqlServer.Dts.Pipeline   
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper   
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper   
Namespace Uppercase   
  
 <DtsPipelineComponent(DisplayName="Uppercase")> _   
 Public Class Uppercase   
 Inherits PipelineComponent   
   Private m_ColumnIndexList As ArrayList = New ArrayList   
  
   Public  Overrides Sub ProvideComponentProperties()   
     MyBase.ProvideComponentProperties   
     ComponentMetaData.InputCollection(0).Name = "Uppercase Input"   
     ComponentMetaData.OutputCollection(0).Name = "Uppercase Output"   
   End Sub   
  
   Public  Overrides Sub PreExecute()   
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection   
     For Each column As IDTSInputColumn100 In inputColumns   
       If column.DataType = DataType.DT_STR OrElse column.DataType = DataType.DT_WSTR Then   
         m_ColumnIndexList.Add(CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer))   
       End If   
     Next   
   End Sub   
  
   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
     While buffer.NextRow   
       For Each columnIndex As Integer In m_ColumnIndexList   
         Dim str As String = buffer.GetString(columnIndex)   
         buffer.SetString(columnIndex, str.ToUpper)   
       Next   
     End While   
   End Sub   
 End Class   
End Namespace  
```  
  
<span data-ttu-id="e146b-188">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e146b-188">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e146b-189">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="e146b-189">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e146b-190">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="e146b-190">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e146b-191">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="e146b-191">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e146b-192">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e146b-192">See Also</span></span>  
 <span data-ttu-id="e146b-193">[Desarrollar un componente de transformación personalizado con salidas asincrónicas](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span><span class="sxs-lookup"><span data-stu-id="e146b-193">[Developing a Custom Transformation Component with Asynchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span></span>  
 <span data-ttu-id="e146b-194">[Descripción de las transformaciones sincrónicas y asincrónicas](../understanding-synchronous-and-asynchronous-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="e146b-194">[Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) </span></span>  
 [<span data-ttu-id="e146b-195">Crear una transformación sincrónica con el componente de script</span><span class="sxs-lookup"><span data-stu-id="e146b-195">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
