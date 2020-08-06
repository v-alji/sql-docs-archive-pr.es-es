---
title: Compatibilidad con versiones anteriores de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- SSRS, backward compatibility
- SQL Server Reporting Services, backward compatibility
- backward compatibility [Reporting Services]
ms.assetid: 675b0e0e-cfee-4790-9675-80fc3ea6d30f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7203740ba7f52dfc2cd3793a20fed9fecf5f9468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747448"
---
# <a name="reporting-services-backward-compatibility"></a><span data-ttu-id="36d0c-102">Compatibilidad con versiones anteriores de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="36d0c-102">Reporting Services Backward Compatibility</span></span>
  <span data-ttu-id="36d0c-103">En esta sección se describen los cambios de comportamiento entre las versiones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36d0c-103">This section describes changes in behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="36d0c-104">Incluye características que ya no están disponibles o cuya eliminación está prevista para una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="36d0c-104">It covers features that are no longer available or are scheduled to be removed in a future release.</span></span> <span data-ttu-id="36d0c-105">También se describen cambios fundamentales en el producto que afectan a aplicaciones personalizadas que incluyen funcionalidad de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36d0c-105">It also describes fundamental changes to the product that are known to break a custom application that includes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36d0c-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="36d0c-106">In This Section</span></span>  
  
|<span data-ttu-id="36d0c-107">Tema</span><span class="sxs-lookup"><span data-stu-id="36d0c-107">Topic</span></span>|<span data-ttu-id="36d0c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="36d0c-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="36d0c-109">Funcionalidad de SQL Server Reporting Services descontinuada en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="36d0c-109">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)|<span data-ttu-id="36d0c-110">Describe características que existían en versiones anteriores de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pero que se han quitado en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="36d0c-110">Describes features that existed in earlier versions of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] but that have been removed in later versions.</span></span>|  
|[<span data-ttu-id="36d0c-111">Características desusadas de SQL Server Reporting Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="36d0c-111">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>](deprecated-features-in-sql-server-reporting-services-ssrs.md)|<span data-ttu-id="36d0c-112">Describe las características que existen en esta versión de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] por compatibilidad con versiones anteriores, pero que se quitarán en una futura versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36d0c-112">Describes features that exist this release of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] for backward compatibility, but which will be removed in a future version of SQL Server.</span></span>|  
|[<span data-ttu-id="36d0c-113">Cambios importantes de SQL Server Reporting Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="36d0c-113">Breaking Changes in SQL Server Reporting Services in SQL Server 2014</span></span>](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="36d0c-114">Describe los problemas que se pueden encontrar cuando se actualiza [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36d0c-114">Describes issues that you might encounter when you upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="36d0c-115">Cambios de comportamiento de SQL Server Reporting Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="36d0c-115">Behavior Changes to SQL Server Reporting Services  in SQL Server 2014</span></span>](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="36d0c-116">Describe las características que se han cambiado en [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36d0c-116">Describes features that have changed in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36d0c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36d0c-117">See Also</span></span>  
 <span data-ttu-id="36d0c-118">[Compatibilidad con versiones anteriores](../../2014/getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="36d0c-118">[Backward Compatibility](../../2014/getting-started/backward-compatibility.md) </span></span>  
 [<span data-ttu-id="36d0c-119">Compatibilidad con versiones anteriores Analysis Services</span><span class="sxs-lookup"><span data-stu-id="36d0c-119">Analysis Services Backward Compatibility</span></span>](../../2014/analysis-services/analysis-services-backward-compatibility.md)  
  
  
