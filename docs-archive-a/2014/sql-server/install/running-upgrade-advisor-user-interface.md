---
title: Ejecutar el asesor de actualizaciones (interfaz de usuario) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Report Viewer
- Upgrade Advisor [SQL Server], running
- launching Upgrade Advisor
- Upgrade Advisor Analysis Wizard
- starting Upgrade Advisor
- SQL Server Upgrade Advisor, running
ms.assetid: 7f47c9b3-88d3-43d6-837e-f157b49a55ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a5e47ef2b8183823dff884e114adc420e371adf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677381"
---
# <a name="running-upgrade-advisor-user-interface"></a><span data-ttu-id="92a9f-102">Ejecutar el Asesor de actualizaciones (interfaz de usuario)</span><span class="sxs-lookup"><span data-stu-id="92a9f-102">Running Upgrade Advisor (User Interface)</span></span>
  <span data-ttu-id="92a9f-103">Puede ejecutar el Asesor de actualizaciones para analizar componentes locales o remotos durante la planeación de la actualización.</span><span class="sxs-lookup"><span data-stu-id="92a9f-103">You can run Upgrade Advisor to analyze local or remote components during upgrade planning.</span></span> <span data-ttu-id="92a9f-104">El asesor de actualizaciones genera un informe para cada componente e instancia que se analiza.</span><span class="sxs-lookup"><span data-stu-id="92a9f-104">Upgrade Advisor produces a report for each component and instance that is analyzed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="92a9f-105">El Asesor de actualizaciones no analiza instancias remotas de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92a9f-105">Upgrade Advisor does not analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="92a9f-106">Para analizar una instancia de [!INCLUDE[ssRS](../../includes/ssrs.md)], el Asesor de actualizaciones se debe instalar en el equipo donde esté instalado [!INCLUDE[ssRS](../../includes/ssrs.md)].</span><span class="sxs-lookup"><span data-stu-id="92a9f-106">To analyze an instance of [!INCLUDE[ssRS](../../includes/ssrs.md)], Upgrade Advisor must be installed on the computer where [!INCLUDE[ssRS](../../includes/ssrs.md)] is installed.</span></span>  
>   
>  <span data-ttu-id="92a9f-107">Para analizar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, debe tener [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalado e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="92a9f-107">To analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, you must have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] installed and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed on the same computer.</span></span>  
  
## <a name="running-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="92a9f-108">Ejecutar el Asistente para análisis del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="92a9f-108">Running the Upgrade Advisor Analysis Wizard</span></span>  
 <span data-ttu-id="92a9f-109">La ejecución del Asistente para análisis del Asesor de actualizaciones consta de seis pasos:</span><span class="sxs-lookup"><span data-stu-id="92a9f-109">Running the Upgrade Advisor Analysis Wizard has six steps:</span></span>  
  
1.  <span data-ttu-id="92a9f-110">Inicie el asistente desde la página de inicio del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="92a9f-110">Launch the wizard from the Upgrade Advisor start page.</span></span>  
  
2.  <span data-ttu-id="92a9f-111">Identifique el servidor y los componentes que desea analizar.</span><span class="sxs-lookup"><span data-stu-id="92a9f-111">Identify server and components to analyze.</span></span>  
  
3.  <span data-ttu-id="92a9f-112">Recopile información de autenticación.</span><span class="sxs-lookup"><span data-stu-id="92a9f-112">Gather authentication information.</span></span>  
  
4.  <span data-ttu-id="92a9f-113">Recopile los parámetros adicionales según el tipo de componente.</span><span class="sxs-lookup"><span data-stu-id="92a9f-113">Gather additional parameters based on component type.</span></span>  
  
5.  <span data-ttu-id="92a9f-114">Analice los componentes seleccionados.</span><span class="sxs-lookup"><span data-stu-id="92a9f-114">Analyze selected components.</span></span>  
  
6.  <span data-ttu-id="92a9f-115">Genere un informe de los problemas de la actualización.</span><span class="sxs-lookup"><span data-stu-id="92a9f-115">Generate report of upgrade issues.</span></span>  
  
 <span data-ttu-id="92a9f-116">Para obtener más información acerca del Asistente para análisis del Asesor de actualizaciones, vea [Cómo: ejecutar el Asistente para análisis del Asesor de actualizaciones](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="92a9f-116">For more information about the Upgrade Advisor Analysis Wizard, see [How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span></span>  
  
 <span data-ttu-id="92a9f-117">Para obtener información específica necesaria para cada paso, consulte referencia de la [interfaz de usuario del Asesor de actualizaciones](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="92a9f-117">For specific information that is required for each step, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
## <a name="running-the-upgrade-advisor-report-viewer"></a><span data-ttu-id="92a9f-118">Ejecutar el visor de informes del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="92a9f-118">Running the Upgrade Advisor Report Viewer</span></span>  
 <span data-ttu-id="92a9f-119">El Visor de informes del Asesor de actualizaciones se usa para visualizar informes generados por el Asistente para análisis del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="92a9f-119">You use the Upgrade Advisor Report Viewer to view reports generated by the Upgrade Advisor Analysis Wizard.</span></span> <span data-ttu-id="92a9f-120">Cuando se cargue el informe, podrá filtrar los componentes del mismo según los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="92a9f-120">When the report is loaded, you can filter the components of the report by the following factors:</span></span>  
  
-   <span data-ttu-id="92a9f-121">Todos los problemas</span><span class="sxs-lookup"><span data-stu-id="92a9f-121">All issues</span></span>  
  
-   <span data-ttu-id="92a9f-122">Todos los problemas de actualización</span><span class="sxs-lookup"><span data-stu-id="92a9f-122">All upgrade issues</span></span>  
  
-   <span data-ttu-id="92a9f-123">Problemas anteriores a la actualización</span><span class="sxs-lookup"><span data-stu-id="92a9f-123">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="92a9f-124">Todos los problemas de migración</span><span class="sxs-lookup"><span data-stu-id="92a9f-124">All migration issues</span></span>  
  
-   <span data-ttu-id="92a9f-125">Problemas resueltos</span><span class="sxs-lookup"><span data-stu-id="92a9f-125">Resolved issues</span></span>  
  
-   <span data-ttu-id="92a9f-126">Problemas sin resolver</span><span class="sxs-lookup"><span data-stu-id="92a9f-126">Unresolved issues</span></span>  
  
 <span data-ttu-id="92a9f-127">Para obtener instrucciones paso a paso relacionadas con el uso del visor de informes, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="92a9f-127">For step-by-step instructions for using the report viewer, see the following topics:</span></span>  
  
-   [<span data-ttu-id="92a9f-128">Procedimientos: Ver un informe del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="92a9f-128">How to: View an Upgrade Advisor Report</span></span>](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md)  
  
-   [<span data-ttu-id="92a9f-129">Procedimientos: Filtrar informes</span><span class="sxs-lookup"><span data-stu-id="92a9f-129">How to: Filter Reports</span></span>](../../../2014/sql-server/install/how-to-filter-reports.md)  
  
-   [<span data-ttu-id="92a9f-130">Procedimientos: Export Reports</span><span class="sxs-lookup"><span data-stu-id="92a9f-130">How to: Export Reports</span></span>](../../../2014/sql-server/install/how-to-export-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="92a9f-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92a9f-131">See Also</span></span>  
 <span data-ttu-id="92a9f-132">[Cómo: ejecutar el Asistente para análisis del Asesor de actualizaciones](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="92a9f-132">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="92a9f-133">[Referencia de la interfaz de usuario del Asesor de actualizaciones](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="92a9f-133">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 <span data-ttu-id="92a9f-134">[Resolver problemas de actualización](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="92a9f-134">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="92a9f-135">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="92a9f-135">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
