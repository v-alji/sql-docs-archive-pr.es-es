---
title: Administrar una base de datos del servidor de informes (Modo nativo de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], databases
- renaming databases
- report server database
- databases [Reporting Services], administering
- reportservertempdb
- reportserver database
ms.assetid: 97b2e1b5-3869-4766-97b9-9bf206b52262
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bfb1cb9108af8d3904a4ec679d2c42f11c734ade
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674614"
---
# <a name="administer-a-report-server-database-ssrs-native-mode"></a><span data-ttu-id="5b3ba-102">Administrar una base de datos del servidor de informes (Modo nativo de SSRS)</span><span class="sxs-lookup"><span data-stu-id="5b3ba-102">Administer a Report Server Database (SSRS Native Mode)</span></span>
  <span data-ttu-id="5b3ba-103">Una implementación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] usa dos bases de datos relacionales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para almacenamiento interno.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] deployment uses two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases for internal storage.</span></span> <span data-ttu-id="5b3ba-104">De manera predeterminada, las bases de datos tienen los nombres ReportServer y ReportServerTempdb.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-104">By default, the databases are named ReportServer and ReportServerTempdb.</span></span> <span data-ttu-id="5b3ba-105">ReportServerTempdb se crea con la base de datos principal del servidor de informes y se usa para almacenar datos temporales, información de sesión e informes almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-105">ReportServerTempdb is created with the primary report server database and is used to store temporary data, session information, and cached reports.</span></span>  
  
 <span data-ttu-id="5b3ba-106">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], entre las tareas de administración de bases de datos se incluyen la copia de seguridad y restauración de bases de datos del servidor de informes y la administración de las claves de cifrado que se usan para cifrar y descifrar datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-106">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], database administration tasks include backing up and restoring the report server databases and managing the encryption keys that are used to encrypt and decrypt sensitive data.</span></span>  
  
 <span data-ttu-id="5b3ba-107">Para administrar las bases de datos del servidor de informes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona una amplia variedad de herramientas.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-107">To administer the report server databases, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a variety of tools.</span></span>  
  
-   <span data-ttu-id="5b3ba-108">Para realizar una copia de seguridad, restaurar, mover o recuperar una base de datos del servidor de informes, puede usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], los comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] o las utilidades de símbolo del sistema de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-108">To back up or restore the report server database, move a report server database, or recover a report server database, you can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], the [!INCLUDE[tsql](../../includes/tsql-md.md)] commands, or the database command prompt utilities.</span></span> <span data-ttu-id="5b3ba-109">Para obtener instrucciones, vea [Mover las bases de datos del servidor de informes a otro equipo &#40;Modo nativo de SSRS&#41;](moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-109">For instructions, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) in SQL Server Books Online.</span></span>  
  
-   <span data-ttu-id="5b3ba-110">Para copiar el contenido de una base de datos existente en otra base de datos del servidor de informes, puede adjuntar una copia de una base de datos del servidor de informes y utilizarla con una instancia distinta del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-110">To copy existing database content to another report server database, you can attach a copy of a report server database and use it with a different report server instance.</span></span> <span data-ttu-id="5b3ba-111">También puede crear y ejecutar un script que utilice llamadas SOAP para volver a crear contenido del servidor de informes en una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-111">Or, you can create and run a script that uses SOAP calls to recreate report server content in a new database.</span></span> <span data-ttu-id="5b3ba-112">Puede usar la utilidad **rs** para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-112">You can use the **rs** utility to run the script.</span></span>  
  
-   <span data-ttu-id="5b3ba-113">Para administrar las conexiones entre el servidor de informes y la base de datos del servidor de informes, y para averiguar qué base de datos se utiliza para una instancia concreta del servidor de informes, puede utilizarse la página Instalación de base de datos de la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b3ba-113">To manage connections between the report server and report server database, and to find out which database is used for a particular report server instance, you can use Database Setup page in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Configuration tool.</span></span> <span data-ttu-id="5b3ba-114">Para obtener más información sobre la conexión del servidor de informes a la base de datos del servidor de informes, vea [Configurar una conexión a la base de datos del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5b3ba-114">To learn more about the report server connection to the report server database, see [Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md).</span></span>  
  
## <a name="sql-server-login-and-database-permissions"></a><span data-ttu-id="5b3ba-115">Permisos de inicio de sesión y de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b3ba-115">SQL Server Login and Database Permissions</span></span>  
 <span data-ttu-id="5b3ba-116">Las bases de datos del servidor de informes son utilizadas internamente por este.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-116">The report server databases are used internally by the report server.</span></span> <span data-ttu-id="5b3ba-117">El servicio del servidor de informes realiza conexiones a cualquier base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-117">Connections to either database are made by the Report Server service.</span></span> <span data-ttu-id="5b3ba-118">Puede usar la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurar la conexión del servidor de informes a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-118">You use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to configure the report server connection to the report server database.</span></span>  
  
 <span data-ttu-id="5b3ba-119">Las credenciales para la conexión del servidor de informes a la base de datos pueden ser la cuenta de servicio, una cuenta de usuario de dominio o local de Windows o un usuario de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b3ba-119">Credentials for the report server connection to the database can be the service account, a Windows local or domain user account, or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database user.</span></span> <span data-ttu-id="5b3ba-120">Debe elegir una cuenta existente para la conexión, ya que [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no crea cuentas por usted.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-120">You must choose an existing account for the connection; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not create accounts for you.</span></span>  
  
 <span data-ttu-id="5b3ba-121">Automáticamente se creará para usted un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la base de datos del servidor de informes para la cuenta especificada.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-121">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to the report server database is created for you automatically for the account you specify.</span></span>  
  
 <span data-ttu-id="5b3ba-122">Los permisos a la base de datos también se configuran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-122">Permissions to the database are also configured automatically.</span></span> <span data-ttu-id="5b3ba-123">La herramienta de configuración de Reporting Services asignará la cuenta o usuario de la base de datos a los roles `Public` y `RSExecRole` para las bases de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-123">The Reporting Services Configuration tool will assign the account or database user to the `Public` and `RSExecRole` roles for the report server databases.</span></span> <span data-ttu-id="5b3ba-124">`RSExecRole` otorga permisos para tener acceso a las tablas de base de datos y para ejecutar procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-124">The `RSExecRole` provides permissions for accessing the database tables and for executing stored procedures.</span></span> <span data-ttu-id="5b3ba-125">`RSExecRole`Se crea en Master y msdb al crear la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-125">The `RSExecRole` is created in master and msdb when you create the report server database.</span></span> <span data-ttu-id="5b3ba-126">`RSExecRole` es miembro del rol `db_owner` para las bases de datos del servidor de informes, lo que permite al servidor de informes actualizar su propio esquema que admite un proceso de actualización automática.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-126">The `RSExecRole` is a member of the `db_owner` role for the report server databases, allowing the report server to update its own schema in support of an auto-upgrade process.</span></span>  
  
## <a name="naming-conventions-for-the-report-server-databases"></a><span data-ttu-id="5b3ba-127">Convenciones de nomenclatura para las bases de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5b3ba-127">Naming Conventions for the Report Server Databases</span></span>  
 <span data-ttu-id="5b3ba-128">Cuando se crea la base de datos principal, su nombre debe seguir las reglas especificadas para los [Identificadores de bases de datos](../../relational-databases/databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="5b3ba-128">When creating the primary database, the name of the database must follow the rules specified for [Database Identifiers](../../relational-databases/databases/database-identifiers.md).</span></span> <span data-ttu-id="5b3ba-129">El nombre de la base de datos temporal utiliza siempre el mismo nombre que la base de datos principal del servidor de informes pero con el sufijo Tempdb.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-129">The temporary database name always uses the same name as the primary report server database but with a Tempdb suffix.</span></span> <span data-ttu-id="5b3ba-130">No puede elegir un nombre diferente para la base de datos temporal.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-130">You cannot choose a different name for the temporary database.</span></span>  
  
 <span data-ttu-id="5b3ba-131">No se permite cambiar el nombre de una base de datos del servidor de informes porque las bases de datos del servidor de informes se consideran componentes internos.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-131">Renaming a report server database is not supported because the report server databases are considered internal components.</span></span> <span data-ttu-id="5b3ba-132">Si se cambia el nombre de las bases de datos del servidor de informes, se producen errores.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-132">Renaming the report server databases causes errors to occur.</span></span> <span data-ttu-id="5b3ba-133">Específicamente, si se cambia el nombre de la base de datos principal, un mensaje de error explica que los nombres de las bases de datos no están sincronizados. Si cambia el nombre de la base de datos ReportServerTempdb, se produce el siguiente error interno más adelante al ejecutar informes:</span><span class="sxs-lookup"><span data-stu-id="5b3ba-133">Specifically, if you rename the primary database, an error message explains that the database names are out of sync. If you rename the ReportServerTempdb database, the following internal error occurs later when you run reports:</span></span>  
  
 <span data-ttu-id="5b3ba-134">"Error interno en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-134">"An internal error occurred on the report server.</span></span> <span data-ttu-id="5b3ba-135">Vea el registro de errores para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-135">See the error log for more details.</span></span> <span data-ttu-id="5b3ba-136">(rsInternalError)</span><span class="sxs-lookup"><span data-stu-id="5b3ba-136">(rsInternalError)</span></span>  
  
 <span data-ttu-id="5b3ba-137">El nombre de objeto 'ReportServerTempDB.dbo.PersistedStream' no es válido."</span><span class="sxs-lookup"><span data-stu-id="5b3ba-137">Invalid object name 'ReportServerTempDB.dbo.PersistedStream'."</span></span>  
  
 <span data-ttu-id="5b3ba-138">Este error se debe a que el nombre ReportServerTempdb se almacena internamente y lo utilizan los procedimientos almacenados para realizar operaciones internas.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-138">This error occurs because the ReportServerTempdb name is stored internally and used by stored procedures to perform internal operations.</span></span> <span data-ttu-id="5b3ba-139">Si se cambia el nombre de la base de datos temporal, no funcionarán correctamente los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-139">Renaming the temporary database will prevent the stored procedures from working properly.</span></span>  
  
## <a name="enabling-snapshot-isolation-on-the-report-server-database"></a><span data-ttu-id="5b3ba-140">Habilitar el aislamiento de instantánea en la base de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5b3ba-140">Enabling Snapshot Isolation on the Report Server Database</span></span>  
 <span data-ttu-id="5b3ba-141">No puede habilitar el aislamiento de instantánea en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-141">You cannot enable snapshot isolation on the report server database.</span></span> <span data-ttu-id="5b3ba-142">Si está activado el aislamiento de instantánea, se producirá el siguiente error: "El informe seleccionado no está listo para su visualización.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-142">If snapshot isolation is turned on, you will encounter the following error: "The selected report is not ready for viewing.</span></span> <span data-ttu-id="5b3ba-143">Aún se está representando o no hay disponible una instantánea de informe".</span><span class="sxs-lookup"><span data-stu-id="5b3ba-143">The report is still being rendered or a report snapshot is not available."</span></span>  
  
 <span data-ttu-id="5b3ba-144">Si no habilitó explícitamente el aislamiento de instantánea, puede que el atributo lo estableciera otra aplicación o que la base de datos **modelo** tenga el aislamiento de instantánea habilitado, haciendo que todas las bases de datos nuevas heredaran el valor.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-144">If you did not purposely enable snapshot isolation, the attribute might have been set by another application or the **model** database might have snapshot isolation enabled, causing all new databases to inherit the setting.</span></span>  
  
 <span data-ttu-id="5b3ba-145">Para desactivar el aislamiento de instantánea en la base de datos del servidor de informes, inicie Management Studio, abra una nueva ventana de consulta y pegue y después ejecute el script siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b3ba-145">To turn off snapshot isolation on the report server database, start Management Studio, open a new query window, paste and then run the following script:</span></span>  
  
```  
ALTER DATABASE ReportServer  
SET ALLOW_SNAPSHOT_ISOLATION OFF  
ALTER DATABASE ReportServerTempdb  
SET ALLOW_SNAPSHOT_ISOLATION OFF  
ALTER DATABASE ReportServer  
SET READ_COMMITTED_SNAPSHOT OFF  
ALTER DATABASE ReportServerTempDb  
SET READ_COMMITTED_SNAPSHOT OFF  
```  
  
## <a name="about-database-versions"></a><span data-ttu-id="5b3ba-146">Acerca de las versiones de base de datos</span><span class="sxs-lookup"><span data-stu-id="5b3ba-146">About Database Versions</span></span>  
 <span data-ttu-id="5b3ba-147">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]no se dispone de información explícita acerca de la versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-147">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], explicit information about the database version is not available.</span></span> <span data-ttu-id="5b3ba-148">Sin embargo, como las versiones de la base de datos siempre están sincronizadas con las versiones de los productos, se puede utilizar la información de la versión del producto para saber cuándo ha cambiado la versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b3ba-148">However, because database versions are always synchronized to product versions, you can use product version information to tell when the database version has changed.</span></span> <span data-ttu-id="5b3ba-149">La información de versión de producto de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se indica a través de la información de versión de archivo que aparece en los archivos de registro, en los encabezados de todas las llamadas SOAP y al conectarse a la dirección URL del servidor de informes (por ejemplo, al abrir un explorador en http://localhost/reportserver) .</span><span class="sxs-lookup"><span data-stu-id="5b3ba-149">Product version information for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is indicated through file version information that appears in the log files, in the headers of all SOAP calls, and when you connect to the report server URL (for example, when you open a browser to http://localhost/reportserver).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3ba-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b3ba-150">See Also</span></span>  
 <span data-ttu-id="5b3ba-151">[Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-151">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="5b3ba-152">[Crear una base de datos del servidor de informes de modo nativo &#40;Administrador de configuración de SSRS&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-152">[Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) </span></span>  
 <span data-ttu-id="5b3ba-153">[Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-153">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="5b3ba-154">[Configurar una conexión a la base de datos del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-154">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="5b3ba-155">[Crear una base de datos del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-155">[Create a Report Server Database  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="5b3ba-156">[Operaciones de copia de seguridad y restauración de Reporting Services](../install-windows/backup-and-restore-operations-for-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-156">[Backup and Restore Operations for Reporting Services](../install-windows/backup-and-restore-operations-for-reporting-services.md) </span></span>  
 <span data-ttu-id="5b3ba-157">[Base de datos del servidor de informes &#40;Modo nativo de SSRS&#41;](report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-157">[Report Server Database &#40;SSRS Native Mode&#41;](report-server-database-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="5b3ba-158">[Servidor de informes de Reporting Services &#40;modo nativo&#41;](reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-158">[Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="5b3ba-159">[Almacenar datos cifrados del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md) </span><span class="sxs-lookup"><span data-stu-id="5b3ba-159">[Store Encrypted Report Server Data &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md) </span></span>  
 [<span data-ttu-id="5b3ba-160">Configurar y administrar claves de cifrado &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5b3ba-160">Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md)  
  
  