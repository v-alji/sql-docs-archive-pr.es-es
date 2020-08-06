---
title: Analizar influenciadores clave (herramientas de análisis de tabla para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- key influencers
- factor analysis
ms.assetid: 54d7b4ce-7b79-407a-985c-aa655ad19280
author: minewiskan
ms.author: owend
ms.openlocfilehash: f60eb5144059b0976d52eec2329f27553132146c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670178"
---
# <a name="analyze-key-influencers-table-analysis-tools-for-excel"></a><span data-ttu-id="c825a-102">Analizar influenciadores clave (Herramientas de análisis de tabla para Excel)</span><span class="sxs-lookup"><span data-stu-id="c825a-102">Analyze Key Influencers (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="c825a-103">![Botón Analizar influenciadores clave de la cinta](media/tat-aki.gif "Botón Analizar influenciadores clave de la cinta")</span><span class="sxs-lookup"><span data-stu-id="c825a-103">![Analyze Key Influencers button in ribbon](media/tat-aki.gif "Analyze Key Influencers button in ribbon")</span></span>  
  
 <span data-ttu-id="c825a-104">Con la herramienta **analizar influenciadores clave** , elija una columna que contenga un resultado de destino y el algoritmo determinará qué factores tenían la influencia más fuerte en el resultado.</span><span class="sxs-lookup"><span data-stu-id="c825a-104">With the **Analyze Key Influencers** tool, you choose a column that contains a target outcome, and the algorithm determines which factors had the strongest influence on the outcome.</span></span>  
  
 <span data-ttu-id="c825a-105">La herramienta crea nuevas tablas de datos que informan sobre los factores asociados con cada resultado e ilustra gráficamente la probabilidad de la relación.</span><span class="sxs-lookup"><span data-stu-id="c825a-105">The tool creates new data tables that report the factors associated with each outcome and graphically displays the probability of the relationship.</span></span> <span data-ttu-id="c825a-106">Puede filtrar las tablas por factores y resultados diferentes para explorar los resultados de forma más minuciosa.</span><span class="sxs-lookup"><span data-stu-id="c825a-106">You can filter the tables by different factors and outcomes to explore the results in more depth.</span></span>  
  
 <span data-ttu-id="c825a-107">También puede seleccionar un par de resultados posibles y compararlos.</span><span class="sxs-lookup"><span data-stu-id="c825a-107">You can also select a pair of possible outcomes and compare them.</span></span> <span data-ttu-id="c825a-108">Por ejemplo, puede comparar grupos de consumidores para determinar los posibles factores que influyen en la toma de decisiones.</span><span class="sxs-lookup"><span data-stu-id="c825a-108">For example, you might compare different groups of consumers to determine possible decision-making factors.</span></span>  
  
## <a name="using-the-analyze-key-influencers-tool"></a><span data-ttu-id="c825a-109">Usar la herramienta Analizar influenciadores clave</span><span class="sxs-lookup"><span data-stu-id="c825a-109">Using the Analyze Key Influencers Tool</span></span>  
  
1.  <span data-ttu-id="c825a-110">Abra una tabla de datos de Excel.</span><span class="sxs-lookup"><span data-stu-id="c825a-110">Open an Excel data table.</span></span>  
  
2.  <span data-ttu-id="c825a-111">En **herramientas de tabla**, en la cinta de opciones **analizar** , haga clic en **analizar influenciadores clave.**</span><span class="sxs-lookup"><span data-stu-id="c825a-111">In **Table Tools**, on the **Analyze** ribbon, click **Analyze Key Influencers.**</span></span>  
  
3.  <span data-ttu-id="c825a-112">Seleccione la columna individual que constituye el objetivo del análisis.</span><span class="sxs-lookup"><span data-stu-id="c825a-112">Select the single column that is the target of analysis.</span></span>  
  
4.  <span data-ttu-id="c825a-113">Opcionalmente, haga clic en **elegir las columnas que se van a usar para el análisis**.</span><span class="sxs-lookup"><span data-stu-id="c825a-113">Optionally, click **Choose columns to be used for analysis**.</span></span> <span data-ttu-id="c825a-114">En el cuadro de diálogo **selección avanzada de columnas** , elija las columnas que tengan más probabilidades de contener datos relevantes.</span><span class="sxs-lookup"><span data-stu-id="c825a-114">In the **Advanced Columns Selection** dialog box, choose the columns that are most likely to contain relevant data.</span></span> <span data-ttu-id="c825a-115">Para mejorar el rendimiento y la precisión, anule la selección de las columnas que contengan identificadores o nombres, que no son importantes para el análisis de patrones.</span><span class="sxs-lookup"><span data-stu-id="c825a-115">To improve performance and accuracy, deselect columns such as ID or name that are unimportant for pattern analysis.</span></span> <span data-ttu-id="c825a-116">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **selección avanzada de columnas** .</span><span class="sxs-lookup"><span data-stu-id="c825a-116">Click **OK** to close the **Advanced Columns Selection** dialog box.</span></span>  
  
5.  <span data-ttu-id="c825a-117">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c825a-117">Click **Run**.</span></span>  
  
     <span data-ttu-id="c825a-118">La herramienta **analizar influenciadores clave** realiza un análisis de los datos para determinar la configuración óptima y establece todos los parámetros de forma automática.</span><span class="sxs-lookup"><span data-stu-id="c825a-118">The **Analyze Key Influencers** tool conducts an analysis of the data to determine the optimum settings, and sets all parameters automatically.</span></span>  
  
6.  <span data-ttu-id="c825a-119">Si no se detecta ningún modelo, el asistente crea una nueva hoja de cálculo que contiene una descripción del problema.</span><span class="sxs-lookup"><span data-stu-id="c825a-119">If no patterns were detected, the wizard creates a new worksheet that contains a description of the problem.</span></span>  
  
7.  <span data-ttu-id="c825a-120">Si se detectan patrones, el asistente crea un informe en una nueva hoja de cálculo que muestra los patrones.</span><span class="sxs-lookup"><span data-stu-id="c825a-120">If patterns are detected, the wizard creates a report on a new worksheet that shows the patterns.</span></span> <span data-ttu-id="c825a-121">El informe se denomina \*\*influenciadores clave para \<column> \*\*.</span><span class="sxs-lookup"><span data-stu-id="c825a-121">The report is named **Key Influencers for \<column>**.</span></span> <span data-ttu-id="c825a-122">Puede personalizar el informe como se describe en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="c825a-122">You can customize the report as described in the following procedure.</span></span>  
  
#### <a name="create-a-custom-report"></a><span data-ttu-id="c825a-123">Creación de un informe personalizado</span><span class="sxs-lookup"><span data-stu-id="c825a-123">Create a custom report</span></span>  
  
1.  <span data-ttu-id="c825a-124">En el cuadro de diálogo **distinción basada en influenciadores clave** , elija los dos valores que desea comparar seleccionándolos en las listas desplegables **valor 1** y **valor 2** .</span><span class="sxs-lookup"><span data-stu-id="c825a-124">In the **Discrimination based on key influencers** dialog box, choose the two values that you want to compare by selecting them from the **Value 1** and **Value 2** dropdown lists.</span></span> <span data-ttu-id="c825a-125">Por ejemplo, puede comparar los compradores con los no compradores.</span><span class="sxs-lookup"><span data-stu-id="c825a-125">For example, you might compare buyers to non-buyers.</span></span>  
  
2.  <span data-ttu-id="c825a-126">Haga clic en **Agregar Informe**.</span><span class="sxs-lookup"><span data-stu-id="c825a-126">Click **Add Report**.</span></span>  
  
     <span data-ttu-id="c825a-127">El asistente crea una nueva hoja de cálculo y agrega una tabla por cada par de comparaciones de factores clave.</span><span class="sxs-lookup"><span data-stu-id="c825a-127">The wizard creates a new worksheet and adds a table for each pair of key factor comparisons.</span></span>  
  
3.  <span data-ttu-id="c825a-128">Cuando haya terminado de realizar comparaciones, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c825a-128">When you are done making comparisons, click **Close**.</span></span>  
  
## <a name="understanding-the-key-influencers-report"></a><span data-ttu-id="c825a-129">Descripción del informe de influenciadores clave</span><span class="sxs-lookup"><span data-stu-id="c825a-129">Understanding the Key Influencers Report</span></span>  
 <span data-ttu-id="c825a-130">Una vez creado el modelo de datos, la herramienta **analizar influenciadores clave** crea informes que le ayudan a explorar y a comparar los influenciadores clave.</span><span class="sxs-lookup"><span data-stu-id="c825a-130">After the data model has been created, the **Analyze Key Influencers** tool creates reports that help you explore and compare key influencers.</span></span>  
  
-   <span data-ttu-id="c825a-131">El informe del lado izquierdo es el que se ha generado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c825a-131">The report on the left side is the one generated by default.</span></span> <span data-ttu-id="c825a-132">Muestra los predictores más eficaces de la columna de resultados (la variable dependiente).</span><span class="sxs-lookup"><span data-stu-id="c825a-132">It shows the strongest predictors of the outcome column (the dependent variable).</span></span>  
  
-   <span data-ttu-id="c825a-133">El informe del lado derecho es opcional y puede crearlo comparando dos valores específicos de resultados.</span><span class="sxs-lookup"><span data-stu-id="c825a-133">The report on the right side is optional, which you can create by comparing two specific outcome values.</span></span> <span data-ttu-id="c825a-134">Este informe compara a los compradores y a los no compradores.</span><span class="sxs-lookup"><span data-stu-id="c825a-134">This report compares buyers and non-buyers.</span></span>  
  
-   <span data-ttu-id="c825a-135">Tenga en cuenta que se agrega una nueva hoja de cálculo para cada informe que cree.</span><span class="sxs-lookup"><span data-stu-id="c825a-135">Note that a new worksheet is added for each report that you create.</span></span> <span data-ttu-id="c825a-136">Puede mover las tablas una vez creadas; las colocamos en paralelo para la comparación.</span><span class="sxs-lookup"><span data-stu-id="c825a-136">You can move the tables after they are created; we placed them side by side for comparison.</span></span>  
  
 <span data-ttu-id="c825a-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span><span class="sxs-lookup"><span data-stu-id="c825a-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span></span>  
  
 <span data-ttu-id="c825a-138">**Impacto relativo**</span><span class="sxs-lookup"><span data-stu-id="c825a-138">**Relative Impact**</span></span>  
 <span data-ttu-id="c825a-139">La barra sombreada en el primer informe indica la solidez de la asociación de este atributo con el resultado.</span><span class="sxs-lookup"><span data-stu-id="c825a-139">The shaded bar in the first report indicates the strength of the association of this attribute with the outcome.</span></span>  
  
 <span data-ttu-id="c825a-140">La longitud de la barra indica la probabilidad de que el factor contribuya al resultado; por tanto, cuanto más larga sea la barra sombreada, más fuerte es la asociación.</span><span class="sxs-lookup"><span data-stu-id="c825a-140">The length of the bar indicates the probability that the factor contributes to the outcome; therefore, the longer the shaded bar, the stronger the association.</span></span>  
  
 <span data-ttu-id="c825a-141">**Favorece**</span><span class="sxs-lookup"><span data-stu-id="c825a-141">**Favors**</span></span>  
 <span data-ttu-id="c825a-142">En el segundo informe, los valores de destino que se comparan se muestran en dos columnas, con los factores relacionados enumerados en orden de confianza descendente.</span><span class="sxs-lookup"><span data-stu-id="c825a-142">In the second report, the target values that you compare are listed in two columns, with the related factors listed in order of descending confidence.</span></span>  
  
-   <span data-ttu-id="c825a-143">La barra **azul** muestra los atributos que contribuyen al resultado, "no" (= no adquirió).</span><span class="sxs-lookup"><span data-stu-id="c825a-143">The **blue** bar shows attributes contributing to the outcome, "No" (=did not purchase).</span></span>  
  
-   <span data-ttu-id="c825a-144">La barra **roja** muestra los atributos que contribuyen al resultado, "sí" (= compra una bicicleta).</span><span class="sxs-lookup"><span data-stu-id="c825a-144">The **red** bar shows attributes contributing to the outcome, "Yes" (=purchased a bike).</span></span>  
  
 <span data-ttu-id="c825a-145">Los colores de la barra de sombreado son arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="c825a-145">The colors in the shading bar are arbitrary.</span></span> <span data-ttu-id="c825a-146">Puede cambiar estos colores estableciendo las opciones para el diseño de la tabla en Excel.</span><span class="sxs-lookup"><span data-stu-id="c825a-146">You can change these colors by setting the options for table design in Excel.</span></span>  
  
 <span data-ttu-id="c825a-147">En un informe que contrasta dos valores, el segundo informe clasifica los influenciadores clave según el impacto que tienen en los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="c825a-147">In a report that contrasts two values, the second report ranks the key influencers by the amount of impact on the target values.</span></span>  
  
 <span data-ttu-id="c825a-148">Puesto que todos los gráficos se basan en las tablas de Excel, puede filtrar y ordenar para centrarse en resultados o factores específicos.</span><span class="sxs-lookup"><span data-stu-id="c825a-148">Because all the charts are based on Excel tables, you can filter and sort to focus on specific factors or outcomes.</span></span>  
  
## <a name="more-about-the-analyze-key-influencers-tool"></a><span data-ttu-id="c825a-149">Más información acerca de la herramienta Analizar influenciadores clave</span><span class="sxs-lookup"><span data-stu-id="c825a-149">More About the Analyze Key Influencers Tool</span></span>  
 <span data-ttu-id="c825a-150">Cuando la herramienta **analizar influenciadores clave** analiza los datos, hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c825a-150">When the **Analyze Key Influencers** tool analyzes your data, it does the following:</span></span>  
  
-   <span data-ttu-id="c825a-151">Crea una estructura de datos que almacena información clave sobre la distribución de los datos.</span><span class="sxs-lookup"><span data-stu-id="c825a-151">Creates a data structure that stores key information about the distribution of your data.</span></span>  
  
-   <span data-ttu-id="c825a-152">Crea un modelo mediante el algoritmo Bayes Naive de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c825a-152">Creates a model using the Microsoft Naïve Bayes algorithm.</span></span>  
  
-   <span data-ttu-id="c825a-153">Crea predicciones que ponen en correlación cada columna de datos con el resultado especificado.</span><span class="sxs-lookup"><span data-stu-id="c825a-153">Creates predictions that correlates each column of data with the specified outcome.</span></span>  
  
-   <span data-ttu-id="c825a-154">Utiliza la puntuación de confianza para cada una de las predicciones a fin de identificar los factores que son más influyentes al generar el resultado pretendido.</span><span class="sxs-lookup"><span data-stu-id="c825a-154">Uses the confidence score for each of the predictions to identify the factors that are the most influential in producing the targeted outcome.</span></span>  
  
-   <span data-ttu-id="c825a-155">Crea un informe que describe los influenciadores clave, ordenados por las puntuaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="c825a-155">Creates a report describing the key influencers, ordered by confidence scores.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="c825a-156">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c825a-156">Requirements</span></span>  
 <span data-ttu-id="c825a-157">Si la columna de destino contiene valores numéricos continuos, la herramienta segmenta automáticamente los valores numéricos en grupos.</span><span class="sxs-lookup"><span data-stu-id="c825a-157">If the target column contains continuous numeric values, the tool automatically segments the numeric values into groups.</span></span> <span data-ttu-id="c825a-158">Estas agrupaciones representan clústeres de casos que tienen características similares.</span><span class="sxs-lookup"><span data-stu-id="c825a-158">These groupings represent clusters of cases that have similar characteristics.</span></span> <span data-ttu-id="c825a-159">Sin embargo, los valores numéricos podrían no estar divididos en grupos fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="c825a-159">However, numeric values might not be divided into user-friendly groups.</span></span> <span data-ttu-id="c825a-160">Por ejemplo, el informe puede contener una agrupación como " \< 12,85701", mientras que los usuarios de informes normalmente desean ver las agrupaciones que utilizan números enteros, como 10-19, 20-29, etc.</span><span class="sxs-lookup"><span data-stu-id="c825a-160">For example, the report might contain a grouping such as "\<12.85701", whereas report users typically like to see groupings that use whole numbers, such as 10-19, 20-29, and so on.</span></span>  
  
 <span data-ttu-id="c825a-161">Si desea agrupar los datos numéricos de otra forma, debe segmentar los datos de la forma deseada antes de crear el análisis.</span><span class="sxs-lookup"><span data-stu-id="c825a-161">If you want to group numeric data in a different way, you must segment the data the way you want before creating the analysis.</span></span> <span data-ttu-id="c825a-162">Por ejemplo, puede usar la herramienta cambiar [etiquetas](relabel-sql-server-data-mining-add-ins.md) del cliente de minería de datos para Excel para crear una nueva etiqueta de agrupación en una columna independiente y, a continuación, utilizar solo esa nueva columna en el análisis.</span><span class="sxs-lookup"><span data-stu-id="c825a-162">For example, you can use the [Relabel](relabel-sql-server-data-mining-add-ins.md) tool in the Data Mining Client for Excel to create a new grouping label in a separate column, and then use only that new column in analysis.</span></span>  
  
### <a name="related-tools"></a><span data-ttu-id="c825a-163">Herramientas relacionadas</span><span class="sxs-lookup"><span data-stu-id="c825a-163">Related Tools</span></span>  
 <span data-ttu-id="c825a-164">La cinta de opciones **minería de datos** proporciona herramientas más avanzadas, incluida la capacidad de personalizar modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c825a-164">The **Data Mining** ribbon provides more advanced tools, including the ability to customize data mining models</span></span>  
  
 <span data-ttu-id="c825a-165">Si guarda el modelo mediante la herramienta **analizar influenciadores clave** , puede usar el cliente de minería de datos para examinar el modelo y explorar las relaciones con más detalle.</span><span class="sxs-lookup"><span data-stu-id="c825a-165">If you save your model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="c825a-166">Para obtener más información, vea [examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c825a-166">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span> <span data-ttu-id="c825a-167">También puede usar Microsoft Office Visio para crear gráficos y diagramas que muestren las relaciones como clúster o como redes de dependencias.</span><span class="sxs-lookup"><span data-stu-id="c825a-167">You can also use Microsoft Office Visio to create charts and diagrams that display the relationships as cluster or as dependency networks.</span></span> <span data-ttu-id="c825a-168">Para obtener más información, vea [solucionar problemas de diagramas de minería de datos de Visio &#40;SQL Server complementos de minería de datos&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c825a-168">For more information, see [Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c825a-169">Los modelos creados cuando se usan las Herramientas de análisis de tabla se eliminan al cerrar la hoja de cálculo o terminar la conexión con el servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c825a-169">The models that are created when you use the Table Analysis Tools are deleted when you close your worksheet or terminate the connection with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="c825a-170">Por tanto, solo puede examinar los modelos mientras la conexión permanezca abierta.</span><span class="sxs-lookup"><span data-stu-id="c825a-170">Therefore, you can only browse the models as long as the connection remains open.</span></span> <span data-ttu-id="c825a-171">No puede representar los modelos en Visio si cierra la conexión o cierra la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="c825a-171">You cannot render the models in Visio if you close the connection or close the worksheet.</span></span>  
  
 <span data-ttu-id="c825a-172">Para obtener más información acerca del algoritmo usado por la herramienta **analizar influenciadores clave** , vea el tema sobre el algoritmo Bayes Naive de Microsoft en libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c825a-172">For more information about the algorithm used by the **Analyze Key Influencers** tool, see "Microsoft Naïve Bayes Algorithm" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c825a-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c825a-173">See Also</span></span>  
 <span data-ttu-id="c825a-174">[Herramientas de análisis de tabla para Excel](table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="c825a-174">[Table Analysis Tools for Excel](table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="c825a-175">Crear un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c825a-175">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
