---
title: MSSQL_ENG003724 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003724 error
ms.assetid: 10cb119d-92df-4124-b85d-cd2f2666c99c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dbfb68575c5ffa73276b3bbe1643381c3f0cc412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750697"
---
# <a name="mssql_eng003724"></a><span data-ttu-id="2438b-102">MSSQL_ENG003724</span><span class="sxs-lookup"><span data-stu-id="2438b-102">MSSQL_ENG003724</span></span>
    
## <a name="message-details"></a><span data-ttu-id="2438b-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="2438b-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2438b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="2438b-104">Product Name</span></span>|<span data-ttu-id="2438b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2438b-105">SQL Server</span></span>|  
|<span data-ttu-id="2438b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2438b-106">Event ID</span></span>|<span data-ttu-id="2438b-107">3724</span><span class="sxs-lookup"><span data-stu-id="2438b-107">3724</span></span>|  
|<span data-ttu-id="2438b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="2438b-108">Event Source</span></span>|<span data-ttu-id="2438b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2438b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2438b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2438b-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="2438b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2438b-111">Symbolic Name</span></span>||  
|<span data-ttu-id="2438b-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2438b-112">Message Text</span></span>|<span data-ttu-id="2438b-113">No se puede %1! %2! '%3!' porque se está utilizando para la replicación.</span><span class="sxs-lookup"><span data-stu-id="2438b-113">Cannot %S_MSG the %S_MSG '%.\*ls' because it is being used for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2438b-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="2438b-114">Explanation</span></span>  
 <span data-ttu-id="2438b-115">Cuando se replican objetos en una base de datos, se marcan como replicados en la tabla del sistema **sysarticles** (en publicaciones de instantáneas y transaccionales) o **sysmergearticles** (en publicaciones de combinación).</span><span class="sxs-lookup"><span data-stu-id="2438b-115">When objects in a database are replicated, they are marked as replicated in the system table **sysarticles** (for snapshot and transactional publications) or **sysmergearticles** (for merge publications).</span></span> <span data-ttu-id="2438b-116">Si intenta quitar un objeto replicado, se produce este error.</span><span class="sxs-lookup"><span data-stu-id="2438b-116">If you attempt drop a replicated object, this error is raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2438b-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2438b-117">User Action</span></span>  
 <span data-ttu-id="2438b-118">Asegúrese de que el objeto de la base de datos no está replicado antes de intentar quitarlo.</span><span class="sxs-lookup"><span data-stu-id="2438b-118">Ensure the database object is not replicated before attempting to drop it.</span></span> <span data-ttu-id="2438b-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2438b-119">For example:</span></span>  
  
-   <span data-ttu-id="2438b-120">Si el error se produce en la base de datos de publicaciones, quite el artículo de la publicación antes de quitar el objeto.</span><span class="sxs-lookup"><span data-stu-id="2438b-120">If the error occurs in the publication database, drop the article from the publication before dropping the object.</span></span> <span data-ttu-id="2438b-121">Para más información, vea [Agregar y quitar artículos de publicaciones existentes](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="2438b-121">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
-   <span data-ttu-id="2438b-122">Si el error se produce en la base de datos de suscripciones, quite la suscripción antes de quitar el objeto.</span><span class="sxs-lookup"><span data-stu-id="2438b-122">If the error occurs in the subscription database, drop the subscription before dropping the object.</span></span> <span data-ttu-id="2438b-123">Para obtener más información, vea [Suscribirse a publicaciones](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="2438b-123">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="2438b-124">En suscripciones de publicaciones transaccionales, es posible quitar la suscripción de un artículo individual en vez de toda la publicación.</span><span class="sxs-lookup"><span data-stu-id="2438b-124">For subscriptions to transactional publications, it is possible to drop the subscription to an individual article rather than the entire publication.</span></span> <span data-ttu-id="2438b-125">Para obtener más información, vea [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2438b-125">For more information, see [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span>  
  
 <span data-ttu-id="2438b-126">Si se produce este error en una base de datos que no está replicada, ejecute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para asegurarse de que los objetos de la base de datos no están marcados como replicados.</span><span class="sxs-lookup"><span data-stu-id="2438b-126">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2438b-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2438b-127">See Also</span></span>  
 [<span data-ttu-id="2438b-128">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="2438b-128">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
