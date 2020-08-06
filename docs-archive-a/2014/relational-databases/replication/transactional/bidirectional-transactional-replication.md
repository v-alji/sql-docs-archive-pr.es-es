---
title: Replicación transaccional bidireccional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- bidirectional replication
- transactional replication, bidirectional replication
- bidirectional transactional replication
ms.assetid: 98772e95-67ed-4010-8108-5113dbe709ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57b18dde2e7134e0ba9eb6a9b2e8f5357d171a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673630"
---
# <a name="bidirectional-transactional-replication"></a><span data-ttu-id="42530-102">replicación transaccional bidireccional</span><span class="sxs-lookup"><span data-stu-id="42530-102">Bidirectional Transactional Replication</span></span>
  <span data-ttu-id="42530-103">La replicación transaccional bidireccional es una topología de replicación transaccional específica que permite a dos servidores intercambiar cambios mutuamente: cada servidor publica datos y después se suscribe a una publicación con los mismos datos en el otro servidor.</span><span class="sxs-lookup"><span data-stu-id="42530-103">Bidirectional transactional replication is a specific transactional replication topology that allows two servers to exchange changes with each other: each server publishes data and then subscribes to a publication with the same data from the other server.</span></span> <span data-ttu-id="42530-104">El **@loopback_detection** parámetro de [sp_addsubscription &#40;&#41;de TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) se establece en true para garantizar que los cambios se envíen únicamente al suscriptor y no tengan como resultado que el cambio se envíe de vuelta al publicador.</span><span class="sxs-lookup"><span data-stu-id="42530-104">The **@loopback_detection** parameter of [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) is set to TRUE to ensure that changes are only sent to the Subscriber and do not result in the change being sent back to the Publisher.</span></span>  
  
 <span data-ttu-id="42530-105">En [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] y versiones posteriores, esta topología también es compatible con la replicación transaccional punto a punto, pero la replicación bidireccional puede proporcionar un mayor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="42530-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, this topology is also supported by peer-to-peer transactional replication, but bidirectional replication can provide improved performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42530-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42530-106">See Also</span></span>  
 [<span data-ttu-id="42530-107">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="42530-107">Peer-to-Peer Transactional Replication</span></span>](peer-to-peer-transactional-replication.md)  
  
  
