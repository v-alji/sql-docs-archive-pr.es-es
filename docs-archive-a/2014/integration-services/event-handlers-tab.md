---
title: Pestaña controladores de eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673804"
---
# <a name="event-handlers-tab"></a><span data-ttu-id="8d568-102">Pestaña Controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="8d568-102">Event Handlers Tab</span></span>
  <span data-ttu-id="8d568-103">Utilice la pestaña **Controladores de eventos** del Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] para generar un flujo de control en un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d568-103">Use the **Event Handlers** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to build a control flow in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="8d568-104">Un controlador de eventos se ejecuta en respuesta a un evento generado por el paquete o por una tarea o un contenedor de un paquete.</span><span class="sxs-lookup"><span data-stu-id="8d568-104">An event handler runs in response to an event raised by the package or by a task or container in the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d568-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="8d568-105">Options</span></span>  
 <span data-ttu-id="8d568-106">**Executable**</span><span class="sxs-lookup"><span data-stu-id="8d568-106">**Executable**</span></span>  
 <span data-ttu-id="8d568-107">Seleccione el ejecutable para el cual desea generar un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8d568-107">Select the executable for which you want to build an event handler.</span></span> <span data-ttu-id="8d568-108">El ejecutable puede ser el paquete, o una tarea o contenedores del paquete.</span><span class="sxs-lookup"><span data-stu-id="8d568-108">The executable can be the package, or a task or containers in the package.</span></span>  
  
 <span data-ttu-id="8d568-109">**Controlador de eventos**</span><span class="sxs-lookup"><span data-stu-id="8d568-109">**Event handler**</span></span>  
 <span data-ttu-id="8d568-110">Seleccione un tipo de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8d568-110">Select a type of event handler.</span></span> <span data-ttu-id="8d568-111">Cree el controlador de eventos arrastrando los elementos desde el **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="8d568-111">Create the event handler by dragging items from the **Toolbox**.</span></span>  
  
 <span data-ttu-id="8d568-112">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="8d568-112">**Delete**</span></span>  
 <span data-ttu-id="8d568-113">Seleccione un controlador de eventos y elimínelo del paquete haciendo clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8d568-113">Select an event handler, and remove it from the package by clicking **Delete**.</span></span>  
  
 <span data-ttu-id="8d568-114">**Haga clic aquí para crear un \<event handler name> para el ejecutable \<executable name>** .</span><span class="sxs-lookup"><span data-stu-id="8d568-114">**Click here to create an \<event handler name> for the executable \<executable name>**</span></span>  
 <span data-ttu-id="8d568-115">Haga clic aquí para crear el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8d568-115">Click to create the event handler.</span></span>  
  
 <span data-ttu-id="8d568-116">Cree el flujo de control arrastrando objetos gráficos que representan contenedores y tareas de [!INCLUDE[ssIS](../includes/ssis-md.md)] desde el **Cuadro de herramientas** a la superficie de diseño de la pestaña **Controladores de eventos** y, a continuación, conecte los objetos utilizando las restricciones de precedencia para definir la secuencia en que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="8d568-116">Create the control flow by dragging graphical objects that represent [!INCLUDE[ssIS](../includes/ssis-md.md)] tasks and containers from the **Toolbox** to the design surface of the **Event Handlers** tab, and then connecting the objects by using precedence constraints to define the sequence in which they run.</span></span>  
  
 <span data-ttu-id="8d568-117">Además, para agregar anotaciones, haga clic con el botón derecho en la superficie de diseño y, después, en el menú, haga clic en **Agregar anotación**.</span><span class="sxs-lookup"><span data-stu-id="8d568-117">Additionally, to add annotations, right-click the design surface, and then on the menu, click **Add Annotation**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d568-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d568-118">See Also</span></span>  
 <span data-ttu-id="8d568-119">[Controladores de eventos de Integration Services &#40;SSIS&#41;](integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="8d568-119">[Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="8d568-120">[Flujo de control](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8d568-120">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="8d568-121">[Diseñador SSIS](ssis-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8d568-121">[SSIS Designer](ssis-designer.md) </span></span>  
 [<span data-ttu-id="8d568-122">Controladores de eventos de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8d568-122">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
