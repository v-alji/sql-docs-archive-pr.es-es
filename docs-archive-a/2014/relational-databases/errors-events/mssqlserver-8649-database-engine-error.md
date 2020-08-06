---
title: MSSQLSERVER_8649 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8649 (Database Engine error)
ms.assetid: 992dbc74-7c3a-498b-9f1b-b28387640677
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b39ed0d8ffe5f7f601b6cb1393596d0d6546e557
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674848"
---
# <a name="mssqlserver_8649"></a><span data-ttu-id="5469b-102">MSSQLSERVER_8649</span><span class="sxs-lookup"><span data-stu-id="5469b-102">MSSQLSERVER_8649</span></span>
    
## <a name="details"></a><span data-ttu-id="5469b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5469b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5469b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5469b-104">Product Name</span></span>|<span data-ttu-id="5469b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5469b-105">SQL Server</span></span>|  
|<span data-ttu-id="5469b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5469b-106">Event ID</span></span>|<span data-ttu-id="5469b-107">8649</span><span class="sxs-lookup"><span data-stu-id="5469b-107">8649</span></span>|  
|<span data-ttu-id="5469b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5469b-108">Event Source</span></span>|<span data-ttu-id="5469b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5469b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5469b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5469b-110">Component</span></span>|<span data-ttu-id="5469b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5469b-111">SQLEngine</span></span>|  
|<span data-ttu-id="5469b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5469b-112">Symbolic Name</span></span>|<span data-ttu-id="5469b-113">COST_TOO_HIGH</span><span class="sxs-lookup"><span data-stu-id="5469b-113">COST_TOO_HIGH</span></span>|  
|<span data-ttu-id="5469b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5469b-114">Message Text</span></span>|<span data-ttu-id="5469b-115">Se ha cancelado la consulta porque el costo estimado de esta consulta (%d) supera el umbral configurado de %d.</span><span class="sxs-lookup"><span data-stu-id="5469b-115">The query has been canceled because the estimated cost of this query (%d) exceeds the configured threshold of %d.</span></span> <span data-ttu-id="5469b-116">Póngase en contacto con el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="5469b-116">Contact the system administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5469b-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="5469b-117">Explanation</span></span>  
 <span data-ttu-id="5469b-118">La consulta se canceló porque el costo estimado de la misma supera el umbral configurado establecido para QUERY_GOVERNOR_COST_LIMIT.</span><span class="sxs-lookup"><span data-stu-id="5469b-118">The query was canceled because the estimated cost of this query exceeds the configured threshold set for the QUERY_GOVERNOR_COST_LIMIT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5469b-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5469b-119">User Action</span></span>  
 <span data-ttu-id="5469b-120">Establezca la opción QUERY_GOVERNOR_COST_LIMIT en un valor mayor.</span><span class="sxs-lookup"><span data-stu-id="5469b-120">Set the QUERY_GOVERNOR_COST_LIMIT option to a higher value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5469b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5469b-121">See Also</span></span>  
 [<span data-ttu-id="5469b-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5469b-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql)  
  
  
