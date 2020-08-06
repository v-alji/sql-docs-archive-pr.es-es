---
title: Depurar un paquete estableciendo puntos de interrupción en una tarea o un contenedor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], breakpoints
- breakpoints [Integration Services]
- tasks [Integration Services], breakpoints
ms.assetid: e7fa106a-2221-403a-bb74-efc9f12bb450
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 21e334faff95e63e59bbf9c40fdf7e479de949da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669760"
---
# <a name="debug-a-package-by-setting-breakpoints-on-a-task-or-a-container"></a><span data-ttu-id="eb61c-102">Depurar un paquete estableciendo puntos de interrupción en una tarea o un contenedor</span><span class="sxs-lookup"><span data-stu-id="eb61c-102">Debug a Package by Setting Breakpoints on a Task or a Container</span></span>
  <span data-ttu-id="eb61c-103">Este procedimiento describe cómo establecer puntos de interrupción en un paquete, una tarea, un contenedor de bucles For o Foreach o un contenedor de secuencias.</span><span class="sxs-lookup"><span data-stu-id="eb61c-103">This procedure describes how to set breakpoints in a package, a task, a For Loop container, a Foreach Loop container, or a Sequence container.</span></span>  
  
### <a name="to-set-breakpoints-in-a-package-a-task-or-a-container"></a><span data-ttu-id="eb61c-104">Para establecer puntos de interrupción en un paquete, una tarea o un contenedor</span><span class="sxs-lookup"><span data-stu-id="eb61c-104">To set breakpoints in a package, a task, or a container</span></span>  
  
1.  <span data-ttu-id="eb61c-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="eb61c-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="eb61c-106">Haga doble clic en el paquete en el que desee establecer puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="eb61c-106">Double-click the package in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="eb61c-107">En el Diseñador SSIS, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="eb61c-107">In SSIS Designer, do the following:</span></span>  
  
    -   <span data-ttu-id="eb61c-108">Para establecer puntos de interrupción en el objeto de paquete, haga clic en la pestaña **Flujo de control** , coloque el cursor en cualquier lugar del fondo de la superficie de diseño, haga clic con el botón derecho y, después, haga clic en **Editar puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="eb61c-108">To set breakpoints in the package object, click the **Control Flow** tab, place the cursor anywhere on the background of the design surface, right-click, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="eb61c-109">Para establecer puntos de interrupción en un flujo de control de paquete, haga clic en la pestaña **Flujo de control** , haga clic con el botón derecho en una tarea, un contenedor de bucles For o Foreach o un contenedor de secuencias y, después, haga clic en **Editar puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="eb61c-109">To set breakpoints in a package control flow, click the **Control Flow** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="eb61c-110">Para establecer puntos de interrupción en un controlador de eventos, haga clic en la pestaña **Controlador de eventos** , haga clic con el botón derecho en una tarea, un contenedor de bucles For o Foreach o un contenedor de secuencias y, después, haga clic en **Editar puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="eb61c-110">To set breakpoints in an event handler, click the **Event Handler** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
4.  <span data-ttu-id="eb61c-111">En el cuadro de diálogo **Establecer puntos de interrupción \<container name>** , seleccione los puntos de interrupción que quiera habilitar.</span><span class="sxs-lookup"><span data-stu-id="eb61c-111">In the **Set Breakpoints \<container name>** dialog box, select the breakpoints to enable.</span></span>  
  
5.  <span data-ttu-id="eb61c-112">Opcionalmente, modifique el tipo y la cantidad de número de llamadas para cada punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="eb61c-112">Optionally, modify the hit count type and the hit count number for each breakpoint.</span></span>  
  
6.  <span data-ttu-id="eb61c-113">Para guardar el paquete, haga clic en **Guardar los elementos seleccionados** , en el menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="eb61c-113">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb61c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb61c-114">See Also</span></span>  
 <span data-ttu-id="eb61c-115">[Herramientas para solucionar problemas con el desarrollo de paquetes](troubleshooting/troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="eb61c-115">[Troubleshooting Tools for Package Development](troubleshooting/troubleshooting-tools-for-package-development.md) </span></span>  
 <span data-ttu-id="eb61c-116">[Depurar un script estableciendo puntos de interrupción en una tarea script y un componente script](data-flow/transformations/script-component.md) </span><span class="sxs-lookup"><span data-stu-id="eb61c-116">[Debug a Script by Setting Breakpoints in a Script Task and Script Component](data-flow/transformations/script-component.md) </span></span>  
 <span data-ttu-id="eb61c-117">[Codificar y depurar la tarea script](control-flow/script-task.md) </span><span class="sxs-lookup"><span data-stu-id="eb61c-117">[Coding and Debugging the Script Task](control-flow/script-task.md) </span></span>  
 [<span data-ttu-id="eb61c-118">Codificar y depurar el componente de script</span><span class="sxs-lookup"><span data-stu-id="eb61c-118">Coding and Debugging the Script Component</span></span>](extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md)  
  
  
