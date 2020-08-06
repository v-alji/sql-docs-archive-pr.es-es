---
title: Utilidad de configuración del servidor (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 28435f86-5cec-4a1e-9b7d-b2069c1ddddb
author: minewiskan
ms.author: owend
ms.openlocfilehash: f985338e44bf0f4b591fcb70a4e093901626149f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752409"
---
# <a name="server-configuration-utility-data-mining-add-ins-for-excel"></a><span data-ttu-id="82775-102">Utilidad de configuración del servidor (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="82775-102">Server Configuration Utility (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="82775-103">Al instalar los complementos de minería de datos para Excel, también se instala una utilidad de configuración del servidor, que se ejecutará la primera vez que se abran los complementos. En este tema se describe cómo utilizar la utilidad para conectarse a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y configurar una base de datos para trabajar con modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-103">When you install the Data Mining Add-ins for Excel, a Server Configuration Utility is also installed, and will run the first time you open the add-ins. This topic describes how to use the utility to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and set up a database for working with data mining models.</span></span>  
  

  
##  <a name="step-1-connect-to-analysis-services"></a><a name="bkmk_step1"></a><span data-ttu-id="82775-104">Paso 1: conexión a Analysis Services</span><span class="sxs-lookup"><span data-stu-id="82775-104">Step 1: Connect to Analysis Services</span></span>  
 <span data-ttu-id="82775-105">Elija el servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que proporciona los algoritmos de minería de datos y almacena los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-105">Choose the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that provides the data mining algorithms and stores your data mining models.</span></span>  
  
 <span data-ttu-id="82775-106">Cuando cree una conexión para habilitar la minería de datos, debe elegir un servidor en el que pueda probar con los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-106">When you create a connection to enable data mining, you should choose a server where you can experiment with data mining models.</span></span> <span data-ttu-id="82775-107">Se recomienda crear una nueva base de datos en el servidor y dedicar la nueva base de datos a la minería de datos; o bien, pida al administrador que le prepare un servidor de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-107">We recommend that you create a new database on the server and dedicate the new database to data mining, or ask your administrator to prepare a data mining server for you.</span></span> <span data-ttu-id="82775-108">De esa forma puede crear modelos sin afectar al rendimiento de otros servicios.</span><span class="sxs-lookup"><span data-stu-id="82775-108">That way you can build models without affecting the performance of other services.</span></span>  
  
 <span data-ttu-id="82775-109">Tenga en cuenta que el servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que se usa para minería de datos no tiene por qué estar en el mismo servidor que los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="82775-109">Note that the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that you use for data mining does not need to be on the same server as your source data.</span></span>  
  
 <span data-ttu-id="82775-110">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="82775-110">**Server name**</span></span>  
 <span data-ttu-id="82775-111">Escriba el nombre del servidor que contiene la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que usará para la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-111">Type the name of the server that contains the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you will use for data mining.</span></span>  
  
 <span data-ttu-id="82775-112">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="82775-112">**Authentication**</span></span>  
 <span data-ttu-id="82775-113">Especifique los métodos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="82775-113">Specify the authentication methods.</span></span> <span data-ttu-id="82775-114">La autenticación de Windows es necesaria para las conexiones con [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a menos que el administrador haya configurado el acceso al servidor mediante HTTPPump.</span><span class="sxs-lookup"><span data-stu-id="82775-114">Windows Authentication is required for connections to [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], unless your administrator has configured access to the server via the HTTPPump.</span></span>  
  
##  <a name="step-2-allow-temporary-models"></a><a name="bkmk_step2"></a><span data-ttu-id="82775-115">Paso 2: permitir modelos temporales</span><span class="sxs-lookup"><span data-stu-id="82775-115">Step 2: Allow Temporary Models</span></span>  
 <span data-ttu-id="82775-116">Para poder usar los complementos, se debe cambiar una propiedad del servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para permitir la creación de modelos de minería de datos temporales.</span><span class="sxs-lookup"><span data-stu-id="82775-116">Before you can use the add-ins, an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server property must be changed to permit the creation of temporary mining models.</span></span>  
  
 <span data-ttu-id="82775-117">Los modelos de minería de datos temporales también se denominan *modelos de sesión*.</span><span class="sxs-lookup"><span data-stu-id="82775-117">Temporary mining models are also called *session models*.</span></span> <span data-ttu-id="82775-118">Esto se debe a que los modelos sólo se almacenan mientras la sesión actual permanece abierta.</span><span class="sxs-lookup"><span data-stu-id="82775-118">This is because the models are stored only as long as your current session is open.</span></span> <span data-ttu-id="82775-119">Al cerrar la conexión con el servidor, se da por finalizada la sesión y se eliminan todos los modelos que se usaron durante la misma.</span><span class="sxs-lookup"><span data-stu-id="82775-119">When you close your connection to the server, the session is ended and any models used during the session are deleted.</span></span>  
  
 <span data-ttu-id="82775-120">El uso de modelos de minería de datos de sesión no afecta al espacio de almacenamiento del servidor, pero la sobrecarga asociada a la creación de los modelos de minería de datos puede afectar a su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="82775-120">The use of session mining models does not affect storage space on the server, but the overhead involved in creating data mining models may affect the performance of the server.</span></span>  
  
 <span data-ttu-id="82775-121">El asistente detecta primero la configuración en el servidor que especificó.</span><span class="sxs-lookup"><span data-stu-id="82775-121">The wizard first detects the settings on the server that you specified.</span></span> <span data-ttu-id="82775-122">Si el servidor ya permite modelos de minería de datos temporales, puede hacer clic en **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="82775-122">If the server already allows temporary mining models, you can click **Next** to continue.</span></span> <span data-ttu-id="82775-123">El asistente también proporciona instrucciones sobre cómo habilitar modelos de minería de datos temporales en el servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] especificado o cómo realizar una solicitud al administrador de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82775-123">The wizard also provides instructions for how to enable temporary mining models on the specified [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, or how to make a request to your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] administrator.</span></span>  
  
##  <a name="step-3-create-database-for-add-in-users"></a><a name="bkmk_step3"></a><span data-ttu-id="82775-124">Paso 3: crear una base de datos para los usuarios del complemento</span><span class="sxs-lookup"><span data-stu-id="82775-124">Step 3: Create Database for Add-in Users</span></span>  
 <span data-ttu-id="82775-125">En esta página del asistente para instalación y configuración, puede crear una base de datos nueva dedicada a la minería de datos o puede seleccionar una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] existente.</span><span class="sxs-lookup"><span data-stu-id="82775-125">On this page of the setup and configuration wizard, you can create a new database that is dedicated to data mining, or select an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="82775-126">Minería de datos requiere una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que se ejecute en modo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="82775-126">Data mining requires an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that is running in multidimensional mode.</span></span> <span data-ttu-id="82775-127">El modo tabular no admite minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-127">Tabular mode does not support data mining.</span></span>  
  
 <span data-ttu-id="82775-128">Se recomienda crear una base de datos independiente dedicada a la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-128">We recommend that you create a separate database dedicated to data mining.</span></span> <span data-ttu-id="82775-129">Esto le permite probar con los modelos de minería de datos sin afectar a otros objetos de la solución.</span><span class="sxs-lookup"><span data-stu-id="82775-129">This lets you experiment with data mining models without affecting other solution objects.</span></span>  
  
 <span data-ttu-id="82775-130">Si elige una base de datos existente en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], tenga en cuenta que se pueden sobrescribir modelos existentes si usa los complementos para crear un modelo y ya existe un modelo con dicho nombre.</span><span class="sxs-lookup"><span data-stu-id="82775-130">If you choose an existing database on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], note that it is possible to overwrite existing models if you use the add-ins to create a model and a model of that name already exists.</span></span>  
  
 <span data-ttu-id="82775-131">**Create new database**</span><span class="sxs-lookup"><span data-stu-id="82775-131">**Create new database**</span></span>  
 <span data-ttu-id="82775-132">Seleccione esta opción para crear una base de datos nueva en el servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="82775-132">Select this option to create a new database on the selected server.</span></span> <span data-ttu-id="82775-133">Una base de datos de minería de datos almacenará los orígenes de datos, las estructuras de minería de datos y los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-133">A data mining database will store your data sources, mining structures, and mining models.</span></span>  
  
 <span data-ttu-id="82775-134">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="82775-134">**Database name**</span></span>  
 <span data-ttu-id="82775-135">Escriba el nombre de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-135">Type the name of the new database.</span></span> <span data-ttu-id="82775-136">Si el nombre no se está usando todavía, se creará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="82775-136">If the name is not already in use, it will be created for you.</span></span>  
  
 <span data-ttu-id="82775-137">**Usar base de datos existente**</span><span class="sxs-lookup"><span data-stu-id="82775-137">**Use existing database**</span></span>  
 <span data-ttu-id="82775-138">Seleccione esta opción para usar una base de datos existente de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82775-138">Select this option to use an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="82775-139">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="82775-139">**Database**</span></span>  
 <span data-ttu-id="82775-140">Si eligió la opción para usar una base de datos existente, debe seleccionar el nombre de la base de datos en la lista.</span><span class="sxs-lookup"><span data-stu-id="82775-140">If you chose the option to use an existing database, you must select the database name from the list.</span></span>  
  
##  <a name="step-4-give-add-in-users-appropriate-permissions"></a><a name="bkmk_step4"></a><span data-ttu-id="82775-141">Paso 4: conceder los permisos adecuados a los usuarios del complemento</span><span class="sxs-lookup"><span data-stu-id="82775-141">Step 4: Give Add-in Users Appropriate Permissions</span></span>  
 <span data-ttu-id="82775-142">Debe asegurarse de que tanto usted como los demás usuarios que van a emplear los complementos tienen los permisos necesarios para examinar, editar, procesar o crear estructuras y modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-142">You must ensure that you (and any other users of the add-ins) have the necessary permissions to browse, edit, process, or create data mining structures and models.</span></span>  
  
 <span data-ttu-id="82775-143">De forma predeterminada, para usar los complementos se requiere la autenticación integrada de Windows.</span><span class="sxs-lookup"><span data-stu-id="82775-143">By default, integrated Windows Authentication is required to use the add-ins.</span></span>  
  
 <span data-ttu-id="82775-144">**Conceder a los usuarios del complemento permisos de administración de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="82775-144">**Give add-in users database administration permissions**</span></span>  
 <span data-ttu-id="82775-145">Seleccione esta opción para conceder a los usuarios de la lista acceso administrativo a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-145">Select this option to give the listed users administrative access to the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82775-146">Estos permisos solo se aplican a la base de datos que aparece en el cuadro Nombre de la **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="82775-146">These permissions apply only to the database listed in the **Database name** box.</span></span>  
  
 <span data-ttu-id="82775-147">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="82775-147">**Database name**</span></span>  
 <span data-ttu-id="82775-148">Muestra el nombre de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="82775-148">Displays the name of the selected database.</span></span>  
  
 <span data-ttu-id="82775-149">**Especifique los usuarios o grupos que va a agregar**</span><span class="sxs-lookup"><span data-stu-id="82775-149">**Specify users or groups to add**</span></span>  
 <span data-ttu-id="82775-150">Seleccione los nombres de inicio de sesión que tendrán acceso a la base de datos usada para la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="82775-150">Select the logins that will have access to the database used for data mining.</span></span>  
  
 <span data-ttu-id="82775-151">**Add**</span><span class="sxs-lookup"><span data-stu-id="82775-151">**Add**</span></span>  
 <span data-ttu-id="82775-152">Haga clic en esta opción para abrir un cuadro de diálogo y agregar usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="82775-152">Click to open a dialog box and add users or groups.</span></span>  
  
 <span data-ttu-id="82775-153">**Remove**</span><span class="sxs-lookup"><span data-stu-id="82775-153">**Remove**</span></span>  
 <span data-ttu-id="82775-154">Haga clic en esta opción para quitar al usuario o al grupo seleccionado de la lista de usuarios con permisos de administración.</span><span class="sxs-lookup"><span data-stu-id="82775-154">Click to remove the selected user or group from the list of users with administration permissions.</span></span>  
  
  
