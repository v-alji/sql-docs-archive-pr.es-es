---
title: Creación y administración del almacenamiento de objetos con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 622aabe6-95c7-42cc-8768-ac2e679c5089
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 118e5e582a284023dd8e5cc71629d635e79fb989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671560"
---
# <a name="creating-and-managing-storage-for-memory-optimized-objects"></a><span data-ttu-id="e033a-102">Crear y administrar el almacenamiento de objetos con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="e033a-102">Creating and Managing Storage for Memory-Optimized Objects</span></span>
  <span data-ttu-id="e033a-103">El motor de [!INCLUDE[hek_2](../../includes/hek-2-md.md)] está integrado en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], que le permite tener las tablas optimizadas para memoria y las tablas basadas en disco (tradicionales) en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="e033a-103">The [!INCLUDE[hek_2](../../includes/hek-2-md.md)] engine is integrated into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which lets you have both memory-optimized tables and (traditional) disk-based tables in the same database.</span></span> <span data-ttu-id="e033a-104">Sin embargo, la estructura de almacenamiento para tablas optimizadas para memoria es diferente de las tablas basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="e033a-104">However, the storage structure for memory-optimized tables is different from disk-based tables.</span></span>  
  
 <span data-ttu-id="e033a-105">El almacenamiento para tablas basadas en disco tiene los siguientes atributos clave:</span><span class="sxs-lookup"><span data-stu-id="e033a-105">Storage for disk-based table has following key attributes:</span></span>  
  
-   <span data-ttu-id="e033a-106">Está asignado a un grupo de archivos y el grupo de archivos contiene uno o más archivos.</span><span class="sxs-lookup"><span data-stu-id="e033a-106">Mapped to a filegroup and the filegroup contains one or more files.</span></span>  
  
-   <span data-ttu-id="e033a-107">Cada archivo está dividido en extensiones de 8 páginas y cada página tiene 8 KB.</span><span class="sxs-lookup"><span data-stu-id="e033a-107">Each file is divided into extents of 8 pages and each page is of size 8K bytes.</span></span>  
  
-   <span data-ttu-id="e033a-108">Una extensión se puede compartir entre varias tablas, pero hay una asignación 1 a 1 entre una página asignada y la tabla o índice.</span><span class="sxs-lookup"><span data-stu-id="e033a-108">An extent can be shared across multiple tables, but a there is 1-to-1 mapping between an allocated page and the table or index.</span></span> <span data-ttu-id="e033a-109">En otras palabras, una página no puede tener filas de dos o más tablas o índices.</span><span class="sxs-lookup"><span data-stu-id="e033a-109">In other words, a page can't have rows from two or more tables or index.</span></span>  
  
-   <span data-ttu-id="e033a-110">Los datos se mueven a la memoria (el grupo de búferes) según sea necesario y las páginas modificadas o recién creadas se escriben asincrónicamente en el disco que genera la E/S principalmente aleatoria.</span><span class="sxs-lookup"><span data-stu-id="e033a-110">The data is moved into memory (the buffer pool) as needed and the modified or newly created pages are asynchronously written to the disk generating mostly random IO.</span></span>  
  
 <span data-ttu-id="e033a-111">El almacenamiento de tablas optimizadas para memoria tiene los siguientes atributos clave:</span><span class="sxs-lookup"><span data-stu-id="e033a-111">Storage for memory-optimized tables has following key attributes:</span></span>  
  
-   <span data-ttu-id="e033a-112">Todas las tablas optimizadas para memoria se asignan a un grupo de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="e033a-112">All memory-optimized tables are mapped to a memory-optimized filegroup.</span></span> <span data-ttu-id="e033a-113">Este grupo de archivos se genera mediante el grupo de archivos FileStream.</span><span class="sxs-lookup"><span data-stu-id="e033a-113">This filegroup is built using the filestream filegroup.</span></span>  
  
-   <span data-ttu-id="e033a-114">No existen páginas y los datos se guardan como una fila.</span><span class="sxs-lookup"><span data-stu-id="e033a-114">There are no pages and the data is persisted as a row.</span></span>  
  
-   <span data-ttu-id="e033a-115">Todos los cambios realizados en las tablas optimizadas para memoria se almacenan anexándolos a los archivos activos.</span><span class="sxs-lookup"><span data-stu-id="e033a-115">All changes to memory-optimized tables are stored by appending to active files.</span></span> <span data-ttu-id="e033a-116">Tanto la lectura como la escritura en los archivos son secuenciales.</span><span class="sxs-lookup"><span data-stu-id="e033a-116">Both reading and writing to files is sequential.</span></span>  
  
-   <span data-ttu-id="e033a-117">Una actualización se implementa como una eliminación seguida de una inserción.</span><span class="sxs-lookup"><span data-stu-id="e033a-117">An update is implemented as a delete followed by an insert.</span></span> <span data-ttu-id="e033a-118">Las filas eliminadas no se quitan inmediatamente del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e033a-118">The deleted rows are not immediately removed from the storage.</span></span> <span data-ttu-id="e033a-119">Las filas eliminadas se quitan mediante un proceso en segundo plano, denominado MERGE, según una directiva como se describe en [Durabilidad de las tablas con optimización para memoria](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e033a-119">The deleted rows are removed by a background process, called MERGE, based on a policy as described in [Durability for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="e033a-120">A diferencia de las tablas basadas en disco, el almacenamiento de tablas optimizadas para memoria no se comprime.</span><span class="sxs-lookup"><span data-stu-id="e033a-120">Unlike disk-based tables, storage for memory-optimized tables is not compressed.</span></span> <span data-ttu-id="e033a-121">Al migrar una tabla basada en disco (ROW o PAGE) comprimida tabla a una tabla optimizada para memoria, debe tener en cuenta el cambio del tamaño.</span><span class="sxs-lookup"><span data-stu-id="e033a-121">When migrating a compressed (ROW or PAGE) disk-based table to memory-optimized table, you will need to account for the change in size.</span></span>  
  
-   <span data-ttu-id="e033a-122">Una tabla optimizada para memoria puede ser durable o no durable.</span><span class="sxs-lookup"><span data-stu-id="e033a-122">A memory-optimized table can be durable or can be non-durable.</span></span> <span data-ttu-id="e033a-123">Solo tiene que configurar el almacenamiento para las tablas de optimización de memoria duradera.</span><span class="sxs-lookup"><span data-stu-id="e033a-123">You only need to configure storage for durable memory-optimize tables.</span></span>  
  
 <span data-ttu-id="e033a-124">En esta sección se describen los pares de archivos de punto de comprobación y otros aspectos de cómo se almacenan los datos en tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="e033a-124">This section describes checkpoint file pairs and other aspects of how data in memory-optimized tables is stored.</span></span>  
  
 <span data-ttu-id="e033a-125">Temas de esta sección:</span><span class="sxs-lookup"><span data-stu-id="e033a-125">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="e033a-126">Configurar el almacenamiento para las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="e033a-126">Configuring Storage for Memory-Optimized Tables</span></span>](configuring-storage-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="e033a-127">El grupo de archivos con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="e033a-127">The Memory Optimized Filegroup</span></span>](the-memory-optimized-filegroup.md)  
  
-   [<span data-ttu-id="e033a-128">Durabilidad de las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="e033a-128">Durability for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
-   [<span data-ttu-id="e033a-129">Funcionamiento de los puntos de comprobación para tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="e033a-129">Checkpoint Operation for Memory-Optimized Tables</span></span>](checkpoint-operation-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="e033a-130">Definir la durabilidad de los objetos con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="e033a-130">Defining Durability for Memory-Optimized Objects</span></span>](defining-durability-for-memory-optimized-objects.md)  
  
-   [<span data-ttu-id="e033a-131">Comparar el almacenamiento de tablas basadas en disco con el almacenamiento de tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="e033a-131">Comparing Disk-Based Table Storage to Memory-Optimized Table Storage</span></span>](comparing-disk-based-table-storage-to-memory-optimized-table-storage.md)  
  
-   [<span data-ttu-id="e033a-132">Supervisar y solucionar los problemas de la mezcla para los pares de archivos delta y de datos</span><span class="sxs-lookup"><span data-stu-id="e033a-132">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>](../../database-engine/monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs.md)  
  
## <a name="see-also"></a><span data-ttu-id="e033a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e033a-133">See Also</span></span>  
 [<span data-ttu-id="e033a-134">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="e033a-134">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
