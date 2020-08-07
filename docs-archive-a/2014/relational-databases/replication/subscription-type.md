---
title: Tipo de suscripción | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscriptiontype.f1
ms.assetid: 9a50f588-ee45-4a87-826f-372ff0798587
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 614ff910b13706485ee9466c884243ff1c9027ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745711"
---
# <a name="subscription-type"></a><span data-ttu-id="e7cb4-102">Tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="e7cb4-102">Subscription Type</span></span>
  <span data-ttu-id="e7cb4-103">La replicación de mezcla ofrece dos tipos de suscripción: servidor y cliente (denominadas en versiones anteriores de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] global y local, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="e7cb4-103">Merge replication offers two subscription types: server and client (referred to in previous versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as global and local, respectively).</span></span> <span data-ttu-id="e7cb4-104">Los suscriptores con una suscripción de servidor pueden:</span><span class="sxs-lookup"><span data-stu-id="e7cb4-104">Subscribers with a server subscription can:</span></span>  
  
-   <span data-ttu-id="e7cb4-105">Volver a publicar datos en otros suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e7cb4-105">Republish data to other Subscribers.</span></span>  
  
-   <span data-ttu-id="e7cb4-106">Servir como asociados de sincronización alternativos.</span><span class="sxs-lookup"><span data-stu-id="e7cb4-106">Serve as alternate synchronization partners.</span></span>  
  
-   <span data-ttu-id="e7cb4-107">Solucionador de conflictos en función de la prioridad establecida.</span><span class="sxs-lookup"><span data-stu-id="e7cb4-107">Resolve conflicts according to a priority you set.</span></span>  
  
 <span data-ttu-id="e7cb4-108">La mayoría de los suscriptores no necesitan esta funcionalidad y pueden usar la suscripción de cliente.</span><span class="sxs-lookup"><span data-stu-id="e7cb4-108">Most Subscribers do not require this functionality and can use a client subscription.</span></span> <span data-ttu-id="e7cb4-109">Las suscripciones de cliente todavía permiten la detección y resolución de conflictos, pero los suscriptores no tienen asignada una prioridad: el primer suscriptor que envía un cambio al publicador gana cualquier conflicto que pueda surgir de ese cambio.</span><span class="sxs-lookup"><span data-stu-id="e7cb4-109">Client subscriptions still allow conflict detection and resolution, but Subscribers are not assigned a priority: the first Subscriber to submit a change to the Publisher wins any conflicts that might arise from that change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7cb4-110">El tipo de suscripción no se puede cambiar una vez creada la suscripción.</span><span class="sxs-lookup"><span data-stu-id="e7cb4-110">Subscription type cannot be changed after a subscription is created.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e7cb4-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="e7cb4-111">Options</span></span>  
 <span data-ttu-id="e7cb4-112">**Propiedades de la suscripción**</span><span class="sxs-lookup"><span data-stu-id="e7cb4-112">**Subscription properties**</span></span>  
 <span data-ttu-id="e7cb4-113">Para cada suscriptor, seleccione **Cliente** o **Servidor** en el cuadro de lista desplegable de la columna **Tipo de suscripción** .</span><span class="sxs-lookup"><span data-stu-id="e7cb4-113">For each Subscriber, select **Client** or **Server** from the drop-down list box in the **Subscription Type** column.</span></span> <span data-ttu-id="e7cb4-114">Para los suscriptores con suscripciones de servidor, escriba un número entre 0 y 99,99 en la columna **Prioridad para la resolución de conflictos** (cuanto mayor sea el número, más alta será la prioridad del suscriptor).</span><span class="sxs-lookup"><span data-stu-id="e7cb4-114">For Subscribers with server subscriptions, enter a number between 0 and 99.99 in the **Priority for Conflict Resolution** column (the higher the number, the higher the priority for the Subscriber).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7cb4-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7cb4-115">See Also</span></span>  
 <span data-ttu-id="e7cb4-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="e7cb4-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="e7cb4-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="e7cb4-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="e7cb4-118">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="e7cb4-118">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
