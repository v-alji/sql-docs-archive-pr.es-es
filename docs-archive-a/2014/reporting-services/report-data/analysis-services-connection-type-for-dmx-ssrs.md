---
title: Tipo de conexión de Analysis Services para DMX (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], DMX
- Data Mining Prediction [Reporting Services]
- query view [Reporting Services]
- DMX [Reporting Services]
- design view [Reporting Services]
- data mining [Reporting Services]
- passing parameters [Reporting Services]
ms.assetid: 2de825e9-6d8a-4128-add0-da15dc6cea3e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c6d2c689689cde5c6c5ef4ffa8ab5c0e8737078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662601"
---
# <a name="analysis-services-connection-type-for-dmx-ssrs"></a><span data-ttu-id="b622d-102">Tipo de conexión de Analysis Services para DMX (SSRS)</span><span class="sxs-lookup"><span data-stu-id="b622d-102">Analysis Services Connection Type for DMX (SSRS)</span></span>
  <span data-ttu-id="b622d-103">Cuando se crea un conjunto de datos usando un origen de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], el Diseñador de informes muestra el diseñador de consultas de expresiones multidimensionales (MDX) si detecta un cubo válido.</span><span class="sxs-lookup"><span data-stu-id="b622d-103">When you create a dataset using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data source, Report Designer displays the Multidimensional Expression (MDX) query designer if it detects a valid cube.</span></span> <span data-ttu-id="b622d-104">Si no se detecta ningún cubo pero está disponible un modelo de minería de datos, el Diseñador de informes muestra el diseñador de consultas de extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="b622d-104">If no cube is detected, but a data mining model is available, Report Designer displays the Data Mining Extensions (DMX) query designer.</span></span> <span data-ttu-id="b622d-105">Para cambiar entre los diseñadores MDX y DMX, haga clic en el botón **Tipo de comando DMX** (![Cambiar a la vista del lenguaje de consultas DMX](../media/rsqdicon-commandtypedmx.gif "Cambio a la vista del lenguaje de consultas DMX")) en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b622d-105">To switch between the MDX and DMX designers, click the **Command Type DMX** (![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")) button on the toolbar.</span></span> <span data-ttu-id="b622d-106">Use el diseñador de consultas DMX para crear interactivamente una consulta DMX con elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="b622d-106">Use the DMX Query Designer to interactively build a DMX query using graphical elements.</span></span> <span data-ttu-id="b622d-107">Para utilizar el Diseñador de consultas DMX, el origen de datos que especifique debe tener previamente un modelo de minería de datos que aporte los datos.</span><span class="sxs-lookup"><span data-stu-id="b622d-107">To use DMX Query Designer, the data source that you specify must already have a data mining model that provides the data.</span></span> <span data-ttu-id="b622d-108">Los resultados de la consulta se convierten en un conjunto de filas planas que se utilizará en el informe.</span><span class="sxs-lookup"><span data-stu-id="b622d-108">Query results are converted to a flattened rowset for use in the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b622d-109">Debe entrenar el modelo antes de diseñar el informe.</span><span class="sxs-lookup"><span data-stu-id="b622d-109">You must train your model before designing your report.</span></span> <span data-ttu-id="b622d-110">Para obtener más información, vea [Soluciones de minería de datos](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="b622d-110">For more information, see [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="design-mode"></a><span data-ttu-id="b622d-111">Modo de diseño</span><span class="sxs-lookup"><span data-stu-id="b622d-111">Design Mode</span></span>  
 <span data-ttu-id="b622d-112">El diseñador de consultas DMX se abre en modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="b622d-112">The DMX query designer opens in Design mode.</span></span> <span data-ttu-id="b622d-113">El modo de diseño incluye una superficie de diseño gráfica que se utiliza para seleccionar un modelo de minería de datos individual, así como una tabla de entrada y una cuadrícula que se utiliza para especificar la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="b622d-113">Design mode includes a graphical design surface used for selecting a single data mining model and input table, and a grid used for specifying the prediction query.</span></span> <span data-ttu-id="b622d-114">Existen otros dos modos en el diseñador de consultas DMX: modo de consulta y modo de resultados.</span><span class="sxs-lookup"><span data-stu-id="b622d-114">There are two other modes in DMX query designer: Query mode and Result mode.</span></span> <span data-ttu-id="b622d-115">En el modo de consulta, la cuadrícula del modo de diseño se sustituye por un panel de consulta, que se puede utilizar para escribir consultas DMX.</span><span class="sxs-lookup"><span data-stu-id="b622d-115">In Query mode, the grid from Design mode is replaced with a Query pane, which you can use to type DMX queries.</span></span> <span data-ttu-id="b622d-116">En el modo de resultados, el conjunto de resultados devuelto por la consulta aparece en una cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="b622d-116">In Result mode, the result set returned by the query appears in a data grid.</span></span>  
  
 <span data-ttu-id="b622d-117">Para cambiar de modo en el diseñador de consultas DMX, haga clic con el botón derecho en la superficie de diseño de la consulta y seleccione **Diseño**, **Consulta**o **Resultado**.</span><span class="sxs-lookup"><span data-stu-id="b622d-117">To change modes for the DMX query designer, right-click on the query design surface and select **Design**, **Query**, or **Result**.</span></span> <span data-ttu-id="b622d-118">Para más información, vea [Interfaz de usuario del Diseñador de consultas DMX de Analysis Services](analysis-services-dmx-query-designer-user-interface.md) y [Recuperar datos de un modelo de minería de datos &#40;DMX&#41; &#40;SSRS&#41;](retrieve-data-from-a-data-mining-model-dmx-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b622d-118">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md) and [Retrieve Data from a Data Mining Model &#40;DMX&#41; &#40;SSRS&#41;](retrieve-data-from-a-data-mining-model-dmx-ssrs.md).</span></span>  
  
## <a name="designing-a-prediction-query"></a><span data-ttu-id="b622d-119">Diseñar una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="b622d-119">Designing a Prediction Query</span></span>  
 <span data-ttu-id="b622d-120">El panel Diseño de consulta del modo de diseño contiene dos ventanas: **Modelo de minería de datos** y **Seleccionar tabla(s) de entrada**.</span><span class="sxs-lookup"><span data-stu-id="b622d-120">The Query Design pane of the Design mode contains two windows: **Mining Model** and **Select Input Table**.</span></span> <span data-ttu-id="b622d-121">Use la ventana **Modelo de minería de datos** para seleccionar el modelo de minería de datos que va a utilizar en la consulta.</span><span class="sxs-lookup"><span data-stu-id="b622d-121">Use the **Mining Model** window to select the mining model to use in your query.</span></span> <span data-ttu-id="b622d-122">Use la ventana **Seleccionar tabla(s) de entrada** para seleccionar la tabla en la que se basarán las predicciones.</span><span class="sxs-lookup"><span data-stu-id="b622d-122">Use the **Select Input Table** window to select the table on which to base your predictions.</span></span> <span data-ttu-id="b622d-123">Si quiere usar una consulta singleton en lugar de una tabla de entrada, haga clic con el botón derecho en el panel Diseño de consulta y elija **Consulta singleton**.</span><span class="sxs-lookup"><span data-stu-id="b622d-123">If you want to use a singleton query instead of an input table, right-click in the Query Design pane and select **Singleton Query**.</span></span> <span data-ttu-id="b622d-124">Una ventana **Entrada de consulta singleton** reemplaza a la ventana **Seleccionar tabla(s) de entrada** .</span><span class="sxs-lookup"><span data-stu-id="b622d-124">The **Select Input Table** window is replaced with a **Singleton Query Input** window.</span></span>  
  
 <span data-ttu-id="b622d-125">En el modo de diseño, arrastre los campos desde las ventanas **Modelo de minería de datos** y **Seleccionar tabla(s) de entrada** hasta la columna **Campo** del panel Cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="b622d-125">In Design mode, drag fields from the **Mining Model** and **Select Input Table** windows to the **Field** column in the Grid pane.</span></span> <span data-ttu-id="b622d-126">También puede rellenar las columnas restantes para especificar un alias, mostrar el campo en los resultados, agrupar campos y especificar un operador para restringir el valor del campo a un criterio o argumento determinado.</span><span class="sxs-lookup"><span data-stu-id="b622d-126">You can also fill in the remaining columns to specify an alias, to show the field in the results, to group fields together, and to specify an operator to restrict the field value to a given criteria or argument.</span></span> <span data-ttu-id="b622d-127">Si está en el modo de consulta, genere la consulta DMX arrastrando los campos al panel Consulta.</span><span class="sxs-lookup"><span data-stu-id="b622d-127">If you are in Query mode, build the DMX query by dragging fields to the Query pane.</span></span>  
  
## <a name="using-parameters"></a><span data-ttu-id="b622d-128">Usar parámetros</span><span class="sxs-lookup"><span data-stu-id="b622d-128">Using Parameters</span></span>  
 <span data-ttu-id="b622d-129">Puede pasar los parámetros del informe a un parámetro de la consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="b622d-129">You can pass report parameters to a DMX query parameter.</span></span> <span data-ttu-id="b622d-130">Para hacerlo, agregue un parámetro a la consulta DMX, defina los parámetros de la consulta en el cuadro de diálogo **Parámetros de la consulta** y, a continuación, modifique los parámetros del informe asociados.</span><span class="sxs-lookup"><span data-stu-id="b622d-130">To do this, you must add a parameter to your DMX query, define the query parameters in the **Query Parameters** dialog box, and then modify the associated report parameters.</span></span> <span data-ttu-id="b622d-131">Para definir un parámetro de consulta, haga clic en el botón **Parámetros de consulta** (![Icono del cuadro de diálogo Parámetros de consulta](../media/iconqueryparameter.gif "Icono del cuadro de diálogo Parámetros de consulta")) en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b622d-131">To define a query parameter, click the **Query Parameters** (![Icon for the Query Parameters dialog box](../media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")) button on the toolbar.</span></span> <span data-ttu-id="b622d-132">Para ver instrucciones sobre cómo definir parámetros en una consulta DMX, consulte [Definir parámetros en el diseñador de consultas MDX para Analysis Services &#40;Generador de informes y SSRS&#41;](define-parameters-in-the-mdx-query-designer-for-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b622d-132">To view instructions about defining parameters in a DMX query, see [Define Parameters in the MDX Query Designer for Analysis Services &#40;Report Builder and SSRS&#41;](define-parameters-in-the-mdx-query-designer-for-analysis-services.md).</span></span>  
  
 <span data-ttu-id="b622d-133">Para más información sobre cómo administrar la relación entre los parámetros de consulta y los parámetros de informe, vea [Asociar un parámetro de consulta a un parámetro de informe &#40;Generador de informes y SSRS&#41;](associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b622d-133">For more information about how to manage the relationship between report parameters and query parameters, see [Associate a Query Parameter with a Report Parameter &#40;Report Builder and SSRS&#41;](associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="b622d-134">Para más información sobre parámetros, vea [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b622d-134">For more information about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b622d-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b622d-135">See Also</span></span>  
 <span data-ttu-id="b622d-136">[Soluciones de minería de datos](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions) </span><span class="sxs-lookup"><span data-stu-id="b622d-136">[Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions) </span></span>  
 <span data-ttu-id="b622d-137">[Herramientas de diseño de consultas en Diseñador de informes SQL Server Data Tools &#40;SSRS&#41;](query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b622d-137">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](query-design-tools-ssrs.md) </span></span>  
 [<span data-ttu-id="b622d-138">Data Connections, Data Sources, and Connection Strings in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b622d-138">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  