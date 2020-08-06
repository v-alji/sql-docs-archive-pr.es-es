---
title: 'Tutorial: SQL Server de archivos de datos en Azure Storage servicio | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e69be67d-da1c-41ae-8c9a-6b12c8c2fb61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 21a0fc11706a0c5ee35cf71e1af69f2927adc9db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677499"
---
# <a name="tutorial-sql-server-data-files-in-azure-storage-service"></a><span data-ttu-id="5f304-102">Tutorial: Archivos de datos de SQL Server en el servicio Azure Storage</span><span class="sxs-lookup"><span data-stu-id="5f304-102">Tutorial: SQL Server Data Files in Azure Storage service</span></span>
  <span data-ttu-id="5f304-103">Este es el tutorial SQL Server los archivos de datos en Azure Storage Service.</span><span class="sxs-lookup"><span data-stu-id="5f304-103">Welcome to the  SQL Server Data Files in Azure Storage Service tutorial.</span></span> <span data-ttu-id="5f304-104">Este tutorial le ayudará a saber cómo almacenar archivos de datos de SQL Server en el servicio Azure Blob Storage directamente.</span><span class="sxs-lookup"><span data-stu-id="5f304-104">This tutorial helps you understand how to store SQL Server data files in the Azure Blob storage service directly.</span></span>  
  
 <span data-ttu-id="5f304-105">SQL Server compatibilidad con la integración del servicio de almacenamiento de blobs de Azure es una mejora del SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="5f304-105">SQL Server integration support for the Azure Blob storage service is a SQL Server 2014 enhancement.</span></span> <span data-ttu-id="5f304-106">Para obtener información general sobre la funcionalidad y las ventajas de usar esta funcionalidad, vea [SQL Server archivos de datos en Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="5f304-106">For an overview of the functionality and benefits of using this functionality, see [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="5f304-107">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="5f304-107">What you will learn</span></span>  
 <span data-ttu-id="5f304-108">En este tutorial se muestra cómo almacenar archivos de datos de SQL Server en Azure Storage Service en varias lecciones.</span><span class="sxs-lookup"><span data-stu-id="5f304-108">This tutorial shows you how to store SQL Server Data Files in Azure Storage service in multiple lessons.</span></span> <span data-ttu-id="5f304-109">Cada una de las lecciones se centra en una tarea determinada.</span><span class="sxs-lookup"><span data-stu-id="5f304-109">Each lesson is focused on a specific task.</span></span> <span data-ttu-id="5f304-110">En primer lugar, aprenderá a crear una cuenta de almacenamiento y un contenedor en Azure.</span><span class="sxs-lookup"><span data-stu-id="5f304-110">First, you will learn how to create a storage account and a container in Azure.</span></span> <span data-ttu-id="5f304-111">A continuación, aprenderá a crear una credencial SQL Server para poder integrar SQL Server con Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="5f304-111">Then, you will learn how to create a SQL Server credential to be able to integrate SQL Server with Azure Storage.</span></span> <span data-ttu-id="5f304-112">A continuación, creará una base de datos en Azure Storage directamente.</span><span class="sxs-lookup"><span data-stu-id="5f304-112">Then, you will create a database in Azure Storage directly.</span></span> <span data-ttu-id="5f304-113">Por otra parte, el tutorial presentará escenarios de cifrado, migración y de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="5f304-113">In addition, the tutorial will demonstrate encryption, migration, and backup and restore scenarios.</span></span>  
  
 <span data-ttu-id="5f304-114">El tutorial se divide en nueve lecciones:</span><span class="sxs-lookup"><span data-stu-id="5f304-114">This tutorial is divided into nine lessons:</span></span>  
  
 <span data-ttu-id="5f304-115">**[Lección 1: Crear la cuenta y el contenedor de Azure Storage](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-115">**[Lesson 1: Create Azure Storage Account and Container](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span></span>  
 <span data-ttu-id="5f304-116">En esta lección, creará una cuenta de Azure Storage y un contenedor.</span><span class="sxs-lookup"><span data-stu-id="5f304-116">In this lesson, you create an Azure Storage account and a container.</span></span>  
  
 <span data-ttu-id="5f304-117">**[Lección 2. Crear una directiva en el contenedor y generar una firma de acceso compartido &#40;clave de&#41; SAS](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-117">**[Lesson 2. Create a policy on container and generate a Shared Access Signature &#40;SAS&#41; key](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="5f304-118">En esta lección, creará una directiva en el contenedor de blobs y también generará una firma de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="5f304-118">In this lesson, you create a policy on the Blob container and also generate a shared access signature.</span></span>  
  
 <span data-ttu-id="5f304-119">**[Lección 3: Crear una credencial de SQL Server](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-119">**[Lesson 3: Create a SQL Server Credential](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="5f304-120">En esta lección, creará una credencial para almacenar la información de seguridad usada para acceder a la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="5f304-120">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="5f304-121">**[Lección 4: Crear una base de datos en Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-121">**[Lesson 4: Create a database in Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span></span>  
 <span data-ttu-id="5f304-122">En esta lección, creará una base de datos en Azure Storage mediante la opción CREATE DATABASE FILENAME.</span><span class="sxs-lookup"><span data-stu-id="5f304-122">In this lesson, you create a database in Azure Storage using CREATE Database FILENAME option.</span></span>  
  
 <span data-ttu-id="5f304-123">**[Lección 5. &#40;opcional&#41; cifrar la base de datos mediante TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-123">**[Lesson 5. &#40;Optional&#41; Encrypt your database using TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span></span>  
 <span data-ttu-id="5f304-124">En esta lección, cifrará la base de datos mediante un cifrado de datos transparente (TDE) y un certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="5f304-124">In this lesson, you encrypt your database by using a transparent data encryption (TDE) and a server certificate.</span></span>  
  
 <span data-ttu-id="5f304-125">**[Lección 6: Migrar una base de datos desde un equipo de origen local a un equipo de destino en Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-125">**[Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="5f304-126">En esta lección, va a migrar una base de datos de local a una máquina virtual de Azure mediante la opción crear base de datos para adjuntar.</span><span class="sxs-lookup"><span data-stu-id="5f304-126">In this lesson, you migrate a database from on-premises to a virtual machine in Azure using CREATE DATABASE FOR ATTACH option.</span></span>  
  
 <span data-ttu-id="5f304-127">**[Lección 7: Mover los archivos de datos a Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-127">**[Lesson 7: Move your data files to Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="5f304-128">En esta lección, moverá los archivos de datos a Azure Storage mediante la instrucción ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="5f304-128">In this lesson, you move your data files to Azure Storage using ALTER DATABASE statement.</span></span>  
  
 <span data-ttu-id="5f304-129">**[Lección 8. Restaurar una base de datos a Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-129">**[Lesson 8. Restore a database to Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span></span>  
 <span data-ttu-id="5f304-130">En esta lección, restaurará una base de datos de a Azure Storage mediante la opción RESTOre Database MOVE.</span><span class="sxs-lookup"><span data-stu-id="5f304-130">In this lesson, you restore a database to Azure Storage using RESTORE Database MOVE option.</span></span>  
  
 <span data-ttu-id="5f304-131">**[Lección 9. Restaurar una base de datos desde Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="5f304-131">**[Lesson 9. Restore a database from Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span></span>  
 <span data-ttu-id="5f304-132">En esta lección, restaurará una base de datos de Azure Storage mediante la opción RESTOre Database MOVE.</span><span class="sxs-lookup"><span data-stu-id="5f304-132">In this lesson, you restore a database from Azure Storage using RESTORE Database MOVE option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f304-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f304-133">See Also</span></span>  
 [<span data-ttu-id="5f304-134">Archivos de datos de SQL Server en Azure</span><span class="sxs-lookup"><span data-stu-id="5f304-134">SQL Server Data Files in Azure</span></span>](databases/sql-server-data-files-in-microsoft-azure.md)  
  
  
