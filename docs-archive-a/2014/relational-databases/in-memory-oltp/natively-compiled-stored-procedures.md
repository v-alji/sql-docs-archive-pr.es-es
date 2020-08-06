---
title: Procedimientos almacenados compilados de forma nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- natively compiled stored procedures
ms.assetid: d5ed432c-10c5-4e4f-883c-ef4d1fa32366
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b8fb7a379c0c08ca357baa1042ebcf51c512c9ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748789"
---
# <a name="natively-compiled-stored-procedures"></a><span data-ttu-id="ad2c1-102">procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad2c1-102">Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="ad2c1-103">Los procedimientos almacenados compilados de forma nativa son los procedimientos almacenados de [!INCLUDE[tsql](../../includes/tsql-md.md)] compilados para código nativo que tienen acceso a las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="ad2c1-103">Natively compiled stored procedures are [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures compiled to native code that access memory-optimized tables.</span></span> <span data-ttu-id="ad2c1-104">Los procedimientos almacenados compilados de forma nativa permiten la ejecución eficaz de consultas y la lógica empresarial en el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="ad2c1-104">Natively compiled stored procedures allow for efficient execution of queries and business logic in the stored procedure.</span></span> <span data-ttu-id="ad2c1-105">Para obtener más información sobre el proceso de compilación nativa, vea [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ad2c1-105">For more details about the native compilation process, see [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span></span> <span data-ttu-id="ad2c1-106">Para obtener más información sobre cómo migrar procedimientos almacenados basados en disco a procedimientos almacenados compilados de forma nativa, vea [Problemas de migración para los procedimientos almacenados compilados de forma nativa](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ad2c1-106">For more information about migrating disk-based stored procedures to natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad2c1-107">Una diferencia entre los procedimientos almacenados (basados en disco) interpretados y los procedimientos almacenados compilados de forma nativa es que un procedimiento almacenado interpretado se compila en la primera ejecución mientras que un procedimiento almacenado compilado se compila cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="ad2c1-107">One difference between interpreted (disk-based) stored procedures and natively compiled stored procedures is that an interpreted stored procedure is compiled at first execution whereas a natively compiled stored procedure is compiled when it is created.</span></span> <span data-ttu-id="ad2c1-108">Con los procedimientos almacenados compilados de forma nativa, muchas condiciones de error (desbordamiento aritmético, conversión de tipo y otras condiciones de división por cero) se pueden detectar en el momento de la creación y harán que la creación del procedimiento almacenado compilado de forma nativa genere un error.</span><span class="sxs-lookup"><span data-stu-id="ad2c1-108">With natively compiled stored procedures, many error conditions (arithmetic overflow, type conversion, and some divide-by-zero conditions) can be detected at create time and will cause creation of the natively compiled stored procedure to fail.</span></span> <span data-ttu-id="ad2c1-109">Con los procedimientos almacenados interpretados, estas condiciones de error normalmente no provocarán un error al crear el procedimiento almacenado, pero todas las ejecuciones producirán un error.</span><span class="sxs-lookup"><span data-stu-id="ad2c1-109">With interpreted stored procedures, these error conditions will typically not cause a failure when the stored procedure is created, but all executions will fail.</span></span>  
  
 <span data-ttu-id="ad2c1-110">Temas de esta sección:</span><span class="sxs-lookup"><span data-stu-id="ad2c1-110">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="ad2c1-111">Crear procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad2c1-111">Creating Natively Compiled Stored Procedures</span></span>](creating-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="ad2c1-112">Bloques atómicos</span><span class="sxs-lookup"><span data-stu-id="ad2c1-112">Atomic Blocks</span></span>](atomic-blocks-in-native-procedures.md)  
  
-   [<span data-ttu-id="ad2c1-113">Construcciones admitidas en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad2c1-113">Supported Constructs in Natively Compiled Stored Procedures</span></span>](supported-features-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="ad2c1-114">Utilizar Try..Catch en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad2c1-114">Using Try..Catch in Natively Compiled Stored Procedures</span></span>](../../database-engine/using-try-catch-in-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="ad2c1-115">Construcciones admitidas en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad2c1-115">Supported Constructs on Natively Compiled Stored Procedures</span></span>](supported-ddl-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="ad2c1-116">Procedimientos almacenados compilados de forma nativa y opciones SET de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ad2c1-116">Natively Compiled Stored Procedures and Execution Set Options</span></span>](natively-compiled-stored-procedures-and-execution-set-options.md)  
  
-   [<span data-ttu-id="ad2c1-117">Prácticas recomendadas para llamar a un procedimiento almacenado compilado de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad2c1-117">Best Practices for Calling Natively Compiled Stored Procedures</span></span>](best-practices-for-calling-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="ad2c1-118">Supervisar el rendimiento de los procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="ad2c1-118">Monitoring Performance of Natively Compiled Stored Procedures</span></span>](monitoring-performance-of-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="ad2c1-119">Llamar a procedimientos almacenados compilados de forma nativa desde aplicaciones de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="ad2c1-119">Calling Natively Compiled Stored Procedures from Data Access Applications</span></span>](calling-natively-compiled-stored-procedures-from-data-access-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad2c1-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad2c1-120">See Also</span></span>  
 [<span data-ttu-id="ad2c1-121">Tablas optimizadas para la memoria</span><span class="sxs-lookup"><span data-stu-id="ad2c1-121">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
