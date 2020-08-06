---
title: Características de bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 04518abb-8581-47c8-a601-ee9136c3c0eb
author: rothja
ms.author: jroth
ms.openlocfilehash: 56b9f9ba9cc6e11ea82b822ae10b31710c8617b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674156"
---
# <a name="database-features"></a><span data-ttu-id="16d7e-102">Características de la base de datos</span><span class="sxs-lookup"><span data-stu-id="16d7e-102">Database Features</span></span>
  <span data-ttu-id="16d7e-103">Esta sección contiene las características y las tareas asociadas a bases de datos, objetos de base de datos, tipos de datos y mecanismos usados para trabajar con datos o para administrarlos.</span><span class="sxs-lookup"><span data-stu-id="16d7e-103">This section contains the features and tasks associated with databases, database objects, data types, and the mechanisms used to work with or manage data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16d7e-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="16d7e-104">In This Section</span></span>  
  
|||
|--|--|
|[<span data-ttu-id="16d7e-105">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="16d7e-105">Databases</span></span>](databases/databases.md)|[<span data-ttu-id="16d7e-106">Copia de seguridad y restauración de bases de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="16d7e-106">Back Up and Restore of SQL Server Databases</span></span>](backup-restore/back-up-and-restore-of-sql-server-databases.md)|  
|[<span data-ttu-id="16d7e-107">Tablas</span><span class="sxs-lookup"><span data-stu-id="16d7e-107">Tables</span></span>](tables/tables.md)|[<span data-ttu-id="16d7e-108">Números de secuencia</span><span class="sxs-lookup"><span data-stu-id="16d7e-108">Sequence Numbers</span></span>](sequence-numbers/sequence-numbers.md)|[<span data-ttu-id="16d7e-109">Importar y exportar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-109">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](import-export/bulk-import-and-export-of-data-sql-server.md)|  
|[<span data-ttu-id="16d7e-110">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-110">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp/in-memory-oltp-in-memory-optimization.md)|[<span data-ttu-id="16d7e-111">Desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="16d7e-111">DDL Triggers</span></span>](triggers/ddl-triggers.md)|[<span data-ttu-id="16d7e-112">Data Compression</span><span class="sxs-lookup"><span data-stu-id="16d7e-112">Data Compression</span></span>](data-compression/data-compression.md)|  
|[<span data-ttu-id="16d7e-113">Índices</span><span class="sxs-lookup"><span data-stu-id="16d7e-113">Indexes</span></span>](indexes/indexes.md)|[<span data-ttu-id="16d7e-114">Desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="16d7e-114">DML Triggers</span></span>](triggers/dml-triggers.md)|[<span data-ttu-id="16d7e-115">Objetos de automatización OLE en Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16d7e-115">OLE Automation Objects in Transact-SQL</span></span>](stored-procedures/ole-automation-objects-in-transact-sql.md)|  
|[<span data-ttu-id="16d7e-116">Tablas e índices con particiones</span><span class="sxs-lookup"><span data-stu-id="16d7e-116">Partitioned Tables and Indexes</span></span>](partitions/partitioned-tables-and-indexes.md)|[<span data-ttu-id="16d7e-117">Sinónimos &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-117">Synonyms &#40;Database Engine&#41;</span></span>](synonyms/synonyms-database-engine.md)|[<span data-ttu-id="16d7e-118">Notificaciones de eventos</span><span class="sxs-lookup"><span data-stu-id="16d7e-118">Event Notifications</span></span>](service-broker/event-notifications.md)|  
|[<span data-ttu-id="16d7e-119">Vistas</span><span class="sxs-lookup"><span data-stu-id="16d7e-119">Views</span></span>](views/views.md)|[<span data-ttu-id="16d7e-120">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-120">XML Data &#40;SQL Server&#41;</span></span>](xml/xml-data-sql-server.md)|[<span data-ttu-id="16d7e-121">Supervisión y optimización del rendimiento</span><span class="sxs-lookup"><span data-stu-id="16d7e-121">Monitor and Tune for Performance</span></span>](performance/monitor-and-tune-for-performance.md)|  
|[<span data-ttu-id="16d7e-122">Procedimientos almacenados &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-122">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures/stored-procedures-database-engine.md)|[<span data-ttu-id="16d7e-123">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial/spatial-data-sql-server.md)||  
|[<span data-ttu-id="16d7e-124">SQL Server de &#40;de búsqueda&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-124">Search &#40;SQL Server&#41;</span></span>](../database-engine/search-sql-server.md)|[<span data-ttu-id="16d7e-125">Datos de objeto binario grande &#40;Blob&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-125">Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;</span></span>](blob/binary-large-object-blob-data-sql-server.md)||  
|[<span data-ttu-id="16d7e-126">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="16d7e-126">User-Defined Functions</span></span>](user-defined-functions/user-defined-functions.md)|[<span data-ttu-id="16d7e-127">Aplicaciones de capa de datos</span><span class="sxs-lookup"><span data-stu-id="16d7e-127">Data-tier Applications</span></span>](data-tier-applications/data-tier-applications.md)||  
|[<span data-ttu-id="16d7e-128">estadísticas</span><span class="sxs-lookup"><span data-stu-id="16d7e-128">Statistics</span></span>](statistics/statistics.md)|[<span data-ttu-id="16d7e-129">El registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-129">The Transaction Log &#40;SQL Server&#41;</span></span>](logs/the-transaction-log-sql-server.md)||  
|[<span data-ttu-id="16d7e-130">Guías de plan</span><span class="sxs-lookup"><span data-stu-id="16d7e-130">Plan Guides</span></span>](performance/plan-guides.md)|[<span data-ttu-id="16d7e-131">Puntos de comprobación de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16d7e-131">Database Checkpoints &#40;SQL Server&#41;</span></span>](logs/database-checkpoints-sql-server.md)||  
  
  
