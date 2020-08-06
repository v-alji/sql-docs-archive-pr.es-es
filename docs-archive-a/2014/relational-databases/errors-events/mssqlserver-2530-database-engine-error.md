---
title: MSSQLSERVER_2530 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 5d4be07a-38a5-4b25-819c-4dcb4636cc15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 30b57aae907d6f0acc4d1c0e6021bf936621c69e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662994"
---
# <a name="mssqlserver_2530"></a><span data-ttu-id="19725-102">MSSQLSERVER_2530</span><span class="sxs-lookup"><span data-stu-id="19725-102">MSSQLSERVER_2530</span></span>
    
## <a name="details"></a><span data-ttu-id="19725-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="19725-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19725-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="19725-104">Product Name</span></span>|<span data-ttu-id="19725-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="19725-105">SQL Server</span></span>|  
|<span data-ttu-id="19725-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="19725-106">Event ID</span></span>|<span data-ttu-id="19725-107">2530</span><span class="sxs-lookup"><span data-stu-id="19725-107">2530</span></span>|  
|<span data-ttu-id="19725-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="19725-108">Event Source</span></span>|<span data-ttu-id="19725-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="19725-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="19725-110">Componente</span><span class="sxs-lookup"><span data-stu-id="19725-110">Component</span></span>|<span data-ttu-id="19725-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="19725-111">SQLEngine</span></span>|  
|<span data-ttu-id="19725-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="19725-112">Symbolic Name</span></span>|<span data-ttu-id="19725-113">DBCC_INDEX_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="19725-113">DBCC_INDEX_IS_OFFLINE</span></span>|  
|<span data-ttu-id="19725-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="19725-114">Message Text</span></span>|<span data-ttu-id="19725-115">El índice "%.\*ls"" de la tabla "%.\*ls" está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="19725-115">The index "%.\*ls" on table "%.\*ls" is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19725-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="19725-116">Explanation</span></span>  
 <span data-ttu-id="19725-117">La instrucción DBCC no puede continuar porque el índice especificado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="19725-117">The DBCC statement cannot proceed because the specified index is disabled.</span></span> <span data-ttu-id="19725-118">Cuando se deshabilita un índice, sigue deshabilitado hasta que se vuelve a generar o se quita y se vuelve a crear.</span><span class="sxs-lookup"><span data-stu-id="19725-118">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped and re-created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19725-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="19725-119">User Action</span></span>  
  
1.  <span data-ttu-id="19725-120">Habilite el índice deshabilitado utilizando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="19725-120">Enable the disabled index by using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="19725-121">Instrucción ALTER INDEX con la cláusula REBUILD</span><span class="sxs-lookup"><span data-stu-id="19725-121">ALTER INDEX statement with the REBUILD clause</span></span>  
  
    -   <span data-ttu-id="19725-122">CREATE INDEX con la cláusula DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="19725-122">CREATE INDEX with the DROP_EXISTING clause</span></span>  
  
    -   <span data-ttu-id="19725-123">DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="19725-123">DBCC DBREINDEX</span></span>  
  
2.  <span data-ttu-id="19725-124">Ejecute de nuevo la instrucción DBCC.</span><span class="sxs-lookup"><span data-stu-id="19725-124">Rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19725-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19725-125">See Also</span></span>  
 <span data-ttu-id="19725-126">[Habilitar índices y restricciones](../indexes/enable-indexes-and-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="19725-126">[Enable Indexes and Constraints](../indexes/enable-indexes-and-constraints.md) </span></span>  
 <span data-ttu-id="19725-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="19725-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="19725-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="19725-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="19725-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="19725-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql)  
  
  
