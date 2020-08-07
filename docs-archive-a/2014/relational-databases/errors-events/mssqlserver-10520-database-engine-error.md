---
title: MSSQLSERVER_10520 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b8bdf080703fa6bd02fc34b8c31f59407814b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745813"
---
# <a name="mssqlserver_10520"></a><span data-ttu-id="0fde2-102">MSSQLSERVER_10520</span><span class="sxs-lookup"><span data-stu-id="0fde2-102">MSSQLSERVER_10520</span></span>
    
## <a name="details"></a><span data-ttu-id="0fde2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0fde2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fde2-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="0fde2-104">Product Name</span></span>|<span data-ttu-id="0fde2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fde2-105">SQL Server</span></span>|  
|<span data-ttu-id="0fde2-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="0fde2-106">Event ID</span></span>|<span data-ttu-id="0fde2-107">10520</span><span class="sxs-lookup"><span data-stu-id="0fde2-107">10520</span></span>|  
|<span data-ttu-id="0fde2-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="0fde2-108">Event Source</span></span>|<span data-ttu-id="0fde2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0fde2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0fde2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0fde2-110">Component</span></span>|<span data-ttu-id="0fde2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0fde2-111">SQLEngine</span></span>|  
|<span data-ttu-id="0fde2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0fde2-112">Symbolic Name</span></span>|<span data-ttu-id="0fde2-113">PG_PARAM_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="0fde2-113">PG_PARAM_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="0fde2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0fde2-114">Message Text</span></span>|<span data-ttu-id="0fde2-115">No se puede crear la guía de plan '%.\*ls' porque @type se especificó como '%ls' y se especificó un valor no NULL para el parámetro '%ls'.</span><span class="sxs-lookup"><span data-stu-id="0fde2-115">Cannot create plan guide '%.\*ls' because @type was specified as '%ls' and a non-NULL value is specified for the parameter '%ls'.</span></span> <span data-ttu-id="0fde2-116">Este tipo requiere un valor NULL para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="0fde2-116">This type requires a NULL value for the parameter.</span></span> <span data-ttu-id="0fde2-117">Especifique NULL para el parámetro o cambie el tipo por otro que admita un valor no NULL para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="0fde2-117">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0fde2-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="0fde2-118">Explanation</span></span>  
 <span data-ttu-id="0fde2-119">El tipo especificado en @type requiere un valor NULL para el parámetro especificado; sin embargo, se proporcionó un valor distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="0fde2-119">The type specified in @type requires a NULL value for the specified parameter, however a non-NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0fde2-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0fde2-120">User Action</span></span>  
 <span data-ttu-id="0fde2-121">Especifique NULL para el parámetro o cambie el tipo por otro que admita un valor no NULL para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="0fde2-121">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fde2-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fde2-122">See Also</span></span>  
 <span data-ttu-id="0fde2-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0fde2-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="0fde2-124">Guías de plan</span><span class="sxs-lookup"><span data-stu-id="0fde2-124">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
