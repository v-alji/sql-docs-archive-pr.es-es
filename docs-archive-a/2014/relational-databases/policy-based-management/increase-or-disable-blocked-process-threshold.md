---
title: Aumentar o deshabilitar el umbral de procesos bloqueados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 71db8ef6-341b-4465-99db-5c63e48d4c7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7a90aea3fa8fb4d9c423cea1ec6008b01cde883
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663445"
---
# <a name="increase-or-disable-blocked-process-threshold"></a><span data-ttu-id="46d45-102">Aumentar o deshabilitar el umbral de procesos bloqueados</span><span class="sxs-lookup"><span data-stu-id="46d45-102">Increase or Disable Blocked Process Threshold</span></span>
  <span data-ttu-id="46d45-103">Esta regla comprueba si la opción blocked process threshold esté establecida en 0 (deshabilitada) o en un valor mayor o igual que 5 (segundos).</span><span class="sxs-lookup"><span data-stu-id="46d45-103">This rules checks that the blocked process threshold option is set to 0 (disabled) or set to a value higher than or equal to 5 (seconds).</span></span> <span data-ttu-id="46d45-104">Si se establece la opción blocked process threshold en un valor comprendido entre 1 y 4, puede provocar que el monitor de interbloqueo se ejecute constantemente.</span><span class="sxs-lookup"><span data-stu-id="46d45-104">Setting the blocked process threshold option to a value from 1 to 4 can cause the deadlock monitor to run constantly.</span></span> <span data-ttu-id="46d45-105">Los valores 1 a 4 solo se deberían utilizar para solucionar problemas y nunca a largo plazo o en un entorno de producción sin la ayuda del servicio de atención al cliente y soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46d45-105">Values 1 to 4 should only be used for troubleshooting, and never long term or in a production environment without the assistance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="46d45-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="46d45-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="46d45-107">Para resolver este problema, establezca el valor de la opción blocked process threshold en 5 (segundos) o más, o deshabilite el umbral de procesos bloqueados estableciendo el valor en 0.</span><span class="sxs-lookup"><span data-stu-id="46d45-107">To resolve this problem, set the blocked process threshold option to a value of 5 (seconds) or higher, or disable blocked process threshold by setting the value to 0.</span></span> <span data-ttu-id="46d45-108">Para establecer el valor en `5` segundos, ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="46d45-108">To set the blocked process threshold to a value of `5` seconds, execute the following statement:</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 5 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="46d45-109">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="46d45-109">For More Information</span></span>  
 [<span data-ttu-id="46d45-110">blocked process threshold (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="46d45-110">blocked process threshold Server Configuration Option</span></span>](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="46d45-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46d45-111">See Also</span></span>  
 [<span data-ttu-id="46d45-112">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="46d45-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
