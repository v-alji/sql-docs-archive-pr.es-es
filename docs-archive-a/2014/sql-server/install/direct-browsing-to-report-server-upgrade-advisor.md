---
title: Exploración directa del servidor de informes (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3d2814a4-318a-45ed-b093-1e852fab561f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ab4d146bba4bd87de56b30ad100b57f79eb68de3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677401"
---
# <a name="direct-browsing-to-report-server-upgrade-advisor"></a><span data-ttu-id="8fa3c-102">Exploración directa del servidor de informes (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="8fa3c-102">Direct Browsing to Report Server (Upgrade Advisor)</span></span>
  <span data-ttu-id="8fa3c-103">El asesor de actualizaciones ha detectado que la instalación actual de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] está navegando directamente al directorio virtual del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8fa3c-103">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory.</span></span>  
  
||  
|-|  
|<span data-ttu-id="8fa3c-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fa3c-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="8fa3c-105">Componente</span><span class="sxs-lookup"><span data-stu-id="8fa3c-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="8fa3c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fa3c-106">Description</span></span>  
 <span data-ttu-id="8fa3c-107">El asesor de actualizaciones ha detectado que la instalación actual de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] está navegando directamente al directorio virtual del servidor de informes, por ejemplo, **http:// \<server name> /ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="8fa3c-107">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory, for example **http://\<server name>/ReportServer**.</span></span> <span data-ttu-id="8fa3c-108">Esto no se admite en las versiones actuales de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fa3c-108">This is not supported in current versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fa3c-109">Esta regla es una advertencia y la actualización no se bloquea.</span><span class="sxs-lookup"><span data-stu-id="8fa3c-109">This rule is a warning and upgrade is not blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="8fa3c-110">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="8fa3c-110">Corrective Action</span></span>  
 <span data-ttu-id="8fa3c-111">Examine el uso de la interfaz de usuario de SharePoint para bibliotecas de documentos o use el \*\* \<server name>> del sitio/sharepoint de http:///_vti_bin/ReportServer\*\*.</span><span class="sxs-lookup"><span data-stu-id="8fa3c-111">Browse using the SharePoint user interface for document libraries or use **http://\<server name>/sharepoint site>/_vti_bin/reportserver**.</span></span>  
  
  
