---
title: Referencia de interfaz de usuario del Asistente para la instalación de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.deploymentwizard.confirminstallation.f1
- sql12.dts.deploymentwizard.deploydtspackages.f1
- sql12.dts.deploymentwizard.selectinstfolder.f1
- sql12.dts.deploymentwizard.specifytargetsqlserver.f1
- sql12.dts.deploymentwizard.welcome.f1
- sql12.dts.deploymentwizard.finish.f1
- sql12.dts.deploymentwizard.configurepackages.f1
- sql12.dts.deploymentwizard.packagevalidation.f1
helpviewer_keywords:
- Package Installer Wizard
ms.assetid: 6fca44d9-5001-4644-bcf3-c2d10a674b97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c15b423c66891e799f7f8dcd27682036dce6d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744758"
---
# <a name="package-installation-wizard-ui-reference"></a><span data-ttu-id="76528-102">Referencia de la interfaz de usuario del Asistente para la instalación de paquetes</span><span class="sxs-lookup"><span data-stu-id="76528-102">Package Installation Wizard UI Reference</span></span>
  <span data-ttu-id="76528-103">Use el **Asistente para la instalación de paquetes** para implementar un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , incluidos los paquetes y los distintos archivos que contienen, así como las dependencias del paquete.</span><span class="sxs-lookup"><span data-stu-id="76528-103">Use the **Package Installation Wizard** to deploy a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, including the packages and miscellaneous files it contains and any package dependencies.</span></span>  
  
 <span data-ttu-id="76528-104">Antes de implementar paquetes, puede crear configuraciones y después implementarlas con los paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-104">Before you deploy packages, you can create configurations and then deploy them with the packages.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="76528-105">utiliza configuraciones para actualizar dinámicamente las propiedades de los paquetes y los objetos de paquete en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76528-105">uses configurations to dynamically update properties of packages and package objects at run time.</span></span> <span data-ttu-id="76528-106">Por ejemplo, la cadena de conexión de una conexión OLE DB puede establecerse dinámicamente en tiempo de ejecución proporcionando una configuración que asigne un valor a la propiedad que contiene la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="76528-106">For example, the connection string of an OLE DB connection can be set dynamically at run time by providing a configuration that maps a value to the property that contains the connection string.</span></span>  
  
 <span data-ttu-id="76528-107">No se puede ejecutar el Asistente para la instalación de paquetes hasta que se genere un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y se cree una utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="76528-107">You cannot run the Package Installation Wizard until you build an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and create a deployment utility.</span></span> <span data-ttu-id="76528-108">Para más información, consulte [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="76528-108">For more information, see [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="76528-109">En las siguientes secciones se describen las páginas del asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-109">The following sections describe pages of the wizard.</span></span>  
  
## <a name="welcome-to-the-package-installation-wizard-page"></a><span data-ttu-id="76528-110">Asistente para la instalación de paquetes (página principal)</span><span class="sxs-lookup"><span data-stu-id="76528-110">Welcome to the Package Installation Wizard Page</span></span>  
 <span data-ttu-id="76528-111">Use el **Asistente para la instalación de paquetes** para implementar un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para el que ha creado una utilidad de implementación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-111">Use the **Package Installation Wizard** to deploy an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you built a package deployment utility.</span></span>  
  
 <span data-ttu-id="76528-112">**No volver a mostrar esta página**</span><span class="sxs-lookup"><span data-stu-id="76528-112">**Do not show this starting page again**</span></span>  
 <span data-ttu-id="76528-113">Seleccione para omitir la página de inicio al volver a ejecutar el asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-113">Select to skip the starting page when you run the wizard again.</span></span>  
  
 <span data-ttu-id="76528-114">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="76528-114">**Next**</span></span>  
 <span data-ttu-id="76528-115">Va a la siguiente página del asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-115">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="76528-116">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="76528-116">**Finish**</span></span>  
 <span data-ttu-id="76528-117">Salte a la página Salir del Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-117">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="76528-118">Puede usar esta opción tras volver a las páginas anteriores del asistente para revisar las elecciones o si ha especificado todas las opciones requeridas.</span><span class="sxs-lookup"><span data-stu-id="76528-118">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="configure-packages-page"></a><span data-ttu-id="76528-119">Página Configurar paquetes</span><span class="sxs-lookup"><span data-stu-id="76528-119">Configure Packages Page</span></span>  
 <span data-ttu-id="76528-120">Utilice la página **Configurar paquetes** para modificar la configuración de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-120">Use the **Configure Packages** page to edit package configurations.</span></span>  
  
### <a name="options"></a><span data-ttu-id="76528-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="76528-121">Options</span></span>  
 <span data-ttu-id="76528-122">**Archivo de configuración**</span><span class="sxs-lookup"><span data-stu-id="76528-122">**Configuration file**</span></span>  
 <span data-ttu-id="76528-123">Para modificar el contenido de un archivo de configuración, seleccione el archivo en la lista.</span><span class="sxs-lookup"><span data-stu-id="76528-123">Edit the contents of a configuration file by selecting the file from the list.</span></span>  
  
 <span data-ttu-id="76528-124">**Temas relacionados:** [Crear configuraciones de paquetes](../../2014/integration-services/create-package-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="76528-124">**Related Topics:** [Create Package Configurations](../../2014/integration-services/create-package-configurations.md)</span></span>  
  
 <span data-ttu-id="76528-125">**Path**</span><span class="sxs-lookup"><span data-stu-id="76528-125">**Path**</span></span>  
 <span data-ttu-id="76528-126">Muestra la ruta de acceso de la propiedad que debe configurarse.</span><span class="sxs-lookup"><span data-stu-id="76528-126">View the path of the property to be configured.</span></span>  
  
 <span data-ttu-id="76528-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="76528-127">**Type**</span></span>  
 <span data-ttu-id="76528-128">Muestra el tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="76528-128">View the data type of the property.</span></span>  
  
 <span data-ttu-id="76528-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="76528-129">**Value**</span></span>  
 <span data-ttu-id="76528-130">Especifique el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="76528-130">Specify the value of the configuration.</span></span>  
  
 <span data-ttu-id="76528-131">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="76528-131">**Next**</span></span>  
 <span data-ttu-id="76528-132">Va a la siguiente página del asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-132">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="76528-133">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="76528-133">**Finish**</span></span>  
 <span data-ttu-id="76528-134">Salte a la página Salir del Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-134">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="76528-135">Puede usar esta opción tras volver a las páginas anteriores del asistente para revisar las elecciones o si ha especificado todas las opciones requeridas.</span><span class="sxs-lookup"><span data-stu-id="76528-135">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="confirm-installation-page"></a><span data-ttu-id="76528-136">Página Confirmar la instalación</span><span class="sxs-lookup"><span data-stu-id="76528-136">Confirm Installation Page</span></span>  
 <span data-ttu-id="76528-137">Use la página **Confirmar la instalación** para iniciar la instalación de paquetes, ver el estado y ver la información que utilizará el asistente para instalar los archivos del proyecto especificado.</span><span class="sxs-lookup"><span data-stu-id="76528-137">Use the **Confirm Installation** page to start the installation of packages, to view the status, and to view the information that the wizard will use to install files from the specified project.</span></span>  
  
 <span data-ttu-id="76528-138">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="76528-138">**Next**</span></span>  
 <span data-ttu-id="76528-139">Instale los paquetes y sus dependencias y vaya a la siguiente página del asistente una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="76528-139">Install the packages and their dependencies and go to the next wizard page when installation is completed.</span></span>  
  
 <span data-ttu-id="76528-140">**Estado**</span><span class="sxs-lookup"><span data-stu-id="76528-140">**Status**</span></span>  
 <span data-ttu-id="76528-141">Muestra el progreso de la instalación del paquete.</span><span class="sxs-lookup"><span data-stu-id="76528-141">Shows the progress of the package installation.</span></span>  
  
 <span data-ttu-id="76528-142">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="76528-142">**Finish**</span></span>  
 <span data-ttu-id="76528-143">Vaya a la página Salir del Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-143">Go to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="76528-144">Utilice esta opción si ha comprobado las páginas del asistente para revisar sus elecciones y ha especificado todas las opciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="76528-144">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all the required options.</span></span>  
  
## <a name="deploy-ssis-packages-page"></a><span data-ttu-id="76528-145">Página Implementar paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="76528-145">Deploy SSIS Packages Page</span></span>  
 <span data-ttu-id="76528-146">Use la página **Implementar paquetes SSIS** para especificar dónde instalar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="76528-146">Use the **Deploy SSIS Packages** page to specify where to install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="76528-147">Opciones</span><span class="sxs-lookup"><span data-stu-id="76528-147">Options</span></span>  
 <span data-ttu-id="76528-148">**Implementación en el sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="76528-148">**File system deployment**</span></span>  
 <span data-ttu-id="76528-149">Implementa paquetes y dependencias en una carpeta determinada del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="76528-149">Deploy packages and dependencies in a specified folder in the file system.</span></span>  
  
 <span data-ttu-id="76528-150">**Implementación en SQL Server**</span><span class="sxs-lookup"><span data-stu-id="76528-150">**SQL Server deployment**</span></span>  
 <span data-ttu-id="76528-151">Implementa paquetes y dependencias en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76528-151">Deploy packages and dependencies in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="76528-152">Use esta opción si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] comparte paquetes entre servidores.</span><span class="sxs-lookup"><span data-stu-id="76528-152">Use this option if [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shares packages between servers.</span></span> <span data-ttu-id="76528-153">Las dependencias de paquetes se instalan en la carpeta especificada del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="76528-153">Any package dependencies are installed in the specified folder in the file system.</span></span>  
  
 <span data-ttu-id="76528-154">**Validar los paquetes después de la instalación**</span><span class="sxs-lookup"><span data-stu-id="76528-154">**Validate packages after installation**</span></span>  
 <span data-ttu-id="76528-155">Indica si se van a validar los paquetes después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="76528-155">Indicate whether to validate packages after installation.</span></span>  
  
 <span data-ttu-id="76528-156">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="76528-156">**Next**</span></span>  
 <span data-ttu-id="76528-157">Va a la siguiente página del asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-157">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="76528-158">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="76528-158">**Finish**</span></span>  
 <span data-ttu-id="76528-159">Salte a la página Salir del Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-159">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="76528-160">Puede usar esta opción tras volver a las páginas anteriores del asistente para revisar las elecciones o si ha especificado todas las opciones requeridas.</span><span class="sxs-lookup"><span data-stu-id="76528-160">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="packages-validation-page"></a><span data-ttu-id="76528-161">Página Validación de paquetes</span><span class="sxs-lookup"><span data-stu-id="76528-161">Packages Validation Page</span></span>  
 <span data-ttu-id="76528-162">Use la página **Validación de paquetes** para ver el progreso y los resultados de la validación del paquete.</span><span class="sxs-lookup"><span data-stu-id="76528-162">Use the **Packages Validation** page to view the progress and results of the package validation.</span></span>  
  
 <span data-ttu-id="76528-163">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="76528-163">**Next**</span></span>  
 <span data-ttu-id="76528-164">Va a la siguiente página del asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-164">Go to the next page in the wizard.</span></span>  
  
## <a name="select-installation-folder-page"></a><span data-ttu-id="76528-165">Página Seleccionar la carpeta de instalación</span><span class="sxs-lookup"><span data-stu-id="76528-165">Select Installation Folder Page</span></span>  
 <span data-ttu-id="76528-166">Use la página **Seleccionar la carpeta de instalación** para especificar la carpeta del sistema de archivos en la que desea instalar los paquetes y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="76528-166">Use the **Select Installation Folder** page to specify the file system folder in which to install the packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="76528-167">Opciones</span><span class="sxs-lookup"><span data-stu-id="76528-167">Options</span></span>  
 <span data-ttu-id="76528-168">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="76528-168">**Folder**</span></span>  
 <span data-ttu-id="76528-169">Permite especificar la ruta y la carpeta en la que se desea copiar el paquete y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="76528-169">Specify the path and folder in which to copy the package and its dependencies.</span></span>  
  
 <span data-ttu-id="76528-170">**Browse**</span><span class="sxs-lookup"><span data-stu-id="76528-170">**Browse**</span></span>  
 <span data-ttu-id="76528-171">Permite ir a la carpeta de destino mediante el cuadro de diálogo **Buscar carpeta** .</span><span class="sxs-lookup"><span data-stu-id="76528-171">Browse to the target folder by using the **Browse For Folder** dialog box.</span></span>  
  
 <span data-ttu-id="76528-172">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="76528-172">**Next**</span></span>  
 <span data-ttu-id="76528-173">Va a la siguiente página del asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-173">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="76528-174">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="76528-174">**Finish**</span></span>  
 <span data-ttu-id="76528-175">Salte a la página Salir del Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-175">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="76528-176">Puede usar esta opción tras volver a las páginas anteriores del asistente para revisar las elecciones o si ha especificado todas las opciones requeridas.</span><span class="sxs-lookup"><span data-stu-id="76528-176">Use this option if you have backtracked through the wizard pages to revise your choices and if have specified all of the required options.</span></span>  
  
## <a name="specify-target-sql-server-page"></a><span data-ttu-id="76528-177">Página Especificar el SQL Server de destino</span><span class="sxs-lookup"><span data-stu-id="76528-177">Specify Target SQL Server Page</span></span>  
 <span data-ttu-id="76528-178">Use la página **Especificar el SQL Server de destino** para especificar las opciones de implementación del paquete en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76528-178">Use the **Specify Target SQL Server** page to specify options for deploying the package to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="options"></a><span data-ttu-id="76528-179">Opciones</span><span class="sxs-lookup"><span data-stu-id="76528-179">Options</span></span>  
 <span data-ttu-id="76528-180">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="76528-180">**Server name**</span></span>  
 <span data-ttu-id="76528-181">Especifique el nombre del servidor en el que se implementarán los paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-181">Specify the name of the server to deploy the packages to.</span></span>  
  
 <span data-ttu-id="76528-182">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="76528-182">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="76528-183">Permite especificar si se usará la autenticación de Windows al iniciar una sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="76528-183">Specify whether to use Windows Authentication to log on to the server.</span></span> <span data-ttu-id="76528-184">Para obtener una mayor seguridad, es recomendable utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="76528-184">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="76528-185">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="76528-185">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="76528-186">Permite especificar si el paquete debe usar la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] al iniciar una sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="76528-186">Specify whether the package should use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to log on to the server.</span></span> <span data-ttu-id="76528-187">Si usa la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , debe proporcionar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="76528-187">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="76528-188">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="76528-188">**User name**</span></span>  
 <span data-ttu-id="76528-189">Especifique un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="76528-189">Specify a user name.</span></span>  
  
 <span data-ttu-id="76528-190">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="76528-190">**Password**</span></span>  
 <span data-ttu-id="76528-191">Especifique una contraseña.</span><span class="sxs-lookup"><span data-stu-id="76528-191">Specify a password.</span></span>  
  
 <span data-ttu-id="76528-192">**Ruta de acceso del paquete**</span><span class="sxs-lookup"><span data-stu-id="76528-192">**Package path**</span></span>  
 <span data-ttu-id="76528-193">Especifique el nombre de la carpeta lógica o escribe "/" para la carpeta predeterminada.</span><span class="sxs-lookup"><span data-stu-id="76528-193">Specify the name of the logical folder, or enter "/" for the default folder.</span></span>  
  
 <span data-ttu-id="76528-194">Para seleccionar la carpeta en el cuadro de diálogo **Paquete SSIS** , haga clic en el botón para examinar (…). Sin embargo, el cuadro de diálogo no proporciona medios para seleccionar la carpeta predeterminada.</span><span class="sxs-lookup"><span data-stu-id="76528-194">To select the folder in the **SSIS Package** dialog box, click browse (...). However, the dialog box does not provide a means to select the default folder.</span></span> <span data-ttu-id="76528-195">Si desea utilizar la carpeta predeterminada, tiene que escribir "/" en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="76528-195">If you want to use the default folder, you have to enter "/" in the text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76528-196">Si no escribe una ruta de acceso del paquete válida, aparece el mensaje de error siguiente: "Uno o más argumentos no son válidos".</span><span class="sxs-lookup"><span data-stu-id="76528-196">If you do not enter a valid package path, the following error message appears: "One or more arguments are invalid."</span></span>  
  
 <span data-ttu-id="76528-197">**Basar el cifrado en el almacenamiento del servidor**</span><span class="sxs-lookup"><span data-stu-id="76528-197">**Rely on server storage for encryption**</span></span>  
 <span data-ttu-id="76528-198">Seleccione estas características de seguridad del [!INCLUDE[ssDE](../includes/ssde-md.md)] para contribuir a proteger los paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-198">Select to use security features of the [!INCLUDE[ssDE](../includes/ssde-md.md)] to help secure the packages.</span></span>  
  
 <span data-ttu-id="76528-199">**Siguiente**</span><span class="sxs-lookup"><span data-stu-id="76528-199">**Next**</span></span>  
 <span data-ttu-id="76528-200">Va a la siguiente página del asistente.</span><span class="sxs-lookup"><span data-stu-id="76528-200">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="76528-201">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="76528-201">**Finish**</span></span>  
 <span data-ttu-id="76528-202">Salte a la página Salir del Asistente para la instalación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="76528-202">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="76528-203">Puede usar esta opción tras volver a las páginas anteriores del asistente para revisar las elecciones o si ha especificado todas las opciones requeridas.</span><span class="sxs-lookup"><span data-stu-id="76528-203">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="finish-the-package-installation-page"></a><span data-ttu-id="76528-204">Página Salir del Asistente para la instalación de paquetes</span><span class="sxs-lookup"><span data-stu-id="76528-204">Finish the Package Installation Page</span></span>  
 <span data-ttu-id="76528-205">Use la página **Salir del Asistente para la instalación de paquetes** para ver un resumen de los resultados de la instalación del paquete.</span><span class="sxs-lookup"><span data-stu-id="76528-205">Use the **Finish the Package Installation Wizard** page to view a summary of the package installation results.</span></span> <span data-ttu-id="76528-206">Esta página muestra información, como el nombre del proyecto implementado de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , los paquetes instalados, los archivos de configuración y la ubicación de la instalación.</span><span class="sxs-lookup"><span data-stu-id="76528-206">This page provides details such as the name of the deployed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, the packages that were installed, the configuration files, and the installation location.</span></span>  
  
 <span data-ttu-id="76528-207">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="76528-207">**Finish**</span></span>  
 <span data-ttu-id="76528-208">Para salir del asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="76528-208">Exit the wizard by clicking **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76528-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76528-209">See Also</span></span>  
 [<span data-ttu-id="76528-210">Implementación de paquetes &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="76528-210">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
