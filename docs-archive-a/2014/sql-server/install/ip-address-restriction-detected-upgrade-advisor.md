---
title: Restricción de dirección IP detectada (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 9a154455-c68f-4403-a3a7-b90f4d35eecb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2028e59e91d42bfdced2d18fa6ce129dfb108302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746105"
---
# <a name="ip-address-restriction-detected-upgrade-advisor"></a><span data-ttu-id="b4dd9-102">Se detectó una restricción de dirección IP (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="b4dd9-102">IP address restriction detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="b4dd9-103">El Asesor de actualizaciones ha detectado una o varias restricciones de dirección IP en el sitio web de IIS que hospeda los directorios virtuales del servidor de informes o del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="b4dd9-103">Upgrade Advisor detected one or more IP address restrictions on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="b4dd9-104">no proporciona compatibilidad nativa con las restricciones de dirección IP.</span><span class="sxs-lookup"><span data-stu-id="b4dd9-104">does not provide native support for IP address restrictions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="b4dd9-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Nativos.</span><span class="sxs-lookup"><span data-stu-id="b4dd9-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="b4dd9-106">Componente</span><span class="sxs-lookup"><span data-stu-id="b4dd9-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b4dd9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4dd9-107">Description</span></span>  
 <span data-ttu-id="b4dd9-108">La instalación no puede definir las restricciones de dirección IP en URL creadas para un servidor de informes actualizado.</span><span class="sxs-lookup"><span data-stu-id="b4dd9-108">Setup cannot define IP address restrictions on URLs created for an upgraded report server.</span></span> <span data-ttu-id="b4dd9-109">La actualización puede continuar, pero las restricciones de dirección IP no se definirán en las URL de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4dd9-109">Upgrade can continue, but IP address restrictions will not be defined on the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b4dd9-110">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="b4dd9-110">Corrective Action</span></span>  
 <span data-ttu-id="b4dd9-111">Tras la actualización, utilice ISA Server, su software de firewall u otra solución para permitir o denegar las solicitudes realizadas desde direcciones IP específicas al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b4dd9-111">After upgrade, use ISA Server, your firewall software, or another solution to allow or exclude requests from specific IP addresses to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4dd9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4dd9-112">See Also</span></span>  
 [<span data-ttu-id="b4dd9-113">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="b4dd9-113">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
