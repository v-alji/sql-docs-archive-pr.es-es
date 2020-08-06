---
title: La actualización modificará las suscripciones de actualización en cola que utilizan Message Queue Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication]
- MSMQ [SQL Server replication]
- queues [SQL Server replication]
- queued updating subscriptions [SQL Server replication]
ms.assetid: 97944de3-fbad-4db1-939a-dcd550bf5893
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d44cbad43d75634cbf8660110cc879522265c54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751666"
---
# <a name="upgrading-will-modify-queued-updating-subscriptions-that-use-message-queuing"></a><span data-ttu-id="5224e-102">Con la actualización, se modificarán las suscripciones de actualización en cola que utilicen Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="5224e-102">Upgrading will modify queued updating subscriptions that use Message Queuing</span></span>
  <span data-ttu-id="5224e-103">El Asesor de actualizaciones ha detectado que podría tener una o más suscripciones de actualización en cola que utilizan [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queue Server (también conocido como MSMQ).</span><span class="sxs-lookup"><span data-stu-id="5224e-103">Upgrade Advisor detected that you might have one or more queued updating subscriptions that use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="5224e-104">La replicación ya no admite Message Queue Server, por lo que las suscripciones se modificarán de forma que usen una cola de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5224e-104">Replication no longer supports Message Queuing; therefore, the subscriptions will be modified to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span>  
  
 <span data-ttu-id="5224e-105">Solo se permite un valor de **SQL** .</span><span class="sxs-lookup"><span data-stu-id="5224e-105">Only a value of **sql** is allowed.</span></span> <span data-ttu-id="5224e-106">Las publicaciones existentes que usan Message Queue Server se modifican durante la actualización para que usen una cola de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5224e-106">Existing publications that use Message Queuing are modified during upgrade to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="5224e-107">Si tiene aplicaciones que dependen de las actualizaciones en cola que utilizan Message Queue Server, estas aplicaciones deberán reescribirse para su inclusión en una cola de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5224e-107">If you have applications that depend on queued updating using Message Queuing, these applications will have to be rewritten to accommodate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="5224e-108">Para obtener más información sobre las suscripciones de actualización en cola, vea "Suscripciones actualizable para la replicación transaccional" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5224e-108">For more information about queued updating subscriptions, see "Updatable Subscriptions for Transactional Replication" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="5224e-109">La actualización quitará las colas de suscripción de Message Queue Server existentes si el servicio Message Queue Server se ejecuta mientras [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se actualiza.</span><span class="sxs-lookup"><span data-stu-id="5224e-109">Upgrade will remove the existing Message Queuing subscription queues if the Message Queuing service is running while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being upgraded.</span></span>  
  
 <span data-ttu-id="5224e-110">Si el servicio Message Queue Server no está en ejecución, elimine manualmente las colas una vez completada la actualización.</span><span class="sxs-lookup"><span data-stu-id="5224e-110">If the Message Queuing service is not running, remove the queues manually after upgrade is complete.</span></span> <span data-ttu-id="5224e-111">Para obtener más información acerca de cómo quitar colas, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="5224e-111">For more information about how to remove queues, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5224e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5224e-112">See Also</span></span>  
 [<span data-ttu-id="5224e-113">Problemas de actualización de replicación</span><span class="sxs-lookup"><span data-stu-id="5224e-113">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
