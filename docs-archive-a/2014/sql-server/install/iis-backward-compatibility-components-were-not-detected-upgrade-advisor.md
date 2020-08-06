---
title: No se detectaron componentes de compatibilidad con versiones anteriores de IIS (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IIS [Reporting Services]
ms.assetid: e794185a-0a77-480a-9aea-d09f8760a6b8
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a5aad54a01b3840e121c6a63de0ea26f35921fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676821"
---
# <a name="iis-backward-compatibility-components-were-not-detected-upgrade-advisor"></a><span data-ttu-id="a0f3b-102">No se detectaron componentes de compatibilidad con versiones anteriores de IIS (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="a0f3b-102">IIS backward compatibility components were not detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="a0f3b-103">El Asesor de actualizaciones no ha detectado componentes y configuraciones de IIS que proporcionan la información utilizada por el programa de instalación para crear las nuevas URL de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0f3b-103">Upgrade Advisor did not detect IIS components and settings that provide information used by Setup to create new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLS.</span></span>  
  
||  
|-|  
|<span data-ttu-id="a0f3b-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="a0f3b-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="a0f3b-105">Componente</span><span class="sxs-lookup"><span data-stu-id="a0f3b-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a0f3b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0f3b-106">Description</span></span>  
 <span data-ttu-id="a0f3b-107">IIS incluye componentes que proporcionan información acerca de los directorios virtuales del Administrador de informes y del servidor de informes, y esos componentes no se instalan en el equipo del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a0f3b-107">IIS includes components that provide information about the report server and Report Manager virtual directories, and those components are not installed on the report server computer.</span></span> <span data-ttu-id="a0f3b-108">La actualización puede continuar, pero ésta no volverá a crear las URL para el servidor de informes o para el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="a0f3b-108">Upgrade can continue, but URLs for the report server or Report Manager will not be recreated by upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a0f3b-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="a0f3b-109">Corrective Action</span></span>  
 <span data-ttu-id="a0f3b-110">Tras finalizar la actualización, utilice la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para establecer las URL para el servidor de informes o para el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="a0f3b-110">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set the URLs for report server or Report Manager.</span></span> <span data-ttu-id="a0f3b-111">Utilice el Administrador de IIS para quitar los directorios virtuales que no necesite.</span><span class="sxs-lookup"><span data-stu-id="a0f3b-111">Use IIS Manager to remove the virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="a0f3b-112">Para obtener más información, vea [configurar una dirección URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) en los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] libros en pantalla de.</span><span class="sxs-lookup"><span data-stu-id="a0f3b-112">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f3b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0f3b-113">See Also</span></span>  
 [<span data-ttu-id="a0f3b-114">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="a0f3b-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
