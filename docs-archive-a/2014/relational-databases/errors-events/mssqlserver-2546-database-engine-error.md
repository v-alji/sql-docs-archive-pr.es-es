---
title: MSSQLSERVER_2546 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2546 (Database Engine error)
ms.assetid: c8f0e1b4-c7c4-45f2-9221-746714172313
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c1c5f64ca0daba413f2b71c05f5b8e57b2d55df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744714"
---
# <a name="mssqlserver_2546"></a><span data-ttu-id="af984-102">MSSQLSERVER_2546</span><span class="sxs-lookup"><span data-stu-id="af984-102">MSSQLSERVER_2546</span></span>
    
## <a name="details"></a><span data-ttu-id="af984-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="af984-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af984-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="af984-104">Product Name</span></span>|<span data-ttu-id="af984-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="af984-105">SQL Server</span></span>|  
|<span data-ttu-id="af984-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="af984-106">Event ID</span></span>|<span data-ttu-id="af984-107">2546</span><span class="sxs-lookup"><span data-stu-id="af984-107">2546</span></span>|  
|<span data-ttu-id="af984-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="af984-108">Event Source</span></span>|<span data-ttu-id="af984-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="af984-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="af984-110">Componente</span><span class="sxs-lookup"><span data-stu-id="af984-110">Component</span></span>|<span data-ttu-id="af984-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="af984-111">SQLEngine</span></span>|  
|<span data-ttu-id="af984-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="af984-112">Symbolic Name</span></span>|<span data-ttu-id="af984-113">DBCC_INDEX_MARKED_DISABLED</span><span class="sxs-lookup"><span data-stu-id="af984-113">DBCC_INDEX_MARKED_DISABLED</span></span>|  
|<span data-ttu-id="af984-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="af984-114">Message Text</span></span>|<span data-ttu-id="af984-115">El índice 'INDEX_NAME' de la tabla 'OBJECT_NAME' está marcado como deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="af984-115">Index 'INDEX_NAME' on table 'OBJECT_NAME' is marked as disabled.</span></span> <span data-ttu-id="af984-116">Genere de nuevo el índice para ponerlo en línea.</span><span class="sxs-lookup"><span data-stu-id="af984-116">Rebuild the index to bring it online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="af984-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="af984-117">Explanation</span></span>  
 <span data-ttu-id="af984-118">El índice especificado está marcado como sin conexión o está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="af984-118">The specified index is marked as offline or is disabled.</span></span> <span data-ttu-id="af984-119">Por tanto, este índice no se puede comprobar.</span><span class="sxs-lookup"><span data-stu-id="af984-119">Therefore, this index cannot be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af984-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="af984-120">User Action</span></span>  
 <span data-ttu-id="af984-121">Vuelva a generar el índice usando ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="af984-121">Rebuild the index by using ALTER INDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af984-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af984-122">See Also</span></span>  
 <span data-ttu-id="af984-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af984-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="af984-124">Reorganizar y volver a generar índices</span><span class="sxs-lookup"><span data-stu-id="af984-124">Reorganize and Rebuild Indexes</span></span>](../indexes/indexes.md)  
  
  
