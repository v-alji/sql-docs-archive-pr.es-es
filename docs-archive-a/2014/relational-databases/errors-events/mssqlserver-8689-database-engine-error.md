---
title: MSSQLSERVER_8689 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8689 (Database Engine error)
ms.assetid: 99467a32-6576-4272-a076-b16c06933f2a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdca0a3cd9ce47ccb39ebeaf8fd1cd260aafbd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745302"
---
# <a name="mssqlserver_8689"></a><span data-ttu-id="e16ef-102">MSSQLSERVER_8689</span><span class="sxs-lookup"><span data-stu-id="e16ef-102">MSSQLSERVER_8689</span></span>
    
## <a name="details"></a><span data-ttu-id="e16ef-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e16ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e16ef-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e16ef-104">Product Name</span></span>|<span data-ttu-id="e16ef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e16ef-105">SQL Server</span></span>|  
|<span data-ttu-id="e16ef-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e16ef-106">Event ID</span></span>|<span data-ttu-id="e16ef-107">8689</span><span class="sxs-lookup"><span data-stu-id="e16ef-107">8689</span></span>|  
|<span data-ttu-id="e16ef-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e16ef-108">Event Source</span></span>|<span data-ttu-id="e16ef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e16ef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e16ef-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e16ef-110">Component</span></span>|<span data-ttu-id="e16ef-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e16ef-111">SQLEngine</span></span>|  
|<span data-ttu-id="e16ef-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e16ef-112">Symbolic Name</span></span>|<span data-ttu-id="e16ef-113">USEPLAN_ERR_NO_DB</span><span class="sxs-lookup"><span data-stu-id="e16ef-113">USEPLAN_ERR_NO_DB</span></span>|  
|<span data-ttu-id="e16ef-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e16ef-114">Message Text</span></span>|<span data-ttu-id="e16ef-115">La base de datos '%.\*ls' especificada en la sugerencia USE PLAN no existe.</span><span class="sxs-lookup"><span data-stu-id="e16ef-115">Database '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="e16ef-116">Especifique una base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="e16ef-116">Specify an existing database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e16ef-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e16ef-117">Explanation</span></span>  
 <span data-ttu-id="e16ef-118">Una de las bases de datos que se especifican en la sugerencia USE PLAN no existe.</span><span class="sxs-lookup"><span data-stu-id="e16ef-118">A database that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e16ef-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e16ef-119">User Action</span></span>  
 <span data-ttu-id="e16ef-120">Asegúrese de que todas las bases de datos que se especifican en la sugerencia USE PLAN existen.</span><span class="sxs-lookup"><span data-stu-id="e16ef-120">Ensure all databases that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16ef-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e16ef-121">See Also</span></span>  
 <span data-ttu-id="e16ef-122">[Sugerencias de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="e16ef-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="e16ef-123">Guías de plan</span><span class="sxs-lookup"><span data-stu-id="e16ef-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
