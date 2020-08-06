---
title: Solucionar problemas de una instalación de PowerPivot para SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97bc2ce7-af04-4372-ad79-c96b8c3417ab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3adc27132d976288c14ac702baae0b842e8aef0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672444"
---
# <a name="troubleshoot-a-powerpivot-for-sharepoint-installation"></a><span data-ttu-id="3520b-102">Solucionar problemas de una instalación de PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="3520b-102">Troubleshoot a PowerPivot for SharePoint Installation</span></span>
  <span data-ttu-id="3520b-103">Si obtiene errores en lugar de las páginas y características que espera, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3520b-103">If you get errors instead of the pages and features you expect, do the following.</span></span>  
  
-   <span data-ttu-id="3520b-104">Revise las notas de la versión para SharePoint y [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] con el fin de conocer soluciones alternativas para los problemas de instalación conocidos.</span><span class="sxs-lookup"><span data-stu-id="3520b-104">Review release notes for both SharePoint and [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to get workarounds for known installation problems.</span></span> <span data-ttu-id="3520b-105">Las notas de la versión se proporcionan con los discos de instalación o en el sitio de Microsoft del que descargó el software.</span><span class="sxs-lookup"><span data-stu-id="3520b-105">Release notes are provided with the installation media or on the Microsoft site from which you downloaded the software.</span></span>  
  
    -   <span data-ttu-id="3520b-106">[SQL Server notas](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx)de la versión de 2014.</span><span class="sxs-lookup"><span data-stu-id="3520b-106">[SQL Server 2014 Release Notes](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span></span>  
  
-   <span data-ttu-id="3520b-107">Vea el tema de la wiki [de TechNet sobre cómo solucionar problemas de instalaciones de PowerPivot (y otros complementos)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span><span class="sxs-lookup"><span data-stu-id="3520b-107">See the Technet wiki topic, [Troubleshooting Installations of PowerPivot (and other add-ins)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span></span>  
  
## <a name="issues"></a><span data-ttu-id="3520b-108">Issues</span><span class="sxs-lookup"><span data-stu-id="3520b-108">Issues</span></span>  
  
### <a name="powerpivot-gallery-thumbnail-images-show-as-a-red-x"></a><span data-ttu-id="3520b-109">Las imágenes en miniatura de la galería de PowerPivot se muestran como una X roja</span><span class="sxs-lookup"><span data-stu-id="3520b-109">PowerPivot Gallery Thumbnail images show as a red X</span></span>  
 <span data-ttu-id="3520b-110">Una posible causa es que la **integración de las características de PowerPivot para las colecciones de sitios** no esté activa.</span><span class="sxs-lookup"><span data-stu-id="3520b-110">One Possible cause is the **PowerPivot features Integration for Site Collections** is not active.</span></span> <span data-ttu-id="3520b-111">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3520b-111">Complete the following:</span></span>  
  
1.  <span data-ttu-id="3520b-112">En la biblioteca de la galería de PowerPivot, haga clic en **configuración del sitio** desde el icono de engranaje ![configuración de SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Configuración de SharePoint") o desde la lista **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="3520b-112">In the PowerPivot Gallery library, click **Site Settings** from either the gear icon ![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings") or the **Home** list.</span></span>  
  
2.  <span data-ttu-id="3520b-113">En la sección **Administración de la colección de sitios** , haga clic en **Características de la colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="3520b-113">In the **Site Collection Administration** section, click **Site Collection Features**.</span></span>  
  
3.  <span data-ttu-id="3520b-114">Haga clic en **Características de la colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="3520b-114">Click **Site Collection Features**.</span></span>  
  
4.  <span data-ttu-id="3520b-115">Compruebe que la **integración de las características de PowerPivot para las colecciones de sitios** está **activa**.</span><span class="sxs-lookup"><span data-stu-id="3520b-115">Verify **PowerPivot features Integration for Site Collections** is **Active**.</span></span>  
  
 <span data-ttu-id="3520b-116">Para otras causas de este problema, vea [la galería de PowerPivot muestra X roja para iconos](https://support.microsoft.com/kb/2361559) ( https://support.microsoft.com/kb/2361559) .</span><span class="sxs-lookup"><span data-stu-id="3520b-116">For additional causes of this issue, see [PowerPivot Gallery shows Red X's for Icons](https://support.microsoft.com/kb/2361559) (https://support.microsoft.com/kb/2361559).</span></span>  
  
  
