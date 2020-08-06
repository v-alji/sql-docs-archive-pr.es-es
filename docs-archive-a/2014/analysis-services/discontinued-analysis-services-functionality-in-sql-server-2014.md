---
title: Funcionalidad de Analysis Services no incluida en SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, backward compatibility
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
- discontinued functionality [Analysis Services]
- unsupported features [Analysis Services]
ms.assetid: 39406be1-9819-4629-9c29-b32fb20bab2e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5414344eb65c907593c9077ee2ba5610b8b397c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677277"
---
# <a name="discontinued-analysis-services-functionality-in-sql-server-2014"></a><span data-ttu-id="40103-102">Funcionalidad de Analysis Services no incluida en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="40103-102">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>
  <span data-ttu-id="40103-103">Este tema describe las características de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que ya no están disponibles en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40103-103">This topic describes [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] features that are no longer available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
## <a name="discontinued-features-in-sssql14"></a><span data-ttu-id="40103-104">Características no incluidas en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40103-104">Discontinued Features in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
  
|<span data-ttu-id="40103-105">Category</span><span class="sxs-lookup"><span data-stu-id="40103-105">Category</span></span>|<span data-ttu-id="40103-106">Característica desusada</span><span class="sxs-lookup"><span data-stu-id="40103-106">Deprecated feature</span></span>|<span data-ttu-id="40103-107">Sustituta</span><span class="sxs-lookup"><span data-stu-id="40103-107">Replacement</span></span>|  
|--------------|------------------------|-----------------|  
|<span data-ttu-id="40103-108">Cubos locales</span><span class="sxs-lookup"><span data-stu-id="40103-108">Local cubes</span></span>|<span data-ttu-id="40103-109">Propiedad de la cadena de conexión InsertInto</span><span class="sxs-lookup"><span data-stu-id="40103-109">InsertInto connection string property</span></span>|<span data-ttu-id="40103-110">La sintaxis original de la cadena de conexión para rellenar cubos locales se sustituye por la instrucción Create Global Cube.</span><span class="sxs-lookup"><span data-stu-id="40103-110">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="40103-111">Para obtener más información, vea [Create global Cube Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="40103-111">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="40103-112">Cubos locales</span><span class="sxs-lookup"><span data-stu-id="40103-112">Local cubes</span></span>|<span data-ttu-id="40103-113">Propiedad de la cadena de conexión CreateCube</span><span class="sxs-lookup"><span data-stu-id="40103-113">CreateCube connection string property</span></span>|<span data-ttu-id="40103-114">La sintaxis original de la cadena de conexión para rellenar cubos locales se sustituye por la instrucción Create Global Cube.</span><span class="sxs-lookup"><span data-stu-id="40103-114">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="40103-115">Para obtener más información, vea [Create global Cube Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="40103-115">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="40103-116">Minería de datos</span><span class="sxs-lookup"><span data-stu-id="40103-116">Data Mining</span></span>|<span data-ttu-id="40103-117">SQL Server 2000 PMML</span><span class="sxs-lookup"><span data-stu-id="40103-117">SQL Server 2000 PMML</span></span>|<span data-ttu-id="40103-118">La característica de SQL Server 2000 PMML creaba una forma de PMML que tenía extensiones propias para admitir las características únicas que proporcionan los algoritmos de minería de datos que no estaban disponibles en la especificación PMML.</span><span class="sxs-lookup"><span data-stu-id="40103-118">The SQL Server 2000 PMML feature produced a form of PMML that had proprietary extensions to support unique features provided by Data Mining algorithms that were not available in the PMML specification.</span></span> <span data-ttu-id="40103-119">En SQL Server 2005, Analysis Services actualizó la característica PMML al estándar PMML 2.1 más reciente.</span><span class="sxs-lookup"><span data-stu-id="40103-119">In SQL Server 2005, Analysis Services updated the PMML feature to the newer PMML 2.1 standard.</span></span> <span data-ttu-id="40103-120">Como resultado, las extensiones propias agregadas en SQL Server 2000 ya no se necesitan, aunque todavía se admiten en esta versión.</span><span class="sxs-lookup"><span data-stu-id="40103-120">As a result, the proprietary extensions added in SQL Server 2000 are no longer needed, although they are still supported in this release.</span></span>|  
|<span data-ttu-id="40103-121">Instrucción MDX</span><span class="sxs-lookup"><span data-stu-id="40103-121">MDX Statement</span></span>|<span data-ttu-id="40103-122">Instrucción Create Action</span><span class="sxs-lookup"><span data-stu-id="40103-122">Create Action statement</span></span>|<span data-ttu-id="40103-123">Esta instrucción se incluye por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="40103-123">This statement is included for backwards compatibility.</span></span> <span data-ttu-id="40103-124">Se reemplaza por el objeto Action.</span><span class="sxs-lookup"><span data-stu-id="40103-124">It is replaced by the Action object.</span></span> <span data-ttu-id="40103-125">Para obtener más información sobre cómo crear acciones en las versiones recientes de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , vea [acciones &#40;Analysis Services-&#41;de datos multidimensionales ](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="40103-125">For more information about how to create actions in recent versions of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="discontinued-features-in-previous-releases"></a><span data-ttu-id="40103-126">Características descontinuadas en versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="40103-126">Discontinued Features in Previous Releases</span></span>  
 <span data-ttu-id="40103-127">El Asistente para la migración, que se usaba para migrar las bases de datos de SQL Server 2000  Analysis Services a versiones más recientes, se deja de usar porque SQL Server 2000 ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="40103-127">Migration Wizard, used to migrate SQL Server 2000 Analysis Services databases to newer versions, is discontinued because SQL Server 2000 is no longer supported.</span></span>  
  
 <span data-ttu-id="40103-128">La biblioteca Objetos de ayuda para la toma de decisiones (DSO) que proporcionaba compatibilidad con las bases de datos de SQL Server 2000 Analysis Services también ha dejado de usarse y ya no forma parte de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40103-128">Decision Support Objects (DSO) library that provided compatibility with SQL Server 2000 Analysis Services databases is also discontinued and no longer part of SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40103-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40103-129">See Also</span></span>  
 [<span data-ttu-id="40103-130">Compatibilidad con versiones anteriores Analysis Services</span><span class="sxs-lookup"><span data-stu-id="40103-130">Analysis Services Backward Compatibility</span></span>](analysis-services-backward-compatibility.md)  
  
  
