---
title: Ficha distinción de atributos (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.discrimination.f1
ms.assetid: 68323f23-121e-44fc-be85-6f9915d6d3c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: a8b0d4bc99b1c8f1c5de0269312f02eeb09df022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670166"
---
# <a name="attribute-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="a333f-102">Pestaña Distinción del atributo (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="a333f-102">Attribute Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="a333f-103">Utilice la pestaña **Distinción del atributo** para comparar los estados de los atributos de entrada y ver cómo se relacionan con el atributo de resultados.</span><span class="sxs-lookup"><span data-stu-id="a333f-103">Use the **Attribute Discrimination** tab to compare the states of the input attributes and see how they are related to the outcome attribute.</span></span> <span data-ttu-id="a333f-104">Los valores de atributo que permiten diferenciar en mayor medida los dos estados de atributo de predicción se enumeran en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a333f-104">The attribute values that make the most difference between the two selected predictable attribute states are listed first.</span></span>  
  
 <span data-ttu-id="a333f-105">**Para más información:** [Algoritmo Bayes naive de Microsoft](data-mining/microsoft-naive-bayes-algorithm.md), [Examinar un modelo usando el visor Bayes naive de Microsoft](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="a333f-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="a333f-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="a333f-106">Options</span></span>  
 <span data-ttu-id="a333f-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="a333f-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="a333f-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="a333f-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="a333f-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="a333f-109">**Mining Model**</span></span>  
 <span data-ttu-id="a333f-110">Elija un modelo de minería de datos de los de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="a333f-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="a333f-111">El modelo de minería de datos se abre automáticamente en el visor personalizado correcto.</span><span class="sxs-lookup"><span data-stu-id="a333f-111">The mining model automatically opens in the correct custom viewer.</span></span>  
  
 <span data-ttu-id="a333f-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="a333f-112">**Viewer**</span></span>  
 <span data-ttu-id="a333f-113">Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a333f-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="a333f-114">Para cada modelo, puede elegir el visor personalizado o el Visor de contenido de minería de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a333f-114">For each model, you can choose either the custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="a333f-115">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="a333f-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="a333f-116">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="a333f-116">**Attribute**</span></span>  
 <span data-ttu-id="a333f-117">Elija un atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="a333f-117">Choose a predictable attribute.</span></span>  
  
 <span data-ttu-id="a333f-118">**Valor 1**</span><span class="sxs-lookup"><span data-stu-id="a333f-118">**Value 1**</span></span>  
 <span data-ttu-id="a333f-119">Elija un estado del atributo de predicción para compararlo con el estado contenido en el **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="a333f-119">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span>  
  
 <span data-ttu-id="a333f-120">**Valor 2**</span><span class="sxs-lookup"><span data-stu-id="a333f-120">**Value 2**</span></span>  
 <span data-ttu-id="a333f-121">Seleccione un estado del atributo de predicción para compararlo con el estado contenido en el **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="a333f-121">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span> <span data-ttu-id="a333f-122">También puede seleccionar **todos los demás Estados** para comparar el valor de **valor 1** con su complemento, es decir, todos los demás valores excepto el valor 1.</span><span class="sxs-lookup"><span data-stu-id="a333f-122">You can also select **All Other States** to compare the value in **Value 1** with its complement-that is, all other values except Value 1.</span></span>  
  
 <span data-ttu-id="a333f-123">**Puntuaciones de distinción para \<Value 1> y\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="a333f-123">**Discrimination scores for \<Value 1> and \<Value 2>**</span></span>  
 <span data-ttu-id="a333f-124">El gráfico contiene las siguientes columnas, que describen cómo se relaciona el atributo de destino con los estados específicos del atributo de entrada.</span><span class="sxs-lookup"><span data-stu-id="a333f-124">The graph contains the following columns, which describe how the target attribute is related to specific states of the input attribute.</span></span>  
  
|<span data-ttu-id="a333f-125">Value</span><span class="sxs-lookup"><span data-stu-id="a333f-125">Value</span></span>|<span data-ttu-id="a333f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="a333f-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a333f-127">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="a333f-127">**Attributes**</span></span>|<span data-ttu-id="a333f-128">Un atributo de entrada en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a333f-128">An input attribute in the mining model.</span></span>|  
|<span data-ttu-id="a333f-129">**Valores**</span><span class="sxs-lookup"><span data-stu-id="a333f-129">**Values**</span></span>|<span data-ttu-id="a333f-130">Un estado del atributo que se incluye en **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="a333f-130">A state of the attribute that is listed in **Attributes**.</span></span>|  
|<span data-ttu-id="a333f-131">**Favorece\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="a333f-131">**Favors \<Value 1>**</span></span>|<span data-ttu-id="a333f-132">La barra indica si el atributo y valor actuales favorecen el resultado de destino seleccionado en **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="a333f-132">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 1**.</span></span>|  
|<span data-ttu-id="a333f-133">**Favorece\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="a333f-133">**Favors \<Value 2>**</span></span>|<span data-ttu-id="a333f-134">La barra indica si el atributo y valor actuales favorecen el resultado de destino seleccionado en **Valor 2.**</span><span class="sxs-lookup"><span data-stu-id="a333f-134">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a333f-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a333f-135">See Also</span></span>  
 <span data-ttu-id="a333f-136">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a333f-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="a333f-137">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a333f-137">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="a333f-138">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a333f-138">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
