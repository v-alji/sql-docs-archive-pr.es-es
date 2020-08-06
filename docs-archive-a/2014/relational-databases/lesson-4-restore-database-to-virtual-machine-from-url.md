---
title: Lección 5. Opta Cifrar la base de datos mediante TDE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ba793c8f-665a-4c46-b68d-f558a37906b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 613b66c04a69364f3c9be1059f95021dd3eff595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674111"
---
# <a name="lesson-5-optional-encrypt-your-database-using-tde"></a><span data-ttu-id="49d24-103">Lección 5.</span><span class="sxs-lookup"><span data-stu-id="49d24-103">Lesson 5.</span></span> <span data-ttu-id="49d24-104">(Opcional) Cifrar la base de datos mediante TDE</span><span class="sxs-lookup"><span data-stu-id="49d24-104">(Optional) Encrypt your database using TDE</span></span>
  <span data-ttu-id="49d24-105">Como paso opcional, puede cifrar la base de datos creada recientemente.</span><span class="sxs-lookup"><span data-stu-id="49d24-105">As an optional step, you can encrypt the newly created database.</span></span> <span data-ttu-id="49d24-106">El cifrado de datos transparente (TDE) realiza el cifrado y descifrado de E/S en tiempo real de los datos y los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="49d24-106">Transparent data encryption (TDE) performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="49d24-107">Este tipo de cifrado utiliza una clave de cifrado de la base de datos (DEK), que está almacenada en el registro de arranque de la base de datos para que esté disponible durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="49d24-107">This kind of encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="49d24-108">Para obtener más información, vea [Cifrado de datos transparente &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) y [mueva una base de datos protegida por TDE a otra SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="49d24-108">For more information, see [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) and [Move a TDE Protected Database to Another SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span></span>  
  
 <span data-ttu-id="49d24-109">En esta lección se supone que ya completó los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="49d24-109">This lesson assumes you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="49d24-110">Tiene una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="49d24-110">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="49d24-111">Ha creado un contenedor en su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="49d24-111">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="49d24-112">Ha creado una directiva en un contenedor con derechos de lectura, escritura y enumeración.</span><span class="sxs-lookup"><span data-stu-id="49d24-112">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="49d24-113">También generó una clave SAS.</span><span class="sxs-lookup"><span data-stu-id="49d24-113">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="49d24-114">Ha creado una credencial de SQL Server en el equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="49d24-114">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="49d24-115">Ha creado una base de datos siguiendo los pasos descritos en la lección 4.</span><span class="sxs-lookup"><span data-stu-id="49d24-115">You have created a database by following the steps that are described in Lesson 4.</span></span>  
  
 <span data-ttu-id="49d24-116">Si desea cifrar una base de datos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="49d24-116">If you want to encrypt a database, follow these steps:</span></span>  
  
1.  <span data-ttu-id="49d24-117">En la máquina de origen, modifique y ejecute las instrucciones siguientes en una ventana de consulta:</span><span class="sxs-lookup"><span data-stu-id="49d24-117">In the source machine, modify and run the following statements in a query window:</span></span>  
  
    ```  
  
    -- Create a master key and a server certificate   
    USE master   
    GO   
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01';   
    GO   
    CREATE CERTIFICATE MySQLCert WITH SUBJECT = 'SQL - Azure Storage Certification'   
    GO   
    -- Create a backup of the server certificate in the master database.   
    -- Store TDS certificates in the source machine locally.   
    BACKUP CERTIFICATE MySQLCert   
    TO FILE = 'C:\certs\MySQLCert.CER'   
    WITH PRIVATE KEY   
    (   
    FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
    ENCRYPTION BY PASSWORD = 'MySQLKey01'   
    );  
  
    ```  
  
2.  <span data-ttu-id="49d24-118">A continuación, cifre la nueva base de datos en el equipo de origen siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="49d24-118">Then, encrypt your new database in the source machine by following these steps:</span></span>  
  
    ```  
  
    -- Switch to the new database.   
    -- Create a database encryption key, that is protected by the server certificate in the master database.    
    -- Alter the new database to encrypt the database using TDE.   
    USE TestDB1;   
    GO   
    -- Encrypt your database   
    CREATE DATABASE ENCRYPTION KEY   
    WITH ALGORITHM = AES_256   
    ENCRYPTION BY SERVER CERTIFICATE MySQLCert   
    GO   
  
    ALTER DATABASE TestDB1   
    SET ENCRYPTION ON   
    GO  
  
    ```  
  
 <span data-ttu-id="49d24-119">Si desea obtener el estado de cifrado de una base de datos y sus claves de cifrado asociadas de la base de datos, ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="49d24-119">If you want to learn the encryption state of a database and its associated database encryption keys, run the following statement:</span></span>  
  
```  
  
SELECT * FROM sys.dm_database_encryption_keys;   
GO  
  
```  
  
 <span data-ttu-id="49d24-120">Para obtener información detallada sobre las instrucciones Transact-SQL que se han utilizado en esta lección, vea [Create database &#40;SQL Server Transact-sql&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [Create Master Key &#40;Transact- ](/sql/t-sql/statements/create-master-key-transact-sql)sql&#41;, [CREATE Certificate &#40;transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql)y [Sys. dm_database_encryption_keys &#40;Transact-SQL ](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql)&#41;.</span><span class="sxs-lookup"><span data-stu-id="49d24-120">For detailed information the Transact-SQL statements that have been used in this lesson, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql), and [sys.dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span></span>  
  
 <span data-ttu-id="49d24-121">**Lección siguiente:**</span><span class="sxs-lookup"><span data-stu-id="49d24-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="49d24-122">Lección 6: Migrar una base de datos desde un equipo de origen local a un equipo de destino en Azure</span><span class="sxs-lookup"><span data-stu-id="49d24-122">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>](lesson-5-backup-database-using-file-snapshot-backup.md)  
  
  
