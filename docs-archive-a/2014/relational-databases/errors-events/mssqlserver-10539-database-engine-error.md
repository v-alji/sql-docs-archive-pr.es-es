---
title: MSSQLSERVER_10539 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10539 (Database Engine error)
ms.assetid: 49c26ff7-18b8-4f07-a087-f45f63463b3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd1f190b8f5d3ab9755409bdd034fa374ea5314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745799"
---
# <a name="mssqlserver_10539"></a><span data-ttu-id="29c04-102">MSSQLSERVER_10539</span><span class="sxs-lookup"><span data-stu-id="29c04-102">MSSQLSERVER_10539</span></span>
    
## <a name="details"></a><span data-ttu-id="29c04-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="29c04-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29c04-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="29c04-104">Product Name</span></span>|<span data-ttu-id="29c04-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="29c04-105">SQL Server</span></span>|  
|<span data-ttu-id="29c04-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="29c04-106">Event ID</span></span>|<span data-ttu-id="29c04-107">10539</span><span class="sxs-lookup"><span data-stu-id="29c04-107">10539</span></span>|  
|<span data-ttu-id="29c04-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="29c04-108">Event Source</span></span>|<span data-ttu-id="29c04-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="29c04-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="29c04-110">Componente</span><span class="sxs-lookup"><span data-stu-id="29c04-110">Component</span></span>|<span data-ttu-id="29c04-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="29c04-111">SQLEngine</span></span>|  
|<span data-ttu-id="29c04-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="29c04-112">Symbolic Name</span></span>|<span data-ttu-id="29c04-113">PG_NO_PLAN_FOR_STMT</span><span class="sxs-lookup"><span data-stu-id="29c04-113">PG_NO_PLAN_FOR_STMT</span></span>|  
|<span data-ttu-id="29c04-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="29c04-114">Message Text</span></span>|<span data-ttu-id="29c04-115">No se puede crear la guía de plan '%.\*ls' a partir de la memoria caché porque no está disponible un plan de consulta para la instrucción con desplazamiento de inicio %d.</span><span class="sxs-lookup"><span data-stu-id="29c04-115">Cannot create plan guide '%.\*ls' from cache because a query plan is not available for the statement with start offset %d.</span></span> <span data-ttu-id="29c04-116">Este problema puede producirse si la instrucción depende de objetos de base de datos que aún no se han creado.</span><span class="sxs-lookup"><span data-stu-id="29c04-116">This problem can occur if the statement depends on database objects that have not yet been created.</span></span> <span data-ttu-id="29c04-117">Asegúrese de que todos los objetos de base de datos necesarios existen y ejecute la instrucción antes de crear la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="29c04-117">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="29c04-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="29c04-118">Explanation</span></span>  
 <span data-ttu-id="29c04-119">No se dispone de un plan de consulta en la memoria caché de plan para la instrucción con el desplazamiento de inicio especificado.</span><span class="sxs-lookup"><span data-stu-id="29c04-119">A query plan is not available in the plan cache for the statement with the specified starting offset.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29c04-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="29c04-120">User Action</span></span>  
 <span data-ttu-id="29c04-121">Asegúrese de que todos los objetos de base de datos necesarios existen y ejecute la instrucción antes de crear la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="29c04-121">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c04-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29c04-122">See Also</span></span>  
 [<span data-ttu-id="29c04-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29c04-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
