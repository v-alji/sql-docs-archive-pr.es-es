---
title: Filtros ISAPI detectados en el sitio del servidor de informes (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ISAPI filters
- report servers [Reporting Services], upgrade issues
ms.assetid: dd30560d-9e16-47c7-ba68-a9743a657e4e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: bff1834ddf1b8f90787a47a8fd58a240d2b715d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749614"
---
# <a name="isapi-filters-detected-on-the-report-server-site-upgrade-advisor"></a><span data-ttu-id="fc64f-102">Se han detectado filtros ISAPI en el sitio del servidor de informes (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="fc64f-102">ISAPI filters detected on the report server site (Upgrade Advisor)</span></span>
  <span data-ttu-id="fc64f-103">El Asesor de actualizaciones ha detectado uno o más filtros ISAPI en el sitio web que hospeda los directorios virtuales del Administrador de informes y del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fc64f-103">Upgrade Advisor detected one or more ISAPI filters on the Web site that hosts the report server and Report Manager virtual directories.</span></span> <span data-ttu-id="fc64f-104">Los Filtros ISAPI no se admiten en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc64f-104">ISAPI filters are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="fc64f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Nativos.</span><span class="sxs-lookup"><span data-stu-id="fc64f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native .</span></span>|  
  
## <a name="component"></a><span data-ttu-id="fc64f-106">Componente</span><span class="sxs-lookup"><span data-stu-id="fc64f-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="fc64f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc64f-107">Description</span></span>  
 <span data-ttu-id="fc64f-108">Antes de actualizar, compruebe si los filtros ISAPI del sitio web están siendo utilizados por aplicaciones de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc64f-108">Before upgrading, verify whether the ISAPI filters on the Web site are used by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications.</span></span> <span data-ttu-id="fc64f-109">Si no necesita el filtro ISAPI, puede actualizar el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fc64f-109">If you do not require the ISAPI filter, you can upgrade the report server.</span></span> <span data-ttu-id="fc64f-110">La instalación creará las URL predeterminadas, sin compatibilidad con el filtro ISAPI que se ejecuta en IIS.</span><span class="sxs-lookup"><span data-stu-id="fc64f-110">Setup will create the default URLs, without support for the ISAPI filter that runs in IIS.</span></span> <span data-ttu-id="fc64f-111">Si necesita el filtro ISAPI, no lleve a cabo la actualización hasta que encuentre una forma alternativa de hospedar el filtro ISAPI (por ejemplo, utilizando ISA Server u hospedándolo en IIS).</span><span class="sxs-lookup"><span data-stu-id="fc64f-111">If you require the ISAPI filter, do not upgrade until you find an alternative way of hosting the ISAPI filter (for example, using ISA Server or continuing to host the ISAPI filter in IIS).</span></span> <span data-ttu-id="fc64f-112">El servidor de informes admite ASP.NET HTTPModules como reemplazo de los filtros ISAPI en determinadas situaciones.</span><span class="sxs-lookup"><span data-stu-id="fc64f-112">The report server supports ASP.NET HTTPModules as a replacement for ISAPI filters in certain scenarios.</span></span> <span data-ttu-id="fc64f-113">Para obtener más información, vea la documentación de ASP.NET en MSDN.</span><span class="sxs-lookup"><span data-stu-id="fc64f-113">For more information, see the ASP.NET documentation on MSDN.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="fc64f-114">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="fc64f-114">Corrective Action</span></span>  
 <span data-ttu-id="fc64f-115">Evalúe y utilice una solución independiente para hospedar los filtros ISAPI requeridos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="fc64f-115">Evaluate and use a separate solution for hosting ISAPI filters required by your deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc64f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc64f-116">See Also</span></span>  
 [<span data-ttu-id="fc64f-117">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="fc64f-117">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
