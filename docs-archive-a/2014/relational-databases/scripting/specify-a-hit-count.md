---
title: Especificar un número de llamadas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpt.hitcount
helpviewer_keywords:
- Transact-SQL debugger, breakpoint hit count
ms.assetid: 24836939-94ed-4e57-aa85-5d6938d859e4
author: rothja
ms.author: jroth
ms.openlocfilehash: 34c75e990bce1ea5e64c0b45f7acbcaa52fc3c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675262"
---
# <a name="specify-a-hit-count"></a><span data-ttu-id="64a4c-102">Especificar un número de llamadas</span><span class="sxs-lookup"><span data-stu-id="64a4c-102">Specify a Hit Count</span></span>
  <span data-ttu-id="64a4c-103">Un número de llamadas al punto de interrupción es un contador que el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] incrementa cada vez que se alcanza el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="64a4c-103">A breakpoint hit count is a counter that is incremented by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger each time the breakpoint is reached.</span></span> <span data-ttu-id="64a4c-104">Si se alcanza el número de llamadas especificado y se satisface la condición de punto de interrupción especificada, el depurador realiza la acción definida para el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="64a4c-104">If the specified hit count is reached and any specified breakpoint condition is satisfied, the debugger performs the action specified for the breakpoint.</span></span>  
  
## <a name="hit-count-considerations"></a><span data-ttu-id="64a4c-105">Consideraciones sobre el número de llamadas</span><span class="sxs-lookup"><span data-stu-id="64a4c-105">Hit Count Considerations</span></span>  
 <span data-ttu-id="64a4c-106">De forma predeterminada, la ejecución se interrumpe cada vez se ejecuta un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="64a4c-106">By default, execution breaks every time a breakpoint is hit.</span></span> <span data-ttu-id="64a4c-107">Puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="64a4c-107">You can choose between the following options:</span></span>  
  
-   <span data-ttu-id="64a4c-108">Interrumpir siempre ( valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="64a4c-108">Break always (the default).</span></span>  
  
-   <span data-ttu-id="64a4c-109">Interrumpir cuando el número de llamadas alcanza un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="64a4c-109">Break when the hit count equals a specified value.</span></span>  
  
-   <span data-ttu-id="64a4c-110">Interrumpir cuando el número de llamadas alcanza un múltiplo de un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="64a4c-110">Break when the hit count equals a multiple of a specified value.</span></span>  
  
-   <span data-ttu-id="64a4c-111">Interrumpir cuando el número de llamadas es mayor o igual que un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="64a4c-111">Break when the hit count is greater than or equal to a specified value.</span></span>  
  
 <span data-ttu-id="64a4c-112">Los números de llamadas al punto de interrupción se incrementan dentro del ámbito de una sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="64a4c-112">Breakpoint hit counts are incremented within the scope of a debugging session.</span></span> <span data-ttu-id="64a4c-113">Todos los números de llamadas se establecen en cero al comienzo de cada sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="64a4c-113">All hit counts are set to zero at the start of each debugging session.</span></span>  
  
 <span data-ttu-id="64a4c-114">Si desea realizar un seguimiento del número de veces que se ejecuta un punto de interrupción sin disponer de la ejecución de detención de punto de interrupción, especifique un número de llamadas con un valor muy alto para que nunca se produzca la detención de punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="64a4c-114">If you want to track how many times a breakpoint is hit without having the breakpoint break execution, specify a hit count with a very high value so the breakpoint never breaks.</span></span>  
  
 <span data-ttu-id="64a4c-115">La acción predeterminada para un punto de interrupción es que se detenga la ejecución cuando se hayan satisfecho el número de llamadas y la condición de punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="64a4c-115">The default action for a breakpoint is to break execution when both the hit count and breakpoint condition have been satisfied.</span></span> <span data-ttu-id="64a4c-116">Para obtener información sobre cómo especificar otras acciones, vea [Especificar una acción del punto de interrupción](specify-a-breakpoint-action.md).</span><span class="sxs-lookup"><span data-stu-id="64a4c-116">For information about specifying other actions, see [Specify a Breakpoint Action](specify-a-breakpoint-action.md).</span></span>  
  
#### <a name="to-specify-a-hit-count"></a><span data-ttu-id="64a4c-117">Para especificar un número de llamadas</span><span class="sxs-lookup"><span data-stu-id="64a4c-117">To Specify a Hit Count</span></span>  
  
1.  <span data-ttu-id="64a4c-118">En la ventana del editor, haga clic con el botón derecho en el glifo de punto de interrupción y, luego, haga clic en **Número de llamadas** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="64a4c-118">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="64a4c-119">O bien</span><span class="sxs-lookup"><span data-stu-id="64a4c-119">-or-</span></span>  
  
     <span data-ttu-id="64a4c-120">En la ventana **Puntos de interrupción** , haga clic con el botón derecho en el glifo de punto de interrupción y, luego, haga clic en **Número de llamadas** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="64a4c-120">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="64a4c-121">En el cuadro de diálogo **Número de llamadas al punto de interrupción** , seleccione el comportamiento que desea en el cuadro **Cuando el punto de interrupción se visita** .</span><span class="sxs-lookup"><span data-stu-id="64a4c-121">In the **Breakpoint Hit Count** dialog box, select the behavior you want from the **When the breakpoint is hit** box.</span></span>  
  
     <span data-ttu-id="64a4c-122">Si elige un valor distinto de **Interrumpir siempre**, aparecerá un cuadro de texto a la derecha de la lista.</span><span class="sxs-lookup"><span data-stu-id="64a4c-122">If you choose any setting other than **Break Always**, a text box appears to the right of the list.</span></span> <span data-ttu-id="64a4c-123">Escriba un número entero en el cuadro de texto para especificar el número de llamadas que desea.</span><span class="sxs-lookup"><span data-stu-id="64a4c-123">Enter an integer in the text box to specify the hit count you want.</span></span>  
  
3.  <span data-ttu-id="64a4c-124">Haga clic en **Aceptar** para implementar los cambios o en **Cancelar** para salir sin aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="64a4c-124">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
#### <a name="to-view-or-reset-the-current-hit-count"></a><span data-ttu-id="64a4c-125">Para ver o restablecer el número de llamadas actual</span><span class="sxs-lookup"><span data-stu-id="64a4c-125">To View or Reset the Current Hit Count</span></span>  
  
1.  <span data-ttu-id="64a4c-126">En la ventana del editor, haga clic con el botón derecho en el glifo de punto de interrupción y, luego, haga clic en **Número de llamadas** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="64a4c-126">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="64a4c-127">O bien</span><span class="sxs-lookup"><span data-stu-id="64a4c-127">-or-</span></span>  
  
     <span data-ttu-id="64a4c-128">En la ventana **Puntos de interrupción** , haga clic con el botón derecho en el glifo de punto de interrupción y, luego, haga clic en **Número de llamadas** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="64a4c-128">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="64a4c-129">En el cuadro de diálogo **Número de llamadas al punto de interrupción** , se muestra el **Número actual** justo encima del botón **Restablecer** .</span><span class="sxs-lookup"><span data-stu-id="64a4c-129">In the **Breakpoint Hit Count** dialog box, the **Current hit count:** is displayed just above the **Reset** button.</span></span>  
  
3.  <span data-ttu-id="64a4c-130">Haga clic en **Restablecer** si desea establecer en cero el número de llamadas actual.</span><span class="sxs-lookup"><span data-stu-id="64a4c-130">Click **Reset** if you want to set the current hit count to zero.</span></span>  
  
4.  <span data-ttu-id="64a4c-131">Haga clic en **Aceptar** o en **Cancelar** para salir del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="64a4c-131">Click **OK** or **Cancel** to exit the dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a4c-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64a4c-132">See Also</span></span>  
 [<span data-ttu-id="64a4c-133">Especificar una condición de punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="64a4c-133">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)  
  
  
