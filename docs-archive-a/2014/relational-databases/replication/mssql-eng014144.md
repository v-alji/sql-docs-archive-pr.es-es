---
title: MSSQL_ENG014144 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d93f06a585bcc01c52438ff7b99bbd635532402
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661934"
---
# <a name="mssql_eng014144"></a><span data-ttu-id="5e3e1-102">MSSQL_ENG014144</span><span class="sxs-lookup"><span data-stu-id="5e3e1-102">MSSQL_ENG014144</span></span>
    
## <a name="message-details"></a><span data-ttu-id="5e3e1-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="5e3e1-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e3e1-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5e3e1-104">Product Name</span></span>|<span data-ttu-id="5e3e1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e3e1-105">SQL Server</span></span>|  
|<span data-ttu-id="5e3e1-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5e3e1-106">Event ID</span></span>|<span data-ttu-id="5e3e1-107">14144</span><span class="sxs-lookup"><span data-stu-id="5e3e1-107">14144</span></span>|  
|<span data-ttu-id="5e3e1-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5e3e1-108">Event Source</span></span>|<span data-ttu-id="5e3e1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5e3e1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5e3e1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5e3e1-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="5e3e1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5e3e1-111">Symbolic Name</span></span>||  
|<span data-ttu-id="5e3e1-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5e3e1-112">Message Text</span></span>|<span data-ttu-id="5e3e1-113">No se puede quitar el suscriptor '%s'.</span><span class="sxs-lookup"><span data-stu-id="5e3e1-113">Cannot drop Subscriber '%s'.</span></span> <span data-ttu-id="5e3e1-114">Mantiene suscripciones en la base de datos de publicación '%2!'.</span><span class="sxs-lookup"><span data-stu-id="5e3e1-114">There are subscriptions for it in the publication database '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5e3e1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="5e3e1-115">Explanation</span></span>  
 <span data-ttu-id="5e3e1-116">Una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ha sido configurada como suscriptor no puede quitarse del rol de suscriptor mientras haya suscripciones activas configuradas para la instancia.</span><span class="sxs-lookup"><span data-stu-id="5e3e1-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Subscriber cannot be removed from the role of Subscriber while there are active subscriptions configured for the instance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e3e1-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5e3e1-117">User Action</span></span>  
 <span data-ttu-id="5e3e1-118">Quite todas las suscripciones asociadas antes de intentar cambiar el estado del suscriptor de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="5e3e1-118">Drop all associated subscriptions before attempting to change the Subscriber status of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance:</span></span>  
  
1.  <span data-ttu-id="5e3e1-119">Para buscar suscripciones, ejecute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) en la base de datos de publicación del publicador.</span><span class="sxs-lookup"><span data-stu-id="5e3e1-119">Execute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) in the publication database at the Publisher to find subscriptions.</span></span>  
  
2.  <span data-ttu-id="5e3e1-120">Para quitar suscripciones, ejecute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) en la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="5e3e1-120">Execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) in the publication database to drop subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3e1-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e3e1-121">See Also</span></span>  
 <span data-ttu-id="5e3e1-122">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="5e3e1-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="5e3e1-123">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="5e3e1-123">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
