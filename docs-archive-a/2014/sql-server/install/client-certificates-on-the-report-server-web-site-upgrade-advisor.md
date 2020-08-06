---
title: Certificados de cliente en el sitio web del servidor de informes (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 5ecce26b-99df-4109-8e51-d150d369dff7
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 563a64e695ef552a712a5678f56d38fdfbff619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672502"
---
# <a name="client-certificates-on-the-report-server-web-site-upgrade-advisor"></a><span data-ttu-id="ed73a-102">Certificados de cliente en el sitio web del servidor de informes (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="ed73a-102">Client certificates on the report server web site (Upgrade Advisor)</span></span>
  <span data-ttu-id="ed73a-103">El Asesor de actualizaciones detectó uno o más certificados de cliente en el sitio web de IIS que hospeda el servidor de informes o los directorios virtuales del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="ed73a-103">Upgrade Advisor detected one or more client certificates on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span>  
  
||  
|-|  
|<span data-ttu-id="ed73a-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="ed73a-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="ed73a-105">Componente</span><span class="sxs-lookup"><span data-stu-id="ed73a-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ed73a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed73a-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="ed73a-107">no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] admite el uso de certificados de cliente para autenticar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed73a-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support the use of client certificates to authenticate users.</span></span> <span data-ttu-id="ed73a-108">La actualización puede continuar, pero el servidor de informes actualizado no utilizará los certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="ed73a-108">Upgrade can continue, but client certificates will not be used by the upgraded report server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="ed73a-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="ed73a-109">Corrective Action</span></span>  
 <span data-ttu-id="ed73a-110">Tendrá que utilizar una solución independiente como ISA Server para asegurarse de que se cumplen todos los requisitos de autenticación de certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="ed73a-110">You will have to use a separate solution such as ISA Server to ensure any client certificate authentication requirements are addressed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed73a-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed73a-111">See Also</span></span>  
 [<span data-ttu-id="ed73a-112">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="ed73a-112">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
