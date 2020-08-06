---
title: Creación de una copia de seguridad cifrada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: e29061d3-c2ab-4d98-b9be-8e90a11d17fe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d46cc686684d87fe393a5db7cfe01194ae917836
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749359"
---
# <a name="create-an-encrypted-backup"></a><span data-ttu-id="c238f-102">Crear una copia de seguridad cifrada</span><span class="sxs-lookup"><span data-stu-id="c238f-102">Create an Encrypted Backup</span></span>
  <span data-ttu-id="c238f-103">En este tema se describen los pasos necesarios para crear una copia de seguridad cifrada mediante Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c238f-103">This topic describes the steps necessary to create an encrypted backup using Transact-SQL.</span></span>  
  
## <a name="backup-to-disk-with-encryption"></a><span data-ttu-id="c238f-104">Copia de seguridad en disco con cifrado</span><span class="sxs-lookup"><span data-stu-id="c238f-104">Backup to Disk with Encryption</span></span>  
 <span data-ttu-id="c238f-105">**Requisitos previos:**</span><span class="sxs-lookup"><span data-stu-id="c238f-105">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="c238f-106">Acceso a un disco local o al almacenamiento con espacio suficiente para crear una copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c238f-106">Access to a local disk or to storage with adequate space to create a backup of the database.</span></span>  
  
-   <span data-ttu-id="c238f-107">Una clave maestra de base de datos para la base de datos maestra y un certificado o una clave asimétrica disponible en la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c238f-107">A Database Master Key for the master database, and a certificate or asymmetric key available on the instance of SQL Server.</span></span> <span data-ttu-id="c238f-108">Para conocer los requisitos de cifrado y los permisos, vea [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="c238f-108">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
 <span data-ttu-id="c238f-109">Siga estos pasos para crear una copia de seguridad cifrada de una base de datos en un disco local.</span><span class="sxs-lookup"><span data-stu-id="c238f-109">Use the following steps to create an encrypted backup of a database to a local disk.</span></span> <span data-ttu-id="c238f-110">En este ejemplo se utiliza una base de datos de usuario denominada MyTestDB.</span><span class="sxs-lookup"><span data-stu-id="c238f-110">This example uses a user database called MyTestDB.</span></span>  
  
1.  <span data-ttu-id="c238f-111">**Creación de una clave maestra de base datos de la base de datos maestra:** Elija una contraseña para cifrar la copia de la clave maestra que se almacenará en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c238f-111">**Create a Database Master Key of the master database:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="c238f-112">Conecte con el motor de base de datos, inicie una nueva ventana de consulta, copie y pegue el siguiente ejemplo y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c238f-112">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.   
    -- The key is encrypted using the password "<master key password>"  
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
2.  <span data-ttu-id="c238f-113">**Creación de un certificado de copia de seguridad:** Cree un certificado de copia de seguridad en la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="c238f-113">**Create a Backup Certificate:** Create a backup certificate in the master database.</span></span> <span data-ttu-id="c238f-114">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c238f-114">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
    ```  
    Use Master  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDB Backup Encryption Certificate';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="c238f-115">**Copia de seguridad de la base de datos:** Especifique el algoritmo de cifrado y el certificado que se usará.</span><span class="sxs-lookup"><span data-stu-id="c238f-115">**Backup the database:** Specify the encryption algorithm and certificate to use.</span></span> <span data-ttu-id="c238f-116">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c238f-116">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      COMPRESSION,  
      ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
 <span data-ttu-id="c238f-117">Para obtener un ejemplo sobre cómo cifrar una copia de seguridad protegida por EKM, vea [Administración extensible de claves con el Almacén de claves de Azure &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c238f-117">For an example of encrypting a backup protected by an EKM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
### <a name="backup-to-azure-storage-with-encryption"></a><span data-ttu-id="c238f-118">Copia de seguridad en Azure Storage con cifrado</span><span class="sxs-lookup"><span data-stu-id="c238f-118">Backup to Azure Storage with Encryption</span></span>  
 <span data-ttu-id="c238f-119">Si crea una copia de seguridad en Azure Storage con la opción **SQL Server Backup to URL** (Copia de seguridad en URL de SQL Server), los pasos de cifrado son los mismos pero debe usar una dirección URL como destino y una credencial SQL para autenticarse en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c238f-119">If you are creating a backup to Azure storage using the **SQL Server Backup to URL** option, the encryption steps are the same, but you must use URL as the destination and a SQL Credential to authenticate to the Azure storage.</span></span> <span data-ttu-id="c238f-120">Si desea configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] con opciones de cifrado, consulte [configuración de SQL Server copia de seguridad administrada en Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) y [configuración de SQL Server copia de seguridad administrada en Azure para grupos de disponibilidad](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c238f-120">If you want to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with encryption options, see [Setting up SQL Server Managed Backup to Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 <span data-ttu-id="c238f-121">**Requisitos previos:**</span><span class="sxs-lookup"><span data-stu-id="c238f-121">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="c238f-122">Una cuenta de almacenamiento de Windows y un contenedor.</span><span class="sxs-lookup"><span data-stu-id="c238f-122">A windows storage account and a container.</span></span> <span data-ttu-id="c238f-123">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="c238f-123">For more information, see.</span></span> <span data-ttu-id="c238f-124">[Lección 1: Crear objetos de Azure Storage](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c238f-124">[Lesson 1: Create Azure Storage Objects](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span></span>  
  
-   <span data-ttu-id="c238f-125">Una clave maestra para la base de datos maestra y un certificado o una clave asimétrica en la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c238f-125">A Database Master Key for the master database, and a certificate or asymmetric key  on the instance of SQL Server.</span></span> <span data-ttu-id="c238f-126">Para conocer los requisitos de cifrado y los permisos, vea [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="c238f-126">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
1.  <span data-ttu-id="c238f-127">**Creación de una credencial de SQL Server:** Para crear una credencial de SQL Server, conéctese al motor de base de datos, abra una nueva ventana de consulta, copie y pegue el ejemplo siguiente y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c238f-127">**Create SQL Server Credential:** To create a SQL Server credential, connect to the Database Engine, open a new query window, and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account    
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account  
    ```  
  
2.  <span data-ttu-id="c238f-128">**Cree la clave maestra de una base de datos:** Elija una contraseña para cifrar la copia de la clave maestra que se almacenará en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c238f-128">**Create a Database Master Key:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="c238f-129">Conecte con el motor de base de datos, inicie una nueva ventana de consulta, copie y pegue el siguiente ejemplo y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c238f-129">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.  
    -- The key is encrypted using the password "<master key password>"  
    USE Master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="c238f-130">**Creación de un certificado de copia de seguridad:** Cree un certificado de copia de seguridad en la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="c238f-130">**Create a Backup Certificate:** Create a Backup Certificate in the master database.</span></span> <span data-ttu-id="c238f-131">Copie el ejemplo siguiente, péguelo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c238f-131">Copy and paste the following example in the query window and click **Execute**</span></span>  
  
    ```  
    USE Master;  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDBBackupEncryptCert ';  
    GO  
  
    ```  
  
4.  <span data-ttu-id="c238f-132">**Copia de seguridad de la base de datos:** Especifique el algoritmo de cifrado y el certificado que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c238f-132">**Backup the database:** Specify the encryption algorithm and the certificate to use.</span></span> <span data-ttu-id="c238f-133">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c238f-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO URL = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      CREDENTIAL 'mycredential' - this is the name of the credential created in the first step.  
      ,COMPRESSION  
      ,ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
  
