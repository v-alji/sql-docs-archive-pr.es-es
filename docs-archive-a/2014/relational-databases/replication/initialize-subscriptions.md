---
title: Inicializar suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8c9388138ddec275dc1abd2b75e0b0c7fc99de4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663336"
---
# <a name="initialize-subscriptions"></a><span data-ttu-id="9373a-102">Inicializar suscripciones</span><span class="sxs-lookup"><span data-stu-id="9373a-102">Initialize Subscriptions</span></span>
  <span data-ttu-id="9373a-103">Deberá inicializar los suscriptores antes de que puedan comenzar a recibir datos replicados.</span><span class="sxs-lookup"><span data-stu-id="9373a-103">Subscribers must be initialized before they can begin receiving replicated data.</span></span> <span data-ttu-id="9373a-104">No se requiere un conjunto de datos inicial, pero el suscriptor deberá poseer al menos el esquema de cada objeto replicado y todas las tablas de metadatos y los procedimientos necesarios para la replicación.</span><span class="sxs-lookup"><span data-stu-id="9373a-104">An initial dataset is not required, but the Subscriber must at least have the schema for each replicated object and any metadata tables and procedures required by replication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9373a-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="9373a-105">Options</span></span>  
 <span data-ttu-id="9373a-106">**Propiedades de la suscripción**</span><span class="sxs-lookup"><span data-stu-id="9373a-106">**Subscription properties**</span></span>  
 <span data-ttu-id="9373a-107">Active la casilla de la columna **Inicializar** para cada suscriptor que necesite un conjunto de datos inicial.</span><span class="sxs-lookup"><span data-stu-id="9373a-107">Select the check box in the **Initialize** column for each Subscriber that requires an initial data set.</span></span> <span data-ttu-id="9373a-108">Si desactiva la casilla, solo se inicializarán los procedimientos y metadatos de replicación.</span><span class="sxs-lookup"><span data-stu-id="9373a-108">If the check box is cleared, only the replication metadata and procedures will be initialized.</span></span> <span data-ttu-id="9373a-109">Para más información, vea [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md) (Inicializar una suscripción transaccional sin una instantánea).</span><span class="sxs-lookup"><span data-stu-id="9373a-109">For more information about initializing a subscription without a snapshot, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
 <span data-ttu-id="9373a-110">Seleccione **Inmediatamente** en la columna **Inicializar cuando** del cuadro de lista desplegable para que el Agente de mezcla o el Agente de distribución transfieran los archivos de instantáneas al suscriptor una vez finalizado el asistente.</span><span class="sxs-lookup"><span data-stu-id="9373a-110">Select **Immediately** from the drop-down list box in the **Initialize When** column to have the Merge Agent or Distribution Agent transfer snapshot files to the Subscriber after this wizard is completed.</span></span> <span data-ttu-id="9373a-111">Seleccione **En la primera sincronización** para que el agente transfiera los archivos la próxima vez que esté programado para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="9373a-111">Select **At first synchronization** to have the agent transfer the files the next time it is scheduled to run.</span></span> <span data-ttu-id="9373a-112">La opción **Inmediatamente** no está disponible para suscripciones de extracción a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9373a-112">The **Immediately** option is not available for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="9373a-113">El Agente de mezcla y el Agente de distribución no se ejecutarán con instancias de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], por lo que deberá inicializar la suscripción de otra forma.</span><span class="sxs-lookup"><span data-stu-id="9373a-113">The Merge Agent and Distribution Agent do not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; therefore the subscription must be initialized through another method.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9373a-114">El asistente podría solicitar una conexión al distribuidor para iniciar un trabajo adecuado del Agente de distribución o el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="9373a-114">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9373a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9373a-115">See Also</span></span>  
 <span data-ttu-id="9373a-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="9373a-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="9373a-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="9373a-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="9373a-118">[Initialize a Subscription](initialize-a-subscription.md)  (Inicializar una suscripción)</span><span class="sxs-lookup"><span data-stu-id="9373a-118">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="9373a-119">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="9373a-119">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
