---
title: Volver a publicar datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- republishing data
- publishing [SQL Server replication], Subscribers
- Subscribers [SQL Server replication], republishing data
ms.assetid: a1485cf4-b1c4-49e9-ab06-8ccfaad998f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f1e4213266121b3bf55bf2857e15f71f1e94e301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662782"
---
# <a name="republish-data"></a><span data-ttu-id="e60e5-102">Volver a publicar datos</span><span class="sxs-lookup"><span data-stu-id="e60e5-102">Republish Data</span></span>
  <span data-ttu-id="e60e5-103">En un modelo de republicación, el publicador envía datos a un suscriptor y éste, a su vez, vuelve a publicar los datos en cualquier número de suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e60e5-103">In a republishing model, the Publisher sends data to a Subscriber, which then republishes the data to any number of other Subscribers.</span></span> <span data-ttu-id="e60e5-104">Esto es útil cuando un publicador tiene que enviar datos a suscriptores a través de un vínculo de comunicaciones lento o costoso.</span><span class="sxs-lookup"><span data-stu-id="e60e5-104">This is useful when a Publisher must send data to Subscribers over a slow or expensive communications link.</span></span> <span data-ttu-id="e60e5-105">Si hay varios suscriptores en el otro extremo del vínculo, el uso de un republicador desplaza la mayor parte de la carga de distribución a ese extremo del vínculo.</span><span class="sxs-lookup"><span data-stu-id="e60e5-105">If there are a number of Subscribers on the far side of that link, using a republisher shifts the bulk of the distribution load to that side of the link.</span></span>  
  
 <span data-ttu-id="e60e5-106">Para republicar datos, lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e60e5-106">Republishing data involves the following steps:</span></span>  
  
1.  <span data-ttu-id="e60e5-107">Cree una publicación en el publicador.</span><span class="sxs-lookup"><span data-stu-id="e60e5-107">Create a publication at the Publisher.</span></span>  
  
2.  <span data-ttu-id="e60e5-108">Cree una suscripción a la publicación para el suscriptor de republicación.</span><span class="sxs-lookup"><span data-stu-id="e60e5-108">Create a subscription to the publication for the republishing Subscriber.</span></span>  
  
3.  <span data-ttu-id="e60e5-109">Inicialice la suscripción.</span><span class="sxs-lookup"><span data-stu-id="e60e5-109">Initialize the subscription.</span></span> <span data-ttu-id="e60e5-110">La suscripción se debe inicializar antes de crear la publicación en el suscriptor de republicación; de lo contrario, se producirá un error de replicación.</span><span class="sxs-lookup"><span data-stu-id="e60e5-110">The subscription must be initialized before the publication is created at the republishing Subscriber, or replication will fail.</span></span>  
  
4.  <span data-ttu-id="e60e5-111">Cree una publicación en la base de datos de suscripciones para el suscriptor de republicación.</span><span class="sxs-lookup"><span data-stu-id="e60e5-111">Create a publication in the subscription database at the republishing Subscriber.</span></span>  
  
5.  <span data-ttu-id="e60e5-112">Cree suscripciones a la publicación en el suscriptor de republicación para los demás suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e60e5-112">Create subscriptions to the publication at the republishing Subscriber for the other Subscribers.</span></span>  
  
6.  <span data-ttu-id="e60e5-113">Inicialice las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="e60e5-113">Initialize the subscriptions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e60e5-114">Si utiliza la replicación de mezcla en una topología de republicación, todos los suscriptores de republicación deberán utilizar las suscripciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="e60e5-114">If you use merge replication in a republishing topology, all republishing Subscribers must use server subscriptions.</span></span> <span data-ttu-id="e60e5-115">Para obtener más información sobre los tipos de suscripción, vea [Subscribe to Publications](subscribe-to-publications.md) (Suscribirse a publicaciones).</span><span class="sxs-lookup"><span data-stu-id="e60e5-115">For more information about subscription types, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
 <span data-ttu-id="e60e5-116">En la siguiente ilustración, tanto el publicador como el republicador actúan como sus propios distribuidores locales.</span><span class="sxs-lookup"><span data-stu-id="e60e5-116">In the following illustration, both the Publisher and the republisher are acting as their own local Distributors.</span></span> <span data-ttu-id="e60e5-117">Si estuvieran configurados para utilizar un distribuidor remoto, cada distribuidor tendría que estar en el mismo lado del vínculo de comunicaciones lento o costoso que su publicador.</span><span class="sxs-lookup"><span data-stu-id="e60e5-117">If each were set up to use a remote Distributor, each Distributor would need to be on the same side of the slow or expensive communications link as its Publisher.</span></span> <span data-ttu-id="e60e5-118">Los publicadores tienen que estar conectados con sus distribuidores remotos mediante vínculos de comunicaciones confiables y de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="e60e5-118">Publishers must be connected to remote Distributors by reliable, high-speed communications links.</span></span>  
  
 <span data-ttu-id="e60e5-119">![Volver a publicar datos](media/repl-06a.gif "Volver a publicar datos")</span><span class="sxs-lookup"><span data-stu-id="e60e5-119">![Republishing data](media/repl-06a.gif "Republishing data")</span></span>  
  
 <span data-ttu-id="e60e5-120">Cualquier servidor puede funcionar como publicador y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e60e5-120">Any server can act as both a Publisher and Subscriber.</span></span> <span data-ttu-id="e60e5-121">Por ejemplo, observe el siguiente diagrama en el que la publicación de una tabla que existe en Londres se tiene que distribuir a cuatro ciudades diferentes de los Estados Unidos: Chicago, Nueva York, San Diego y Seattle.</span><span class="sxs-lookup"><span data-stu-id="e60e5-121">For example, consider the following diagram in which a publication of a table exists in London and must be distributed to four different cities in the United States: Chicago, New York, San Diego, and Seattle.</span></span> <span data-ttu-id="e60e5-122">El servidor de Nueva York es el elegido para que se suscriba a la tabla publicada de Londres, porque el sitio de Nueva York cumple estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="e60e5-122">The server in New York is chosen to subscribe to the published table originating in London, because the New York site meets these conditions:</span></span>  
  
-   <span data-ttu-id="e60e5-123">El vínculo de red de retorno a Londres es relativamente confiable.</span><span class="sxs-lookup"><span data-stu-id="e60e5-123">The network link back to London is relatively reliable.</span></span>  
  
-   <span data-ttu-id="e60e5-124">Los costos de comunicación entre Londres y Nueva York son aceptables.</span><span class="sxs-lookup"><span data-stu-id="e60e5-124">The London-to-New York communication costs are acceptable.</span></span>  
  
-   <span data-ttu-id="e60e5-125">Hay buenas líneas de comunicación de red desde Nueva York a todos los demás sitios suscriptores de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="e60e5-125">There are good network communications lines from New York to all other Subscriber sites in the United States.</span></span>  
  
     <span data-ttu-id="e60e5-126">![Volver a publicar datos para ubicaciones dispersas](media/repl-06.gif "Volver a publicar datos para ubicaciones dispersas")</span><span class="sxs-lookup"><span data-stu-id="e60e5-126">![Republishing data to dispersed locations](media/repl-06.gif "Republishing data to dispersed locations")</span></span>  
  
 <span data-ttu-id="e60e5-127">La replicación es compatible con los casos de republicación que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e60e5-127">Replication supports the republishing scenarios shown in the following table.</span></span>  
  
|<span data-ttu-id="e60e5-128">Publicador</span><span class="sxs-lookup"><span data-stu-id="e60e5-128">Publisher</span></span>|<span data-ttu-id="e60e5-129">Suscriptor de publicación</span><span class="sxs-lookup"><span data-stu-id="e60e5-129">Publishing Subscriber</span></span>|<span data-ttu-id="e60e5-130">Suscriptor</span><span class="sxs-lookup"><span data-stu-id="e60e5-130">Subscriber</span></span>|  
|---------------|---------------------------|----------------|  
|<span data-ttu-id="e60e5-131">Publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e60e5-131">Transactional publication</span></span>|<span data-ttu-id="e60e5-132">Suscripción transaccional/publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e60e5-132">Transactional subscription/transactional publication</span></span>|<span data-ttu-id="e60e5-133">Suscripción transaccional</span><span class="sxs-lookup"><span data-stu-id="e60e5-133">Transactional subscription</span></span>|  
|<span data-ttu-id="e60e5-134">Publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e60e5-134">Transactional publication</span></span>|<span data-ttu-id="e60e5-135">Suscripción transaccional/publicación de combinación<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e60e5-135">Transactional subscription/merge publication<sup>1</sup></span></span>|<span data-ttu-id="e60e5-136">Suscripción de mezcla</span><span class="sxs-lookup"><span data-stu-id="e60e5-136">Merge subscription</span></span>|  
|<span data-ttu-id="e60e5-137">Publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="e60e5-137">Merge publication</span></span>|<span data-ttu-id="e60e5-138">Suscripción de mezcla/publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="e60e5-138">Merge subscription/merge publication</span></span>|<span data-ttu-id="e60e5-139">Suscripción de mezcla</span><span class="sxs-lookup"><span data-stu-id="e60e5-139">Merge subscription</span></span>|  
|<span data-ttu-id="e60e5-140">Publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="e60e5-140">Merge publication</span></span>|<span data-ttu-id="e60e5-141">Suscripción de mezcla/publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e60e5-141">Merge subscription/transactional publication</span></span>|<span data-ttu-id="e60e5-142">Suscripción transaccional</span><span class="sxs-lookup"><span data-stu-id="e60e5-142">Transactional subscription</span></span>|  
  
 <span data-ttu-id="e60e5-143"><sup>1</sup> Debe establecer la `@published_in_tran_pub` propiedad en la publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="e60e5-143"><sup>1</sup>You should set the `@published_in_tran_pub` property on the merge publication.</span></span> <span data-ttu-id="e60e5-144">De forma predeterminada, la replicación transaccional espera que las tablas del suscriptor se traten como de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e60e5-144">By default, transactional replication expects tables at the Subscriber to be treated as read-only.</span></span> <span data-ttu-id="e60e5-145">Si la replicación de mezcla realiza cambios en los datos de una tabla de una suscripción transaccional, la convergencia de los datos puede no producirse.</span><span class="sxs-lookup"><span data-stu-id="e60e5-145">If merge replication makes data changes to a table in a transactional subscription, non-convergence of data can occur.</span></span> <span data-ttu-id="e60e5-146">Para evitar este riesgo, se recomienda que cada tabla de este tipo se especifique como solo para descarga en la publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="e60e5-146">To avoid this risk, we recommend that any such table be specified as download-only in the merge publication.</span></span> <span data-ttu-id="e60e5-147">Esto evita que un suscriptor de mezcla cargue cambios de datos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e60e5-147">This prevents a merge Subscriber from uploading data changes to the table.</span></span> <span data-ttu-id="e60e5-148">Para más información, vea [Optimizar el rendimiento de la replicación de mezcla con artículos de solo descarga](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span><span class="sxs-lookup"><span data-stu-id="e60e5-148">For more information, see [Optimize Merge Replication Performance with Download-Only Articles](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60e5-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e60e5-149">See Also</span></span>  
 <span data-ttu-id="e60e5-150">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="e60e5-150">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="e60e5-151">[Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e60e5-151">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="e60e5-152">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="e60e5-152">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="e60e5-153">[Initialize a Subscription](initialize-a-subscription.md)  (Inicializar una suscripción)</span><span class="sxs-lookup"><span data-stu-id="e60e5-153">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="e60e5-154">Sincronizar datos</span><span class="sxs-lookup"><span data-stu-id="e60e5-154">Synchronize Data</span></span>](synchronize-data.md)  
  
  
