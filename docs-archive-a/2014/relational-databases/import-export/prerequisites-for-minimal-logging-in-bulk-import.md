---
title: Requisitos previos para el registro mínimo durante la importación masiva | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- minimal logging [SQL Server]
- logged bulk copy [SQL Server]
- logs [SQL Server], minimal logging
- minimally logged operations [SQL Server]
- bulk importing [SQL Server], minimal logging
ms.assetid: bd1dac6b-6ef8-4735-ad4e-67bb42dc4f66
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4711e25dcfcc99e14894e47166638673c61a6831
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749942"
---
# <a name="prerequisites-for-minimal-logging-in-bulk-import"></a><span data-ttu-id="531c1-102">Requisitos previos para el registro mínimo durante la importación masiva</span><span class="sxs-lookup"><span data-stu-id="531c1-102">Prerequisites for Minimal Logging in Bulk Import</span></span>
  <span data-ttu-id="531c1-103">En el caso de las bases de datos que utilizan el modelo de recuperación completa, todas las operaciones de inserción de filas que se efectúan durante la importación masiva se registran por completo en el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="531c1-103">For a database under the full recovery model, all row-insert operations that are performed by bulk import are fully logged in the transaction log.</span></span> <span data-ttu-id="531c1-104">Las importaciones de datos de gran volumen pueden hacer que el registro de transacciones se llene rápidamente si se utiliza el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="531c1-104">Large data imports can cause the transaction log to fill rapidly if the full recovery model is used.</span></span> <span data-ttu-id="531c1-105">En cambio, bajo el modelo de recuperación simple o el modelo de recuperación optimizado para cargas masivas de registros, el registro mínimo de operaciones de importaciones masivas reduce la posibilidad de que una de estas operaciones acabe con el espacio del registro.</span><span class="sxs-lookup"><span data-stu-id="531c1-105">In contrast, under the simple recovery model or bulk-logged recovery model, minimal logging of bulk-import operations reduces the possibility that a bulk-import operation will fill the log space.</span></span> <span data-ttu-id="531c1-106">Además, el registro mínimo es más eficaz que el completo.</span><span class="sxs-lookup"><span data-stu-id="531c1-106">Minimal logging is also more efficient than full logging.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="531c1-107">El modelo de recuperación optimizado para cargas masivas de registros está diseñado para reemplazar temporalmente al modelo de recuperación completa durante operaciones masivas de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="531c1-107">The bulk-logged recovery model is designed to temporarily replace the full recovery model during large bulk operations.</span></span>  
  
## <a name="table-requirements-for-minimally-logging-bulk-import-operations"></a><span data-ttu-id="531c1-108">Requisitos de las tablas para las operaciones de importación masiva de registro mínimo</span><span class="sxs-lookup"><span data-stu-id="531c1-108">Table Requirements for Minimally Logging Bulk-Import Operations</span></span>  
 <span data-ttu-id="531c1-109">El registro mínimo exige que la tabla de destino cumpla las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="531c1-109">Minimal logging requires that the target table meets the following conditions:</span></span>  
  
-   <span data-ttu-id="531c1-110">La tabla no se está replicando.</span><span class="sxs-lookup"><span data-stu-id="531c1-110">The table is not being replicated.</span></span>  
  
-   <span data-ttu-id="531c1-111">Se ha especificado el bloqueo de tabla (mediante TABLOCK).</span><span class="sxs-lookup"><span data-stu-id="531c1-111">Table locking is specified (using TABLOCK).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="531c1-112">Aunque no se registren las inserciones de datos en el registro de transacciones cuando se realiza una importación masiva de registro mínimo, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] seguirá registrando las asignaciones de extensiones cada vez que se asigne una nueva a la tabla.</span><span class="sxs-lookup"><span data-stu-id="531c1-112">Although data insertions are not logged in the transaction log during a minimally logged bulk-import operation, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] still logs extent allocations each time a new extent is allocated to the table.</span></span>  
  
-   <span data-ttu-id="531c1-113">La tabla no está optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="531c1-113">Table is not a memory-optimized table.</span></span>  
  
 <span data-ttu-id="531c1-114">La posibilidad de utilizar el registro mínimo con una tabla también depende de si la tabla está indizada y, en este caso, de si está vacía:</span><span class="sxs-lookup"><span data-stu-id="531c1-114">Whether minimal logging can occur for a table also depends on whether the table is indexed and, if so, whether the table is empty:</span></span>  
  
-   <span data-ttu-id="531c1-115">Si la tabla no tiene índices, el registro de las páginas de datos será mínimo.</span><span class="sxs-lookup"><span data-stu-id="531c1-115">If the table has no indexes, data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="531c1-116">Si la tabla no tiene índice clúster sino uno o más índices no clúster, el registro de las páginas de datos siempre será mínimo.</span><span class="sxs-lookup"><span data-stu-id="531c1-116">If the table has no clustered index but has one or more nonclustered indexes, data pages are always minimally logged.</span></span> <span data-ttu-id="531c1-117">Sin embargo, el modo en que se registran las páginas de índice depende de si la tabla está vacía:</span><span class="sxs-lookup"><span data-stu-id="531c1-117">How index pages are logged, however, depends on whether the table is empty:</span></span>  
  
    -   <span data-ttu-id="531c1-118">Si la tabla está vacía, el registro de las páginas de índice será mínimo.</span><span class="sxs-lookup"><span data-stu-id="531c1-118">If the table is empty, index pages are minimally logged.</span></span>  
  
    -   <span data-ttu-id="531c1-119">Si la tabla no está vacía, el registro de las páginas de índice será completo.</span><span class="sxs-lookup"><span data-stu-id="531c1-119">If table is non-empty, index pages are fully logged.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="531c1-120">Si empieza con una tabla vacía y realiza una importación masiva de datos mediante varios lotes, el registro de las páginas de índice y de datos será mínimo para el primer lote pero, a partir del segundo lote, solo las páginas de datos se registrarán de forma mínima.</span><span class="sxs-lookup"><span data-stu-id="531c1-120">If you start with an empty table and bulk import the data in multiple batches, both index and data pages are minimally logged for the first batch, but beginning with the second batch, only data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="531c1-121">Si la tabla tiene un índice clúster y está vacía, tanto las páginas de datos como de índice se registrarán de forma mínima.</span><span class="sxs-lookup"><span data-stu-id="531c1-121">If the table has a clustered index and is empty, both data and index pages are minimally logged.</span></span> <span data-ttu-id="531c1-122">En cambio, si la tabla tiene un índice clúster pero no está vacía, tanto las páginas de datos como las de índice se registrarán de forma completa, independientemente del modelo de recuperación utilizado.</span><span class="sxs-lookup"><span data-stu-id="531c1-122">In contrast, if a table has a clustered index and is non-empty, data pages and index pages are both fully logged regardless of the recovery model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="531c1-123">Si empieza con una tabla vacía y realiza una importación masiva de datos mediante varios lotes, el registro de las páginas de índice y de datos será mínimo para el primer lote pero, a partir del segundo lote, solo las páginas de datos se registrarán de forma mínima.</span><span class="sxs-lookup"><span data-stu-id="531c1-123">If you start with an empty table and bulk import the data in batches, both index and data pages are minimally logged for the first batch, but from the second batch onwards, only data pages are bulk logged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="531c1-124">Cuando la replicación transaccional está habilitada, las operaciones BULK INSERT se registran por completo en el modelo de recuperación optimizado para cargas masivas de registros.</span><span class="sxs-lookup"><span data-stu-id="531c1-124">When transactional replication is enabled, BULK INSERT operations are fully logged even under the Bulk Logged recovery model.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="531c1-125">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="531c1-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="531c1-126">Ver o cambiar el modelo de recuperación de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="531c1-126">View or Change the Recovery Model of a Database &#40;SQL Server&#41;</span></span>](../backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="531c1-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="531c1-127">See Also</span></span>  
 <span data-ttu-id="531c1-128">[Modelos de recuperación &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="531c1-128">[Recovery Models &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="531c1-129">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="531c1-129">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="531c1-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="531c1-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="531c1-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="531c1-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="531c1-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="531c1-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="531c1-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="531c1-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="531c1-134">[Sugerencias de tabla &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="531c1-134">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 [<span data-ttu-id="531c1-135">INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="531c1-135">INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/insert-transact-sql)  
  
  
