---
title: Cómo ver un informe del Asesor de actualizaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- viewing reports
- Upgrade Advisor [SQL Server], reports
- SQL Server Upgrade Advisor, reports
- reports [Upgrade Advisor], viewing
ms.assetid: d13b38af-0ac3-4030-83cd-e7d7825dd09f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e6df35b869186a601458889c348153093ccbce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676828"
---
# <a name="how-to-view-an-upgrade-advisor-report"></a><span data-ttu-id="8ac4b-102">Procedimientos: Ver un informe del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="8ac4b-102">How to: View an Upgrade Advisor Report</span></span>
  <span data-ttu-id="8ac4b-103">El Asesor de actualizaciones crea informes de cada componente que haya seleccionado para su análisis.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-103">Upgrade Advisor creates reports for each component that you select to analyze.</span></span> <span data-ttu-id="8ac4b-104">En este tema se describe cómo ver un informe del Asesor de actualizaciones desde la página de inicio de este último.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-104">This topic describes how to view an Upgrade Advisor report from the Upgrade Advisor start page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8ac4b-105">El visor de informes carga archivos basados en nombres de archivo estándar.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-105">The report viewer loads files based on standard file names.</span></span> <span data-ttu-id="8ac4b-106">Si se ha cambiado el nombre los archivos, el visor de informes no los cargará.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-106">If the files have been renamed, the report viewer will not load them.</span></span>  
  
### <a name="to-view-a-report"></a><span data-ttu-id="8ac4b-107">Para ver un informe</span><span class="sxs-lookup"><span data-stu-id="8ac4b-107">To view a report</span></span>  
  
1.  <span data-ttu-id="8ac4b-108">Haga clic en **Inicio**, **todos los programas**, **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]** y, a continuación, haga clic en \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Asesor de actualizaciones\*\*.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-108">Click **Start**, click **All Programs**, click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**, and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
2.  <span data-ttu-id="8ac4b-109">En la página de inicio del Asesor de actualizaciones, haga clic en **iniciar el visor de informes del Asesor de actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
3.  <span data-ttu-id="8ac4b-110">Para seleccionar un informe en la ubicación predeterminada en su equipo:</span><span class="sxs-lookup"><span data-stu-id="8ac4b-110">To select a report in the default location on your computer:</span></span>  
  
    1.  <span data-ttu-id="8ac4b-111">En la lista **servidor** , seleccione un servidor.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-111">In the **Server** list, select a server.</span></span>  
  
    2.  <span data-ttu-id="8ac4b-112">En la lista **instancia o componente** , seleccione una combinación componente o componente/instancia.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-112">In the **Instance or component** list, select a component or component/instance combination.</span></span>  
  
     <span data-ttu-id="8ac4b-113">Para seleccionar un informe en otra ubicación:</span><span class="sxs-lookup"><span data-stu-id="8ac4b-113">To select a report at another location:</span></span>  
  
    1.  <span data-ttu-id="8ac4b-114">Haga clic en el vínculo **abrir Informe** .</span><span class="sxs-lookup"><span data-stu-id="8ac4b-114">Click the **Open Report** link.</span></span>  
  
    2.  <span data-ttu-id="8ac4b-115">Vaya a la ubicación del informe y haga doble clic en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-115">Browse to the report location and then double-click the XML file.</span></span>  
  
     <span data-ttu-id="8ac4b-116">El Asesor de actualizaciones almacena hasta cinco informes del análisis anterior como historial.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-116">Upgrade Advisor stores up to five reports from previous analysis as history.</span></span> <span data-ttu-id="8ac4b-117">Para ver estos informes, haga clic en el cuadro de lista desplegable **Informe** y seleccione un informe.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-117">To view these reports, click the **Report** drop-down list box, and select a report.</span></span> <span data-ttu-id="8ac4b-118">Los informes se enumeran según la marca de tiempo establecida durante su generación.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-118">The reports are listed by the timestamp from when they were generated.</span></span>  
  
     <span data-ttu-id="8ac4b-119">El informe contiene los detalles siguientes para todos los problemas detectados:</span><span class="sxs-lookup"><span data-stu-id="8ac4b-119">The report contains the following details for all detected issues:</span></span>  
  
    -   <span data-ttu-id="8ac4b-120">**Importancia**, que indica la importancia de corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-120">**Importance**, which indicates how important it is to fix the issue.</span></span>  
  
    -   <span data-ttu-id="8ac4b-121">**Cuándo solucionarlo**, que indica si se debe corregir el problema antes o después de actualizar a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , antes o después de migrar la aplicación o los datos, o en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-121">**When to fix**, which indicates if you should (or must) fix the issue before or after upgrading to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], before or after migrating the application or data, or anytime.</span></span>  
  
    -   <span data-ttu-id="8ac4b-122">Breve descripción del problema.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-122">A brief description of the issue.</span></span>  
  
4.  <span data-ttu-id="8ac4b-123">Si el informe contiene más de 20 elementos, haga clic en la flecha verde hacia la derecha situada en la parte superior o en parte inferior del informe para ver el conjunto siguiente de elementos.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-123">If the report contains more than 20 items, click the green forward arrow at the top or bottom of the report to view the next set of items.</span></span> <span data-ttu-id="8ac4b-124">Haga clic en la flecha verde hacia la izquierda para ver los 20 elementos anteriores.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-124">Click the green back button to view the previous 20 items.</span></span>  
  
5.  <span data-ttu-id="8ac4b-125">Para ordenar el informe, haga clic en uno de los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-125">To sort the report, click a column heading.</span></span>  
  
6.  <span data-ttu-id="8ac4b-126">Para ver los detalles de un elemento en particular, haga clic en dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-126">To view details for a specific item, click the item.</span></span> <span data-ttu-id="8ac4b-127">Aparecerá una descripción del problema, junto con una serie de opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="8ac4b-127">A description of the issue appears, along with additional options:</span></span>  
  
    -   <span data-ttu-id="8ac4b-128">Para ver los objetos en los que se encontró este problema, haga clic en **Mostrar objetos afectados**.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-128">To view the objects where this issue was found, click **Show affected objects**.</span></span>  
  
    -   <span data-ttu-id="8ac4b-129">Para ver la ayuda del problema, haga clic en **más información sobre este problema y cómo resolverlo**.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-129">To view help for the issue, click **Tell me more about this issue and how to resolve it**.</span></span>  
  
    -   <span data-ttu-id="8ac4b-130">Para marcar el problema como resuelto, lo que oculta el problema al volver a ver el informe, seleccione **este problema**se ha resuelto.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-130">To mark the issue as resolved, which hides the issue when you view the report again, select **This issue has been resolved**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ac4b-131">Es posible que el informe contenga elementos correspondientes a problemas indetectables.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-131">The report may contain an item for undetectable issues.</span></span> <span data-ttu-id="8ac4b-132">Se trata de problemas que no se pueden detectar o que generarían demasiados resultados positivos falsos.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-132">These are issues that cannot be detected or that would generate too many false-positive results.</span></span> <span data-ttu-id="8ac4b-133">Haga clic en el vínculo **más información sobre este problema y cómo resolverlo** para ver una lista de problemas no detectables del componente.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-133">Click the **Tell me more about this issue and how to resolve it** link to see a list of undetectable issues for the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac4b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ac4b-134">See Also</span></span>  
 <span data-ttu-id="8ac4b-135">[Cómo: exportar informes](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="8ac4b-135">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="8ac4b-136">[Cómo: ejecutar el Asistente para análisis del Asesor de actualizaciones](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="8ac4b-136">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="8ac4b-137">[Resolver problemas de actualización](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8ac4b-137">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="8ac4b-138">[Temas de procedimientos del Asesor de actualizaciones](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="8ac4b-138">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="8ac4b-139">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="8ac4b-139">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
