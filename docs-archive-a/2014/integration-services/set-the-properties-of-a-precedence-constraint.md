---
title: Establecer las propiedades de una restricción de precedencia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Precedence Constraint Editor dialog box
- precedence constraints [Integration Services], properties
ms.assetid: d990f600-5c09-4cd5-8528-0a58d79dc9f2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55b95bdb79d801156bef6198bc0f57accb5d9517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676567"
---
# <a name="set-the-properties-of-a-precedence-constraint"></a><span data-ttu-id="a3b57-102">Establecer las propiedades de una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="a3b57-102">Set the Properties of a Precedence Constraint</span></span>
  <span data-ttu-id="a3b57-103">Para establecer las propiedades en restricciones de precedencia, puede utilizar una de estas herramientas:</span><span class="sxs-lookup"><span data-stu-id="a3b57-103">To set properties on precedence constraints, you can use one of these tools:</span></span>  
  
-   <span data-ttu-id="a3b57-104">Puede utilizar el cuadro de diálogo **Editor de restricciones de precedencia** .</span><span class="sxs-lookup"><span data-stu-id="a3b57-104">You can use the **Precedence Constraint Editor** dialog box.</span></span>  
  
-   <span data-ttu-id="a3b57-105">Puede utilizar la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="a3b57-105">You can use the Properties window.</span></span> <span data-ttu-id="a3b57-106">En la ventana Propiedades se enumeran las propiedades para configurar restricciones de precedencia que no están disponibles en el cuadro de diálogo **Editor de restricciones de precedencia** .</span><span class="sxs-lookup"><span data-stu-id="a3b57-106">The Properties window lists properties for configuring precedence constraints that are not available in the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="a3b57-107">En dicha ventana se puede proporcionar una descripción y un nombre de la restricción de precedencia y configurar la anotación que se debe mostrar para ella en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="a3b57-107">In the Properties window, you can provide a description and name of the precedence constraint, and configure the annotation to display for the precedence constraint on the design surface.</span></span>  
  
 <span data-ttu-id="a3b57-108">Los procedimientos siguientes describen cómo establecer propiedades en restricciones de precedencia utilizando cada una de estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="a3b57-108">The following procedures describe how to set properties on precedence constraints by using each of these tools.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-precedence-constraint-editor"></a><span data-ttu-id="a3b57-109">Para establecer las propiedades de una restricción de precedencia mediante el Editor de restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="a3b57-109">To set the properties of a precedence constraint by using the Precedence Constraint Editor</span></span>  
  
1.  <span data-ttu-id="a3b57-110">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="a3b57-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a3b57-111">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="a3b57-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a3b57-112">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="a3b57-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="a3b57-113">Haga doble clic en la restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="a3b57-113">Double-click the precedence constraint.</span></span>  
  
     <span data-ttu-id="a3b57-114">Se abre el **Editor de restricciones de precedencia** .</span><span class="sxs-lookup"><span data-stu-id="a3b57-114">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="a3b57-115">En la lista desplegable **Operación de evaluación** , seleccione una operación de evaluación.</span><span class="sxs-lookup"><span data-stu-id="a3b57-115">In the **Evaluation operation** drop-down list, select an evaluation operation.</span></span>  
  
6.  <span data-ttu-id="a3b57-116">En la `Value` lista desplegable, seleccione el resultado de la ejecución del ejecutable de precedencia.</span><span class="sxs-lookup"><span data-stu-id="a3b57-116">In the `Value` drop-down list, select the execution result of the precedence executable.</span></span>  
  
7.  <span data-ttu-id="a3b57-117">Si la operación de evaluación usa una expresión, `Expression` Escriba una expresión en el cuadro y haga clic en **probar** para evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="a3b57-117">If the evaluation operation uses an expression, in the `Expression` box, type an expression, and click **Test** to evaluate the expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a3b57-118">Los nombres de variables distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a3b57-118">Variable names are case-sensitive.</span></span>  
  
8.  <span data-ttu-id="a3b57-119">Si hay varias tareas o contenedores conectados al ejecutable restringido, seleccione **y lógico** para especificar que los resultados de la ejecución de todos los ejecutables anteriores deben evaluarse como `true` .</span><span class="sxs-lookup"><span data-stu-id="a3b57-119">If multiple tasks or containers are connected to the constrained executable, select **Logical AND** to specify that the execution results of all preceding executables must evaluate to `true`.</span></span> <span data-ttu-id="a3b57-120">Seleccione **or lógico** para especificar que solo un resultado de la ejecución debe evaluarse como `true` .</span><span class="sxs-lookup"><span data-stu-id="a3b57-120">Select **Logical OR** to specify that only one execution result must evaluate to `true`.</span></span>  
  
9. <span data-ttu-id="a3b57-121">Haga clic en **Aceptar** para cerrar el **Editor de restricciones de precedencia**.</span><span class="sxs-lookup"><span data-stu-id="a3b57-121">Click **OK** to close the **Precedence Constraint Editor**.</span></span>  
  
10. <span data-ttu-id="a3b57-122">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="a3b57-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-properties-window"></a><span data-ttu-id="a3b57-123">Para establecer las propiedades de una restricción de precedencia mediante la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="a3b57-123">To set the properties of a precedence constraint by using the Properties window</span></span>  
  
1.  <span data-ttu-id="a3b57-124">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="a3b57-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to modify.</span></span>  
  
2.  <span data-ttu-id="a3b57-125">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="a3b57-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a3b57-126">Haga clic en la pestaña **flujo de control** . En la superficie de diseño de la pestaña **flujo de control** , haga clic con el botón secundario en la restricción de precedencia y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a3b57-126">Click the **Control Flow** tab. On the design surface of the **Control Flow** tab, right-click the precedence constraint, and then click **Properties**.</span></span> <span data-ttu-id="a3b57-127">En la ventana Propiedades, modifique los valores de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="a3b57-127">In the Properties window, modify the property values.</span></span>  
  
4.  <span data-ttu-id="a3b57-128">En la ventana **Propiedades** , establezca las siguientes propiedades de lectura y escritura para las restricciones de precedencia:</span><span class="sxs-lookup"><span data-stu-id="a3b57-128">In the **Properties** window, set the following read/write properties of precedence constraints:</span></span>  
  
    |<span data-ttu-id="a3b57-129">Propiedad de lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="a3b57-129">Read/write property</span></span>|<span data-ttu-id="a3b57-130">Acción de configuración</span><span class="sxs-lookup"><span data-stu-id="a3b57-130">Configuration action</span></span>|  
    |--------------------------|--------------------------|  
    |<span data-ttu-id="a3b57-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3b57-131">Description</span></span>|<span data-ttu-id="a3b57-132">Escribir una descripción.</span><span class="sxs-lookup"><span data-stu-id="a3b57-132">Provide a description.</span></span>|  
    |<span data-ttu-id="a3b57-133">EvalOp</span><span class="sxs-lookup"><span data-stu-id="a3b57-133">EvalOp</span></span>|<span data-ttu-id="a3b57-134">Seleccionar una operación de evaluación.</span><span class="sxs-lookup"><span data-stu-id="a3b57-134">Select an evaluation operation.</span></span> <span data-ttu-id="a3b57-135">Si `Expression` se selecciona la operación, **ExpressionAndConstant**o **ExpressionOrConstant** , puede especificar una expresión.</span><span class="sxs-lookup"><span data-stu-id="a3b57-135">If the `Expression`, **ExpressionAndConstant**, or **ExpressionOrConstant** operation is selected, you can specify an expression.</span></span>|  
    |<span data-ttu-id="a3b57-136">Expression</span><span class="sxs-lookup"><span data-stu-id="a3b57-136">Expression</span></span>|<span data-ttu-id="a3b57-137">Si la operación de evaluación contiene una expresión, se debe proporcionar una expresión.</span><span class="sxs-lookup"><span data-stu-id="a3b57-137">If the evaluation operation includes and expression, provide an expression.</span></span> <span data-ttu-id="a3b57-138">La expresión debe evaluarse como un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="a3b57-138">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="a3b57-139">Para más información sobre el lenguaje de expresiones, vea [Expresiones de Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a3b57-139">For more information about the expression language, see [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>|  
    |<span data-ttu-id="a3b57-140">AND lógico</span><span class="sxs-lookup"><span data-stu-id="a3b57-140">LogicalAnd</span></span>|<span data-ttu-id="a3b57-141">Se establece `LogicalAnd` para especificar si la restricción de precedencia se evalúa en conjunto con otras restricciones de precedencia, cuando preceden varios ejecutables y están vinculados al ejecutable restringido.</span><span class="sxs-lookup"><span data-stu-id="a3b57-141">Set `LogicalAnd` to specify whether the precedence constraint is evaluated in concert with other precedence constraints, when multiple executables precede and are linked to the constrained executable</span></span>|  
    |<span data-ttu-id="a3b57-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="a3b57-142">Name</span></span>|<span data-ttu-id="a3b57-143">Actualizar el nombre de la restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="a3b57-143">Update the name of the precedence constraint.</span></span>|  
    |<span data-ttu-id="a3b57-144">ShowAnnotation</span><span class="sxs-lookup"><span data-stu-id="a3b57-144">ShowAnnotation</span></span>|<span data-ttu-id="a3b57-145">Especificar el tipo de anotación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a3b57-145">Specify the type of annotation to use.</span></span> <span data-ttu-id="a3b57-146">Elija **Never** para deshabilitar anotaciones, **AsNeeded** para habilitar anotaciones a petición, **ConstraintName** para realizar anotaciones automáticamente usando el valor de la propiedad Name, **ConstraintDescription** para realizar anotaciones automáticamente usando el valor de la propiedad Description y **ConstraintOptions** para realizar anotaciones automáticamente al usar el valor de las propiedades Value y Expression.</span><span class="sxs-lookup"><span data-stu-id="a3b57-146">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **ConstraintName** to automatically annotate using the value of the Name property, **ConstraintDescription** to automatically annotate using the value of the Description property, and **ConstraintOptions** to automatically annotate using the values of the Value and Expression properties.</span></span>|  
    |<span data-ttu-id="a3b57-147">Value</span><span class="sxs-lookup"><span data-stu-id="a3b57-147">Value</span></span>|<span data-ttu-id="a3b57-148">Si la operación de evaluación especificada en la propiedad EvalOP contiene una restricción, seleccione el resultado de la ejecución del ejecutable de restricción.</span><span class="sxs-lookup"><span data-stu-id="a3b57-148">If the evaluation operation specified in the EvalOP property includes a constraint, select the execution result of the constraining executable.</span></span>|  
  
5.  <span data-ttu-id="a3b57-149">Cierre la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="a3b57-149">Close the Properties window.</span></span>  
  
6.  <span data-ttu-id="a3b57-150">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="a3b57-150">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b57-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3b57-151">See Also</span></span>  
 <span data-ttu-id="a3b57-152">[Restricciones de precedencia](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="a3b57-152">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="a3b57-153">[Conectar tareas y contenedores mediante una restricción de precedencia predeterminada](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="a3b57-153">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="a3b57-154">[Establecer el valor de una restricción de precedencia mediante el menú contextual](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="a3b57-154">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 [<span data-ttu-id="a3b57-155">Usar una expresión en una restricción de precedencia</span><span class="sxs-lookup"><span data-stu-id="a3b57-155">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
