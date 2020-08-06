---
title: Agregar, eliminar, cambiar el ámbito de la variable definida por el usuario en un paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], adding
ms.assetid: cbf40c7f-3c8a-48cd-aefa-8b37faf8b40e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7e5980fc7f730c69ef886e4e80760cfbdc9e4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672247"
---
# <a name="add-delete-change-scope-of-user-defined-variable-in-a-package"></a><span data-ttu-id="3db50-102">Agregar, eliminar, cambiar el ámbito de la variable definida por el usuario en un paquete</span><span class="sxs-lookup"><span data-stu-id="3db50-102">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>
  <span data-ttu-id="3db50-103">Estos procedimientos describen cómo agregar, eliminar y cambiar el ámbito de una variable definida por el usuario en un paquete usando la ventana **Variables** .</span><span class="sxs-lookup"><span data-stu-id="3db50-103">These procedures describe how to add, delete, and change the scope of a user-defined variable in a package by using the **Variables** window.</span></span>  
  
 <span data-ttu-id="3db50-104">Para más información sobre el ámbito de las variables, vea [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="3db50-104">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="3db50-105">también proporciona variables del sistema que hacen que la información del sistema esté disponible en tiempo de ejecución y se pueden utilizar en contenedores como paquetes y controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="3db50-105">also provides system variables that make system information available at run time and can be used in containers such as packages and event handlers.</span></span> <span data-ttu-id="3db50-106">Las variables del sistema no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="3db50-106">You cannot delete system variables.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="3db50-107">Para agregar una variable</span><span class="sxs-lookup"><span data-stu-id="3db50-107">To add a variable</span></span>  
  
1.  <span data-ttu-id="3db50-108">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="3db50-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="3db50-109">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="3db50-109">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3db50-110">En el diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , siga uno de estos procedimientos para definir el ámbito de la variable:</span><span class="sxs-lookup"><span data-stu-id="3db50-110">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="3db50-111">Para establecer el ámbito en el paquete, haga clic en cualquier lugar de la superficie de diseño de la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="3db50-111">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="3db50-112">Para establecer el ámbito en un controlador de eventos, seleccione un ejecutable y un controlador de eventos en la superficie de diseño de la pestaña **Controlador de eventos** .</span><span class="sxs-lookup"><span data-stu-id="3db50-112">To set the scope to an event handler, select an executable and an event handler on the design surface of the **Event Handler** tab.</span></span>  
  
    -   <span data-ttu-id="3db50-113">Para establecer el ámbito en una tarea o un contenedor, en la superficie de diseño de la pestaña **Flujo de control** o **Controlador de eventos** , haga clic en una tarea o un contenedor.</span><span class="sxs-lookup"><span data-stu-id="3db50-113">To set the scope to a task or container, on the design surface of the **Control Flow** tab or the **Event Handler** tab, click a task or container.</span></span>  
  
4.  <span data-ttu-id="3db50-114">En el menú **SSIS** , haga clic en **Variables**.</span><span class="sxs-lookup"><span data-stu-id="3db50-114">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="3db50-115">También puede ver la ventana **Variables** si asigna el comando View.Variables a una combinación de teclas que desee en la página **Teclado** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="3db50-115">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
5.  <span data-ttu-id="3db50-116">En la ventana **variables** , haga clic en el icono **Agregar variable** .</span><span class="sxs-lookup"><span data-stu-id="3db50-116">In the **Variables** window, click the **Add Variable** icon.</span></span> <span data-ttu-id="3db50-117">Se agregará la nueva variable a la lista.</span><span class="sxs-lookup"><span data-stu-id="3db50-117">The new variable is added to the list.</span></span>  
  
6.  <span data-ttu-id="3db50-118">Opcionalmente, haga clic en el icono **Opciones de cuadrícula** , seleccione las columnas adicionales que desee mostrar en el cuadro de diálogo **Opciones de cuadrícula de variables** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3db50-118">Optionally, click the **Grid Options** icon, select additional columns to show in the **Variables Grid Options** dialog box, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="3db50-119">O bien, establezca las propiedades de una variable.</span><span class="sxs-lookup"><span data-stu-id="3db50-119">Optionally, set the variable properties.</span></span> <span data-ttu-id="3db50-120">Para obtener más información, vea [Establecer las propiedades de una variable definida por el usuario](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span><span class="sxs-lookup"><span data-stu-id="3db50-120">For more information, see [Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span></span>  
  
8.  <span data-ttu-id="3db50-121">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="3db50-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-variable"></a><span data-ttu-id="3db50-122">Para eliminar una variable</span><span class="sxs-lookup"><span data-stu-id="3db50-122">To delete a variable</span></span>  
  
1.  <span data-ttu-id="3db50-123">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="3db50-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3db50-124">En el Explorador de soluciones, haga clic con el botón secundario en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="3db50-124">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3db50-125">En el menú **SSIS** , haga clic en **Variables**.</span><span class="sxs-lookup"><span data-stu-id="3db50-125">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="3db50-126">También puede ver la ventana **Variables** si asigna el comando View.Variables a una combinación de teclas que desee en la página **Teclado** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="3db50-126">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="3db50-127">Seleccione la variable que desee eliminar y haga clic en **Eliminar variable**.</span><span class="sxs-lookup"><span data-stu-id="3db50-127">Select the variable to delete, and then click **Delete Variable**.</span></span>  
  
     <span data-ttu-id="3db50-128">Si no ve la variable en la ventana variables, haga clic en **Opciones de cuadrícula** y, a continuación, seleccione **Mostrar variables de todos los ámbitos**.</span><span class="sxs-lookup"><span data-stu-id="3db50-128">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="3db50-129">Si se abre el cuadro de diálogo **Confirmar eliminación de variables** , haga clic en **Sí** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="3db50-129">If the **Confirm Deletion of Variables** dialog box opens, click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="3db50-130">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="3db50-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-change-the-scope-of-a-variable"></a><span data-ttu-id="3db50-131">Para cambiar el ámbito de una variable</span><span class="sxs-lookup"><span data-stu-id="3db50-131">To change the scope of a variable</span></span>  
  
1.  <span data-ttu-id="3db50-132">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="3db50-132">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3db50-133">En el Explorador de soluciones, haga clic con el botón secundario en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="3db50-133">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3db50-134">En el menú **SSIS** , haga clic en **Variables**.</span><span class="sxs-lookup"><span data-stu-id="3db50-134">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="3db50-135">También puede ver la ventana **Variables** si asigna el comando View.Variables a una combinación de teclas que desee en la página **Teclado** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="3db50-135">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="3db50-136">Seleccione la variable y haga clic en **Mover variable**.</span><span class="sxs-lookup"><span data-stu-id="3db50-136">Select the variable and then click **Move Variable**.</span></span>  
  
     <span data-ttu-id="3db50-137">Si no ve la variable en la ventana variables, haga clic en **Opciones de cuadrícula** y, a continuación, seleccione **Mostrar variables de todos los ámbitos**.</span><span class="sxs-lookup"><span data-stu-id="3db50-137">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="3db50-138">En el cuadro de diálogo **Seleccionar nuevo ámbito** , seleccione el paquete o un contenedor, una tarea o un controlador de eventos en el paquete, para cambiar el ámbito de la variable.</span><span class="sxs-lookup"><span data-stu-id="3db50-138">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
6.  <span data-ttu-id="3db50-139">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="3db50-139">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db50-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3db50-140">See Also</span></span>  
 <span data-ttu-id="3db50-141">[Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3db50-141">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="3db50-142">[Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3db50-142">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="3db50-143">[Establecer las propiedades de una variable definida por el usuario](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span><span class="sxs-lookup"><span data-stu-id="3db50-143">[Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span></span>  
 [<span data-ttu-id="3db50-144">Usar los valores de variables y parámetros en un paquete secundario</span><span class="sxs-lookup"><span data-stu-id="3db50-144">Use the Values of Variables and Parameters in a Child Package</span></span>](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md)  
  
  
