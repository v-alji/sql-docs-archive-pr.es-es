---
title: Usar PowerShell para realizar una copia de seguridad de varias bases de datos en Azure Blob Storage servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: f7008339-e69d-4e20-9265-d649da670460
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95da5d0009f88943029e62960e7429b292242bbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673733"
---
# <a name="use-powershell-to-backup-multiple-databases-to-azure-blob-storage-service"></a><span data-ttu-id="075ae-102">Uso de PowerShell para hacer la copia de seguridad de varias bases de datos en el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="075ae-102">Use PowerShell to Backup Multiple Databases to Azure Blob Storage Service</span></span>
  <span data-ttu-id="075ae-103">Este tema proporciona ejemplos de scripts que se pueden utilizar para automatizar las copias de seguridad del servicio Azure Blob Storage con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="075ae-103">This topic provides sample scripts that can be used to automate backups to Azure Blob storage service using PowerShell cmdlets.</span></span>  
  
## <a name="overview-of-powershell-cmdlets-for-backup-and-restore"></a><span data-ttu-id="075ae-104">Información general de los cmdlets de PowerShell para las copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="075ae-104">Overview of PowerShell cmdlets for Backup and Restore</span></span>  
 <span data-ttu-id="075ae-105">`Backup-SqlDatabase` y `Restore-SqlDatabase` son los dos cmdlets principales disponibles para realizar operaciones de copias de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="075ae-105">The `Backup-SqlDatabase` and `Restore-SqlDatabase` are the two main cmdlets available to do backup and restore operations.</span></span> <span data-ttu-id="075ae-106">Además, hay otros cmdlets que pueden requerir automatizar las copias de seguridad para Azure Blob Storage, como el conjunto de cmdlets de **SqlCredential**. La siguiente es una lista de los cmdlets de PowerShell disponibles en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que se utilizan en las operaciones de copia de seguridad y restauración:</span><span class="sxs-lookup"><span data-stu-id="075ae-106">In addition, there are other cmdlets that may be required to automate backups to Azure Blob storage like the set of **SqlCredential** cmdlets  Following is a list of PowerShell cmdlets available in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that are used in backup and restore operations:</span></span>  
  
 <span data-ttu-id="075ae-107">Backup-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="075ae-107">Backup-SqlDatabase</span></span>  
 <span data-ttu-id="075ae-108">Este cmdlet se utiliza para crear una copia de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="075ae-108">This cmdlet is used to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Backup.</span></span>  
  
 <span data-ttu-id="075ae-109">Restore-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="075ae-109">Restore-SqlDatabase</span></span>  
 <span data-ttu-id="075ae-110">Se usa para restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="075ae-110">Used to restore a database.</span></span>  
  
 <span data-ttu-id="075ae-111">New-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="075ae-111">New-SqlCredential</span></span>  
 <span data-ttu-id="075ae-112">Este cmdlet se utiliza para crear una credencial SQL para la copia de seguridad de SQL Server en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="075ae-112">This cmdlet is used to create a SQL Credential to use for SQL Server Backup to Azure Storage.</span></span> <span data-ttu-id="075ae-113">Para obtener más información sobre las credenciales y su uso en SQL Server copias de seguridad y restauración, consulte [SQL Server Backup and restore with Azure BLOB Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="075ae-113">For more information on credentials and their use in SQL Server Backup and Restore, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="075ae-114">Get-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="075ae-114">Get-SqlCredential</span></span>  
 <span data-ttu-id="075ae-115">Este cmdlet se utiliza para recuperar el objeto Credencial y sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="075ae-115">This cmdlet is used to retrieve the Credential object and its properties.</span></span>  
  
 <span data-ttu-id="075ae-116">Remove-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="075ae-116">Remove-SqlCredential</span></span>  
 <span data-ttu-id="075ae-117">Eliminar un objeto Credencial SQL</span><span class="sxs-lookup"><span data-stu-id="075ae-117">Delete a SQL Credential object</span></span>  
  
 <span data-ttu-id="075ae-118">Set-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="075ae-118">Set-SqlCredential</span></span>  
 <span data-ttu-id="075ae-119">Este cmdlet se utiliza para cambiar o establecer las propiedades del objeto Credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="075ae-119">This cmdlet is used to change or set the properties of the SQL Credential Object.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="075ae-120">Los cmdlets de credenciales se utilizan en las copias de seguridad y en la restauración en los escenarios de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="075ae-120">The Credential cmdlets are used in Backup and Restore to Azure Blob storage scenarios.</span></span>  
  
### <a name="powershell-for-multi-database-multi-instance-backup-operations"></a><span data-ttu-id="075ae-121">PowerShell para operaciones de copia de seguridad de varias instancias y varias bases de datos</span><span class="sxs-lookup"><span data-stu-id="075ae-121">PowerShell for Multi-Database, Multi-Instance Backup Operations</span></span>  
 <span data-ttu-id="075ae-122">Las secciones siguientes contienen scripts para varias operaciones como crear una credencial SQL en varias instancias de SQL Server, hacer la copia de seguridad de todas las bases de datos de usuario en una instancia de SQL Server, etcétera.</span><span class="sxs-lookup"><span data-stu-id="075ae-122">The following sections include scripts for various operations like creating a SQL Credential on multiple instance of SQL Server, backing up all user databases in an instance of SQL Server, and such.</span></span> <span data-ttu-id="075ae-123">Puede utilizar estos scripts para automatizar o para programar las operaciones de copia de seguridad según los requisitos de su entorno.</span><span class="sxs-lookup"><span data-stu-id="075ae-123">You can use these scripts to automate or schedule backup operations according to the requirements of your environment.</span></span> <span data-ttu-id="075ae-124">Los scripts que aquí se muestran son ejemplos y se pueden modificar o ampliar para su entorno.</span><span class="sxs-lookup"><span data-stu-id="075ae-124">The scripts provided here are examples, and may be modified or extended for your environment.</span></span>  
  
 <span data-ttu-id="075ae-125">A continuación se presentan las consideraciones para los scripts de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="075ae-125">The following are considerations for the sample scripts:</span></span>  
  
1.  <span data-ttu-id="075ae-126">**Navegar por las rutas de acceso de SQL Server PowerShell:** Windows PowerShell implementa cmdlets para navegar por la estructura de ruta de acceso que representa la jerarquía de objetos compatible con un proveedor de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="075ae-126">**Navigating SQL Server PowerShell paths:** Windows PowerShell implements cmdlets to navigate the path structure that represents the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="075ae-127">Cuando ha navegado a un nodo de la ruta de acceso, puede usar otros cmdlets para realizar operaciones básicas en el objeto actual.</span><span class="sxs-lookup"><span data-stu-id="075ae-127">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span>  
  
2.  <span data-ttu-id="075ae-128">`Get-ChildItem` cmdlet: la información devuelta por `Get-ChildItem` depende de la ubicación de una ruta de acceso de PowerShell de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="075ae-128">`Get-ChildItem` cmdlet: The information returned by the `Get-ChildItem` depends on the location in a SQL Server PowerShell path.</span></span> <span data-ttu-id="075ae-129">Por ejemplo, si la ubicación está en el equipo, este cmdlet devuelve todas las instancias del motor de base de datos de SQL Server instaladas en él.</span><span class="sxs-lookup"><span data-stu-id="075ae-129">For example, if the location is at the computer level, this cmdlet returns all the SQL Server database engine instances installed on the computer.</span></span> <span data-ttu-id="075ae-130">Como otro ejemplo, si la ubicación está en un objeto como son las bases de datos, este cmdlet devuelve una lista de objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="075ae-130">As another example, if the location is at the object level such as databases, then this cmdlet returns a list of database objects.</span></span>  <span data-ttu-id="075ae-131">De forma predeterminada, el cmdlet `Get-ChildItem` no devuelve los objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="075ae-131">By default the `Get-ChildItem` cmdlet does not return system objects.</span></span>  <span data-ttu-id="075ae-132">Con el parámetro -Force, puede ver los objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="075ae-132">Using the -Force parameter you can see the system objects.</span></span>  
  
     <span data-ttu-id="075ae-133">Para obtener más información, consulte [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span><span class="sxs-lookup"><span data-stu-id="075ae-133">For more information, see [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span></span>  
  
3.  <span data-ttu-id="075ae-134">Aunque cada ejemplo de código se pueda probar de forma independiente cambiando los valores de las variables, la creación de una cuenta de Azure Storage y una credencial SQL son requisitos previos imprescindibles para todas las operaciones de copia de seguridad y de restauración en el servicio Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="075ae-134">Although each code sample can be tried independently by changing the variable values, creating an Azure Storage Account and a SQL Credential are prerequisites and required for all backup and restore operations to Azure Blob storage service.</span></span>  
  
### <a name="create-a-sql-credential-on-all-the-instances-of-sql-server"></a><span data-ttu-id="075ae-135">Crear una credencial SQL en todas las instancias de SQL Server</span><span class="sxs-lookup"><span data-stu-id="075ae-135">Create a SQL Credential on All the Instances of SQL Server</span></span>  
 <span data-ttu-id="075ae-136">Hay dos ejemplos de scripts y ambos crean una credencial SQL "mybackupToURL" en todas las instancias de SQL Server de un equipo.</span><span class="sxs-lookup"><span data-stu-id="075ae-136">There are two sample scripts, and both create a SQL Credential "mybackupToURL" on all the instances of SQL Server on a computer.</span></span> <span data-ttu-id="075ae-137">El primer ejemplo es sencillo, crea la credencial y no intercepta las excepciones.</span><span class="sxs-lookup"><span data-stu-id="075ae-137">The first example creates is simple and creates the credential and does not trap exceptions.</span></span>  <span data-ttu-id="075ae-138">Por ejemplo, si hubiera ya una credencial existente con el mismo nombre en una de las instancias del equipo, el script produciría un error.</span><span class="sxs-lookup"><span data-stu-id="075ae-138">For example, if there was already an existing credential with the same name on one of the instances of the computer, the script would fail.</span></span> <span data-ttu-id="075ae-139">El segundo ejemplo intercepta los errores y permite que el script continúe.</span><span class="sxs-lookup"><span data-stu-id="075ae-139">The second example traps errors and allows the script to continue.</span></span>  
  
```powershell
import-module sqlps  
  
# create variables  
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#pipe the instances to new-sqlcredentail cmdlet to create SQL credential  
$instances | New-SqlCredential -Name $credentialName -Identity $storageAccount -Secret $secureString  
```  
  
```powershell
import-module sqlps  
  
# set the parameter values
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#loop through instances and create a SQL credential, output any errors  
ForEach ($instance In $instances)  
{  
    Try  
{  
     New-SqlCredential -Name $credentialName -path "SQLServer:\SQL\$($instance.name)" -Identity $storageAccount -Secret $secureString -ea Stop
}  
Catch [Exception]  
    {
            Write-Host "instance - $($instance.name): "$_.Exception.Message
    }
 }
```  
  
### <a name="remove-a-sql-credential-from-all-the-instances-of-sql-server"></a><span data-ttu-id="075ae-140">Quitar una credencial SQL de todas las instancias de SQL Server</span><span class="sxs-lookup"><span data-stu-id="075ae-140">Remove A SQL Credential from All the Instances of SQL Server</span></span>  
 <span data-ttu-id="075ae-141">Este script se puede utilizar para quitar una credencial específica de todas las instancias de SQL Server instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="075ae-141">This script can be used to remove a specific credential from all the instances of SQL Server installed on the computer.</span></span> <span data-ttu-id="075ae-142">Si el objeto Credencial no existe en una instancia concreta, aparece un mensaje de error y el script continúa hasta que se comprueban todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="075ae-142">If the Credential object does not exist on a specific instance, an error message is displayed, and the script continues until all instances are checked.</span></span>  
  
```powershell
import-module sqlps  
  
cd SQLServer:\SQL\COMPUTERNAME  
$credentialName = "mybackuptoURL"  
  
$instances = Get-ChildItem  
  
ForEach ($instance In $instances)  
   {
    Try  
        {  
            $path = "SQLServer:\SQL\$($instance.name)\credentials\$credentialName"   
            Remove-SqlCredential -Path $path -ea stop   
         }  
         Catch [Exception]  
         {  
            Write-Host $_.Exception.Message
        }
    }  
```  
  
### <a name="full-database-backup-for-all-databases-including-system-databases"></a><span data-ttu-id="075ae-143">Copia de seguridad completa de base de datos para todas las bases de datos (INCLUDING SYSTEM DATABASES)</span><span class="sxs-lookup"><span data-stu-id="075ae-143">Full Database Backup for all Databases (INCLUDING SYSTEM DATABASES)</span></span>  
 <span data-ttu-id="075ae-144">El siguiente script crea copias de seguridad de todas las bases de datos del equipo.</span><span class="sxs-lookup"><span data-stu-id="075ae-144">The following script creates backups of all databases on the computer.</span></span> <span data-ttu-id="075ae-145">Esto incluye tanto a las bases de datos de usuario como a la base de datos del sistema **msdb** .</span><span class="sxs-lookup"><span data-stu-id="075ae-145">This includes both user databases and **msdb** system database.</span></span> <span data-ttu-id="075ae-146">El script filtra las bases de datos del sistema **tempdb** y **model** .</span><span class="sxs-lookup"><span data-stu-id="075ae-146">The script filters out **tempdb** and **model** system databases.</span></span>  
  
```powershell
import-module sqlps  
# set the parameter values  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the  databases -filter out tempdb and model databases  
  
 ForEach ($instance In $instances)  
 {  
   $path = "sqlserver:\sql\$($instance.name)\databases"  
   $alldatabases = Get-ChildItem -Force -path $path | Where-Object {$_.name -ne "tempdb" -and $_.name -ne "model"}   
   $alldatabases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On -script   
 }
```  
  
### <a name="full-database-backup-for-all-user-databases"></a><span data-ttu-id="075ae-147">Copia de seguridad completa de base de datos de todas las bases de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="075ae-147">Full Database Backup for ALL User Databases</span></span>  
 <span data-ttu-id="075ae-148">El script siguiente se puede utilizar para realizar la copia de seguridad de todas las bases de datos de usuario en todas las instancias de SQL Server del equipo.</span><span class="sxs-lookup"><span data-stu-id="075ae-148">The following script can be used to back up all the user databases on all the instances of SQL Server on the computer.</span></span>  
  
```powershell
import-module sqlps
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the user databases  
 ForEach ($instance In $instances)  
 {  
    $databases = dir "sqlserver:\sql\$($instance.name)\databases"  
    $databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On
 }  
```  
  
### <a name="full-database-backup-for-master-and-msdb-system-databases-on-all-the-instances-of-sql-server"></a><span data-ttu-id="075ae-149">Copia de seguridad completa de la base de datos MAESTRA y MSDB (BASES DATABASE SYSTEM) en todas las instancias de SQL Server</span><span class="sxs-lookup"><span data-stu-id="075ae-149">Full Database Backup for MASTER and MSDB (SYSTEM DATABASES) On All the Instances of SQL Server</span></span>  
 <span data-ttu-id="075ae-150">El script siguiente se puede usar para crear copias de seguridad de las bases de datos **master** y **msdb** en todas las instancias de SQL Server instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="075ae-150">The following script can be used to back up **master** and **msdb** databases on all the instances of SQL Server installed on the computer.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackupToUrl"  
$sysDbs = "master", "msdb"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
$instances = Get-ChildItem
ForEach ($instance In $instances)  
 {  
      ForEach ($s In $sysdbs)  
     {  
        Backup-SqlDatabase -Database $s -path "sqlserver:\sql\$($instance.name)" -BackupContainer  $backupUrlContainer -SqlCredential $credentialName -Compression On   
}
 } 
```  
  
### <a name="full-database-backup-for-all-user-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="075ae-151">Copia de seguridad completa de todas las bases de datos de usuario en una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="075ae-151">Full Database Backup for All User Databases on an Instance of SQL Server</span></span>  
 <span data-ttu-id="075ae-152">El siguiente script se utiliza para realizar la copia de seguridad solo de las bases de datos de usuario disponibles en una instancia con nombre de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="075ae-152">The following script is used to back up only the user databases available on a named instance of SQL Server.</span></span> <span data-ttu-id="075ae-153">El mismo script se puede utilizar para la instancia predeterminada del equipo cambiando el valor del parámetro $srvPath.</span><span class="sxs-lookup"><span data-stu-id="075ae-153">The same script can be used for the default instance on the computer by changing the $srvPath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME"  # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
  
#retrieves the database objects for a specific instance  
$databases = dir $srvPath\databases  
  
#backup all the user databases  
$databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
```  
  
### <a name="full-database-backup-for-only-system-databases-master-and-msdb-on-an-instance-of-sql-server"></a><span data-ttu-id="075ae-154">Copia de seguridad completa solo de las bases de datos del sistema (MAESTRA y MSDB) en una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="075ae-154">Full Database Backup for Only System Databases (MASTER AND MSDB) On an Instance of SQL Server</span></span>  
 <span data-ttu-id="075ae-155">El script completo se puede usar para crear una copia de seguridad de las bases de datos **master** y **msdb** en una instancia con nombre de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="075ae-155">The full script can be used to back up the **master** and the **msdb** databases on a named instance of SQL Server.</span></span> <span data-ttu-id="075ae-156">El mismo script se puede utilizar para la instancia predeterminada del equipo cambiando el valor del parámetro $srvPath.</span><span class="sxs-lookup"><span data-stu-id="075ae-156">The same script can be used for the default instance on the computer by changing the $srvpath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME" # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#navigate to instance level  
cd $srvPath  
  
$sysDbs = "master", "msdb"  
ForEach ($s In $sysDbs)
{  
Backup-SqlDatabase -Database $s -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="075ae-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="075ae-157">See Also</span></span>
 <span data-ttu-id="075ae-158">[SQL Server de copias de seguridad y restauración con Azure BLOB Storage servicio](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server las prácticas recomendadas de copia de seguridad y solución de problemas](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="075ae-158">[SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
