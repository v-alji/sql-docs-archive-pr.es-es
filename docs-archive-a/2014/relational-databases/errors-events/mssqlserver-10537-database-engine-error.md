---
title: MSSQLSERVER_10537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10537 (Database Engine error)
ms.assetid: 728469a4-6523-4a37-925f-a950d75420fa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b1baccad5236bd8c1a71024b7dd542cc9d11cbd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747022"
---
# <a name="mssqlserver_10537"></a><span data-ttu-id="d7eb2-102">MSSQLSERVER_10537</span><span class="sxs-lookup"><span data-stu-id="d7eb2-102">MSSQLSERVER_10537</span></span>
    
## <a name="details"></a><span data-ttu-id="d7eb2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d7eb2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7eb2-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d7eb2-104">Product Name</span></span>|<span data-ttu-id="d7eb2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7eb2-105">SQL Server</span></span>|  
|<span data-ttu-id="d7eb2-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d7eb2-106">Event ID</span></span>|<span data-ttu-id="d7eb2-107">10537</span><span class="sxs-lookup"><span data-stu-id="d7eb2-107">10537</span></span>|  
|<span data-ttu-id="d7eb2-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d7eb2-108">Event Source</span></span>|<span data-ttu-id="d7eb2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d7eb2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d7eb2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d7eb2-110">Component</span></span>|<span data-ttu-id="d7eb2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d7eb2-111">SQLEngine</span></span>|  
|<span data-ttu-id="d7eb2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d7eb2-112">Symbolic Name</span></span>|<span data-ttu-id="d7eb2-113">PG_DUP_ENABLED</span><span class="sxs-lookup"><span data-stu-id="d7eb2-113">PG_DUP_ENABLED</span></span>|  
|<span data-ttu-id="d7eb2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d7eb2-114">Message Text</span></span>|<span data-ttu-id="d7eb2-115">No se puede habilitar la guía de plan '%.\*ls' porque la guía de plan habilitada '%.\*ls' contiene el mismo ámbito y el mismo valor de desplazamiento de inicio que la instrucción.</span><span class="sxs-lookup"><span data-stu-id="d7eb2-115">Cannot enable plan guide '%.\*ls' because the enabled plan guide '%.\*ls' contains the same scope and starting offset value as the statement.</span></span> <span data-ttu-id="d7eb2-116">Deshabilite la guía de plan existente antes de habilitar la especificada.</span><span class="sxs-lookup"><span data-stu-id="d7eb2-116">Disable the existing plan guide before enabling the specified plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d7eb2-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="d7eb2-117">Explanation</span></span>  
 <span data-ttu-id="d7eb2-118">Una guía de plan existente contiene el mismo ámbito y el mismo valor de desplazamiento de inicio que la instrucción de la guía de plan especificada.</span><span class="sxs-lookup"><span data-stu-id="d7eb2-118">An existing plan guide contains the same scope and starting offset value as the statement in the specified plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d7eb2-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d7eb2-119">User Action</span></span>  
 <span data-ttu-id="d7eb2-120">Deshabilite la guía de plan existente antes de habilitar la especificada.</span><span class="sxs-lookup"><span data-stu-id="d7eb2-120">Disable the existing plan guide before enabling the specified plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7eb2-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7eb2-121">See Also</span></span>  
 <span data-ttu-id="d7eb2-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d7eb2-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="d7eb2-123">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="d7eb2-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="d7eb2-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d7eb2-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
