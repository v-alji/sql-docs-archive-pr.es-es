---
title: Implementar una base de datos mediante una DAC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbdeployment.settings.f1
- sql12.swb.dbdeployment.progress.f1
- sql12.swb.dbdeployment.summary.f1
- sql12.swb.dbdeployment.results.f1
- sql12.swb.dbdeployment.welcome.f1
helpviewer_keywords:
- deploy database wizard
- database deploy [SQL Server]
ms.assetid: 08c506e8-4ba0-4a19-a066-6e6a5c420539
author: stevestein
ms.author: sstein
ms.openlocfilehash: f753cfaf44e51b5bd3ffb939e38e2a300acb9703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749340"
---
# <a name="deploy-a-database-by-using-a-dac"></a><span data-ttu-id="9ca6e-102">Implementar una base de datos mediante una DAC</span><span class="sxs-lookup"><span data-stu-id="9ca6e-102">Deploy a Database By Using a DAC</span></span>
  <span data-ttu-id="9ca6e-103">Use el asistente para **implementar una base de datos en SQL Azure** para implementar una base de datos entre una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y un servidor de [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] o entre dos servidores de [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca6e-103">Use the **Deploy a Database to SQL Azure** Wizard to deploy a database between an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and a [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] server, or between two [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]servers.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeBegin"></a> <span data-ttu-id="9ca6e-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9ca6e-104">Before You Begin</span></span>  
 <span data-ttu-id="9ca6e-105">El asistente emplea un archivo de almacenamiento BACPAC de aplicación de capa de datos (DAC) para implementar los datos y las definiciones de los objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-105">The wizard uses a Data-tier Application (DAC) BACPAC archive file to deploy both the data and the definitions of database objects.</span></span> <span data-ttu-id="9ca6e-106">Realiza una operación de exportación de DAC de la base de datos de origen y una importación de DAC al destino.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-106">It performs a DAC export operation from the source database, and a DAC import to the destination.</span></span>  
  
###  <a name="database-options-and-settings"></a><a name="DBOptSettings"></a> <span data-ttu-id="9ca6e-107">Opciones y configuración de bases de datos</span><span class="sxs-lookup"><span data-stu-id="9ca6e-107">Database Options and Settings</span></span>  
 <span data-ttu-id="9ca6e-108">De forma predeterminada, la base de datos que se crea durante la implementación tendrá la configuración predeterminada de la instrucción CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-108">By default, the database created during the deployment will have the default settings from the CREATE DATABASE statement.</span></span> <span data-ttu-id="9ca6e-109">La excepción es que la intercalación de base de datos y el nivel de compatibilidad se establecen en los valores de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-109">The exception is that the database collation and compatibility level are set to the values from the source database.</span></span>  
  
 <span data-ttu-id="9ca6e-110">Algunas opciones de base de datos, como TRUSTWORTHY, DB_CHAINING y HONOR_BROKER_PRIORITY, no se pueden ajustar como parte del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-110">Database options, such as TRUSTWORTHY, DB_CHAINING and HONOR_BROKER_PRIORITY, cannot be adjusted as part of the deployment process.</span></span> <span data-ttu-id="9ca6e-111">Las propiedades físicas, como el número de grupos de archivos o el número y tamaño de los archivos no se pueden modificar en el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-111">Physical properties, such as the number of filegroups, or the numbers and sizes of files cannot be altered as part of the deployment process.</span></span> <span data-ttu-id="9ca6e-112">Una vez se haya completado la implementación, podrá usar la instrucción ALTER DATABASE, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell para personalizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-112">After the deployment completes, you can use the ALTER DATABASE statement, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell to tailor the database.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="9ca6e-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9ca6e-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9ca6e-114">El asistente **Implementar la base de datos** admite implementar una base de datos:</span><span class="sxs-lookup"><span data-stu-id="9ca6e-114">The **Deploy Database** wizard supports deploying a database:</span></span>  
  
-   <span data-ttu-id="9ca6e-115">Desde una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] en [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca6e-115">From an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span>  
  
-   <span data-ttu-id="9ca6e-116">Desde [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] en una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca6e-116">From [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="9ca6e-117">Entre dos servidores de [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-117">Between two [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] servers.</span></span>  
  
 <span data-ttu-id="9ca6e-118">El asistente no admite la implementación de bases de datos entre dos instancias del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca6e-118">The wizard does not support deploying databases between two instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="9ca6e-119">Para poder usar el asistente, una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] debe ejecutar [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o posterior.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-119">An instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later to work with the wizard.</span></span> <span data-ttu-id="9ca6e-120">Si una base de datos de una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] contiene objetos no admitidos en [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], no puede usar el asistente para implementar la base de datos en [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca6e-120">If a database on an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] contains objects not supported on [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], you cannot use the wizard to deploy the database to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="9ca6e-121">Si una base de datos de [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] contiene objetos no admitidos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], no puede usar el asistente para implementar la base de datos en instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca6e-121">If a database on [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] contains objects not supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you cannot use the wizard to deploy the database to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ca6e-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9ca6e-122">Security</span></span>  
 <span data-ttu-id="9ca6e-123">Para mejorar la seguridad, los inicios de sesión de Autenticación de SQL Server están almacenados en un archivo BACPAC de DAC sin contraseña.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-123">To improve security, SQL Server Authentication logins are stored in a DAC BACPAC file without a password.</span></span> <span data-ttu-id="9ca6e-124">Cuando se importa el archivo BACPAC, el inicio de sesión se crea como un inicio de sesión deshabilitado con una contraseña generada.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-124">When the BACPAC is imported, the login is created as a disabled login with a generated password.</span></span> <span data-ttu-id="9ca6e-125">Para habilitar los inicios de sesión, use un inicio de sesión que disponga del permiso ALTER ANY LOGIN y emplee ALTER LOGIN para habilitar el inicio de sesión y asignar una nueva contraseña que pueda comunicar al usuario.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-125">To enable the logins, log in using a login that has ALTER ANY LOGIN permission and use ALTER LOGIN to enable the login and assign a new password that can be communicated to the user.</span></span> <span data-ttu-id="9ca6e-126">Esto no se necesita para los inicios de sesión de Autenticación de Windows, porque SQL Server no administra sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-126">This is not needed for Windows Authentication logins because their passwords are not managed by SQL Server.</span></span>  
  
#### <a name="permissions"></a><span data-ttu-id="9ca6e-127">Permisos</span><span class="sxs-lookup"><span data-stu-id="9ca6e-127">Permissions</span></span>  
 <span data-ttu-id="9ca6e-128">El asistente necesita permisos de exportación de DAC en la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-128">The wizard requires DAC export permissions on the source database.</span></span> <span data-ttu-id="9ca6e-129">El inicio de sesión necesita al menos permisos ALTER ANY LOGIN y VIEW DEFINITION en el ámbito de la base de datos, así como permisos SELECT en **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-129">The login requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="9ca6e-130">La exportación de una DAC la pueden realizar los miembros del rol fijo de servidor securityadmin que sean también miembros del rol fijo de base de datos database_owner en la base de datos de la que se exporta la DAC.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-130">Exporting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is exported.</span></span> <span data-ttu-id="9ca6e-131">Los miembros del rol fijo de servidor sysadmin o de la cuenta de administrador del sistema de SQL Server integrada denominada **sa** también pueden exportar una DAC.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-131">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also export a DAC.</span></span>  
  
 <span data-ttu-id="9ca6e-132">El asistente necesita permisos de importación de DAC en la instancia o el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-132">The wizard requires DAC import permissions on the destination instance or server.</span></span> <span data-ttu-id="9ca6e-133">El inicio de sesión debe ser miembro de los roles fijos de servidor **sysadmin** o **serveradmin** , o del rol fijo de servidor **dbcreator** y disponer de permisos ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-133">The login must be a member of the **sysadmin** or **serveradmin** fixed server roles, or in the **dbcreator** fixed server role and have ALTER ANY LOGIN permissions.</span></span> <span data-ttu-id="9ca6e-134">La cuenta de administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integrada denominada **sa** también puede importar una DAC.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-134">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also import a DAC.</span></span> <span data-ttu-id="9ca6e-135">La importación de una DAC con inicios de sesión en [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiere la pertenencia a los roles loginmanager o serveradmin.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-135">Importing a DAC with logins to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the loginmanager or serveradmin roles.</span></span> <span data-ttu-id="9ca6e-136">La importación de una DAC sin inicios de sesión en [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiere la pertenencia a los roles dbmanager o serveradmin.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-136">Importing a DAC without logins to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the dbmanager or serveradmin roles.</span></span>  
  
##  <a name="using-the-deploy-database-wizard"></a><a name="UsingDeployDACWizard"></a> <span data-ttu-id="9ca6e-137">Usar el Asistente para implementar bases de datos</span><span class="sxs-lookup"><span data-stu-id="9ca6e-137">Using the Deploy Database Wizard</span></span>  
 <span data-ttu-id="9ca6e-138">**Para migrar una base de datos mediante el Asistente para implementar bases de datos**</span><span class="sxs-lookup"><span data-stu-id="9ca6e-138">**To migrate a database using the Deploy Database Wizard**</span></span>  
  
1.  <span data-ttu-id="9ca6e-139">Conéctese a la ubicación de la base de datos que desee implementar.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-139">Connect to the location of the database you want to deploy.</span></span> <span data-ttu-id="9ca6e-140">Puede especificar una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] o un servidor de [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-140">You can specify either an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] or a [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] server.</span></span>  
  
2.  <span data-ttu-id="9ca6e-141">En el **Explorador de objetos**, expanda el nodo de la instancia que contiene la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-141">In **Object Explorer**, expand the node for the instance that has the database.</span></span>  
  
3.  <span data-ttu-id="9ca6e-142">Expanda el nodo **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-142">Expand the **Databases** node.</span></span>  
  
4.  <span data-ttu-id="9ca6e-143">Haga clic con el botón derecho en la base de datos que quiera implementar, seleccione **Tareas** y, después, seleccione **Implementar base de datos en SQL Azure...** .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-143">Right click the database you want to deploy, select **Tasks**, and then select **Deploy Database to SQL Azure...**</span></span>  
  
5.  <span data-ttu-id="9ca6e-144">Complete los cuadros de diálogo del asistente:</span><span class="sxs-lookup"><span data-stu-id="9ca6e-144">Complete the Wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="9ca6e-145">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="9ca6e-145">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="9ca6e-146">Configuración de implementación</span><span class="sxs-lookup"><span data-stu-id="9ca6e-146">Deployment Settings</span></span>](#Deployment_settings)  
  
    -   [<span data-ttu-id="9ca6e-147">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="9ca6e-147">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="9ca6e-148">Resultados</span><span class="sxs-lookup"><span data-stu-id="9ca6e-148">Results</span></span>](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="9ca6e-149">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="9ca6e-149">Introduction Page</span></span>  
 <span data-ttu-id="9ca6e-150">Esta página describe los pasos del asistente **Implementar la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-150">This page describes the steps for the **Deploy Database** Wizard.</span></span>  
  
 <span data-ttu-id="9ca6e-151">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="9ca6e-151">**Options**</span></span>  
  
-   <span data-ttu-id="9ca6e-152">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="9ca6e-152">**Do not show this page again.**</span></span> <span data-ttu-id="9ca6e-153">- Active la casilla para que la página Introducción deje de mostrarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-153">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="9ca6e-154">**Siguiente** : continúa a la página **Configuración de implementación** .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-154">**Next** - Proceeds to the **Deployment Settings** page.</span></span>  
  
-   <span data-ttu-id="9ca6e-155">**Cancelar** : cancela la operación y cierra el asistente.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-155">**Cancel** - Cancels the operation and closes the Wizard.</span></span>  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a><span data-ttu-id="9ca6e-156">Página configuración de implementación</span><span class="sxs-lookup"><span data-stu-id="9ca6e-156">Deployment Settings Page</span></span>  
 <span data-ttu-id="9ca6e-157">Use esta página para especificar el servidor de destino y proporcionar detalles sobre la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-157">Use this page to specify the destination server and to provide details about your new database.</span></span>  
  
 <span data-ttu-id="9ca6e-158">**Host local:**</span><span class="sxs-lookup"><span data-stu-id="9ca6e-158">**Local host:**</span></span>  
  
-   <span data-ttu-id="9ca6e-159">**Conexión de servidor**: especifique los detalles de conexión del servidor y haga clic en **Conectar** para comprobar la conexión.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-159">**Server connection** - Specify server connection details and then click **Connect** to verify the connection.</span></span>  
  
-   <span data-ttu-id="9ca6e-160">**Nombre de la nueva base de datos**: especifique un nombre para la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-160">**New database name** - Specify a name for the new database.</span></span>  
  
 <span data-ttu-id="9ca6e-161">**[!INCLUDE[ssSDS](../../includes/sssds-md.md)]configuración de base de datos:**</span><span class="sxs-lookup"><span data-stu-id="9ca6e-161">**[!INCLUDE[ssSDS](../../includes/sssds-md.md)] database settings:**</span></span>  
  
-   <span data-ttu-id="9ca6e-162">\*\* [!INCLUDE[ssSDS](../../includes/sssds-md.md)] edición\*\* : seleccione la edición de [!INCLUDE[ssSDS](../../includes/sssds-md.md)] en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-162">**[!INCLUDE[ssSDS](../../includes/sssds-md.md)] edition** - Select the edition of [!INCLUDE[ssSDS](../../includes/sssds-md.md)] from the drop-down menu.</span></span>  
  
-   <span data-ttu-id="9ca6e-163">**Tamaño máximo de la base de datos**: seleccione el tamaño máximo de la base de datos en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-163">**Maximum database size** - Select the maximum database size from the drop-down menu.</span></span>  
  
 <span data-ttu-id="9ca6e-164">**Otros valores:**</span><span class="sxs-lookup"><span data-stu-id="9ca6e-164">**Other settings:**</span></span>  
  
-   <span data-ttu-id="9ca6e-165">Especifique un directorio local para el archivo temporal, que es el archivo de almacenamiento BACPAC.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-165">Specify a local directory for the temporary file, which is the BACPAC archive file.</span></span> <span data-ttu-id="9ca6e-166">Tenga en cuenta que el archivo se creará en la ubicación especificada y permanecerá en ella una vez completada la operación.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-166">Note that the file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="9ca6e-167">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="9ca6e-167">Summary Page</span></span>  
 <span data-ttu-id="9ca6e-168">Esta página se utiliza para revisar los valores de origen y de destino especificados de la operación.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-168">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="9ca6e-169">Para completar la operación de implementación con los valores especificados, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-169">To complete the deploy operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="9ca6e-170">Para cancelar la operación de implementación y salir del asistente, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-170">To cancel the deploy operation and exit the Wizard, click **Cancel**.</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="9ca6e-171">Página Progreso</span><span class="sxs-lookup"><span data-stu-id="9ca6e-171">Progress Page</span></span>  
 <span data-ttu-id="9ca6e-172">En esta página se muestra una barra de progreso que indica el estado de la operación.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-172">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="9ca6e-173">Para ver el estado detallado, haga clic en la opción **Ver detalles** .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-173">To view detailed status, click the **View details** option.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="9ca6e-174">Página resultados</span><span class="sxs-lookup"><span data-stu-id="9ca6e-174">Results Page</span></span>  
 <span data-ttu-id="9ca6e-175">En esta página se notifica la corrección o el error de la operación de implementación, mostrando los resultados de cada acción.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-175">This page reports the success or failure of the deploy operation, showing the results of each action.</span></span> <span data-ttu-id="9ca6e-176">Cualquier acción que encontrara un error tendrá un vínculo en la columna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="9ca6e-176">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="9ca6e-177">Haga clic en el vínculo para ver un informe del error para esa acción.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-177">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="9ca6e-178">Haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-178">Click **Finish** to close the Wizard.</span></span>  
  
## <a name="using-a-net-framework-application"></a><span data-ttu-id="9ca6e-179">Mediante una aplicación de .Net Framework</span><span class="sxs-lookup"><span data-stu-id="9ca6e-179">Using a .Net Framework Application</span></span>  
 <span data-ttu-id="9ca6e-180">**Para implementar una base de datos por medio de los métodos Export() e Import() de DacStore en una aplicación de .NET Framework.**</span><span class="sxs-lookup"><span data-stu-id="9ca6e-180">**To deploy a database using the DacStoreExport() and Import() methods in a .Net Framework application.**</span></span>  
  
 <span data-ttu-id="9ca6e-181">Para obtener un ejemplo de código, descargue la aplicación de ejemplo de DAC en [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575).</span><span class="sxs-lookup"><span data-stu-id="9ca6e-181">To view a code example, download the DAC sample application on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span></span>  
  
1.  <span data-ttu-id="9ca6e-182">Cree un objeto SMO Server y establézcalo en la instancia o el servidor que contenga la base de datos que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-182">Create a SMO Server object and set it to the instance or server that contains the database to be deployed.</span></span>  
  
2.  <span data-ttu-id="9ca6e-183">Abra un objeto `ServerConnection` y conéctese a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-183">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="9ca6e-184">Use el método `Export` del tipo `Microsoft.SqlServer.Management.Dac.DacStore` para exportar la base de datos a un archivo BACPAC.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-184">Use the `Export` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to export the database to a BACPAC file.</span></span> <span data-ttu-id="9ca6e-185">Especifique el nombre de la base de datos que se exportará y la ruta de acceso a la carpeta donde se va a guardar el archivo BACPAC.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-185">Specify the name of the database to be exported, and the path to the folder where the BACPAC file is to be placed.</span></span>  
  
4.  <span data-ttu-id="9ca6e-186">Cree un objeto SMO Server y establézcalo en la instancia o el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-186">Create a SMO Server object and set it to the destination instance or server.</span></span>  
  
5.  <span data-ttu-id="9ca6e-187">Abra un objeto `ServerConnection` y conéctese a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-187">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
6.  <span data-ttu-id="9ca6e-188">Use el método de `Import` del tipo `Microsoft.SqlServer.Management.Dac.DacStore` para importar el archivo BACPAC.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-188">Use the `Import` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to import the BACPAC.</span></span> <span data-ttu-id="9ca6e-189">Especifique el archivo BACPAC creado por la exportación.</span><span class="sxs-lookup"><span data-stu-id="9ca6e-189">Specify the BACPAC file created by the export.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca6e-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ca6e-190">See Also</span></span>  
 <span data-ttu-id="9ca6e-191">[Aplicaciones de capa de datos](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="9ca6e-191">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="9ca6e-192">[Exportar una aplicación de capa de datos](export-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="9ca6e-192">[Export a Data-tier Application](export-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="9ca6e-193">Importar un archivo de bacpac para crear una nueva base de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="9ca6e-193">Import a BACPAC File to Create a New User Database</span></span>](import-a-bacpac-file-to-create-a-new-user-database.md)  
  
  