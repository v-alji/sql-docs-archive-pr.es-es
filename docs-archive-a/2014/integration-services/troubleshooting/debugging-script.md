---
title: Depurar script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Script task [Integration Services], debugging
- debugging [Integration Services], scripts
- scripts [Integration Services], debugging
ms.assetid: fddf57d8-8607-4f88-85a0-1b683087b491
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7926f806f20f76c7aaac0c22b970addc5e93a78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748165"
---
# <a name="debugging-script"></a><span data-ttu-id="ac91f-102">Depurar script</span><span class="sxs-lookup"><span data-stu-id="ac91f-102">Debugging Script</span></span>
  <span data-ttu-id="ac91f-103">Escriba los scripts que la tarea Script y el componente Script usan, en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools para aplicaciones (VSTA).</span><span class="sxs-lookup"><span data-stu-id="ac91f-103">You write the scripts that the Script task and Script component use, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
 <span data-ttu-id="ac91f-104">EN VSTA se establecen y programan los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="ac91f-104">You set and script breakpoints in VSTA.</span></span> <span data-ttu-id="ac91f-105">Puede administrar los puntos de interrupción en VSTA, pero también puede administrar los puntos de interrupción mediante el cuadro de diálogo **Establecer puntos de interrupción** que proporciona el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac91f-105">You can manage breakpoints in VSTA, but you can also manage the breakpoints using the **Set Breakpoints** dialog box that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides.</span></span> <span data-ttu-id="ac91f-106">Para más información, consulte [Debugging Control Flow](debugging-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="ac91f-106">For more information, see [Debugging Control Flow](debugging-control-flow.md).</span></span>  
  
 <span data-ttu-id="ac91f-107">El cuadro de diálogo **Establecer puntos de interrupción** incluye los puntos de interrupción del script.</span><span class="sxs-lookup"><span data-stu-id="ac91f-107">The **Set Breakpoints** dialog box includes the script breakpoints.</span></span> <span data-ttu-id="ac91f-108">Estos puntos de interrupción aparecen en la parte inferior de la lista de puntos de interrupción, y muestran el número de línea y el nombre de la función en que aparece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="ac91f-108">These breakpoints appear at the bottom of the breakpoint list, and display the line number and the name of the function in which the breakpoint appears.</span></span> <span data-ttu-id="ac91f-109">Es posible eliminar un punto de interrupción de script en el cuadro de diálogo **Establecer puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="ac91f-109">You can delete a script breakpoint from the **Set Breakpoints** dialog box.</span></span>  
  
 <span data-ttu-id="ac91f-110">En tiempo de ejecución, los puntos de interrupción establecidos en líneas de código del script se integran con los puntos de interrupción establecidos en el paquete o las tareas y contenedores del paquete.</span><span class="sxs-lookup"><span data-stu-id="ac91f-110">At run time, the breakpoints set on lines of code in script are integrated with the breakpoints set on the package or the tasks and containers in the package.</span></span> <span data-ttu-id="ac91f-111">El depurador puede ejecutarse desde un punto de interrupción en el script hasta un conjunto de puntos de interrupción en el paquete, tarea o contenedor, y viceversa.</span><span class="sxs-lookup"><span data-stu-id="ac91f-111">The debugger can run from a breakpoint in the script to a breakpoint set on the package, task, or container, and vice versa.</span></span> <span data-ttu-id="ac91f-112">Por ejemplo, un paquete puede tener puntos de interrupción establecidos en las condiciones de interrupción que se producen cuando el paquete recibe los eventos **OnPreExecute** y **OnPostExecute** y también puede tener una tarea Script que tiene puntos de interrupción en líneas de su script.</span><span class="sxs-lookup"><span data-stu-id="ac91f-112">For example, a package might have breakpoints set on the break conditions that occur when the package receives the **OnPreExecute** and **OnPostExecute** events, and also have a Script task that has breakpoints on lines of its script.</span></span> <span data-ttu-id="ac91f-113">En este escenario, el paquete puede suspender la ejecución en la condición de interrupción asociada al evento **OnPreExecute** , ejecutar los puntos de interrupción en el script y finalmente ejecutarse en la condición de interrupción asociada con el evento **OnPostExecute** .</span><span class="sxs-lookup"><span data-stu-id="ac91f-113">In this scenario, the package can suspend execution on the break condition associated with the **OnPreExecute** event, run to the breakpoints in the script, and finally run to the break condition associated with the **OnPostExecute** event.</span></span>  
  
 <span data-ttu-id="ac91f-114">Para obtener más información acerca de cómo depurar la tarea Script y el componente Script, vea [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) y [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="ac91f-114">For more information about debugging the Script task and Script component, see [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) and [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>  
  
### <a name="to-set-a-breakpoint-in-visual-studio-for-applications"></a><span data-ttu-id="ac91f-115">Para establecer un punto de interrupción en Visual Studio para Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ac91f-115">To set a breakpoint in Visual Studio for Applications</span></span>  
  
-   [<span data-ttu-id="ac91f-116">Depurar un script mediante el establecimiento de puntos de interrupción en una tarea Script y un componente de script</span><span class="sxs-lookup"><span data-stu-id="ac91f-116">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>](../extending-packages-scripting/debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac91f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac91f-117">See Also</span></span>  
 [<span data-ttu-id="ac91f-118">Herramientas para solucionar problemas con el desarrollo de paquetes</span><span class="sxs-lookup"><span data-stu-id="ac91f-118">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
