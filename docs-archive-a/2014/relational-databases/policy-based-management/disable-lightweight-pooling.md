---
title: Deshabilitar la agrupación ligera | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 481bb43d-6fe5-497c-9096-971fb6bf733b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13b9ccba0a3a5805dab2eec1d04cc161e6dbd6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750809"
---
# <a name="disable-lightweight-pooling"></a><span data-ttu-id="738e8-102">Deshabilitar la agrupación ligera</span><span class="sxs-lookup"><span data-stu-id="738e8-102">Disable Lightweight Pooling</span></span>
  <span data-ttu-id="738e8-103">Esta regla comprueba que la agrupación ligera está deshabilitada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="738e8-103">This rule checks that lightweight pooling is disabled on the server.</span></span> <span data-ttu-id="738e8-104">Si establece lightweightpooling en el valor 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cambiará a la programación en modo de fibra.</span><span class="sxs-lookup"><span data-stu-id="738e8-104">Setting lightweightpooling to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="738e8-105">El modo de fibra se destina a determinadas situaciones en las que el cambio de contexto de los trabajadores de UMS es un cuello de botella importante para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="738e8-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers is the important bottleneck in performance.</span></span> <span data-ttu-id="738e8-106">Al ser esta situación inusual, el modo de fibra rara vez mejora el rendimiento o la escalabilidad en el sistema típico.</span><span class="sxs-lookup"><span data-stu-id="738e8-106">Because this is rare, fiber mode seldom improves performance or scalability on the typical system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="738e8-107">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="738e8-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="738e8-108">La opción lightweightpooling solo debería habilitarse después de realizar pruebas minuciosas, una vez evaluadas todas las demás oportunidades de ajustar el rendimiento y cuando el cambio de contexto sea un problema constatado del entorno.</span><span class="sxs-lookup"><span data-stu-id="738e8-108">The lightweightpooling option should only be enabled after thorough testing, after all other performance tuning opportunities are evaluated, and when context switching is a known issue in your environment.</span></span>  
  
 <span data-ttu-id="738e8-109">Se recomienda no usar la programación del modo de fibra en el funcionamiento normal porque puede reducir el rendimiento al impedir las ventajas normales del cambio de contexto y que algunos componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usan el almacenamiento local de subprocesos (TLS) u objetos de subprocesos, como exclusiones mutuas (un tipo de objeto de kernel de Win32), no pueden funcionar correctamente en modo de fibra.</span><span class="sxs-lookup"><span data-stu-id="738e8-109">We recommend that you do not use fiber mode scheduling for routine operation because it can decrease performance by preventing the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a kind of Win32 kernel object), cannot function correctly in fiber mode</span></span>  
  
 <span data-ttu-id="738e8-110">Para quitar la agrupación ligera, ejecute la instrucción siguiente y, a continuación, reinicie [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="738e8-110">To remove lightweight pooling, execute the following statement, and then restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
sp_configure 'lightweightpooling', 0;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="738e8-111">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="738e8-111">For More Information</span></span>  
 [<span data-ttu-id="738e8-112">lightweight pooling (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="738e8-112">lightweight pooling Server Configuration Option</span></span>](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="738e8-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="738e8-113">See Also</span></span>  
 [<span data-ttu-id="738e8-114">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="738e8-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
