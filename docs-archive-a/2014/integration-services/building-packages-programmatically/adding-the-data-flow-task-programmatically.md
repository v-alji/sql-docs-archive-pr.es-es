---
title: Agregar la tarea Flujo de datos mediante programación | Microsoft Docs
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
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f7e699cc8e88bafb2a4508fdac8560fa73befe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671643"
---
# <a name="adding-the-data-flow-task-programmatically"></a><span data-ttu-id="f7570-102">Agregar la tarea de flujo de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="f7570-102">Adding the Data Flow Task Programmatically</span></span>
  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="f7570-103">incluye una tarea denominada Flujo de datos, representada por el espacio de nombres <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="f7570-103">includes a task called the Data Flow task, which is represented by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> namespace in the object model.</span></span> <span data-ttu-id="f7570-104">La tarea Flujo de datos es una tarea especializada de alto rendimiento que se dedica a transformar y mover datos durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="f7570-104">The Data Flow task is a specialized, high-performance task, dedicated to transforming and moving data during package execution.</span></span> <span data-ttu-id="f7570-105">Al igual que ocurre con otras tareas, la tarea Flujo de datos está incluida en el objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> y, desde la perspectiva del motor en tiempo de ejecución, esta tarea es simplemente una más del paquete.</span><span class="sxs-lookup"><span data-stu-id="f7570-105">Like other tasks, the Data Flow task is wrapped by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object, and from the perspective of the run-time engine, this task is just another task in the package.</span></span> <span data-ttu-id="f7570-106">Sin embargo, el flujo de datos contiene objetos adicionales denominados componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f7570-106">However, the data flow contains additional objects called data flow components.</span></span> <span data-ttu-id="f7570-107">Estos componentes son aquellos que hacen que se muevan los datos de un origen a un destino, a veces a través de una transformación.</span><span class="sxs-lookup"><span data-stu-id="f7570-107">These components are the components that make data move from a source to a destination, sometimes through a transformation.</span></span> <span data-ttu-id="f7570-108">Los componentes definen tanto la dirección del movimiento como la forma en que se transforman los datos.</span><span class="sxs-lookup"><span data-stu-id="f7570-108">The components define both the direction of movement and how data is transformed.</span></span> <span data-ttu-id="f7570-109">La configuración de la tarea Flujo de datos implica agregar componentes a la tarea y conectarlos después para establecer el flujo de datos y lograr la transformación deseada.</span><span class="sxs-lookup"><span data-stu-id="f7570-109">Configuring the Data Flow task involves adding components to the task, and then connecting them to establish the flow of data and achieve the intended transformation.</span></span>  
  
 <span data-ttu-id="f7570-110">Existen tres tipos de componentes en una tarea Flujo de datos: **Orígenes de flujo de datos**, **Transformaciones de flujo de datos** y **Destinos de flujo de datos**, que aparecen en este orden en el cuadro de herramientas del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7570-110">There are three types of components within a Data Flow task: **Data Flow Sources**, **Data Flow Transformations**, and **Data Flow Destinations**, shown in that order within the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer toolbox.</span></span> <span data-ttu-id="f7570-111">También se hace referencia a estos tipos de forma más sencilla como orígenes, transformaciones o destinos.</span><span class="sxs-lookup"><span data-stu-id="f7570-111">These types are also referred to more simply as sources, transformations, or destinations.</span></span> <span data-ttu-id="f7570-112">Como los nombres indican, los datos fluyen desde un origen a una transformación y, después, a un destino.</span><span class="sxs-lookup"><span data-stu-id="f7570-112">As implied by the names, data flows from a source to a transformation, and then to a destination.</span></span> <span data-ttu-id="f7570-113">Ésta es una descripción simplista del flujo de datos para ilustrar el concepto, pero la tarea Flujo de datos es suficientemente flexible y eficaz para controlar varios orígenes y conectar numerosas transformaciones que envíen resultados a múltiples destinos.</span><span class="sxs-lookup"><span data-stu-id="f7570-113">This is a simplistic description of the data flow to illustrate the concept, but the Data Flow task is flexible and powerful enough to handle multiple sources, and to connect together many transformations that send output to multiple destinations.</span></span>  
  
 <span data-ttu-id="f7570-114">La tarea Flujo de datos se agrega a un paquete de la misma forma que otras tareas.</span><span class="sxs-lookup"><span data-stu-id="f7570-114">The Data Flow task is added to a package the same way other tasks are added.</span></span> <span data-ttu-id="f7570-115">Una vez agregada, la tarea se configura; para ello, se agregan componentes a la tarea de flujo de datos y, después, se configuran y conectan sus componentes.</span><span class="sxs-lookup"><span data-stu-id="f7570-115">After the task has been added, it is configured by adding components to the data flow task, and configuring and connecting components in the task.</span></span>  
  
## <a name="sample"></a><span data-ttu-id="f7570-116">Muestra</span><span class="sxs-lookup"><span data-stu-id="f7570-116">Sample</span></span>  
 <span data-ttu-id="f7570-117">En el ejemplo de código siguiente se muestra cómo agregar una tarea Flujo de datos a un paquete.</span><span class="sxs-lookup"><span data-stu-id="f7570-117">The following code sample shows how to add a Data Flow task to a package.</span></span> <span data-ttu-id="f7570-118">En este ejemplo, es necesario establecer una referencia a los ensamblados Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap y Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="f7570-118">This example requires a reference to the assemblies Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap, and Microsoft.SqlServer.ManagedDTS.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="f7570-119">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="f7570-119">External Resources</span></span>  
 <span data-ttu-id="f7570-120">Entrada de blog sobre [EzAPI, actualizado para SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="f7570-120">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="f7570-121">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f7570-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f7570-122">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="f7570-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f7570-123">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="f7570-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f7570-124">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="f7570-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7570-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7570-125">See Also</span></span>  
 [<span data-ttu-id="f7570-126">Detectar componentes de flujo de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="f7570-126">Discovering Data Flow Components Programmatically</span></span>](../building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  
