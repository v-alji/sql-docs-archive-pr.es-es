---
title: Pestaña perfiles de atributo (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.profiles.f1
ms.assetid: 17c7e7ae-273c-4a6b-9a35-e8b9b8e65999
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61c81b95f030bf1a69aed165bd64e58ff9af8339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670161"
---
# <a name="attribute-profiles-tab-mining-model-viewer"></a><span data-ttu-id="6cbed-102">Pestaña Perfiles del atributo (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="6cbed-102">Attribute Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="6cbed-103">Utilice la pestaña **Perfiles del atributo** para ver cómo la distribución de los valores de entrada en un estado del modelo Bayes naive contribuye a cada estado del atributo de resultados.</span><span class="sxs-lookup"><span data-stu-id="6cbed-103">Use the **Attribute Profiles** tab to see how the distribution of input values in a Naive Bayes model state contribute to each state of the outcome attribute.</span></span> <span data-ttu-id="6cbed-104">La distribución de los valores se muestra como un histograma con colores, todas las distribuciones se presentan en un formato tabular, para facilitar la comparación de los valores.</span><span class="sxs-lookup"><span data-stu-id="6cbed-104">The distribution of values is shown as a colored histogram, all distributions presented in a tabular format, to make it easier to compare values.</span></span>  
  
 <span data-ttu-id="6cbed-105">**Para más información:** [Algoritmo Bayes naive de Microsoft](data-mining/microsoft-naive-bayes-algorithm.md), [Examinar un modelo usando el visor Bayes naive de Microsoft](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="6cbed-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="6cbed-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="6cbed-106">Options</span></span>  
 <span data-ttu-id="6cbed-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="6cbed-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="6cbed-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="6cbed-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="6cbed-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="6cbed-109">**Mining Model**</span></span>  
 <span data-ttu-id="6cbed-110">Elija un modelo de minería de datos que desea ver de los modelos de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="6cbed-110">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="6cbed-111">El modelo de minería de datos se abrirá en el visor asociado.</span><span class="sxs-lookup"><span data-stu-id="6cbed-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="6cbed-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="6cbed-112">**Viewer**</span></span>  
 <span data-ttu-id="6cbed-113">Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6cbed-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="6cbed-114">Puede elegir el visor personalizado proporcionado para cada modelo de minería de datos o el Visor de contenido de minería de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cbed-114">You can choose the custom viewer provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="6cbed-115">También puede usar visores de complemento, si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="6cbed-115">You can also use plug-in viewers if they are available.</span></span>  
  
 <span data-ttu-id="6cbed-116">**Mostrar leyenda**</span><span class="sxs-lookup"><span data-stu-id="6cbed-116">**Show Legend**</span></span>  
 <span data-ttu-id="6cbed-117">Seleccione esta opción para mostrar una clave que haga coincidir cada valor de **Estados** con uno de los colores usados en el gráfico de distribución.</span><span class="sxs-lookup"><span data-stu-id="6cbed-117">Select this option to display a key that matches each value in **States** to one of the colors used in the distribution chart.</span></span>  
  
 <span data-ttu-id="6cbed-118">**Barras de histograma**</span><span class="sxs-lookup"><span data-stu-id="6cbed-118">**Histogram bars**</span></span>  
 <span data-ttu-id="6cbed-119">Seleccione la cantidad de barras que se incluirán en el histograma.</span><span class="sxs-lookup"><span data-stu-id="6cbed-119">Select how many bars to include in the histogram.</span></span> <span data-ttu-id="6cbed-120">Si existen más barras de las que eligió mostrar, se retienen las barras de la importancia más alta y el resto de las barras se agrupa en **Otro**.</span><span class="sxs-lookup"><span data-stu-id="6cbed-120">If more bars exist than you choose to display, the bars of highest importance are retained, and the remaining bars are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="6cbed-121">**Predicción**</span><span class="sxs-lookup"><span data-stu-id="6cbed-121">**Predictable**</span></span>  
 <span data-ttu-id="6cbed-122">Seleccione una columna de predicción del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbed-122">Select a predictable column from the mining model.</span></span>  
  
 <span data-ttu-id="6cbed-123">**Perfiles del atributo**</span><span class="sxs-lookup"><span data-stu-id="6cbed-123">**Attribute Profiles**</span></span>  
 <span data-ttu-id="6cbed-124">La tabla contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cbed-124">The table contains the following columns:</span></span>  
  
|<span data-ttu-id="6cbed-125">Value</span><span class="sxs-lookup"><span data-stu-id="6cbed-125">Value</span></span>|<span data-ttu-id="6cbed-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="6cbed-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6cbed-127">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="6cbed-127">**Attributes**</span></span>|<span data-ttu-id="6cbed-128">Muestra las columnas del modelo de minería de datos contenidas en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbed-128">Lists the mining model columns contained within the mining model.</span></span>|  
|<span data-ttu-id="6cbed-129">**States**</span><span class="sxs-lookup"><span data-stu-id="6cbed-129">**States**</span></span>|<span data-ttu-id="6cbed-130">Una columna opcional que describe el estado que representa el color en la fila de atributos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6cbed-130">An optional column that describes what state the color in the corresponding row of attributes represents.</span></span> <span data-ttu-id="6cbed-131">Agregue o quite mediante la casilla **Mostrar leyenda** .</span><span class="sxs-lookup"><span data-stu-id="6cbed-131">Add or remove by using the **Show Legend** check box.</span></span>|  
|<span data-ttu-id="6cbed-132">**Llenado**</span><span class="sxs-lookup"><span data-stu-id="6cbed-132">**Population**</span></span>|<span data-ttu-id="6cbed-133">Muestra la distribución del atributo en todo el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbed-133">Displays the distribution of the attribute across the whole dataset.</span></span>|  
|<span data-ttu-id="6cbed-134">**Columna para estados de atributo de predicción**</span><span class="sxs-lookup"><span data-stu-id="6cbed-134">**Column for states of predictable attribute**</span></span>|<span data-ttu-id="6cbed-135">Muestra una columna para cada estado de la columna de predicción, con cada fila correspondiente a un atributo de entrada en el modelo.</span><span class="sxs-lookup"><span data-stu-id="6cbed-135">Displays a column for each state of the predictable column, with each row corresponding to an input attribute in the model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6cbed-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6cbed-136">See Also</span></span>  
 <span data-ttu-id="6cbed-137">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6cbed-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="6cbed-138">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="6cbed-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="6cbed-139">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6cbed-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
