---
title: 'Lección 2: crear una credencial de SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 64f8805c-1ddc-4c96-a47c-22917d12e1ab
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e8b13c8d4d9e5937064cef5503ec64bfd6e4a2d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751602"
---
# <a name="lesson-2-create-a-sql-server-credential"></a><span data-ttu-id="93583-102">Lección 2: Crear una credencial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="93583-102">Lesson 2: Create a SQL Server Credential</span></span>
  <span data-ttu-id="93583-103">**Credencial:** Una credencial de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] es un objeto que se usa para almacenar la información de autenticación necesaria para conectarse a un recurso fuera de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93583-103">**Credential:** A [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="93583-104">Aquí, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] los procesos de copia de seguridad y restauración usan credenciales para autenticarse en el servicio de almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="93583-104">Here, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="93583-105">La credencial contiene los valores de nombre y la **clave de acceso** de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="93583-105">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="93583-106">Una vez creada la credencial, se debe especificar en la opción WITH CREDENTIAL al emitir las instrucciones BACKUP y RESTORE.</span><span class="sxs-lookup"><span data-stu-id="93583-106">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="93583-107">Para obtener más información sobre cómo ver, copiar o regenerar **access keys**de cuentas de almacenamiento, vea [Ver, copiar y regenerar las claves de acceso de una cuenta de almacenamiento de Windows Azure](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="93583-107">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="93583-108">Para obtener información general sobre las credenciales, vea [credenciales](../relational-databases/security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="93583-108">For general information about credentials, see [Credentials](../relational-databases/security/authentication-access/credentials-database-engine.md).</span></span>  
  
 <span data-ttu-id="93583-109">Para obtener información sobre otros ejemplos donde se usan credenciales, consulte [creación de un proxy de Agente SQL Server](../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="93583-109">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="93583-110">Los requisitos para crear una SQL Server credenciales que se describen a continuación son específicos de SQL Server procesos de copia de seguridad ([SQL Server copia de seguridad en la dirección URL](../relational-databases/backup-restore/sql-server-backup-to-url.md)y [SQL Server copia de seguridad administrada en Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span><span class="sxs-lookup"><span data-stu-id="93583-110">The requirements for creating a SQL Server credential described below are specific to SQL Server backup processes ([SQL Server Backup to URL](../relational-databases/backup-restore/sql-server-backup-to-url.md), and [SQL Server Managed  Backup to Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span></span> <span data-ttu-id="93583-111">Cuando SQL Server obtiene acceso al Almacenamiento de Azure para escribir o leer copias de seguridad, usa el nombre de la cuenta de almacenamiento y la información de la clave de acceso.</span><span class="sxs-lookup"><span data-stu-id="93583-111">SQL Server, when accessing Azure storage to write or read backups uses the storage account name and access key information.</span></span>  <span data-ttu-id="93583-112">Para obtener más información acerca de cómo crear credenciales para almacenar archivos de base de datos, vea [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md).</span><span class="sxs-lookup"><span data-stu-id="93583-112">For more information on creating credentials for storing database files in Azure storage, see [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span></span>  
  
## <a name="create-a-sql-server-credential"></a><span data-ttu-id="93583-113">Crear una credencial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="93583-113">Create a SQL Server Credential</span></span>  
 <span data-ttu-id="93583-114">Para crear una credencial de SQL Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="93583-114">To create a SQL Server Credential, use the following steps:</span></span>  
  
1.  <span data-ttu-id="93583-115">Conéctese a SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="93583-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="93583-116">En el Explorador de objetos, conéctese a la instancia del motor de base de datos que tiene instalada la base de datos AdventureWorks2012 o use su propia base de datos para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="93583-116">In Object Explorer, connect to the instance of Database Engine that has AdventureWorks2012 database installed, or use your own database you plan to use for this tutorial.</span></span>  
  
3.  <span data-ttu-id="93583-117">En la barra de herramientas **Estándar** , haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="93583-117">On the **Standard** tool bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="93583-118">Copie y pegue el ejemplo siguiente en la ventana de consulta, y modifíquelo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="93583-118">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account (See Lesson 1)   
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account (See Lesson 1)  
  
    ```  
  
     <span data-ttu-id="93583-119">![asignación de la cuenta de almacenamiento a credenciales de SQL](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "asignación de la cuenta de almacenamiento a credenciales de SQL")</span><span class="sxs-lookup"><span data-stu-id="93583-119">![mapping storage account to sql credentials](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
5.  <span data-ttu-id="93583-120">Compruebe la instrucción T-SQL y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="93583-120">Verify the T-SQL statement and click **Execute**.</span></span>  
  
 <span data-ttu-id="93583-121">Para obtener más información sobre el servicio Azure BLOB Storage para los conceptos y los requisitos de copia de seguridad, vea [SQL Server Backup and restore with Azure BLOB Storage Service](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="93583-121">For more information about the Azure Blob storage service for backup concepts and requirements, see [SQL Server Backup and Restore with Azure Blob Storage Service](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="93583-122">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="93583-122">Next Lesson</span></span>  
 <span data-ttu-id="93583-123">[Lección 3: escribir una copia de seguridad completa de la base de datos en el servicio Azure BLOB Storage](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="93583-123">[Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span></span>  
  
  
