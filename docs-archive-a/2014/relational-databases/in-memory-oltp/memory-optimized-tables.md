---
title: Tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 14dddf81-b502-49dc-a6b6-d18b1ae32d2b
author: rothja
ms.author: jroth
ms.openlocfilehash: 73430505e55230daf31c492d882eadeb6d35d29f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749897"
---
# <a name="memory-optimized-tables"></a><span data-ttu-id="83786-102">Tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-102">Memory-Optimized Tables</span></span>
  <span data-ttu-id="83786-103">OLTP en memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ayuda a mejorar el rendimiento de las aplicaciones OLTP mediante un acceso a los datos eficiente y optimizado para memoria, compilación nativa de la lógica de negocios, y algoritmos sin bloqueos y bloqueos temporales.</span><span class="sxs-lookup"><span data-stu-id="83786-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] In-Memory OLTP helps improve performance of OLTP applications through efficient, memory-optimized data access, native compilation of business logic, and lock- and latch free algorithms.</span></span> <span data-ttu-id="83786-104">La característica OLTP en memoria incluye tablas optimizadas para memoria y tipos de tablas, así como la compilación nativa de procedimientos almacenados de [!INCLUDE[tsql](../../includes/tsql-md.md)] para un acceso eficiente a estas tablas.</span><span class="sxs-lookup"><span data-stu-id="83786-104">The In-Memory OLTP feature includes memory-optimized tables and table types, as well as native compilation of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures for efficient access to these tables.</span></span>  
  
 <span data-ttu-id="83786-105">Para obtener más información acerca de las tablas optimizadas para memoria, vea:</span><span class="sxs-lookup"><span data-stu-id="83786-105">For more information about memory-optimized tables, see:</span></span>  
  
-   [<span data-ttu-id="83786-106">Introducción a las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-106">Introduction to Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
     <span data-ttu-id="83786-107">Define las tablas optimizadas para memoria y proporciona información acerca de la durabilidad de los datos, el acceso a datos de tablas optimizadas para memoria, el rendimiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="83786-107">Details what memory-optimized tables are and provides information about data durability, accessing data in memory-optimized tables, and performance and scalability.</span></span>  
  
-   [<span data-ttu-id="83786-108">Compilación nativa de tablas y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="83786-108">Native Compilation of Tables and Stored Procedures</span></span>](../in-memory-oltp/natively-compiled-stored-procedures.md)  
  
     <span data-ttu-id="83786-109">Define cómo se compilan en DLL las tablas optimizadas para memoria y los procedimientos almacenados compilados de forma nativa, y proporciona consideraciones de seguridad relacionadas.</span><span class="sxs-lookup"><span data-stu-id="83786-109">Details how memory-optimized tables and natively compiled stored procedures are compiled into DLLs, and provides related security considerations.</span></span>  
  
-   [<span data-ttu-id="83786-110">Modificar tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-110">Altering Memory-Optimized Tables</span></span>](altering-memory-optimized-tables.md)  
  
     <span data-ttu-id="83786-111">Directrices para la actualización de tablas optimizadas para memoria (incluye el cambio de columnas de tabla, índices y bucket_count).</span><span class="sxs-lookup"><span data-stu-id="83786-111">Guidelines for updating memory-optimized tables (including changing table columns, indexes, and bucket_count).</span></span>  
  
-   [<span data-ttu-id="83786-112">Descripción de las transacciones en tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-112">Understanding Transactions on Memory-Optimized Tables</span></span>](../../database-engine/understanding-transactions-on-memory-optimized-tables.md)  
  
     <span data-ttu-id="83786-113">En esta sección se proporcionan varios temas relacionados con la realización de transacciones en tablas optimizadas para memoria, incluidos los niveles de aislamiento de las transacciones y las transacciones entre contenedores.</span><span class="sxs-lookup"><span data-stu-id="83786-113">This section provides several topics related to performing transactions on memory-optimized tables including transaction isolation levels, and cross-container transactions.</span></span>  
  
-   [<span data-ttu-id="83786-114">Patrón de aplicación para crear particiones de tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-114">Application Pattern for Partitioning Memory-Optimized Tables</span></span>](application-pattern-for-partitioning-memory-optimized-tables.md)  
  
     <span data-ttu-id="83786-115">Código de ejemplo detallado que muestra cómo emular tablas particionadas al usar tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="83786-115">Detailed code sample that shows how to emulate partitioned tables when using memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="83786-116">Estadísticas para las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-116">Statistics for Memory-Optimized Tables</span></span>](statistics-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="83786-117">Define cómo se compilan las estadísticas para las tablas optimizadas para memoria y cómo mantener y actualizar manualmente estadísticas para tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="83786-117">Details how statistics are compiled for memory-optimized tables and how to maintain and manually update statistics for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="83786-118">Intercalaciones y páginas de códigos</span><span class="sxs-lookup"><span data-stu-id="83786-118">Collations and Code Pages</span></span>](../../database-engine/collations-and-code-pages.md)  
  
     <span data-ttu-id="83786-119">Define las restricciones sobre intercalaciones compatibles y páginas de código para tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="83786-119">Details the restrictions on supported collations and code pages for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="83786-120">Tamaño de tabla y fila de las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-120">Table and Row Size in Memory-Optimized Tables</span></span>](table-and-row-size-in-memory-optimized-tables.md)  
  
     <span data-ttu-id="83786-121">Define el límite de 8060 sobre filas de tablas optimizadas para memoria y proporciona un ejemplo para calcular los tamaños de tablas y filas.</span><span class="sxs-lookup"><span data-stu-id="83786-121">Details the 8060 byte limit on memory-optimized table rows, and provides an example for calculating table and row sizes.</span></span>  
  
-   [<span data-ttu-id="83786-122">Guía del procesamiento de consultas para tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="83786-122">A Guide to Query Processing for Memory-Optimized Tables</span></span>](a-guide-to-query-processing-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="83786-123">Proporciona información general del procesamiento de consultas tanto para las tablas optimizadas para memoria como para los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="83786-123">Provides an overview of query processing for both memory-optimized tables, and natively compiled stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83786-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83786-124">See Also</span></span>  
 [<span data-ttu-id="83786-125">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="83786-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
