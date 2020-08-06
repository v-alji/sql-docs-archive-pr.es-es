---
title: Asistente para conversión de Integration Services proyecto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.migrationwizard.f1
ms.assetid: a192b094-4d0f-4c21-b911-460ec844a49f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c47dc8ed1d0485a62128be732cc34de1dca35740
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673167"
---
# <a name="integration-services-project-conversion-wizard"></a><span data-ttu-id="d7877-102">Asistente para conversión de proyectos de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d7877-102">Integration Services Project Conversion Wizard</span></span>
  <span data-ttu-id="d7877-103">El **Asistente para conversión de proyectos de Integration Services** convierte un proyecto al modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="d7877-103">The **Integration Services Project Conversion Wizard** converts a project to the project deployment model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7877-104">Si el proyecto contiene uno o más orígenes de datos, se quitan los orígenes de datos cuando se completa la conversión del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-104">If the project contains one or more datasources, the datasources are removed when the project conversion is completed.</span></span> <span data-ttu-id="d7877-105">Para crear una conexión a un origen de datos que se pueden compartir los paquetes en el proyecto, agregue un administrador de conexiones en el nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-105">To create a connection to a data source that can be shared by the packages in the project, add a connection manager at the project level.</span></span> <span data-ttu-id="d7877-106">Para obtener más información, consulte [agregar, eliminar o compartir un administrador de conexiones en un paquete](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="d7877-106">For more information, see [Add, Delete, or Share a Connection Manager in a Package](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span></span>  
  
 <span data-ttu-id="d7877-107">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="d7877-107">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="d7877-108">Abrir el Asistente para conversión de proyectos de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d7877-108">Open the Integration Services Project Conversion Wizard</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="d7877-109">Establecer las opciones de la página Buscar paquetes</span><span class="sxs-lookup"><span data-stu-id="d7877-109">Set Options on the Locate Packages Page</span></span>](#locate)  
  
-   [<span data-ttu-id="d7877-110">Establecer las opciones de la página Seleccionar paquete</span><span class="sxs-lookup"><span data-stu-id="d7877-110">Set Options on the Select Packages Page</span></span>](#selectPackages)  
  
-   [<span data-ttu-id="d7877-111">Establecer las opciones de la página Seleccionar destino</span><span class="sxs-lookup"><span data-stu-id="d7877-111">Set Options on the Select Destination Page</span></span>](#destination)  
  
-   [<span data-ttu-id="d7877-112">Establecer las opciones de la página Especificar propiedades del proyecto</span><span class="sxs-lookup"><span data-stu-id="d7877-112">Set Options on the Specify Project Properties Page</span></span>](#projectProperties)  
  
-   [<span data-ttu-id="d7877-113">Establecer las opciones de la página Actualizar la tarea Ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="d7877-113">Set Options on the Update Execute Package Task Page</span></span>](#executePackage)  
  
-   [<span data-ttu-id="d7877-114">Establecer las opciones de la página Seleccionar configuraciones</span><span class="sxs-lookup"><span data-stu-id="d7877-114">Set Options on the Select Configurations Page</span></span>](#configurations)  
  
-   [<span data-ttu-id="d7877-115">Establecer las opciones de la página Crear parámetros</span><span class="sxs-lookup"><span data-stu-id="d7877-115">Set Options on the Create Parameters Page</span></span>](#createParameters)  
  
-   [<span data-ttu-id="d7877-116">Establecer las opciones de la página Configurar parámetros</span><span class="sxs-lookup"><span data-stu-id="d7877-116">Set Options on the Configure Parameters Page</span></span>](#configureParameters)  
  
-   [<span data-ttu-id="d7877-117">Establecer las opciones en la página Revisar</span><span class="sxs-lookup"><span data-stu-id="d7877-117">Set the Options on the Review page</span></span>](#review)  
  
-   [<span data-ttu-id="d7877-118">Establecer las opciones en Realizar conversión</span><span class="sxs-lookup"><span data-stu-id="d7877-118">Set the Options on the Perform Conversion</span></span>](#conversion)  
  
##  <a name="open-the-integration-services-project-conversion-wizard"></a><a name="open_dialog"></a><span data-ttu-id="d7877-119">Abrir el Asistente para la conversión de Integration Services Project</span><span class="sxs-lookup"><span data-stu-id="d7877-119">Open the Integration Services Project Conversion Wizard</span></span>  
 <span data-ttu-id="d7877-120">Para abrir el asistente **Conversión de proyecto de Integration Services** , realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7877-120">Do one of the following to open the **Integration Services Project Conversion** Wizard.</span></span>  
  
-   <span data-ttu-id="d7877-121">Abra el proyecto en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]y, en el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Convertir al modelo de implementación de proyectos**.</span><span class="sxs-lookup"><span data-stu-id="d7877-121">Open the project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], and then in Solution Explorer, right-click the project and click **Convert to Project Deployment Model**.</span></span>  
  
-   <span data-ttu-id="d7877-122">En el Explorador de objetos de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], haga clic con el botón derecho en el nodo **Proyectos** y seleccione **Importar paquetes**.</span><span class="sxs-lookup"><span data-stu-id="d7877-122">From Object Explorer in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], right-click the **Projects** node and select **Import Packages**.</span></span>  
  
 <span data-ttu-id="d7877-123">Dependiendo de si ejecuta el **Asistente para la conversión de proyectos de Integration Services** desde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] o desde [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], el asistente realiza tareas de conversión diferentes.</span><span class="sxs-lookup"><span data-stu-id="d7877-123">Depending on whether you run the **Integration Services Project Conversion Wizard** from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] or from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], the wizard performs different conversion tasks.</span></span> <span data-ttu-id="d7877-124">Para más información, consulte [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7877-124">For more information, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
##  <a name="set-options-on-the-locate-packages-page"></a><a name="locate"></a><span data-ttu-id="d7877-125">Establecer las opciones de la página Buscar paquetes</span><span class="sxs-lookup"><span data-stu-id="d7877-125">Set Options on the Locate Packages Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7877-126"> La página **Buscar paquetes** está disponible solamente cuando ejecuta el asistente desde [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7877-126">The **Locate Packages** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="d7877-127">La siguiente opción aparece en la página al seleccionar **Sistema de archivos** en la lista desplegable **Origen** .</span><span class="sxs-lookup"><span data-stu-id="d7877-127">The following option displays on the page when you select **File system** in the **Source** drop-down list.</span></span> <span data-ttu-id="d7877-128">Seleccione esta opción si el paquete reside en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="d7877-128">Select this option when the package is resides in the file system.</span></span>  
  
 <span data-ttu-id="d7877-129">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="d7877-129">**Folder**</span></span>  
 <span data-ttu-id="d7877-130">Escriba la ruta de acceso al paquete, o bien haga clic en **Examinar**para abrir la ubicación del paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-130">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="d7877-131">En la página se muestran las opciones siguientes al seleccionar **Almacén de paquetes SSIS** en la lista desplegable **Origen**.</span><span class="sxs-lookup"><span data-stu-id="d7877-131">The following options display on the page when you select **SSIS Package Store** in the **Source** drop-down list.</span></span> <span data-ttu-id="d7877-132">Para más información sobre el almacén de paquetes, vea [Administración de paquetes &#40;servicio SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="d7877-132">For more information about the package store, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="d7877-133">**Server**</span><span class="sxs-lookup"><span data-stu-id="d7877-133">**Server**</span></span>  
 <span data-ttu-id="d7877-134">Especifique el nombre del servidor o seleccione el servidor.</span><span class="sxs-lookup"><span data-stu-id="d7877-134">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="d7877-135">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="d7877-135">**Folder**</span></span>  
 <span data-ttu-id="d7877-136">Escriba la ruta de acceso al paquete, o bien haga clic en **Examinar**para abrir la ubicación del paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-136">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="d7877-137">En la página se muestran las opciones siguientes al seleccionar **Microsoft SQL Server** en la lista desplegable **Origen** .</span><span class="sxs-lookup"><span data-stu-id="d7877-137">The following options display on the page when you select **Microsoft SQL Server** in the **Source** drop-down list.</span></span> <span data-ttu-id="d7877-138">Seleccione esta opción si el paquete reside en Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7877-138">Select this option when the package resides in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d7877-139">**Server**</span><span class="sxs-lookup"><span data-stu-id="d7877-139">**Server**</span></span>  
 <span data-ttu-id="d7877-140">Especifique el nombre del servidor o seleccione el servidor.</span><span class="sxs-lookup"><span data-stu-id="d7877-140">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="d7877-141">**Usar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="d7877-141">**Use Windows authentication**</span></span>  
 <span data-ttu-id="d7877-142">El modo de autenticación de Microsoft Windows permite que un usuario pueda conectarse a través de una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="d7877-142">Microsoft Windows Authentication mode allows a user to connect through a Windows user account.</span></span> <span data-ttu-id="d7877-143">Si utiliza la autenticación de Windows, no será necesario que proporcione un nombre de usuario o una contraseña.</span><span class="sxs-lookup"><span data-stu-id="d7877-143">If you use Windows Authentication, you do not need to provide a user name or password.</span></span>  
  
 <span data-ttu-id="d7877-144">**Usar autenticación SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d7877-144">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="d7877-145">Cuando un usuario se conecta con un nombre de inicio de sesión y una contraseña especificados desde una conexión que no es de confianza, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] autentica la conexión (para hacerlo, comprueba si se ha configurado una cuenta de inicio de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y si la contraseña especificada coincide con la almacenada anteriormente).</span><span class="sxs-lookup"><span data-stu-id="d7877-145">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authenticates the connection by checking to see if a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="d7877-146">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no tiene configurada una cuenta de inicio de sesión, la autenticación no se realizará correctamente y el usuario recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d7877-146">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="d7877-147">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="d7877-147">**User name**</span></span>  
 <span data-ttu-id="d7877-148">Especifique un nombre de usuario cuando utilice la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7877-148">Specify a user name when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d7877-149">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d7877-149">**Password**</span></span>  
 <span data-ttu-id="d7877-150">Especifique la contraseña cuando use la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7877-150">Provide the password when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d7877-151">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="d7877-151">**Folder**</span></span>  
 <span data-ttu-id="d7877-152">Escriba la ruta de acceso al paquete, o bien haga clic en **Examinar**para abrir la ubicación del paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-152">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
##  <a name="set-options-on-the-select-packages-page"></a><a name="selectPackages"></a><span data-ttu-id="d7877-153">Establecer opciones en la página seleccionar paquetes</span><span class="sxs-lookup"><span data-stu-id="d7877-153">Set Options on the Select Packages Page</span></span>  
 <span data-ttu-id="d7877-154">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="d7877-154">**Package Name**</span></span>  
 <span data-ttu-id="d7877-155">Muestra el archivo de paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-155">Lists the package file.</span></span>  
  
 <span data-ttu-id="d7877-156">**Estado**</span><span class="sxs-lookup"><span data-stu-id="d7877-156">**Status**</span></span>  
 <span data-ttu-id="d7877-157">Indica si un paquete está listo para convertir el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="d7877-157">Indicates whether a package is ready to convert to the project deployment model.</span></span>  
  
 <span data-ttu-id="d7877-158">**Message**</span><span class="sxs-lookup"><span data-stu-id="d7877-158">**Message**</span></span>  
 <span data-ttu-id="d7877-159">Muestra un mensaje asociado al paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-159">Displays a message associated with the package.</span></span>  
  
 <span data-ttu-id="d7877-160">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d7877-160">**Password**</span></span>  
 <span data-ttu-id="d7877-161">Muestra una contraseña asociada al paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-161">Displays a password associated with the package.</span></span> <span data-ttu-id="d7877-162">Se oculta el texto de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="d7877-162">The password text is hidden.</span></span>  
  
 <span data-ttu-id="d7877-163">**Aplicar a la selección**</span><span class="sxs-lookup"><span data-stu-id="d7877-163">**Apply to selection**</span></span>  
 <span data-ttu-id="d7877-164">Haga clic en el cuadro de texto **Contraseña** para aplicar la contraseña a los paquetes seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d7877-164">Click to apply the password in the **Password** text box, to the selected package or packages.</span></span>  
  
 <span data-ttu-id="d7877-165">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="d7877-165">**Refresh**</span></span>  
 <span data-ttu-id="d7877-166">Actualiza la lista de paquetes.</span><span class="sxs-lookup"><span data-stu-id="d7877-166">Refreshes the list of packages.</span></span>  
  
##  <a name="set-options-on-the-select-destination-page"></a><a name="destination"></a><span data-ttu-id="d7877-167">Establecer opciones en la página Seleccionar destino</span><span class="sxs-lookup"><span data-stu-id="d7877-167">Set Options on the Select Destination Page</span></span>  
 <span data-ttu-id="d7877-168">En esta página, especifique el nombre y la ruta de un nuevo archivo de implementación del proyecto (.ispac) o seleccione un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="d7877-168">On this page, specify the name and path for a new project deployment file (.ispac) or select an existing file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7877-169"> La página **Seleccionar destino** está disponible solamente cuando ejecuta el asistente desde [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7877-169">The **Select Destination** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="d7877-170">**Ruta de acceso de salida**</span><span class="sxs-lookup"><span data-stu-id="d7877-170">**Output path**</span></span>  
 <span data-ttu-id="d7877-171">Escriba la ruta de acceso al archivo de implementación, o bien haga clic en **Examinar**para abrir la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="d7877-171">Type the path for the deployment file or navigate to the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="d7877-172">**Nombre del proyecto**</span><span class="sxs-lookup"><span data-stu-id="d7877-172">**Project name**</span></span>  
 <span data-ttu-id="d7877-173">Escriba el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-173">Type the project name.</span></span>  
  
 <span data-ttu-id="d7877-174">**Nivel de protección**</span><span class="sxs-lookup"><span data-stu-id="d7877-174">**Protection level**</span></span>  
 <span data-ttu-id="d7877-175">Seleccione el nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="d7877-175">Select the protection level.</span></span> <span data-ttu-id="d7877-176">Para más información, consulte [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="d7877-176">For more information, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="d7877-177">**Descripción del proyecto**</span><span class="sxs-lookup"><span data-stu-id="d7877-177">**Project description**</span></span>  
 <span data-ttu-id="d7877-178">Escriba una descripción opcional para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-178">Type an optional description for the project.</span></span>  
  
##  <a name="set-options-on-the-specify-project-properties-page"></a><a name="projectProperties"></a><span data-ttu-id="d7877-179">Establecer las opciones de la página especificar propiedades del proyecto</span><span class="sxs-lookup"><span data-stu-id="d7877-179">Set Options on the Specify Project Properties Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7877-180"> La página **Especificar propiedades del proyecto** solo está disponible cuando se ejecuta el asistente desde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7877-180">The **Specify Project Properties** page is available only when you run the wizard from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="d7877-181">**Nombre del proyecto**</span><span class="sxs-lookup"><span data-stu-id="d7877-181">**Project name**</span></span>  
 <span data-ttu-id="d7877-182">Muestra el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-182">Lists the project name.</span></span>  
  
 <span data-ttu-id="d7877-183">**Nivel de protección**</span><span class="sxs-lookup"><span data-stu-id="d7877-183">**Protection level**</span></span>  
 <span data-ttu-id="d7877-184">Seleccione un nivel de protección para los paquetes que se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-184">Select a protection level for the packages contained in the project.</span></span> <span data-ttu-id="d7877-185">Para obtener más información acerca de los niveles de protección, vea [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="d7877-185">For more information about protection levels, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="d7877-186">**Descripción del proyecto**</span><span class="sxs-lookup"><span data-stu-id="d7877-186">**Project description**</span></span>  
 <span data-ttu-id="d7877-187">Escriba una descripción del proyecto opcional.</span><span class="sxs-lookup"><span data-stu-id="d7877-187">Type an optional project description.</span></span>  
  
##  <a name="set-options-on-the-update-execute-package-task-page"></a><a name="executePackage"></a><span data-ttu-id="d7877-188">Establecer las opciones de la página actualizar la tarea ejecutar paquete</span><span class="sxs-lookup"><span data-stu-id="d7877-188">Set Options on the Update Execute Package Task Page</span></span>  
 <span data-ttu-id="d7877-189">Actualice las tareas Ejecutar paquete que se incluyen en los paquetes para usar una referencia basada en proyectos.</span><span class="sxs-lookup"><span data-stu-id="d7877-189">Update Execute Package Tasks contain in the packages, to use a project-based reference.</span></span> <span data-ttu-id="d7877-190">Para obtener más información, vea [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="d7877-190">For more information, see [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span></span>  
  
 <span data-ttu-id="d7877-191">**Paquete primario**</span><span class="sxs-lookup"><span data-stu-id="d7877-191">**Parent Package**</span></span>  
 <span data-ttu-id="d7877-192">Muestra el nombre del paquete que ejecuta el paquete secundario mediante la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-192">Lists the name of the package that executes the child package using the Execute Package task.</span></span>  
  
 <span data-ttu-id="d7877-193">**Nombre de tarea**</span><span class="sxs-lookup"><span data-stu-id="d7877-193">**Task name**</span></span>  
 <span data-ttu-id="d7877-194">Muestra el nombre de la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-194">Lists the name of the Execute Package task.</span></span>  
  
 <span data-ttu-id="d7877-195">**Referencia original**</span><span class="sxs-lookup"><span data-stu-id="d7877-195">**Original reference**</span></span>  
 <span data-ttu-id="d7877-196">Muestra la ruta de acceso actual del paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="d7877-196">Lists the current path of the child package.</span></span>  
  
 <span data-ttu-id="d7877-197">**Asignar referencia**</span><span class="sxs-lookup"><span data-stu-id="d7877-197">**Assign reference**</span></span>  
 <span data-ttu-id="d7877-198">Seleccione un paquete secundario que esté almacenado en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-198">Select a child package stored in the project.</span></span>  
  
##  <a name="set-options-on-the-select-configurations-page"></a><a name="configurations"></a><span data-ttu-id="d7877-199">Establecer las opciones de la página seleccionar configuraciones</span><span class="sxs-lookup"><span data-stu-id="d7877-199">Set Options on the Select Configurations Page</span></span>  
 <span data-ttu-id="d7877-200">Seleccione las configuraciones del paquete que desea reemplazar por parámetros.</span><span class="sxs-lookup"><span data-stu-id="d7877-200">Select the package configurations that you want to replace with parameters.</span></span>  
  
 <span data-ttu-id="d7877-201">**Package**</span><span class="sxs-lookup"><span data-stu-id="d7877-201">**Package**</span></span>  
 <span data-ttu-id="d7877-202">Muestra el archivo de paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-202">Lists the package file.</span></span>  
  
 <span data-ttu-id="d7877-203">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d7877-203">**Type**</span></span>  
 <span data-ttu-id="d7877-204">Muestra el tipo de configuración como, por ejemplo, un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="d7877-204">Lists the type of configuration, such as an XML configuration file.</span></span>  
  
 <span data-ttu-id="d7877-205">**Cadena de configuración**</span><span class="sxs-lookup"><span data-stu-id="d7877-205">**Configuration String**</span></span>  
 <span data-ttu-id="d7877-206">Muestra la ruta de acceso del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d7877-206">Lists the path of the configuration file.</span></span>  
  
 <span data-ttu-id="d7877-207">**Estado**</span><span class="sxs-lookup"><span data-stu-id="d7877-207">**Status**</span></span>  
 <span data-ttu-id="d7877-208">Muestra un mensaje de estado para la configuración.</span><span class="sxs-lookup"><span data-stu-id="d7877-208">Displays a status message for the configuration.</span></span> <span data-ttu-id="d7877-209">Haga clic en el mensaje para ver el mensaje de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d7877-209">Click the message to view the entire message text.</span></span>  
  
 <span data-ttu-id="d7877-210">**Agregar configuraciones**</span><span class="sxs-lookup"><span data-stu-id="d7877-210">**Add Configurations**</span></span>  
 <span data-ttu-id="d7877-211">Agregue configuraciones de paquetes que se incluyan en otros proyectos a la lista de valores de configuración disponibles que desee reemplazar con parámetros.</span><span class="sxs-lookup"><span data-stu-id="d7877-211">Add package configurations contained in other projects to the list of available configurations that you want to replace with parameters.</span></span> <span data-ttu-id="d7877-212">Puede seleccionar las configuraciones almacenadas en un sistema de archivos o en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7877-212">You can select configurations stored in a file system or stored in SQL Server.</span></span>  
  
 <span data-ttu-id="d7877-213">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="d7877-213">**Refresh**</span></span>  
 <span data-ttu-id="d7877-214">Haga clic para actualizar la lista de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="d7877-214">Click to refresh the list of configurations.</span></span>  
  
 <span data-ttu-id="d7877-215">**Quite las configuraciones de todos los paquetes después de la conversión**</span><span class="sxs-lookup"><span data-stu-id="d7877-215">**Remove configurations from all packages after conversion**</span></span>  
 <span data-ttu-id="d7877-216">Es recomendable que quite todas las configuraciones del proyecto seleccionando esta opción.</span><span class="sxs-lookup"><span data-stu-id="d7877-216">It is recommended that you remove all configurations from the project by selecting this option.</span></span>  
  
 <span data-ttu-id="d7877-217">Si no selecciona esta opción, solo se quitan las configuraciones que haya elegido reemplazar por parámetros.</span><span class="sxs-lookup"><span data-stu-id="d7877-217">If you don't select this option, only the configurations that you selected to replace with parameters are removed.</span></span>  
  
##  <a name="set-options-on-the-create-parameters-page"></a><a name="createParameters"></a><span data-ttu-id="d7877-218">Establecer las opciones de la página crear parámetros</span><span class="sxs-lookup"><span data-stu-id="d7877-218">Set Options on the Create Parameters Page</span></span>  
 <span data-ttu-id="d7877-219">Seleccione el nombre y el ámbito de parámetro para cada propiedad de configuración.</span><span class="sxs-lookup"><span data-stu-id="d7877-219">Select the parameter name and scope for each configuration property.</span></span>  
  
 <span data-ttu-id="d7877-220">**Package**</span><span class="sxs-lookup"><span data-stu-id="d7877-220">**Package**</span></span>  
 <span data-ttu-id="d7877-221">Muestra el archivo de paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-221">Lists the package file.</span></span>  
  
 <span data-ttu-id="d7877-222">**Nombre de parámetro**</span><span class="sxs-lookup"><span data-stu-id="d7877-222">**Parameter Name**</span></span>  
 <span data-ttu-id="d7877-223">Muestra el nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-223">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="d7877-224">**Ámbito**</span><span class="sxs-lookup"><span data-stu-id="d7877-224">**Scope**</span></span>  
 <span data-ttu-id="d7877-225">Seleccione el ámbito del parámetro, un paquete o un proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-225">Select the scope of the parameter, either package or project.</span></span>  
  
##  <a name="set-options-on-the-configure-parameters-page"></a><a name="configureParameters"></a><span data-ttu-id="d7877-226">Establecer las opciones de la página Configurar parámetros</span><span class="sxs-lookup"><span data-stu-id="d7877-226">Set Options on the Configure Parameters Page</span></span>  
 <span data-ttu-id="d7877-227">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d7877-227">**Name**</span></span>  
 <span data-ttu-id="d7877-228">Muestra el nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-228">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="d7877-229">**Ámbito**</span><span class="sxs-lookup"><span data-stu-id="d7877-229">**Scope**</span></span>  
 <span data-ttu-id="d7877-230">Muestra el ámbito del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-230">Lists the scope of the parameter.</span></span>  
  
 <span data-ttu-id="d7877-231">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d7877-231">**Value**</span></span>  
 <span data-ttu-id="d7877-232">Muestra el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-232">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="d7877-233">Haga clic en los puntos suspensivos junto al campo del valor para configurar las propiedades de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-233">Click the ellipsis button next to the value field to configure the parameter properties.</span></span>  
  
 <span data-ttu-id="d7877-234">En el cuadro de diálogo **Establecer detalles de parámetro** , puede modificar el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-234">In the **Set Parameter Details** dialog box, you can edit the parameter value.</span></span> <span data-ttu-id="d7877-235">También puede especificar si el valor del parámetro debe proporcionarse al ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="d7877-235">You can also specify whether the parameter value must be provided when you run the package.</span></span>  
  
 <span data-ttu-id="d7877-236">Puede modificar el valor en la página **Parámetros** del cuadro de diálogo **Configurar** de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]; para ello, haga clic en el botón Examinar situado junto al parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-236">You can modify value in the **Parameters** page of the **Configure** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], by clicking the browse button next to the parameter.</span></span> <span data-ttu-id="d7877-237">Aparece el cuadro de diálogo **Establecer valor de parámetro** .</span><span class="sxs-lookup"><span data-stu-id="d7877-237">The **Set Parameter Value** dialog box appears.</span></span>  
  
 <span data-ttu-id="d7877-238">El cuadro de diálogo **Establecer detalles de parámetros** también muestra el tipo de datos de parámetro y el origen del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7877-238">The **Set Parameter Details** dialog box also lists the data type of the parameter value and the origin of the parameter.</span></span>  
  
##  <a name="set-the-options-on-the-review-page"></a><a name="review"></a><span data-ttu-id="d7877-239">Establecer las opciones de la página revisar</span><span class="sxs-lookup"><span data-stu-id="d7877-239">Set the Options on the Review page</span></span>  
 <span data-ttu-id="d7877-240">Use la página **Revisar** para confirmar las opciones que ha seleccionado para la conversión del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-240">Use the **Review** page to confirm the options that you've selected for the conversion of the project.</span></span>  
  
 <span data-ttu-id="d7877-241">**Anterior**</span><span class="sxs-lookup"><span data-stu-id="d7877-241">**Previous**</span></span>  
 <span data-ttu-id="d7877-242">Haga clic aquí para cambiar una opción.</span><span class="sxs-lookup"><span data-stu-id="d7877-242">Click to change an option.</span></span>  
  
 <span data-ttu-id="d7877-243">**Convertir**</span><span class="sxs-lookup"><span data-stu-id="d7877-243">**Convert**</span></span>  
 <span data-ttu-id="d7877-244">Haga clic en esta opción para convertir el proyecto al modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="d7877-244">Click to convert the project to the project deployment model.</span></span>  
  
##  <a name="set-the-options-on-the-perform-conversion"></a><a name="conversion"></a><span data-ttu-id="d7877-245">Establecer las opciones en realizar conversión</span><span class="sxs-lookup"><span data-stu-id="d7877-245">Set the Options on the Perform Conversion</span></span>  
 <span data-ttu-id="d7877-246">La página Realizar conversión muestra el estado de la conversión del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7877-246">The Perform Conversion page shows status of the project conversion.</span></span>  
  
 <span data-ttu-id="d7877-247">**Acción**</span><span class="sxs-lookup"><span data-stu-id="d7877-247">**Action**</span></span>  
 <span data-ttu-id="d7877-248">Enumera un paso concreto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="d7877-248">Lists a specific conversion step.</span></span>  
  
 <span data-ttu-id="d7877-249">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d7877-249">**Result**</span></span>  
 <span data-ttu-id="d7877-250">Muestra el estado de cada paso de conversión.</span><span class="sxs-lookup"><span data-stu-id="d7877-250">Lists the status of each conversion step.</span></span> <span data-ttu-id="d7877-251">Haga clic en el mensaje de estado para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d7877-251">Click the status message for more information.</span></span>  
  
 <span data-ttu-id="d7877-252">La conversión de proyectos no se guarda hasta que el proyecto se guarde en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7877-252">The project conversion is not saved until the project is saved in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="d7877-253">**Guardar informe**</span><span class="sxs-lookup"><span data-stu-id="d7877-253">**Save report**</span></span>  
 <span data-ttu-id="d7877-254">Haga clic en esta opción para guardar un resumen de la conversión del proyecto en un archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="d7877-254">Click to save a summary of the project conversion in an .xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7877-255">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7877-255">See Also</span></span>  
 [<span data-ttu-id="d7877-256">Implementación de paquetes en el servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d7877-256">Deploy Projects to Integration Services Server</span></span>](../../2014/integration-services/deploy-projects-to-integration-services-server.md)  
  
  
