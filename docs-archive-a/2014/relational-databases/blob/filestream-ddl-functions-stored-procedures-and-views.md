---
title: FILESTREAM DDL, funciones, procedimientos almacenados y vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
ms.assetid: 9ecb49ee-f64e-4d30-a803-e4064a21950a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dffcc454d21a0a8dea0e98c4db2c19a4af29e948
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662100"
---
# <a name="filestream-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="60588-102">FILESTREAM DDL, funciones, procedimientos almacenados y vistas</span><span class="sxs-lookup"><span data-stu-id="60588-102">FILESTREAM DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="60588-103">Enumera las instrucciones Transact-SQL y los objetos de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que admiten FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="60588-103">Lists the Transact-SQL statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that support FILESTREAM.</span></span>  
  
 <span data-ttu-id="60588-104">Para obtener la lista de objetos de base de datos que admiten la característica FileTable, vea [FileTable DDL, Functions, Stored Procedures, and Views](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="60588-104">For the list of database objects that support the FileTable feature, see [FileTable DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="60588-105">Instrucciones del lenguaje de definición de datos (DDL) de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60588-105">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
-   [<span data-ttu-id="60588-106">CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-106">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="60588-107">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-107">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="60588-108">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-108">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
-   [<span data-ttu-id="60588-109">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-109">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
-   [<span data-ttu-id="60588-110">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-110">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
-   <span data-ttu-id="60588-111">[DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="60588-111">[DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)DROP INDEX</span></span>  
  
##  <a name="system-functions"></a><a name="func"></a> <span data-ttu-id="60588-112">Funciones del sistema</span><span class="sxs-lookup"><span data-stu-id="60588-112">System Functions</span></span>  
  
-   [<span data-ttu-id="60588-113">GET_FILESTREAM_TRANSACTION_CONTEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-113">GET_FILESTREAM_TRANSACTION_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/get-filestream-transaction-context-transact-sql)  
  
-   [<span data-ttu-id="60588-114">PathName &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-114">PathName &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/pathname-transact-sql)  
  
##  <a name="system-stored-procedures"></a><a name="proc"></a> <span data-ttu-id="60588-115">Procedimientos almacenados del sistema</span><span class="sxs-lookup"><span data-stu-id="60588-115">System Stored Procedures</span></span>  
  
-   [<span data-ttu-id="60588-116">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="60588-117">sp_filestream_force_garbage_collection &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-117">sp_filestream_force_garbage_collection &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-filestream-force-garbage-collection)  
  
##  <a name="system-views---catalog-views"></a><a name="cat"></a> <span data-ttu-id="60588-118">Vistas del sistema: vistas de catálogo</span><span class="sxs-lookup"><span data-stu-id="60588-118">System Views - Catalog Views</span></span>  
  
-   [<span data-ttu-id="60588-119">sys.database_filestream_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-119">sys.database_filestream_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql)  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="60588-120">Vistas del sistema: vistas de administración dinámica</span><span class="sxs-lookup"><span data-stu-id="60588-120">System Views - Dynamic Management Views</span></span>  
  
-   [<span data-ttu-id="60588-121">sys.dm_filestream_file_io_handles &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-121">sys.dm_filestream_file_io_handles &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-handles-transact-sql)  
  
-   [<span data-ttu-id="60588-122">sys.dm_filestream_file_io_requests &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60588-122">sys.dm_filestream_file_io_requests &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-requests-transact-sql)  
  
##  <a name="programming-apis"></a><a name="api"></a> <span data-ttu-id="60588-123">API de programación</span><span class="sxs-lookup"><span data-stu-id="60588-123">Programming APIs</span></span>  
  
-   [<span data-ttu-id="60588-124">Obtener acceso a los datos FILESTREAM con OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="60588-124">Access FILESTREAM Data with OpenSqlFilestream</span></span>](access-filestream-data-with-opensqlfilestream.md)  
  
-   [<span data-ttu-id="60588-125">API administrada: clase SqlFileStream</span><span class="sxs-lookup"><span data-stu-id="60588-125">Managed API - SqlFileStream Class</span></span>](https://go.microsoft.com/fwlink/?LinkId=220875)  
  
  
