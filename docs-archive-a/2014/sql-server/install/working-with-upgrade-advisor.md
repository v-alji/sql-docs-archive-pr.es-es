---
title: Trabajar con el asesor de actualizaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], when to use
- SQL Server Upgrade Advisor, when to use
- when to use Upgrade Advisor
ms.assetid: 5f26a7b9-1ac2-442c-8316-87b078db3baf
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 75a16e57734493cdd7ac00e7bad3124eb7a99d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672369"
---
# <a name="working-with-upgrade-advisor"></a><span data-ttu-id="e56f0-102">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e56f0-102">Working with Upgrade Advisor</span></span>
  <span data-ttu-id="e56f0-103">Para asegurarse de que la actualización a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] se realice correctamente, el Asesor de actualizaciones proporciona una consola central que permite identificar los problemas que se deben tratar en las instalaciones de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e56f0-103">To help ensure that your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is successful, Upgrade Advisor provides a central console to identify issues to address in your installations before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="e56f0-104">Puede utilizar el Asesor de actualizaciones para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e56f0-104">You can use Upgrade Advisor to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="e56f0-105">Analizar los componentes de la versión anterior en servidores locales o remotos.</span><span class="sxs-lookup"><span data-stu-id="e56f0-105">Analyze previous version's components on local or remote servers.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e56f0-106">No es posible analizar instancias remotas de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e56f0-106">You cannot analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e56f0-107">Ver los resultados del análisis.</span><span class="sxs-lookup"><span data-stu-id="e56f0-107">View the results of the analysis.</span></span>  
  
 <span data-ttu-id="e56f0-108">El Asesor de actualizaciones incluye un analizador y un visor.</span><span class="sxs-lookup"><span data-stu-id="e56f0-108">Upgrade Advisor includes an analyzer and a viewer.</span></span> <span data-ttu-id="e56f0-109">El Asistente para análisis del Asesor de actualizaciones analizará aquellos componentes que seleccione.</span><span class="sxs-lookup"><span data-stu-id="e56f0-109">The Upgrade Advisor Analysis Wizard analyzes the components you select.</span></span> <span data-ttu-id="e56f0-110">A continuación, el analizador generará los informes personalizados sobre los problemas que debe resolver antes de poder actualizar a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e56f0-110">The analyzer then generates custom reports about issues that you must handle before you can upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="e56f0-111">Puede utilizar el Visor de informes del Asesor de actualizaciones para ver informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="e56f0-111">You use the Upgrade Advisor Report Viewer to view the custom reports.</span></span> <span data-ttu-id="e56f0-112">Para obtener más información sobre qué detecta el análisis del Asesor de actualizaciones, vea [resolver problemas de actualización](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e56f0-112">For more information about what Upgrade Advisor analysis detects, see [Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="e56f0-113">En los temas de esta sección se ofrece información general acerca de las funcionalidades del Asesor de actualizaciones, así como información acerca de cómo usar el Asesor de actualizaciones y los informes de éste.</span><span class="sxs-lookup"><span data-stu-id="e56f0-113">The topics in this section provide an overview of Upgrade Advisor functionality and information about how to use Upgrade Advisor and Upgrade Advisor reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e56f0-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e56f0-114">In This Section</span></span>  
  
|<span data-ttu-id="e56f0-115">Tema</span><span class="sxs-lookup"><span data-stu-id="e56f0-115">Topic</span></span>|<span data-ttu-id="e56f0-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e56f0-116">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e56f0-117">Información general sobre el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e56f0-117">Overview of Upgrade Advisor</span></span>](../../../2014/sql-server/install/overview-of-upgrade-advisor.md)|<span data-ttu-id="e56f0-118">Proporciona información general acerca del proceso de actualización, el Asistente para análisis del Asesor de actualizaciones y el Visor de informes del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="e56f0-118">Provides an overview of the upgrade process, the Upgrade Advisor Analysis Wizard, and the Upgrade Advisor Report Viewer.</span></span>|  
|[<span data-ttu-id="e56f0-119">Temas de procedimiento del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e56f0-119">Upgrade Advisor How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md)|<span data-ttu-id="e56f0-120">Proporciona instrucciones para llevar a cabo los procedimientos más comunes del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="e56f0-120">Provides instructions to perform common Upgrade Advisor procedures.</span></span>|  
|[<span data-ttu-id="e56f0-121">Referencia de la interfaz de usuario del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e56f0-121">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)|<span data-ttu-id="e56f0-122">Contiene temas que aparecen si presiona la tecla F1 o hace clic en **ayuda** en las páginas del Asistente para análisis del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="e56f0-122">Contains topics that appear if you press the F1 key or click **Help** on the Upgrade Advisor Analysis Wizard pages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e56f0-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e56f0-123">See Also</span></span>  
 <span data-ttu-id="e56f0-124">[Instalando el asesor de actualizaciones](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="e56f0-124">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="e56f0-125">Resolver problemas de la actualización</span><span class="sxs-lookup"><span data-stu-id="e56f0-125">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
