---
title: MSSQLSERVER_10521 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10521 (Database Engine error)
ms.assetid: ba2d7e44-207c-4428-b5f0-c975ac122c0d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c034bd13e212b9b39bfd348353d59e23fc748079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745811"
---
# <a name="mssqlserver_10521"></a><span data-ttu-id="907b7-102">MSSQLSERVER_10521</span><span class="sxs-lookup"><span data-stu-id="907b7-102">MSSQLSERVER_10521</span></span>
    
## <a name="details"></a><span data-ttu-id="907b7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="907b7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="907b7-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="907b7-104">Product Name</span></span>|<span data-ttu-id="907b7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="907b7-105">SQL Server</span></span>|  
|<span data-ttu-id="907b7-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="907b7-106">Event ID</span></span>|<span data-ttu-id="907b7-107">10521</span><span class="sxs-lookup"><span data-stu-id="907b7-107">10521</span></span>|  
|<span data-ttu-id="907b7-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="907b7-108">Event Source</span></span>|<span data-ttu-id="907b7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="907b7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="907b7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="907b7-110">Component</span></span>|<span data-ttu-id="907b7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="907b7-111">SQLEngine</span></span>|  
|<span data-ttu-id="907b7-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="907b7-112">Symbolic Name</span></span>|<span data-ttu-id="907b7-113">PG_PARAM_NEEDED</span><span class="sxs-lookup"><span data-stu-id="907b7-113">PG_PARAM_NEEDED</span></span>|  
|<span data-ttu-id="907b7-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="907b7-114">Message Text</span></span>|<span data-ttu-id="907b7-115">No se puede crear la guía de plan '%.\*ls' porque se especificó `@type` como '%ls' y el valor del parámetro '%ls' es NULL.</span><span class="sxs-lookup"><span data-stu-id="907b7-115">Cannot create plan guide '%.\*ls' because `@type` was specified as '%ls' and the parameter '%ls' is NULL.</span></span> <span data-ttu-id="907b7-116">Este tipo requiere un valor no NULL para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="907b7-116">This type requires a non-NULL value for the parameter.</span></span> <span data-ttu-id="907b7-117">Especifique un valor no NULL para el parámetro o cambie el tipo por otro que admita un valor NULL para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="907b7-117">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="907b7-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="907b7-118">Explanation</span></span>  
 <span data-ttu-id="907b7-119">El tipo especificado en `@type` requiere un valor no NULL para el parámetro especificado; sin embargo, se proporcionó un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="907b7-119">The type specified in `@type` requires a non-NULL value for the specified parameter; however a NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="907b7-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="907b7-120">User Action</span></span>  
 <span data-ttu-id="907b7-121">Especifique un valor no NULL para el parámetro o cambie el tipo por otro que admita un valor NULL para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="907b7-121">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907b7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="907b7-122">See Also</span></span>  
 <span data-ttu-id="907b7-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="907b7-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="907b7-124">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="907b7-124">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="907b7-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="907b7-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
