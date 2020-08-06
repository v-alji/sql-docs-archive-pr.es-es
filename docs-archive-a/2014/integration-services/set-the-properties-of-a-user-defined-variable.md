---
title: Establecer las propiedades de una variable definida por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- modifying variables
- variables [Integration Services], properties
ms.assetid: f98ddbec-f668-4dba-a768-44ac3ae0536f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf53be469e3d377f7efb379f78e85e31b26767b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751274"
---
# <a name="set-the-properties-of-a-user-defined-variable"></a><span data-ttu-id="83a7c-102">Establecer las propiedades de una variable definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="83a7c-102">Set the Properties of a User-Defined Variable</span></span>
  <span data-ttu-id="83a7c-103">Para establecer las propiedades de una variable definida por el usuario en [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], puede utilizar una de las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="83a7c-103">To set the properties of a user-defined variable in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you can use one of the following features:</span></span>  
  
-   <span data-ttu-id="83a7c-104">Ventana Variables.</span><span class="sxs-lookup"><span data-stu-id="83a7c-104">Variables window.</span></span>  
  
-   <span data-ttu-id="83a7c-105">Ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="83a7c-105">Properties window.</span></span> <span data-ttu-id="83a7c-106">En la ventana **Propiedades** se muestra una lista de propiedades para configurar variables que no están disponibles en la ventana **Variables** : Description, EvaluateAsExpression, Expression, ReadOnly, ValueType yIncludeInDebugDump.</span><span class="sxs-lookup"><span data-stu-id="83a7c-106">The **Properties** window lists properties for configuring variables that are not available in the **Variables** window: Description, EvaluateAsExpression, Expression, ReadOnly, ValueType, and IncludeInDebugDump.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="83a7c-107">también proporciona un conjunto de variables del sistema cuyas propiedades no se pueden actualizar, excepto la propiedad de RaiseChangedEvent.</span><span class="sxs-lookup"><span data-stu-id="83a7c-107">also provides a set of system variables whose properties cannot be updated, with the exception of the RaiseChangedEvent property.</span></span>  
  
 <span data-ttu-id="83a7c-108">**Expresiones de valor en variables**</span><span class="sxs-lookup"><span data-stu-id="83a7c-108">**Setting Expressions on Variables**</span></span>  
  
 <span data-ttu-id="83a7c-109">Cuando se usa la ventana **Propiedades** para establecer expresiones en una variable definida por el usuario:</span><span class="sxs-lookup"><span data-stu-id="83a7c-109">When you use the **Properties** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="83a7c-110">El valor de una variable se puede establecer por las propiedades Value o Expression.</span><span class="sxs-lookup"><span data-stu-id="83a7c-110">The value of a variable can be set by the Value or the Expression property.</span></span> <span data-ttu-id="83a7c-111">De forma predeterminada, la propiedad EvaluateAsExpression se establece en `False` y el valor de la variable se establece mediante la propiedad Value.</span><span class="sxs-lookup"><span data-stu-id="83a7c-111">By default, the EvaluateAsExpression property is set to `False` and the value of the variable is set by the Value property.</span></span> <span data-ttu-id="83a7c-112">Para usar una expresión para establecer el valor, primero debe establecer EvaluateAsExpression en `True` y, a continuación, proporcionar una expresión en la propiedad Expression.</span><span class="sxs-lookup"><span data-stu-id="83a7c-112">To use an expression to set the value, you must first set EvaluateAsExpression to `True`, and then provide an expression in the Expression property.</span></span> <span data-ttu-id="83a7c-113">La propiedad Value se establece automáticamente en el resultado de la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="83a7c-113">The Value property is automatically set to the evaluation result of the expression.</span></span>  
  
-   <span data-ttu-id="83a7c-114">La propiedad ValueType contiene el tipo de datos del valor de la propiedad Value.</span><span class="sxs-lookup"><span data-stu-id="83a7c-114">The ValueType property contains the data type of the value in the Value property.</span></span> <span data-ttu-id="83a7c-115">Si Value se establece con una expresión, ValueType se actualiza automáticamente a un tipo de datos compatible con el resultado de la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="83a7c-115">When Value is set by an expression, ValueType is automatically updated to a data type that is compatible with the evaluation result of the expression.</span></span> <span data-ttu-id="83a7c-116">Por ejemplo, si valor contiene 0 y la propiedad ValueType contiene **Int32** y después establece Expression en getDate (), Value contiene la fecha y hora actuales y ValueType está establecido en `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="83a7c-116">For example, if Value contains 0 and ValueType property contains **Int32** and you then set Expression to GETDATE(), Value contains the current date and time and ValueType is set to `DateTime`.</span></span>  
  
-   <span data-ttu-id="83a7c-117">La ventana **Propiedades** de la variable proporciona acceso al cuadro de diálogo **Generador de expresiones** .</span><span class="sxs-lookup"><span data-stu-id="83a7c-117">The **Properties** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="83a7c-118">Esta herramienta se puede usar para generar, validar y evaluar expresiones.</span><span class="sxs-lookup"><span data-stu-id="83a7c-118">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="83a7c-119">Para más información, vea [Generador de expresiones](expressions/expression-builder.md) y [Expresiones de Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="83a7c-119">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="83a7c-120">Cuando se usa la ventana **Variables** para establecer expresiones en una variable definida por el usuario:</span><span class="sxs-lookup"><span data-stu-id="83a7c-120">When you use the **Variables** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="83a7c-121">Para usar una expresión para establecer el valor de la variable, primero confirme que el tipo de datos de la variable es compatible con el resultado de la evaluación de la expresión y, a continuación, proporcione una expresión en la `Expression` columna de la ventana **variables** .</span><span class="sxs-lookup"><span data-stu-id="83a7c-121">To use an expression to set the variable value, first confirm that the variable data type is compatible with the evaluation result of the expression and then provide an expression in the `Expression` column of the **Variables** window.</span></span> <span data-ttu-id="83a7c-122">La propiedad EvaluateAsExpression de la ventana **propiedades** se establece automáticamente en `True` .</span><span class="sxs-lookup"><span data-stu-id="83a7c-122">The EvaluateAsExpression property in the **Properties** window is automatically set to `True`.</span></span>  
  
-   <span data-ttu-id="83a7c-123">Cuando asigne una expresión a una variable, un marcador especial de icono se muestra junto a la variable.</span><span class="sxs-lookup"><span data-stu-id="83a7c-123">When you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="83a7c-124">Este marcador de icono especial también aparece junto a los administradores de conexiones y las tareas con expresiones establecidas.</span><span class="sxs-lookup"><span data-stu-id="83a7c-124">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
-   <span data-ttu-id="83a7c-125">La ventana **Variables** de la variable proporciona acceso al cuadro de diálogo **Generador de expresiones** .</span><span class="sxs-lookup"><span data-stu-id="83a7c-125">The **Variables** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="83a7c-126">Esta herramienta se puede usar para generar, validar y evaluar expresiones.</span><span class="sxs-lookup"><span data-stu-id="83a7c-126">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="83a7c-127">Para más información, vea [Generador de expresiones](expressions/expression-builder.md) y [Expresiones de Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="83a7c-127">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="83a7c-128">En la ventana **variables** y **propiedades** , si asigna una expresión a la variable y `EvaluateAsExpression` está establecida en `True` , no puede cambiar el tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="83a7c-128">In both the **Variables** and **Properties** window, if you assign an expression to the variable, and `EvaluateAsExpression` is set to `True`, you cannot change the variable data type.</span></span>  
  
 <span data-ttu-id="83a7c-129">**Establecer las propiedades Espacio de nombres y Nombre**</span><span class="sxs-lookup"><span data-stu-id="83a7c-129">**Setting the Namespace and Name Properties**</span></span>  
  
 <span data-ttu-id="83a7c-130">Los valores de las propiedades `Name` y `Namespace` deben empezar con una letra, como se define en el Estándar Unicode 2.0, o un carácter de subrayado (_).</span><span class="sxs-lookup"><span data-stu-id="83a7c-130">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="83a7c-131">Los caracteres siguientes pueden ser letras o números, tal como se define en el Estándar Unicode 2.0, o el carácter de subrayado (\_).</span><span class="sxs-lookup"><span data-stu-id="83a7c-131">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="using-the-variables-window-to-set-properties"></a><span data-ttu-id="83a7c-132">Usar la ventana Variables para establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="83a7c-132">Using the Variables Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-variables-window"></a><span data-ttu-id="83a7c-133">Para establecer las propiedades de una variable mediante la ventana Variables</span><span class="sxs-lookup"><span data-stu-id="83a7c-133">To set the properties of a variable by using the Variables window</span></span>  
  
1.  <span data-ttu-id="83a7c-134">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="83a7c-134">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="83a7c-135">En el Explorador de soluciones, haga clic con el botón secundario en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="83a7c-135">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="83a7c-136">En el menú **SSIS** , haga clic en **Variables**.</span><span class="sxs-lookup"><span data-stu-id="83a7c-136">On the **SSIS** menu, click **Variables**.</span></span>  
  
     <span data-ttu-id="83a7c-137">También puede ver la ventana **Variables** si asigna el comando View.Variables a una combinación de teclas que desee en la página **Teclado** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="83a7c-137">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="83a7c-138">Opcionalmente, haga clic en **Opciones de cuadrícula** de la ventana **Variables**, seleccione las columnas que aparecen en la ventana **Variables** y seleccione filtros para aplicarlos a la lista de variables.</span><span class="sxs-lookup"><span data-stu-id="83a7c-138">Optionally, in the **Variables** window click **Grid Options**, and then select the columns to appear in the **Variables** window and select the filters to apply to the list of variables.</span></span>  
  
5.  <span data-ttu-id="83a7c-139">Seleccione la variable en la lista y, a continuación, actualice los valores de los `Name` **tipos de datos**,,,, `Value` `Namespace` **generar evento de cambio**, **Descripción** y `Expression` columnas.</span><span class="sxs-lookup"><span data-stu-id="83a7c-139">Select the variable in the list, and then update values in the `Name`, **Data Type**, `Value`, `Namespace`, **Raise Change Event**, **Description,** and `Expression` columns.</span></span>  
  
6.  <span data-ttu-id="83a7c-140">Seleccione la variable en la lista y haga clic en **Mover variable** para cambiar el ámbito.</span><span class="sxs-lookup"><span data-stu-id="83a7c-140">Select the variable in the list, and then click **Move Variable** to change the scope.</span></span>  
  
7.  <span data-ttu-id="83a7c-141">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="83a7c-141">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="using-the-properties-window-to-set-properties"></a><span data-ttu-id="83a7c-142">Usar la ventana Propiedades para establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="83a7c-142">Using the Properties Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-properties-window"></a><span data-ttu-id="83a7c-143">Para establecer las propiedades de una variable mediante la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="83a7c-143">To set the properties of a variable by using the Properties window</span></span>  
  
1.  <span data-ttu-id="83a7c-144">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="83a7c-144">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="83a7c-145">En el Explorador de soluciones, haga clic con el botón secundario en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="83a7c-145">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="83a7c-146">En el menú **Ver** , haga clic en **Ventana de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="83a7c-146">On the **View** menu, click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="83a7c-147">En el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en la pestaña **Explorador de paquetes** y expanda el nodo Paquete.</span><span class="sxs-lookup"><span data-stu-id="83a7c-147">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Package Explorer** tab and expand the Package node.</span></span>  
  
5.  <span data-ttu-id="83a7c-148">Para modificar variables en el ámbito de paquete, expanda el nodo Variables; también puede expandir los nodos Controladores de eventos o Ejecutables hasta localizar el nodo Variables que contiene la variable que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="83a7c-148">To modify variables with package scope, expand the Variables node; otherwise, expand the Event Handlers or Executables nodes until you locate the Variables node that contains the variable that you want to modify.</span></span>  
  
6.  <span data-ttu-id="83a7c-149">Haga clic en la variable cuyas propiedades desee modificar.</span><span class="sxs-lookup"><span data-stu-id="83a7c-149">Click the variable whose properties you want to modify.</span></span>  
  
7.  <span data-ttu-id="83a7c-150">En la ventana **Propiedades** , actualice las propiedades de la variable de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="83a7c-150">In the **Properties** window, update the read/write variable properties.</span></span> <span data-ttu-id="83a7c-151">Algunas propiedades son solo de lectura/escritura para las variables definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="83a7c-151">Some properties are read/read only for user-defined variables.</span></span>  
  
     <span data-ttu-id="83a7c-152">Para más información sobre las propiedades, vea [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="83a7c-152">For more information about the properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
8.  <span data-ttu-id="83a7c-153">Para guardar el paquete actualizado, en el menú **Archivo** , haga clic en **Guardar los elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="83a7c-153">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a7c-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83a7c-154">See Also</span></span>  
 <span data-ttu-id="83a7c-155">[Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="83a7c-155">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="83a7c-156">[Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="83a7c-156">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="83a7c-157">Agregar, eliminar, cambiar el ámbito de la variable definida por el usuario en un paquete</span><span class="sxs-lookup"><span data-stu-id="83a7c-157">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
