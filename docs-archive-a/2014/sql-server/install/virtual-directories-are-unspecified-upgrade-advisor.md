---
title: Los directorios virtuales no están especificados (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 7d32b560-49d6-4558-b5d6-9127067f82d6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e20c48d0bf58d28cb2894baa26c2e11db26fab96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672403"
---
# <a name="virtual-directories-are-unspecified-upgrade-advisor"></a><span data-ttu-id="c822c-102">Los directorios virtuales no están especificados (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="c822c-102">Virtual directories are unspecified (Upgrade Advisor)</span></span>
  <span data-ttu-id="c822c-103">El Asesor de actualizaciones no ha detectado ninguna configuración de directorios virtuales para el servicio web del servidor de informes o para el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="c822c-103">Upgrade Advisor did not detect virtual directory settings for the Report Server Web service or Report Manager.</span></span> <span data-ttu-id="c822c-104">Una vez completada la actualización, debe configurar las reservas de direcciones URL para el servidor de informes mediante el Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c822c-104">After upgrade completes, you must configure URL reservations for the report server by using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager.</span></span>  
  
||  
|-|  
|<span data-ttu-id="c822c-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="c822c-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="c822c-106">Componente</span><span class="sxs-lookup"><span data-stu-id="c822c-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c822c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c822c-107">Description</span></span>  
 <span data-ttu-id="c822c-108">La actualización de una instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] incluye reservar nuevas URL para el servicio web del servidor de informes y para el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="c822c-108">Upgrading a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation includes reserving new URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="c822c-109">El Asesor de actualizaciones no ha detectado directorios virtuales para el servidor de informes o para el Administrador de informes de la instancia que se va a actualizar y, por consiguiente, el proceso de actualización no pudo recopilar información suficiente para crear las reservas de direcciones URL del servidor de informes actualizado.</span><span class="sxs-lookup"><span data-stu-id="c822c-109">Upgrade Advisor did not detect virtual directories for the report server or Report Manager for the instance to be upgraded, and therefore the upgrade process has insufficient information to create URL reservations for the upgraded report server.</span></span> <span data-ttu-id="c822c-110">La actualización puede continuar, pero el directorio virtual del servidor de informes o del Administrador de informes quedará sin definir después de la instalación de la actualización.</span><span class="sxs-lookup"><span data-stu-id="c822c-110">Upgrade can continue, but the report server or Report Manager virtual directory will be undefined after the upgraded installation.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c822c-111">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="c822c-111">Corrective Action</span></span>  
 <span data-ttu-id="c822c-112">Tras finalizar la actualización, use el Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para establecer las direcciones URL para el servidor de informes y para el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="c822c-112">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to set the URLs for report server and Report Manager.</span></span> <span data-ttu-id="c822c-113">Use el administrador de IIS para quitar los directorios virtuales que ya no necesite.</span><span class="sxs-lookup"><span data-stu-id="c822c-113">Use IIS Manager to remove any virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="c822c-114">Para obtener más información, vea [configurar una dirección URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) en los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] libros en pantalla de.</span><span class="sxs-lookup"><span data-stu-id="c822c-114">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c822c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c822c-115">See Also</span></span>  
 [<span data-ttu-id="c822c-116">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="c822c-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
