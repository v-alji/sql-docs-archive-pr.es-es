---
title: MSSQLSERVER_10531 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10531 (Database Engine error)
ms.assetid: bb40e994-231c-44ce-933f-8d767fb2f450
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6230c046a9eb7b900377888c59a3a492f2b89f73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745810"
---
# <a name="mssqlserver_10531"></a><span data-ttu-id="6d951-102">MSSQLSERVER_10531</span><span class="sxs-lookup"><span data-stu-id="6d951-102">MSSQLSERVER_10531</span></span>
    
## <a name="details"></a><span data-ttu-id="6d951-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6d951-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d951-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="6d951-104">Product Name</span></span>|<span data-ttu-id="6d951-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d951-105">SQL Server</span></span>|  
|<span data-ttu-id="6d951-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="6d951-106">Event ID</span></span>|<span data-ttu-id="6d951-107">10531</span><span class="sxs-lookup"><span data-stu-id="6d951-107">10531</span></span>|  
|<span data-ttu-id="6d951-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="6d951-108">Event Source</span></span>|<span data-ttu-id="6d951-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6d951-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6d951-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6d951-110">Component</span></span>|<span data-ttu-id="6d951-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6d951-111">SQLEngine</span></span>|  
|<span data-ttu-id="6d951-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6d951-112">Symbolic Name</span></span>|<span data-ttu-id="6d951-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="6d951-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="6d951-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6d951-114">Message Text</span></span>|<span data-ttu-id="6d951-115">No se puede crear la guía de plan '%.\*ls' a partir de la memoria caché porque el usuario no tiene los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="6d951-115">Cannot create plan guide '%.\*ls' from cache because the user does not have adequate permissions.</span></span> <span data-ttu-id="6d951-116">Conceda el permiso VIEW SERVER STATE al usuario que va a crear la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="6d951-116">Grant the VIEW SERVER STATE permission to the user creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6d951-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="6d951-117">Explanation</span></span>  
 <span data-ttu-id="6d951-118">El usuario no tiene los permisos adecuados para crear la guía de plan especificada a partir de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="6d951-118">The user does not have adequate permissions to create the specified plan guide from the plan cache.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d951-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6d951-119">User Action</span></span>  
 <span data-ttu-id="6d951-120">Conceda el permiso VIEW SERVER STATE al usuario que va a crear la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="6d951-120">Grant VIEW SERVER STATE permission to the user creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d951-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d951-121">See Also</span></span>  
 <span data-ttu-id="6d951-122">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="6d951-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="6d951-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d951-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="6d951-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6d951-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
