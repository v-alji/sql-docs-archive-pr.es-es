---
title: Instalar Herramientas de administración de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Tools
ms.assetid: af68d59a-a04d-4f23-9967-ad4ee2e63381
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 39a7ed6d859c6bbbb63e938cc7127958082737dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675160"
---
# <a name="install-sql-server-management-tools"></a><span data-ttu-id="68991-102">Instalar las herramientas de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="68991-102">Install SQL Server Management Tools</span></span>
  <span data-ttu-id="68991-103">Las herramientas de administración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incluyen los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="68991-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management tools include the following components:</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="68991-104">Asistente para la optimización de bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68991-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Tuning Advisor</span></span>  
  
-   <span data-ttu-id="68991-105">Herramientas del símbolo del sistema, como sqlcmd.exe y osql.exe</span><span class="sxs-lookup"><span data-stu-id="68991-105">Command prompt tools, such as sqlcmd.exe and osql.exe.</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="68991-106">Complementos para [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68991-106">add-ins to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
 <span data-ttu-id="68991-107">Observe que [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] es una opción independiente durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68991-107">Note that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] is a separate option during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="68991-108">Con independencia del número de instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instaladas en un equipo, solo se instalará una copia de las herramientas de administración de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68991-108">Regardless of how many instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are installed on a computer, only one copy of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Management Tools will be installed.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="68991-109">Las herramientas de administración pueden ejecutarse en paralelo en el mismo equipo con versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="68991-109">Management Tools can run side-by-side on the same computer with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Tools.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68991-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68991-110">See Also</span></span>  
 <span data-ttu-id="68991-111">[Características admitidas por las ediciones de SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="68991-111">[Features Supported by the Editions of SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="68991-112">[Ediciones y componentes de SQL Server 2014](../editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="68991-112">[Editions and Components of SQL Server 2014](../editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="68991-113">[Instale SQL Server 2014 desde el Asistente para la instalación &#40;el programa de instalación&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="68991-113">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 [<span data-ttu-id="68991-114">Actualice a SQL Server 2014 mediante el Asistente para la instalación &#40;la instalación&#41;</span><span class="sxs-lookup"><span data-stu-id="68991-114">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](../../database-engine/install-windows/upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
