---
title: La base de datos del servidor de informes no está configurada (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: b964300c-b220-4244-9fa6-c0c6a57760f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 072e689da3f43222396f071e607214a2ec494749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662507"
---
# <a name="report-server-database-is-not-configured-upgrade-advisor"></a><span data-ttu-id="83d67-102">La base de datos del servidor de informes no está configurada (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="83d67-102">Report server database is not configured (Upgrade Advisor)</span></span>
  <span data-ttu-id="83d67-103">La actualización está bloqueada debido a una configuración del servidor de informes incompleta.</span><span class="sxs-lookup"><span data-stu-id="83d67-103">Upgrade is blocked due to an incomplete report server configuration.</span></span> <span data-ttu-id="83d67-104">La base de datos del servidor de informes no está configurada.</span><span class="sxs-lookup"><span data-stu-id="83d67-104">The report server database is not configured.</span></span>  
  
||  
|-|  
|<span data-ttu-id="83d67-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modo de SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83d67-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="83d67-106">Componente</span><span class="sxs-lookup"><span data-stu-id="83d67-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="83d67-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="83d67-107">Description</span></span>  
 <span data-ttu-id="83d67-108">La instalación solo puede actualizar una instancia del servidor de informes que esté totalmente configurada.</span><span class="sxs-lookup"><span data-stu-id="83d67-108">Setup can only upgrade a fully configured report server instance.</span></span> <span data-ttu-id="83d67-109">Para continuar, debe configurar la base de datos del servidor de informes o usar el **Panel de control** de Microsoft Windows para quitar la característica del servidor de informes de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="83d67-109">To continue, you must either configure the report server database, or use Microsoft Windows **Control Panel** to remove the report server feature from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="83d67-110">Tras quitar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede actualizar otros componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83d67-110">After you remove [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can upgrade other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="83d67-111">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="83d67-111">Corrective Action</span></span>  
 <span data-ttu-id="83d67-112">Si no configuró la base de datos del servidor de informes, éste no estará operativo y debería eliminarse antes de la actualización.</span><span class="sxs-lookup"><span data-stu-id="83d67-112">If you did not configure the report server database, the report server is not operational and should be removed prior to upgrade.</span></span>  
  
 <span data-ttu-id="83d67-113">Para obtener información adicional sobre cómo desinstalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , vea [desinstalar Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span><span class="sxs-lookup"><span data-stu-id="83d67-113">For additional information on uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , see [Uninstall Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span></span> <span data-ttu-id="83d67-114">En este tema se describe cómo desinstalar una versión concreta; los procedimientos son similares para versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="83d67-114">the topic describes how to uninstall a specific version and the procedures are similar for previous versions as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d67-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83d67-115">See Also</span></span>  
 [<span data-ttu-id="83d67-116">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="83d67-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
