---
title: Comprobar el valor de Máximo de subprocesos de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 2d94adfd-3ba1-493a-b29a-b436f9d583df
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dbffb87f58d2beb633f43ff18680222ea62cf5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670979"
---
# <a name="verify-max-worker-threads-setting"></a><span data-ttu-id="931ba-102">Comprobar el valor de Máximo de subprocesos de trabajo</span><span class="sxs-lookup"><span data-stu-id="931ba-102">Verify Max Worker Threads Setting</span></span>
  <span data-ttu-id="931ba-103">Esta regla comprueba si la opción de servidor Máximo de subprocesos de trabajo tiene valores potencialmente incorrectos.</span><span class="sxs-lookup"><span data-stu-id="931ba-103">This rule checks the max worker threads server option for potentially incorrect settings.</span></span> <span data-ttu-id="931ba-104">Al establecer la opción Máximo de subprocesos de trabajo en un valor pequeño, puede evitar que suficientes subprocesos atiendan las solicitudes de clientes entrantes de una manera oportuna y podría provocar el "colapso de los subprocesos".</span><span class="sxs-lookup"><span data-stu-id="931ba-104">Setting the max worker threads option to a small value may prevent enough threads from servicing incoming client requests in a timely manner and could lead to "thread starvation".</span></span> <span data-ttu-id="931ba-105">Sin embargo, al establecer la opción en un valor grande, puede desperdiciar el espacio de direcciones, porque cada subproceso activo consume 512 KB en los servidores de 32 bits y hasta 4 MB en los servidores de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="931ba-105">However, setting the option to a large value can waste address space, because each active thread consumes 512 KB on 32-bit servers and up to 4 MB on 64-bit servers.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="931ba-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="931ba-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="931ba-107">Establezca la opción Máximo de subprocesos de trabajo en 0.</span><span class="sxs-lookup"><span data-stu-id="931ba-107">Set the max worker threads option to 0.</span></span> <span data-ttu-id="931ba-108">Esto permite que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] determine automáticamente el número correcto de subprocesos de trabajo activos según las solicitudes de usuario.</span><span class="sxs-lookup"><span data-stu-id="931ba-108">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically determine the correct number of active worker threads based on user requests.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="931ba-109">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="931ba-109">For More Information</span></span>  
 [<span data-ttu-id="931ba-110">Establecer la opción de configuración del servidor Máximo de subprocesos de trabajo</span><span class="sxs-lookup"><span data-stu-id="931ba-110">Configure the max worker threads Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="931ba-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="931ba-111">See Also</span></span>  
 [<span data-ttu-id="931ba-112">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="931ba-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
