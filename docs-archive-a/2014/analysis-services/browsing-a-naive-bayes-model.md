---
title: Examinar un modelo Bayes Naive | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9160b48-3beb-439c-9694-f084e1afa625
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3b0d18cd74e71f1ef18bffd6b0998e0b326e887a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670104"
---
# <a name="browsing-a-naive-bayes-model"></a><span data-ttu-id="08f6b-102">Examinar un modelo Bayes naive</span><span class="sxs-lookup"><span data-stu-id="08f6b-102">Browsing a Naive Bayes Model</span></span>
  <span data-ttu-id="08f6b-103">Al abrir un modelo Bayes naive con **examinar**, el modelo se muestra en un visor interactivo con cuatro paneles diferentes.</span><span class="sxs-lookup"><span data-stu-id="08f6b-103">When you open a Naïve Bayes model using **Browse**, the model is displayed in an interactive viewer with four different panes.</span></span> <span data-ttu-id="08f6b-104">El visor se usa para explorar las correlaciones y obtener información sobre el modelo y los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="08f6b-104">Use the viewer to explore correlations, and get information about the model and the underlying data.</span></span>  
  
-   [<span data-ttu-id="08f6b-105">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="08f6b-105">Dependency Network</span></span>](#bkmk_DepNet)  
  
-   [<span data-ttu-id="08f6b-106">Perfiles del atributo</span><span class="sxs-lookup"><span data-stu-id="08f6b-106">Attribute Profiles</span></span>](#bkmk_AttProf)  
  
-   [<span data-ttu-id="08f6b-107">Características del atributo</span><span class="sxs-lookup"><span data-stu-id="08f6b-107">Attribute Characteristics</span></span>](#bkmk_AttChar)  
  
-   [<span data-ttu-id="08f6b-108">Distinción del atributo</span><span class="sxs-lookup"><span data-stu-id="08f6b-108">Attribute Discrimination</span></span>](#bkmk_AttDisc)  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="08f6b-109">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="08f6b-109">Explore the Model</span></span>  
 <span data-ttu-id="08f6b-110">El visor tiene por objeto ayudarle a explorar la interacción entre los atributos de entrada y los atributos de salida (las entradas y variables dependientes) que se detectaron mediante el modelo Bayes naive de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08f6b-110">The purpose of the viewer is to help you explore the interaction between input and output attributes (inputs and dependent variables) that were discovered by the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes model.</span></span>  
  
 <span data-ttu-id="08f6b-111">Si desea experimentar con el visor Bayes de Naive, use el asistente [para clasificar &#40;complementos de minería de datos para el Asistente para&#41;de Excel](classify-wizard-data-mining-add-ins-for-excel.md) en la cinta de opciones minería de datos, haga clic en la opción **avanzadas** y cambie el algoritmo para que use el algoritmo Bayes Naive.</span><span class="sxs-lookup"><span data-stu-id="08f6b-111">If you want to experiment with the Naïve Bayes viewer, use the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard in the Data Mining ribbon, click the **Advanced** option, and change the algorithm to use the Naïve Bayes algorithm</span></span>  
  
 <span data-ttu-id="08f6b-112">En estos ejemplos, usamos los datos de origen en el libro de ejemplo y agrupamos la columna **ingresos anuales**en cinco grupos de ingresos, de **muy bajo** a **muy alto**.</span><span class="sxs-lookup"><span data-stu-id="08f6b-112">For these examples, we used the Source data in the sample workbook, and grouped the column, **Yearly Income**, into five income groups, from **Very Low** to **Very High**.</span></span> <span data-ttu-id="08f6b-113">Posteriormente, el modelo Bayes naive analiza los factores en correlación con cada categoría de ingresos.</span><span class="sxs-lookup"><span data-stu-id="08f6b-113">The Naïve Bayes model then analyzed the factors correlated with each income category.</span></span>  
  
###  <a name="dependency-network"></a><a name="bkmk_DepNet"></a><span data-ttu-id="08f6b-114">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="08f6b-114">Dependency Network</span></span>  
 <span data-ttu-id="08f6b-115">La primera ventana que se va a usar es la **red de dependencias**.</span><span class="sxs-lookup"><span data-stu-id="08f6b-115">The first window you'll use is the **Dependency Network**.</span></span> <span data-ttu-id="08f6b-116">Muestra de un solo vistazo las entradas que están estrechamente correlacionadas con el resultado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="08f6b-116">It shows you at a glance which inputs are closely correlated to the selected outcome.</span></span>  
  
 <span data-ttu-id="08f6b-117">![red de dependencias en visor Bayes naive](media/dm13-nb.gif "red de dependencias en visor Bayes naive")</span><span class="sxs-lookup"><span data-stu-id="08f6b-117">![dependency network in Naive Bayes viewer](media/dm13-nb.gif "dependency network in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="08f6b-118">Explorar la red de dependencias</span><span class="sxs-lookup"><span data-stu-id="08f6b-118">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="08f6b-119">En primer lugar, haga clic en el resultado de destino, **yearly Income**, que se representa como un nodo en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="08f6b-119">First, click the target outcome, **Yearly Income**, which is represented as a node in the graph.</span></span>  
  
     <span data-ttu-id="08f6b-120">Los nodos resaltados que rodean la variable de destino son los que se correlacionan estadísticamente con este resultado.</span><span class="sxs-lookup"><span data-stu-id="08f6b-120">The highlighted nodes surrounding the target variable are those that are statistically correlated with this outcome.</span></span> <span data-ttu-id="08f6b-121">Use la leyenda en la parte inferior del visor para entender la naturaleza de la relación.</span><span class="sxs-lookup"><span data-stu-id="08f6b-121">Use the legend at the bottom of the viewer to understand the nature of the relationship.</span></span>  
  
2.  <span data-ttu-id="08f6b-122">Haga clic en el control deslizante a la izquierda del visor y arrástrelo hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="08f6b-122">Click the slider at the left of the viewer and drag it downward.</span></span>  
  
     <span data-ttu-id="08f6b-123">Este control filtra las variables independientes según la importancia de las dependencias.</span><span class="sxs-lookup"><span data-stu-id="08f6b-123">This control filters the independent variables, based on the strengths of the dependencies.</span></span> <span data-ttu-id="08f6b-124">Cuando desplace el control deslizante hacia abajo, solamente permanecen en el gráfico los vínculos de mayor importancia.</span><span class="sxs-lookup"><span data-stu-id="08f6b-124">When you drag the slider down, only the strongest links remain in the graph.</span></span>  
  
3.  <span data-ttu-id="08f6b-125">Después de filtrar el gráfico, haga clic en el botón **copiar vista del gráfico**.</span><span class="sxs-lookup"><span data-stu-id="08f6b-125">After you have filtered the graph, click the button, **Copy Graph View**.</span></span> <span data-ttu-id="08f6b-126">A continuación, seleccione una hoja de cálculo de Excel y presione Ctrl+V.</span><span class="sxs-lookup"><span data-stu-id="08f6b-126">Then select a worksheet in Excel, and press Ctrl+V.</span></span>  
  
     <span data-ttu-id="08f6b-127">Esta opción copia la vista seleccionada, incluidos los filtros y lo que se ha resaltado.</span><span class="sxs-lookup"><span data-stu-id="08f6b-127">This option copies the view that you have selected, including filters and highlighting.</span></span>  
  
 [<span data-ttu-id="08f6b-128">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="08f6b-128">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-profiles"></a><a name="bkmk_AttProf"></a><span data-ttu-id="08f6b-129">Perfiles de atributo</span><span class="sxs-lookup"><span data-stu-id="08f6b-129">Attribute Profiles</span></span>  
 <span data-ttu-id="08f6b-130">Las ventanas **perfiles de atributo** le ofrecen una indicación visual de cómo todas las demás variables están relacionadas con los resultados individuales.</span><span class="sxs-lookup"><span data-stu-id="08f6b-130">The **Attribute Profiles** windows gives you a visual indication of how all other variables are related to the individual outcomes.</span></span>  
  
##### <a name="explore-the-profiles"></a><span data-ttu-id="08f6b-131">Explorar los perfiles</span><span class="sxs-lookup"><span data-stu-id="08f6b-131">Explore the profiles</span></span>  
  
1.  <span data-ttu-id="08f6b-132">Para ocultar algunos valores de forma que pueda comparar los resultados con mayor facilidad, haga clic en el encabezado de columna y arrástrelo a otra columna.</span><span class="sxs-lookup"><span data-stu-id="08f6b-132">To hide some values so that you can more easily compare outcomes, click the column heading and drag it under another column.</span></span>  
  
     <span data-ttu-id="08f6b-133">![perfiles del atributo en visor Bayes naive](media/dm13-nb-attprof.gif "perfiles del atributo en visor Bayes naive")</span><span class="sxs-lookup"><span data-stu-id="08f6b-133">![attribute profiles in Naive Bayes viewer](media/dm13-nb-attprof.gif "attribute profiles in Naive Bayes viewer")</span></span>  
  
2.  <span data-ttu-id="08f6b-134">Haga clic en cualquier celda para ver la distribución de los valores de la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="08f6b-134">Click in any cell to view the distribution of values in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="08f6b-135">Como los atributos asociados a los distintos resultados se muestran visualmente, es fácil identificar correlaciones interesantes, como por ejemplo, la forma en que se distribuyen los ingresos por región.</span><span class="sxs-lookup"><span data-stu-id="08f6b-135">Because the attributes associated with different outcomes are displayed visually, it is easy to spot interesting correlations, such as how incomes are distributed by region.</span></span>  
  
3.  <span data-ttu-id="08f6b-136">Para obtener los datos subyacentes de esta vista, haga clic en **copiar a Excel**.</span><span class="sxs-lookup"><span data-stu-id="08f6b-136">To obtain the data underlying this view, click **Copy to Excel**.</span></span> <span data-ttu-id="08f6b-137">Una tabla se genera en una hoja de cálculo nueva que muestra las correlaciones entre atributos y resultados individuales.</span><span class="sxs-lookup"><span data-stu-id="08f6b-137">A table is generated in a new worksheet that shows the correlations among individual attributes and outcomes.</span></span> <span data-ttu-id="08f6b-138">En esta tabla de Excel puede ocultar o filtrar columnas fácilmente.</span><span class="sxs-lookup"><span data-stu-id="08f6b-138">In this Excel table you can easily hide or filter columns.</span></span>  
  
 [<span data-ttu-id="08f6b-139">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="08f6b-139">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-characteristics"></a><a name="bkmk_AttChar"></a><span data-ttu-id="08f6b-140">Características del atributo</span><span class="sxs-lookup"><span data-stu-id="08f6b-140">Attribute Characteristics</span></span>  
 <span data-ttu-id="08f6b-141">La vista **características del atributo** resulta útil para el examen exhaustivo de una variable de resultado determinada y los factores que contribuyen.</span><span class="sxs-lookup"><span data-stu-id="08f6b-141">The **Attribute Characteristics** view is useful for in-depth examination of a particular outcome variable and the contributing factors.</span></span>  
  
 <span data-ttu-id="08f6b-142">![características del atributo en visor Bayes naive](media/dm13-nb-viewer.gif "características del atributo en visor Bayes naive")</span><span class="sxs-lookup"><span data-stu-id="08f6b-142">![attribute characteristics in Naive Bayes viewer](media/dm13-nb-viewer.gif "attribute characteristics in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-attribute-characteristics"></a><span data-ttu-id="08f6b-143">Explorar las características del atributo</span><span class="sxs-lookup"><span data-stu-id="08f6b-143">Explore the attribute characteristics</span></span>  
  
1.  <span data-ttu-id="08f6b-144">Haga clic en **valor** y seleccione un elemento del **valor**.</span><span class="sxs-lookup"><span data-stu-id="08f6b-144">Click **Value** and select an item from the **Value**.</span></span>  
  
     <span data-ttu-id="08f6b-145">Al seleccionar un resultado de destino, el gráfico se actualiza para mostrar los factores más estrechamente asociados a los resultados, ordenados según su importancia.</span><span class="sxs-lookup"><span data-stu-id="08f6b-145">As you select a target outcome, the graph updates to show the factors that are most strongly associated with the outcome, sorted by importance.</span></span>  
  
     <span data-ttu-id="08f6b-146">Tenga en cuenta que si crea un modelo mediante la opción [analizar influenciadores clave &#40;herramientas de análisis de tabla para Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) , puede crear modelos que tengan más de un atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="08f6b-146">Note that if you create a model using the [Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) option, you can create models that have more than one predictable attribute.</span></span> <span data-ttu-id="08f6b-147">Sin embargo, el resto de los asistentes de los complementos de minería de datos le limitarán a un solo atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="08f6b-147">However, all other wizards in the Data Mining add-ins limit you to one predictable attribute.</span></span>  
  
2.  <span data-ttu-id="08f6b-148">Haga clic en **copiar a Excel** para crear una tabla, en una nueva hoja de cálculo, donde se muestran las puntuaciones de todos los atributos relacionados con el resultado de destino seleccionado.</span><span class="sxs-lookup"><span data-stu-id="08f6b-148">Click **Copy to Excel** to create a table, in a new worksheet, listing the scores for all attributes that are related to the selected target outcome.</span></span>  
  
 [<span data-ttu-id="08f6b-149">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="08f6b-149">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-discrimination"></a><a name="bkmk_AttDisc"></a><span data-ttu-id="08f6b-150">Distinción de atributos</span><span class="sxs-lookup"><span data-stu-id="08f6b-150">Attribute Discrimination</span></span>  
 <span data-ttu-id="08f6b-151">La vista de **distinción de atributos** ayuda a comparar dos resultados, o un resultado frente a todos los demás resultados.</span><span class="sxs-lookup"><span data-stu-id="08f6b-151">The **Attribute Discrimination** view helps compare two outcomes, or one outcome vs. all other outcomes.</span></span>  
  
 <span data-ttu-id="08f6b-152">![distinción del atributo en visor Bayes naive](media/dm13-nb-attdisc.gif "distinción del atributo en visor Bayes naive")</span><span class="sxs-lookup"><span data-stu-id="08f6b-152">![attribute discrimination in Naive Bayes viewer](media/dm13-nb-attdisc.gif "attribute discrimination in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-attribute-discrimination"></a><span data-ttu-id="08f6b-153">Explorar la distinción del atributo</span><span class="sxs-lookup"><span data-stu-id="08f6b-153">Explore attribute discrimination</span></span>  
  
1.  <span data-ttu-id="08f6b-154">Use los controles, **valor 1** y **valor 2**para seleccionar los resultados que desea comparar.</span><span class="sxs-lookup"><span data-stu-id="08f6b-154">Use the controls, **Value 1** and **Value 2**, to select the outcomes that you want to compare.</span></span>  
  
     <span data-ttu-id="08f6b-155">Por ejemplo, en este modelo había algunos atributos interesantes en el grupo de ingresos bajos, por lo que elegimos el grupo de ingresos más bajo en la primera lista desplegable y elegimos **todos los demás Estados** en la segunda lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="08f6b-155">For example, in this model there were some interesting attributes in the low income group, so we chose the lowest income group in the first dropdown list, and chose **All other states** in the second dropdown list.</span></span>  
  
     <span data-ttu-id="08f6b-156">Los atributos se ordenan por orden de importancia (se calcula en función de los datos de entrenamiento).</span><span class="sxs-lookup"><span data-stu-id="08f6b-156">The attributes are sorted by order of importance (calculated based on the training data).</span></span> <span data-ttu-id="08f6b-157">Por tanto, el empleo es el factor más estrechamente correlacionado con los ingresos (al menos para el primer grupo de destino).</span><span class="sxs-lookup"><span data-stu-id="08f6b-157">Therefore, occupation is the factor most closely correlated with income (for this target group, at least),</span></span>  
  
     <span data-ttu-id="08f6b-158">Para ver las figuras exactas, haga clic en la barra coloreada y vea la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="08f6b-158">To see the exact figures, click the colored bar and view the **Mining Legend**.</span></span>  
  
2.  <span data-ttu-id="08f6b-159">Observe que los ingresos más bajos también se correlacionan con la región Europa.</span><span class="sxs-lookup"><span data-stu-id="08f6b-159">Note that lower incomes are also correlated with the Europe region.</span></span>  
  
     <span data-ttu-id="08f6b-160">El modelo de Bayes naive no admite la obtención de detalles; sin embargo, si quisiera investigar los casos asociados a este grupo de resultados, puede utilizar una consulta.</span><span class="sxs-lookup"><span data-stu-id="08f6b-160">The Naïve Bayes model does not support drilldown; however, if you wanted to investigate the cases associated with this outcome group, you could use a query.</span></span> <span data-ttu-id="08f6b-161">Para obtener información sobre las consultas de este tipo de modelo, vea [ejemplos de consultas del modelo Bayes Naive](data-mining/naive-bayes-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="08f6b-161">For information about queries on this type of model, see [Naive Bayes Model Query Examples](data-mining/naive-bayes-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="08f6b-162">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="08f6b-162">Back To Top</span></span>](#BKMK_Tabs)  
  
## <a name="see-also"></a><span data-ttu-id="08f6b-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08f6b-163">See Also</span></span>  
 [<span data-ttu-id="08f6b-164">Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="08f6b-164">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
