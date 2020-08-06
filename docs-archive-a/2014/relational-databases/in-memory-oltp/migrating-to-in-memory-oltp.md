---
title: Migración a OLTP en memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 405cdac5-a0d4-47a4-9180-82876b773b82
author: rothja
ms.author: jroth
ms.openlocfilehash: ed764ce52d41d76667213b846cec51b26f634a27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750990"
---
# <a name="migrating-to-in-memory-oltp"></a><span data-ttu-id="71504-102">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="71504-102">Migrating to In-Memory OLTP</span></span>
  <span data-ttu-id="71504-103">En esta sección se describe cómo migrar los objetos de base de datos para usar OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="71504-103">This section discusses how to migrate database objects to use In-Memory OLTP.</span></span>  
  
-   [<span data-ttu-id="71504-104">Determinar si una tabla o un procedimiento almacenado se debe pasar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="71504-104">Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP</span></span>](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)  
  
-   [<span data-ttu-id="71504-105">Asesor de optimización en memoria</span><span class="sxs-lookup"><span data-stu-id="71504-105">Memory Optimization Advisor</span></span>](memory-optimization-advisor.md)  
  
-   [<span data-ttu-id="71504-106">Asistente de compilación nativa</span><span class="sxs-lookup"><span data-stu-id="71504-106">Native Compilation Advisor</span></span>](native-compilation-advisor.md)  
  
-   [<span data-ttu-id="71504-107">Construcciones de Transact-SQL no admitidas en In-Memory OLTP.</span><span class="sxs-lookup"><span data-stu-id="71504-107">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
-   [<span data-ttu-id="71504-108">Implementar columnas LOB en una tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="71504-108">Implementing LOB Columns in a Memory-Optimized Table</span></span>](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="71504-109">Implementar SQL_VARIANT en una tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="71504-109">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="71504-110">Problemas de migración para los procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="71504-110">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="71504-111">Migrar columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="71504-111">Migrating Computed Columns</span></span>](migrating-computed-columns.md)  
  
-   [<span data-ttu-id="71504-112">Migrar desencadenadores</span><span class="sxs-lookup"><span data-stu-id="71504-112">Migrating Triggers</span></span>](migrating-triggers.md)  
  
-   [<span data-ttu-id="71504-113">Consultas entre bases de datos</span><span class="sxs-lookup"><span data-stu-id="71504-113">Cross-Database Queries</span></span>](cross-database-queries.md)  
  
-   [<span data-ttu-id="71504-114">Migrar restricciones CHECK y de clave externa</span><span class="sxs-lookup"><span data-stu-id="71504-114">Migrating Check and Foreign Key Constraints</span></span>](../../database-engine/migrating-check-and-foreign-key-constraints.md)  
  
-   [<span data-ttu-id="71504-115">Implementar IDENTITY en una tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="71504-115">Implementing IDENTITY in a Memory-Optimized Table</span></span>](implementing-identity-in-a-memory-optimized-table.md)  
  
 <span data-ttu-id="71504-116">Para obtener más información sobre las metodologías de migración, vea [OLTP en memoria: patrones de carga de trabajo comunes y consideraciones sobre la migración](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="71504-116">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71504-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71504-117">See Also</span></span>  
 <span data-ttu-id="71504-118">[OLTP en memoria &#40;optimización en memoria&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="71504-118">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 [<span data-ttu-id="71504-119">Estimar los requisitos de memoria para las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="71504-119">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
