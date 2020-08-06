---
title: Copia de seguridad en URL de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 11be89e9-ff2a-4a94-ab5d-27d8edf9167d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6918a099e00b1de9e773320b5c6c0e4089859e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747055"
---
# <a name="sql-server-backup-to-url"></a><span data-ttu-id="6aee1-102">Copia de seguridad en URL de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6aee1-102">SQL Server Backup to URL</span></span>
  <span data-ttu-id="6aee1-103">En este tema se presentan los conceptos, los requisitos y los componentes necesarios para utilizar el servicio de almacenamiento de blobs de Azure como destino de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-103">This topic introduces the concepts, requirements and components necessary to use the Azure Blob storage service as a backup destination.</span></span> <span data-ttu-id="6aee1-104">La funcionalidad de copia de seguridad y restauración es igual o similar que la que usa DISK o TAPE, con algunas diferencias.</span><span class="sxs-lookup"><span data-stu-id="6aee1-104">The backup and restore functionality are same or similar to when using DISK or TAPE, with a few differences.</span></span> <span data-ttu-id="6aee1-105">En este tema se incluyen las diferencias, excepciones notables y algunos ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="6aee1-105">The differences are and any notable exceptions, and a few code examples are included in this topic.</span></span>  
  
## <a name="requirements-components-and-concepts"></a><span data-ttu-id="6aee1-106">Requisitos, componentes y conceptos</span><span class="sxs-lookup"><span data-stu-id="6aee1-106">Requirements, Components, and Concepts</span></span>  
 <span data-ttu-id="6aee1-107">**Esta sección:**</span><span class="sxs-lookup"><span data-stu-id="6aee1-107">**In this section:**</span></span>  
  
-   [<span data-ttu-id="6aee1-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6aee1-108">Security</span></span>](#security)  
  
-   [<span data-ttu-id="6aee1-109">Introducción a los principales componentes y conceptos</span><span class="sxs-lookup"><span data-stu-id="6aee1-109">Introduction to Key Components and Concepts</span></span>](#intorkeyconcepts)  
  
-   [<span data-ttu-id="6aee1-110">Servicio de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="6aee1-110">Azure Blob Storage Service</span></span>](#Blob)  
  
-   [<span data-ttu-id="6aee1-111">Componentes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6aee1-111">SQL Server Components</span></span>](#sqlserver)  
  
-   [<span data-ttu-id="6aee1-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="6aee1-112">Limitations</span></span>](#limitations)  
  
-   [<span data-ttu-id="6aee1-113">Compatibilidad con instrucciones backup/restore</span><span class="sxs-lookup"><span data-stu-id="6aee1-113">Support for Backup/Restore Statements</span></span>](#Support)  
  
-   [<span data-ttu-id="6aee1-114">Usar la tarea Copia de seguridad en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6aee1-114">Using Backup Task in SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#BackupTaskSSMS)  
  
-   [<span data-ttu-id="6aee1-115">Copia de seguridad de SQL Server en una dirección URL mediante el Asistente para planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="6aee1-115">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>](sql-server-backup-to-url.md#MaintenanceWiz)  
  
-   [<span data-ttu-id="6aee1-116">Restauración desde Azure Storage con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6aee1-116">Restoring from Azure storage Using SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#RestoreSSMS)  
  
###  <a name="security"></a><a name="security"></a> <span data-ttu-id="6aee1-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6aee1-117">Security</span></span>  
 <span data-ttu-id="6aee1-118">A continuación se muestran los requisitos y las consideraciones de seguridad al realizar copias de seguridad o restaurar desde los servicios de almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="6aee1-118">The following are security considerations and requirements when backing up to or restoring from the Azure Blob storage services.</span></span>  
  
-   <span data-ttu-id="6aee1-119">Al crear un contenedor para el servicio de almacenamiento de blobs de Azure, se recomienda establecer el acceso en **privado**.</span><span class="sxs-lookup"><span data-stu-id="6aee1-119">When creating a container for the Azure Blob storage service, we recommend that you set the access to **private**.</span></span> <span data-ttu-id="6aee1-120">Al configurar el acceso privado se restringe el acceso a los usuarios o las cuentas capaces de proporcionar la información necesaria para autenticarse en la cuenta de Azure.</span><span class="sxs-lookup"><span data-stu-id="6aee1-120">Setting the access to private restricts the access to users or accounts able to provide the necessary information to authenticate to the Azure account.</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="6aee1-121">requiere que el nombre de cuenta de Azure y la autenticación de clave de acceso se almacenen en una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credencial.</span><span class="sxs-lookup"><span data-stu-id="6aee1-121">requires Azure account name and access key authentication to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential.</span></span> <span data-ttu-id="6aee1-122">Esta información se usa para autenticarse en la cuenta de Azure cuando realiza operaciones de copia de seguridad o restauración.</span><span class="sxs-lookup"><span data-stu-id="6aee1-122">This information is used to authenticate to the Azure account when it performs backup or restore operations.</span></span>  
  
-   <span data-ttu-id="6aee1-123">La cuenta de usuario que se usa para emitir comandos BACKUP o RESTORE debe tener el rol de base de datos **operador de db_backup** con permisos **Modificar cualquier credencial** .</span><span class="sxs-lookup"><span data-stu-id="6aee1-123">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
###  <a name="introduction-to-key-components-and-concepts"></a><a name="intorkeyconcepts"></a><span data-ttu-id="6aee1-124">Introducción a los principales componentes y conceptos</span><span class="sxs-lookup"><span data-stu-id="6aee1-124">Introduction to Key Components and Concepts</span></span>  
 <span data-ttu-id="6aee1-125">En las dos secciones siguientes se presentan el servicio de almacenamiento de blobs de Azure y los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes que se usan al realizar copias de seguridad o restaurar desde el servicio de almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="6aee1-125">The following two sections introduce the Azure Blob storage service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components used when backing up to or restoring from the Azure Blob storage service.</span></span> <span data-ttu-id="6aee1-126">Es importante comprender los componentes y la interacción entre ellos para realizar una copia de seguridad o una restauración desde el servicio de almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="6aee1-126">It is important to understand the components and the interaction between them to do a backup to or restore from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="6aee1-127">La creación de una cuenta de Azure es el primer paso de este proceso.</span><span class="sxs-lookup"><span data-stu-id="6aee1-127">Creating an Azure account is the first step to this process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="6aee1-128">usa el **nombre** de la cuenta de almacenamiento de Azure y sus valores de **clave de acceso** para autenticar y escribir y leer blobs en el servicio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6aee1-128">uses the **Azure storage account name** and its **access key** values to authenticate and write and read blobs to the storage service.</span></span> <span data-ttu-id="6aee1-129">La credencial de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] almacena esta información de autenticación y se emplea durante las operaciones de copia de seguridad o restauración.</span><span class="sxs-lookup"><span data-stu-id="6aee1-129">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential stores this authentication information and is used during the backup or restore operations.</span></span> <span data-ttu-id="6aee1-130">Para obtener un tutorial completo sobre cómo crear una cuenta de almacenamiento y realizar una restauración simple, vea el tutorial sobre cómo [usar el servicio de Azure Storage para la copia de seguridad y restauración de SQL Server](https://go.microsoft.com/fwlink/?LinkId=271615).</span><span class="sxs-lookup"><span data-stu-id="6aee1-130">For a complete walkthrough of creating a storage account and performing a simple restore, see [Tutorial Using Azure Storage Service for SQL Server Backup and Restore](https://go.microsoft.com/fwlink/?LinkId=271615).</span></span>  
  
 <span data-ttu-id="6aee1-131">![asignación de la cuenta de almacenamiento a credenciales de SQL](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "asignación de la cuenta de almacenamiento a credenciales de SQL")</span><span class="sxs-lookup"><span data-stu-id="6aee1-131">![mapping storage account to sql credentials](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
###  <a name="azure-blob-storage-service"></a><a name="Blob"></a><span data-ttu-id="6aee1-132">Servicio de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="6aee1-132">Azure Blob Storage Service</span></span>  
 <span data-ttu-id="6aee1-133">**Cuenta de almacenamiento**: La cuenta de almacenamiento es el punto de partida para todos los servicios de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6aee1-133">**Storage Account:** The storage account is the starting point for all storage services.</span></span> <span data-ttu-id="6aee1-134">Para acceder al servicio Azure Blob Storage, cree primero una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="6aee1-134">To access the Azure Blob Storage service, first create an Azure storage account.</span></span> <span data-ttu-id="6aee1-135">El **nombre** de la cuenta de almacenamiento y sus propiedades de **clave de acceso** son necesarias para autenticarse en el servicio de Azure BLOB Storage y sus componentes.</span><span class="sxs-lookup"><span data-stu-id="6aee1-135">The **storage account name** and its **access key** properties are required to authenticate to the Azure Blob Storage service and its components.</span></span>  
  
 <span data-ttu-id="6aee1-136">**Contenedor:** Un contenedor proporciona una agrupación de un conjunto de blobs y puede almacenar un número ilimitado de blobs.</span><span class="sxs-lookup"><span data-stu-id="6aee1-136">**Container:** A container provides a grouping of a set of Blobs, and can store an unlimited number of Blobs.</span></span> <span data-ttu-id="6aee1-137">Para escribir una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] copia de seguridad en Azure BLOB Service, debe haber creado al menos el contenedor raíz.</span><span class="sxs-lookup"><span data-stu-id="6aee1-137">To write a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to the Azure Blob service, you must have at least the root container created.</span></span>  
  
 <span data-ttu-id="6aee1-138">**Blob:** Un archivo de cualquier tipo y tamaño.</span><span class="sxs-lookup"><span data-stu-id="6aee1-138">**Blob:** A file of any type and size.</span></span> <span data-ttu-id="6aee1-139">Hay dos tipos de blobs que se pueden almacenar en el servicio de almacenamiento de blobs de Azure: blobs en bloques y en páginas.</span><span class="sxs-lookup"><span data-stu-id="6aee1-139">There are two types of blobs that can be stored in the Azure Blob storage service: block and page blobs.</span></span> <span data-ttu-id="6aee1-140">La copia de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa blobs en páginas como tipo de blob.</span><span class="sxs-lookup"><span data-stu-id="6aee1-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup uses page Blobs as the Blob type.</span></span> <span data-ttu-id="6aee1-141">Los blobs son direccionables mediante el siguiente formato de dirección URL: https:// \<storage account> . BLOB.Core.Windows.net/\<container>/\<blob></span><span class="sxs-lookup"><span data-stu-id="6aee1-141">Blobs are addressable using the following URL format: https://\<storage account>.blob.core.windows.net/\<container>/\<blob></span></span>  
  
 <span data-ttu-id="6aee1-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span><span class="sxs-lookup"><span data-stu-id="6aee1-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span></span>  
  
 <span data-ttu-id="6aee1-143">Para obtener más información sobre el servicio Azure BLOB Storage, consulte [uso del servicio de Azure BLOB Storage](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span><span class="sxs-lookup"><span data-stu-id="6aee1-143">For more information about the Azure Blob storage service, see [How to use the Azure Blob Storage Service](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span></span>  
  
 <span data-ttu-id="6aee1-144">Para más información sobre los blobs en páginas, consulte la [descripción de los blobs en bloques y en páginas](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span><span class="sxs-lookup"><span data-stu-id="6aee1-144">For more information about page Blobs, see [Understanding Block and Page Blobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span></span>  
  
###  <a name="ssnoversion-components"></a><span data-ttu-id="6aee1-145">Componentes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de <a name="sqlserver"></a></span><span class="sxs-lookup"><span data-stu-id="6aee1-145"><a name="sqlserver"></a> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components</span></span>  
 <span data-ttu-id="6aee1-146">**Dirección URL:** Una dirección URL especifica un identificador uniforme de recursos (URI) para un archivo de copia de seguridad único.</span><span class="sxs-lookup"><span data-stu-id="6aee1-146">**URL:** A URL specifies a Uniform Resource Identifier (URI) to a unique backup file.</span></span> <span data-ttu-id="6aee1-147">La dirección URL se emplea para proporcionar la ubicación y el nombre del archivo de copia de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6aee1-147">The URL is used to provide the location and name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup file.</span></span> <span data-ttu-id="6aee1-148">En esta implementación, la única dirección URL válida es aquella que señala a un BLOB en páginas en una cuenta de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="6aee1-148">In this implementation, the only valid URL is one that points to a page Blob in an Azure storage account.</span></span> <span data-ttu-id="6aee1-149">La dirección URL debe apuntar a un blob real, no solo a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="6aee1-149">The URL must point to an actual Blob, not just a container.</span></span> <span data-ttu-id="6aee1-150">Si el blob no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="6aee1-150">If the Blob does not exist, it is created.</span></span> <span data-ttu-id="6aee1-151">Si se especifica un BLOB existente, se produce un error en la copia de seguridad, a menos que se especifique la opción "WITH FORMAT".</span><span class="sxs-lookup"><span data-stu-id="6aee1-151">If an existing Blob is specified, BACKUP fails, unless the "WITH FORMAT" option is specified.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="6aee1-152">Si elige copiar y cargar un archivo de copia de seguridad en el servicio de almacenamiento de blobs de Azure, use el BLOB en páginas como opción de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6aee1-152">If you choose to copy and upload a backup file to the Azure Blob storage service, use page blob as your storage option.</span></span> <span data-ttu-id="6aee1-153">No se admiten restauraciones desde blobs en bloques.</span><span class="sxs-lookup"><span data-stu-id="6aee1-153">Restores from Block Blobs are not supported.</span></span> <span data-ttu-id="6aee1-154">La instrucción RESTORE desde un tipo de blob en bloques produce un error.</span><span class="sxs-lookup"><span data-stu-id="6aee1-154">RESTORE from a block blob type fails with an error.</span></span>  
  
 <span data-ttu-id="6aee1-155">Este es un valor de dirección URL de ejemplo: http [s]://ACCOUNTNAME.Blob.core.windows.net/ \<CONTAINER> / \<FILENAME.bak> .</span><span class="sxs-lookup"><span data-stu-id="6aee1-155">Here is a sample URL value: http[s]://ACCOUNTNAME.Blob.core.windows.net/\<CONTAINER>/\<FILENAME.bak>.</span></span> <span data-ttu-id="6aee1-156">HTTPS no es necesario, pero es recomendable.</span><span class="sxs-lookup"><span data-stu-id="6aee1-156">HTTPS is not required, but is recommended.</span></span>  
  
 <span data-ttu-id="6aee1-157">**Credencial:** Una credencial de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un objeto que se usa para almacenar la información de autenticación necesaria para conectarse a un recurso fuera de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aee1-157">**Credential:** A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="6aee1-158">Aquí, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los procesos de copia de seguridad y restauración usan credenciales para autenticarse en el servicio de almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="6aee1-158">Here, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="6aee1-159">La credencial contiene los valores de nombre y la **clave de acceso** de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6aee1-159">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="6aee1-160">Una vez creada la credencial, se debe especificar en la opción WITH CREDENTIAL al emitir las instrucciones BACKUP y RESTORE.</span><span class="sxs-lookup"><span data-stu-id="6aee1-160">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="6aee1-161">Para obtener más información sobre cómo ver, copiar o regenerar **access keys**de cuentas de almacenamiento, vea [Ver, copiar y regenerar las claves de acceso de una cuenta de almacenamiento de Windows Azure](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="6aee1-161">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="6aee1-162">Para obtener instrucciones paso a paso sobre cómo crear una credencial de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea el ejemplo de [Create a Credential](#credential) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="6aee1-162">For step by step instructions about how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential, see [Create a Credential](#credential) example later in this topic.</span></span>  
  
 <span data-ttu-id="6aee1-163">Para obtener información general sobre las credenciales, vea [Credenciales](../security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="6aee1-163">For general information about credentials, see [Credentials](../security/authentication-access/credentials-database-engine.md)</span></span>  
  
 <span data-ttu-id="6aee1-164">Para obtener información sobre otros ejemplos donde se usan credenciales, consulte [creación de un proxy de Agente SQL Server](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="6aee1-164">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
###  <a name="limitations"></a><a name="limitations"></a> <span data-ttu-id="6aee1-165">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="6aee1-165">Limitations</span></span>  
  
-   <span data-ttu-id="6aee1-166">No se pueden realizar copias de seguridad en el almacenamiento premium.</span><span class="sxs-lookup"><span data-stu-id="6aee1-166">Backup to premium storage is not supported.</span></span>  
  
-   <span data-ttu-id="6aee1-167">El tamaño máximo de copia de seguridad admitido es 1 TB.</span><span class="sxs-lookup"><span data-stu-id="6aee1-167">The maximum backup size supported is 1 TB.</span></span>  
  
-   <span data-ttu-id="6aee1-168">Puede emitir instrucciones de copia de seguridad o de restauración mediante cmdlets de PowerShell, SMO o TSQL.</span><span class="sxs-lookup"><span data-stu-id="6aee1-168">You can issue backup or restore statements by using TSQL, SMO, or PowerShell cmdlets.</span></span> <span data-ttu-id="6aee1-169">Actualmente no está habilitada la copia de seguridad o la restauración desde el servicio de almacenamiento de blobs de Azure mediante SQL Server Management Studio Asistente para copia de seguridad o restauración.</span><span class="sxs-lookup"><span data-stu-id="6aee1-169">A backup to or restoring from the Azure Blob storage service by using SQL Server Management Studio Backup or Restore wizard is not currently enabled.</span></span>  
  
-   <span data-ttu-id="6aee1-170">No se admite la creación de un nombre de dispositivo lógico.</span><span class="sxs-lookup"><span data-stu-id="6aee1-170">Creating a logical device name is not supported.</span></span> <span data-ttu-id="6aee1-171">Por tanto, no se admite agregar URL como dispositivo de copia de seguridad mediante sp_dumpdevice o mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="6aee1-171">So adding URL as a backup device using sp_dumpdevice or through SQL Server Management Studio is not supported.</span></span>  
  
-   <span data-ttu-id="6aee1-172">No se admite anexar a blobs de copia de seguridad existentes.</span><span class="sxs-lookup"><span data-stu-id="6aee1-172">Appending to existing backup blobs is not supported.</span></span> <span data-ttu-id="6aee1-173">Las copias de seguridad en un blob existente solo se pueden sobrescribir mediante la opción WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="6aee1-173">Backups to an existing Blob can only be overwritten by using the WITH FORMAT option.</span></span>  
  
-   <span data-ttu-id="6aee1-174">No se admite la copia de seguridad en varios blobs en una sola operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-174">Backup to multiple blobs in a single backup operation is not supported.</span></span> <span data-ttu-id="6aee1-175">Por ejemplo, el código siguiente devuelve un error:</span><span class="sxs-lookup"><span data-stu-id="6aee1-175">For example, the following returns an error:</span></span>  
  
    ```sql
    BACKUP DATABASE AdventureWorks2012
    TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_1.bak'
       URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_2.bak'
          WITH CREDENTIAL = 'mycredential'
         ,STATS = 5;  
    GO
    ```  
  
-   <span data-ttu-id="6aee1-176">No se admite especificar un tamaño de bloque con `BACKUP`.</span><span class="sxs-lookup"><span data-stu-id="6aee1-176">Specifying a block size with `BACKUP` is not supported.</span></span>  
  
-   <span data-ttu-id="6aee1-177">No se admite especificar `MAXTRANSFERSIZE`.</span><span class="sxs-lookup"><span data-stu-id="6aee1-177">Specifying `MAXTRANSFERSIZE` is not supported.</span></span>  
  
-   <span data-ttu-id="6aee1-178">No se admite especificar opciones de conjunto de copia de seguridad, `RETAINDAYS` y `EXPIREDATE`.</span><span class="sxs-lookup"><span data-stu-id="6aee1-178">Specifying backupset options - `RETAINDAYS` and `EXPIREDATE` are not supported.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6aee1-179">tiene un límite máximo de 259 caracteres para un nombre de dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-179">has a maximum limit of 259 characters for a backup device name.</span></span> <span data-ttu-id="6aee1-180">BACKUP TO URL consume 36 caracteres para los elementos necesarios que se usan para especificar la dirección URL: "https://.blob.core.windows.net//.bak", y deja 223 caracteres para la cuenta, el contenedor y los nombres de blob.</span><span class="sxs-lookup"><span data-stu-id="6aee1-180">The BACKUP TO URL consumes 36 characters for the required elements used to specify the URL - 'https://.blob.core.windows.net//.bak', leaving 223 characters for account, container, and blob names put together.</span></span>  
  
###  <a name="support-for-backuprestore-statements"></a><a name="Support"></a> <span data-ttu-id="6aee1-181">Compatibilidad con instrucciones BACKUP y RESTORE</span><span class="sxs-lookup"><span data-stu-id="6aee1-181">Support for Backup/Restore Statements</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="6aee1-182">Instrucción BACKUP/RESTORE</span><span class="sxs-lookup"><span data-stu-id="6aee1-182">Backup/Restore Statement</span></span>|<span data-ttu-id="6aee1-183">Compatible</span><span class="sxs-lookup"><span data-stu-id="6aee1-183">Supported</span></span>|<span data-ttu-id="6aee1-184">Excepciones</span><span class="sxs-lookup"><span data-stu-id="6aee1-184">Exceptions</span></span>|<span data-ttu-id="6aee1-185">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6aee1-185">Comments</span></span>|  
|<span data-ttu-id="6aee1-186">BACKUP</span><span class="sxs-lookup"><span data-stu-id="6aee1-186">BACKUP</span></span>|<span data-ttu-id="6aee1-187">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-187">&#x2713;</span></span>|<span data-ttu-id="6aee1-188">No se admiten BLOCKSIZE y MAXTRANSFERSIZE.</span><span class="sxs-lookup"><span data-stu-id="6aee1-188">BLOCKSIZE, and MAXTRANSFERSIZE are not supported.</span></span>|<span data-ttu-id="6aee1-189">Es necesario especificar WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-189">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="6aee1-190">RESTORE</span><span class="sxs-lookup"><span data-stu-id="6aee1-190">RESTORE</span></span>|<span data-ttu-id="6aee1-191">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-191">&#x2713;</span></span>||<span data-ttu-id="6aee1-192">Es necesario especificar WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-192">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="6aee1-193">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="6aee1-193">RESTORE FILELISTONLY</span></span>|<span data-ttu-id="6aee1-194">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-194">&#x2713;</span></span>||<span data-ttu-id="6aee1-195">Es necesario especificar WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-195">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="6aee1-196">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="6aee1-196">RESTORE HEADERONLY</span></span>|<span data-ttu-id="6aee1-197">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-197">&#x2713;</span></span>||<span data-ttu-id="6aee1-198">Es necesario especificar WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-198">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="6aee1-199">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="6aee1-199">RESTORE LABELONLY</span></span>|<span data-ttu-id="6aee1-200">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-200">&#x2713;</span></span>||<span data-ttu-id="6aee1-201">Es necesario especificar WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-201">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="6aee1-202">RESTORE VERIFYONLY</span><span class="sxs-lookup"><span data-stu-id="6aee1-202">RESTORE VERIFYONLY</span></span>|<span data-ttu-id="6aee1-203">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-203">&#x2713;</span></span>||<span data-ttu-id="6aee1-204">Es necesario especificar WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-204">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="6aee1-205">RESTORE REWINDONLY</span><span class="sxs-lookup"><span data-stu-id="6aee1-205">RESTORE REWINDONLY</span></span>|<span data-ttu-id="6aee1-206">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-206">&#x2713;</span></span>|||  
  
 <span data-ttu-id="6aee1-207">Para conocer la sintaxis y obtener información general sobre las instrucciones de copia de seguridad, vea [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aee1-207">For syntax and general information about backup statements, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="6aee1-208">Para conocer la sintaxis y obtener información general sobre las instrucciones de restauración, vea [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aee1-208">For syntax and general information about restore statements, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
### <a name="support-for-backup-arguments"></a><span data-ttu-id="6aee1-209">Compatibilidad con los argumentos de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6aee1-209">Support for Backup Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="6aee1-210">Argumento</span><span class="sxs-lookup"><span data-stu-id="6aee1-210">Argument</span></span>|<span data-ttu-id="6aee1-211">Compatible</span><span class="sxs-lookup"><span data-stu-id="6aee1-211">Supported</span></span>|<span data-ttu-id="6aee1-212">Excepción</span><span class="sxs-lookup"><span data-stu-id="6aee1-212">Exception</span></span>|<span data-ttu-id="6aee1-213">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6aee1-213">Comments</span></span>|  
|<span data-ttu-id="6aee1-214">DATABASE</span><span class="sxs-lookup"><span data-stu-id="6aee1-214">DATABASE</span></span>|<span data-ttu-id="6aee1-215">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-215">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-216">REGISTRO</span><span class="sxs-lookup"><span data-stu-id="6aee1-216">LOG</span></span>|<span data-ttu-id="6aee1-217">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-217">&#x2713;</span></span>|||  
||  
|<span data-ttu-id="6aee1-218">TO (URL)</span><span class="sxs-lookup"><span data-stu-id="6aee1-218">TO (URL)</span></span>|<span data-ttu-id="6aee1-219">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-219">&#x2713;</span></span>|<span data-ttu-id="6aee1-220">A diferencia de DISK y TAPE, URL no admite especificar o crear un nombre lógico.</span><span class="sxs-lookup"><span data-stu-id="6aee1-220">Unlike DISK and TAPE, URL does not support specifying or creating a logical name.</span></span>|<span data-ttu-id="6aee1-221">Este argumento se emplea para especificar la ruta de acceso de la dirección URL del archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-221">This argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="6aee1-222">MIRROR TO</span><span class="sxs-lookup"><span data-stu-id="6aee1-222">MIRROR TO</span></span>|<span data-ttu-id="6aee1-223">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-223">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-224">**OPCIONES DE WITH:**</span><span class="sxs-lookup"><span data-stu-id="6aee1-224">**WITH OPTIONS:**</span></span>||||  
|<span data-ttu-id="6aee1-225">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-225">CREDENTIAL</span></span>|<span data-ttu-id="6aee1-226">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-226">&#x2713;</span></span>||<span data-ttu-id="6aee1-227">WITH CREDENTIAL solo se admite cuando se usa la opción BACKUP TO URL para hacer una copia de seguridad en el servicio Azure BLOB Storage.</span><span class="sxs-lookup"><span data-stu-id="6aee1-227">WITH CREDENTIAL is only supported when using BACKUP TO URL option to back up to the Azure Blob storage service.</span></span>|  
|<span data-ttu-id="6aee1-228">DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-228">DIFFERENTIAL</span></span>|<span data-ttu-id="6aee1-229">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-229">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-230">COPY_ONLY</span><span class="sxs-lookup"><span data-stu-id="6aee1-230">COPY_ONLY</span></span>|<span data-ttu-id="6aee1-231">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-231">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-232">COMPRESSION&#124;NO_COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="6aee1-232">COMPRESSION&#124;NO_COMPRESSION</span></span>|<span data-ttu-id="6aee1-233">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-233">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-234">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6aee1-234">DESCRIPTION</span></span>|<span data-ttu-id="6aee1-235">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-235">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-236">NAME</span><span class="sxs-lookup"><span data-stu-id="6aee1-236">NAME</span></span>|<span data-ttu-id="6aee1-237">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-237">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-238">EXPIREDATE &#124; RETAINDAYS</span><span class="sxs-lookup"><span data-stu-id="6aee1-238">EXPIREDATE &#124; RETAINDAYS</span></span>|<span data-ttu-id="6aee1-239">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-239">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-240">NOINIT &#124; INIT</span><span class="sxs-lookup"><span data-stu-id="6aee1-240">NOINIT &#124; INIT</span></span>|<span data-ttu-id="6aee1-241">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-241">&#x2713;</span></span>||<span data-ttu-id="6aee1-242">Esta opción se omite si se usa.</span><span class="sxs-lookup"><span data-stu-id="6aee1-242">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="6aee1-243">No es posible anexar a blobs.</span><span class="sxs-lookup"><span data-stu-id="6aee1-243">Appending to blobs is not possible.</span></span> <span data-ttu-id="6aee1-244">Para sobrescribir una copia de seguridad, use el argumento FORMAT.</span><span class="sxs-lookup"><span data-stu-id="6aee1-244">To overwrite a backup use the FORMAT argument.</span></span>|  
|<span data-ttu-id="6aee1-245">NOSKIP &#124; SKIP</span><span class="sxs-lookup"><span data-stu-id="6aee1-245">NOSKIP &#124; SKIP</span></span>|<span data-ttu-id="6aee1-246">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-246">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-247">NOFORMAT &#124; FORMAT</span><span class="sxs-lookup"><span data-stu-id="6aee1-247">NOFORMAT &#124; FORMAT</span></span>|<span data-ttu-id="6aee1-248">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-248">&#x2713;</span></span>||<span data-ttu-id="6aee1-249">Esta opción se omite si se usa.</span><span class="sxs-lookup"><span data-stu-id="6aee1-249">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="6aee1-250">Una copia de seguridad realizada en un blob existente producirá un error a menos que se especifique WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="6aee1-250">A backup taken to an existing blob fails unless WITH FORMAT is specified.</span></span> <span data-ttu-id="6aee1-251">Se sobrescribe el blob existente si se especifica WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="6aee1-251">The existing blob is overwritten when WITH FORMAT is specified.</span></span>|  
|<span data-ttu-id="6aee1-252">MEDIADESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6aee1-252">MEDIADESCRIPTION</span></span>|<span data-ttu-id="6aee1-253">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-253">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-254">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="6aee1-254">MEDIANAME</span></span>|<span data-ttu-id="6aee1-255">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-255">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-256">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="6aee1-256">BLOCKSIZE</span></span>|<span data-ttu-id="6aee1-257">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-257">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-258">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="6aee1-258">BUFFERCOUNT</span></span>|<span data-ttu-id="6aee1-259">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-259">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-260">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="6aee1-260">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="6aee1-261">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-261">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-262">NO_CHECKSUM &#124; CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="6aee1-262">NO_CHECKSUM &#124; CHECKSUM</span></span>|<span data-ttu-id="6aee1-263">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-263">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="6aee1-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="6aee1-265">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-265">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-266">STATS</span><span class="sxs-lookup"><span data-stu-id="6aee1-266">STATS</span></span>|<span data-ttu-id="6aee1-267">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-267">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-268">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="6aee1-268">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="6aee1-269">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-269">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-270">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="6aee1-270">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="6aee1-271">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-271">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-272">NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="6aee1-272">NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="6aee1-273">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-273">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-274">NO_TRUNCATE</span><span class="sxs-lookup"><span data-stu-id="6aee1-274">NO_TRUNCATE</span></span>|<span data-ttu-id="6aee1-275">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-275">&#x2713;</span></span>|||  
  
 <span data-ttu-id="6aee1-276">Para obtener más información sobre los argumentos de copia de seguridad, vea [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aee1-276">For more information about backup arguments, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="support-for-restore-arguments"></a><span data-ttu-id="6aee1-277">Compatibilidad con los argumentos de restauración</span><span class="sxs-lookup"><span data-stu-id="6aee1-277">Support for Restore Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="6aee1-278">Argumento</span><span class="sxs-lookup"><span data-stu-id="6aee1-278">Argument</span></span>|<span data-ttu-id="6aee1-279">Compatible</span><span class="sxs-lookup"><span data-stu-id="6aee1-279">Supported</span></span>|<span data-ttu-id="6aee1-280">Excepciones</span><span class="sxs-lookup"><span data-stu-id="6aee1-280">Exceptions</span></span>|<span data-ttu-id="6aee1-281">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6aee1-281">Comments</span></span>|  
|<span data-ttu-id="6aee1-282">DATABASE</span><span class="sxs-lookup"><span data-stu-id="6aee1-282">DATABASE</span></span>|<span data-ttu-id="6aee1-283">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-283">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-284">REGISTRO</span><span class="sxs-lookup"><span data-stu-id="6aee1-284">LOG</span></span>|<span data-ttu-id="6aee1-285">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-285">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-286">FROM (URL)</span><span class="sxs-lookup"><span data-stu-id="6aee1-286">FROM (URL)</span></span>|<span data-ttu-id="6aee1-287">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-287">&#x2713;</span></span>||<span data-ttu-id="6aee1-288">El argumento FROM URL se emplea para especificar la ruta de acceso de la dirección URL del archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-288">The FROM URL argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="6aee1-289">**WITH Options:**</span><span class="sxs-lookup"><span data-stu-id="6aee1-289">**WITH Options:**</span></span>||||  
|<span data-ttu-id="6aee1-290">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-290">CREDENTIAL</span></span>|<span data-ttu-id="6aee1-291">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-291">&#x2713;</span></span>||<span data-ttu-id="6aee1-292">WITH CREDENTIAL solo se admite cuando se usa la opción RESTOre FROM URL para restaurar desde Azure Blob Storage Service.</span><span class="sxs-lookup"><span data-stu-id="6aee1-292">WITH CREDENTIAL is only supported when using RESTORE FROM URL option to restore from Azure Blob Storage service.</span></span>|  
|<span data-ttu-id="6aee1-293">PARTIAL</span><span class="sxs-lookup"><span data-stu-id="6aee1-293">PARTIAL</span></span>|<span data-ttu-id="6aee1-294">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-294">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="6aee1-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="6aee1-296">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-296">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-297">LOADHISTORY</span><span class="sxs-lookup"><span data-stu-id="6aee1-297">LOADHISTORY</span></span>|<span data-ttu-id="6aee1-298">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-298">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-299">MOVE</span><span class="sxs-lookup"><span data-stu-id="6aee1-299">MOVE</span></span>|<span data-ttu-id="6aee1-300">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-300">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-301">REPLACE</span><span class="sxs-lookup"><span data-stu-id="6aee1-301">REPLACE</span></span>|<span data-ttu-id="6aee1-302">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-302">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-303">RESTART</span><span class="sxs-lookup"><span data-stu-id="6aee1-303">RESTART</span></span>|<span data-ttu-id="6aee1-304">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-304">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-305">RESTRICTED_USER</span><span class="sxs-lookup"><span data-stu-id="6aee1-305">RESTRICTED_USER</span></span>|<span data-ttu-id="6aee1-306">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-306">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-307">FILE</span><span class="sxs-lookup"><span data-stu-id="6aee1-307">FILE</span></span>|<span data-ttu-id="6aee1-308">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-308">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-309">PASSWORD</span><span class="sxs-lookup"><span data-stu-id="6aee1-309">PASSWORD</span></span>|<span data-ttu-id="6aee1-310">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-310">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-311">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="6aee1-311">MEDIANAME</span></span>|<span data-ttu-id="6aee1-312">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-312">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-313">MEDIAPASSWORD</span><span class="sxs-lookup"><span data-stu-id="6aee1-313">MEDIAPASSWORD</span></span>|<span data-ttu-id="6aee1-314">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-314">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-315">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="6aee1-315">BLOCKSIZE</span></span>|<span data-ttu-id="6aee1-316">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-316">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-317">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="6aee1-317">BUFFERCOUNT</span></span>|<span data-ttu-id="6aee1-318">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-318">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-319">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="6aee1-319">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="6aee1-320">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-320">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-321">CHECKSUM &#124; NO_CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="6aee1-321">CHECKSUM &#124; NO_CHECKSUM</span></span>|<span data-ttu-id="6aee1-322">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-322">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="6aee1-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="6aee1-324">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-324">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-325">FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="6aee1-325">FILESTREAM</span></span>|<span data-ttu-id="6aee1-326">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-326">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-327">STATS</span><span class="sxs-lookup"><span data-stu-id="6aee1-327">STATS</span></span>|<span data-ttu-id="6aee1-328">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-328">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-329">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="6aee1-329">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="6aee1-330">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-330">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-331">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="6aee1-331">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="6aee1-332">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-332">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-333">KEEP_REPLICATION</span><span class="sxs-lookup"><span data-stu-id="6aee1-333">KEEP_REPLICATION</span></span>|<span data-ttu-id="6aee1-334">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-334">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-335">KEEP_CDC</span><span class="sxs-lookup"><span data-stu-id="6aee1-335">KEEP_CDC</span></span>|<span data-ttu-id="6aee1-336">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-336">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span><span class="sxs-lookup"><span data-stu-id="6aee1-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span></span>|<span data-ttu-id="6aee1-338">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-338">&#x2713;</span></span>|||  
|<span data-ttu-id="6aee1-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span><span class="sxs-lookup"><span data-stu-id="6aee1-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span></span>|<span data-ttu-id="6aee1-340">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="6aee1-340">&#x2713;</span></span>|||  
  
 <span data-ttu-id="6aee1-341">Para obtener más información sobre los argumentos de restauración, vea [RESTORE &#40;argumentos, Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aee1-341">For more information about Restore arguments, see [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
##  <a name="using-backup-task-in-sql-server-management-studio"></a><a name="BackupTaskSSMS"></a><span data-ttu-id="6aee1-342">Uso de la tarea de copia de seguridad en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6aee1-342">Using Backup Task in SQL Server Management Studio</span></span>  
 <span data-ttu-id="6aee1-343">La tarea de copia de seguridad de SQL Server Management Studio se ha mejorado para incluir la dirección URL como una de las opciones de destino y otros objetos de compatibilidad necesarios para realizar la copia de seguridad en Azure Storage, como la credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="6aee1-343">The Backup task in SQL Server Management Studio has been enhanced to include URL as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span>  
  
 <span data-ttu-id="6aee1-344">En los pasos siguientes se describen los cambios realizados en la tarea copia de seguridad de base de datos para permitir realizar copias de seguridad en Azure Storage:</span><span class="sxs-lookup"><span data-stu-id="6aee1-344">The following steps describe the changes made to the Back Up Database task to allow for backing up to Azure storage.:</span></span>  
  
1.  <span data-ttu-id="6aee1-345">Inicie SQL Server Management Studio y conéctese a una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aee1-345">Start SQL Server Management Studio and connect to the SQL Server instance.</span></span>  <span data-ttu-id="6aee1-346">Seleccione una base de datos de la que desee hacer una copia de seguridad, haga clic con el botón derecho en **tareas**y seleccione **copia de seguridad..**. Se abrirá el cuadro de diálogo copia de seguridad de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6aee1-346">Select a database you want to backup, and right click on **Tasks**, and select **Back Up..**. This opens the Back Up Database dialog box.</span></span>  
  
2.  <span data-ttu-id="6aee1-347">En la página general, se usa la opción **dirección URL** para crear una copia de seguridad en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="6aee1-347">On the general page the **URL** option is used to create a backup to Azure storage.</span></span> <span data-ttu-id="6aee1-348">Al seleccionar esta opción, se ven otras opciones habilitadas en esta página:</span><span class="sxs-lookup"><span data-stu-id="6aee1-348">When you select this option, you see other options enabled on this page:</span></span>  
  
    1.  <span data-ttu-id="6aee1-349">**Nombre de archivo:** nombre del archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-349">**File Name:** Name of the backup file.</span></span>  
  
    2.  <span data-ttu-id="6aee1-350">**Credencial SQL:** puede especificar una credencial existente de SQL Server o crear una nueva haciendo clic en **Crear** , junto al cuadro Credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="6aee1-350">**SQL Credential:** You can either specify an existing SQL Server Credential, or can create a new one by clicking on the **Create** next to the SQL Credential box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="6aee1-351">El cuadro de diálogo que se abre al hacer clic en **Crear** requiere un certificado de administración o el perfil de publicación para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="6aee1-351">The dialog that opens when you click **Create** requires a management certificate or the publishing profile for the subscription.</span></span> <span data-ttu-id="6aee1-352">SQL Server admite actualmente la versión 2.0 del perfil de publicación.</span><span class="sxs-lookup"><span data-stu-id="6aee1-352">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="6aee1-353">Para descargar la versión compatible del perfil de publicación, vea [Descargar perfil de publicación 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="6aee1-353">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
        >   
        >  <span data-ttu-id="6aee1-354">Si no tiene acceso al certificado de administración o al perfil de publicación, puede crear una credencial de SQL; para ello, especifique la información del nombre de cuenta de almacenamiento y de clave de acceso mediante Transact-SQL o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="6aee1-354">If you do not have access to the management certificate or publishing profile, you can create a SQL Credential by specifying the storage account name and access key information using Transact-SQL or SQL Server Management Studio.</span></span> <span data-ttu-id="6aee1-355">Vea el código de ejemplo de la sección [Crear una credencial](#credential) para crear una credencial mediante Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="6aee1-355">See the sample code in the [Create a Credential](#credential) section to create a credential using Transact-SQL.</span></span> <span data-ttu-id="6aee1-356">O bien, con SQL Server Management Studio, desde el motor de base de datos, haga clic con el botón secundario en **Seguridad**, seleccione **Nuevo**y **Credencial**.</span><span class="sxs-lookup"><span data-stu-id="6aee1-356">Alternatively, using SQL Server Management Studio, from the database engine instance, right click **Security**, select **New**, and select **Credential**.</span></span> <span data-ttu-id="6aee1-357">Especifique el nombre de cuenta de almacenamiento para **Identidad** y la clave de acceso en el campo **Contraseña** .</span><span class="sxs-lookup"><span data-stu-id="6aee1-357">Specify the storage account name for **Identity** and the access key in the **Password** field.</span></span>  
  
    3.  <span data-ttu-id="6aee1-358">**Contenedor de Azure Storage:** Nombre del contenedor de almacenamiento de Azure en el que se almacenarán los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-358">**Azure storage container:** The name of the Azure storage container to store the backup files.</span></span>  
  
    4.  <span data-ttu-id="6aee1-359">**Prefijo de dirección URL:** se genera automáticamente con la información especificada en los campos que se describen en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6aee1-359">**URL prefix:** This is built automatically using the information specified in the fields described in the previous steps.</span></span> <span data-ttu-id="6aee1-360">Si edita este valor manualmente, asegúrese de que coincide con el resto de la información que proporcionó antes.</span><span class="sxs-lookup"><span data-stu-id="6aee1-360">If you do edit this value manually, make sure it matches with the other information you provided previously.</span></span> <span data-ttu-id="6aee1-361">Por ejemplo, si modifica la dirección URL de almacenamiento, asegúrese de que la credencial SQL está establecida para autenticar en la misma cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6aee1-361">For example if you modify the storage URL, make sure the SQL Credential is set to authenticate to the same storage account.</span></span>  
  
 <span data-ttu-id="6aee1-362">Al seleccionar Dirección URL como destino, ciertas opciones de la página **Opciones multimedia** están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="6aee1-362">When you select URL as the destination, certain options in the **Media Options** page are disabled.</span></span>  <span data-ttu-id="6aee1-363">Los temas siguientes tienen más información acerca del cuadro de diálogo Copia de seguridad de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="6aee1-363">The following topics have more information on the Back Up Database dialog:</span></span>  
  
 [<span data-ttu-id="6aee1-364">Copia de seguridad de base de datos &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="6aee1-364">Back Up Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
 [<span data-ttu-id="6aee1-365">Copia de seguridad de la base de datos &#40;página Opciones multimedia&#41;</span><span class="sxs-lookup"><span data-stu-id="6aee1-365">Back Up Database &#40;Media Options Page&#41;</span></span>](back-up-database-media-options-page.md)  
  
 [<span data-ttu-id="6aee1-366">Copia de seguridad de la base de datos &#40;página Opciones de copia de seguridad&#41;</span><span class="sxs-lookup"><span data-stu-id="6aee1-366">Back Up Database &#40;Backup Options Page&#41;</span></span>](back-up-database-backup-options-page.md)  
  
 [<span data-ttu-id="6aee1-367">Crear credencial - autenticarse en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="6aee1-367">Create Credential - Authenticate to Azure Storage</span></span>](create-credential-authenticate-to-azure-storage.md)  
  
##  <a name="sql-server-backup-to-url-using-maintenance-plan-wizard"></a><a name="MaintenanceWiz"></a><span data-ttu-id="6aee1-368">SQL Server realizar copia de seguridad en URL mediante el Asistente para planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="6aee1-368">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>  
 <span data-ttu-id="6aee1-369">Al igual que la tarea de copia de seguridad descrita anteriormente, el Asistente para planes de mantenimiento de SQL Server Management Studio se ha mejorado para incluir la **dirección URL** como una de las opciones de destino y otros objetos de compatibilidad necesarios para realizar la copia de seguridad en Azure Storage, como la credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="6aee1-369">Similar to the backup task described previously, the Maintenance Plan Wizard in SQL Server Management Studio has been enhanced to include **URL** as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span> <span data-ttu-id="6aee1-370">Para obtener más información, consulte la sección **Definir las tareas de copia de seguridad** en [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span><span class="sxs-lookup"><span data-stu-id="6aee1-370">For more information, see  the **Define Backup Tasks** section in [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span></span>  
  
##  <a name="restoring-from-azure-storage-using-sql-server-management-studio"></a><a name="RestoreSSMS"></a><span data-ttu-id="6aee1-371">Restauración desde Azure Storage mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6aee1-371">Restoring from Azure storage Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6aee1-372">Si restaura una base de datos, **Dirección URL** se incluye como dispositivo desde el que restaurar.</span><span class="sxs-lookup"><span data-stu-id="6aee1-372">If you are restoring a database, **URL** is included as the device to restore from.</span></span> <span data-ttu-id="6aee1-373">En los pasos siguientes se describen los cambios en la tarea de restauración para permitir la restauración desde Azure Storage:</span><span class="sxs-lookup"><span data-stu-id="6aee1-373">Following steps describe the changes in the Restore task to allow restoring from Azure storage:</span></span>  
  
1.  <span data-ttu-id="6aee1-374">Al seleccionar **Dispositivos** en la página **General** de la tarea Restaurar en SQL Server Management Studio, se le llevará al cuadro de diálogo **Seleccionar dispositivos de copia de seguridad** que incluye **Dirección URL** como tipo de medio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6aee1-374">When you select **Devices** in the **General** page of the Restore task in SQL Server Management Studio, this takes you to the **Select backup devices** dialog box which includes **URL** as a backup media type.</span></span>  
  
2.  <span data-ttu-id="6aee1-375">Al seleccionar **Dirección URL** y hacer clic en **Agregar**, se abre el cuadro de diálogo **Conectar al almacenamiento de Windows Azure** .</span><span class="sxs-lookup"><span data-stu-id="6aee1-375">When you select **URL** and click **Add**, this opens the **Connect to Azure storage** dialog.</span></span> <span data-ttu-id="6aee1-376">Especifique la información de la credencial SQL para autenticarse en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="6aee1-376">Specify the SQL Credential information to authenticate to Azure storage.</span></span>  
  
3.  <span data-ttu-id="6aee1-377">A continuación, SQL Server se conecta a Azure Storage con la información de la credencial SQL proporcionada y abre el cuadro **de diálogo Buscar archivo de copia de seguridad en Azure** .</span><span class="sxs-lookup"><span data-stu-id="6aee1-377">SQL Server then connects to Azure storage using the SQL Credential information you provided and opens the **Locate Backup File in Azure** dialog.</span></span> <span data-ttu-id="6aee1-378">Los archivos de copia de seguridad que residen en el almacenamiento se muestran en esta página.</span><span class="sxs-lookup"><span data-stu-id="6aee1-378">The backup files residing in the storage are displayed on this page.</span></span> <span data-ttu-id="6aee1-379">Seleccione el archivo que desee usar para restaurar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aee1-379">Select the file you want to use to restore and click **OK**.</span></span> <span data-ttu-id="6aee1-380">De esta forma, vuelve al cuadro de diálogo **Seleccionar dispositivos de copia de seguridad** y, haciendo clic en **Aceptar** en este cuadro de diálogo, vuelve al cuadro de diálogo principal **Restaurar** donde podrá completar la restauración.</span><span class="sxs-lookup"><span data-stu-id="6aee1-380">This takes you back to the **Select Backup Devices** dialog, and Clicking **OK** on this dialog takes you back to the main **Restore** dialog where you will be able complete the restore.</span></span>  <span data-ttu-id="6aee1-381">Para obtener más información, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6aee1-381">For more information see, the following topics:</span></span>  
  
     [<span data-ttu-id="6aee1-382">Restaurar la base de datos &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="6aee1-382">Restore Database &#40;General Page&#41;</span></span>](restore-database-general-page.md)  
  
     [<span data-ttu-id="6aee1-383">Restaurar base de datos &#40;página Archivos&#41;</span><span class="sxs-lookup"><span data-stu-id="6aee1-383">Restore Database &#40;Files Page&#41;</span></span>](restore-database-files-page.md)  
  
     [<span data-ttu-id="6aee1-384">Restaurar base de datos &#40;página Opciones&#41;</span><span class="sxs-lookup"><span data-stu-id="6aee1-384">Restore Database &#40;Options Page&#41;</span></span>](restore-database-options-page.md)  
  
##  <a name="code-examples"></a><a name="Examples"></a> <span data-ttu-id="6aee1-385">Ejemplos de código</span><span class="sxs-lookup"><span data-stu-id="6aee1-385">Code Examples</span></span>  
 <span data-ttu-id="6aee1-386">Esta sección contiene los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6aee1-386">This section contains the following examples.</span></span>  
  
-   [<span data-ttu-id="6aee1-387">Crear una credencial</span><span class="sxs-lookup"><span data-stu-id="6aee1-387">Create a Credential</span></span>](#credential)  
  
-   [<span data-ttu-id="6aee1-388">Realizar una copia de seguridad completa de la base de datos</span><span class="sxs-lookup"><span data-stu-id="6aee1-388">Backing up a complete database</span></span>](#complete)  
  
-   [<span data-ttu-id="6aee1-389">Realizar una copia de seguridad de la base de datos y el registro</span><span class="sxs-lookup"><span data-stu-id="6aee1-389">Backing up the database and log</span></span>](#databaselog)  
  
-   [<span data-ttu-id="6aee1-390">Crear una copia de seguridad de archivos completa del grupo de archivos principal</span><span class="sxs-lookup"><span data-stu-id="6aee1-390">Creating a full file backup of the primary filegroup</span></span>](#filebackup)  
  
-   [<span data-ttu-id="6aee1-391">Crear una copia de seguridad de archivos diferencial del grupo de archivos principal</span><span class="sxs-lookup"><span data-stu-id="6aee1-391">Creating a differential file backup of the primary filegroups</span></span>](#differential)  
  
-   [<span data-ttu-id="6aee1-392">Restaurar una base de datos y mover archivos</span><span class="sxs-lookup"><span data-stu-id="6aee1-392">Restoring a database and move files</span></span>](#restoredbwithmove)  
  
-   [<span data-ttu-id="6aee1-393">Restaurar a un momento dado con STOPAT</span><span class="sxs-lookup"><span data-stu-id="6aee1-393">Restoring to a point-in-time using STOPAT</span></span>](#PITR)  
  
###  <a name="create-a-credential"></a><a name="credential"></a> <span data-ttu-id="6aee1-394">Crear una credencial</span><span class="sxs-lookup"><span data-stu-id="6aee1-394">Create a Credential</span></span>  
 <span data-ttu-id="6aee1-395">En el ejemplo siguiente se crea una credencial que almacena la información de autenticación de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="6aee1-395">The following example creates a credential that stores the Azure Storage authentication information.</span></span>  

   ```sql
   IF NOT EXISTS  
   (SELECT * FROM sys.credentials   
   WHERE credential_identity = 'mycredential')  
   CREATE CREDENTIAL mycredential WITH IDENTITY = 'mystorageaccount'  
   ,SECRET = '<storage access key>' ;  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
   string secret = "<storage access key>";  
  
   // Create a Credential  
   string credentialName = "mycredential";  
   Credential credential = new Credential(server, credentialName);  
   credential.Create(identity, secret);  
   ```  
  
   ```powershell
   # create variables  
   $storageAccount = "mystorageaccount"  
   $storageKey = "<storage access key>"  
   $secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
   $credentialName = "mycredential"  
  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Create a credential  
   New-SqlCredential -Name $credentialName -Path $srvpath -Identity $storageAccount -Secret $secureString
   ```  
  
###  <a name="backing-up-a-complete-database"></a><a name="complete"></a><span data-ttu-id="6aee1-396">Copia de seguridad de una base de datos completa</span><span class="sxs-lookup"><span data-stu-id="6aee1-396">Backing up a complete database</span></span>  
 <span data-ttu-id="6aee1-397">En el ejemplo siguiente se realiza una copia de seguridad de la base de datos AdventureWorks2012 en el servicio Azure BLOB Storage.</span><span class="sxs-lookup"><span data-stu-id="6aee1-397">The following example backs up the AdventureWorks2012 database to the Azure Blob storage service.</span></span>
  
   ```sql
   BACKUP DATABASE AdventureWorks2012   
   TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
         WITH CREDENTIAL = 'mycredential'   
         ,COMPRESSION  
         ,STATS = 5;  
   GO
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);  
   ```
  
   ```powershell
   # create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"   
   # for default instance, the $srvpath varilable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance  
   CD $srvPath   
   $backupFile = $backupUrlContainer + "AdventureWorks2012" +  ".bak"  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On
   ```  
  
###  <a name="backing-up-the-database-and-log"></a><a name="databaselog"></a><span data-ttu-id="6aee1-398">Realizar copias de seguridad de la base de datos y del registro</span><span class="sxs-lookup"><span data-stu-id="6aee1-398">Backing up the database and log</span></span>  
 <span data-ttu-id="6aee1-399">En el ejemplo siguiente se realiza la copia de seguridad de la base de datos de ejemplo AdventureWorks2012, que usa de forma predeterminada el modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="6aee1-399">The following example backups up the AdventureWorks2012 sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="6aee1-400">Para admitir copias de seguridad de registros, se ha modificado la base de datos AdventureWorks2012 para usar el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="6aee1-400">To support log backups, the AdventureWorks2012 database is modified to use the full recovery model.</span></span> <span data-ttu-id="6aee1-401">A continuación, en el ejemplo se crea una copia de seguridad de base de datos completa en BLOB de Azure y, después de un período de actividad de actualización, se realiza una copia de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="6aee1-401">The example then creates a full database backup to Azure Blob, and after a period of update activity, backs up the log.</span></span> <span data-ttu-id="6aee1-402">En este ejemplo se crea un nombre de archivo de copia de seguridad con una marca de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="6aee1-402">This example creates a backup file name with a datetime stamp.</span></span>  
  
   ```sql
   -- To permit log backups, before the full database backup, modify the database   
   -- to use the full recovery model.  
   USE master;  
   GO  
   ALTER DATABASE AdventureWorks2012  
      SET RECOVERY FULL;  
   GO  
  
   -- Back up the full AdventureWorks2012 database.  
          -- First create a file name for the backup file with DateTime stamp  
  
   DECLARE @Full_Filename AS VARCHAR (300);  
   SET @Full_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Full_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.bak';   
   --Back up Adventureworks2012 database  
  
   BACKUP DATABASE AdventureWorks2012  
   TO URL =  @Full_Filename  
   WITH CREDENTIAL = 'mycredential';  
   ,COMPRESSION  
   GO  
   -- Back up the AdventureWorks2012 log.  
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url for data backup  
   string urlDataBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Data-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database to Url  
   Backup backupData = new Backup();  
   backupData.CredentialName = credentialName;  
   backupData.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupData.Devices.AddDevice(urlDataBackup, DeviceType.Url);  
   backupData.SqlBackup(server);  
  
   // Generate Unique Url for data backup  
   string urlLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Log-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database Log to Url  
   Backup backupLog = new Backup();  
   backupLog.CredentialName = credentialName;  
   backupLog.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupLog.Devices.AddDevice(urlLogBackup, DeviceType.Url);  
   backupLog.Action = BackupActionType.Log;  
   backupLog.SqlBackup(server);  
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to theSQL Server Instance
   CD $srvPath   
   #Create a unique file name for the full database backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Backup Database to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Database    
  
   #Create a unique file name for log backup  
  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup Log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Log
   ```  
  
###  <a name="creating-a-full-file-backup-of-the-primary-filegroup"></a><a name="filebackup"></a><span data-ttu-id="6aee1-403">Crear una copia de seguridad de archivos completa del grupo de archivos principal</span><span class="sxs-lookup"><span data-stu-id="6aee1-403">Creating a full file backup of the primary filegroup</span></span>  
 <span data-ttu-id="6aee1-404">En el ejemplo siguiente se crea una copia de seguridad de archivos completa del grupo de archivos principal.</span><span class="sxs-lookup"><span data-stu-id="6aee1-404">The following example creates a full file backup of the primary filegroup.</span></span>
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012files.bck'  
       WITH CREDENTIAL = 'mycredential'  
       ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bck",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to the SQL Server Instance  
  
   CD $srvPath   
   #Create a unique file name for the file backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bck"  
  
   #Backup Primary File Group to URL  
  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary
   ```  
  
###  <a name="creating-a-differential-file-backup-of-the-primary-filegroup"></a><a name="differential"></a><span data-ttu-id="6aee1-405">Crear una copia de seguridad diferencial de archivos del grupo de archivos principal</span><span class="sxs-lookup"><span data-stu-id="6aee1-405">Creating a differential file backup of the primary filegroup</span></span>  
 <span data-ttu-id="6aee1-406">En el ejemplo siguiente se crea una copia de seguridad de archivos diferencial del grupo de archivos principal.</span><span class="sxs-lookup"><span data-stu-id="6aee1-406">The following example creates a differential file backup of the primary filegroup.</span></span>  
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012filesdiff.bck'  
       WITH   
          CREDENTIAL = 'mycredential'  
          ,COMPRESSION  
      ,DIFFERENTIAL;  
   GO
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.Incremental = true;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server); 
   ```

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Create a differential backup of the primary filegroup
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary -Incremental
   ```  
  
###  <a name="restore-a-database-and-move-files"></a><a name="restoredbwithmove"></a><span data-ttu-id="6aee1-407">Restaurar una base de datos y migrar archivos</span><span class="sxs-lookup"><span data-stu-id="6aee1-407">Restore a database and move files</span></span>  
 <span data-ttu-id="6aee1-408">Para restaurar una copia de seguridad completa y mover la base de datos restaurada al directorio C:\Archivos de programa\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6aee1-408">To restore a full database backup and move the restored database to C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data directory, use the following steps.</span></span>
  
   ```sql
   -- Backup the tail of the log first
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,NORECOVERY;  
   GO  
  
   RESTORE DATABASE AdventureWorks2012 FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'  
   WITH CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,MOVE 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,STATS = 5
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for tail log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName+ "_Log", newLogFilePath));  
   restore.SqlRestore(server);
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTNACENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On      
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery    
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath)
   ```  
  
###  <a name="restoring-to-a-point-in-time-using-stopat"></a><a name="PITR"></a> <span data-ttu-id="6aee1-409">Restaurar a un momento dado con STOPAT</span><span class="sxs-lookup"><span data-stu-id="6aee1-409">Restoring to a point-in-time using STOPAT</span></span>  
 <span data-ttu-id="6aee1-410">En el ejemplo siguiente se restaura una base de datos a su estado en un momento dado y se muestra una operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="6aee1-410">The following example restores a database to its state to a point in time, and shows a restore operation.</span></span>  
  
   ```sql
   RESTORE DATABASE AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
   WITH   
     CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,Move 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,NORECOVERY  
    --,REPLACE  
    ,STATS = 5;  
   GO   
  
   RESTORE LOG AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.trn'   
   WITH CREDENTIAL = 'mycredential'  
    ,RECOVERY   
    ,STOPAT = 'Oct 23, 2012 5:00 PM'   
   GO  
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for Tail Log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.NoRecovery = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName + "_Log", newLogFilePath));  
   restore.SqlRestore(server);  
      
   // Restore transaction Log with stop at   
   Restore restoreLog = new Restore();  
   restoreLog.CredentialName = credentialName;  
   restoreLog.Database = dbName;  
   restoreLog.Action = RestoreActionType.Log;  
   restoreLog.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restoreLog.ToPointInTime = DateTime.Now.ToString();   
   restoreLog.SqlRestore(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Navigate to SQL Server Instance Directory
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On     
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery     
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath) -NoRecovery    
  
   # Restore Transaction log with Stop At:  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backuplogFile  -ToPointInTime (Get-Date).ToString()
   ```  
  
## <a name="see-also"></a><span data-ttu-id="6aee1-411">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6aee1-411">See Also</span></span>  
 <span data-ttu-id="6aee1-412">[Prácticas recomendadas y solución de problemas de Copia de seguridad en URL de SQL Server](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="6aee1-412">[SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span></span>  
 [<span data-ttu-id="6aee1-413">Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6aee1-413">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](back-up-and-restore-of-system-databases-sql-server.md)   
