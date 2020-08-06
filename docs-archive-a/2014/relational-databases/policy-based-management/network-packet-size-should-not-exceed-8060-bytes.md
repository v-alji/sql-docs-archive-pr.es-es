---
title: El tamaño de paquete de red no debería superar 8060 bytes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 01b500cbe65107767d73bc2901b6d5e028b94ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670995"
---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a><span data-ttu-id="2ca57-102">El tamaño de paquete de red no debería superar 8060 bytes</span><span class="sxs-lookup"><span data-stu-id="2ca57-102">Network Packet Size Should Not Exceed 8060 Bytes</span></span>
  <span data-ttu-id="2ca57-103">Si el valor especificado para sp_configure 'network packet size' o si el tamaño de paquete de red de cualquier usuario registrado es mayor que 8060 bytes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza diferentes operaciones de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="2ca57-103">If the value specified for sp_configure 'network packet size' or if the network packet size of any logged-in user is more than 8060 bytes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs different memory allocation operations.</span></span> <span data-ttu-id="2ca57-104">Esto puede producir un aumento en el espacio de direcciones virtuales de proceso que no se reserva para el grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="2ca57-104">This can cause an increase in the process virtual address space that is not reserved for the buffer pool.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="2ca57-105">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="2ca57-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="2ca57-106">El tamaño de paquete de red no debería superar 8060 bytes.</span><span class="sxs-lookup"><span data-stu-id="2ca57-106">The network packet size should not exceed 8060 bytes.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="2ca57-107">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="2ca57-107">For More Information</span></span>  
 [<span data-ttu-id="2ca57-108">Artículo 903002 de Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="2ca57-108">Microsoft Knowledge Base article 903002</span></span>](https://go.microsoft.com/fwlink/?linkid=117749)  
  
## <a name="see-also"></a><span data-ttu-id="2ca57-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ca57-109">See Also</span></span>  
 [<span data-ttu-id="2ca57-110">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="2ca57-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
