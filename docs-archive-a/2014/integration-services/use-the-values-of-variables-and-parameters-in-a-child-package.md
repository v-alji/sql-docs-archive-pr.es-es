---
title: Usar los valores de variables y parámetros en un paquete secundario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], passing between packages
- configurations [Integration Services]
- packages [Integration Services], configurations
- variables [Integration Services], adding
ms.assetid: 9b939edb-4e17-48e5-8428-855beb10049c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 28561db91e5e924d8b25f9c7be7a4a51c6c315ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674898"
---
# <a name="use-the-values-of-variables-and-parameters-in-a-child-package"></a><span data-ttu-id="415cb-102">Usar los valores de variables y parámetros en un paquete secundario</span><span class="sxs-lookup"><span data-stu-id="415cb-102">Use the Values of Variables and Parameters in a Child Package</span></span>
  <span data-ttu-id="415cb-103">Este procedimiento describe cómo crear una configuración de paquete que utiliza el tipo de configuración de variables primarias.</span><span class="sxs-lookup"><span data-stu-id="415cb-103">This procedure describes how to create a package configuration that uses the parent variable configuration type.</span></span> <span data-ttu-id="415cb-104">Este tipo de configuración habilita un paquete secundario que se ejecuta desde un paquete primario para tener acceso a una variable del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="415cb-104">This configuration type enables a child package that is run from a parent package to access a variable in the parent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="415cb-105">También puede pasar valores a un paquete secundario configurando la Tarea Ejecutar paquete para asignar variables o parámetros del paquete primario, o parámetros del proyecto, a parámetros del paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="415cb-105">You can also pass values to a child package by configuring the Execute Package Task to map parent package variables or parameters, or project parameters, to child package parameters.</span></span> <span data-ttu-id="415cb-106">Para más información, consulte [Execute Package Task](control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="415cb-106">For more information, see [Execute Package Task](control-flow/execute-package-task.md).</span></span>  
  
 <span data-ttu-id="415cb-107">No es necesario crear la variable en el paquete primario antes de crear la configuración de paquete en el paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="415cb-107">It is not necessary to create the variable in the parent package before you create the package configuration in the child package.</span></span> <span data-ttu-id="415cb-108">Puede agregar la variable al paquete primario en cualquier momento, pero debe utilizar el nombre exacto de la variable primaria en la configuración del paquete.</span><span class="sxs-lookup"><span data-stu-id="415cb-108">You can add the variable to the parent package at any time, but you must use the exact name of the parent variable in the package configuration.</span></span> <span data-ttu-id="415cb-109">Sin embargo, antes de que pueda crear una configuración de variable primaria, debe existir una variable en el paquete secundario que la configuración pueda actualizar.</span><span class="sxs-lookup"><span data-stu-id="415cb-109">However, before you can create a parent variable configuration, there must be an existing variable in the child package that the configuration can update.</span></span> <span data-ttu-id="415cb-110">Para obtener más información sobre cómo agregar y configurar variables, vea [Agregar, eliminar, cambiar el ámbito de la variable definida por el usuario en un paquete](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="415cb-110">For more information about adding and configuring variables, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
 <span data-ttu-id="415cb-111">El ámbito de la variable del paquete primario que se utiliza en una configuración de variable primaria se puede establecer en la tarea Ejecutar paquete, el contenedor que contiene la tarea o el paquete.</span><span class="sxs-lookup"><span data-stu-id="415cb-111">The scope of the variable in the parent package that is used in a parent variable configuration can be set to the Execute Package task, to the container that has the task, or to the package.</span></span> <span data-ttu-id="415cb-112">Si se definen varias variables con el mismo nombre en un paquete, se utiliza la variable que está más próxima en ámbito de la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="415cb-112">If multiple variables with the same name are defined in a package, the variable that is closest in scope to the Execute Package task is used.</span></span> <span data-ttu-id="415cb-113">El ámbito más cercano a la tarea Ejecutar paquete es la tarea propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="415cb-113">The closest scope to the Execute Package task is the task itself.</span></span>  
  
### <a name="to-add-a-variable-to-a-parent-package"></a><span data-ttu-id="415cb-114">Para agregar una variable a un paquete primario</span><span class="sxs-lookup"><span data-stu-id="415cb-114">To add a variable to a parent package</span></span>  
  
1.  <span data-ttu-id="415cb-115">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete al que desea agregar una variable para pasar a un paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="415cb-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a variable to pass to a child package.</span></span>  
  
2.  <span data-ttu-id="415cb-116">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="415cb-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="415cb-117">En el diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , siga uno de estos procedimientos para definir el ámbito de la variable:</span><span class="sxs-lookup"><span data-stu-id="415cb-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="415cb-118">Para establecer el ámbito en el paquete, haga clic en cualquier lugar de la superficie de diseño de la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="415cb-118">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="415cb-119">Para establecer el ámbito en un contenedor primario de la tarea Ejecutar paquete, haga clic en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="415cb-119">To set the scope to a parent container of the Execute Package task, click the container.</span></span>  
  
    -   <span data-ttu-id="415cb-120">Para establecer el ámbito a la tarea Ejecutar paquete, haga clic en ella.</span><span class="sxs-lookup"><span data-stu-id="415cb-120">To set the scope to the Execute Package task, click the task.</span></span>  
  
4.  <span data-ttu-id="415cb-121">Agregue y configure una variable.</span><span class="sxs-lookup"><span data-stu-id="415cb-121">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="415cb-122">Seleccione un tipo de datos que sea compatible con los datos que almacenará la variable.</span><span class="sxs-lookup"><span data-stu-id="415cb-122">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="415cb-123">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="415cb-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-variable-to-a-child-package"></a><span data-ttu-id="415cb-124">Para agregar una variable a un paquete secundario</span><span class="sxs-lookup"><span data-stu-id="415cb-124">To add a variable to a child package</span></span>  
  
1.  <span data-ttu-id="415cb-125">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete al que desea agregar una configuración de variable primaria.</span><span class="sxs-lookup"><span data-stu-id="415cb-125">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a parent variable configuration.</span></span>  
  
2.  <span data-ttu-id="415cb-126">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="415cb-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="415cb-127">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , para establecer el ámbito en el paquete, haga clic en cualquier lugar de la superficie de diseño de la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="415cb-127">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="415cb-128">Agregue y configure una variable.</span><span class="sxs-lookup"><span data-stu-id="415cb-128">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="415cb-129">Seleccione un tipo de datos que sea compatible con los datos que almacenará la variable.</span><span class="sxs-lookup"><span data-stu-id="415cb-129">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="415cb-130">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="415cb-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-parent-package-configuration-to-a-child-package"></a><span data-ttu-id="415cb-131">Para agregar una configuración de paquete primario a un paquete secundario</span><span class="sxs-lookup"><span data-stu-id="415cb-131">To add a parent package configuration to a child package</span></span>  
  
1.  <span data-ttu-id="415cb-132">Si el paquete secundario todavía no está abierto, ábralo en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="415cb-132">If it is not already open, open the child package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="415cb-133">Haga clic en cualquier punto de la superficie de diseño de la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="415cb-133">Click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="415cb-134">En el menú **SSIS** , haga clic en **Configuraciones de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="415cb-134">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="415cb-135">En el cuadro de diálogo **Organizador de configuraciones de paquetes** , seleccione **Habilitar configuraciones de paquetes**y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="415cb-135">In the **Package Configuration Organizer** dialog box, select **Enable package configuration**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="415cb-136">En la página de bienvenida del Asistente para la configuración de paquetes, haga clic en **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="415cb-136">On the welcome page of the Package Configuration Wizard, click **Next.**</span></span>  
  
6.  <span data-ttu-id="415cb-137">En la página Seleccionar tipo de configuración, en la lista **Tipo de configuración** , seleccione **Variable de paquete primario** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="415cb-137">On the Select Configuration Type page, in the **Configuration type** list, select **Parent package variable** and do one of the following:</span></span>  
  
    -   <span data-ttu-id="415cb-138">Seleccione **Especificar valores de configuración directamente**y luego, en el cuadro **Variable primaria** , proporcione el nombre de la variable del paquete primario que se utilizará en la configuración.</span><span class="sxs-lookup"><span data-stu-id="415cb-138">Select **Specify configuration settings directly**, and then in the **Parent variable** box, provide the name of the variable in the parent package to use in the configuration.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="415cb-139">Los nombres de variables distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="415cb-139">Variable names are case sensitive.</span></span>  
  
    -   <span data-ttu-id="415cb-140">Seleccione **La ubicación de configuración se almacena en una variable de entorno** y luego, en la **lista Variable de entorno**, seleccione la variable de entorno que contenga el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="415cb-140">Select or **Configuration location is stored in an environment variable,** and then in the **Environment variable list**, select the environmentvariable that contains the name of the variable.</span></span>  
  
7.  <span data-ttu-id="415cb-141">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="415cb-141">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="415cb-142">En la página Seleccionar propiedad de destino, expanda el nodo **Variable** y expanda el nodo **Propiedades** de la variable para configurarla, y luego haga clic en la propiedad que establecerá la configuración.</span><span class="sxs-lookup"><span data-stu-id="415cb-142">On the Select Target Property page, expand the **Variable** node, and expand the **Properties** node of the variable to configure, and then click the property to be set by the configuration.</span></span>  
  
9. <span data-ttu-id="415cb-143">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="415cb-143">Click **Next**.</span></span>  
  
10. <span data-ttu-id="415cb-144">En la página Finalización del asistente, también puede modificar el nombre predeterminado de la configuración y revisar la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="415cb-144">On the Completing the Wizard page, optionally, modify the default name of the configuration and review the configuration information.</span></span>  
  
11. <span data-ttu-id="415cb-145">Haga clic en **Finalizar** para completar el asistente y volver al cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="415cb-145">Click **Finish** to complete the wizard and return to the **Package Configuration Organizer** dialog box.</span></span>  
  
12. <span data-ttu-id="415cb-146">En el cuadro de diálogo **Organizador de configuraciones de paquetes** , el cuadro **Configuración** muestra la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="415cb-146">In the **Package Configuration Organizer** dialog box, the **Configuration** box lists the new configuration.</span></span>  
  
13. <span data-ttu-id="415cb-147">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="415cb-147">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415cb-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="415cb-148">See Also</span></span>  
 <span data-ttu-id="415cb-149">[Configuraciones de paquetes](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="415cb-149">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="415cb-150">[Crear configuraciones de paquetes](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="415cb-150">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="415cb-151">[Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="415cb-151">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="415cb-152">Usar variables en paquetes</span><span class="sxs-lookup"><span data-stu-id="415cb-152">Use Variables in Packages</span></span>](../../2014/integration-services/use-variables-in-packages.md)  
  
  
