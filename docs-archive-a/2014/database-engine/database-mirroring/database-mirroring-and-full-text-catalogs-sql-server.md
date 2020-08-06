---
title: Creación de reflejo de la base de datos y catálogos de texto completo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- full-text catalogs [SQL Server], database mirroring
- catalogs [SQL Server], database mirroring
ms.assetid: e34072ae-fe8a-462d-bb03-02fa0987f793
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 39929f4bed6edbd1e8ec5c1b72dbe8f7aefeec68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670566"
---
# <a name="database-mirroring-and-full-text-catalogs-sql-server"></a><span data-ttu-id="f60e9-102">Creación de reflejo de la base de datos y catálogos de texto completo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f60e9-102">Database Mirroring and Full-Text Catalogs (SQL Server)</span></span>
  <span data-ttu-id="f60e9-103">Para crear un reflejo de base de datos que tenga un catálogo de texto completo, utilice una copia de seguridad de la forma habitual para crear una copia de seguridad completa de base de datos de la base de datos principal y, a continuación, restaure la copia de seguridad para copiar la base de datos al servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="f60e9-103">To mirror a database that has a full-text catalog, use backup as usual to create a full database backup of the principal database, and then restore the backup to copy the database to the mirror server.</span></span> <span data-ttu-id="f60e9-104">Para obtener más información, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f60e9-104">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
## <a name="full-text-catalog-and-indexes-before-failover"></a><span data-ttu-id="f60e9-105">Catálogo de texto completo e índices antes de la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="f60e9-105">Full-Text Catalog and Indexes Before Failover</span></span>  
 <span data-ttu-id="f60e9-106">En la base de datos reflejada recién creada, el catálogo de texto completo es el mismo que cuando se creó la copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f60e9-106">In a newly created mirror database, the full-text catalog is the same as when the database was backed up.</span></span> <span data-ttu-id="f60e9-107">Después de que empiece la creación de reflejo de la base de datos, los cambios en el catálogo realizados por instrucciones de DDL (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) se registran y se envían al servidor reflejado para que se vuelvan a reproducir en la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="f60e9-107">After database mirroring starts, any catalog-level changes that were made by DDL statements (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) are logged and sent to the mirror server to be replayed on the mirror database.</span></span> <span data-ttu-id="f60e9-108">Sin embargo, los cambios en el índice no se reproducen en la base de datos reflejada porque no está registrada en el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="f60e9-108">However, index-level changes are not reproduced on the mirror database because it is not logged on to the principal server.</span></span> <span data-ttu-id="f60e9-109">Por tanto, puesto que el contenido del catálogo de texto completo cambia en la base de datos principal, el contenido del catálogo de texto completo de la base de datos reflejada no está sincronizado.</span><span class="sxs-lookup"><span data-stu-id="f60e9-109">Therefore, as the contents of the full-text catalog change on the principal database, the contents of the full-text catalog on the mirror database are unsynchronized.</span></span>  
  
## <a name="full-text-indexes-after-failover"></a><span data-ttu-id="f60e9-110">Índices de texto completo después de la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="f60e9-110">Full-Text Indexes After Failover</span></span>  
 <span data-ttu-id="f60e9-111">Después de una conmutación por error, es posible que se necesite o que resulte útil un rastreo completo de un índice de texto completo en el nuevo servidor principal en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="f60e9-111">After a failover, a full crawl of a full-text index on the new principal server might be required or useful in the following situations:</span></span>  
  
-   <span data-ttu-id="f60e9-112">Si el seguimiento de cambios está DESACTIVADO en un índice de texto completo, debe iniciar un rastreo completo en ese índice con la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="f60e9-112">If change-tracking is turned OFF on a full text index, you must start a full crawl on that index by using the following statement:</span></span>  
  
     <span data-ttu-id="f60e9-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span><span class="sxs-lookup"><span data-stu-id="f60e9-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span></span>  
  
-   <span data-ttu-id="f60e9-114">Si un índice de texto completo está configurado para seguimiento de cambios automático, el índice de texto completo se sincronizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f60e9-114">If a full-text index is configured for automatic change tracking, the full-text index is automatically synchronized.</span></span> <span data-ttu-id="f60e9-115">Sin embargo, la sincronización reduce el rendimiento de texto completo en cierta medida.</span><span class="sxs-lookup"><span data-stu-id="f60e9-115">However, synchronization slows full-text performance somewhat.</span></span> <span data-ttu-id="f60e9-116">Si el rendimiento es demasiado lento, puede desencadenar un rastreo completo desactivando el seguimiento de cambios y restableciéndolo al modo automático.</span><span class="sxs-lookup"><span data-stu-id="f60e9-116">If performance is too slow, you can cause a full crawl by setting change tracking off and then resetting it to automatic:</span></span>  
  
    -   <span data-ttu-id="f60e9-117">Para desactivar el seguimiento de cambios:</span><span class="sxs-lookup"><span data-stu-id="f60e9-117">To set change tracking off:</span></span>  
  
         <span data-ttu-id="f60e9-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="f60e9-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span></span>  
  
    -   <span data-ttu-id="f60e9-119">Para establecer el seguimiento de cambios automático al modo automático:</span><span class="sxs-lookup"><span data-stu-id="f60e9-119">To set on automatic change tracking to automatic:</span></span>  
  
         <span data-ttu-id="f60e9-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="f60e9-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f60e9-121">Para ver si el seguimiento de cambios automático está activado, puede usar la función [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) para consultar la propiedad **TableFullTextBackgroundUpdateIndexOn** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="f60e9-121">To see whether auto change tracking is on, you can use the [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) function to query the **TableFullTextBackgroundUpdateIndexOn** property of the table.</span></span>  
  
 <span data-ttu-id="f60e9-122">Para obtener más información, vea [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f60e9-122">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f60e9-123">El inicio de un rastreo después de una conmutación por error funciona igual que el inicio de un rastreo después de una operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="f60e9-123">Starting a crawl after failover works the same as starting a crawl after a restore.</span></span>  
  
## <a name="after-forcing-service"></a><span data-ttu-id="f60e9-124">Después de forzar el servicio</span><span class="sxs-lookup"><span data-stu-id="f60e9-124">After Forcing Service</span></span>  
 <span data-ttu-id="f60e9-125">Después de forzar el servicio al servidor reflejado (con posible pérdida de datos), inicie un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="f60e9-125">After service is forced to the mirror server (with possible data loss), start a full crawl.</span></span> <span data-ttu-id="f60e9-126">El método que debe usar para iniciar un rastreo completo depende de si el índice de texto completo tiene seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="f60e9-126">The method to use for starting a full crawl depends on whether the full-text index is change tracked.</span></span> <span data-ttu-id="f60e9-127">Para obtener más información, vea "Índices de texto completo después de la conmutación por error" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="f60e9-127">For more information, see "Full-Text Indexes After Failover," earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60e9-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f60e9-128">See Also</span></span>  
 <span data-ttu-id="f60e9-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f60e9-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="f60e9-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f60e9-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="f60e9-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f60e9-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="f60e9-132">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f60e9-132">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="f60e9-133">Realizar copias de seguridad de los catálogos e índices de texto completo y restaurarlos</span><span class="sxs-lookup"><span data-stu-id="f60e9-133">Back Up and Restore Full-Text Catalogs and Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
  
