---
title: Descripción de las transacciones en tablas optimizadas para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0671bba8b7a0bda27ea27cf059cb9e3b1bb87b2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746403"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a><span data-ttu-id="2c652-102">Descripción de las transacciones en tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="2c652-102">Understanding Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="2c652-103">Las transacciones tienen acceso a las tablas optimizadas para memoria mediante control de simultaneidad optimista multiversión.</span><span class="sxs-lookup"><span data-stu-id="2c652-103">Transactions access memory-optimized tables using a form of optimistic, multi-version concurrency control.</span></span> <span data-ttu-id="2c652-104">Esto significa que hay versiones diferentes de los datos.</span><span class="sxs-lookup"><span data-stu-id="2c652-104">This means that there are different versions of the data.</span></span> <span data-ttu-id="2c652-105">Cada transacción opera en su propia versión coherente de forma transaccional de la base de datos, de forma independiente de otras transacciones que se ejecutan simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="2c652-105">Each transaction operates on its own transactionally consistent version of the database, independent from other concurrently running transactions.</span></span> <span data-ttu-id="2c652-106">Además, las transacciones operan con la suposición optimista de que no habrá ningún conflicto con otras transacciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="2c652-106">In addition, transactions operate under the optimistic assumption that there will be no conflicts with other, concurrent, transactions.</span></span> <span data-ttu-id="2c652-107">Esto evita la necesidad de utilizar bloqueos, pero requiere que el sistema detecte los conflictos y termine una de las transacciones en conflicto.</span><span class="sxs-lookup"><span data-stu-id="2c652-107">This avoids the need to use locks, but does require the system to detect conflicts and terminate one of the conflicting transactions.</span></span> <span data-ttu-id="2c652-108">Los conflictos pueden aparecer solo para las transacciones de escritura contra escritura y para las transacciones de lectura contra escritura.</span><span class="sxs-lookup"><span data-stu-id="2c652-108">Conflicts can occur only for write-write transactions and for read-write transactions.</span></span> <span data-ttu-id="2c652-109">Si hay un conflicto de escritura contra escritura, finaliza una transacción de escritura.</span><span class="sxs-lookup"><span data-stu-id="2c652-109">If there is a write-write conflict, one write transaction is terminated.</span></span>  
  
 <span data-ttu-id="2c652-110">Hay similitudes entre el control de simultaneidad de las tablas optimizadas para memoria y el control de simultaneidad en las tablas basadas en disco para los niveles de aislamiento de transacción READ_COMMITTED_SNAPSHOT y SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="2c652-110">There are similarities between the concurrency control for memory-optimized tables and the concurrency control for disk-based tables for the READ_COMMITTED_SNAPSHOT and SNAPSHOT transaction isolation levels.</span></span> <span data-ttu-id="2c652-111">(Para obtener más información acerca de las tablas basadas en disco, vea [niveles de aislamiento basados en versiones de fila en el motor de base de datos](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx)).</span><span class="sxs-lookup"><span data-stu-id="2c652-111">(For more information about disk-based tables, see [Row Versioning-based Isolation Levels in the Database Engine](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span></span>  
  
## <a name="topics-in-this-section"></a><span data-ttu-id="2c652-112">Temas de esta sección</span><span class="sxs-lookup"><span data-stu-id="2c652-112">Topics in This Section</span></span>  
 <span data-ttu-id="2c652-113">Esta sección sobre las transacciones en tablas optimizadas para memoria incluye los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c652-113">This section on transactions in memory-optimized tables includes the following topics:</span></span>  
  
-   [<span data-ttu-id="2c652-114">Instrucciones para los niveles de aislamiento de transacciones con tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="2c652-114">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [<span data-ttu-id="2c652-115">Instrucciones para la lógica de reintento de transacciones en tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="2c652-115">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="2c652-116">Transacciones en tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="2c652-116">Transactions in Memory-Optimized Tables</span></span>](transactions-in-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="2c652-117">Niveles de aislamiento de transacción</span><span class="sxs-lookup"><span data-stu-id="2c652-117">Transaction Isolation Levels</span></span>](transaction-isolation-levels.md)  
  
-   [<span data-ttu-id="2c652-118">Transacciones entre contenedores</span><span class="sxs-lookup"><span data-stu-id="2c652-118">Cross-Container Transactions</span></span>](cross-container-transactions.md)  
  
 <span data-ttu-id="2c652-119">Para saber más, vea [Control de la durabilidad de las transacciones](../relational-databases/logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="2c652-119">For more information, see [Control Transaction Durability](../relational-databases/logs/control-transaction-durability.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c652-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c652-120">See Also</span></span>  
 [<span data-ttu-id="2c652-121">Tablas optimizadas para la memoria</span><span class="sxs-lookup"><span data-stu-id="2c652-121">Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
