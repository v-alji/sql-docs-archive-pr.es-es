---
title: Ventana Variables | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variables.f1
helpviewer_keywords:
- Variables Window dialog box
ms.assetid: f405e5ce-ef69-4c58-8c7d-a3d44dfe9ab0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffd6da67386291c14ebf588da9a1cf8f399214b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674892"
---
# <a name="variables-window"></a><span data-ttu-id="eafd1-102">Ventana Variables</span><span class="sxs-lookup"><span data-stu-id="eafd1-102">Variables Window</span></span>
  <span data-ttu-id="eafd1-103">Use la ventana **Variables** para crear y modificar variables definidas por el usuario y ver variables del sistema.</span><span class="sxs-lookup"><span data-stu-id="eafd1-103">Use the **Variables** window to create and modify user-defined variables and view system variables.</span></span>  
  
 <span data-ttu-id="eafd1-104">De forma predeterminada, la ventana **variables** se encuentra debajo del área **Administradores de conexiones** en el Diseñador SSIS, en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eafd1-104">By default, the **Variables** window is located below the **Connection Managers** area in the SSIS Designer, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="eafd1-105">Si no ve la ventana **variables**, haga clic en **Variables** en el menú **SSIS** para mostrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="eafd1-105">If you don't see the **Variables** window, click **Variables** on the **SSIS** menu to display the window.</span></span>  
  
 <span data-ttu-id="eafd1-106">También puede ver la ventana **Variables** si asigna el comando View.Variables a una combinación de teclas que desee en la página **Teclado** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="eafd1-106">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eafd1-107">Los valores de las propiedades `Name` y `Namespace` deben empezar con una letra, como se define en el Estándar Unicode 2.0, o un carácter de subrayado (_).</span><span class="sxs-lookup"><span data-stu-id="eafd1-107">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="eafd1-108">Los caracteres siguientes pueden ser letras o números, tal como se define en el Estándar Unicode 2.0, o el carácter de subrayado (\_).</span><span class="sxs-lookup"><span data-stu-id="eafd1-108">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eafd1-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="eafd1-109">Options</span></span>  
 <span data-ttu-id="eafd1-110">**Agregar variable**</span><span class="sxs-lookup"><span data-stu-id="eafd1-110">**Add Variable**</span></span>  
 <span data-ttu-id="eafd1-111">Agrega una variable definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="eafd1-111">Add a user-defined variable.</span></span>  
  
 <span data-ttu-id="eafd1-112">**Mover variable**</span><span class="sxs-lookup"><span data-stu-id="eafd1-112">**Move Variable**</span></span>  
 <span data-ttu-id="eafd1-113">Haga clic en una variable de la lista y luego en **Mover variable** para cambiar el ámbito de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-113">Click a variable in the list, and then click **Move Variable** to change the variable scope.</span></span> <span data-ttu-id="eafd1-114">En el cuadro de diálogo **Seleccionar nuevo ámbito** , seleccione el paquete o un contenedor, una tarea o un controlador de eventos en el paquete, para cambiar el ámbito de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-114">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
 <span data-ttu-id="eafd1-115">Para más información sobre el ámbito de las variables, vea [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="eafd1-115">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="eafd1-116">**Eliminar variable**</span><span class="sxs-lookup"><span data-stu-id="eafd1-116">**Delete Variable**</span></span>  
 <span data-ttu-id="eafd1-117">Seleccione una variable en la lista y, luego, haga clic en **Eliminar variable**.</span><span class="sxs-lookup"><span data-stu-id="eafd1-117">Select a variable from the list, and then click **Delete Variable**.</span></span>  
  
 <span data-ttu-id="eafd1-118">**Opciones de cuadrícula**</span><span class="sxs-lookup"><span data-stu-id="eafd1-118">**Grid Options**</span></span>  
 <span data-ttu-id="eafd1-119">Haga clic para abrir el cuadro de diálogo **Opciones de la cuadrícula de variables** , donde puede cambiar la selección de la columna y aplicar filtros a la ventana **Variables** .</span><span class="sxs-lookup"><span data-stu-id="eafd1-119">Click to open the **Variable Grid Options** dialog box where you can change the column selection and apply filters to the **Variables** window.</span></span> <span data-ttu-id="eafd1-120">Para más información, consulte [Opciones de la cuadrícula de variables](../../2014/integration-services/variable-grid-options.md).</span><span class="sxs-lookup"><span data-stu-id="eafd1-120">For more information, see [Variable Grid Options](../../2014/integration-services/variable-grid-options.md).</span></span>  
  
 `Name`  
 <span data-ttu-id="eafd1-121">Escriba el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-121">View the variable name.</span></span> <span data-ttu-id="eafd1-122">Puede actualizar el nombre de la variable para las variables definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="eafd1-122">You can update the name for user-defined variables.</span></span>  
  
 <span data-ttu-id="eafd1-123">**Ámbito**</span><span class="sxs-lookup"><span data-stu-id="eafd1-123">**Scope**</span></span>  
 <span data-ttu-id="eafd1-124">Presenta el ámbito de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-124">View the scope of the variable.</span></span> <span data-ttu-id="eafd1-125">La variable tiene el ámbito de todo el paquete o el ámbito de un contenedor o una tarea.</span><span class="sxs-lookup"><span data-stu-id="eafd1-125">A variable has either the scope of the entire package, or the scope of a container or task.</span></span> <span data-ttu-id="eafd1-126">El ámbito de la variable debe ser suficiente como para que ésta sea visible para cualquier otra tarea u otro componente que necesite leer o establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="eafd1-126">The scope of the variable must be sufficient so that the variable is visible to any other tasks or components that need to read or set its value.</span></span>  
  
 <span data-ttu-id="eafd1-127">Puede cambiar el ámbito haciendo clic en la variable y haciendo clic en **Mover variable** en la ventana **Variables** .</span><span class="sxs-lookup"><span data-stu-id="eafd1-127">You can change the scope by clicking the variable and then clicking **Move Variable** in the **Variables** window.</span></span>  
  
 <span data-ttu-id="eafd1-128">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="eafd1-128">**Data Type**</span></span>  
 <span data-ttu-id="eafd1-129">Presenta el tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-129">View the data type of the variable.</span></span> <span data-ttu-id="eafd1-130">Puede seleccionar un tipo de dato de la lista para variables definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="eafd1-130">You can select a data type from the list for user-defined variables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eafd1-131">Si asigna una expresión variable, no puede cambiar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="eafd1-131">If you assign an expression to the variable, you cannot change the data type.</span></span>  
  
 <span data-ttu-id="eafd1-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="eafd1-132">**Value**</span></span>  
 <span data-ttu-id="eafd1-133">Presenta el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-133">View the variable value.</span></span> <span data-ttu-id="eafd1-134">Puede actualizar el valor de la variable para variables definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="eafd1-134">You can update the value for user-defined variables.</span></span> <span data-ttu-id="eafd1-135">Este valor puede ser un literal o una expresión y el valor puede ser una cadena de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="eafd1-135">This value can be a literal or an expression, and the value can be a multi-line string.</span></span> <span data-ttu-id="eafd1-136">Para asignar una expresión variable, haga clic en el botón de la elipse que se encuentra junto a la columna **Expresión** en la ventana **Variables** .</span><span class="sxs-lookup"><span data-stu-id="eafd1-136">To assign an expression to the variable, click the ellipse button that is next to the **Expression** column in the **Variables** window.</span></span>  
  
 `Namespace`  
 <span data-ttu-id="eafd1-137">Presenta el nombre del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="eafd1-137">View the namespace name.</span></span> <span data-ttu-id="eafd1-138">Las variables definidas por el usuario se crean Inicialmente en el espacio de nombres del **usuario** , pero puede cambiar el nombre del espacio de nombres en el `Namespace` campo.</span><span class="sxs-lookup"><span data-stu-id="eafd1-138">User-defined variables are initially created in the **User** namespace, but you can change the namespace name in the `Namespace` field.</span></span> <span data-ttu-id="eafd1-139">Para mostrar esta columna, haga clic en **Opciones de cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="eafd1-139">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="eafd1-140">**Raise Change Event**</span><span class="sxs-lookup"><span data-stu-id="eafd1-140">**Raise Change Event**</span></span>  
 <span data-ttu-id="eafd1-141">Indica si se activa un evento `OnVariableValueChanged` cuando un valor cambia.</span><span class="sxs-lookup"><span data-stu-id="eafd1-141">Indicate whether to raise the `OnVariableValueChanged` event when a value changes.</span></span> <span data-ttu-id="eafd1-142">Puede actualizar el valor de la variable para variables definidas por el usuario y el sistema.</span><span class="sxs-lookup"><span data-stu-id="eafd1-142">You can update the value for user-defined and system variables.</span></span> <span data-ttu-id="eafd1-143">De manera predeterminada, la ventana **Variables** no muestra esta columna.</span><span class="sxs-lookup"><span data-stu-id="eafd1-143">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="eafd1-144">Para mostrar esta columna, haga clic en **Opciones de cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="eafd1-144">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="eafd1-145">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="eafd1-145">**Description**</span></span>  
 <span data-ttu-id="eafd1-146">Vea la descripción de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-146">View the variable description.</span></span> <span data-ttu-id="eafd1-147">Puede cambiar la descripción para variables definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="eafd1-147">You can change the description for user-defined variables.</span></span> <span data-ttu-id="eafd1-148">De manera predeterminada, la ventana **Variables** no muestra esta columna.</span><span class="sxs-lookup"><span data-stu-id="eafd1-148">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="eafd1-149">Para mostrar esta columna, haga clic en **Opciones de cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="eafd1-149">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="eafd1-150">**Expression**</span><span class="sxs-lookup"><span data-stu-id="eafd1-150">**Expression**</span></span>  
 <span data-ttu-id="eafd1-151">Vea la expresión asignada a la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-151">View the expression assigned to the variable.</span></span> <span data-ttu-id="eafd1-152">Para asignar una expresión, haga clic en el botón de la elipse.</span><span class="sxs-lookup"><span data-stu-id="eafd1-152">To assign an expression, click the ellipse button.</span></span>  
  
 <span data-ttu-id="eafd1-153">Si asigna una expresión a una variable, un marcador especial de icono se muestra junto a la variable.</span><span class="sxs-lookup"><span data-stu-id="eafd1-153">If you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="eafd1-154">Este marcador de icono especial también aparece junto a los administradores de conexiones y las tareas con expresiones establecidas.</span><span class="sxs-lookup"><span data-stu-id="eafd1-154">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafd1-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eafd1-155">See Also</span></span>  
 <span data-ttu-id="eafd1-156">[Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="eafd1-156">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="eafd1-157">[Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="eafd1-157">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="eafd1-158">[Integration Services &#40;expresiones de&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="eafd1-158">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="eafd1-159">Generar archivos de volcado para la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="eafd1-159">Generating Dump Files for Package Execution</span></span>](troubleshooting/generating-dump-files-for-package-execution.md)  
  
  
