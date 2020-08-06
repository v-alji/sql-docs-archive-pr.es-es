---
title: Compatibilidad con versiones anteriores de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- installing Analysis Services, backward compatibility
- backward compatibility [Analysis Services]
- compatibility [Analysis Services]
- Analysis Services, backward compatibility
- upgrading Analysis Services
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
ms.assetid: 618b6c3a-e20d-47a9-b2c6-6d848dfba05a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44a5296bfbd2bae746eb9936d416fd696de16cb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670210"
---
# <a name="analysis-services-backward-compatibility"></a><span data-ttu-id="18d85-102">Compatibilidad con versiones anteriores de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="18d85-102">Analysis Services Backward Compatibility</span></span>
  <span data-ttu-id="18d85-103">En los temas de esta sección se describen los cambios de comportamiento entre las versiones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18d85-103">The topics in this section describe the changes in behavior between versions of  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18d85-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="18d85-104">In This Section</span></span>  
  
|<span data-ttu-id="18d85-105">Temas</span><span class="sxs-lookup"><span data-stu-id="18d85-105">Topics</span></span>|<span data-ttu-id="18d85-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="18d85-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18d85-107">Características en desuso de Analysis Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="18d85-107">Deprecated Analysis Services Features in SQL Server 2014</span></span>](deprecated-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="18d85-108">Describe las características que se han conservado en la versión actual para mantener la compatibilidad con versiones anteriores, pero que se quitarán en una futura versión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18d85-108">Describes features that have been retained in the current version to maintain backward compatibility,  but which will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="18d85-109">Funcionalidad de Analysis Services no incluida en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="18d85-109">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>](discontinued-analysis-services-functionality-in-sql-server-2014.md)|<span data-ttu-id="18d85-110">Describe características que existían en versiones anteriores de  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] pero que se han quitado en versiones posteriores desde entonces.</span><span class="sxs-lookup"><span data-stu-id="18d85-110">Describes features that existed in earlier versions of  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] but that have since been removed in later versions.</span></span>|  
|[<span data-ttu-id="18d85-111">Cambios recientes en las características de Analysis Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="18d85-111">Breaking Changes to Analysis Services Features in SQL Server 2014</span></span>](breaking-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="18d85-112">Describe los cambios de código introducidos en esta versión de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que podrían afectar a un modelo, a las aplicaciones personalizadas o a los scripts creados en versiones anteriores del software.</span><span class="sxs-lookup"><span data-stu-id="18d85-112">Describes code changes introduced in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that could potentially break a model or custom applications or script created in previous versions of the software .</span></span>|  
|[<span data-ttu-id="18d85-113">Cambios de comportamiento en las características de Analysis Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="18d85-113">Behavior Changes to Analysis Services Features in SQL Server 2014</span></span>](behavior-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="18d85-114">Describe las características existentes que tienen comportamientos diferentes en esta versión de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18d85-114">Describes existing features that have different behaviors in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="18d85-115">Algunos ejemplos comunes son el cambio de un valor predeterminado a un valor nuevo o diferente, impidiendo una operación o configuración permitida previamente, o bien introduciendo un requisito para revisar manualmente o reemplazar una opción o configuración que se pierda durante la actualización.</span><span class="sxs-lookup"><span data-stu-id="18d85-115">Common examples include changing a default to a new or different value, disallowing a previously allowable operation or configuration, or a introducing a requirement to manually revise or replace a setting or configuration that is lost during upgrade.</span></span><br /> <span data-ttu-id="18d85-116">.</span><span class="sxs-lookup"><span data-stu-id="18d85-116">.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18d85-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18d85-117">See Also</span></span>  
 <span data-ttu-id="18d85-118">[Novedades de Analysis Services y Business Intelligence](what-s-new-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="18d85-118">[What's New in Analysis Services and Business Intelligence](what-s-new-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="18d85-119">Actualizar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="18d85-119">Upgrade Analysis Services</span></span>](../database-engine/install-windows/upgrade-analysis-services.md)  
  
  
