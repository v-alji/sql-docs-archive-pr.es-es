---
title: Lección 9. Restaurar una base de datos desde Azure Storage | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ebba12c7-3d13-4c9d-8540-ad410a08356d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5e7c2350bb2a9b1f8c31da8e094459b5bc8ccd90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677075"
---
# <a name="lesson-9-restore-a-database-from-azure-storage"></a><span data-ttu-id="93658-103">Lección 9.</span><span class="sxs-lookup"><span data-stu-id="93658-103">Lesson 9.</span></span> <span data-ttu-id="93658-104">Restaurar una base de datos desde Azure Storage</span><span class="sxs-lookup"><span data-stu-id="93658-104">Restore a database from Azure Storage</span></span>
  <span data-ttu-id="93658-105">En esta lección, aprenderá a restaurar un archivo de copia de seguridad de base de datos de Azure Storage en una base de datos, que reside en local o en una máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="93658-105">In this lesson, you will learn how to restore a database backup file from Azure Storage to a database, which either resides on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="93658-106">Para seguir esta lección, no es necesario completar las lecciones 4, 5, 6, 7 y 8.</span><span class="sxs-lookup"><span data-stu-id="93658-106">To follow this lesson, you do not need to complete Lesson 4, 5, 6, 7, and 8.</span></span>  
  
 <span data-ttu-id="93658-107">En esta lección se supone que ya completó los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="93658-107">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="93658-108">Ha creado una base de datos en el equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="93658-108">You have created a database in the source machine.</span></span>  
  
-   <span data-ttu-id="93658-109">Ha creado una copia de seguridad de su base de datos (. bak) en Azure Storage mediante el uso de la característica [SQL Server Backup and restore with Azure BLOB Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="93658-109">You have created a backup of your database (.bak) in Azure Storage by using the [SQL Server Backup and Restore with Azure Blob Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) feature.</span></span> <span data-ttu-id="93658-110">Tenga en cuenta que deberá crear una credencial de SQL Server en este paso.</span><span class="sxs-lookup"><span data-stu-id="93658-110">Note that you will need to create another SQL Server Credential in this step.</span></span> <span data-ttu-id="93658-111">Esta credencial utiliza las claves de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="93658-111">This credential uses storage account keys.</span></span>  
  
-   <span data-ttu-id="93658-112">Tiene una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="93658-112">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="93658-113">Ha creado un contenedor en su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="93658-113">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="93658-114">Ha creado una directiva en un contenedor con derechos de lectura, escritura y enumeración.</span><span class="sxs-lookup"><span data-stu-id="93658-114">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="93658-115">También generó una clave SAS.</span><span class="sxs-lookup"><span data-stu-id="93658-115">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="93658-116">Ha creado una SQL Server credencial en el equipo para Azure Storage característica de integración.</span><span class="sxs-lookup"><span data-stu-id="93658-116">You have created a SQL Server credential on your machine for Azure Storage Integration feature.</span></span> <span data-ttu-id="93658-117">Observe que esta credencial requiere una clave de la firma de acceso compartido (SAS).</span><span class="sxs-lookup"><span data-stu-id="93658-117">Note that this credential requires a Shared Access Signature (SAS) key.</span></span>  
  
 <span data-ttu-id="93658-118">Para restaurar una base de datos a partir de Azure Storage, puede seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="93658-118">To restore a database from Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="93658-119">Inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="93658-119">Start SQL Server Management Studio.</span></span> <span data-ttu-id="93658-120">Conéctese a la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="93658-120">Connect to the default instance.</span></span>  
  
2.  <span data-ttu-id="93658-121">Haga clic en **nueva consulta** en la barra de herramientas estándar.</span><span class="sxs-lookup"><span data-stu-id="93658-121">Click **New Query** on the Standard Toolbar.</span></span>  
  
3.  <span data-ttu-id="93658-122">Copie y pegue el script completo siguiente en la ventana de consultas.</span><span class="sxs-lookup"><span data-stu-id="93658-122">Copy and paste the following complete script to the query window.</span></span> <span data-ttu-id="93658-123">Modifique el script según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="93658-123">Modify the script as needed.</span></span>  
  
     <span data-ttu-id="93658-124">**Nota:** Ejecute la `RESTORE` instrucción para restaurar la copia de seguridad de base de datos (. bak) de Azure Storage en una instancia de base de datos de otro equipo.</span><span class="sxs-lookup"><span data-stu-id="93658-124">**Note:** You run the `RESTORE` statement to restore the database backup (.bak) in Azure Storage to a database instance in another machine.</span></span>  
  
    ```sql  
  
    USE master   
    GO   
    -- Create a new database to be backed up.   
    CREATE DATABASE TestDbRestoreFrom;   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    SELECT * from dbo.Table1;   
    GO   
    -- Create a credential to be used by SQL Server Backup and Restore with Azure -----Blob Storage Service.   
    USE master;   
    GO   
    CREATE CREDENTIAL BackupCredential    
    WITH IDENTITY= 'teststorageaccnt',   
    SECRET = 'BO1nH/lWRdnc8TGPlQIXmGLWVCoEa48suYSGiAlC73+S0TX5VXo5/LCm8qiyGCYafDg4ZsueDIV3GQ5RXHaRGw=='    
    GO   
    -- Display the newly created credential   
    SELECT * from sys.credentials   
    -- Create a backup in Azure Storage.   
    BACKUP DATABASE TestDBRestoreFrom    
    TO URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
          WITH CREDENTIAL = 'BackupCredential'    
         ,COMPRESSION   
         ,STATS = 5;   
    GO    
    -- Create a Shared Access Signature credential   
    CREATE CREDENTIAL [https://teststorageaccnt.blob.core.windows.net/testrestorefrom]   
    WITH IDENTITY='SHARED ACCESS SIGNATURE',   
    SECRET = 'sv=2012-02-12&sr=c&si=policy_resfrom&sig=EhVpzLUXjG4ThAMLmVhrnoiCt8IfmD3BsuYiMawGzxc%3D'   
    GO   
    USE master;   
    GO   
    RESTORE DATABASE TestDBRestoreFrom    
    FROM URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
    WITH    
    CREDENTIAL = 'BackupCredential',    
    REPLACE,   
    MOVE 'TestDBRestoreFrom' TO 'C:\Backup\TestDBRestoreFrom.mdf',     
    MOVE 'TestDBRestoreFrom_log' TO 'C:\Backup\TestDBRestoreFrom_log.ldf';   
    GO  
  
    ```  
  
 <span data-ttu-id="93658-125">**Final del tutorial: archivos de datos de SQL Server en Azure Storage Service**</span><span class="sxs-lookup"><span data-stu-id="93658-125">**End of Tutorial: SQL Server Data Files in Azure Storage service**</span></span>  
  
  
