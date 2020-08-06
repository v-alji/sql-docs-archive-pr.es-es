---
title: Examinar un modelo de agrupación en clústeres | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- clustering [data mining]
- mining model, clustering
ms.assetid: 7f3f0949-d791-403a-88e2-54cb1a803dae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f1d508603acd29fde981bddc5642b54ca9413f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670126"
---
# <a name="browsing-a-clustering-model"></a><span data-ttu-id="e1bbf-102">Examinar un modelo de clústeres</span><span class="sxs-lookup"><span data-stu-id="e1bbf-102">Browsing a Clustering Model</span></span>
  <span data-ttu-id="e1bbf-103">Al abrir un modelo de agrupación en clústeres mediante **examinar**, el modelo se muestra en un visor interactivo, similar al visor de agrupación en clústeres de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-103">When you open a clustering model using **Browse**, the model is displayed in an interactive viewer, similar to the clustering viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e1bbf-104">El visor le ayudará a explorar los clústeres que se han creado y a conocer las características del clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-104">The viewer helps you explore the clusters that were created, and understand cluster characteristics.</span></span> <span data-ttu-id="e1bbf-105">Asimismo, podrá comparar y contrastar segmentos individuales con otros segmentos o con la población.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-105">You can also compare and contrast individual segments with other segments or with the population.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="e1bbf-106">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="e1bbf-106">Explore the Model</span></span>  
 <span data-ttu-id="e1bbf-107">La ventana **examinar** incluye las siguientes herramientas para ayudarle a entender el modelo de agrupación en clústeres y explorar los atributos de los grupos de datos subyacentes:</span><span class="sxs-lookup"><span data-stu-id="e1bbf-107">The **Browse** window includes the following tools to help you understand your clustering model and explore the attributes of the underlying data groups:</span></span>  
  
-   [<span data-ttu-id="e1bbf-108">Diagrama del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-108">Cluster Diagram</span></span>](#BKMK_ClusterDiagram)  
  
-   [<span data-ttu-id="e1bbf-109">Perfiles del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-109">Cluster Profiles</span></span>](#BKMK_ClusterProfiles)  
  
-   [<span data-ttu-id="e1bbf-110">Características del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-110">Cluster Characteristics</span></span>](#BKMK_ClusterCharacteristics)  
  
-   [<span data-ttu-id="e1bbf-111">Distinción del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-111">Cluster Discrimination</span></span>](#BKMK_ClusterDiscrimination)  
  
 <span data-ttu-id="e1bbf-112">Para experimentar con un modelo de agrupación en clústeres, puede usar los datos de ejemplo de la pestaña entrenamiento del libro de datos de ejemplo y generar un modelo de agrupación en clústeres mediante el [Asistente para clúster &#40;complementos de minería de datos para Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) y todos los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-112">To experiment with a clustering model, you can use the sample data on the Training tab of the sample data workbook, and build a clustering model using [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) and all the defaults.</span></span>  
  
###  <a name="cluster-diagram"></a><a name="BKMK_ClusterDiagram"></a><span data-ttu-id="e1bbf-113">Diagrama del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-113">Cluster Diagram</span></span>  
 <span data-ttu-id="e1bbf-114">La pestaña **Diagrama del clúster** muestra todos los clústeres que se encuentran en un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-114">The **Cluster Diagram** tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="e1bbf-115">Aquí puede comprobar la cantidad de agrupaciones que se encontraron en el conjunto de datos y lo cerca o lejos que se encuentran entre sí.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-115">Here you can see how many different groupings were found in your data set, and how near or far they are from each other.</span></span>  
  
##### <a name="explore-the-cluster-diagram"></a><span data-ttu-id="e1bbf-116">Explorar el diagrama del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-116">Explore the cluster diagram</span></span>  
  
1.  <span data-ttu-id="e1bbf-117">Haga clic en el Clúster 1 en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-117">Click Cluster 1 in the diagram.</span></span>  
  
     <span data-ttu-id="e1bbf-118">Observe cómo las líneas en gris que conectan todos los clústeres cambian, de forma que la líneas que se dirigen al clúster seleccionado se resaltan en azul chillón.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-118">Note how the gray lines connecting all clusters change so that lines leading to the selected cluster are highlighted in bright blue.</span></span>  
  
     <span data-ttu-id="e1bbf-119">![introducción al diagrama del clúster](media/dm13-cluster-diagram-intro.gif "introducción al diagrama del clúster")</span><span class="sxs-lookup"><span data-stu-id="e1bbf-119">![cluster diagram intro](media/dm13-cluster-diagram-intro.gif "cluster diagram intro")</span></span>  
  
     <span data-ttu-id="e1bbf-120">La intensidad de la línea que conecta un clúster a otro representa la importancia de la similitud de los clústeres.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-120">The intensity of the line that connects one cluster to another represents the strength of the similarity of the clusters.</span></span> <span data-ttu-id="e1bbf-121">Si el sombreado es claro o inexistente, los clústeres no son muy similares.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-121">If the shading is light or nonexistent, the clusters are not very similar.</span></span> <span data-ttu-id="e1bbf-122">A medida que la línea se va oscureciendo, indica que la similitud entre dos clústeres es más marcada.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-122">As the line becomes darker, it indicates that the similarity between the two clusters is stronger.</span></span>  
  
2.  <span data-ttu-id="e1bbf-123">Haga clic y arrastre el control deslizante hacia la izquierda del diagrama del clúster para ajustar el número de líneas que va a mostrar el visor.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-123">Click and drag the slider to the left of the cluster diagram, to adjust how many lines the viewer shows.</span></span>  
  
     <span data-ttu-id="e1bbf-124">Cuando baje el control deslizante, solamente se mostrarán los vínculos de mayor importancia entre los clústeres.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-124">When you drag the slider down, only the strongest links between clusters are shown.</span></span> <span data-ttu-id="e1bbf-125">De esta forma, resultará más sencillo centrase en los grupos relacionados.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-125">This helps you focus on related groups.</span></span>  
  
3.  <span data-ttu-id="e1bbf-126">Observe el control **variable de sombreado** en la esquina superior derecha de la ventana **Diagrama del clúster** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-126">Notice the **Shading Variable** control in the upper right corner of the **Cluster Diagram** window.</span></span>  
  
     <span data-ttu-id="e1bbf-127">De forma predeterminada, se establece en **Population**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-127">By default, it is set to **Population**.</span></span> <span data-ttu-id="e1bbf-128">Esto indica que los clústeres más oscuros proporcionan mayor compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-128">What this means is that the darker clusters have greater support.</span></span>  
  
4.  <span data-ttu-id="e1bbf-129">Deténgase sobre cualquier clúster con el cursor.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-129">Pause over any cluster with the cursor.</span></span>  
  
     <span data-ttu-id="e1bbf-130">Aparecerá una ventana con información sobre herramientas que contiene la población de ese clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-130">A ToolTip is displayed that contains the population of that cluster.</span></span>  
  
5.  <span data-ttu-id="e1bbf-131">Ahora, haga clic en la lista desplegable **variable de sombreado** y elija la variable **Age** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-131">Now, click the **Shading Variable** dropdown list and choose the **Age** variable.</span></span> <span data-ttu-id="e1bbf-132">Al hacerlo, aparecerá una lista de valores en el cuadro de texto **Estado** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-132">As you do so, a list of values appears in the **State** text box.</span></span>  
  
     <span data-ttu-id="e1bbf-133">La columna Edad se usa como entrada en este modelo y contiene valores numéricos continuos, pero para fines de agrupación en clústeres, el algoritmo siempre discretiza números.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-133">The Age column used as input to this model contains continuous numeric values, but for the purpose of clustering, the algorithm always discretizes numbers.</span></span> <span data-ttu-id="e1bbf-134">Aquí puede ver las ubicaciones o los grupos creados por el algoritmo, como "muy bajo ( \<=27)" and "Very High (> = 63)".</span><span class="sxs-lookup"><span data-stu-id="e1bbf-134">Here you can see the bins, or groups that the algorithm created, such as "Very Low (\<=27)" and "Very High (>=63)".</span></span>  
  
6.  <span data-ttu-id="e1bbf-135">En las listas desplegables **Estado** , seleccione **muy alta** y vea cómo cambia el diagrama.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-135">From the **State** dropdown lists, select **Very High** and see how the diagram changes.</span></span>  
  
     <span data-ttu-id="e1bbf-136">Si cambia la variable de sombreado, podrá ver fácilmente qué clústeres contienen más elementos de este grupo de edad objetivo y qué clústeres contienen muy pocos clientes de este grupo de edad.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-136">By changing the shading variable, you can see at a glance which clusters contain more of this targeted age group, and which clusters contain very few customers in this age group.</span></span>  
  
     <span data-ttu-id="e1bbf-137">![Modificar el diagrama de clúster para mostrar la edad](media/dm13-cluster-diagramshadebyage.gif "Modificar el diagrama de clúster para mostrar la edad")</span><span class="sxs-lookup"><span data-stu-id="e1bbf-137">![Modify the cluster diagram to show age](media/dm13-cluster-diagramshadebyage.gif "Modify the cluster diagram to show age")</span></span>  
  
     <span data-ttu-id="e1bbf-138">Cuanto más oscuro sea el sombreado, mayor será la proporción del atributo de destino y la distribución de valores para ese clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-138">The darker the shading, the larger the proportion of the target attribute and value distribution that cluster.</span></span>  
  
7.  <span data-ttu-id="e1bbf-139">Busque el clúster sombreado más oscuro cuando la variable de **sombreado** esté establecida en Age >65.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-139">Locate the cluster that is shaded darkest when the **Shading Variable** is set to Age >65.</span></span>  
  
     <span data-ttu-id="e1bbf-140">Mantenga el mouse sobre el clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-140">Hover the mouse over the cluster.</span></span>  
  
     <span data-ttu-id="e1bbf-141">El valor que aparece ahora en la ventana de información sobre herramientas muestra la población de clientes en este clúster con más de 65 años de edad.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-141">The value displayed in the ToolTip now shows you the population of customers in this cluster who are over 65.</span></span>  
  
8.  <span data-ttu-id="e1bbf-142">Haga clic con el botón derecho en el clúster y seleccione **cambiar nombre de clúster**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-142">Right-click the cluster and select **Rename Cluster**.</span></span> <span data-ttu-id="e1bbf-143">Escriba un nuevo nombre descriptivo, por ejemplo, **más de 65**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-143">Type a new name that is descriptive, such as **Over 65**.</span></span> <span data-ttu-id="e1bbf-144">El nuevo nombre se guarda con el modelo en el servidor y se puede usar para identificar el clúster en las otras vistas de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-144">The new name is saved with the model to the server and can be used for identifying the cluster in the other clustering views.</span></span>  
  
 [<span data-ttu-id="e1bbf-145">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="e1bbf-145">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-profiles"></a><a name="BKMK_ClusterProfiles"></a><span data-ttu-id="e1bbf-146">Perfiles del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-146">Cluster Profiles</span></span>  
 <span data-ttu-id="e1bbf-147">La pestaña **perfiles del clúster** le permite comparar la composición de todos los clústeres de un vistazo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-147">The **Cluster Profiles** tab lets you compare the makeup of all clusters at a glance.</span></span> <span data-ttu-id="e1bbf-148">Es un buen punto de partida cuando se empieza a familiarizar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-148">This is a good place to start when you are getting familiar with the model.</span></span> <span data-ttu-id="e1bbf-149">Esta vista será también útil más adelante, si ha estado explorando un clúster determinado y decide que necesita buscar clústeres relacionados.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-149">This view is also useful later on, if you have been exploring a particular cluster and decide you need to find related ones.</span></span>  
  
 <span data-ttu-id="e1bbf-150">Los **perfiles de clúster** también proporcionan una buena información general sobre el modo en que los clústeres son diferentes entre sí.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-150">**Cluster Profiles** also gives you a good overview of how the clusters are different from each other.</span></span> <span data-ttu-id="e1bbf-151">Por consiguiente, se recomienda usar esta vista para asignar a cada clúster un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-151">Therefore, you might find it convenient to use this view to give each cluster a descriptive name.</span></span>  
  
##### <a name="explore-the-cluster-profiles"></a><span data-ttu-id="e1bbf-152">Explorar los perfiles del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-152">Explore the cluster profiles</span></span>  
  
1.  <span data-ttu-id="e1bbf-153">Haga clic en la celda de profesiones, en la columna **Estados** , para ver la lista de todos los valores de ocupación.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-153">Click the cell for Occupations, in the **States** column, to see the list of all values for Occupation.</span></span>  
  
2.  <span data-ttu-id="e1bbf-154">Ahora desplace el cursor sobre Empleos en los perfiles del clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-154">Now move the cursor over Occupation in the cluster profiles.</span></span>  
  
     <span data-ttu-id="e1bbf-155">La información sobre herramientas muestra la distribución de los empleos en ese clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-155">The ToolTip shows the distribution of occupations in that cluster.</span></span>  
  
     <span data-ttu-id="e1bbf-156">![Vea los valores detallados en la información sobre herramientas o en la leyenda](media/dm13-cluster-profile-age-tooltip.gif "Vea los valores detallados en la información sobre herramientas o en la leyenda")</span><span class="sxs-lookup"><span data-stu-id="e1bbf-156">![View detailed values in Tooltips or in Legend](media/dm13-cluster-profile-age-tooltip.gif "View detailed values in Tooltips or in Legend")</span></span>  
  
     <span data-ttu-id="e1bbf-157">Tenga en cuenta que, en algunos clústeres (como el del gráfico), la lista de profesiones no está completa y algunas profesiones se sustituyen por la etiqueta **other**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-157">Notice that, in some clusters (such as the one in the graphic), the list of occupations is not complete, and some occupations are replaced with the label, **Other**.</span></span>  
  
     <span data-ttu-id="e1bbf-158">Esto es así por motivos de diseño, ya que podría resultar difícil ver las diferencias entre muchas barras pequeñas en un histograma.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-158">This is by design, because it can be hard to tell the difference between many small bars in a histogram.</span></span> <span data-ttu-id="e1bbf-159">De forma predeterminada, solo se conservan las barras de mayor importancia y las barras restantes se agrupan en **otro** cubo gris.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-159">By default only the bars of highest importance are retained, and the remaining bars are grouped together into a gray **Other** bucket.</span></span>  
  
     <span data-ttu-id="e1bbf-160">Para cambiar el número de barras que están visibles en cualquier histograma, use la opción **barras de histograma**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-160">To change the number of bars that are visible in any histogram, use the option **Histogram bars**.</span></span>  
  
3.  <span data-ttu-id="e1bbf-161">Tenga en cuenta que la columna **Age** es diferente de las demás.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-161">Note that the **Age** column looks different from the others.</span></span> <span data-ttu-id="e1bbf-162">Haga clic en el rombo del gráfico que se usa para representar la edad.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-162">Click the diamond in the chart used to represent Age.</span></span>  
  
     <span data-ttu-id="e1bbf-163">La columna Edad inicialmente solo contenía números continuos.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-163">The column Age originally contained only continuous numbers.</span></span> <span data-ttu-id="e1bbf-164">El algoritmo de clústeres requiere valores discretos, de modo que agrupó los valores numéricos de la columna Edad en un número limitado de grupos de edad, en función de la distribución de valores.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-164">The clustering algorithm requires discrete values, so it grouped the numeric values in the Age column into a limited number of age groups, based on the distribution of values.</span></span>  
  
4.  <span data-ttu-id="e1bbf-165">Haga clic en uno de los gráficos de rombo en un perfil del clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-165">Click one of the diamond charts in a cluster profile.</span></span>  
  
     <span data-ttu-id="e1bbf-166">Estos gráficos de rombo se muestran únicamente cuando los datos de origen usan valores numéricos continuos.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-166">These diamond charts are displayed only when the source data uses continuous numeric values.</span></span> <span data-ttu-id="e1bbf-167">Los gráficos de rombo proporcionan algunas estadísticas descriptivas de utilidad, lo cual incluye la media y la desviación estándar para ese valor en cada clúster:</span><span class="sxs-lookup"><span data-stu-id="e1bbf-167">The diamond charts provide some useful descriptive statistics, including the mean and standard deviation for that value in each cluster:</span></span>  
  
    -   <span data-ttu-id="e1bbf-168">La línea del gráfico de rombo representa el intervalo de valores del atributo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-168">The line in the diamond chart represents the range of values for the attribute.</span></span> <span data-ttu-id="e1bbf-169">Los valores también se muestran en la columna **Estados** a la izquierda del gráfico **perfiles** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-169">The values are also shown in the **States** column at the left of the **Profiles** chart.</span></span>  
  
    -   <span data-ttu-id="e1bbf-170">El centro del rombo se encuentra en la media del nodo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-170">The center of the diamond is positioned at the mean for the node.</span></span>  
  
    -   <span data-ttu-id="e1bbf-171">El ancho del rombo representa la varianza del atributo en ese nodo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-171">The width of the diamond represents the variance of the attribute at that node.</span></span> <span data-ttu-id="e1bbf-172">Por tanto, un rombo más estrecho indica que el nodo puede crear una predicción más exacta.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-172">Therefore, a thinner diamond indicates that the node can create a more accurate prediction.</span></span>  
  
5.  <span data-ttu-id="e1bbf-173">Para hacer más espacio en el gráfico, haga clic con el botón derecho en un clúster que no necesite ver de inmediato y seleccione **Ocultar columna**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-173">To make more room in the graph, right-click a cluster you don't need to view right away, and select **Hide Column**.</span></span> <span data-ttu-id="e1bbf-174">Esto no lo elimina del modelo, simplemente contrae la columna de forma temporal.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-174">This doesn't delete it from the model, just collapses the column temporarily.</span></span>  
  
     <span data-ttu-id="e1bbf-175">Para ver los clústeres que ha ocultado, puede hacer clic y arrastrar el borde de la columna o seleccionar el nombre del clúster en la lista, **más clústeres**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-175">To view clusters that you've hidden, you can click and drag the column edge, or select the cluster name from the list, **More clusters**.</span></span>  
  
6.  <span data-ttu-id="e1bbf-176">Descienda por la lista de atributos hasta que encuentre Bike Buyer y, después, busque el clúster con el porcentaje más alto de los valores Sí.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-176">Scroll down the attribute list till you find Bike Buyer, and then find the cluster that has the highest percentage of Yes values.</span></span>  
  
     <span data-ttu-id="e1bbf-177">Haga clic con el botón derecho en el encabezado de columna del clúster cuyo nombre desea cambiar, seleccione **cambiar nombre de clúster**y escriba **Bike**Buyers.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-177">Right-click the column heading for the cluster that you want to rename, select **Rename cluster**, and type **Bike Buyers**.</span></span>  
  
     <span data-ttu-id="e1bbf-178">El nuevo nombre del clúster se mantiene en todas las vistas y en el servidor hasta que se vuelva a procesar el modelo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-178">The new cluster name is persisted in all views, and on the server, until you reprocess the model.</span></span>  
  
     <span data-ttu-id="e1bbf-179">![Cambiar el nombre de los clústeres para que el gráfico sea más fácil de utilizar](media/dm13-cluster-rename.gif "Cambiar el nombre de los clústeres para que el gráfico sea más fácil de utilizar")</span><span class="sxs-lookup"><span data-stu-id="e1bbf-179">![Rename clusters to make chart easier to use](media/dm13-cluster-rename.gif "Rename clusters to make chart easier to use")</span></span>  
  
 <span data-ttu-id="e1bbf-180">**Sugerencias**</span><span class="sxs-lookup"><span data-stu-id="e1bbf-180">**Tips**</span></span>  
  
-   <span data-ttu-id="e1bbf-181">Haga clic en un encabezado de columna para ordenar los atributos por orden de importancia respecto a ese clúster.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-181">Click a column heading to sort the attributes in order of importance for that cluster.</span></span>  
  
-   <span data-ttu-id="e1bbf-182">Arrastre las columnas para volver a ordenarlas en el visor.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-182">Drag columns to reorder them in the viewer.</span></span>  
  
-   <span data-ttu-id="e1bbf-183">Haga clic en cualquier celda del gráfico de perfiles para ver estadísticas detalladas en la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-183">Click any cell in the profiles chart to view detailed statistics in the **Mining Legend**.</span></span>  
  
-   <span data-ttu-id="e1bbf-184">Haga clic con el botón secundario en cualquier celda y seleccione **columnas del modelo de obtención de detalles** para generar los datos subyacentes en una nueva hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-184">Right-click any cell and select **Drillthrough model columns** to output the underlying data to a new worksheet in Excel.</span></span>  
  
-   <span data-ttu-id="e1bbf-185">Haga clic con el botón derecho en el encabezado de columna del clúster y seleccione **obtención de detalles para estructurar datos** para obtener información detallada sobre los miembros del clúster que no se incluyeron en el modelo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-185">Right-click the cluster's column heading and select **Drillthrough to structure data** to get detailed information about the cluster members that wasn't included in the model.</span></span>  
  
     <span data-ttu-id="e1bbf-186">Por ejemplo, si va a generar perfiles de clientes, puede dejar la información de contacto en los datos subyacentes (la estructura de minería de datos), pero no incluirla en el modelo, ya que no es útil para el análisis.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-186">For example, if you are profiling customers, you might leave the contact information in the underlying data (the mining structure) but not include it in the model, because it's not useful for analysis.</span></span> <span data-ttu-id="e1bbf-187">Sin embargo, una vez se hayan asignado los clientes a los clústeres, podrá ver los datos detallados mediante la obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-187">However, after customers have been assigned to clusters, you can view the detailed data by using drillthrough.</span></span>  
  
 [<span data-ttu-id="e1bbf-188">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="e1bbf-188">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-characteristics"></a><a name="BKMK_ClusterCharacteristics"></a><span data-ttu-id="e1bbf-189">Características del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-189">Cluster Characteristics</span></span>  
 <span data-ttu-id="e1bbf-190">Con la vista Características de clúster, podrá realizar una exploración profunda de un solo clúster, para buscar los atributos que mejor definen a este grupo de datos.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-190">The Cluster Characteristics view lets you really explore a single cluster, to find which attributes most strongly characterize this group of data.</span></span>  
  
##### <a name="explore-the-cluster-characteristics"></a><span data-ttu-id="e1bbf-191">Explorar las características del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-191">Explore the cluster characteristics</span></span>  
  
1.  <span data-ttu-id="e1bbf-192">Seleccione el clúster de **más de 65** en la lista de **clústeres** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-192">Select the **Over 65** cluster from the **Cluster** list.</span></span>  
  
     <span data-ttu-id="e1bbf-193">Tras seleccionar un clúster, puede ver detalladamente las características que lo componen.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-193">After you select a cluster, you can see in detail the characteristics that make up that specific cluster.</span></span>  
  
     <span data-ttu-id="e1bbf-194">Los atributos que contiene el clúster se enumeran en las columnas **Variables** ; el estado del atributo se indica en la columna **Valores** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-194">The attributes that the cluster contains are listed in the **Variables** columns, and the state of the listed attribute is listed in the **Values** column.</span></span>  
  
     <span data-ttu-id="e1bbf-195">Los Estados de los atributos se muestran por orden de importancia, junto con su probabilidad en este clúster, representados como una barra coloreada en la columna **probabilidad** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-195">Attribute states are listed in order of importance, accompanied by their probability in this cluster, represented as a colored bar in the **Probability** column.</span></span>  
  
     <span data-ttu-id="e1bbf-196">![Características de un modelo de agrupación en clústeres](media/dm13-cluster-characteristics.gif "Características de un modelo de agrupación en clústeres")</span><span class="sxs-lookup"><span data-stu-id="e1bbf-196">![Characteristics of a clustering model](media/dm13-cluster-characteristics.gif "Characteristics of a clustering model")</span></span>  
  
2.  <span data-ttu-id="e1bbf-197">Haga clic en la columna **variables** para ordenar por atributo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-197">Click the **Variables** column to sort by attribute.</span></span>  
  
     <span data-ttu-id="e1bbf-198">Al cambiar la variable para ordenar, podrá ver con más facilidad cómo se distribuyen en el grupo los valores de variables tales como ingresos o propiedad de vehículo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-198">By changing the sort variable, you can more easily see how values for variables such as income or car ownership are distributed in the group.</span></span>  
  
3.  <span data-ttu-id="e1bbf-199">Haga clic en **copiar a Excel**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-199">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="e1bbf-200">Se agrega una nueva hoja de cálculo al libro que contiene las características del clúster seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-200">A new worksheet is added to your workbook that contains the characteristics of the selected cluster.</span></span>  
  
4.  <span data-ttu-id="e1bbf-201">Ahora elija otro clúster de la lista, **Bike**Buyers.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-201">Now choose a different cluster from the list, **Bike Buyers**.</span></span>  
  
5.  <span data-ttu-id="e1bbf-202">Haga clic en **copiar a Excel**.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-202">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="e1bbf-203">Tenga en cuenta que el nuevo gráfico de características del clúster se ha agregado en su propia hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-203">Note that the new cluster characteristics chart is added on its own worksheet.</span></span> <span data-ttu-id="e1bbf-204">Puede moverla a la misma hoja de cálculo que el otro perfil para facilitar su comparación, lo que hará en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-204">You can move it onto the same worksheet as the other profile to make it easier to compare them, which you'll do in the next step.</span></span>  
  
 <span data-ttu-id="e1bbf-205">**Sugerencias**</span><span class="sxs-lookup"><span data-stu-id="e1bbf-205">**Tips**</span></span>  
  
-   <span data-ttu-id="e1bbf-206">Tenga en cuenta que la principal característica del cliente en el clúster de más de 65 es que no compran el producto.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-206">Note that the primary characteristic of the customer in the Over 65 cluster is that they don't buy your product!</span></span> <span data-ttu-id="e1bbf-207">Si quiere saber por qué es así, puede examinar los clústeres y comparar los grupos o bien, puede crear un modelo relacionado con un algoritmo que sea bueno para examinar las causas y los resultados, como un modelo de árbol de decisión o un modelo Bayes naive.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-207">If you want to know why this is so, you can browse clusters and compare groups, or you might create a related model using an algorithm that is good at exploring causes and outcomes, such as a decision tree model or a Naïve Bayes model.</span></span>  
  
-   <span data-ttu-id="e1bbf-208">Si desea obtener una lista completa de atributos y de probabilidades para este clúster (o para todos los clústeres) puede crear una consulta.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-208">If you want to get a complete list of attributes and probabilities for this cluster (or all clusters) you can create a query.</span></span> <span data-ttu-id="e1bbf-209">Para obtener ejemplos de consultas en los modelos de agrupación en clústeres, vea [ejemplos de consultas de modelos de agrupación en clústeres](data-mining/clustering-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e1bbf-209">For examples of queries on clustering models, see [Clustering Model Query Examples](data-mining/clustering-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="e1bbf-210">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="e1bbf-210">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-discrimination"></a><a name="BKMK_ClusterDiscrimination"></a><span data-ttu-id="e1bbf-211">Distinción del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-211">Cluster Discrimination</span></span>  
 <span data-ttu-id="e1bbf-212">Utilice la pestaña **distinción del clúster** para comparar los atributos entre dos clústeres, o entre un clúster y todos los demás casos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-212">You use the **Cluster Discrimination** tab to compare attributes between two clusters, or between a cluster and all the other cases in the data set.</span></span>  
  
 <span data-ttu-id="e1bbf-213">Para resaltar las características de este visor, se comparará con las tablas en paralelo de Excel que se crearon en función de la vista **características del clúster** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-213">To highlight the features of this viewer, we'll compare it to the side-by-side tables in Excel that you created based on the **Cluster Characteristics** view.</span></span>  
  
##### <a name="explore-cluster-discrimination"></a><span data-ttu-id="e1bbf-214">Explorar la distinción del clúster</span><span class="sxs-lookup"><span data-stu-id="e1bbf-214">Explore cluster discrimination</span></span>  
  
1.  <span data-ttu-id="e1bbf-215">Utilice las listas **Clúster 1** y **Clúster 2** para seleccionar los clústeres que desea comparar.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-215">Use the **Cluster 1** and **Cluster 2** lists to select the clusters to compare.</span></span>  
  
    -   <span data-ttu-id="e1bbf-216">Para Clúster 1, seleccione Más de 65.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-216">For Cluster 1, select Over 65.</span></span>  
  
    -   <span data-ttu-id="e1bbf-217">Para Clúster 2, seleccione Bike Buyers.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-217">For Cluster 2, select Bike Buyers.</span></span>  
  
     <span data-ttu-id="e1bbf-218">La comparación debería tener una apariencia similar a la del gráfico siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1bbf-218">The comparison should look similar to the following graphic.</span></span>  
  
     <span data-ttu-id="e1bbf-219">![comparar los clústeres de un modelo](media/dm13-cluster-compareclusters.gif "comparar los clústeres de un modelo")</span><span class="sxs-lookup"><span data-stu-id="e1bbf-219">![comparing clusters in a model](media/dm13-cluster-compareclusters.gif "comparing clusters in a model")</span></span>  
  
     <span data-ttu-id="e1bbf-220">Tenga en cuenta que, en segundo plano, el visor de **distinción de clústeres** envía consultas complejas al servidor de minería de datos para extraer los atributos más importantes para distinguir entre los dos grupos, lo que facilita la comparación de dos conjuntos de clientes.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-220">Note that, under the covers, the **Cluster Discrimination** viewer sends complex queries to the data mining server, to extract the attributes that are most important in distinguishing between the two groups, making it easier to compare two sets of customers.</span></span>  
  
2.  <span data-ttu-id="e1bbf-221">Haga clic en una de las columnas **favorecer...** .</span><span class="sxs-lookup"><span data-stu-id="e1bbf-221">Click either of the **Favors...** columns.</span></span>  
  
     <span data-ttu-id="e1bbf-222">La barra a la derecha de la lista de atributos y valores muestra las características o valores que son más importantes como rasgos diferenciadores del clúster seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-222">The bar to the right of the attribute and value list shows which features or values are most important as a characteristic of the selected cluster.</span></span>  
  
3.  <span data-ttu-id="e1bbf-223">Ahora compare las listas de Excel.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-223">Now compare the lists in Excel.</span></span>  
  
     <span data-ttu-id="e1bbf-224">![Gráfico de redes de dependencias para un modelo de asociación](media/dm13-comparing-profiles-in-excel.gif "Gráfico de redes de dependencias para un modelo de asociación")</span><span class="sxs-lookup"><span data-stu-id="e1bbf-224">![Dependency network graph for an association model](media/dm13-comparing-profiles-in-excel.gif "Dependency network graph for an association model")</span></span>  
  
     <span data-ttu-id="e1bbf-225">Dado que las estadísticas subyacentes que se usaron para generar la imagen en el visor se guardan en Excel como tablas, puede filtrar y ordenar, y ver los valores reales de probabilidad.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-225">Because the underlying statistics that were used to build the image in the viewer are saved to Excel as tables, you can filter and sort, and view the actual probability values.</span></span>  
  
     <span data-ttu-id="e1bbf-226">Además de utilizar Excel, se recomienda que pruebe el visor de clústeres para Visio, el cual permite no solo ver los puntos de datos, sino también modificar y mejorar ampliamente el gráfico.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-226">In addition to using Excel, we recommend that you try the cluster viewer for Visio, which also allows you to not just view data points but also extensively modify and enhance the graph.</span></span> <span data-ttu-id="e1bbf-227">Para obtener más información, vea [tutorial del diagrama del clúster &#40;complementos de minería de datos&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e1bbf-227">For more information, see [Cluster Diagram Walkthrough &#40;Data Mining Add-ins&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span></span>  
  
 <span data-ttu-id="e1bbf-228">**Sugerencias**</span><span class="sxs-lookup"><span data-stu-id="e1bbf-228">**Tips**</span></span>  
  
 <span data-ttu-id="e1bbf-229">Después de obtener información sobre los grupos de clientes, pruebe a usar el [escenario de escenarios condicionales &#40;herramientas de análisis de tabla para excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) o el [escenario de búsqueda de objetivos &#40;herramientas de análisis de tabla para Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) herramientas para explorar los factores del modelo que podrían cambiarse para afectar al resultado.</span><span class="sxs-lookup"><span data-stu-id="e1bbf-229">After getting some insights into groups of customers, try using the [What-If Scenario &#40;Table Analysis Tools for Excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) or [Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) tools, to explore factors in the model that might be changed to affect the outcome.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bbf-230">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1bbf-230">See Also</span></span>  
 <span data-ttu-id="e1bbf-231">[Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="e1bbf-231">[Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="e1bbf-232">Asistente para clúster &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="e1bbf-232">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
  
