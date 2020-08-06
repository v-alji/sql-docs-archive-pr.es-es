---
title: Examinar un modelo de reglas de asociación | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining model, association
- mining models, viewing
- association [data mining]
ms.assetid: faffe208-7a64-4ec6-825f-ecbaa79caff7
author: minewiskan
ms.author: owend
ms.openlocfilehash: de5adbca264fff81b44424d865a2c8201a6fdfc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670092"
---
# <a name="browsing-an-association-rules-model"></a><span data-ttu-id="6ecca-102">Examinar un modelo de reglas de asociación</span><span class="sxs-lookup"><span data-stu-id="6ecca-102">Browsing an Association Rules Model</span></span>
  <span data-ttu-id="6ecca-103">Al abrir un modelo de asociación mediante **examinar**, el modelo se muestra en un visor interactivo, similar al visor de reglas de Asociación de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ecca-103">When you open an association model using **Browse**, the model is displayed in an interactive viewer, similar to the Association Rules Viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  <span data-ttu-id="6ecca-104">El visor le permite comprobar de un vistazo qué elementos estaban en correlación entre sí y muestra las reglas que puede utilizar para la predicción o para realizar recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="6ecca-104">The viewer lets you see at a glance which items were correlated with each other, and displays rules that you can use for prediction or making recommendations.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="6ecca-105">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="6ecca-105">Explore the Model</span></span>  
 <span data-ttu-id="6ecca-106">Al abrir un modelo de minería de datos que se creó mediante el [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo reglas de Asociación de, la ventana **examinar** incluye las siguientes vistas, cada una diseñada para que pueda explorar un aspecto diferente del modelo:</span><span class="sxs-lookup"><span data-stu-id="6ecca-106">When you open a mining model that was created using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm, the **Browse** window includes the following views, each designed to let you explore a different aspect of the model:</span></span>  
  
-   [<span data-ttu-id="6ecca-107">Conjuntos de elementos</span><span class="sxs-lookup"><span data-stu-id="6ecca-107">Itemsets</span></span>](#BKMK_Itemsets)  
  
-   [<span data-ttu-id="6ecca-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="6ecca-108">Rules</span></span>](#BKMK_Rules)  
  
-   [<span data-ttu-id="6ecca-109">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="6ecca-109">Dependency Net</span></span>](#BKMK_Dependency)  
  
 <span data-ttu-id="6ecca-110">Tome nota de la opción en cada pestaña, **Mostrar nombre largo** .</span><span class="sxs-lookup"><span data-stu-id="6ecca-110">Take note of the option on each tab, **Show long name** .</span></span> <span data-ttu-id="6ecca-111">Si selecciona esta opción, puede mostrar u ocultar la tabla desde la que el conjunto de elementos se origina, y luego abreviar o alargar el nombre de la regla o el conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-111">By selecting this option, you can show or hide the table from which the itemset originates, and shorten or lengthen the name of the rule or itemset.</span></span> <span data-ttu-id="6ecca-112">Esta opción es particularmente útil cuando los datos de casos y los datos de atributos son de orígenes de datos distintos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-112">This option is particularly useful when your case data and attribute data are from different data sources.</span></span>  
  
 <span data-ttu-id="6ecca-113">Para experimentar con un modelo de asociación, puede utilizar los datos de ejemplo en la pestaña Asociado del libro de ejemplo y generar un modelo de asociación con todos los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="6ecca-113">To experiment with an association model, you can use the sample data on the Associate tab of the sample data workbook, and build an association model using all the defaults.</span></span> <span data-ttu-id="6ecca-114">También puede crear un modelo de análisis de la cesta de compras y abrirlo con **examinar**.</span><span class="sxs-lookup"><span data-stu-id="6ecca-114">You can also build a Shopping Basket Analysis model and open that using **Browse**.</span></span>  
  
###  <a name="itemsets"></a><a name="BKMK_Itemsets"></a><span data-ttu-id="6ecca-115">Conjuntos</span><span class="sxs-lookup"><span data-stu-id="6ecca-115">Itemsets</span></span>  
 <span data-ttu-id="6ecca-116">La pestaña **conjuntos** es un buen lugar para empezar a explorar un modelo de asociación.</span><span class="sxs-lookup"><span data-stu-id="6ecca-116">The **Itemsets** tab is a good place to begin exploring an association model.</span></span> <span data-ttu-id="6ecca-117">Esta pestaña muestra una lista de los elementos que el modelo encontró juntos con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="6ecca-117">This tab shows a list of the items that the model frequently found together.</span></span>  
  
 <span data-ttu-id="6ecca-118">![Lista de elementos de un modelo de asociación](media/dm13-association-itemsets.gif "Lista de elementos de un modelo de asociación")</span><span class="sxs-lookup"><span data-stu-id="6ecca-118">![List of items in an association model](media/dm13-association-itemsets.gif "List of items in an association model")</span></span>  
  
 <span data-ttu-id="6ecca-119">El ejemplo más común de conjuntos de elementos se encuentra en un modelo de cesta de la compra, donde un conjunto de elementos representa pares o conjuntos de productos que muchos clientes compran al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="6ecca-119">The most common example of itemsets is in a shopping basket model, where an itemset represents pairs or sets of products that lots of customers purchase at the same time.</span></span> <span data-ttu-id="6ecca-120">Sin embargo, según cómo agrupe y ordene los elementos, el conjunto de elementos puede contener una secuencia de películas que los clientes piden durante un período de tiempo o de eventos que tienden a aparecer en una ubicación concreta.</span><span class="sxs-lookup"><span data-stu-id="6ecca-120">However, depending on how you group and order your items, the itemset might contain a sequence of movies that customers order over a period of time, or events that tend to occur in  a particular location.</span></span>  
  
 <span data-ttu-id="6ecca-121">Un conjunto de *elementos puede contener tan solo un elemento* en dos, tres o, sin embargo, muchos se establece como el tamaño máximo del conjunto de elementos para el modelo.</span><span class="sxs-lookup"><span data-stu-id="6ecca-121">An *itemset* can contain as few as one item to two, three, or however, many is set as the maximum itemset size for the model.</span></span> <span data-ttu-id="6ecca-122">Para cada conjunto de conjunto, el visor muestra la *compatibilidad*, la *probabilidad*y el *tamaño*del conjunto de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-122">For each itemset, the viewer displays the itemset  *support*,  *probability*, and *size*.</span></span> <span data-ttu-id="6ecca-123">La compatibilidad y la probabilidad son las estadísticas principales utilizadas para alinear los conjuntos de elementos y las reglas que genera un modelo de asociación.</span><span class="sxs-lookup"><span data-stu-id="6ecca-123">Support and probability are the principal statistics used to rank the itemsets and rules generated by an association model.</span></span> <span data-ttu-id="6ecca-124">Estos valores también se utilizan para calcular y describir su importancia.</span><span class="sxs-lookup"><span data-stu-id="6ecca-124">These values are also used to calculate and describe their importance.</span></span>  
  
 <span data-ttu-id="6ecca-125">**Compatibilidad con**.</span><span class="sxs-lookup"><span data-stu-id="6ecca-125">**Support**.</span></span> <span data-ttu-id="6ecca-126">La compatibilidad indica el número de casos o filas de datos de entrada con este elemento.</span><span class="sxs-lookup"><span data-stu-id="6ecca-126">Support means the number of cases or rows of input data that have this item.</span></span> <span data-ttu-id="6ecca-127">Por ejemplo, si un conjunto de elementos contiene dos elementos que se encuentran en un carro de la compra, el número de la columna **soporte** indica el número de veces que se ha producido la combinación de elementos en los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="6ecca-127">For example, if an itemset contains two items that are found in a shopping cart, the number in the **Support** column indicates how many times that combination of items occurred in the source data.</span></span>  
  
 <span data-ttu-id="6ecca-128">**Tamaño**.</span><span class="sxs-lookup"><span data-stu-id="6ecca-128">**Size**.</span></span> <span data-ttu-id="6ecca-129">Al cambiar el tamaño del conjunto de elementos, puede controlar la longitud de las listas de conjuntos de elementos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-129">By changing itemset size, you can control the length of the lists of itemsets.</span></span> <span data-ttu-id="6ecca-130">Si no desea ver los productos individuales en la lista, cambie la opción, **tamaño mínimo**del conjunto de valores, a 2 o más.</span><span class="sxs-lookup"><span data-stu-id="6ecca-130">If you don't want to see single products in the list, change the option, **Minimum itemset size**, to 2 or more.</span></span>  <span data-ttu-id="6ecca-131">Si restringe la lista aumentando el tamaño mínimo de los conjuntos de elementos podrá buscar patrones muy concretos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-131">Restricting the list by increasing the minimum size of itemsets lets you look for very specific patterns.</span></span> <span data-ttu-id="6ecca-132">Esto podría serle útil si está trabajando con un conjunto de datos muy grande.</span><span class="sxs-lookup"><span data-stu-id="6ecca-132">This might be useful if you are working with a very large set of data.</span></span>  
  
 <span data-ttu-id="6ecca-133">Puede filtrar el número de conjuntos que se muestran en la pestaña cambiando los valores de **compatibilidad mínima** y **máximo de filas** .</span><span class="sxs-lookup"><span data-stu-id="6ecca-133">You can filter the number of itemsets that are displayed in the tab by changing the **Minimum support** and **Maximum rows** values.</span></span> <span data-ttu-id="6ecca-134">Si aumenta el valor de **compatibilidad mínima** , la lista mostrará menos conjuntos, pero conjuntos serán las más comunes en los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6ecca-134">If you increase the **Minimum Support** value, the list will show fewer itemsets, but the itemsets will be the more common ones in the input data.</span></span> <span data-ttu-id="6ecca-135">Tanto si es común como importante, es otra pregunta que puede explorar mediante la pestaña **reglas** .</span><span class="sxs-lookup"><span data-stu-id="6ecca-135">Whether common is the same as important is another question, which you can explore using the **Rules** tab.</span></span>  
  
 <span data-ttu-id="6ecca-136">Tenga en cuenta que al cambiar el valor de compatibilidad u otros controles en la pestaña **conjuntos** solo se cambian los elementos que se muestran y no se ve afectado el modelo subyacente.</span><span class="sxs-lookup"><span data-stu-id="6ecca-136">Note that changing the support value or other controls on the **Itemsets** tab only changes the items that are displayed, and does not affect the underlying model.</span></span> <span data-ttu-id="6ecca-137">Si desea generar menos o más conjuntos, o limitar su tamaño, debe utilizar los parámetros `MINIMUM_SUPPORT` y `MAXIMUM_SUPPORT` , disponibles en el cuadro de diálogo **parámetros de algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="6ecca-137">If you want to generate fewer or more itemsets, or limit their size, you should use the parameters, `MINIMUM_SUPPORT` and `MAXIMUM_SUPPORT`, available in the **Algorithm Parameters** dialog box.</span></span>  
  
##### <a name="explore-the-itemsets-list"></a><span data-ttu-id="6ecca-138">Explorar la lista de conjuntos de elementos</span><span class="sxs-lookup"><span data-stu-id="6ecca-138">Explore the itemsets list</span></span>  
  
1.  <span data-ttu-id="6ecca-139">Haga clic en la columna **soporte** para ordenar de mayor a menor compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="6ecca-139">Click the **Support** column to sort by highest to lowest support.</span></span> <span data-ttu-id="6ecca-140">Esto le proporcionará una idea de lo que los clientes compran con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="6ecca-140">This will give you an idea of what customers are buying most often.</span></span>  
  
2.  <span data-ttu-id="6ecca-141">Para centrarse en un conjunto de elementos de interés determinado, a partir de los muchos miles de combinaciones posibles, escriba algún texto en el cuadro **filtrar** conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-141">To focus on a particular itemset of interest, out of the many thousand combinations possible, type some text in the **Filter Itemset** box.</span></span>  
  
     <span data-ttu-id="6ecca-142">Aquí hemos escrito `Gloves` .</span><span class="sxs-lookup"><span data-stu-id="6ecca-142">Here we typed `Gloves`.</span></span> <span data-ttu-id="6ecca-143">Al aplicar el filtro, la lista se actualiza para mostrar solo los conjuntos de elementos que contienen guantes.</span><span class="sxs-lookup"><span data-stu-id="6ecca-143">When you apply the filter, the list is refreshed to show only itemsets containing gloves.</span></span> <span data-ttu-id="6ecca-144">Esto le permite centrarse en las transacciones en las que los clientes compraron guantes y otros artículos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-144">This lets you focus on the transactions where customers purchased gloves and some other item.</span></span>  
  
     <span data-ttu-id="6ecca-145">La opción **Filtrar conjunto de elementos** también muestra una lista de los filtros que ha usado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6ecca-145">The **Filter Itemset** option also displays a list of the filters that you have used previously.</span></span>  
  
3.  <span data-ttu-id="6ecca-146">Cambie el valor de **tamaño mínimo** del conjunto de elementos para filtrar los clientes que compraron solo guantes y ningún otro elemento.</span><span class="sxs-lookup"><span data-stu-id="6ecca-146">Change the value of **Minimum itemset size** to filter out the customers who bought only gloves and no other items.</span></span>  
  
4.  <span data-ttu-id="6ecca-147">Haga clic en la lista desplegable de la opción **Mostrar**para controlar cómo se muestran los atributos:</span><span class="sxs-lookup"><span data-stu-id="6ecca-147">Click the dropdown list for the option **Show**, to control how the attributes are displayed:</span></span>  
  
    -   <span data-ttu-id="6ecca-148">**Mostrar el valor y el nombre del atributo**</span><span class="sxs-lookup"><span data-stu-id="6ecca-148">**Show attribute name and value**</span></span>  
  
    -   <span data-ttu-id="6ecca-149">**Mostrar solo el valor del atributo**</span><span class="sxs-lookup"><span data-stu-id="6ecca-149">**Show attribute value only**</span></span>  
  
    -   <span data-ttu-id="6ecca-150">**Mostrar solo el nombre del atributo**</span><span class="sxs-lookup"><span data-stu-id="6ecca-150">**Show attribute name only**</span></span>  
  
     <span data-ttu-id="6ecca-151">Observe cómo cambia el nombre.</span><span class="sxs-lookup"><span data-stu-id="6ecca-151">Notice how the name changes.</span></span> <span data-ttu-id="6ecca-152">En el caso de un modelo de cesta de la compra, que se crea con tablas anidadas de productos que varios clientes compraron, el nombre de atributo suele ser el nombre del producto y la presencia del producto en la lista se marca como `Existing`, lo que significa que el cliente compró el artículo.</span><span class="sxs-lookup"><span data-stu-id="6ecca-152">In the case of a market basket model, which is built on nested tables of products that were purchased by multiple customers, the attribute name is typically the product name, and the presence of the product in the list is marked as `Existing`, meaning that the customer did buy the item.</span></span>  
  
     <span data-ttu-id="6ecca-153">El opuesto de `Existing` es `Missing`, que puede ser un atributo muy útil para investigar en minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-153">The opposite of `Existing` is `Missing`, which can be a very useful attribute to investigate in data mining.</span></span> <span data-ttu-id="6ecca-154">Por ejemplo, supongamos que el conjunto de elementos A + B es tan popular que quería encontrar clientes que compraron el elemento A pero no el elemento B. Para ello, puede usar una consulta de predicción y recuperar las transacciones con una pero no la otra, y realizar algunos análisis más en ellos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-154">For example, suppose the itemset A +B is so very popular that you wanted to find customers who purchased Item A but not item B. You could do this by using a prediction query and retrieving the transactions with one but not the other, and do some further analysis on those.</span></span> <span data-ttu-id="6ecca-155">Para obtener información sobre cómo crear consultas de predicción en modelos de asociación, vea [ejemplos de consultas de modelos de asociación](data-mining/association-model-query-examples.md) en libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6ecca-155">For information about how to create prediction queries on association models, see [Association Model Query Examples](data-mining/association-model-query-examples.md) in SQL Server Books Online</span></span>  
  
5.  <span data-ttu-id="6ecca-156">Para forzar que se vuelva a mostrar la lista de conjuntos con los nuevos criterios de filtro, puede activar o desactivar la casilla **Mostrar nombre largo** .</span><span class="sxs-lookup"><span data-stu-id="6ecca-156">To force the list of itemsets to redisplay using your new filter criteria, you can select or clear the **Show long name** check box.</span></span>  
  
 [<span data-ttu-id="6ecca-157">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="6ecca-157">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="rules"></a><a name="BKMK_Rules"></a><span data-ttu-id="6ecca-158">Reglamento</span><span class="sxs-lookup"><span data-stu-id="6ecca-158">Rules</span></span>  
 <span data-ttu-id="6ecca-159">La pestaña **reglas** combina información sobre conjuntos y su valor relativo.</span><span class="sxs-lookup"><span data-stu-id="6ecca-159">The **Rules** tab combines information about the itemsets and their relative value.</span></span>  
  
 <span data-ttu-id="6ecca-160">![Lista de reglas creadas por un modelo de asociación](media/dm13-association-rules.gif "Lista de reglas creadas por un modelo de asociación")</span><span class="sxs-lookup"><span data-stu-id="6ecca-160">![List of rules created by an association model](media/dm13-association-rules.gif "List of rules created by an association model")</span></span>  
  
 <span data-ttu-id="6ecca-161">La *probabilidad* representa la fracción de casos del conjunto de DataSet que contiene la combinación de elementos de destino.</span><span class="sxs-lookup"><span data-stu-id="6ecca-161">*Probability* represents the fraction of cases in the dataset that contain the targeted combination of items.</span></span> <span data-ttu-id="6ecca-162">La probabilidad es similar al concepto estadístico de *confianza*y proporciona una indicación de la probabilidad de que se produzca el resultado de una regla.</span><span class="sxs-lookup"><span data-stu-id="6ecca-162">Probability is similar to the statistical concept of *confidence*, and gives you an indication of how likely the result of a rule is to occur.</span></span> <span data-ttu-id="6ecca-163">Puede cambiar el valor de **probabilidad mínima** en este panel para filtrar las reglas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="6ecca-163">You can change the value of **Minimum probability** in this pane to filter the rules that are displayed.</span></span>  
  
 <span data-ttu-id="6ecca-164">El valor de **probabilidad mínima** que se ve inicialmente es el valor de umbral que usó el algoritmo al generar el modelo.</span><span class="sxs-lookup"><span data-stu-id="6ecca-164">The value for **Minimum probability** that you initially see is the threshold value that was used by the algorithm when building the model.</span></span> <span data-ttu-id="6ecca-165">Una vez completado el modelo, no puede reducir este valor, pero puede aumentarlo para mostrar solo los elementos de probabilidad más altos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-165">After the model is complete, you can't decrease this value, but you can increase it to show only the higher probability items.</span></span>  
  
 <span data-ttu-id="6ecca-166">La *importancia* está diseñada para medir la utilidad de una regla.</span><span class="sxs-lookup"><span data-stu-id="6ecca-166">*Importance* is designed to measure the usefulness of a rule.</span></span> <span data-ttu-id="6ecca-167">Una regla que sea muy común puede ser tan ubicua que tenga poco valor informativo.</span><span class="sxs-lookup"><span data-stu-id="6ecca-167">A rule that is very common might be so ubiquitous that is has little information value.</span></span> <span data-ttu-id="6ecca-168">Cuanto mayor sea la importancia, más valiosa será la regla para predecir el resultado.</span><span class="sxs-lookup"><span data-stu-id="6ecca-168">The greater the importance, the more valuable the rule is for predicting the outcome.</span></span> <span data-ttu-id="6ecca-169">En el [análisis de la cesta de compras &#40;tabla análisis para Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) Tool, la importancia puede combinarse con el precio de los artículos para determinar las agrupaciones que son potencialmente más valiosas en términos de ventas.</span><span class="sxs-lookup"><span data-stu-id="6ecca-169">In the [Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) tool, importance can be combined with the price of items to determine the bundles that are potentially most valuable in terms of sales.</span></span>  
  
##### <a name="explore-the-rules-list"></a><span data-ttu-id="6ecca-170">Explorar la lista de reglas</span><span class="sxs-lookup"><span data-stu-id="6ecca-170">Explore the rules list</span></span>  
  
1.  <span data-ttu-id="6ecca-171">Intente hacer clic en los encabezados de columna ( **probabilidad**, **importancia**y **regla** ) para ver cómo cambian los datos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-171">Try clicking the column headings - **Probability**, **Importance**, and **Rule** - to see how the data changes.</span></span>  
  
2.  <span data-ttu-id="6ecca-172">Use la opción **filtrar regla** para escribir valores y centrarse en reglas de destino.</span><span class="sxs-lookup"><span data-stu-id="6ecca-172">Use the **Filter Rule** option to type in values and focus on targeted rules.</span></span>  
  
     <span data-ttu-id="6ecca-173">Por ejemplo, si desea ver todas las reglas que predicen qué clientes es probable que compren junto con guantes, escriba "guantes" en el cuadro de texto y actualice el panel.</span><span class="sxs-lookup"><span data-stu-id="6ecca-173">For example, if you want to see all the rules that predict what customers are likely to purchase along with gloves, type "gloves" in the text box and refresh the pane.</span></span>  
  
     <span data-ttu-id="6ecca-174">La opción **Filtrar conjunto de elementos** también muestra una lista de los filtros que ha usado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6ecca-174">The **Filter Itemset** option also displays a list of the filters that you have used previously.</span></span>  
  
3.  <span data-ttu-id="6ecca-175">Para forzar que se vuelva a mostrar la lista de reglas usando criterios de filtro, puede activar o desactivar la casilla **Mostrar nombre largo** .</span><span class="sxs-lookup"><span data-stu-id="6ecca-175">To force the list of rules to redisplay using filter criteria, you can select or clear the **Show long name** check box.</span></span>  
  
4.  <span data-ttu-id="6ecca-176">Use la opción **Mostrar** para controlar la manera en que se muestran los nombres de las reglas.</span><span class="sxs-lookup"><span data-stu-id="6ecca-176">Use the option, **Show** to control the way that rule names are displayed.</span></span>  
  
5.  <span data-ttu-id="6ecca-177">Establezca el valor de la opción **número máximo de filas** en 100 y, a continuación, haga clic en **copiar a Excel**.</span><span class="sxs-lookup"><span data-stu-id="6ecca-177">Set the value for the **Maximum rows** option to 100, and then click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="6ecca-178">Tenga en cuenta que el cambio de este valor no afecta a la cantidad de datos del modelo; simplemente controla el número de filas de la lista de visualización.</span><span class="sxs-lookup"><span data-stu-id="6ecca-178">Note that changing this value doesn't have any effect on the amount of data in the model; it simply controls the number of rows in the display list.</span></span> <span data-ttu-id="6ecca-179">Esta opción puede ser útil cuando se trabaja con modelos muy grandes.</span><span class="sxs-lookup"><span data-stu-id="6ecca-179">This option can be useful when working with very large models.</span></span>  
  
 [<span data-ttu-id="6ecca-180">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="6ecca-180">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="6ecca-181">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="6ecca-181">Dependency Network</span></span>  
 <span data-ttu-id="6ecca-182">La pestaña **red de dependencias** es un mapa visual de las correlaciones entre elementos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-182">The **Dependency Network** tab is a visual map of the correlations among items.</span></span> <span data-ttu-id="6ecca-183">Cada óvalo del gráfico (denominado *nodo*) representa un par atributo-valor, como "chaleco = Existing" o "Age = 1-30".</span><span class="sxs-lookup"><span data-stu-id="6ecca-183">Each oval in the graph (referred to as a *node*) represents an attribute-value pair, such as "Vest = Existing" or "Age = 1-30".</span></span>  <span data-ttu-id="6ecca-184">Cada línea que conecta los óvalos (a la que se hace referencia como un *borde*) representa un tipo de correlación.</span><span class="sxs-lookup"><span data-stu-id="6ecca-184">Each line connecting the ovals (referred to as an *edge*) represents a type of correlation.</span></span>  
  
 <span data-ttu-id="6ecca-185">![Gráfico de redes de dependencias para un modelo de asociación](media/dm13-association-dependencynetwork.gif "Gráfico de redes de dependencias para un modelo de asociación")</span><span class="sxs-lookup"><span data-stu-id="6ecca-185">![Dependency network graph for an association model](media/dm13-association-dependencynetwork.gif "Dependency network graph for an association model")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="6ecca-186">Explorar la red de dependencias</span><span class="sxs-lookup"><span data-stu-id="6ecca-186">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="6ecca-187">Haga clic en el botón **Buscar** y use el cuadro de diálogo **Buscar nodo** para escribir un elemento de interés.</span><span class="sxs-lookup"><span data-stu-id="6ecca-187">Click the **Find** button and use the **Find Node** dialog box to type an item of interest.</span></span>  
  
     <span data-ttu-id="6ecca-188">Por ejemplo, escriba "guantes" y, a continuación, maximice el gráfico en la ventana para que pueda ver fácilmente los resultados.</span><span class="sxs-lookup"><span data-stu-id="6ecca-188">For example, type "gloves" and then maximize the graph in the window so that you can easily see the results.</span></span>  
  
     <span data-ttu-id="6ecca-189">Se resalta el nodo que contiene el elemento, mientras que las flechas que apuntan al nodo representan una regla que conecta elementos.</span><span class="sxs-lookup"><span data-stu-id="6ecca-189">The node that contains the item is highlighted, while the arrows pointing to the node represent a rule that connects the items.</span></span>  
  
     <span data-ttu-id="6ecca-190">La dirección de la flecha le indica la dirección de la regla.</span><span class="sxs-lookup"><span data-stu-id="6ecca-190">The direction of the arrow tells you the direction of the rule.</span></span> <span data-ttu-id="6ecca-191">Por ejemplo, si alguien que compra guantes también es probable que compre un chaleco, la flecha comenzará desde el nodo "guante" y terminará en el nodo "chaleco".</span><span class="sxs-lookup"><span data-stu-id="6ecca-191">For example, if someone who buys gloves is also likely to buy a vest, the arrow will start from the "glove" node and terminate on the "vest" node.</span></span>  
  
     <span data-ttu-id="6ecca-192">Para obtener estadísticas adicionales acerca de esta regla, puede hacer clic en la pestaña **reglas** y buscar una regla con la descripción "guante-existente"-> "atribución existente".)</span><span class="sxs-lookup"><span data-stu-id="6ecca-192">To get additional statistics about this rule, you can click the **Rules** tab and look for a rule with the description, "Glove - Existing" -> "Vest - Existing.")</span></span>  
  
2.  <span data-ttu-id="6ecca-193">Haga clic en el control deslizante y arrástrelo a la izquierda del visor.</span><span class="sxs-lookup"><span data-stu-id="6ecca-193">Click and drag the slider at the left of the viewer.</span></span>  
  
     <span data-ttu-id="6ecca-194">El control deslizante actúa como filtro en la probabilidad de las reglas.</span><span class="sxs-lookup"><span data-stu-id="6ecca-194">The slider acts as a filter on the probability of the rules.</span></span> <span data-ttu-id="6ecca-195">Si desplaza el control deslizante hacia abajo, solo se verán las reglas más similares.</span><span class="sxs-lookup"><span data-stu-id="6ecca-195">Lowering the slider shows only the strongest rules.</span></span>  
  
3.  <span data-ttu-id="6ecca-196">Haga clic en **copiar a Excel** para copiar una instantánea de la ventana actual en Excel.</span><span class="sxs-lookup"><span data-stu-id="6ecca-196">Click **Copy to Excel** to copy a snapshot of the current window to Excel.</span></span>  
  
     <span data-ttu-id="6ecca-197">No podrá trabajar con el gráfico que copia en Excel; Si necesita un gráfico de red interactiva, use el [&#41;ver modelos de minería de datos en Visio &#40;complementos de minería de datos ](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="6ecca-197">You won't be able to work with the graph that you copy into Excel; if you need an interactive network graph, use the [Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
 [<span data-ttu-id="6ecca-198">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="6ecca-198">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="more-about-association-models"></a><span data-ttu-id="6ecca-199">Más información sobre los modelos de asociación</span><span class="sxs-lookup"><span data-stu-id="6ecca-199">More about Association Models</span></span>  
 <span data-ttu-id="6ecca-200">Puede usar la característica **examinar** para abrir y explorar cualquier modelo creado mediante el algoritmo de reglas de Asociación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6ecca-200">You can use the **Browse** feature to open and explore any model that was created using the Microsoft Association Rules algorithm.</span></span> <span data-ttu-id="6ecca-201">Esto incluye los modelos creados con el análisis de la [cesta de compras &#40;tabla análisis para Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) Tool, en la cinta de opciones **herramientas de análisis de tabla** o en [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ecca-201">This includes models built using the [Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) tool, in the **Table Analysis Tools** ribbon, or in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6ecca-202">Si crea un modelo de reglas de asociación con la herramienta de análisis de cesta de la compra, muchas de las opciones avanzadas se configuran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6ecca-202">If you create an association rules model using the Shopping Basket Analysis tool, many of the advanced options are configured automatically for you.</span></span>  
  
 <span data-ttu-id="6ecca-203">Si desea establecer parámetros avanzados o modificar la probabilidad y la compatibilidad mínimas, use el Asistente para la Asociación &#40;el Asistente para la [&#41;de datos del cliente de minería de datos para Excel](associate-wizard-data-mining-client-for-excel.md) o cree su propio modelo mediante la opción [Agregar modelo a estructura &#40;de minería de datos para Excel&#41;de](add-model-to-structure-data-mining-add-ins-for-excel.md) modelado.</span><span class="sxs-lookup"><span data-stu-id="6ecca-203">If you want to set advanced parameters or alter minimum probability and support, use the [Associate Wizard &#40;Data Mining Client for Excel&#41;](associate-wizard-data-mining-client-for-excel.md) wizard, or build your own model using the [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md) modeling option.</span></span>  
  
-   <span data-ttu-id="6ecca-204">**Conjuntos:** Al crear el modelo, también puede controlar el número de conjuntos que se generan asignando un valor al parámetro MINIMUM_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="6ecca-204">**Itemsets:** When you create the model, you can also control the number of itemsets that are generated by assigning a value to the MINIMUM_PROBABILITY parameter.</span></span> <span data-ttu-id="6ecca-205">Este parámetro está disponible en el cuadro de diálogo Parámetros de algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6ecca-205">This parameter is available in the Algorithm Parameters dialog box.</span></span>  
  
-   <span data-ttu-id="6ecca-206">**Reglas:** El [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de reglas de Asociación de usa valores de probabilidad para restringir el número de reglas que se generan.</span><span class="sxs-lookup"><span data-stu-id="6ecca-206">**Rules:** The [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm uses probability values to restrict the number of rules that are generated.</span></span> <span data-ttu-id="6ecca-207">Puede controlar el número de reglas estableciendo los parámetros `MINIMUM_PROBABILITY` o `MINIMUM _IMPORTANCE`.</span><span class="sxs-lookup"><span data-stu-id="6ecca-207">You can control the number of rules by setting the parameters, `MINIMUM_PROBABILITY` or `MINIMUM _IMPORTANCE`.</span></span>  
  
 <span data-ttu-id="6ecca-208">Para obtener más información acerca de la configuración de parámetros avanzados, vea [algoritmos de minería de datos &#40;SQL Server complementos de minería de datos&#41;](data-mining-algorithms-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="6ecca-208">For more information about configuring advanced parameters, see [Data Mining Algorithms &#40;SQL Server Data Mining Add-ins&#41;](data-mining-algorithms-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecca-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ecca-209">See Also</span></span>  
 [<span data-ttu-id="6ecca-210">Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="6ecca-210">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  