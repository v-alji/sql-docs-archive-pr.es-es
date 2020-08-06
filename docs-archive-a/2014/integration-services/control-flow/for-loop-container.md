---
title: Contenedor de bucles Para | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainerdetails.f1
helpviewer_keywords:
- repeating control flow
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: 44cf7355-992b-4bbf-a28c-bfb012de06f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a6c864779237fdbf4dd249f87b7c06655293c047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662211"
---
# <a name="for-loop-container"></a><span data-ttu-id="e8eb8-102">Contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="e8eb8-102">For Loop Container</span></span>
  <span data-ttu-id="e8eb8-103">El contenedor de bucles For define un flujo de control que se repite en un paquete.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-103">The For Loop container defines a repeating control flow in a package.</span></span> <span data-ttu-id="e8eb8-104">La implementación del bucle es similar a la estructura de bucle **For** de los lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-104">The loop implementation is similar to the **For** looping structure in programming languages.</span></span> <span data-ttu-id="e8eb8-105">En cada repetición del bucle, el contenedor de bucles For evalúa una expresión y repite el flujo de trabajo hasta que la expresión se evalúe como `False`.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-105">In each repeat of the loop, the For Loop container evaluates an expression and repeats its workflow until the expression evaluates to `False`.</span></span>  
  
 <span data-ttu-id="e8eb8-106">El contenedor de bucles For usa los elementos siguientes para definir el bucle:</span><span class="sxs-lookup"><span data-stu-id="e8eb8-106">The For Loop container usesthe following elements to define the loop:</span></span>  
  
-   <span data-ttu-id="e8eb8-107">Una expresión de inicialización opcional que asigna valores a los contadores de bucle.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-107">An optional initialization expression that assigns values to the loop counters.</span></span>  
  
-   <span data-ttu-id="e8eb8-108">Una expresión de evaluación que contiene la expresión usada para comprobar si el bucle debe detenerse o continuar.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-108">An evaluation expression that contains the expression used to test whether the loop should stop or continue.</span></span>  
  
-   <span data-ttu-id="e8eb8-109">Una expresión de iteración opcional que incrementa o disminuye el contador del bucle.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-109">An optional iteration expression that increments or decrements the loop counter.</span></span>  
  
 <span data-ttu-id="e8eb8-110">El siguiente diagrama muestra un contenedor de bucles For con una tarea Enviar correo.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-110">The following diagram shows a For Loop container with a Send Mail task.</span></span> <span data-ttu-id="e8eb8-111">Si la expresión de inicialización es `@Counter = 0`, la expresión de evaluación es `@Counter < 4`y la expresión de iteración es `@Counter = @Counter + 1`, el bucle se repetirá cuatro veces y enviará cuatro mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-111">If the initialization expression is `@Counter = 0`, the evaluation expression is `@Counter < 4`, and the iteration expression is `@Counter = @Counter + 1`, the loop repeats four times and sends four e-mail messages.</span></span>  
  
 <span data-ttu-id="e8eb8-112">![Un contenedor de bucles For repite una tarea cuatro veces.](../media/ssis-forloop.gif "Un contenedor de bucles For repite una tarea cuatro veces.")</span><span class="sxs-lookup"><span data-stu-id="e8eb8-112">![A For Loop container repeats a task four times](../media/ssis-forloop.gif "A For Loop container repeats a task four times")</span></span>  
  
 <span data-ttu-id="e8eb8-113">Las expresiones deben ser expresiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] válidas.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-113">The expressions must be valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions.</span></span>  
  
 <span data-ttu-id="e8eb8-114">Para crear las expresiones de inicialización y asignación, puede utilizar el operador de asignación (=).</span><span class="sxs-lookup"><span data-stu-id="e8eb8-114">To create the initialization and assignment expressions, you can use the assignment operator (=).</span></span> <span data-ttu-id="e8eb8-115">La gramática de expresiones de Integration Services no admite este operador; solo se puede utilizar en las expresiones de inicialización y asignación del contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-115">This operator is not otherwise supported by the Integration Services expression grammar and can only be used by the initialization and assignment expression types in the For Loop container.</span></span> <span data-ttu-id="e8eb8-116">Cualquier expresión que use el operador de asignación necesita tener la sintaxis `@Var = <expression>`, donde **Var** es una variable de tiempo de ejecución y \<expression> es una expresión que sigue las reglas de sintaxis de expresiones de [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8eb8-116">Any expression that uses the assignment operator must have the syntax `@Var = <expression>`, where **Var** is a run-time variable and \<expression> is an expression that follows the rules of the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="e8eb8-117">La expresión puede incluir variables, literales y cualquier operador o función compatible con la gramática de expresiones de SSIS.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-117">The expression can include the variables, literals, and any operators and functions that the SSIS expression grammar supports.</span></span> <span data-ttu-id="e8eb8-118">La evaluación de la expresión debe devolver un tipo de datos que se pueda convertir al tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-118">The expression must evaluate to a data type that can be cast to the data type of the variable.</span></span>  
  
 <span data-ttu-id="e8eb8-119">Un contenedor de bucles For solo puede tener una expresión de evaluación.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-119">A For Loop container can have only one evaluation expression.</span></span> <span data-ttu-id="e8eb8-120">Esto significa que el contenedor de bucles For ejecutará todos los elementos de flujo de control el mismo número de veces.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-120">This means that the For Loop container runs all its control flow elements the same number of times.</span></span> <span data-ttu-id="e8eb8-121">Como el contenedor de bucles For puede incluir otros contenedores de bucles For, es posible generar bucles anidados e implementar bucles complejos en paquetes.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-121">Because the For Loop container can include other For Loop containers, you can build nested loops and implement complex looping in packages.</span></span>  
  
 <span data-ttu-id="e8eb8-122">Puede establecer una propiedad de transacción en el contenedor de bucles For para definir una transacción para un subconjunto del flujo de control del paquete.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-122">You can set a transaction property on the For Loop container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="e8eb8-123">De esta manera, puede administrar las transacciones en mayor detalle.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-123">In this way, you can manage transactions at a more granular level.</span></span> <span data-ttu-id="e8eb8-124">Por ejemplo, si un contenedor de bucles For repite un flujo de control que actualiza los datos de una tabla varias veces, puede configurar el bucle For y su flujo de control para que utilicen una transacción, a fin de asegurarse de que si no se actualizan todos los datos correctamente, no se actualice ningún dato.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-124">For example, if a For Loop container repeats a control flow that updates data in a table multiple times, you can configure the For Loop and its control flow to use a transaction to ensure that if not all data is updated successfully, no data is updated.</span></span> <span data-ttu-id="e8eb8-125">Para más información, vea [Transacciones de Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="e8eb8-125">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-for-loop-container"></a><span data-ttu-id="e8eb8-126">Configuración del contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="e8eb8-126">Configuration of the For Loop Container</span></span>  
 <span data-ttu-id="e8eb8-127">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-127">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e8eb8-128">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8eb8-128">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e8eb8-129">Editor de bucles For</span><span class="sxs-lookup"><span data-stu-id="e8eb8-129">For Loop Editor</span></span>](../for-loop-editor.md)  
  
-   [<span data-ttu-id="e8eb8-130">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="e8eb8-130">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="e8eb8-131">Para obtener más información sobre cómo establecer estas propiedades mediante programación, vea la documentación de la clase **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** en la Guía del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-131">For more information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e8eb8-132">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e8eb8-132">Related Tasks</span></span>  
 <span data-ttu-id="e8eb8-133">Para obtener información acerca de cómo configurar el contenedor de bucles For, vea los temas siguientes.</span><span class="sxs-lookup"><span data-stu-id="e8eb8-133">For information about how to configure a For Loop Container, see the following topics.</span></span>  
  
-   [<span data-ttu-id="e8eb8-134">Configurar un contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="e8eb8-134">Configure a For Loop Container</span></span>](for-loop-container.md)  
  
-   [<span data-ttu-id="e8eb8-135">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="e8eb8-135">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="e8eb8-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8eb8-136">See Also</span></span>  
 <span data-ttu-id="e8eb8-137">[Flujo de control](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="e8eb8-137">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="e8eb8-138">Expresiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e8eb8-138">Integration Services &#40;SSIS&#41; Expressions</span></span>](../expressions/integration-services-ssis-expressions.md)  
  
  
