---
title: Ver el tamaño del archivo disperso de una instantánea de base de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server database snapshots], sparse files
- space [SQL Server], sparse files
- sparse files [SQL Server]
- size [SQL Server], sparse files
- maximum sparse file size
- database snapshots [SQL Server], sparse files
- space [SQL Server], database snapshots
ms.assetid: 1867c5f8-d57c-46d3-933d-3642ab0a8e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: 424399b9915c8e7e26e1076fd2e553aafe06fcf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747613"
---
# <a name="view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql"></a><span data-ttu-id="79156-102">Ver el tamaño del archivo disperso de una instantánea de base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="79156-102">View the Size of the Sparse File of a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="79156-103">En este tema se describe cómo usar [!INCLUDE[tsql](../../includes/tsql-md.md)] para comprobar que un archivo de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un archivo disperso y para determinar su tamaño real y máximo.</span><span class="sxs-lookup"><span data-stu-id="79156-103">This topic describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to verify that a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database file is a sparse file and to find out its actual and maximum sizes.</span></span> <span data-ttu-id="79156-104">Las instantáneas de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usan archivos dispersos, que son una característica del sistema de archivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="79156-104">Sparse files, which are a feature of the NTFS file system, are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshots.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79156-105">Durante la creación de instantáneas de base de datos, se crean archivos dispersos con los nombres de archivo de la instrucción CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="79156-105">During database snapshot creation, sparse files are created by using the file names in the CREATE DATABASE statement.</span></span> <span data-ttu-id="79156-106">Estos nombres de archivo se almacenan en la columna **physical_name** de **sys.master_files** .</span><span class="sxs-lookup"><span data-stu-id="79156-106">These file names are stored in **sys.master_files** in the **physical_name** column.</span></span> <span data-ttu-id="79156-107">En **sys.database_files** , ya sea en la base de datos de origen o en una instantánea, la columna **physical_name** siempre incluye los nombres de los archivos de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="79156-107">In **sys.database_files** (whether in the source database or in a snapshot), the **physical_name** column always contains the names of the source database files.</span></span>  
  
## <a name="verify-that-a-database-file-is-a-sparse-file"></a><span data-ttu-id="79156-108">Comprobar que un archivo de base de datos es un archivo disperso</span><span class="sxs-lookup"><span data-stu-id="79156-108">Verify that a Database File is a Sparse File</span></span>  
  
1.  <span data-ttu-id="79156-109">En la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79156-109">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="79156-110">Seleccione la columna **is_sparse** de **sys.database_files** en la instantánea de base de datos o de **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="79156-110">Select the **is_sparse** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="79156-111">El valor indica si el archivo es un archivo disperso, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="79156-111">The value indicates whether the file is a sparse file, as follows:</span></span>  
  
     <span data-ttu-id="79156-112">1 = El archivo es un archivo disperso.</span><span class="sxs-lookup"><span data-stu-id="79156-112">1 = File is a sparse file.</span></span>  
  
     <span data-ttu-id="79156-113">0 = El archivo no es un archivo disperso.</span><span class="sxs-lookup"><span data-stu-id="79156-113">0 = File is not a sparse file.</span></span>  
  
## <a name="find-out-the-actual-size-of-a-sparse-file"></a><span data-ttu-id="79156-114">Calcular el tamaño real de un archivo disperso</span><span class="sxs-lookup"><span data-stu-id="79156-114">Find Out the Actual Size of a Sparse File</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79156-115">El tamaño de los archivos dispersos aumenta en incrementos de 64 kilobytes (KB), por lo que siempre es un múltiplo de 64 KB.</span><span class="sxs-lookup"><span data-stu-id="79156-115">Sparse files grow in 64-kilobyte (KB) increments; thus, the size of a sparse file on disk is always a multiple of 64 KB.</span></span>  
  
 <span data-ttu-id="79156-116">Para ver el número de bytes que cada archivo disperso de una instantánea está usando actualmente en el disco, consulte la columna **size_on_disk_bytes** de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vista de administración dinámica [Sys. dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="79156-116">To view the number of bytes that each sparse file of a snapshot is currently using on disk, query the **size_on_disk_bytes** column of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][sys.dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) dynamic management view.</span></span>  
  
 <span data-ttu-id="79156-117">Para ver el espacio en disco que usa un archivo disperso, haga clic con el botón derecho en el archivo en Microsoft Windows, haga clic en **Propiedades**y consulte el valor de **Tamaño en disco** .</span><span class="sxs-lookup"><span data-stu-id="79156-117">To view the disk space used by a sparse file, right-click the file in Microsoft Windows, click **Properties**, and look at the **Size on disk** value.</span></span>  
  
## <a name="find-out-the-maximum-size-of-a-sparse-file"></a><span data-ttu-id="79156-118">Calcular el tamaño máximo de un archivo disperso</span><span class="sxs-lookup"><span data-stu-id="79156-118">Find Out the Maximum Size of a Sparse File</span></span>  
 <span data-ttu-id="79156-119">El tamaño máximo de un archivo disperso es el tamaño del archivo de la base de datos de origen correspondiente en el momento de la creación de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="79156-119">The maximum size to which a sparse can grow is the size of the corresponding source database file at the time of the snapshot creation.</span></span> <span data-ttu-id="79156-120">Para saber cuál es este tamaño, puede usar cualquiera de las alternativas siguientes:</span><span class="sxs-lookup"><span data-stu-id="79156-120">To learn this size, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="79156-121">Con el símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="79156-121">Using Windows Command Prompt:</span></span>  
  
    1.  <span data-ttu-id="79156-122">Utilice los comandos **dir** de Windows.</span><span class="sxs-lookup"><span data-stu-id="79156-122">Use Windows **dir** commands.</span></span>  
  
    2.  <span data-ttu-id="79156-123">Seleccione el archivo disperso, abra el cuadro de diálogo **Propiedades** del archivo en Windows y consulte el valor de **Tamaño** .</span><span class="sxs-lookup"><span data-stu-id="79156-123">Select the sparse file, open the file **Properties** dialog box in Windows, and look at the **Size** value.</span></span>  
  
-   <span data-ttu-id="79156-124">En la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79156-124">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="79156-125">Seleccione la columna **size** de **sys.database_files** en la instantánea de base de datos o de **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="79156-125">Select the **size** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="79156-126">El valor de la columna **size** refleja el espacio máximo, en páginas SQL, que puede usar la instantánea. Este valor es equivalente al del campo **Tamaño** de Windows, con la diferencia de que se representa en términos de número de páginas SQL del archivo. El tamaño en bytes es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="79156-126">The value of **size** column reflects the maximum space, in SQL pages, that the snapshot can ever use; this value is equivalent to the Windows **Size** field, except that it is represented in terms of the number of SQL pages in the file; the size in bytes is:</span></span>  
  
     <span data-ttu-id="79156-127">( *número_de_páginas* \* 8192)</span><span class="sxs-lookup"><span data-stu-id="79156-127">( *number_of_pages* \* 8192)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79156-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79156-128">See Also</span></span>  
 <span data-ttu-id="79156-129">[Instantáneas de bases de datos &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="79156-129">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="79156-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="79156-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span></span>  
 <span data-ttu-id="79156-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="79156-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 [<span data-ttu-id="79156-132">sys.master_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="79156-132">sys.master_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)  
  
  
