---
title: Plan de ejecución y asignación de búfer | Microsoft Docs
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
- custom data flow components [Integration Services], buffer allocations
- custom data flow components [Integration Services], execution plans
- buffer allocations [Integration Services]
- data flow components [Integration Services], buffer allocations
- data flow components [Integration Services], execution plans
- execution plans [Integration Services]
ms.assetid: 679d9ff0-641e-47c3-abb8-d1a7dcb279dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03b8bb22988ccf77f8920252ac2d600478c92f3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744791"
---
# <a name="execution-plan-and-buffer-allocation"></a><span data-ttu-id="76df4-102">Plan de ejecución y asignación de búfer</span><span class="sxs-lookup"><span data-stu-id="76df4-102">Execution Plan and Buffer Allocation</span></span>
  <span data-ttu-id="76df4-103">Antes de la ejecución, la tarea de flujo de datos examina sus componentes y genera un plan de ejecución para cada secuencia de componentes.</span><span class="sxs-lookup"><span data-stu-id="76df4-103">Before execution, the data flow task examines its components and generates an execution plan for each sequence of components.</span></span> <span data-ttu-id="76df4-104">En esta sección se proporcionan detalles sobre el plan de ejecución, cómo ver el plan y cómo se asignan búferes de entrada y salida en función del plan de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76df4-104">This section provides details about the execution plan, how to view the plan, and how input and output buffers are allocated based on the execution plan.</span></span>  
  
## <a name="understanding-the-execution-plan"></a><span data-ttu-id="76df4-105">Descripción del plan de ejecución</span><span class="sxs-lookup"><span data-stu-id="76df4-105">Understanding the Execution Plan</span></span>  
 <span data-ttu-id="76df4-106">Un plan de ejecución contiene subprocesos de origen y de trabajo; cada subproceso contiene listas de trabajo que especifican listas de trabajo de salida para los subprocesos de origen o listas de trabajo de entrada y salida para los subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76df4-106">An execution plan contains source threads and work threads, and each thread contains work lists that specify output work lists for source threads or input and output work lists for work threads.</span></span> <span data-ttu-id="76df4-107">Los subprocesos de origen de un plan de ejecución representan los componentes de origen del flujo de datos y se identifican en el plan de ejecución mediante *SourceThread\*\*n*, donde *n* es el número de base cero del subproceso de origen.</span><span class="sxs-lookup"><span data-stu-id="76df4-107">The source threads in an execution plan represent the source components in the data flow and are identified in the execution plan by *SourceThread\*\*n*, where *n* is the zero-based number of the source thread.</span></span>  
  
 <span data-ttu-id="76df4-108">Cada subproceso de origen crea un búfer, establece un agente de escucha y llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> en el componente de origen.</span><span class="sxs-lookup"><span data-stu-id="76df4-108">Each source thread creates a buffer, sets a listener, and calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method on the source component.</span></span> <span data-ttu-id="76df4-109">Aquí es donde se inicia la ejecución y se original los datos, a medida que el componente de origen comienza a agregar filas a los búferes de salida que le proporciona la tarea de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="76df4-109">This is where execution starts and data originates, as the source component starts adding rows to the output buffers that are provided to it by the data flow task.</span></span> <span data-ttu-id="76df4-110">Una vez que los subprocesos de origen se están ejecutando, el equilibrio de trabajo se distribuye entre subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76df4-110">After the source threads are running, the balance of work is distributed among work threads.</span></span>  
  
 <span data-ttu-id="76df4-111">Un subproceso de trabajo puede contener listas de trabajo de entrada y salida, y se identifica en el plan de ejecución como *WorkThread\*\*n*, donde *n* es el número de base cero del subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76df4-111">A work thread may contain both input and output work lists and is identified in the execution plan as *WorkThread\*\*n*, where *n* is the zero-based number of the work thread.</span></span> <span data-ttu-id="76df4-112">Estos subproceso contienen listas de trabajo de salida cuando el gráfico contiene un componente con salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="76df4-112">These threads contain output work lists when the graph contains a component with asynchronous outputs.</span></span>  
  
 <span data-ttu-id="76df4-113">El plan de ejecución de ejemplo siguiente representa un flujo de datos que contiene un componente de origen conectado a una transformación con una salida asincrónica conectada a un componente de destino.</span><span class="sxs-lookup"><span data-stu-id="76df4-113">The following sample execution plan represents a data flow that contains a source component connected to a transformation with an asynchronous output connected to a destination component.</span></span> <span data-ttu-id="76df4-114">En este ejemplo, WorkThread0 contiene una lista de trabajo de salida porque el componente de transformación tiene una salida asincrónica.</span><span class="sxs-lookup"><span data-stu-id="76df4-114">In this example, WorkThread0 contains an output work list because the transformation component has an asynchronous output.</span></span>  
  
```  
SourceThread0   
    Influences: 72 158   
    Output Work List   
        CreatePrimeBuffer of type 1 for output id 10   
        SetBufferListener: "WorkThread0" for input ID 73   
        CallPrimeOutput on component "OLE DB Source" (1)   
    End Output Work List   
    This thread drives 0 distributors   
End SourceThread0   
WorkThread0   
    Influences: 72 158   
    Input Work list, input ID 73   
        CallProcessInput on input ID 73 on component "Sort" (72) for view type 2   
    End Input Work list for input 73   
    Output Work List   
        CreatePrimeBuffer of type 3 for output id 74   
        SetBufferListener: "WorkThread1" for input ID 171with internal handoff   
        CallPrimeOutput on component "Sort" (72)   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread0   
WorkThread1   
    Influences: 158   
    Input Work list, input ID 171  
        CallProcessInput on input ID 171 on component "OLE DB Destination" (158) for view type 4  
    End Input Work list for input 171   
    Output Work List   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="76df4-115">El plan de ejecución se genera cada vez que se ejecuta un paquete y se puede capturar agregando un proveedor de registro al paquete, habilitando el registro y seleccionando el evento **PipelineExecutionPlan**.</span><span class="sxs-lookup"><span data-stu-id="76df4-115">The execution plan is generated every time a package is executed, and can be captured by adding a log provider to the package, enabling logging, and selecting the **PipelineExecutionPlan** event.</span></span>  
  
## <a name="understanding-buffer-allocation"></a><span data-ttu-id="76df4-116">Descripción de la asignación de búferes</span><span class="sxs-lookup"><span data-stu-id="76df4-116">Understanding Buffer Allocation</span></span>  
 <span data-ttu-id="76df4-117">La tarea de flujo de datos, basándose en el plan de ejecución, crea búferes que contienen las columnas definidas en las salidas de los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="76df4-117">Based on the execution plan, the data flow task creates buffers that contain the columns defined in the outputs of the data flow components.</span></span> <span data-ttu-id="76df4-118">El búfer se reutiliza a media que los datos fluyen a través de la secuencia de componentes, hasta que se encuentra un componente con salidas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="76df4-118">The buffer is reused as the data flows through the sequence of components, until a component with asynchronous outputs is encountered.</span></span> <span data-ttu-id="76df4-119">Entonces, se crea un nuevo búfer que contiene las columnas de salida de la salida asincrónica y las columnas de salida de componentes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="76df4-119">Then, a new buffer is created, which contains the output columns of the asynchronous output and the output columns of downstream components.</span></span>  
  
 <span data-ttu-id="76df4-120">Durante la ejecución, los componentes tienen acceso al búfer en el subproceso de origen o trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="76df4-120">During execution, components have access to the buffer in the current source or work thread.</span></span> <span data-ttu-id="76df4-121">El búfer es un búfer de entrada, que proporciona el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, o un búfer de salida, que proporciona el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="76df4-121">The buffer is either an input buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, or an output buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="76df4-122">La propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> también identifica cada búfer como búfer de entrada o salida.</span><span class="sxs-lookup"><span data-stu-id="76df4-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> also identifies each buffer as an input or output buffer.</span></span>  
  
 <span data-ttu-id="76df4-123">Los componentes de transformación con salidas asincrónicas reciben el búfer de entrada existente del método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> y reciben el nuevo búfer de salida del método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="76df4-123">Transformation components with asynchronous outputs receive the existing input buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, and receive the new output buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="76df4-124">Un componente de transformación con salidas asincrónicas es el único tipo de componente de flujo de datos que recibe un búfer de entrada y un búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="76df4-124">A transformation component with asynchronous outputs is the only type of data flow component that receives both an input and an output buffer.</span></span>  
  
 <span data-ttu-id="76df4-125">Es probable que el búfer que se proporciona a un componente contenga más columnas de las que el componente incluye en sus colecciones de columnas de entrada o salida, los desarrolladores de componentes pueden llamar al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> para localizar una columna en el búfer mediante la especificación de su valor `LineageID`.</span><span class="sxs-lookup"><span data-stu-id="76df4-125">Because the buffer provided to a component is likely to contain more columns than the component has in its input or output column collections, component developers can call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method to locate a column in the buffer by specifying its `LineageID`.</span></span>  
  
<span data-ttu-id="76df4-126">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="76df4-126">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="76df4-127">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="76df4-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="76df4-128">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="76df4-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="76df4-129">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="76df4-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
