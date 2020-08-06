---
title: MSSQLSERVER_601 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "601"
helpviewer_keywords:
- 601 (Database Engine error)
ms.assetid: 2039cc0a-9a43-4369-a04a-935e384388b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 459a983d72a91e628e8cc33636d3abd81998f1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677148"
---
# <a name="mssqlserver_601"></a><span data-ttu-id="86ade-102">MSSQLSERVER_601</span><span class="sxs-lookup"><span data-stu-id="86ade-102">MSSQLSERVER_601</span></span>
    
## <a name="details"></a><span data-ttu-id="86ade-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="86ade-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86ade-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="86ade-104">Product Name</span></span>|<span data-ttu-id="86ade-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="86ade-105">SQL Server</span></span>|  
|<span data-ttu-id="86ade-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="86ade-106">Event ID</span></span>|<span data-ttu-id="86ade-107">601</span><span class="sxs-lookup"><span data-stu-id="86ade-107">601</span></span>|  
|<span data-ttu-id="86ade-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="86ade-108">Event Source</span></span>|<span data-ttu-id="86ade-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="86ade-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="86ade-110">Componente</span><span class="sxs-lookup"><span data-stu-id="86ade-110">Component</span></span>|<span data-ttu-id="86ade-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="86ade-111">SQLEngine</span></span>|  
|<span data-ttu-id="86ade-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="86ade-112">Symbolic Name</span></span>||  
|<span data-ttu-id="86ade-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="86ade-113">Message Text</span></span>|<span data-ttu-id="86ade-114">No se pudo continuar el examen con NOLOCK debido al movimiento de los datos.</span><span class="sxs-lookup"><span data-stu-id="86ade-114">Could not continue scan with NOLOCK due to data movement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="86ade-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="86ade-115">Explanation</span></span>  
 <span data-ttu-id="86ade-116">El [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] no puede continuar la ejecución de la consulta porque está intentando leer datos actualizados o eliminados por otra transacción.</span><span class="sxs-lookup"><span data-stu-id="86ade-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot continue executing the query because it is trying to read data that was updated or deleted by another transaction.</span></span> <span data-ttu-id="86ade-117">La consulta está utilizando la sugerencia de bloqueo NOLOCK o el nivel de aislamiento de las transacciones READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="86ade-117">The query is using either the NOLOCK locking hint or the READ UNCOMMITTED transaction isolation level.</span></span>  
  
 <span data-ttu-id="86ade-118">Normalmente, se deniega el acceso a los datos modificados por otra transacción debido a los bloqueos colocados en los datos.</span><span class="sxs-lookup"><span data-stu-id="86ade-118">Typically, access to data that is being changed by another transaction is denied because of locks put on the data.</span></span> <span data-ttu-id="86ade-119">Sin embargo, la sugerencia de bloqueo NOLOCK y el nivel de aislamiento de las transacciones READ UNCOMMITTED permiten que una consulta lea los datos bloqueados por otra transacción.</span><span class="sxs-lookup"><span data-stu-id="86ade-119">However, the NOLOCK locking hint and READ UNCOMMITTED transaction isolation level let a query read data that is locked by another transaction.</span></span> <span data-ttu-id="86ade-120">Es lo que se conoce como lectura de datos sucios porque pueden leerse valores que aún no se han confirmado y que están sujetos a cambios.</span><span class="sxs-lookup"><span data-stu-id="86ade-120">This is referred to as a dirty read because you can read values that have not yet been committed and that are subject to change.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86ade-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="86ade-121">User Action</span></span>  
 <span data-ttu-id="86ade-122">Este error cancela la consulta.</span><span class="sxs-lookup"><span data-stu-id="86ade-122">This error cancels the query.</span></span> <span data-ttu-id="86ade-123">Vuelva a enviar la consulta o quite la sugerencia de bloqueo NOLOCK.</span><span class="sxs-lookup"><span data-stu-id="86ade-123">Either resubmit the query or remove the NOLOCK locking hint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ade-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86ade-124">See Also</span></span>  
 <span data-ttu-id="86ade-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="86ade-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span></span>  
 <span data-ttu-id="86ade-126">[Sugerencias de tabla &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="86ade-126">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 <span data-ttu-id="86ade-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="86ade-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="86ade-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="86ade-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)  
  
  
