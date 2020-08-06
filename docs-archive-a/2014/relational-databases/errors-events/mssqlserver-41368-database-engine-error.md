---
title: MSSQLSERVER_41368 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41368 (Database Engine error)
ms.assetid: abc71559-4c4d-4cce-a08f-3299dd167842
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 10e187223a3f35b4b21ede6965e3c9efea2e30c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745772"
---
# <a name="mssqlserver_41368"></a><span data-ttu-id="aec01-102">MSSQLSERVER_41368</span><span class="sxs-lookup"><span data-stu-id="aec01-102">MSSQLSERVER_41368</span></span>
    
## <a name="details"></a><span data-ttu-id="aec01-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="aec01-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aec01-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="aec01-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="aec01-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="aec01-105">Event ID</span></span>|<span data-ttu-id="aec01-106">41368</span><span class="sxs-lookup"><span data-stu-id="aec01-106">41368</span></span>|  
|<span data-ttu-id="aec01-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="aec01-107">Event Source</span></span>|<span data-ttu-id="aec01-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aec01-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aec01-109">Componente</span><span class="sxs-lookup"><span data-stu-id="aec01-109">Component</span></span>|<span data-ttu-id="aec01-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aec01-110">SQLEngine</span></span>|  
|<span data-ttu-id="aec01-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="aec01-111">Symbolic Name</span></span>|<span data-ttu-id="aec01-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="aec01-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="aec01-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="aec01-113">Message Text</span></span>|<span data-ttu-id="aec01-114">El acceso a las tablas optimizadas en memoria con el nivel de aislamiento READ COMMITTED se admite solo para las transacciones de confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="aec01-114">Accessing memory optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="aec01-115">No se admite para las transacciones explícitas o implícitas.</span><span class="sxs-lookup"><span data-stu-id="aec01-115">It is not supported for explicit or implicit transactions.</span></span> <span data-ttu-id="aec01-116">Proporciona un nivel de aislamiento admitido para la tabla optimizada en memoria mediante una sugerencia de tabla, como WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="aec01-116">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aec01-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="aec01-117">Explanation</span></span>  
 <span data-ttu-id="aec01-118">El acceso a tablas optimizadas para memoria con el nivel de aislamiento READ COMMITTED solo se admite para las transacciones de confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="aec01-118">Accessing memory-optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="aec01-119">Para obtener más información, consulte [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="aec01-119">For more information, see [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span></span>  
  
 <span data-ttu-id="aec01-120">Al obtener acceso a una tabla optimizada para memoria desde una transacción explícita iniciada con BEGIN TRANSACTION, o desde una transacción implícita, si IMPLICIT_TRANSACTIONS se establece en ON, no se admite el nivel de aislamiento READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="aec01-120">When accessing a memory-optimized table from an explicit transaction that was started with BEGIN TRANSACTION, or from an implicit transaction, if IMPLICIT_TRANSACTIONS is set to ON, the READ COMMITTED isolation level is not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aec01-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="aec01-121">User Action</span></span>  
 <span data-ttu-id="aec01-122">Utilice SNAPSHOT para tener acceso a una tabla optimizada para memoria desde una transacción READ COMMITTED explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="aec01-122">When accessing a memory-optimized table from an explicit or implicit READ COMMITTED transaction, use SNAPSHOT to access the table.</span></span> <span data-ttu-id="aec01-123">Esto puede lograrse mediante el uso de la sugerencia de tabla WITH (SNAPSHOT) (para obtener más información, vea [instrucciones para los niveles de aislamiento de transacción con tablas optimizadas para memoria](../in-memory-oltp/memory-optimized-tables.md)) o estableciendo la opción de base de datos MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT en ON (para obtener más información, vea [Opciones de ALTER DATABASE Set &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span><span class="sxs-lookup"><span data-stu-id="aec01-123">This can be achieved by using the table hint WITH (SNAPSHOT) (for more information, see [Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md)) or by setting the database option MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT to ON (for more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec01-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aec01-124">See Also</span></span>  
 [<span data-ttu-id="aec01-125">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="aec01-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
