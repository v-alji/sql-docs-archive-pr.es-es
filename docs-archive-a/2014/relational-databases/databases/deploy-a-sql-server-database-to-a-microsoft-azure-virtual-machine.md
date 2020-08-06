---
title: Implementación de una base de datos de SQL Server en una máquina virtual de Microsoft Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.deploymentwizard.deploymentsettings.f1
- sql12.swb.deploymentwizard.progress.f1
- sql11.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.f1
- sql12.swb.deploymentwizard.azuresignin.f1
- sql11.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.azuresignin.f1
- sql12.swb.deploymentwizard.f1
- sql12.swb.sqlvmdialog.f1
- sql11.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.results.f1
- sql11.swb.deploymentwizard.progress.f1
- sql12.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.sourcesettings.f1
- sql12.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.sourcesettings.f1
- sql11.swb.deploymentwizard.results.f1
- sql12.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.deploymentsettings.f1
helpviewer_keywords:
- Deploy a database
- Deploy to Azure VM
- Migrate to Azure
- Azure virtual machine
- Migrate to Azure VM
- Migrate to the cloud
- SQL Server Management Studio
- SSMS
- Deploy database wizard
- Deploy a SQL Server database to Azure
- Azure VM
ms.assetid: 5e82e66a-262e-4d4f-aa89-39cb62696d06
author: stevestein
ms.author: sstein
ms.openlocfilehash: d48c06db038a775811cba6705fbaf1d97a960f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748125"
---
# <a name="deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine"></a><span data-ttu-id="4daeb-102">Implementar una base de datos de SQL Server en una máquina virtual de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="4daeb-102">Deploy a SQL Server Database to a Microsoft Azure Virtual Machine</span></span>
  <span data-ttu-id="4daeb-103">Use el Asistente para **implementar una base de datos de SQL Server en una máquina** virtual de Azure para implementar una base de datos desde una instancia del en [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una máquina virtual (VM) de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-103">Use the **Deploy a SQL Server Database to an Azure VM** wizard to deploy a database from an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in an Azure Virtual Machine (VM).</span></span> <span data-ttu-id="4daeb-104">El asistente emplea una operación de copia de seguridad completa de la base de datos, por lo que siempre copia todo el esquema de la base de datos y los datos de una base de datos de usuario de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4daeb-104">The wizard utilizes a full database backup operation, so it always copies the complete database schema and the data from a SQL Server user database.</span></span> <span data-ttu-id="4daeb-105">El asistente también realiza toda la configuración de Azure VM, por lo que no se requiere ninguna configuración previa de la VM.</span><span class="sxs-lookup"><span data-stu-id="4daeb-105">The wizard also does all of the Azure VM configuration for you, so no pre-configuration of the VM is required.</span></span>  
  
 <span data-ttu-id="4daeb-106">No puede usar el asistente para las copias de seguridad diferenciales porque no sobrescribirá una base de datos existente que tenga el mismo nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4daeb-106">You cannot use the wizard for differential backups because the wizard will not overwrite an existing database that has the same database name.</span></span> <span data-ttu-id="4daeb-107">Para reemplazar una base de datos existente en la VM, debe quitar primero la base de datos existente o cambiar el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4daeb-107">To replace an existing database on the VM, you must first drop the existing database or change the database name.</span></span> <span data-ttu-id="4daeb-108">Si hay un conflicto de nombres entre el nombre de la base de datos para una operación de implementación en ejecución y una base de datos existente en la VM, el asistente sugerirá un nombre de base de datos anexado para la base de datos en ejecución de manera que pueda completar la operación.</span><span class="sxs-lookup"><span data-stu-id="4daeb-108">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
##  <a name="before-you-begin"></a><a name="before_you_begin"></a> <span data-ttu-id="4daeb-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4daeb-109">Before You Begin</span></span>  
 <span data-ttu-id="4daeb-110">Para completar este asistente, debe poder proporcionar la siguiente información y tener esta configuración:</span><span class="sxs-lookup"><span data-stu-id="4daeb-110">To complete this wizard, you must be able to provide the following information and have these configuration settings in place:</span></span>  
  
-   <span data-ttu-id="4daeb-111">Los detalles de cuenta de Microsoft asociados con la suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-111">The Microsoft account details associated with your Azure subscription.</span></span>  
  
-   <span data-ttu-id="4daeb-112">Su perfil de publicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-112">Your Azure publishing profile.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="4daeb-113">SQL Server admite actualmente la versión 2.0 del perfil de publicación.</span><span class="sxs-lookup"><span data-stu-id="4daeb-113">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="4daeb-114">Para descargar la versión compatible del perfil de publicación, vea [Descargar perfil de publicación 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="4daeb-114">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
-   <span data-ttu-id="4daeb-115">El certificado de administración cargado en la suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-115">The management certificate uploaded to your Azure subscription.</span></span>  
  
-   <span data-ttu-id="4daeb-116">El certificado de administración guardado en el almacén de certificados personal en el equipo en el que se está ejecutando el asistente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-116">The management certificate saved into the personal certificate store on the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="4daeb-117">Debe tener una ubicación de almacenamiento temporal que esté disponible en el equipo donde se hospede la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4daeb-117">You must have a temporary storage location that is available to the computer where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is hosted.</span></span> <span data-ttu-id="4daeb-118">La ubicación de almacenamiento temporal también debe estar disponible en el equipo donde el asistente se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4daeb-118">The temporary storage location must also be available to the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="4daeb-119">Si está implementando la base de datos en una VM existente, la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe estar configurada para escuchar en un puerto TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="4daeb-119">If you are deploying the database to an existing VM, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured to listen on a TCP/IP port.</span></span>  
  
-   <span data-ttu-id="4daeb-120">Una máquina virtual de Azure o una imagen de la galería que planea usar para la creación de la máquina virtual debe tener el SQL Server Adaptador para la nube configurado y en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4daeb-120">Either an Azure VM or Gallery image you plan to use for creation of the VM must have the SQL Server Cloud Adapter configured and running.</span></span>  
  
-   <span data-ttu-id="4daeb-121">Debe configurar un punto de conexión abierto para el SQL Server Adaptador para la nube en la puerta de enlace de Azure con el puerto privado 11435.</span><span class="sxs-lookup"><span data-stu-id="4daeb-121">You must configure an open endpoint for your SQL Server Cloud Adapter on the Azure gateway with private port 11435.</span></span>  
  
 <span data-ttu-id="4daeb-122">Además, si piensa implementar la base de datos en una máquina virtual de Azure existente, también debe poder proporcionar:</span><span class="sxs-lookup"><span data-stu-id="4daeb-122">In addition, if you plan to deploy your database into an existing Azure VM, you must also be able to provide:</span></span>  
  
-   <span data-ttu-id="4daeb-123">El nombre DNS del servicio en la nube que hospeda la VM.</span><span class="sxs-lookup"><span data-stu-id="4daeb-123">The DNS name of the cloud service that hosts your VM.</span></span>  
  
-   <span data-ttu-id="4daeb-124">Credenciales de administrador para la VM.</span><span class="sxs-lookup"><span data-stu-id="4daeb-124">Administrator credentials for the VM.</span></span>  
  
-   <span data-ttu-id="4daeb-125">Credenciales con privilegios de operador de copia de seguridad en la base de datos que pretende implementar, desde la instancia de origen de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4daeb-125">Credentials with Backup operator privileges on the database you plan to deploy, from the source instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4daeb-126">Para obtener más información acerca de cómo ejecutar SQL Server en máquinas virtuales de Azure, consulte [preparación para la migración a SQL Server en azure virtual machines](https://msdn.microsoft.com/library/dn133142.aspx).</span><span class="sxs-lookup"><span data-stu-id="4daeb-126">For more information about running SQL Server in Azure virtual machines, see [Getting Ready to Migrate to SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx).</span></span>  
  
 <span data-ttu-id="4daeb-127">En los equipos que ejecutan sistemas operativos Windows Server, debe usar la configuración siguiente para ejecutar este asistente:</span><span class="sxs-lookup"><span data-stu-id="4daeb-127">On computers running Windows Server operating systems, you must use the following configuration settings to run this wizard:</span></span>  
  
-   <span data-ttu-id="4daeb-128">Desactive la Configuración de seguridad mejorada: use Administrador del servidor > Servidor local para establecer la Configuración de seguridad mejorada (ESC) de Internet Explorer en **DESACTIVADA**.</span><span class="sxs-lookup"><span data-stu-id="4daeb-128">Turn off Enhanced Security Configuration:  Use Server Manager > Local Server to set Internet Explorer Enhanced Security Configuration (ESC) to **OFF**.</span></span>  
  
-   <span data-ttu-id="4daeb-129">Habilitar JavaScript: Internet Explorer > Opciones de Internet > Seguridad > Nivel personalizado > Scripting > Active scripting: **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="4daeb-129">Enable JavaScript:  Internet Explorer > Internet Options > Security > Customer Level > Scripting > Active Scripting: **Enable**.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="limitations"></a> <span data-ttu-id="4daeb-130">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4daeb-130">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4daeb-131">La limitación de tamaño de la base de datos para esta operación es 1 TB.</span><span class="sxs-lookup"><span data-stu-id="4daeb-131">The database size limitation for this operation is 1 TB.</span></span>  
  
 <span data-ttu-id="4daeb-132">Esta característica de implementación está disponible en SQL Server Management Studio para [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4daeb-132">This deployment feature is available in SQL Server Management Studio for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="4daeb-133">Esta característica de implementación solo se puede usar con bases de datos de usuario; no se admite implementar bases de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="4daeb-133">This deployment feature is for use only with user databases; deploying system databases is not supported.</span></span>  
  
 <span data-ttu-id="4daeb-134">La característica de implementación no admite los servicios hospedados asociados a un grupo de afinidad.</span><span class="sxs-lookup"><span data-stu-id="4daeb-134">The deployment feature does not support hosted services that are associated with an Affinity Group.</span></span> <span data-ttu-id="4daeb-135">Por ejemplo, las cuentas de almacenamiento asociadas a un grupo de afinidad no se pueden seleccionar para usarlas en la página **Configuración de implementación** de este asistente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-135">For example, storage accounts associated with an Affinity Group cannot be selected for use on the **Deployment Settings** page of this wizard.</span></span>  
  
 <span data-ttu-id="4daeb-136">La versión de SQL Server de la máquina virtual debe ser igual o posterior a la versión de SQL Server de origen.</span><span class="sxs-lookup"><span data-stu-id="4daeb-136">The SQL Server version in the VM must be the same or later than the source SQL Server version.</span></span> <span data-ttu-id="4daeb-137">SQL Server versiones de base de datos que se pueden implementar en una máquina virtual de Azure mediante este asistente:</span><span class="sxs-lookup"><span data-stu-id="4daeb-137">SQL Server database versions that can be deployed to an Azure VM using this wizard:</span></span>  
  
-   <span data-ttu-id="4daeb-138">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="4daeb-138">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="4daeb-139">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4daeb-139">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="4daeb-140">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="4daeb-140">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="4daeb-141">SQL Server versiones de base de datos que se ejecutan en una base de datos de máquinas virtuales de Azure se pueden implementar en:</span><span class="sxs-lookup"><span data-stu-id="4daeb-141">SQL Server database versions running in an Azure VM database can be deployed to:</span></span>  
  
-   <span data-ttu-id="4daeb-142">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="4daeb-142">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="4daeb-143">Si hay un conflicto de nombres entre el nombre de la base de datos para una operación de implementación en ejecución y una base de datos existente en la VM, el asistente sugerirá un nombre de base de datos anexado para la base de datos en ejecución de manera que pueda completar la operación.</span><span class="sxs-lookup"><span data-stu-id="4daeb-143">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
###  <a name="considerations-for-deploying-a-filestream-enabled-database-to-an-azure-vm"></a><a name="filestream"></a> <span data-ttu-id="4daeb-144">Consideraciones para implementar una base de datos habilitada para FILESTREAM en una máquina virtual de Windows Azure</span><span class="sxs-lookup"><span data-stu-id="4daeb-144">Considerations for Deploying a FILESTREAM-enabled Database to an Azure VM</span></span>  
 <span data-ttu-id="4daeb-145">Tenga en cuenta las directrices y limitaciones siguientes al implementar las bases de datos que tienen BLOBS almacenados en objetos FILESTREAM:</span><span class="sxs-lookup"><span data-stu-id="4daeb-145">Note the following guidelines and restrictions when deploying databases that have BLOBS stored in FILESTREAM objects:</span></span>  
  
-   <span data-ttu-id="4daeb-146">La característica de implementación no puede implementar una base de datos habilitada para FILESTREAM en una nueva máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="4daeb-146">The deployment feature cannot deploy a FILESTREAM-enabled database into a new VM.</span></span> <span data-ttu-id="4daeb-147">Si FILESTREAM no está habilitado en la máquina virtual antes de ejecutar el asistente, la operación de restauración de la base de datos producirá un error y la operación del asistente no se podrá completar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-147">If FILESTREAM is not enabled in the VM before you run the wizard, the database restore operation will fail and the wizard operation will not be able to complete successfully.</span></span> <span data-ttu-id="4daeb-148">Para implementar correctamente una base de datos que utiliza FILESTREAM, habilite FILESTREAM en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la máquina virtual host antes de iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-148">To successfully deploy a database that uses FILESTREAM, enable FILESTREAM in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the host VM before launching the wizard.</span></span> <span data-ttu-id="4daeb-149">Para obtener más información, vea [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span><span class="sxs-lookup"><span data-stu-id="4daeb-149">For more information, see [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span></span>  
  
-   <span data-ttu-id="4daeb-150">Si la base de datos utiliza OLTP en memoria, puede implementar la base de datos en una máquina virtual de Windows Azure sin ninguna modificación en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4daeb-150">If your database utilizes In-Memory OLTP, you can deploy the database to an Azure VM without any modifications to the database.</span></span> <span data-ttu-id="4daeb-151">Para obtener más información, vea [OLTP en memoria (optimización en memoria)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="4daeb-151">For more information, see [In-Memory OLTP (In-Memory Optimization)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span></span>  
  
###  <a name="considerations-for-geographic-distribution-of-assets"></a><a name="geography"></a><span data-ttu-id="4daeb-152">Consideraciones sobre la distribución geográfica de activos</span><span class="sxs-lookup"><span data-stu-id="4daeb-152">Considerations for Geographic Distribution of Assets</span></span>  
 <span data-ttu-id="4daeb-153">Observe que los activos siguientes se deben encontrar en la misma región geográfica:</span><span class="sxs-lookup"><span data-stu-id="4daeb-153">Note that the following assets must be located in the same geographic region:</span></span>  
  
-   <span data-ttu-id="4daeb-154">Servicio en la nube</span><span class="sxs-lookup"><span data-stu-id="4daeb-154">Cloud Service</span></span>  
  
-   <span data-ttu-id="4daeb-155">Ubicación de máquina virtual</span><span class="sxs-lookup"><span data-stu-id="4daeb-155">VM Location</span></span>  
  
-   <span data-ttu-id="4daeb-156">Servicio de almacenamiento en disco de datos</span><span class="sxs-lookup"><span data-stu-id="4daeb-156">Data Disk Storage Service</span></span>  
  
 <span data-ttu-id="4daeb-157">Si los activos enumerados anteriormente no se ubican conjuntamente, el asistente no se podrá completar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-157">If the assets listed above are not co-located, the wizard will not be able to complete successfully.</span></span>  
  
###  <a name="wizard-configuration-settings"></a><a name="configuration_settings"></a> <span data-ttu-id="4daeb-158">Valores de configuración del asistente</span><span class="sxs-lookup"><span data-stu-id="4daeb-158">Wizard Configuration Settings</span></span>  
 <span data-ttu-id="4daeb-159">Utilice los detalles siguientes de configuración para modificar la configuración de una implementación de la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una máquina virtual de Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-159">Use the following configuration details to modify settings for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database deployment to an Azure VM.</span></span>  
  
-   <span data-ttu-id="4daeb-160">**Ruta de acceso predeterminada del archivo de configuración** : %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span><span class="sxs-lookup"><span data-stu-id="4daeb-160">**Default path for the configuration file** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span></span>  
  
-   <span data-ttu-id="4daeb-161">**Estructura de los archivos de configuración**</span><span class="sxs-lookup"><span data-stu-id="4daeb-161">**Configuration file structure**</span></span>  
  
    -   \<DeploymentSettings>  
  
        -   <span data-ttu-id="4daeb-162"><OtherSettings</span><span class="sxs-lookup"><span data-stu-id="4daeb-162"><OtherSettings</span></span>  
  
            -   <span data-ttu-id="4daeb-163">TraceLevel = "debug"\<!-- Logging level --></span><span class="sxs-lookup"><span data-stu-id="4daeb-163">TraceLevel="Debug" \<!-- Logging level --></span></span>  
  
            -   <span data-ttu-id="4daeb-164">BackupPath = " \\ \\ [nombre de servidor] \\ [volumen] \\ "\<!-- The last used path for backup. Used as default in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="4daeb-164">BackupPath="\\\\[server name]\\[volume]\\" \<!-- The last used path for backup. Used as default in the wizard. --></span></span>  
  
            -   <span data-ttu-id="4daeb-165">CleanupDisabled = false/>\<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span><span class="sxs-lookup"><span data-stu-id="4daeb-165">CleanupDisabled = False /> \<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span></span>  
  
        -   <span data-ttu-id="4daeb-166"><PublishProfile\<!-- The last used publish profile information. --></span><span class="sxs-lookup"><span data-stu-id="4daeb-166"><PublishProfile \<!-- The last used publish profile information. --></span></span>  
  
            -   <span data-ttu-id="4daeb-167">Certificate = "12A34B567890123ABCD4EF567A8"\<!-- The certificate for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="4daeb-167">Certificate="12A34B567890123ABCD4EF567A8" \<!-- The certificate for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="4daeb-168">Subscription = "1a2b34c5-67d8-90ef-AB12-Xxxxxxxxxxxxx"\<!-- The subscription for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="4daeb-168">Subscription="1a2b34c5-67d8-90ef-ab12-xxxxxxxxxxxxx" \<!-- The subscription for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="4daeb-169">Name = "mi suscripción"\<!-- The name of the subscription. --></span><span class="sxs-lookup"><span data-stu-id="4daeb-169">Name="My Subscription" \<!-- The name of the subscription. --></span></span>  
  
            -   <span data-ttu-id="4daeb-170">Publisher="" /></span><span class="sxs-lookup"><span data-stu-id="4daeb-170">Publisher="" /></span></span>  
  
    -   \</DeploymentSettings>  
  
 <span data-ttu-id="4daeb-171">**Valores del archivo de configuración**</span><span class="sxs-lookup"><span data-stu-id="4daeb-171">**Configuration file values**</span></span>  
  
###  <a name="permissions"></a><a name="permissions"></a> <span data-ttu-id="4daeb-172">Permisos</span><span class="sxs-lookup"><span data-stu-id="4daeb-172">Permissions</span></span>  
 <span data-ttu-id="4daeb-173">La base de datos que se implementa debe estar en un estado normal, la base de datos debe ser accesible para la cuenta de usuario que ejecuta el asistente y la cuenta de usuario debe tener permisos para realizar una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4daeb-173">The database being deployed must be in a normal state, the database must be accessible to the user account running the wizard, and the user account must have permissions to perform a backup operation.</span></span>  
  
##  <a name="using-the-deploy-database-to-azure-vm-wizard"></a><a name="launch_wizard"></a><span data-ttu-id="4daeb-174">Uso del Asistente para implementar una base de datos en máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="4daeb-174">Using the Deploy Database to Azure VM Wizard</span></span>  
 <span data-ttu-id="4daeb-175">**Para iniciar el asistente, realice los pasos siguientes:**</span><span class="sxs-lookup"><span data-stu-id="4daeb-175">**To launch the wizard, use the following steps:**</span></span>  
  
1.  <span data-ttu-id="4daeb-176">Use SQL Server Management Studio para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la base de datos que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="4daeb-176">Use SQL Server Management Studio to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the database you want to deploy.</span></span>  
  
2.  <span data-ttu-id="4daeb-177">En el **Explorador de objetos**, expanda el nombre de instancia y, a continuación, expanda el nodo **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="4daeb-177">In **Object Explorer**, expand the instance name, then expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="4daeb-178">Haga clic con el botón derecho en la base de datos que desea implementar, seleccione **tareas**y, después, seleccione **implementar base de datos en máquina virtual de Azure...**</span><span class="sxs-lookup"><span data-stu-id="4daeb-178">Right-click the database you want to deploy, select **Tasks**, and then select **Deploy Database to Azure VM...**</span></span>  
  

  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="4daeb-179">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="4daeb-179">Introduction Page</span></span>  
 <span data-ttu-id="4daeb-180">En esta página se describe el asistente **para implementar una base de datos SQL Server en una máquina virtual de Azure** .</span><span class="sxs-lookup"><span data-stu-id="4daeb-180">This page describes the **Deploy a SQL Server Database to an Azure VM** wizard.</span></span>  
  
 <span data-ttu-id="4daeb-181">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="4daeb-181">**Options**</span></span>  
  
-   <span data-ttu-id="4daeb-182">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="4daeb-182">**Do not show this page again.**</span></span> <span data-ttu-id="4daeb-183">- Active esta casilla para que la página Introducción deje de mostrarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="4daeb-183">- Click this check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="4daeb-184">**Siguiente** : continúa en la página **Configuración de origen** .</span><span class="sxs-lookup"><span data-stu-id="4daeb-184">**Next** - Proceeds to the **Source Settings** page.</span></span>  
  
-   <span data-ttu-id="4daeb-185">**Cancelar** : cancela la operación y cierra el asistente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-185">**Cancel** - Cancels the operation and closes the wizard.</span></span>  
  
-   <span data-ttu-id="4daeb-186">**Ayuda** : inicia el tema de ayuda de MSDN para el asistente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-186">**Help** - Launches the MSDN Help topic for the wizard.</span></span>  
  
##  <a name="source-settings"></a><a name="Source_settings"></a><span data-ttu-id="4daeb-187">Configuración de origen</span><span class="sxs-lookup"><span data-stu-id="4daeb-187">Source Settings</span></span>  
 <span data-ttu-id="4daeb-188">Use esta página para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda la base de datos que desea implementar en la máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-188">Use this page to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database you want to deploy to the Azure VM.</span></span> <span data-ttu-id="4daeb-189">También especificará una ubicación temporal para que los archivos se guarden desde el equipo local antes de que se transfieran a Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-189">You will also specify a temporary location for files to be saved from the local machine before they are transferred to Azure.</span></span> <span data-ttu-id="4daeb-190">Esta puede ser una ubicación de red compartida.</span><span class="sxs-lookup"><span data-stu-id="4daeb-190">This can be a shared, network location.</span></span>  
  
 <span data-ttu-id="4daeb-191">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="4daeb-191">**Options**</span></span>  
  
-   <span data-ttu-id="4daeb-192">Haga clic en **conectar...** y, a continuación, especifique los detalles de conexión de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda la base de datos que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="4daeb-192">Click **Connect...** and then specify connection details for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database to deploy.</span></span>  
  
-   <span data-ttu-id="4daeb-193">Use la lista desplegable **Seleccionar base de datos** para especificar la base de datos que implementar.</span><span class="sxs-lookup"><span data-stu-id="4daeb-193">Use the **Select Database** drop-down list to specify the database to deploy.</span></span>  
  
-   <span data-ttu-id="4daeb-194">En el campo **otras opciones** , especifique una carpeta compartida que sea accesible para el servicio de VM de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-194">In the **Other Settings** field, specify a shared folder that will be accessible to the Azure VM service.</span></span>  
  
##  <a name="azure-sign-in"></a><a name="Azure_sign-in"></a><span data-ttu-id="4daeb-195">Inicio de sesión en Azure</span><span class="sxs-lookup"><span data-stu-id="4daeb-195">Azure Sign-in</span></span>  
 <span data-ttu-id="4daeb-196">Use esta página para conectarse a Azure y proporcionar el certificado de administración o los detalles del perfil de publicación.</span><span class="sxs-lookup"><span data-stu-id="4daeb-196">Use this page to connect to Azure and provide management certificate or publishing profile details.</span></span>  
  
 <span data-ttu-id="4daeb-197">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="4daeb-197">**Options**</span></span>  
  
-   <span data-ttu-id="4daeb-198">**Certificado de administración** : Utilice esta opción para especificar un certificado del almacén de certificados local que coincida con el certificado de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-198">**Management Certificate** - Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span>  
  
-   <span data-ttu-id="4daeb-199">**Perfil de publicación** : Utilice esta opción si ya tiene un perfil de publicación descargado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4daeb-199">**Publishing Profile** - Use this option if you already have a publishing profile downloaded to your computer.</span></span>  
  
-   <span data-ttu-id="4daeb-200">**Iniciar sesión** : Use esta opción para iniciar sesión en Azure con un cuenta de Microsoft (por ejemplo, un Live ID o una cuenta de hotmail) para generar y descargar un nuevo certificado de administración.</span><span class="sxs-lookup"><span data-stu-id="4daeb-200">**Sign In** - Use this option to sign in to Azure using a Microsoft account - for example, a Live ID or Hotmail account - to generate and download a new management certificate.</span></span> <span data-ttu-id="4daeb-201">Observe que el número de certificados por suscripción está limitado.</span><span class="sxs-lookup"><span data-stu-id="4daeb-201">Note that the number of certificates per subscription is limited.</span></span>  
  
-   <span data-ttu-id="4daeb-202">**Suscripción** : seleccione, escriba o pegue el identificador de suscripción de Azure que coincida con el certificado de administración del almacén de certificados local o un perfil de publicación.</span><span class="sxs-lookup"><span data-stu-id="4daeb-202">**Subscription** - Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store or a publishing profile.</span></span>  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a><span data-ttu-id="4daeb-203">Página configuración de implementación</span><span class="sxs-lookup"><span data-stu-id="4daeb-203">Deployment Settings Page</span></span>  
 <span data-ttu-id="4daeb-204">Use esta página para especificar el servidor de destino y proporcionar detalles sobre la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="4daeb-204">Use this page to specify the destination server and to provide details about your new database.</span></span>  
  
 <span data-ttu-id="4daeb-205">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="4daeb-205">**Options**</span></span>  
  
-   <span data-ttu-id="4daeb-206">**Máquina virtual de Azure** : especifique los detalles de la máquina virtual que hospedará la base de datos SQL Server:</span><span class="sxs-lookup"><span data-stu-id="4daeb-206">**Azure Virtual Machine** - Specify details for the VM that will host the SQL Server database:</span></span>  
  
-   <span data-ttu-id="4daeb-207">**Nombre del servicio en la nube** : especifique el nombre del servicio que hospeda la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="4daeb-207">**Cloud Service name** - Specify the name of the service that hosts the VM.</span></span> <span data-ttu-id="4daeb-208">Para crear un nuevo servicio en la nube, especifique un nombre para este.</span><span class="sxs-lookup"><span data-stu-id="4daeb-208">To create a new Cloud Service, specify a name for the new Cloud Service.</span></span>  
  
-   <span data-ttu-id="4daeb-209">**Nombre de la máquina virtual** : especifique el nombre de la máquina virtual que hospedará la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4daeb-209">**Virtual Machine name** - Specify the name of the VM that will host the SQL Server database.</span></span> <span data-ttu-id="4daeb-210">Para crear una nueva máquina virtual de Azure, especifique un nombre para la nueva máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="4daeb-210">To create a new Azure VM, specify a name for the new VM.</span></span>  
  
-   <span data-ttu-id="4daeb-211">**Configuración** : Use el botón configuración para crear una nueva máquina virtual que hospede la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4daeb-211">**Settings** - Use the Settings button to create a new VM to host the SQL Server database.</span></span> <span data-ttu-id="4daeb-212">Si está utilizando una VM existente, la información que proporcione se utilizará para autenticar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="4daeb-212">If you are using an existing VM, the information you provide will be used to authenticate your credentials.</span></span>  
  
-   <span data-ttu-id="4daeb-213">**Cuenta de almacenamiento** : seleccione la cuenta de almacenamiento en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4daeb-213">**Storage account** - Select the storage account from the drop-down list.</span></span> <span data-ttu-id="4daeb-214">Para crear una nueva cuenta de almacenamiento, especifique un nombre para esta.</span><span class="sxs-lookup"><span data-stu-id="4daeb-214">To create a new storage account, specify a name for the new account.</span></span> <span data-ttu-id="4daeb-215">Observe que las cuentas de almacenamiento asociadas a un grupo de afinidad no estarán disponibles en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4daeb-215">Note that storage accounts associated with an Affinity Group will not be available in the drop-down list.</span></span>  
  
-   <span data-ttu-id="4daeb-216">**Base de datos de destino** : especifique los detalles de la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="4daeb-216">**Target Database** - Specify details for the target database.</span></span>  
  
-   <span data-ttu-id="4daeb-217">**Conexión de servidor** : detalles de conexión para el servidor.</span><span class="sxs-lookup"><span data-stu-id="4daeb-217">**Server Connection** - Connection details for the server.</span></span>  
  
-   <span data-ttu-id="4daeb-218">**Base de datos** : especifique o confirme el nombre de una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="4daeb-218">**Database** - Specify or confirm the name of a new database.</span></span> <span data-ttu-id="4daeb-219">Si el nombre de la base de datos ya existe en la instancia de SQL Server de destino, se recomienda especificar un nombre de base de datos modificado.</span><span class="sxs-lookup"><span data-stu-id="4daeb-219">If the database name already exists on the destination SQL Server instance, we suggest that you specify a modified database name.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="4daeb-220">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="4daeb-220">Summary Page</span></span>  
 <span data-ttu-id="4daeb-221">Esta página se utiliza para revisar la configuración especificada para la operación.</span><span class="sxs-lookup"><span data-stu-id="4daeb-221">Use this page to review the specified settings for the operation.</span></span> <span data-ttu-id="4daeb-222">Para completar la operación de implementación con los valores especificados, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4daeb-222">To complete the deploy operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="4daeb-223">Para cancelar la operación de implementación y salir del asistente, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="4daeb-223">To cancel the deploy operation and exit the wizard, click **Cancel**.</span></span>  
  
 <span data-ttu-id="4daeb-224">Puede haber pasos manuales necesarios para implementar los detalles de la base de datos en la SQL Server base de datos en la máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="4daeb-224">There may be manual steps required to deploy database details to the SQL Server database on the Azure VM.</span></span> <span data-ttu-id="4daeb-225">Estos pasos se describen en detalle.</span><span class="sxs-lookup"><span data-stu-id="4daeb-225">These steps will be outlined in detail for you.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="4daeb-226">Página resultados</span><span class="sxs-lookup"><span data-stu-id="4daeb-226">Results Page</span></span>  
 <span data-ttu-id="4daeb-227">En esta página se notifica la corrección o el error de la operación de implementación, mostrando los resultados de cada acción.</span><span class="sxs-lookup"><span data-stu-id="4daeb-227">This page reports the success or failure of the deploy operation, showing the results of each action.</span></span> <span data-ttu-id="4daeb-228">Cualquier acción que encuentre un error tendrá una indicación en la columna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="4daeb-228">Any action that encountered an error will have an indication in the **Result** column.</span></span> <span data-ttu-id="4daeb-229">Haga clic en el vínculo para ver un informe del error para esa acción.</span><span class="sxs-lookup"><span data-stu-id="4daeb-229">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="4daeb-230">Haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="4daeb-230">Click **Finish** to close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4daeb-231">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4daeb-231">See Also</span></span>  
 <span data-ttu-id="4daeb-232">[Adaptador para la nube para SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4daeb-232">[Cloud Adapter for SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span></span>  
 <span data-ttu-id="4daeb-233">[Administración del ciclo de vida de la base](../database-lifecycle-management.md) </span><span class="sxs-lookup"><span data-stu-id="4daeb-233">[Database Lifecycle Management](../database-lifecycle-management.md) </span></span>  
 <span data-ttu-id="4daeb-234">[Exportar una aplicación de capa de datos](../data-tier-applications/export-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="4daeb-234">[Export a Data-tier Application](../data-tier-applications/export-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="4daeb-235">[Importar un archivo BACPAC para crear una nueva base de datos de usuario](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span><span class="sxs-lookup"><span data-stu-id="4daeb-235">[Import a BACPAC File to Create a New User Database](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span></span>  
 <span data-ttu-id="4daeb-236">[Copia de seguridad y restauración de Azure SQL Database](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span><span class="sxs-lookup"><span data-stu-id="4daeb-236">[Azure SQL Database Backup and Restore](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span></span>  
 <span data-ttu-id="4daeb-237">[SQL Server implementación en Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span><span class="sxs-lookup"><span data-stu-id="4daeb-237">[SQL Server Deployment in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span></span>  
 [<span data-ttu-id="4daeb-238">Preparar la migración a SQL Server en Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="4daeb-238">Getting Ready to Migrate to SQL Server in Azure Virtual Machines</span></span>](https://msdn.microsoft.com/library/dn133142.aspx)  
  
  
