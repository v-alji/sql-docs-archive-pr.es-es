---
title: Eliminación de archivos de blob de copia de seguridad con concesiones activas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 13a8f879-274f-4934-a722-b4677fc9a782
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02aea910589633a5c3ec79e283c757727b4d92cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672131"
---
# <a name="deleting-backup-blob-files-with-active-leases"></a><span data-ttu-id="0a429-102">Eliminar archivos de blob de copia de seguridad con concesiones activas</span><span class="sxs-lookup"><span data-stu-id="0a429-102">Deleting Backup Blob Files with Active Leases</span></span>
  <span data-ttu-id="0a429-103">Cuando se realiza una copia de seguridad o se restaura desde Azure Storage, SQL Server adquiere una concesión infinita para bloquear el acceso exclusivo al BLOB.</span><span class="sxs-lookup"><span data-stu-id="0a429-103">When backing up to or restoring from Azure storage, SQL Server acquires an infinite lease in order to lock exclusive access to the blob.</span></span> <span data-ttu-id="0a429-104">Cuando el proceso de copia de seguridad o de restauración se ha completado correctamente, se libera la concesión.</span><span class="sxs-lookup"><span data-stu-id="0a429-104">When the backup or restore process is successfully completed, the lease is released.</span></span> <span data-ttu-id="0a429-105">Si una copia de seguridad o una restauración dan error, el proceso de copia de seguridad intenta limpiar los blobs no válidos.</span><span class="sxs-lookup"><span data-stu-id="0a429-105">If a backup or restore fails, the backup process attempts to clean up any invalid blob.</span></span> <span data-ttu-id="0a429-106">Sin embargo, si el error de la copia de seguridad se debe a un error de conectividad en la red mantenido o prolongado, es posible que el proceso de copia de seguridad no pueda obtener acceso al blob y este podría quedar huérfano.</span><span class="sxs-lookup"><span data-stu-id="0a429-106">However, if the backup fails due to prolonged or sustained network connectivity failure, the backup  process may not be able gain access to the blob and the blob may remain orphaned.</span></span> <span data-ttu-id="0a429-107">Esto significa que no se puede escribir en el blob o que el blob no se puede eliminar hasta que no se libera la concesión.</span><span class="sxs-lookup"><span data-stu-id="0a429-107">This means that the blob cannot be written to or deleted until the lease is released.</span></span> <span data-ttu-id="0a429-108">En este tema se describe cómo liberar la concesión y eliminar el blob.</span><span class="sxs-lookup"><span data-stu-id="0a429-108">This topic describes how to release the lease and deleting the blob..</span></span>  
  
 <span data-ttu-id="0a429-109">Para obtener más información sobre los tipos de concesiones, lea este [artículo](https://go.microsoft.com/fwlink/?LinkId=275664).</span><span class="sxs-lookup"><span data-stu-id="0a429-109">For more information on the types of leases, read this [article](https://go.microsoft.com/fwlink/?LinkId=275664).</span></span>  
  
 <span data-ttu-id="0a429-110">Si se produce un error en la operación de copia de seguridad, se puede obtener un archivo de copia de seguridad que no es válido.</span><span class="sxs-lookup"><span data-stu-id="0a429-110">If the backup operation fails, it can result in a backup file that is not valid.</span></span>  <span data-ttu-id="0a429-111">El archivo blob de copia de seguridad también podría tener una concesión activa, impidiendo su eliminación o sobrescritura.</span><span class="sxs-lookup"><span data-stu-id="0a429-111">The backup blob file might also have an active lease, preventing it from being deleted or overwritten.</span></span>  <span data-ttu-id="0a429-112">Con el fin de eliminar o sobrescribir estos blobs, primero se debe interrumpir la concesión. Si hay errores de copia de seguridad, se recomienda limpiar las concesiones y eliminar los blobs.</span><span class="sxs-lookup"><span data-stu-id="0a429-112">In order to delete or overwrite such blobs, the lease should first be broken.If there are backup failures, we recommend that you clean up leases and delete blobs.</span></span> <span data-ttu-id="0a429-113">También puede elegir periódicamente una limpieza como parte de las tareas de administración de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0a429-113">You can also choose cleanup periodically as part of storage management tasks.</span></span>  
  
 <span data-ttu-id="0a429-114">Si se produce un error de restauración, las restauraciones posteriores no se bloquean y, por tanto, la concesión activa puede no suponer ningún problema.</span><span class="sxs-lookup"><span data-stu-id="0a429-114">If there is a restore failure, subsequent restores are not blocked, and therefore the active lease may not be an issue.</span></span> <span data-ttu-id="0a429-115">Solo es necesario interrumpir la concesión cuando se tiene que sobrescribir o eliminar el blob.</span><span class="sxs-lookup"><span data-stu-id="0a429-115">Breaking the lease is only necessary when you have to overwrite or delete the blob.</span></span>  
  
## <a name="managing-orphaned-blobs"></a><span data-ttu-id="0a429-116">Administrar blobs huérfanos</span><span class="sxs-lookup"><span data-stu-id="0a429-116">Managing Orphaned Blobs</span></span>  
 <span data-ttu-id="0a429-117">En los pasos siguientes se describe cómo realizar la limpieza después de una actividad de copia de seguridad o restauración con errores.</span><span class="sxs-lookup"><span data-stu-id="0a429-117">The follow steps describe how to clean up after failed backup or restore activity.</span></span> <span data-ttu-id="0a429-118">Todos los pasos se pueden realizar mediante scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a429-118">All the steps can be done using PowerShell scripts.</span></span> <span data-ttu-id="0a429-119">En la sección siguiente se proporciona un ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="0a429-119">A code example is provided in the following section:</span></span>  
  
1.  <span data-ttu-id="0a429-120">**Identificar blobs que tienen concesiones** : si tiene un script o un proceso que ejecuta los procesos de copia de seguridad, es posible que pueda capturar el error dentro del script o del proceso y usarlo para limpiar los blobs.</span><span class="sxs-lookup"><span data-stu-id="0a429-120">**Identifying blobs that have leases:** If you have a script or a process that runs the backup processes, you might be able to capture the failure within the script or process and use that to clean up the blobs.</span></span>   <span data-ttu-id="0a429-121">También puede usar las propiedades LeaseStats y LeastState para identificar los blobs que tienen concesiones.</span><span class="sxs-lookup"><span data-stu-id="0a429-121">You can also use the LeaseStats and LeastState properties to identify the blobs that have leases on them.</span></span> <span data-ttu-id="0a429-122">Una vez identificados los blobs, se recomienda que revise la lista y compruebe la validez del archivo de copia de seguridad antes de eliminar el blob.</span><span class="sxs-lookup"><span data-stu-id="0a429-122">Once you have identified the blobs, we recommend that you review the list, verify the validity of the backup file before deleting the blob.</span></span>  
  
2.  <span data-ttu-id="0a429-123">**Interrumpir la concesión** : una solicitud autorizada puede interrumpir la concesión sin proporcionar un identificador de concesión.</span><span class="sxs-lookup"><span data-stu-id="0a429-123">**Breaking the lease:** An authorized request can break the lease without supplying a lease ID.</span></span> <span data-ttu-id="0a429-124">Vea [aquí](https://go.microsoft.com/fwlink/?LinkID=275664) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0a429-124">See [here](https://go.microsoft.com/fwlink/?LinkID=275664) for more information.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="0a429-125">SQL Server emite un identificador de concesión para establecer acceso exclusivo durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="0a429-125">SQL Server issues a lease ID to establish exclusive access during the restore operation.</span></span> <span data-ttu-id="0a429-126">El identificador de concesión de restauración es BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span><span class="sxs-lookup"><span data-stu-id="0a429-126">The restore lease ID is BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span></span>  
  
3.  <span data-ttu-id="0a429-127">**Eliminar el blob** : para eliminar un blob que tiene una concesión activa, debe interrumpir primero la concesión.</span><span class="sxs-lookup"><span data-stu-id="0a429-127">**Deleting the Blob:** To delete a blob that has an active lease, you must first break the lease.</span></span>  
  
###  <a name="powershell-script-example"></a><a name="Code_Example"></a><span data-ttu-id="0a429-128">Ejemplo de script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a429-128">PowerShell Script Example</span></span>  
 <span data-ttu-id="0a429-129">Importante: Si está ejecutando PowerShell 2,0, puede que tenga problemas al cargar el ensamblado de Microsoft WindowsAzure.Storage.dll. \*\* \* \* \* \* \*\*</span><span class="sxs-lookup"><span data-stu-id="0a429-129">**\*\* Important \*\*** If you are running PowerShell 2.0, you may have problems loading the Microsoft WindowsAzure.Storage.dll assembly.</span></span> <span data-ttu-id="0a429-130">Recomendamos que se actualice a Powershell 3.0 para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="0a429-130">We recommend that you upgrade to Powershell 3.0 to solve the issue.</span></span> <span data-ttu-id="0a429-131">También puede usar la siguiente solución alternativa para PowerShell 2.0:</span><span class="sxs-lookup"><span data-stu-id="0a429-131">You may also use the following workaround for PowerShell 2.0:</span></span>  
  
-   <span data-ttu-id="0a429-132">Cree o modifique el archivo powershell.exe.config para cargar los ensamblados de .NET 2.0 y .NET 4.0 en tiempo de ejecución con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a429-132">Create or modify the powershell.exe.config file to load .NET 2.0 and .NET 4.0 assemblies at runtime with the following:</span></span>  
  
    ```xml
    <?xml version="1.0"?>
    <configuration>
        <startup useLegacyV2RuntimeActivationPolicy="true">
            <supportedRuntime version="v4.0.30319"/>
            <supportedRuntime version="v2.0.50727"/>
        </startup>
    </configuration>
    ```  
  
 <span data-ttu-id="0a429-133">En el ejemplo siguiente se ilustra cómo identificar los blobs que tienen concesiones activas y cómo interrumpirlas.</span><span class="sxs-lookup"><span data-stu-id="0a429-133">The following example illustrates identifying blobs that have active leases and then breaking them.</span></span> <span data-ttu-id="0a429-134">En el ejemplo también se muestra cómo filtrar los identificadores de concesión de versión.</span><span class="sxs-lookup"><span data-stu-id="0a429-134">The example also demonstrates how filter for release lease IDs.</span></span>  
  
 <span data-ttu-id="0a429-135">Sugerencias para ejecutar este script</span><span class="sxs-lookup"><span data-stu-id="0a429-135">Tips on running this script</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0a429-136">Si una copia de seguridad en el servicio de almacenamiento de blobs de Azure se está ejecutando al mismo tiempo que este script, se puede producir un error en la copia de seguridad, ya que este script interrumpirá la concesión que la copia de seguridad está intentando adquirir al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="0a429-136">If a backup to Azure Blob storage service is running at the same time as this script, the backup can fail since this script will break the lease that the backup is trying to acquire at the same time.</span></span> <span data-ttu-id="0a429-137">Se recomienda ejecutar este script durante una ventana de mantenimiento o cuando no esté previsto que se ejecute ninguna copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0a429-137">We recommend running this script during a maintenance windows or when no backups are expected to run.</span></span>  
  
1.  <span data-ttu-id="0a429-138">Al ejecutar este script, se le pedirá que proporcione valores para la cuenta de almacenamiento, la clave de almacenamiento, el contenedor y los parámetros de ruta de acceso y nombre del ensamblado de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="0a429-138">When you run this script, you will be prompted to provide values for the storage account, storage key, container, and the Azure storage assembly path and name parameters.</span></span> <span data-ttu-id="0a429-139">La ruta de acceso del almacenamiento en el ensamblado es el directorio de instalación de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a429-139">The path of the storage is assembly is the installation directory of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0a429-140">El nombre de archivo del ensamblado de almacenamiento es Microsoft.WindowsAzure.Storage.dll.</span><span class="sxs-lookup"><span data-stu-id="0a429-140">The file name for the storage assembly is Microsoft.WindowsAzure.Storage.dll.</span></span> <span data-ttu-id="0a429-141">A continuación se muestra un ejemplo de los mensajes y los valores especificados:</span><span class="sxs-lookup"><span data-stu-id="0a429-141">Following is an example of the prompts and values entered:</span></span>  
  
    ```  
    cmdlet  at command pipeline position 1  
    Supply values for the following parameters:  
    storageAccount: mycloudstorageaccount  
    storageKey: 0BopKY7eEha3gBnistYk+904nf  
    blobContainer: mycontainer   
    storageAssemblyPath: C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Microsoft.WindowsAzure.Storage.dll  
    ```  
  
2.  <span data-ttu-id="0a429-142">Si no hay ningún blob que tenga concesiones bloqueadas debe aparecer un mensaje similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a429-142">If there are no blobs that have locked leases you should see the following message:</span></span>  
  
     <span data-ttu-id="0a429-143">**No hay ningún blob con el estado de concesión bloqueada**</span><span class="sxs-lookup"><span data-stu-id="0a429-143">**There are no blobs with locked lease status**</span></span>  
  
     <span data-ttu-id="0a429-144">Si hay blobs con concesiones bloqueadas, debe ver los mensajes siguientes:</span><span class="sxs-lookup"><span data-stu-id="0a429-144">If there are blobs with locked leases, you should see the following messages:</span></span>  
  
     <span data-ttu-id="0a429-145">**Interrumpir concesiones**</span><span class="sxs-lookup"><span data-stu-id="0a429-145">**Breaking Leases**</span></span>  
  
     <span data-ttu-id="0a429-146">**La concesión de \<URL of the Blob> es una concesión de restauración: solo verá este mensaje si tiene un BLOB con una concesión de restauración que todavía está activa.**</span><span class="sxs-lookup"><span data-stu-id="0a429-146">**The lease on \<URL of the Blob> is a restore lease: You will see this message only if you have a blob with a restore lease that is still active.**</span></span>  
  
     <span data-ttu-id="0a429-147">**La concesión en \<URL of the Blob> no es una concesión de restauración interrumpida en \<URL of the Bob> .**</span><span class="sxs-lookup"><span data-stu-id="0a429-147">**The lease on \<URL of the Blob> is not a restore lease Breaking lease on \<URL of the Bob>.**</span></span>  
  
```powershell
param(  
       [Parameter(Mandatory=$true)]  
       [string]$storageAccount,  
       [Parameter(Mandatory=$true)]  
       [string]$storageKey,  
       [Parameter(Mandatory=$true)]  
       [string]$blobContainer,  
       [Parameter(Mandatory=$true)]  
       [string]$storageAssemblyPath  
)  
  
# Well known Restore Lease ID  
$restoreLeaseId = "BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2"  
  
# Load the storage assembly without locking the file for the duration of the PowerShell session  
$bytes = [System.IO.File]::ReadAllBytes($storageAssemblyPath)  
[System.Reflection.Assembly]::Load($bytes)  
  
$cred = New-Object 'Microsoft.WindowsAzure.Storage.Auth.StorageCredentials' $storageAccount, $storageKey  
$client = New-Object 'Microsoft.WindowsAzure.Storage.Blob.CloudBlobClient' "https://$storageAccount.blob.core.windows.net", $cred  
$container = $client.GetContainerReference($blobContainer)  
  
#list all the blobs  
$allBlobs = $container.ListBlobs()
  
$lockedBlobs = @()  
# filter blobs that are have Lease Status as "locked"  
foreach($blob in $allBlobs)  
{  
    $blobProperties = $blob.Properties
    if($blobProperties.LeaseStatus -eq "Locked")  
    {  
        $lockedBlobs += $blob  
    }  
}  
  
if ($lockedBlobs.Count -eq 0)  
{
    Write-Host " There are no blobs with locked lease status"  
}

if($lockedBlobs.Count -gt 0)  
{  
    Write-Host "Breaking leases"  
    foreach($blob in $lockedBlobs )
    {  
        try  
        {  
            $blob.AcquireLease($null, $restoreLeaseId, $null, $null, $null)  
            Write-Host "The lease on $($blob.Uri) is a restore lease"  
        }  
        catch [Microsoft.WindowsAzure.Storage.StorageException]  
        {  
            if($_.Exception.RequestInformation.HttpStatusCode -eq 409)  
            {  
                Write-Host "The lease on $($blob.Uri) is not a restore lease"  
            }  
        }  
  
        Write-Host "Breaking lease on $($blob.Uri)"  
        $blob.BreakLease($(New-TimeSpan), $null, $null, $null) | Out-Null  
    }  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="0a429-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a429-148">See Also</span></span>  
 [<span data-ttu-id="0a429-149">Procedimientos recomendados y solución de problemas de Copia de seguridad en URL de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a429-149">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
