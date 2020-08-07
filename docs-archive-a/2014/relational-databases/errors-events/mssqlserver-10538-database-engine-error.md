---
title: MSSQLSERVER_10538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: edc6abf192a3341f9b84c99e99071343cc882c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745802"
---
# <a name="mssqlserver_10538"></a><span data-ttu-id="a43e8-102">MSSQLSERVER_10538</span><span class="sxs-lookup"><span data-stu-id="a43e8-102">MSSQLSERVER_10538</span></span>
    
## <a name="details"></a><span data-ttu-id="a43e8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a43e8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a43e8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a43e8-104">Product Name</span></span>|<span data-ttu-id="a43e8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a43e8-105">SQL Server</span></span>|  
|<span data-ttu-id="a43e8-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a43e8-106">Event ID</span></span>|<span data-ttu-id="a43e8-107">10538</span><span class="sxs-lookup"><span data-stu-id="a43e8-107">10538</span></span>|  
|<span data-ttu-id="a43e8-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a43e8-108">Event Source</span></span>|<span data-ttu-id="a43e8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a43e8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a43e8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a43e8-110">Component</span></span>|<span data-ttu-id="a43e8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a43e8-111">SQLEngine</span></span>|  
|<span data-ttu-id="a43e8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a43e8-112">Symbolic Name</span></span>|<span data-ttu-id="a43e8-113">PG_INVALID_PLANGUIDE_HANDLE</span><span class="sxs-lookup"><span data-stu-id="a43e8-113">PG_INVALID_PLANGUIDE_HANDLE</span></span>|  
|<span data-ttu-id="a43e8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a43e8-114">Message Text</span></span>|<span data-ttu-id="a43e8-115">No se encuentra la guía de plan porque el Id. de guía de plan especificado es NULL o no es válido, o porque no tiene permiso para el objeto al que hace referencia la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="a43e8-115">Cannot find the plan guide either because the specified plan guide ID is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span> <span data-ttu-id="a43e8-116">Compruebe que el id. de guía de plan es válido, la sesión actual está establecida en el contexto de base de datos correcto y que tiene permiso ALTER para el objeto al que hace referencia la guía de plan o el permiso ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="a43e8-116">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have either ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a43e8-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="a43e8-117">Explanation</span></span>  
 <span data-ttu-id="a43e8-118">El identificador de la guía de plan especificada es NULL o no es válido, o no se tiene permiso para el objeto al que hace referencia la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="a43e8-118">The ID of the specified plan guide is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a43e8-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a43e8-119">User Action</span></span>  
 <span data-ttu-id="a43e8-120">Compruebe que el identificador de guía de plan es válido, la sesión actual está establecida en el contexto de base de datos correcto y se tiene el permiso ALTER DATABASE o ALTER para el objeto al que hace referencia la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="a43e8-120">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43e8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a43e8-121">See Also</span></span>  
 <span data-ttu-id="a43e8-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a43e8-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="a43e8-123">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="a43e8-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="a43e8-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a43e8-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
