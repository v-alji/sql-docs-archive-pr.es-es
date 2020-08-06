---
title: Agregar expresiones a las restricciones de precedencia | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- precedence executables [Integration Services]
- precedence constraints [Integration Services], adding expressions
- adding expressions
- constrained executables [Integration Services]
- combining constraints
- expressions [Integration Services], constraints
ms.assetid: 5574d89a-a68e-4b84-80ea-da93305e5ca1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6dfc73a484020a51738b8ef93e20d96d16edbf1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672237"
---
# <a name="add-expressions-to-precedence-constraints"></a><span data-ttu-id="83a47-102">Agregar expresiones a las restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="83a47-102">Add Expressions to Precedence Constraints</span></span>
  <span data-ttu-id="83a47-103">Una restricción de precedencia puede utilizar una expresión para definir la restricción entre dos aplicaciones ejecutables: el ejecutable de precedencia y el ejecutable restringido.</span><span class="sxs-lookup"><span data-stu-id="83a47-103">A precedence constraint can use an expression to define the constraint between two executables: the precedence executable and the constrained executable.</span></span> <span data-ttu-id="83a47-104">Los ejecutables pueden ser tareas o contenedores.</span><span class="sxs-lookup"><span data-stu-id="83a47-104">The executables can be tasks or containers.</span></span> <span data-ttu-id="83a47-105">La expresión se puede usar por sí sola o combinada con el resultado de la ejecución del ejecutable de precedencia.</span><span class="sxs-lookup"><span data-stu-id="83a47-105">The expression can be used alone or in combination with the execution result of the precedence executable.</span></span> <span data-ttu-id="83a47-106">El resultado de la ejecución de un ejecutable es su ejecución correcta o un error.</span><span class="sxs-lookup"><span data-stu-id="83a47-106">The execution result of an executable is either success or failure.</span></span> <span data-ttu-id="83a47-107">Cuando configura el resultado de ejecución de una restricción de precedencia, puede establecer el resultado de ejecución en `Success`, `Failure` o `Completion`.</span><span class="sxs-lookup"><span data-stu-id="83a47-107">When you configure the execution result of a precedence constraint, you can set the execution result to `Success`, `Failure`, or `Completion`.</span></span> <span data-ttu-id="83a47-108">`Success` exige la ejecución correcta del ejecutable de precedencia, `Failure` requiere que el ejecutable de precedencia genere un error y `Completion` indica que el ejecutable restringido se debe ejecutar independientemente de si la tarea de precedencia se ejecuta correctamente o genera un error.</span><span class="sxs-lookup"><span data-stu-id="83a47-108">`Success` requires that the precedence executable succeed, `Failure` requires that the precedence executable fail, and `Completion` indicates that the constrained executable should run regardless of whether the precedence task succeeds or fails.</span></span> <span data-ttu-id="83a47-109">Para obtener más información, vea [Restricciones de precedencia](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="83a47-109">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="83a47-110">La expresión debe evaluarse como `True` o `False` y debe ser una expresión válida de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83a47-110">The expression must evaluate to `True` or `False` and it must be a valid [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression.</span></span> <span data-ttu-id="83a47-111">La expresión puede usar literales, variables del sistema y personalizadas, y las funciones y operadores que proporciona la gramática de expresiones de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83a47-111">The expression can use literals, system and custom variables, and the functions and operators that the [!INCLUDE[ssIS](../includes/ssis-md.md)] expression grammar provides.</span></span> <span data-ttu-id="83a47-112">Por ejemplo, la expresión `@Count == SQRT(144) + 10` usa la variable `Count`, la función SQRT y los operadores igual (==) y sumar (+).</span><span class="sxs-lookup"><span data-stu-id="83a47-112">For example, the expression `@Count == SQRT(144) + 10` uses the variable `Count`, the SQRT function , and the equal (==) and add (+) operators.</span></span> <span data-ttu-id="83a47-113">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="83a47-113">For more information, see [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="83a47-114">En la ilustración siguiente, la tarea A y la tarea B están vinculadas por una restricción de precedencia que usa un resultado de ejecución y una expresión.</span><span class="sxs-lookup"><span data-stu-id="83a47-114">In the following illustration, task A and task B are linked by a precedence constraint that uses an execution result and an expression.</span></span> <span data-ttu-id="83a47-115">El valor de restricción se establece en `Success` y la expresión es `@X >== @Z`.</span><span class="sxs-lookup"><span data-stu-id="83a47-115">The constraint value is set to `Success` and the expression is  `@X >== @Z`.</span></span> <span data-ttu-id="83a47-116">La tarea B, la tarea restringida, se ejecuta solamente si la tarea A se completa correctamente y el valor de la variable `X` es mayor o igual al valor de la variable `Z`.</span><span class="sxs-lookup"><span data-stu-id="83a47-116">Task B, the constrained task, runs only if task A completes successfully and the value of variable `X` is greater than or equal to the value of variable `Z`.</span></span>  
  
 <span data-ttu-id="83a47-117">![Restricciones de precedencia entre dos tareas](media/mw-dts-03.gif "Restricciones de precedencia entre dos tareas")</span><span class="sxs-lookup"><span data-stu-id="83a47-117">![Precedence constraint between two tasks](media/mw-dts-03.gif "Precedence constraint between two tasks")</span></span>  
  
 <span data-ttu-id="83a47-118">Los ejecutables también se pueden vincular mediante varias restricciones de precedencia que contienen diferentes expresiones.</span><span class="sxs-lookup"><span data-stu-id="83a47-118">Executables can also be linked by using multiple precedence constraints that contain different expressions.</span></span> <span data-ttu-id="83a47-119">Por ejemplo, en la siguiente ilustración, las tareas B y C están vinculadas a la tarea A por restricciones de precedencia que usan resultados de ejecución y expresiones.</span><span class="sxs-lookup"><span data-stu-id="83a47-119">For example, in the following illustration, tasks B and C are linked to task A by precedence constraints that use execution results and expressions.</span></span> <span data-ttu-id="83a47-120">Ambos valores de restricción se establecen en `Success.` Una restricción de precedencia incluye la expresión `@X >== @Z`, y la otra restricción de precedencia la expresión `@X < @Z`.</span><span class="sxs-lookup"><span data-stu-id="83a47-120">Both of the constraint values are set to `Success.` One precedence constraint includes the expression `@X >== @Z`, and the other precedence constraint includes the expression `@X < @Z`.</span></span> <span data-ttu-id="83a47-121">Según los valores de la variable `X` y la variable `Z`, se ejecuta la tarea C o la tarea B.</span><span class="sxs-lookup"><span data-stu-id="83a47-121">Depending on the values of variable `X` and variable `Z`, either task C or task B runs.</span></span>  
  
 <span data-ttu-id="83a47-122">![Expresiones en restricciones de precedencia](media/mw-dts-04.gif "Expresiones en restricciones de precedencia")</span><span class="sxs-lookup"><span data-stu-id="83a47-122">![Expressions on precedence constraints](media/mw-dts-04.gif "Expressions on precedence constraints")</span></span>  
  
 <span data-ttu-id="83a47-123">Puede agregar o modificar una expresión mediante el **Editor de restricciones de precedencia** en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , o en la ventana Propiedades que proporciona [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83a47-123">You can add or modify an expression by using the **Precedence Constraint Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and the Properties window that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides.</span></span> <span data-ttu-id="83a47-124">Sin embargo, la ventana Propiedades no proporciona ninguna comprobación de la sintaxis de la expresión.</span><span class="sxs-lookup"><span data-stu-id="83a47-124">However, the Properties window does not provide verification of the expression syntax.</span></span>  
  
 <span data-ttu-id="83a47-125">Si una restricción de precedencia incluye una expresión, aparece un icono en la superficie de diseño de la pestaña **Flujo de control** , junto a la restricción de precedencia, y la información sobre herramientas del icono muestra la expresión.</span><span class="sxs-lookup"><span data-stu-id="83a47-125">If a precedence constraint includes an expression, an icon appears on the design surface of the **Control Flow** tab, next to the precedence constraint, and the ToolTip on the icon displays the expression.</span></span>  
  
## <a name="combining-execution-values-and-expressions"></a><span data-ttu-id="83a47-126">Combinar valores de ejecución y expresiones</span><span class="sxs-lookup"><span data-stu-id="83a47-126">Combining Execution Values and Expressions</span></span>  
 <span data-ttu-id="83a47-127">La siguiente tabla describe los efectos de combinar una restricción de valor de ejecución y una expresión en una restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="83a47-127">The following table describes the effects of combining an execution value constraint and an expression in a precedence constraint.</span></span>  
  
|<span data-ttu-id="83a47-128">Operación de evaluación</span><span class="sxs-lookup"><span data-stu-id="83a47-128">Evaluation operation</span></span>|<span data-ttu-id="83a47-129">La restricción se evalúa como</span><span class="sxs-lookup"><span data-stu-id="83a47-129">Constraint evaluates to</span></span>|<span data-ttu-id="83a47-130">La expresión se evalúa como</span><span class="sxs-lookup"><span data-stu-id="83a47-130">Expression evaluates to</span></span>|<span data-ttu-id="83a47-131">El ejecutable restringido se ejecuta</span><span class="sxs-lookup"><span data-stu-id="83a47-131">Constrained executable runs</span></span>|  
|--------------------------|-----------------------------|-----------------------------|---------------------------------|  
|<span data-ttu-id="83a47-132">Restricción</span><span class="sxs-lookup"><span data-stu-id="83a47-132">Constraint</span></span>|<span data-ttu-id="83a47-133">True</span><span class="sxs-lookup"><span data-stu-id="83a47-133">True</span></span>|<span data-ttu-id="83a47-134">N/D</span><span class="sxs-lookup"><span data-stu-id="83a47-134">N/A</span></span>|<span data-ttu-id="83a47-135">True</span><span class="sxs-lookup"><span data-stu-id="83a47-135">True</span></span>|  
|<span data-ttu-id="83a47-136">Restricción</span><span class="sxs-lookup"><span data-stu-id="83a47-136">Constraint</span></span>|<span data-ttu-id="83a47-137">False</span><span class="sxs-lookup"><span data-stu-id="83a47-137">False</span></span>|<span data-ttu-id="83a47-138">N/D</span><span class="sxs-lookup"><span data-stu-id="83a47-138">N/A</span></span>|<span data-ttu-id="83a47-139">False</span><span class="sxs-lookup"><span data-stu-id="83a47-139">False</span></span>|  
|<span data-ttu-id="83a47-140">Expression</span><span class="sxs-lookup"><span data-stu-id="83a47-140">Expression</span></span>|<span data-ttu-id="83a47-141">N/D</span><span class="sxs-lookup"><span data-stu-id="83a47-141">N/A</span></span>|<span data-ttu-id="83a47-142">True</span><span class="sxs-lookup"><span data-stu-id="83a47-142">True</span></span>|<span data-ttu-id="83a47-143">True</span><span class="sxs-lookup"><span data-stu-id="83a47-143">True</span></span>|  
|<span data-ttu-id="83a47-144">Expression</span><span class="sxs-lookup"><span data-stu-id="83a47-144">Expression</span></span>|<span data-ttu-id="83a47-145">N/D</span><span class="sxs-lookup"><span data-stu-id="83a47-145">N/A</span></span>|<span data-ttu-id="83a47-146">False</span><span class="sxs-lookup"><span data-stu-id="83a47-146">False</span></span>|<span data-ttu-id="83a47-147">False</span><span class="sxs-lookup"><span data-stu-id="83a47-147">False</span></span>|  
|<span data-ttu-id="83a47-148">Restricción y expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-148">Constraint and Expression</span></span>|<span data-ttu-id="83a47-149">True</span><span class="sxs-lookup"><span data-stu-id="83a47-149">True</span></span>|<span data-ttu-id="83a47-150">True</span><span class="sxs-lookup"><span data-stu-id="83a47-150">True</span></span>|<span data-ttu-id="83a47-151">True</span><span class="sxs-lookup"><span data-stu-id="83a47-151">True</span></span>|  
|<span data-ttu-id="83a47-152">Restricción y expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-152">Constraint and Expression</span></span>|<span data-ttu-id="83a47-153">True</span><span class="sxs-lookup"><span data-stu-id="83a47-153">True</span></span>|<span data-ttu-id="83a47-154">False</span><span class="sxs-lookup"><span data-stu-id="83a47-154">False</span></span>|<span data-ttu-id="83a47-155">False</span><span class="sxs-lookup"><span data-stu-id="83a47-155">False</span></span>|  
|<span data-ttu-id="83a47-156">Restricción y expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-156">Constraint and Expression</span></span>|<span data-ttu-id="83a47-157">False</span><span class="sxs-lookup"><span data-stu-id="83a47-157">False</span></span>|<span data-ttu-id="83a47-158">True</span><span class="sxs-lookup"><span data-stu-id="83a47-158">True</span></span>|<span data-ttu-id="83a47-159">False</span><span class="sxs-lookup"><span data-stu-id="83a47-159">False</span></span>|  
|<span data-ttu-id="83a47-160">Restricción y expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-160">Constraint and Expression</span></span>|<span data-ttu-id="83a47-161">False</span><span class="sxs-lookup"><span data-stu-id="83a47-161">False</span></span>|<span data-ttu-id="83a47-162">False</span><span class="sxs-lookup"><span data-stu-id="83a47-162">False</span></span>|<span data-ttu-id="83a47-163">False</span><span class="sxs-lookup"><span data-stu-id="83a47-163">False</span></span>|  
|<span data-ttu-id="83a47-164">Restricción o expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-164">Constraint or Expression</span></span>|<span data-ttu-id="83a47-165">True</span><span class="sxs-lookup"><span data-stu-id="83a47-165">True</span></span>|<span data-ttu-id="83a47-166">True</span><span class="sxs-lookup"><span data-stu-id="83a47-166">True</span></span>|<span data-ttu-id="83a47-167">True</span><span class="sxs-lookup"><span data-stu-id="83a47-167">True</span></span>|  
|<span data-ttu-id="83a47-168">Restricción o expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-168">Constraint or Expression</span></span>|<span data-ttu-id="83a47-169">True</span><span class="sxs-lookup"><span data-stu-id="83a47-169">True</span></span>|<span data-ttu-id="83a47-170">False</span><span class="sxs-lookup"><span data-stu-id="83a47-170">False</span></span>|<span data-ttu-id="83a47-171">True</span><span class="sxs-lookup"><span data-stu-id="83a47-171">True</span></span>|  
|<span data-ttu-id="83a47-172">Restricción o expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-172">Constraint or Expression</span></span>|<span data-ttu-id="83a47-173">False</span><span class="sxs-lookup"><span data-stu-id="83a47-173">False</span></span>|<span data-ttu-id="83a47-174">True</span><span class="sxs-lookup"><span data-stu-id="83a47-174">True</span></span>|<span data-ttu-id="83a47-175">True</span><span class="sxs-lookup"><span data-stu-id="83a47-175">True</span></span>|  
|<span data-ttu-id="83a47-176">Restricción o expresión</span><span class="sxs-lookup"><span data-stu-id="83a47-176">Constraint or Expression</span></span>|<span data-ttu-id="83a47-177">False</span><span class="sxs-lookup"><span data-stu-id="83a47-177">False</span></span>|<span data-ttu-id="83a47-178">False</span><span class="sxs-lookup"><span data-stu-id="83a47-178">False</span></span>|<span data-ttu-id="83a47-179">False</span><span class="sxs-lookup"><span data-stu-id="83a47-179">False</span></span>|  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a><span data-ttu-id="83a47-180">Para agregar una expresión a una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="83a47-180">To add an expression to a precedence constraint</span></span>  
  
-   [<span data-ttu-id="83a47-181">Usar una expresión en una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="83a47-181">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
-   [<span data-ttu-id="83a47-182">Establecer las propiedades de una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="83a47-182">Set the Properties of a Precedence Constraint</span></span>](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
## <a name="external-resources"></a><span data-ttu-id="83a47-183">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="83a47-183">External Resources</span></span>  
 <span data-ttu-id="83a47-184">Artículo técnico, sobre [ejemplos de expresiones SSIS](https://go.microsoft.com/fwlink/?LinkId=220761), en social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="83a47-184">Technical article, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), on social.technet.microsoft.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a47-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83a47-185">See Also</span></span>  
 <span data-ttu-id="83a47-186">[Varias restricciones de precedencia](../../2014/integration-services/multiple-precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="83a47-186">[Multiple Precedence Constraints](../../2014/integration-services/multiple-precedence-constraints.md) </span></span>  
 [<span data-ttu-id="83a47-187">Restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="83a47-187">Precedence Constraints</span></span>](control-flow/precedence-constraints.md)  
  
  