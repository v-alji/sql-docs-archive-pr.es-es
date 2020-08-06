---
title: Prácticas recomendadas y solución de problemas de Copia de seguridad en URL de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: de676bea-cec7-479d-891a-39ac8b85664f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06127b5e4b422750554c30fae23b6190107cb643
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674167"
---
# <a name="sql-server-backup-to-url-best-practices-and-troubleshooting"></a><span data-ttu-id="d945f-102">Prácticas recomendadas y solución de problemas de Copia de seguridad en URL de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d945f-102">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>
  <span data-ttu-id="d945f-103">Este tema incluye prácticas recomendadas y sugerencias para la solución de problemas de copias de seguridad y restauraciones de SQL Server en Azure Blob service.</span><span class="sxs-lookup"><span data-stu-id="d945f-103">This topic includes best practices and troubleshooting tips for SQL Server backup and restores to the Azure Blob service.</span></span>  
  
 <span data-ttu-id="d945f-104">Para obtener más información sobre cómo usar el servicio Azure Blob Storage para realizar operaciones de copia de seguridad o restauración de SQL Server, vea:</span><span class="sxs-lookup"><span data-stu-id="d945f-104">For more information about using Azure Blob storage service for SQL Server backup or restore operations, see:</span></span>  
  
-   [<span data-ttu-id="d945f-105">Copia de seguridad y restauración de SQL Server con el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="d945f-105">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
-   [<span data-ttu-id="d945f-106">Tutorial: Copia de seguridad y restauración de SQL Server en el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="d945f-106">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="managing-backups"></a><span data-ttu-id="d945f-107">Administrar copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="d945f-107">Managing Backups</span></span>  
 <span data-ttu-id="d945f-108">La lista siguiente incluye recomendaciones generales para administrar copias de seguridad:</span><span class="sxs-lookup"><span data-stu-id="d945f-108">The following list includes general recommendations to manage backups:</span></span>  
  
-   <span data-ttu-id="d945f-109">Se recomienda usar un nombre de archivo único para cada copia de seguridad con el fin de evitar que se sobrescriban accidentalmente los blobs.</span><span class="sxs-lookup"><span data-stu-id="d945f-109">Unique file name for every backup is recommended to prevent accidentally overwriting the blobs.</span></span>  
  
-   <span data-ttu-id="d945f-110">Al crear un contenedor, se recomienda establecer el nivel de acceso en **privado**, de forma que solo los usuarios o las cuentas que puedan proporcionar la información de autenticación necesaria sean capaces de leer o escribir los blobs en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="d945f-110">When creating a container, it is recommended that you set the access level to **private**, so only users or accounts that can provide the required authentication information can read or write the blobs in the container.</span></span>  
  
-   <span data-ttu-id="d945f-111">En el caso de SQL Server bases de datos en una instancia de SQL Server que se ejecutan en una máquina virtual de Azure, use una cuenta de almacenamiento en la misma región que la máquina virtual para evitar costos de transferencia de datos entre regiones.</span><span class="sxs-lookup"><span data-stu-id="d945f-111">For SQL Server databases on an instance of SQL Server running in an Azure Virtual Machine, use a storage account in the same region as the virtual machine to avoid data transfer costs between regions.</span></span> <span data-ttu-id="d945f-112">El uso de la misma región también garantiza un rendimiento óptimo para las operaciones de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="d945f-112">Using the same region also ensures optimal performance for backup and restore operations.</span></span>  
  
-   <span data-ttu-id="d945f-113">Una actividad de copia de seguridad con errores puede dar como resultado un archivo de copia de seguridad no válido.</span><span class="sxs-lookup"><span data-stu-id="d945f-113">Failed backup activity can result in an invalid backup file.</span></span> <span data-ttu-id="d945f-114">Se recomienda identificar periódicamente las copias de seguridad con errores y eliminar los archivos blob.</span><span class="sxs-lookup"><span data-stu-id="d945f-114">We recommend periodic identification of failed backups and deleting the blob files.</span></span> <span data-ttu-id="d945f-115">Para obtener más información, consulte [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md).</span><span class="sxs-lookup"><span data-stu-id="d945f-115">For more information, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
-   <span data-ttu-id="d945f-116">El uso de la opción `WITH COMPRESSION` durante la copia de seguridad puede reducir al mínimo los costos de almacenamiento y los costos de transacciones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d945f-116">Using the `WITH COMPRESSION` option during backup can minimize your storage costs and storage transaction costs.</span></span> <span data-ttu-id="d945f-117">También puede reducir el tiempo necesario para completar el proceso de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d945f-117">It can also decrease the time taken to complete the backup process.</span></span>  
  
## <a name="handling-large-files"></a><span data-ttu-id="d945f-118">Controlar archivos grandes</span><span class="sxs-lookup"><span data-stu-id="d945f-118">Handling Large Files</span></span>  
  
-   <span data-ttu-id="d945f-119">La operación de copia de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emplea varios subprocesos para optimizar la transferencia de datos a los servicios Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="d945f-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup operation uses multiple threads to optimize data transfer to Azure Blob storage services.</span></span>  <span data-ttu-id="d945f-120">Sin embargo, el rendimiento depende en varios factores, como el ancho de banda del ISV y el tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d945f-120">However the performance depends on various factors, such as ISV bandwidth and size of the database.</span></span> <span data-ttu-id="d945f-121">Si piensa hacer copia de seguridad de bases de datos o grupos de archivos grandes desde una base de datos de SQL Server local, se recomienda que realice primero algunas pruebas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d945f-121">If you plan to back up large databases or filegroups from an on-premise SQL Server database, it is recommended that you do some throughput testing first.</span></span> <span data-ttu-id="d945f-122">Los acuerdos de nivel de servicio de [Azure Storage](https://go.microsoft.com/fwlink/?LinkId=271619) tienen tiempos de procesamiento máximos para los blobs que puede tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="d945f-122">[Azure storage SLA's](https://go.microsoft.com/fwlink/?LinkId=271619) have maximum processing times for blobs that you can take into consideration.</span></span>  
  
-   <span data-ttu-id="d945f-123">Usar la opción `WITH COMPRESSION` como se recomienda en la sección **Administrar la copia de seguridad** es muy importante al realizar la copia de seguridad de archivos grandes.</span><span class="sxs-lookup"><span data-stu-id="d945f-123">Using the `WITH COMPRESSION` option as recommended in the **Managing Backup** section, it is very important when backing up large files.</span></span>  
  
## <a name="troubleshooting-backup-to-or-restore-from-url"></a><span data-ttu-id="d945f-124">Resolución de problemas para realizar la copia de seguridad de una dirección URL o una restauración a partir de esta</span><span class="sxs-lookup"><span data-stu-id="d945f-124">Troubleshooting Backup To or Restore from URL</span></span>  
 <span data-ttu-id="d945f-125">A continuación se indican algunas formas rápidas de solucionar errores al hacer copia de seguridad o restaurar desde el servicio Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="d945f-125">Following are some quick ways to troubleshoot errors when backing up to or restoring from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="d945f-126">Para evitar errores debidos a opciones no admitidas o limitaciones, revise la lista de limitaciones y la información sobre los comandos de copia de seguridad y restauración en el artículo [SQL Server copias de seguridad y restauración con Azure BLOB Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="d945f-126">To avoid errors due to unsupported options or limitations, review the list of limitations, and support for BACKUP and RESTORE commands information in the [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) article.</span></span>  
  
 <span data-ttu-id="d945f-127">**Errores de autenticación:**</span><span class="sxs-lookup"><span data-stu-id="d945f-127">**Authentication Errors:**</span></span>  
  
-   <span data-ttu-id="d945f-128">WITH CREDENTIAL es una opción nueva que es necesaria para realizar copias de seguridad en el servicio de almacenamiento de blobs de Azure o restaurar desde este.</span><span class="sxs-lookup"><span data-stu-id="d945f-128">WITH CREDENTIAL is a new option and required to back up to or restore from the Azure Blob storage service.</span></span> <span data-ttu-id="d945f-129">He aquí algunos errores relacionados con las credenciales:</span><span class="sxs-lookup"><span data-stu-id="d945f-129">Failures related to credential could be the following:</span></span>  
  
     <span data-ttu-id="d945f-130">La credencial especificada en el comando `BACKUP` o `RESTORE` no existe.</span><span class="sxs-lookup"><span data-stu-id="d945f-130">The credential specified in the `BACKUP` or `RESTORE` command does not exist.</span></span> <span data-ttu-id="d945f-131">Para evitar este problema, puede incluir instrucciones T-SQL para crear la credencial si no existe ninguna en la instrucción de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d945f-131">To avoid this issue, you can include T-SQL statements to create the credential if one does not exist in the backup statement.</span></span> <span data-ttu-id="d945f-132">He aquí un ejemplo que puede usar:</span><span class="sxs-lookup"><span data-stu-id="d945f-132">The following is an example you can use:</span></span>  
  
    ```  
    IF NOT EXISTS  
    (SELECT * FROM sys.credentials   
    WHERE credential_identity = 'mycredential')  
    CREATE CREDENTIAL <credential name> WITH IDENTITY = 'mystorageaccount'  
    ,SECRET = '<storage access key> ;  
  
    ```  
  
-   <span data-ttu-id="d945f-133">La credencial existe pero la cuenta de inicio de sesión usada para ejecutar el comando de copia de seguridad no tiene permisos de acceso a las credenciales.</span><span class="sxs-lookup"><span data-stu-id="d945f-133">The credential exists but the login account that is used to run the backup command does not have permissions to access the credentials.</span></span> <span data-ttu-id="d945f-134">Use una cuenta de inicio de sesión en el rol **db_backupoperator** con permisos para **Modificar cualquier credencial** .</span><span class="sxs-lookup"><span data-stu-id="d945f-134">Use a login account in the **db_backupoperator** role with **Alter any credential** permissions.</span></span>  
  
-   <span data-ttu-id="d945f-135">Compruebe los valores de clave y nombre de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d945f-135">Verify the storage account name and key values.</span></span> <span data-ttu-id="d945f-136">La información almacenada en la credencial debe coincidir con los valores de propiedad de la cuenta de Azure Storage que se usa en las operaciones de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="d945f-136">The information stored in the credential must match the property values of the Azure storage account you are using in the backup and restore operations.</span></span>  
  
 <span data-ttu-id="d945f-137">**Errores de copia de seguridad:**</span><span class="sxs-lookup"><span data-stu-id="d945f-137">**Backup Errors/Failures:**</span></span>  
  
-   <span data-ttu-id="d945f-138">Las copias de seguridad en paralelo en el mismo blob produce errores en una de las copias de seguridad y hacen que aparezca un **Error de inicialización** .</span><span class="sxs-lookup"><span data-stu-id="d945f-138">Parallel backups to the same blob cause one of the backups to fail with an **Initialization failed** error.</span></span>  
  
-   <span data-ttu-id="d945f-139">Use los registros de errores siguientes como ayuda para solucionar problemas de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="d945f-139">Use the following error logs to help with troubleshooting backup errors:</span></span>  
  
    -   <span data-ttu-id="d945f-140">Establezca la marca de seguimiento 3051 para activar el registro en un registro de errores específico con el siguiente formato en:</span><span class="sxs-lookup"><span data-stu-id="d945f-140">Set trace flag 3051 to turn on logging to a specific error log with the following format in:</span></span>  
  
         <span data-ttu-id="d945f-141">BackupToUrl- \<instname> - \<dbname> -Action- \<PID> . log donde \<action> es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d945f-141">BackupToUrl-\<instname>-\<dbname>-action-\<PID>.log Where \<action> is one of:</span></span>  
  
        -   `DB`  
  
        -   `FILELISTONLY`  
  
        -   `LABELONLY`  
  
        -   `HEADERONLY`  
  
        -   `VERIFYONLY`  
  
    -   <span data-ttu-id="d945f-142">También puede buscar información si revisas el registro de eventos de Windows, en registros de aplicación con el nombre "SQLBackupToUrl".</span><span class="sxs-lookup"><span data-stu-id="d945f-142">You can also find information by reviewing the Windows Event Log - Under Application logs with the name 'SQLBackupToUrl'.</span></span>  
  
-   <span data-ttu-id="d945f-143">Al restaurar desde una copia de seguridad comprimida, puede aparecer el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="d945f-143">When restoring from a compressed backup, you might see the following error:</span></span>  
  
    -   <span data-ttu-id="d945f-144">**SqlException 3284. Gravedad: 16 estado: 5**</span><span class="sxs-lookup"><span data-stu-id="d945f-144">**SqlException 3284 occurred. Severity: 16 State: 5**</span></span>  
        <span data-ttu-id="d945f-145">**La marca de error del mensaje en el dispositivo ' https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak ' no está alineada. Vuelva a emitir la instrucción restore con el mismo tamaño de bloque usado para crear el conjunto de subconjunto: ' 65536 ' parece un valor posible.**</span><span class="sxs-lookup"><span data-stu-id="d945f-145">**Message Filemark on device 'https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak' is not aligned. Reissue the Restore statement with the same block size used to create the backupset: '65536' looks like a possible value.**</span></span>  
  
         <span data-ttu-id="d945f-146">Para resolver este error, vuelva a emitir la instrucción `BACKUP` especificando `BLOCKSIZE = 65536`.</span><span class="sxs-lookup"><span data-stu-id="d945f-146">To solve this error, reissue the `BACKUP` statement with `BLOCKSIZE = 65536` specified.</span></span>  
  
-   <span data-ttu-id="d945f-147">Error durante la copia de seguridad porque los blobs tienen una concesión activa: una actividad de copia de seguridad con errores puede dar como resultado blobs con concesiones activas.</span><span class="sxs-lookup"><span data-stu-id="d945f-147">Error during backup due to blobs that have active lease on them: Failed backup activity can result in blobs with active leases.</span></span>  
  
     <span data-ttu-id="d945f-148">Si se vuelve a intentar una instrucción de copia de seguridad, la operación de copia de seguridad puede producir un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d945f-148">If a backup statement is reattempted, backup operation might fail with an error similar to the following:</span></span>  
  
     <span data-ttu-id="d945f-149">**BACKUP TO URL recibió una excepción del extremo remoto. Mensaje de excepción: Error en el servidor remoto: (412) Actualmente hay una concesión en el blob y no se especificó ningún identificador de concesión en la solicitud**.</span><span class="sxs-lookup"><span data-stu-id="d945f-149">**Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (412) There is currently a lease on the blob and no lease ID was specified in the request**.</span></span>  
  
     <span data-ttu-id="d945f-150">Si se intenta una instrucción de restauración en un archivo de blob de copia de seguridad que tiene una concesión activa, la operación de restauración produce un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d945f-150">If a restore statement is attempted on a backup blob file that has an active lease, the restore operation fails with an error similar to the following:</span></span>  
  
     <span data-ttu-id="d945f-151">**Mensaje de la excepción: Error en el servidor remoto: (409) Conflicto.**</span><span class="sxs-lookup"><span data-stu-id="d945f-151">**Exception Message: The remote server returned an error: (409) Conflict..**</span></span>  
  
     <span data-ttu-id="d945f-152">Cuando se produce ese error, es necesario eliminar los archivos de blob.</span><span class="sxs-lookup"><span data-stu-id="d945f-152">When such error occurs, the blob files need to be deleted.</span></span> <span data-ttu-id="d945f-153">Para obtener más información sobre este escenario y cómo corregir este problema, vea [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md).</span><span class="sxs-lookup"><span data-stu-id="d945f-153">For more information on this scenario and how to correct this problem, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
## <a name="proxy-errors"></a><span data-ttu-id="d945f-154">Errores de proxy</span><span class="sxs-lookup"><span data-stu-id="d945f-154">Proxy Errors</span></span>  
 <span data-ttu-id="d945f-155">Si usa servidores proxy para tener acceso a Internet, pueden producirse los problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d945f-155">If you are using Proxy Servers to access the internet, you may see the following issues:</span></span>  
  
 <span data-ttu-id="d945f-156">**Limitación de la conexión por parte de los servidores proxy:**</span><span class="sxs-lookup"><span data-stu-id="d945f-156">**Connection throttling by Proxy Servers:**</span></span>  
  
 <span data-ttu-id="d945f-157">Los servidores proxy pueden tener configuraciones que limitan el número de conexiones por minuto.</span><span class="sxs-lookup"><span data-stu-id="d945f-157">Proxy Servers can have settings that limit the number of connections per minute.</span></span> <span data-ttu-id="d945f-158">Copia de seguridad en URL es un proceso multiproceso y, por tanto, puede sobrepasar este límite.</span><span class="sxs-lookup"><span data-stu-id="d945f-158">The Backup to URL process is a multi-threaded process and hence can go over this limit.</span></span> <span data-ttu-id="d945f-159">Si esto ocurre, el servidor proxy elimina la conexión.</span><span class="sxs-lookup"><span data-stu-id="d945f-159">If this happens, the proxy server kills the connection.</span></span> <span data-ttu-id="d945f-160">Para resolver este problema, cambie la configuración de proxy para que SQL Server no utilice el proxy.</span><span class="sxs-lookup"><span data-stu-id="d945f-160">To resolve this issue, change the proxy settings so SQL Server is not using the proxy.</span></span>   <span data-ttu-id="d945f-161">A continuación se muestran algunos ejemplos de los tipos o mensajes de error que puede ver en el registro de errores:</span><span class="sxs-lookup"><span data-stu-id="d945f-161">Following are some examples of the types or error messages you may see in the error log:</span></span>  
  
-   <span data-ttu-id="d945f-162">Error de escritura en " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ": la copia de seguridad en URL recibió una excepción del punto de conexión remoto.</span><span class="sxs-lookup"><span data-stu-id="d945f-162">Write on "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak" failed: Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="d945f-163">Mensaje de excepción: No se pueden leer datos de la conexión de transporte: La conexión se cerró.</span><span class="sxs-lookup"><span data-stu-id="d945f-163">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
-   <span data-ttu-id="d945f-164">Error de E/S irrecuperable en el archivo "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:". No se pudo recopilar el error del punto de conexión remoto.</span><span class="sxs-lookup"><span data-stu-id="d945f-164">A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Error could not be gathered from Remote Endpoint.</span></span>  
  
     <span data-ttu-id="d945f-165">Mensaje 3013, nivel 16, estado 1, línea 2</span><span class="sxs-lookup"><span data-stu-id="d945f-165">Msg 3013, Level 16, State 1, Line 2</span></span>  
  
     <span data-ttu-id="d945f-166">Fin anómalo de BACKUP DATABASE.</span><span class="sxs-lookup"><span data-stu-id="d945f-166">BACKUP DATABASE is terminating abnormally.</span></span>  
  
-   <span data-ttu-id="d945f-167">BackupIoRequest:: ReportIoError: error de escritura en el dispositivo de copia de seguridad ' http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak '.</span><span class="sxs-lookup"><span data-stu-id="d945f-167">BackupIoRequest::ReportIoError: write failure on backup device 'http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak'.</span></span> <span data-ttu-id="d945f-168">Error de sistema operativo Copia de seguridad en URL recibió una excepción del extremo remoto.</span><span class="sxs-lookup"><span data-stu-id="d945f-168">Operating system error Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="d945f-169">Mensaje de excepción: No se pueden leer datos de la conexión de transporte: La conexión se cerró.</span><span class="sxs-lookup"><span data-stu-id="d945f-169">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
 <span data-ttu-id="d945f-170">Si activa el registro detallado mediante la marca de seguimiento 3051, puede ver también el mensaje siguiente en los registros:</span><span class="sxs-lookup"><span data-stu-id="d945f-170">If you turn on the verbose logging using the trace flag 3051 you may also see the following message in the logs:</span></span>  
  
 <span data-ttu-id="d945f-171">Código de estado HTTP 502, error de proxy del mensaje de estado HTTP (El número de peticiones HTTP por minuto superó el límite configurado.</span><span class="sxs-lookup"><span data-stu-id="d945f-171">HTTP status code 502, HTTP Status Message Proxy Error ( The number of HTTP requests per minute exceeded the configured limit.</span></span> <span data-ttu-id="d945f-172">Póngase en contacto con el administrador del servidor ISA.</span><span class="sxs-lookup"><span data-stu-id="d945f-172">Contact your ISA Server administrator.</span></span>  <span data-ttu-id="d945f-173">)</span><span class="sxs-lookup"><span data-stu-id="d945f-173">)</span></span>  
  
 <span data-ttu-id="d945f-174">**Configuración de proxy predeterminada no seleccionada:**</span><span class="sxs-lookup"><span data-stu-id="d945f-174">**Default Proxy Settings not picked up:**</span></span>  
  
 <span data-ttu-id="d945f-175">A veces, la configuración predeterminada no se selecciona, lo que produce errores de autenticación del proxy como el que se muestra a continuación:*error de e/s irrecuperable en el archivo " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: " la copia de seguridad en URL recibió una excepción del punto de conexión remoto. Mensaje de excepción: el servidor remoto devolvió un error: (407)* se **requiere autenticación proxy**.</span><span class="sxs-lookup"><span data-stu-id="d945f-175">Sometimes the default settings are not picked up causing proxy authentication errors such as the one shown below:*A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (407)* **Proxy Authentication Required**.</span></span>  
  
 <span data-ttu-id="d945f-176">Para resolver este problema, cree un archivo de configuración que permita al proceso Copia de seguridad en URL utilizar la configuración de proxy predeterminada mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d945f-176">To resolve this issue, create a configuration file that allows the Backup to URL process to use the default proxy settings using the following steps:</span></span>  
  
1.  <span data-ttu-id="d945f-177">Cree un archivo de configuración denominado BackuptoURL.exe.config con el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="d945f-177">Create a configuration file named BackuptoURL.exe.config  with the following xml:</span></span>  
  
    ```  
    <?xml version ="1.0"?>  
    <configuration>   
                    <system.net>   
                                    <defaultProxy enabled="true" useDefaultCredentials="true">   
                                                    <proxy usesystemdefault="true" />   
                                    </defaultProxy>   
                    </system.net>  
    </configuration>  
  
    ```  
  
2.  <span data-ttu-id="d945f-178">Coloque el archivo de configuración en la carpeta Binn de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d945f-178">Place the configuration file in the Binn folder of the SQL Server Instance.</span></span> <span data-ttu-id="d945f-179">Por ejemplo, si el SQL Server está instalado en la unidad C de la máquina, coloque el archivo de configuración aquí: *c:\Archivos de programa\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\Binn*.</span><span class="sxs-lookup"><span data-stu-id="d945f-179">For example, if my SQL Server is installed on the C drive of the machine, place the configuration file here: *C:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Binn*.</span></span>  
  
## <a name="troubleshooting-sql-server-managed-backup-to-azure"></a><span data-ttu-id="d945f-180">Solución de problemas de la copia de seguridad administrada de SQL Server en Azure</span><span class="sxs-lookup"><span data-stu-id="d945f-180">Troubleshooting SQL Server Managed Backup to Azure</span></span>  
 <span data-ttu-id="d945f-181">Puesto que Copia de seguridad administrada de SQL Server se basa en Copia de seguridad en URL, las sugerencias para la solución de problemas que se han descrito en las secciones anteriores son aplicables también a las bases de datos o las instancias que utilizan Copia de seguridad administrada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d945f-181">Since SQL Server Managed Backup is built on top of Backup to URL, the troubleshooting tips described in the earlier sections apply to databases or instances using SQL Server Managed Backup.</span></span>  <span data-ttu-id="d945f-182">La información sobre la solución de problemas de SQL Server copia de seguridad administrada en Azure se describe con más detalle en [solución de problemas de SQL Server copia de seguridad administrada en Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="d945f-182">Information about troubleshooting SQL Server Managed Backup to Azure is described in detail in [Troubleshooting SQL Server Managed  Backup to Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d945f-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d945f-183">See Also</span></span>  
 [<span data-ttu-id="d945f-184">Restauración de las copias de seguridad almacenadas en Azure</span><span class="sxs-lookup"><span data-stu-id="d945f-184">Restoring From Backups Stored in Azure</span></span>](restoring-from-backups-stored-in-microsoft-azure.md)  
  
  
