---
title: Analizar en Excel (pestaña explorador, diseñador de cubos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.datapane.f1
- sql12.asvs.ssms.analyzeinexcel.f1
ms.assetid: 890ed457-137e-44ac-9b2c-83344a1b8fc9
author: minewiskan
ms.author: owend
ms.openlocfilehash: b9fa27ae291d40b7f5637e3968438fcaec1de03d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670181"
---
# <a name="analyze-in-excel-browser-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="00a17-102">Analizar en Excel (pestaña Explorador de cubo del Diseñador de cubos) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="00a17-102">Analyze in Excel (Browser Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="00a17-103">**Analizar en Excel** proporciona al desarrollador de cubos un mecanismo para ver rápidamente cómo se mostraría un proyecto al usuario final.</span><span class="sxs-lookup"><span data-stu-id="00a17-103">**Analyze in Excel** provides the cube developer with a way to quickly review how a project would look to the end user.</span></span> <span data-ttu-id="00a17-104">La característica **Analizar en Excel** abre Microsoft Excel, crea una conexión de origen de datos con la base de datos del área de trabajo y agrega automáticamente una tabla dinámica a la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="00a17-104">The **Analyze in Excel** feature opens Microsoft Excel, creates a data source connection to the workspace database, and automatically adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="00a17-105">Esta característica reemplaza al control Web de Office que, en versiones anteriores, proporcionaba una tabla dinámica incrustada en la pestaña Explorador.</span><span class="sxs-lookup"><span data-stu-id="00a17-105">This feature replaces the Office Web Control that provided an embedded PivotTable in the Browser tab in previous releases.</span></span>  
  
 <span data-ttu-id="00a17-106">**Para ver los datos del cubo:**</span><span class="sxs-lookup"><span data-stu-id="00a17-106">**To view cube data:**</span></span>  
  
1.  <span data-ttu-id="00a17-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el Explorador de soluciones, haga doble clic en un cubo para abrirlo en el Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="00a17-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in Solution Explorer, double-click a cube to open it in Cube Designer.</span></span>  
  
2.  <span data-ttu-id="00a17-108">Haga clic en la pestaña **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="00a17-108">Click the **Browser** tab.</span></span>  
  
3.  <span data-ttu-id="00a17-109">Haga clic en **Volver a conectar** para validar la conexión.</span><span class="sxs-lookup"><span data-stu-id="00a17-109">Click **Reconnect** to validate the connection.</span></span>  
  
4.  <span data-ttu-id="00a17-110">Haga clic en el icono de Excel de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="00a17-110">Click the Excel icon in the menu bar.</span></span>  
  
5.  <span data-ttu-id="00a17-111">Cuando le pidan que habilite las conexiones de datos, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="00a17-111">When asked to enable data connections, click **Enable**.</span></span> <span data-ttu-id="00a17-112">Excel se abre a través la conexión de datos actual y agrega una tabla dinámica a la hoja de cálculo para que pueda empezar a examinar los datos.</span><span class="sxs-lookup"><span data-stu-id="00a17-112">Excel opens using the current data connection, adding a PivotTable to the worksheet so that you can begin browsing your data.</span></span>  
  
 <span data-ttu-id="00a17-113">Ahora puede generar una tabla dinámica de forma interactiva arrastrando medidas desde la tabla de hechos hasta el área de valores y agregando atributos de dimensión a las áreas de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="00a17-113">You can now build a PivotTable interactively by dragging measures from the fact table to the Values area, and dimension attributes to the Row and Column areas.</span></span> <span data-ttu-id="00a17-114">Si tiene jerarquías, agréguelas a las áreas de fila o de columna.</span><span class="sxs-lookup"><span data-stu-id="00a17-114">If you have hierarchies, add them to Rows or Column areas.</span></span> <span data-ttu-id="00a17-115">Puede recorrer la jerarquía hacia arriba o hacia abajo para examinar los datos de hechos en diferentes niveles.</span><span class="sxs-lookup"><span data-stu-id="00a17-115">You can roll up or drill down the hierarchy to browse fact data at different levels.</span></span>  
  
 <span data-ttu-id="00a17-116">Los objetos y los datos se ven en el contexto del usuario o el rol vigente y de la perspectiva.</span><span class="sxs-lookup"><span data-stu-id="00a17-116">Objects and data are viewed within the context of the effective user or role and perspective.</span></span> <span data-ttu-id="00a17-117">Con Excel, para conectarse al origen de datos cuando se ejecuta una consulta, se usan las credenciales del usuario actual, no las credenciales especificadas en la página **Información de suplantación** .</span><span class="sxs-lookup"><span data-stu-id="00a17-117">When using Excel, the credentials of the current user, not the credentials specified in the **Impersonation Information** page, are used to connect to the data source when a query is executed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00a17-118">Para usar la característica Analizar en Excel, Excel debe estar instalado en el mismo equipo que [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00a17-118">To use the Analyze in Excel feature, Excel must be installed on the same computer as [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="00a17-119">Si Excel no está instalado en el mismo equipo, puede usar Excel en otro equipo y conectarse al cubo como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="00a17-119">If Excel is not installed on the same computer, you can use Excel on another computer and connect to the cube as a data source.</span></span> <span data-ttu-id="00a17-120">A continuación, podrá agregar manualmente una tabla dinámica a la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="00a17-120">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="00a17-121">Los objetos del modelo (tablas, columnas, medidas y KPI) se incluyen como campos en la lista de campos de la tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="00a17-121">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
 <span data-ttu-id="00a17-122">Para obtener más información acerca de la característica **Analizar en Excel** , vea estos recursos:</span><span class="sxs-lookup"><span data-stu-id="00a17-122">For more information about the **Analyze in Excel** feature, see these resources:</span></span>  
  
 [<span data-ttu-id="00a17-123">Analizar en Excel &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="00a17-123">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="00a17-124">Analizar un modelo tabular en Excel &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="00a17-124">Analyze a Tabular Model in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-a-tabular-model-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="00a17-125">Examinar los datos y metadatos de un cubo</span><span class="sxs-lookup"><span data-stu-id="00a17-125">Browse data and metadata in Cube</span></span>](multidimensional-models/browse-data-and-metadata-in-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="00a17-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00a17-126">See Also</span></span>  
 <span data-ttu-id="00a17-127">[Explorador de cubos &#40;&#41; &#40;Analysis Services de datos multidimensionales&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="00a17-127">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="00a17-128">[Barra de herramientas &#40;pestaña explorador, diseñador de cubos&#41; &#40;Analysis Services-datos multidimensionales&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="00a17-128">[Toolbar &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="00a17-129">[Metadatos &#40;pestaña explorador, diseñador de cubos&#41; &#40;Analysis Services-datos multidimensionales&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="00a17-129">[Metadata &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="00a17-130">Consulta y filtro &#40;pestaña explorador, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="00a17-130">Query and Filter &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](query-filter-browser-cube-designer-analysis-services-multidimensional-data.md)  
  
  
