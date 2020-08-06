---
title: MSSQL_ENG014157 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0682d740d82c995d64427f56aabce24b8a48ca65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671491"
---
# <a name="mssql_eng014157"></a><span data-ttu-id="008cc-102">MSSQL_ENG014157</span><span class="sxs-lookup"><span data-stu-id="008cc-102">MSSQL_ENG014157</span></span>
    
## <a name="message-details"></a><span data-ttu-id="008cc-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="008cc-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="008cc-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="008cc-104">Product Name</span></span>|<span data-ttu-id="008cc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="008cc-105">SQL Server</span></span>|  
|<span data-ttu-id="008cc-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="008cc-106">Event ID</span></span>|<span data-ttu-id="008cc-107">14157</span><span class="sxs-lookup"><span data-stu-id="008cc-107">14157</span></span>|  
|<span data-ttu-id="008cc-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="008cc-108">Event Source</span></span>|<span data-ttu-id="008cc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="008cc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="008cc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="008cc-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="008cc-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="008cc-111">Symbolic Name</span></span>||  
|<span data-ttu-id="008cc-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="008cc-112">Message Text</span></span>|<span data-ttu-id="008cc-113">La suscripción creada por el suscriptor '%1!s!' a la publicación '%2!s!' expiró y ha sido eliminada.</span><span class="sxs-lookup"><span data-stu-id="008cc-113">The subscription created by Subscriber '%s' to publication '%s' has expired and has been dropped.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="008cc-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="008cc-114">Explanation</span></span>  
 <span data-ttu-id="008cc-115">Un suscriptor debe sincronizarse con el publicador en el tiempo especificado en el período de conservación de la publicación.</span><span class="sxs-lookup"><span data-stu-id="008cc-115">A Subscriber must synchronize with the Publisher within the time specified in the publication retention period.</span></span> <span data-ttu-id="008cc-116">Si un suscriptor no se sincroniza en este período, la suscripción expira.</span><span class="sxs-lookup"><span data-stu-id="008cc-116">If a Subscriber does not synchronize within this period, the subscription expires.</span></span> <span data-ttu-id="008cc-117">Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="008cc-117">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="008cc-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="008cc-118">User Action</span></span>  
 <span data-ttu-id="008cc-119">La suscripción se debe volver a crear e inicializar para que el suscriptor pueda empezar a recibir cambios de datos de nuevo:</span><span class="sxs-lookup"><span data-stu-id="008cc-119">The subscription must be re-created and initialized before the Subscriber can begin receiving data changes again:</span></span>  
  
-   <span data-ttu-id="008cc-120">Para obtener información sobre la creación de suscripciones, vea [Suscribirse a publicaciones](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="008cc-120">For information about creating subscriptions, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
-   <span data-ttu-id="008cc-121">Para obtener información sobre la inicialización de suscripciones, vea [Initialize a Subscription](initialize-a-subscription.md) (Inicializar una suscripción).</span><span class="sxs-lookup"><span data-stu-id="008cc-121">For information about initializing subscriptions, see [Initialize a Subscription](initialize-a-subscription.md).</span></span>  
  
 <span data-ttu-id="008cc-122">Si la base de datos de suscripciones contiene varios cambios que no se han sincronizado con el publicador, puede usar la [tablediff Utility](../../tools/tablediff-utility.md) para determinar qué filas de las bases de datos de publicaciones y suscripciones son diferentes.</span><span class="sxs-lookup"><span data-stu-id="008cc-122">If the subscription database contains changes that have not been synchronized with the Publisher, you can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span>  
  
 <span data-ttu-id="008cc-123">Puede aumentar el período de conservación de la publicación para evitar tener suscripciones expiradas.</span><span class="sxs-lookup"><span data-stu-id="008cc-123">You can increase the publication retention period to avoid having subscriptions expire.</span></span> <span data-ttu-id="008cc-124">Tenga cuidado al establecer un valor alto porque puede provocar que se almacenen más datos y metadatos, lo que afectaría al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="008cc-124">Use caution in setting a high value, because this can result in more data and metadata being stored, which affects performance.</span></span> <span data-ttu-id="008cc-125">Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="008cc-125">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="008cc-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="008cc-126">See Also</span></span>  
 [<span data-ttu-id="008cc-127">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="008cc-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
