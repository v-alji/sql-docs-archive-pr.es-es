---
title: Se detectaron elementos de informe personalizados en el servidor de informes (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- custom report items, upgrading
ms.assetid: aee32006-65b2-4dfe-9570-d85a249d17b2
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: feacf6aa6f233f85a67b43e7b72d3a50913991bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670764"
---
# <a name="custom-report-items-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="471bb-102">Se detectaron elementos de informe personalizados en el servidor de informes (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="471bb-102">Custom report items were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="471bb-103">Los elementos de informe personalizados que se crearon para versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no son compatibles con [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="471bb-103">Custom report items that were created for previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are not compatible with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="471bb-104">La actualización puede continuar, pero los informes que utilicen algún elemento de informe personalizado no funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="471bb-104">Upgrade can continue, but reports that use the custom report item will not run as expected.</span></span> <span data-ttu-id="471bb-105">El Asesor de actualizaciones ha detectado elementos de informe personalizados.</span><span class="sxs-lookup"><span data-stu-id="471bb-105">Upgrade Advisor detected custom report items.</span></span> <span data-ttu-id="471bb-106">La actualización puede continuar, pero debe mover manualmente los archivos de elementos de informes personalizados a la nueva carpeta de instalación una vez completada la actualización.</span><span class="sxs-lookup"><span data-stu-id="471bb-106">Upgrade can continue, but you must manually move the custom report item files to the new installation folder after upgrade completes.</span></span>  
  
||  
|-|  
|<span data-ttu-id="471bb-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modo de SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="471bb-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="471bb-108">Componente</span><span class="sxs-lookup"><span data-stu-id="471bb-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="471bb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="471bb-109">Description</span></span>  
 <span data-ttu-id="471bb-110">El Asesor de actualizaciones ha detectado configuraciones de extensión de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] personalizada en los archivos de configuración, lo que indica que la instalación incluye uno o más ensamblados personalizados para informes.</span><span class="sxs-lookup"><span data-stu-id="471bb-110">Upgrade Advisor detected custom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] extension settings in the configuration files, indicating that your installation includes one or more custom assemblies for reports.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="471bb-111">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="471bb-111">Corrective Action</span></span>  
 <span data-ttu-id="471bb-112">Una vez completada la actualización, mueva manualmente los archivos de elementos de informes personalizados a la nueva carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="471bb-112">After upgrade completes, manually move the custom report item files to the new installation folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="471bb-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="471bb-113">See Also</span></span>  
 [<span data-ttu-id="471bb-114">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="471bb-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
