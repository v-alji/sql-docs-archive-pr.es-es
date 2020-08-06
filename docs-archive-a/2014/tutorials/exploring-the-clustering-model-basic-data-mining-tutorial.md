---
title: Explorar el modelo de agrupación en clústeres (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ce8aa034-161b-473f-baec-9c29e0a8e5f5
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cca9d395fece59f607c8faf209128b9d32663a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751618"
---
# <a name="exploring-the-clustering-model-basic-data-mining-tutorial"></a><span data-ttu-id="d517d-102">Explorar el modelo de agrupación en clústeres (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="d517d-102">Exploring the Clustering Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="d517d-103">El [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de clústeres agrupa los casos en clústeres que contienen características similares.</span><span class="sxs-lookup"><span data-stu-id="d517d-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm groups cases into clusters that contain similar characteristics.</span></span> <span data-ttu-id="d517d-104">Estas agrupaciones son útiles para la exploración de datos, la identificación de anomalías en los datos y la creación de predicciones.</span><span class="sxs-lookup"><span data-stu-id="d517d-104">These groupings are useful for exploring data, identifying anomalies in the data, and creating predictions.</span></span>  
  
 <span data-ttu-id="d517d-105">El Visor de clústeres de [!INCLUDE[msCoName](../includes/msconame-md.md)] ofrece las siguientes pestañas para la exploración de modelos de minería de datos de agrupación en clústeres:</span><span class="sxs-lookup"><span data-stu-id="d517d-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster Viewer provides the following tabs for use in exploring clustering mining models:</span></span>  
  

  
##  <a name="cluster-diagram-tab"></a><a name="ClusterDiagramTab"></a><span data-ttu-id="d517d-106">Pestaña diagrama del clúster</span><span class="sxs-lookup"><span data-stu-id="d517d-106">Cluster Diagram Tab</span></span>  
 <span data-ttu-id="d517d-107">La pestaña Diagrama del clúster muestra todos los clústeres de un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d517d-107">The Cluster Diagram tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="d517d-108">Las líneas entre los clústeres representan la "proximidad" y aparecen sombreadas en función de la similitud entre los clústeres.</span><span class="sxs-lookup"><span data-stu-id="d517d-108">The lines between the clusters represent "closeness" and are shaded based on how similar the clusters are.</span></span> <span data-ttu-id="d517d-109">El color de cada clúster representa la frecuencia de la variable y el estado del clúster.</span><span class="sxs-lookup"><span data-stu-id="d517d-109">The actual color of each cluster represents the frequency of the variable and the state in the cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-diagram-tab"></a><span data-ttu-id="d517d-110">Para explorar el modelo en la pestaña Diagrama del clúster</span><span class="sxs-lookup"><span data-stu-id="d517d-110">To explore the model in the Cluster Diagram tab</span></span>  
  
1.  <span data-ttu-id="d517d-111">Utilice la lista **modelo de minería de datos** en la parte superior de la pestaña visor de modelos de minería de **datos** para cambiar al `TM_Clustering` modelo.</span><span class="sxs-lookup"><span data-stu-id="d517d-111">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_Clustering` model.</span></span>  
  
2.  <span data-ttu-id="d517d-112">En la lista **visor** , seleccione **visor de clústeres de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d517d-112">In the **Viewer** list, select **Microsoft Cluster Viewer**.</span></span>  
  
3.  <span data-ttu-id="d517d-113">En el cuadro **variable de sombreado** , seleccione **Bike Buyer**.</span><span class="sxs-lookup"><span data-stu-id="d517d-113">In the **Shading Variable** box, select **Bike Buyer**.</span></span>  
  
     <span data-ttu-id="d517d-114">La variable predeterminada es **Population**, pero puede cambiarla a cualquier atributo del modelo para detectar qué clústeres contienen miembros que tienen los atributos que desea.</span><span class="sxs-lookup"><span data-stu-id="d517d-114">The default variable is **Population**, but you can change this to any attribute in the model, to discover which clusters contain members that have the attributes you want.</span></span>  
  
4.  <span data-ttu-id="d517d-115">Seleccione **1** en el cuadro **Estado** para explorar los casos en los que se compró una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="d517d-115">Select **1** in the **State** box to explore those cases where a bike was purchased.</span></span>  
  
     <span data-ttu-id="d517d-116">La leyenda de **densidad** describe la densidad del par de estado de atributo seleccionado en la variable de sombreado y el estado.</span><span class="sxs-lookup"><span data-stu-id="d517d-116">The **Density** legend describes the density of the attribute state pair selected in the Shading Variable and the State.</span></span> <span data-ttu-id="d517d-117">En este ejemplo, nos indica que el clusterwith el sombreado más oscuro tiene el porcentaje más alto de compradores de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="d517d-117">In this example it tells us that the clusterwith the darkest shading has the highest percentage of bike buyers.</span></span>  
  
5.  <span data-ttu-id="d517d-118">Pause su mouse sobre el clúster con el sombreado más oscuro.</span><span class="sxs-lookup"><span data-stu-id="d517d-118">Pause your mouse over the cluster with the darkest shading.</span></span>  
  
     <span data-ttu-id="d517d-119">Una información sobre herramientas muestra el porcentaje de casos que tienen el atributo, `Bike Buyer = 1`.</span><span class="sxs-lookup"><span data-stu-id="d517d-119">A tooltip displays the percentage of cases that have the attribute, `Bike Buyer = 1`.</span></span>  
  
6.  <span data-ttu-id="d517d-120">Seleccione el clúster que tiene la mayor densidad, haga clic con el botón derecho en el clúster, seleccione **cambiar nombre de clúster** y escriba Bike buyers **High** para una identificación posterior.</span><span class="sxs-lookup"><span data-stu-id="d517d-120">Select the cluster that has the highest density, right-click the cluster, select **Rename Cluster** and type **Bike Buyers High** for later identification.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="d517d-121">Busque el clúster que tiene el sombreado más ligero (y la densidad más baja).</span><span class="sxs-lookup"><span data-stu-id="d517d-121">Find the cluster that has the lightest shading (and the lowest density).</span></span> <span data-ttu-id="d517d-122">Haga clic con el botón derecho en el clúster, seleccione **cambiar nombre de clúster** y escriba Bike buyers **Low**.</span><span class="sxs-lookup"><span data-stu-id="d517d-122">Right-click the cluster, select **Rename Cluster** and type **Bike Buyers Low**.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="d517d-123">Haga clic en el clúster Bike buyers **High** y arrástrelo hasta un área del panel que le proporcionará una vista clara de sus conexiones a los otros clústeres.</span><span class="sxs-lookup"><span data-stu-id="d517d-123">Click the **Bike Buyers High** cluster and drag it to an area of the pane that will give you a clear view of its connections to the other clusters.</span></span>  
  
     <span data-ttu-id="d517d-124">Al seleccionar un clúster, se resaltan las líneas que conectan este clúster con otros para que pueda ver todas las relaciones existentes para el mismo.</span><span class="sxs-lookup"><span data-stu-id="d517d-124">When you select a cluster, the lines that connect this cluster to other clusters are highlighted, so that you can easily see all the relationships for this cluster.</span></span> <span data-ttu-id="d517d-125">Cuando el clúster no está seleccionado, puede saber por la oscuridad de las líneas la intensidad de las relaciones entre todos los clústeres del diagrama.</span><span class="sxs-lookup"><span data-stu-id="d517d-125">When the cluster is not selected, you can tell by the darkness of the lines how strong the relationships are amongst all the clusters in the diagram.</span></span> <span data-ttu-id="d517d-126">Si el sombreado es claro o inexistente, los clústeres no son muy similares.</span><span class="sxs-lookup"><span data-stu-id="d517d-126">If the shading is light or nonexistent, the clusters are not very similar.</span></span>  
  
9. <span data-ttu-id="d517d-127">Use el control deslizante situado en la parte izquierda de la red para filtrar los vínculos de menor intensidad y encontrar los clústeres con las relaciones más próximas.</span><span class="sxs-lookup"><span data-stu-id="d517d-127">Use the slider to the left of the network, to filter out the weaker links and find the clusters with the closest relationships.</span></span> <span data-ttu-id="d517d-128">El departamento comercial de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] podría desear combinar los clústeres similares al determinar el mejor método para entregar el envío de correo directo.</span><span class="sxs-lookup"><span data-stu-id="d517d-128">The [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department might want to combine similar clusters together when determining the best method for delivering the targeted mailing.</span></span>  
  

  
##  <a name="cluster-profiles-tab"></a><a name="ClusterProfilesTab"></a><span data-ttu-id="d517d-129">Pestaña perfiles del clúster</span><span class="sxs-lookup"><span data-stu-id="d517d-129">Cluster Profiles Tab</span></span>  
 <span data-ttu-id="d517d-130">La pestaña **perfiles del clúster** proporciona una vista general del `TM_Clustering` modelo.</span><span class="sxs-lookup"><span data-stu-id="d517d-130">The **Cluster Profiles** tab provides an overall view of the `TM_Clustering` model.</span></span> <span data-ttu-id="d517d-131">La pestaña **perfiles del clúster** contiene una columna para cada clúster del modelo.</span><span class="sxs-lookup"><span data-stu-id="d517d-131">The **Cluster Profiles** tab contains a column for each cluster in the model.</span></span> <span data-ttu-id="d517d-132">La primera columna enumera los atributos asociados a un clúster como mínimo.</span><span class="sxs-lookup"><span data-stu-id="d517d-132">The first column lists the attributes that are associated with at least one cluster.</span></span> <span data-ttu-id="d517d-133">El resto del visor contiene la distribución de estados de un atributo por cada clúster.</span><span class="sxs-lookup"><span data-stu-id="d517d-133">The rest of the viewer contains the distribution of the states of an attribute for each cluster.</span></span> <span data-ttu-id="d517d-134">La distribución de una variable discreta se muestra como una barra de color con el número máximo de barras que se muestran en la lista de **barras de histograma** .</span><span class="sxs-lookup"><span data-stu-id="d517d-134">The distribution of a discrete variable is shown as a colored bar with the maximum number of bars displayed in the **Histogram bars** list.</span></span> <span data-ttu-id="d517d-135">Los atributos continuos se muestran con un diagrama de rombo, que representa la desviación media y estándar en cada clúster.</span><span class="sxs-lookup"><span data-stu-id="d517d-135">Continuous attributes are displayed with a diamond chart, which represents the mean and standard deviation in each cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-profiles-tab"></a><span data-ttu-id="d517d-136">Para explorar el modelo en la pestaña perfiles del clúster</span><span class="sxs-lookup"><span data-stu-id="d517d-136">To explore the model in the Cluster Profiles tab</span></span>  
  
1.  <span data-ttu-id="d517d-137">Establezca barras de **histograma** en **5**.</span><span class="sxs-lookup"><span data-stu-id="d517d-137">Set **Histogram** bars to **5**.</span></span>  
  
     <span data-ttu-id="d517d-138">En nuestro modelo, 5 es el número máximo de estados para cualquier variable.</span><span class="sxs-lookup"><span data-stu-id="d517d-138">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
2.  <span data-ttu-id="d517d-139">Si la **leyenda de minería de datos** bloquea la presentación de los **perfiles de atributo**, muévalo fuera del camino.</span><span class="sxs-lookup"><span data-stu-id="d517d-139">If the **Mining Legend** blocks the display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="d517d-140">Seleccione la columna Bike buyers **High** y arrástrela hacia la derecha de la columna **Population** .</span><span class="sxs-lookup"><span data-stu-id="d517d-140">Select the **Bike Buyers High** column and drag it to the right of the **Population** column.</span></span>  
  
4.  <span data-ttu-id="d517d-141">Seleccione la columna Bike buyers **Low** y arrástrela a la derecha de la columna Bike buyers **High** .</span><span class="sxs-lookup"><span data-stu-id="d517d-141">Select the **Bike Buyers Low** column and drag it to the right of the **Bike Buyers High** column.</span></span>  
  
5.  <span data-ttu-id="d517d-142">Haga clic en la columna Bike buyers **High** .</span><span class="sxs-lookup"><span data-stu-id="d517d-142">Click the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="d517d-143">La columna **variables** se ordena por orden de importancia para ese clúster.</span><span class="sxs-lookup"><span data-stu-id="d517d-143">The **Variables** column is sorted in order of importance for that cluster.</span></span> <span data-ttu-id="d517d-144">Desplácese por la columna y revise las características del clúster Bike Buyer High.</span><span class="sxs-lookup"><span data-stu-id="d517d-144">Scroll through the column and review characteristics of the Bike Buyer High cluster.</span></span> <span data-ttu-id="d517d-145">Por ejemplo, es muy probable que en todas ellas la característica común sea que la distancia al trabajo sea corta.</span><span class="sxs-lookup"><span data-stu-id="d517d-145">For example, they are more likely to have a short commute.</span></span>  
  
6.  <span data-ttu-id="d517d-146">Haga doble clic en la celda **Age** de la columna Bike buyers **High** .</span><span class="sxs-lookup"><span data-stu-id="d517d-146">Double-click the **Age** cell in the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="d517d-147">La **leyenda de minería de datos** muestra una vista más detallada y puede ver el intervalo de edad de estos clientes, así como la edad media.</span><span class="sxs-lookup"><span data-stu-id="d517d-147">The **Mining Legend** displays a more detailed view and you can see the age range of these customers as well as the mean age.</span></span>  
  
7.  <span data-ttu-id="d517d-148">Haga clic con el botón secundario en la columna Bike buyers **Low** y seleccione **Ocultar columna**.</span><span class="sxs-lookup"><span data-stu-id="d517d-148">Right-click the **Bike Buyers Low** column and select **Hide Column**.</span></span>  
  

  
##  <a name="cluster-characteristics-tab"></a><a name="ClusterCharacteristicsTab"></a><span data-ttu-id="d517d-149">Pestaña características del clúster</span><span class="sxs-lookup"><span data-stu-id="d517d-149">Cluster Characteristics Tab</span></span>  
 <span data-ttu-id="d517d-150">Con la pestaña **características del clúster** , puede examinar con más detalle las características que componen un clúster.</span><span class="sxs-lookup"><span data-stu-id="d517d-150">With the **Cluster Characteristics** tab, you can examine in more detail the characteristics that make up a cluster.</span></span> <span data-ttu-id="d517d-151">En lugar de comparar las características de todos los clústeres (como en la pestaña Perfiles del clúster), puede explorar un clúster a la vez.</span><span class="sxs-lookup"><span data-stu-id="d517d-151">Instead of comparing the characteristics of all of the clusters (as in the Cluster Profiles tab), you can explore one cluster at a time.</span></span> <span data-ttu-id="d517d-152">Por ejemplo, si selecciona Bike buyers **High** en la lista de **clústeres** , puede ver las características de los clientes en este clúster.</span><span class="sxs-lookup"><span data-stu-id="d517d-152">For example, if you select **Bike Buyers High** from the **Cluster** list, you can see the characteristics of the customers in this cluster.</span></span> <span data-ttu-id="d517d-153">Aunque la presentación es diferente del visor Perfiles del clúster, los resultados son los mismos.</span><span class="sxs-lookup"><span data-stu-id="d517d-153">Though the display is different from the Cluster Profiles viewer, the findings are the same.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d517d-154">A menos que establezca un valor inicial para **holdoutseed**, los resultados variarán cada vez que procese el modelo.</span><span class="sxs-lookup"><span data-stu-id="d517d-154">Unless you set an initial value for **holdoutseed**, results will vary each time you process the model.</span></span> <span data-ttu-id="d517d-155">Para obtener más información, vea [elemento HoldoutSeed](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span><span class="sxs-lookup"><span data-stu-id="d517d-155">For more information, see [HoldoutSeed Element](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span></span>  
  

  
##  <a name="cluster-discrimination-tab"></a><a name="ClusterDiscriminationTab"></a><span data-ttu-id="d517d-156">Pestaña distinción del clúster</span><span class="sxs-lookup"><span data-stu-id="d517d-156">Cluster Discrimination Tab</span></span>  
 <span data-ttu-id="d517d-157">Con la pestaña **distinción del clúster** , puede explorar las características que distinguen a un clúster de otro.</span><span class="sxs-lookup"><span data-stu-id="d517d-157">With the **Cluster Discrimination** tab, you can explore the characteristics that distinguish one cluster from another.</span></span> <span data-ttu-id="d517d-158">Después de seleccionar dos clústeres, uno de la lista **clúster 1** y otro de la lista **clúster 2** , el visor calcula las diferencias entre los clústeres y muestra una lista de los atributos que distinguen los clústeres.</span><span class="sxs-lookup"><span data-stu-id="d517d-158">After you select two clusters, one from the **Cluster 1** list, and one from the **Cluster 2** list, the viewer calculates the differences between the clusters and displays a list of the attributes that distinguish the clusters most.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-discrimination-tab"></a><span data-ttu-id="d517d-159">Para explorar el modelo en la pestaña distinción del clúster</span><span class="sxs-lookup"><span data-stu-id="d517d-159">To explore the model in the Cluster Discrimination tab</span></span>  
  
1.  <span data-ttu-id="d517d-160">En el cuadro **clúster 1** , seleccione **Bike**buyers High.</span><span class="sxs-lookup"><span data-stu-id="d517d-160">In the **Cluster 1** box, select **Bike Buyers High**.</span></span>  
  
2.  <span data-ttu-id="d517d-161">En el cuadro **clúster 2** , seleccione **Bike**buyers Low.</span><span class="sxs-lookup"><span data-stu-id="d517d-161">In the **Cluster 2** box, select **Bike Buyers Low**.</span></span>  
  
3.  <span data-ttu-id="d517d-162">Haga clic en **variables** para ordenar alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="d517d-162">Click **Variables** to sort alphabetically.</span></span>  
  
     <span data-ttu-id="d517d-163">Algunas de las diferencias sustanciales entre los clientes de los clústeres de Bike buyers **Low** y Bike buyers **High** son la edad, la propiedad de los automóviles, el número de hijos y la región.</span><span class="sxs-lookup"><span data-stu-id="d517d-163">Some of the more substantial differences among the customers in the **Bike Buyers Low** and **Bike Buyers High** clusters include age, car ownership, number of children, and region.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d517d-164">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d517d-164">Related Tasks</span></span>  
 <span data-ttu-id="d517d-165">Vea los temas siguientes para explorar los demás modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d517d-165">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="d517d-166">Explorar el modelo de árbol de decisión &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d517d-166">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="d517d-167">Explorar el modelo Bayes Naive &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d517d-167">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d517d-168">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="d517d-168">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d517d-169">Explorar el modelo Bayes Naive &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d517d-169">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="d517d-170">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="d517d-170">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="d517d-171">Explorar el modelo de árbol de decisión &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d517d-171">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="d517d-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d517d-172">See Also</span></span>  
 <span data-ttu-id="d517d-173">[Examinar un modelo usando el visor de clústeres de Microsoft](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d517d-173">[Browse a Model Using the Microsoft Cluster Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span></span>  
 <span data-ttu-id="d517d-174">[Pestaña distinción del clúster &#40;visor de modelos de minería de datos&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d517d-174">[Cluster Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="d517d-175">[Pestaña perfiles del clúster &#40;visor de modelos de minería de datos&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d517d-175">[Cluster Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="d517d-176">[Pestaña características del clúster &#40;visor de modelos de minería de datos&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d517d-176">[Cluster Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="d517d-177">Pestaña diagrama del clúster &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d517d-177">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/cluster-diagram-tab-mining-model-viewer.md)  
  
  
