---
title: Cuadro de diálogo Ejecutar paquete | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageexecute.f1
- sql12.ssis.ssms.executepackage.f1
ms.assetid: 4f7a806d-4867-4d1f-bc65-b00c1caee7b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b60381054c781cd59f0a9d434710663b72d616c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673793"
---
# <a name="execute-package-dialog-box"></a><span data-ttu-id="317eb-102">Execute Package Dialog Box</span><span class="sxs-lookup"><span data-stu-id="317eb-102">Execute Package Dialog Box</span></span>
  <span data-ttu-id="317eb-103">Use el cuadro de diálogo **Ejecutar paquete** para ejecutar un paquete que está almacenado en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="317eb-103">Use the **Execute Package** dialog box to run a package that is stored on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="317eb-104">Un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] puede contener parámetros que hagan referencia a valores almacenados en variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="317eb-104">An [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package may contain parameters that values stored in environment variables.</span></span> <span data-ttu-id="317eb-105">Antes de ejecutar este tipo de paquete, debe especificar qué referencia del entorno se utilizará para proporcionar los valores de la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="317eb-105">Before executing such a package, you must specify which environment will be used to provide the environment variable values.</span></span> <span data-ttu-id="317eb-106">Un proyecto puede contener varios entornos, pero se puede utilizar solo un entorno para enlazar los valores de variable de entorno en el momento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="317eb-106">A project may contain multiple environments, but only one environment can be used for binding environment variable values at the time of execution.</span></span> <span data-ttu-id="317eb-107">Si no se usan variables de entorno en el paquete, no se requiere un entorno.</span><span class="sxs-lookup"><span data-stu-id="317eb-107">If no environment variables are used in the package, an environment is not required.</span></span>  
  
 <span data-ttu-id="317eb-108">¿Qué desea hacer?</span><span class="sxs-lookup"><span data-stu-id="317eb-108">What do you want to do?</span></span>  
  
-   [<span data-ttu-id="317eb-109">Abrir el cuadro de diálogo Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="317eb-109">Open the Execute Package dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="317eb-110">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="317eb-110">Set the Options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="317eb-111">Establecer las opciones de la pestaña Parámetros</span><span class="sxs-lookup"><span data-stu-id="317eb-111">Set the Options on the Parameters tab</span></span>](#parameters)  
  
-   [<span data-ttu-id="317eb-112">Establecer las opciones de la pestaña Administradores de conexiones</span><span class="sxs-lookup"><span data-stu-id="317eb-112">Set the Options on the Connection Managers tab</span></span>](#connection)  
  
-   [<span data-ttu-id="317eb-113">Establecer las opciones de la pestaña Avanzadas</span><span class="sxs-lookup"><span data-stu-id="317eb-113">Set the Options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="317eb-114">Scripting de las opciones del cuadro de diálogo Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="317eb-114">Scripting the Options in the Execute Package Dialog Box</span></span>](#script)  
  
##  <a name="open-the-execute-package-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="317eb-115">Abrir el cuadro de diálogo Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="317eb-115">Open the Execute Package dialog box</span></span>  
  
1.  <span data-ttu-id="317eb-116">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="317eb-116">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="317eb-117">Se conectará a la instancia del [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] que hospeda la base de datos SSISDB.</span><span class="sxs-lookup"><span data-stu-id="317eb-117">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="317eb-118">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="317eb-118">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="317eb-119">Expanda el nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="317eb-119">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="317eb-120">Expanda la carpeta que contiene el paquete que desea ejecutar.</span><span class="sxs-lookup"><span data-stu-id="317eb-120">Expand the folder that contains the package you want to run.</span></span>  
  
5.  <span data-ttu-id="317eb-121">Haga clic con el botón derecho en el paquete y, después, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="317eb-121">Right-click the package, and then click **Execute**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="317eb-122">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="317eb-122">Set the Options on the General page</span></span>  
 <span data-ttu-id="317eb-123">Seleccione **Entorno** para especificar el entorno que se aplica cuando se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="317eb-123">Select **Environment** to specify the environment that is applied with the package is run.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-tab"></a><a name="parameters"></a> <span data-ttu-id="317eb-124">Establecer las opciones de la pestaña Parámetros</span><span class="sxs-lookup"><span data-stu-id="317eb-124">Set the Options on the Parameters tab</span></span>  
 <span data-ttu-id="317eb-125">Utilice la pestaña **Parámetros** para modificar los valores de parámetro que se utilizan cuando se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="317eb-125">Use the **Parameters** tab to modify the parameter values that are used when the package runs.</span></span>  
  
##  <a name="set-the-options-on-the-connection-managers-tab"></a><a name="connection"></a> <span data-ttu-id="317eb-126">Establecer las opciones de la pestaña Administradores de conexiones</span><span class="sxs-lookup"><span data-stu-id="317eb-126">Set the Options on the Connection Managers tab</span></span>  
 <span data-ttu-id="317eb-127">Utilice la pestaña Administradores de conexiones para establecer las propiedades de los administradores de conexiones del paquete.</span><span class="sxs-lookup"><span data-stu-id="317eb-127">Use the Connection Managers tab to set the properties of the package connection manager(s).</span></span>  
  
##  <a name="set-the-options-on-the-advanced-tab"></a><a name="advanced"></a> <span data-ttu-id="317eb-128">Establecer las opciones de la pestaña Avanzadas</span><span class="sxs-lookup"><span data-stu-id="317eb-128">Set the Options on the Advanced tab</span></span>  
 <span data-ttu-id="317eb-129">Utilice la pestaña Avanzadas para administrar propiedades y otra configuración del paquete.</span><span class="sxs-lookup"><span data-stu-id="317eb-129">Use the Advanced tab to manage properties and other package settings.</span></span>  
  
 <span data-ttu-id="317eb-130">**Agregar**, **Editar**, **Quitar**</span><span class="sxs-lookup"><span data-stu-id="317eb-130">**Add**, **Edit**, **Remove**</span></span>  
 <span data-ttu-id="317eb-131">Haga clic para agregar, editar o quitar una propiedad.</span><span class="sxs-lookup"><span data-stu-id="317eb-131">Click to add, edit, or remove a property.</span></span>  
  
 <span data-ttu-id="317eb-132">**Nivel de registro**</span><span class="sxs-lookup"><span data-stu-id="317eb-132">**Logging level**</span></span>  
 <span data-ttu-id="317eb-133">Seleccione el nivel de registro de la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="317eb-133">Select the logging level for the package execution.</span></span> <span data-ttu-id="317eb-134">Para más información, vea [catalog.set_execution_parameter_value &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="317eb-134">For more information, see [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span></span>  
  
 <span data-ttu-id="317eb-135">**Volcado de errores**</span><span class="sxs-lookup"><span data-stu-id="317eb-135">**Dump on errors**</span></span>  
 <span data-ttu-id="317eb-136">Especifique si se crea un archivo de volcado cuando se producen errores durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="317eb-136">Specify whether a dump file is created when errors occur during the package execution.</span></span> <span data-ttu-id="317eb-137">Para obtener más información, consulte [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="317eb-137">For more information, see [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span></span>  
  
 <span data-ttu-id="317eb-138">**Tiempo de ejecución de 32 bits**</span><span class="sxs-lookup"><span data-stu-id="317eb-138">**32-bit runtime**</span></span>  
 <span data-ttu-id="317eb-139">Especifique que el paquete se ejecutará en un sistema de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="317eb-139">Specify that the package will execute on a 32-bit system.</span></span>  
  
##  <a name="scripting-the-options-in-the-execute-package-dialog-box"></a><a name="script"></a> <span data-ttu-id="317eb-140">Scripting de las opciones del cuadro de diálogo Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="317eb-140">Scripting the Options in the Execute Package Dialog Box</span></span>  
 <span data-ttu-id="317eb-141">Mientras está en el cuadro de diálogo **Ejecutar paquete** , también puede utilizar el botón **Script** de la barra de herramientas para escribir código de [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="317eb-141">While you are in the **Execute Package** dialog box, you can also use the **Script** button on the toolbar to write [!INCLUDE[tsql](../includes/tsql-md.md)] code for you.</span></span> <span data-ttu-id="317eb-142">El script generado realiza una llamada a los procedimientos almacenados [catalog.start_execution &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) con las mismas opciones que ha seleccionado en el cuadro de diálogo **Ejecutar paquete**.</span><span class="sxs-lookup"><span data-stu-id="317eb-142">The generated script calls the stored procedures [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) with the same options that you have selected in the **Execute Package** dialog box.</span></span> <span data-ttu-id="317eb-143">El script aparece en una nueva ventana de script en [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="317eb-143">The script appears in a new script window in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
  
