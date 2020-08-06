---
title: Suscripciones actualizables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 447114152365e098420f46d4b7e880e8f2907864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745190"
---
# <a name="updatable-subscriptions"></a><span data-ttu-id="09be2-102">Suscripciones actualizables</span><span class="sxs-lookup"><span data-stu-id="09be2-102">Updatable Subscriptions</span></span>
  <span data-ttu-id="09be2-103">Con la replicación transaccional, los datos replicados deben tratarse como de solo lectura, aunque puede modificarlos en un suscriptor de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante suscripciones actualizables.</span><span class="sxs-lookup"><span data-stu-id="09be2-103">With transactional replication, replicated data should be treated as read-only; however, you can modify replicated data at a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscriber by using updatable subscriptions.</span></span> <span data-ttu-id="09be2-104">Si necesita modificar datos en el suscriptor, elija una de las siguientes opciones en función de sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="09be2-104">If you need to modify data at the Subscriber, choose one of the following options depending on your requirements.</span></span>  
  
|<span data-ttu-id="09be2-105">Tipo de suscripción actualizable</span><span class="sxs-lookup"><span data-stu-id="09be2-105">Updatable Subscription Type</span></span>|<span data-ttu-id="09be2-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09be2-106">Requirements</span></span>|  
|---------------------------------|------------------|  
|<span data-ttu-id="09be2-107">Actualización inmediata</span><span class="sxs-lookup"><span data-stu-id="09be2-107">Immediate Updating</span></span>|<span data-ttu-id="09be2-108">El publicador y el suscriptor deben conectarse para actualizar datos en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="09be2-108">Publisher and Subscriber must be connected to update data at the Subscriber.</span></span>|  
|<span data-ttu-id="09be2-109">Actualización en cola</span><span class="sxs-lookup"><span data-stu-id="09be2-109">Queued Updating</span></span>|<span data-ttu-id="09be2-110">El publicador y el suscriptor no tienen que estar conectados para actualizar datos en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="09be2-110">Publisher and Subscriber do not have to be connected to update data at the Subscriber.</span></span> <span data-ttu-id="09be2-111">Las actualizaciones pueden realizarse sin conexión y sincronizarse después entre el publicador y el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="09be2-111">Updates can be made while offline, and later synchronized between the Publisher and Subscriber.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="09be2-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="09be2-112">Options</span></span>  
 <span data-ttu-id="09be2-113">**Replicar cambios de suscriptor**</span><span class="sxs-lookup"><span data-stu-id="09be2-113">**Replicate Subscriber changes**</span></span>  
 <span data-ttu-id="09be2-114">Active la casilla en la columna **Replicar** para cada suscriptor que deba realizar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="09be2-114">Select the check box in the **Replicate** column for each Subscriber that should be able to make updates.</span></span> <span data-ttu-id="09be2-115">Para los suscriptores que pueden realizar actualizaciones, seleccione la opción apropiada en el cuadro de lista desplegable de la columna **Confirmar en el publicador** :</span><span class="sxs-lookup"><span data-stu-id="09be2-115">For those Subscribers that can make updates, select the appropriate option from the drop-down list box in the **Commit at Publisher** column:</span></span>  
  
-   <span data-ttu-id="09be2-116">Seleccione **Confirmar cambios simultáneamente** para realizar una suscripción de actualización inmediata.</span><span class="sxs-lookup"><span data-stu-id="09be2-116">Select **Simultaneously commit changes** for an immediate updating subscription.</span></span>  
  
-   <span data-ttu-id="09be2-117">Seleccione **Poner en cola cambios y confirmar cuando sea posible** para realizar una suscripción de actualización en cola.</span><span class="sxs-lookup"><span data-stu-id="09be2-117">Select **Queue changes and commit when possible** for a queued updating subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09be2-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09be2-118">See Also</span></span>  
 <span data-ttu-id="09be2-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="09be2-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="09be2-120">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="09be2-120">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="09be2-121">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="09be2-121">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="09be2-122">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="09be2-122">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
