---
title: 'Tutorial: Copias de seguridad y restauración de SQL Server en el servicio Azure Blob Storage | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 9e1d94ce-2c93-45d1-ae2a-2a7d1fa094c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d15200968011cdb314829736512f39730782dc0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744628"
---
# <a name="tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service"></a><span data-ttu-id="326f4-102">Tutorial: Copia de seguridad y restauración de SQL Server en el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="326f4-102">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>
  <span data-ttu-id="326f4-103">Este es el Introducción con SQL Server tutorial de copia de seguridad y restauración con Azure Blob Storage Service.</span><span class="sxs-lookup"><span data-stu-id="326f4-103">Welcome to the Getting Started with SQL Server Backup and Restore with Azure Blob Storage Service tutorial.</span></span> <span data-ttu-id="326f4-104">Este tutorial le ayudará a entender cómo escribir copias de seguridad en el servicio Azure Blob Storage y cómo restaurar desde este.</span><span class="sxs-lookup"><span data-stu-id="326f4-104">This tutorial helps you understand how to write backups to and restore from the Azure Blob storage service.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="326f4-105">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="326f4-105">What You Will Learn</span></span>  
 <span data-ttu-id="326f4-106">Este tutorial muestra cómo crear una cuenta de almacenamiento de Windows, un contenedor de blobs, crear credenciales para tener acceso a la cuenta de almacenamiento, escribir una copia de seguridad en el servicio de blob y realizar una restauración simple.</span><span class="sxs-lookup"><span data-stu-id="326f4-106">This tutorial shows you how to create a Windows Storage account, a blob container, creating credentials to access the storage account, writing a backup to the blob service, and performing a simple restore.</span></span> <span data-ttu-id="326f4-107">El tutorial está compuesto por cuatro lecciones:</span><span class="sxs-lookup"><span data-stu-id="326f4-107">This tutorial is divided into four lessons:</span></span>  
  
 [<span data-ttu-id="326f4-108">Lección 1: crear objetos de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="326f4-108">Lesson 1: Create Azure Storage Objects</span></span>](../tutorials/lesson-1-create-windows-azure-storage-objects.md)  
 <span data-ttu-id="326f4-109">En esta lección, creará una cuenta de Azure Storage y un contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="326f4-109">In this lesson, you create an Azure storage account and a blob container.</span></span>  
  
 [<span data-ttu-id="326f4-110">Lección 2: Crear una credencial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="326f4-110">Lesson 2: Create a SQL Server Credential</span></span>](../tutorials/lesson-2-create-a-sql-server-credential.md)  
 <span data-ttu-id="326f4-111">En esta lección, creará una credencial para almacenar la información de seguridad usada para acceder a la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="326f4-111">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 [<span data-ttu-id="326f4-112">Lección 3: Escribir una copia de seguridad completa de la base de datos en el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="326f4-112">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>](../tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md)  
 <span data-ttu-id="326f4-113">En esta lección, emitirá una instrucción T-SQL para escribir una copia de seguridad de la base de datos AdventureWorks2012 en el servicio Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="326f4-113">In this lesson, you issue a T-SQL statement to write a backup of the AdventureWorks2012 database to the Azure Blob storage service.</span></span>  
  
 [<span data-ttu-id="326f4-114">Lección 4: Realización de una restauración desde una copia de seguridad completa de la base de datos</span><span class="sxs-lookup"><span data-stu-id="326f4-114">Lesson 4: Perform a Restore From a Full Database Backup</span></span>](../tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)  
 <span data-ttu-id="326f4-115">En esta lección, emitirá una instrucción T-SQL para restaurar desde la copia de seguridad de la base de datos creada en la lección anterior.</span><span class="sxs-lookup"><span data-stu-id="326f4-115">In this lesson, you issue a T-SQL statement to restore from the database backup you created in the previous lesson.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="326f4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="326f4-116">Requirements</span></span>  
 <span data-ttu-id="326f4-117">Para completar este tutorial, debe estar familiarizado con los conceptos de copias de seguridad y restauración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y con la sintaxis de T-SQL.</span><span class="sxs-lookup"><span data-stu-id="326f4-117">To complete this tutorial, you must be familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore concepts and T-SQL syntax.</span></span> <span data-ttu-id="326f4-118">Para usar este tutorial, el sistema debe cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="326f4-118">To use this tutorial, your system must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="326f4-119">Una instancia de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] y la base de datos AdventureWorks2012 instalada.</span><span class="sxs-lookup"><span data-stu-id="326f4-119">An instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], and AdventureWorks2012 database installed.</span></span>  
  
     <span data-ttu-id="326f4-120">La instancia de SQL Server puede ser local o residir en una máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="326f4-120">The SQL Server instance can be on-premises or in an Azure Virtual Machine.</span></span>  
  
     <span data-ttu-id="326f4-121">Puede usar una base de datos de usuario en lugar de AdventureWorks2012 y modificar la sintaxis de tsql en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="326f4-121">You can use a user database in place of AdventureWorks2012, and modify the tsql syntax accordingly.</span></span>  
  
-   <span data-ttu-id="326f4-122">La cuenta de usuario que se usa para emitir comandos BACKUP o RESTORE debe tener el rol de base de datos **operador de db_backup** con permisos **Modificar cualquier credencial** .</span><span class="sxs-lookup"><span data-stu-id="326f4-122">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
### <a name="additional-reading"></a><span data-ttu-id="326f4-123">Lectura adicional</span><span class="sxs-lookup"><span data-stu-id="326f4-123">Additional Reading</span></span>  
 <span data-ttu-id="326f4-124">A continuación, se indican algunas lecturas recomendadas para entender los conceptos y los procedimientos recomendados al usar el servicio Azure Blob Storage para copias de seguridad de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="326f4-124">Following are some recommended reading to understand the concepts, best practices when using Azure Blob storage service for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups.</span></span>  
  
1.  [<span data-ttu-id="326f4-125">Copia de seguridad y restauración de SQL Server con el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="326f4-125">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
2.  [<span data-ttu-id="326f4-126">Procedimientos recomendados y solución de problemas de Copia de seguridad en URL de SQL Server</span><span class="sxs-lookup"><span data-stu-id="326f4-126">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
  
  
