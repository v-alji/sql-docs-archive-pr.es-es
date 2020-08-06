---
title: Depurar un script estableciendo puntos de interrupción en una tarea Script y un componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- breakpoints [Integration Services]
- scripts [Integration Services], breakpoints
ms.assetid: 6c03464f-3f7d-4882-b7f8-8e396f8e2944
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45e7ffc6680c33e3b17b9b39fba0aabd8fa4028c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670444"
---
# <a name="debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component"></a><span data-ttu-id="31113-102">Depurar un script estableciendo puntos de interrupción en una tarea Script y un componente Script</span><span class="sxs-lookup"><span data-stu-id="31113-102">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>
  <span data-ttu-id="31113-103">Este procedimiento describe cómo establecer puntos de interrupción en los scripts que se utilizan en la tarea Script y en el componente Script.</span><span class="sxs-lookup"><span data-stu-id="31113-103">This procedure describes how to set breakpoints in the scripts that are used in the Script task and Script component.</span></span>  
  
 <span data-ttu-id="31113-104">Después de establecer puntos de interrupción en el script, en el cuadro de diálogo **Establecer puntos de interrupción - \<object name>** se muestran los puntos de interrupción junto con los puntos de interrupción integrados.</span><span class="sxs-lookup"><span data-stu-id="31113-104">After you set breakpoints in the script, the **Set Breakpoints - \<object name>** dialog box lists the breakpoints, along with the built-in breakpoints.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="31113-105">En determinadas circunstancias, se omiten los puntos de interrupción en la tarea Script y el componente de script.</span><span class="sxs-lookup"><span data-stu-id="31113-105">Under certain circumstances, breakpoints in the Script task and Script component are ignored.</span></span> <span data-ttu-id="31113-106">Para obtener más información, vea la sección **depurar la tarea script** en [codificar y depurar la tarea script](../control-flow/script-task.md) y la sección **depurar el componente de script** en [codificar y depurar el componente de script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="31113-106">For more information, see the **Debugging the Script Task** section in [Coding and Debugging the Script Task](../control-flow/script-task.md) and the **Debugging the Script Component** section in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span></span>  
  
### <a name="to-set-a-breakpoint-in-script"></a><span data-ttu-id="31113-107">Para establecer un punto de interrupción en un script</span><span class="sxs-lookup"><span data-stu-id="31113-107">To set a breakpoint in script</span></span>  
  
1.  <span data-ttu-id="31113-108">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="31113-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="31113-109">Haga doble clic en el paquete que contiene el script en la que desea establecer puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="31113-109">Double-click the package that contains the script in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="31113-110">Para abrir la tarea Script, haga clic en la pestaña **Flujo de control** y, a continuación, haga doble clic en la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="31113-110">To open the Script task, click the **Control Flow** tab, and then double-click the Script task.</span></span>  
  
4.  <span data-ttu-id="31113-111">Para abrir el componente de script, haga clic en la pestaña **Flujo de datos** y, a continuación, haga doble clic en el componente de script.</span><span class="sxs-lookup"><span data-stu-id="31113-111">To open the Script component, click the **Data Flow** tab, and then double-click the Script component.</span></span>  
  
5.  <span data-ttu-id="31113-112">Haga clic en **Script** y, a continuación, en **Editar script**.</span><span class="sxs-lookup"><span data-stu-id="31113-112">Click **Script** and then click **Edit Script**.</span></span>  
  
6.  <span data-ttu-id="31113-113">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), ubique la línea del script en la que desea establecer un punto de interrupción, haga clic con el botón derecho en la línea, apunte al **Punto de interrupción** y haga clic en **Insertar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="31113-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), locate the line of script on which you want to set a breakpoint, right-click that line, point to **Breakpoint**, and then click **Insert Breakpoint**.</span></span>  
  
     <span data-ttu-id="31113-114">El icono de punto de interrupción aparece en la línea de código.</span><span class="sxs-lookup"><span data-stu-id="31113-114">The breakpoint icon appears on the line of code.</span></span>  
  
7.  <span data-ttu-id="31113-115">En el menú **Archivo** , haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="31113-115">On the **File** menu, click **Exit**.</span></span>  
  
8.  <span data-ttu-id="31113-116">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="31113-116">Click **OK**.</span></span>  
  
9. <span data-ttu-id="31113-117">Para guardar el paquete, haga clic en **Guardar los elementos seleccionados** , en el menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="31113-117">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
  
