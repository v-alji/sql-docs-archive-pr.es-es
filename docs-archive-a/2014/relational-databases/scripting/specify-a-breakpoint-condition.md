---
title: Especificar una condición de punto de interrupción
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint conditions
ms.assetid: b43d8a2b-99a3-4fb7-8848-99c042ea7ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 659b6ca1149eb8f0412efbe2adbaf4c1ffce59d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746878"
---
# <a name="specify-a-breakpoint-condition"></a><span data-ttu-id="5e5ec-102">Especificar una condición de punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="5e5ec-102">Specify a Breakpoint Condition</span></span>
  <span data-ttu-id="5e5ec-103">Una condición de punto de interrupción es una expresión de [!INCLUDE[tsql](../../includes/tsql-md.md)] evaluada por el depurador cuando se alcanza el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-103">A breakpoint condition is a [!INCLUDE[tsql](../../includes/tsql-md.md)] expression that is evaluated by the debugger when the breakpoint is reached.</span></span> <span data-ttu-id="5e5ec-104">Si se satisface la condición y se alcanza el número de llamadas especificado, el depurador interrumpe, o bien, realiza la acción definida para el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-104">If the condition is satisfied and any specified hit count reached, the debugger either breaks or performs the action specified for the breakpoint.</span></span>  
  
## <a name="specifying-conditions"></a><span data-ttu-id="5e5ec-105">Especificar condiciones</span><span class="sxs-lookup"><span data-stu-id="5e5ec-105">Specifying Conditions</span></span>  
 <span data-ttu-id="5e5ec-106">La expresión especificada debe ser una expresión válida de Transact-SQL que se evalúe como un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-106">The expression specified must be a valid Transact-SQL expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="5e5ec-107">Para obtener más información, vea [Expresiones &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e5ec-107">For more information, see [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span></span>  
  
 <span data-ttu-id="5e5ec-108">Si especifica una condición de punto de interrupción con sintaxis no válida, aparecerá inmediatamente un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-108">If you specify a breakpoint condition with invalid syntax, a warning message appears immediately.</span></span> <span data-ttu-id="5e5ec-109">Si especifica una condición con sintaxis válida, pero la semántica no es válida, aparecerá un mensaje de advertencia la primera vez que se llegue al punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-109">If you specify a condition with valid syntax but invalid semantics, a warning message is displayed the first time the breakpoint is hit.</span></span> <span data-ttu-id="5e5ec-110">En cualquier caso, el depurador interrumpe la ejecución cuando se alcanza el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-110">In either case, the debugger breaks execution when the invalid breakpoint is hit.</span></span>  
  
#### <a name="to-specify-a-condition"></a><span data-ttu-id="5e5ec-111">Para especificar una condición</span><span class="sxs-lookup"><span data-stu-id="5e5ec-111">To Specify a Condition</span></span>  
  
1.  <span data-ttu-id="5e5ec-112">En la ventana del editor, haga clic con el botón derecho en el glifo del punto de interrupción y, después, haga clic en la opción **Condición** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-112">In the editor window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="5e5ec-113">O bien</span><span class="sxs-lookup"><span data-stu-id="5e5ec-113">-or-</span></span>  
  
     <span data-ttu-id="5e5ec-114">En la ventana **Puntos de interrupción** , haga clic con el botón derecho en el glifo del punto de interrupción y, después, haga clic en la opción **Condición** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-114">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="5e5ec-115">En el cuadro de diálogo **Condición de punto de interrupción** , escriba una expresión booleana válida en el cuadro **Condición** .</span><span class="sxs-lookup"><span data-stu-id="5e5ec-115">In the **Breakpoint Condition** dialog box, enter a valid Boolean expression in the **Condition** box.</span></span>  
  
3.  <span data-ttu-id="5e5ec-116">Elija **es true** si desea interrumpir cuando la expresión se evalúa como `true` o elija **ha cambiado** si desea interrumpir cuando el valor de la expresión ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-116">Choose **Is true** if you want to break when the expression evaluates to `true`, or choose **Has changed** if you want to break when the value of the expression has changed.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5e5ec-117">El depurador no evalúa la expresión booleana hasta la primera vez que se alcanza el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-117">The debugger does not evaluate the Boolean expression until the first time the breakpoint is reached.</span></span> <span data-ttu-id="5e5ec-118">Si elige **Ha cambiado**, el depurador no considerará la primera evaluación como cambio, por lo que el depurador no interrumpirá le ejecución en la primera evaluación.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-118">If you choose **Has changed**, the debugger does not consider the first evaluation to be a change, so the debugger will not break on the first evaluation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5ec-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e5ec-119">See Also</span></span>  
 <span data-ttu-id="5e5ec-120">[Especificar un número de llamadas](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="5e5ec-120">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="5e5ec-121">Especificar una acción del punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="5e5ec-121">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
