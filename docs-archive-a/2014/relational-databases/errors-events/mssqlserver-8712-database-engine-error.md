---
title: MSSQLSERVER_8712 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8712 (Database Engine error)
ms.assetid: 292fb3bc-062e-41e4-a566-b5d3d0b21977
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9285d4846cac5af2dd6e87ab55d5fd0610586d07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678198"
---
# <a name="mssqlserver_8712"></a><span data-ttu-id="7fdd6-102">MSSQLSERVER_8712</span><span class="sxs-lookup"><span data-stu-id="7fdd6-102">MSSQLSERVER_8712</span></span>
    
## <a name="details"></a><span data-ttu-id="7fdd6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7fdd6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7fdd6-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7fdd6-104">Product Name</span></span>|<span data-ttu-id="7fdd6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fdd6-105">SQL Server</span></span>|  
|<span data-ttu-id="7fdd6-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7fdd6-106">Event ID</span></span>|<span data-ttu-id="7fdd6-107">8712</span><span class="sxs-lookup"><span data-stu-id="7fdd6-107">8712</span></span>|  
|<span data-ttu-id="7fdd6-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7fdd6-108">Event Source</span></span>|<span data-ttu-id="7fdd6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7fdd6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7fdd6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7fdd6-110">Component</span></span>|<span data-ttu-id="7fdd6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7fdd6-111">SQLEngine</span></span>|  
|<span data-ttu-id="7fdd6-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7fdd6-112">Symbolic Name</span></span>|<span data-ttu-id="7fdd6-113">USEPLAN_ERR_NO_INDEX</span><span class="sxs-lookup"><span data-stu-id="7fdd6-113">USEPLAN_ERR_NO_INDEX</span></span>|  
|<span data-ttu-id="7fdd6-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7fdd6-114">Message Text</span></span>|<span data-ttu-id="7fdd6-115">El índice '%.\*ls', especificado en la sugerencia USE PLAN, no existe.</span><span class="sxs-lookup"><span data-stu-id="7fdd6-115">Index '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="7fdd6-116">Especifique un índice existente o cree un índice con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7fdd6-116">Specify an existing index, or create an index with the specified name.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7fdd6-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="7fdd6-117">Explanation</span></span>  
 <span data-ttu-id="7fdd6-118">Uno de los índices que se especifican en la sugerencia USE PLAN no existe.</span><span class="sxs-lookup"><span data-stu-id="7fdd6-118">An index that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7fdd6-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7fdd6-119">User Action</span></span>  
 <span data-ttu-id="7fdd6-120">Asegurarse de que todos los índices que se especifican en la sugerencia USE PLAN existen.</span><span class="sxs-lookup"><span data-stu-id="7fdd6-120">Ensure all indexes that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fdd6-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fdd6-121">See Also</span></span>  
 <span data-ttu-id="7fdd6-122">[Sugerencias de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="7fdd6-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="7fdd6-123">Guías de plan</span><span class="sxs-lookup"><span data-stu-id="7fdd6-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
