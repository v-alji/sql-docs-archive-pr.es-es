---
title: MSSQL_ENG014005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014005 error
ms.assetid: f168f0d6-cb11-45d4-9781-c374d7f388ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d820fd26cceee72b0d08204d6f6ce73a76508e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662830"
---
# <a name="mssql_eng014005"></a><span data-ttu-id="d1c3c-102">MSSQL_ENG014005</span><span class="sxs-lookup"><span data-stu-id="d1c3c-102">MSSQL_ENG014005</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d1c3c-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="d1c3c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1c3c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d1c3c-104">Product Name</span></span>|<span data-ttu-id="d1c3c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1c3c-105">SQL Server</span></span>|  
|<span data-ttu-id="d1c3c-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d1c3c-106">Event ID</span></span>|<span data-ttu-id="d1c3c-107">14005</span><span class="sxs-lookup"><span data-stu-id="d1c3c-107">14005</span></span>|  
|<span data-ttu-id="d1c3c-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d1c3c-108">Event Source</span></span>|<span data-ttu-id="d1c3c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d1c3c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d1c3c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d1c3c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d1c3c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d1c3c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d1c3c-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d1c3c-112">Message Text</span></span>|<span data-ttu-id="d1c3c-113">No se pudo quitar la publicación.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-113">Could not drop publication.</span></span> <span data-ttu-id="d1c3c-114">Hay una suscripción para ella.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-114">A subscription exists to it.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1c3c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d1c3c-115">Explanation</span></span>  
 <span data-ttu-id="d1c3c-116">Ha intentado quitar una publicación que tiene asociadas una o varias suscripciones.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-116">You have tried to drop a publication which has one or more associated subscriptions.</span></span> <span data-ttu-id="d1c3c-117">Una publicación se puede quitar únicamente si no hay suscripciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-117">A publication can only be dropped if there are no associated subscriptions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1c3c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d1c3c-118">User Action</span></span>  
 <span data-ttu-id="d1c3c-119">Quite las suscripciones antes de quitar la publicación.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-119">Drop the subscriptions before dropping the publication.</span></span> <span data-ttu-id="d1c3c-120">Si utiliza [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para quitar la publicación, se le ofrecerá la opción de quitar automáticamente todas las suscripciones asociadas antes de quitar la publicación.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-120">If you use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to drop the publication, it will give you the option to automatically drop all associated subscriptions before dropping the publication.</span></span> <span data-ttu-id="d1c3c-121">Si utiliza procedimientos almacenados, primero debe quitar explícitamente las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-121">If you use stored procedures, you must explicitly drop the subscriptions first.</span></span> <span data-ttu-id="d1c3c-122">Para obtener más información, consulte [Delete a Push Subscription](delete-a-push-subscription.md) y [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="d1c3c-122">For more information, see [Delete a Push Subscription](delete-a-push-subscription.md) and [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="d1c3c-123">Si parece no existir ninguna suscripción para la publicación o si ve este error cuando crea la publicación, es posible que tenga una suscripción anterior que no se limpiara completamente cuando se quitó.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-123">If no subscriptions appear to exist for the publication or if you see this error when you create a publication, you might have a previous subscription that was not completely cleaned up when it was removed.</span></span> <span data-ttu-id="d1c3c-124">Ejecute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) en la base de datos para eliminar todos los objetos y la configuración completa relacionados con la replicación.</span><span class="sxs-lookup"><span data-stu-id="d1c3c-124">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) on the database to remove all objects and settings related to replication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c3c-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1c3c-125">See Also</span></span>  
 [<span data-ttu-id="d1c3c-126">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="d1c3c-126">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
