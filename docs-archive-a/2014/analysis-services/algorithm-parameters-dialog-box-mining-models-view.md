---
title: Cuadro de diálogo parámetros de algoritmo (vista modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.models.algorithmparameters.f1
helpviewer_keywords:
- Algorithm Parameters dialog box
ms.assetid: 57f9f6f8-8ca4-4a6e-8f18-85f0571b7060
author: minewiskan
ms.author: owend
ms.openlocfilehash: 303d8b5bd3437690c65873e106a94cf2ce8eb9f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670216"
---
# <a name="algorithm-parameters-dialog-box-mining-models-view"></a><span data-ttu-id="79e1c-102">Parámetros de algoritmo (vista Modelos de minería de datos, cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="79e1c-102">Algorithm Parameters Dialog Box (Mining Models View)</span></span>
  <span data-ttu-id="79e1c-103">Utilice el cuadro de diálogo **Parámetros de algoritmo** para ajustar parámetros de algoritmo específicos del modelo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="79e1c-103">Use the **Algorithm Parameters** dialog box to adjust algorithm parameters that are specific to the selected model.</span></span> <span data-ttu-id="79e1c-104">Al cambiar un parámetro de algoritmo, normalmente cambiará los resultados del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="79e1c-104">When you change an algorithm parameter, you will usually change the results of the mining model.</span></span> <span data-ttu-id="79e1c-105">La manera en que cada parámetro afecta a los resultados depende del algoritmo que se use y de los datos.</span><span class="sxs-lookup"><span data-stu-id="79e1c-105">The way that each parameter affects the results depends on the algorithm you are using, and on your data.</span></span> <span data-ttu-id="79e1c-106">Para más información, vea [Personalizar la estructura y los modelos de minería de datos](data-mining/customize-mining-models-and-structure.md).</span><span class="sxs-lookup"><span data-stu-id="79e1c-106">For more information, see [Customize Mining Models and Structure](data-mining/customize-mining-models-and-structure.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="79e1c-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="79e1c-107">Options</span></span>  
 <span data-ttu-id="79e1c-108">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="79e1c-108">**Parameters**</span></span>  
 <span data-ttu-id="79e1c-109">Enumera los parámetros disponibles para el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="79e1c-109">Lists the parameters that are available for the selected mining model.</span></span>  
  
 <span data-ttu-id="79e1c-110">La siguiente lista describe las columnas disponibles.</span><span class="sxs-lookup"><span data-stu-id="79e1c-110">The following list describes the available columns.</span></span>  
  
|<span data-ttu-id="79e1c-111">Columna</span><span class="sxs-lookup"><span data-stu-id="79e1c-111">Column</span></span>|<span data-ttu-id="79e1c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="79e1c-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="79e1c-113">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="79e1c-113">**Parameter**</span></span>|<span data-ttu-id="79e1c-114">Especifica el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="79e1c-114">List the name of the parameter.</span></span>|  
|<span data-ttu-id="79e1c-115">**Valor**</span><span class="sxs-lookup"><span data-stu-id="79e1c-115">**Value**</span></span>|<span data-ttu-id="79e1c-116">Especifique un valor únicamente si desea cambiar el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="79e1c-116">Enter a value only if you want to change the default value of the parameter.</span></span>|  
|<span data-ttu-id="79e1c-117">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="79e1c-117">**Default**</span></span>|<span data-ttu-id="79e1c-118">Especifica el valor predeterminado del parámetro que utilizará el algoritmo si no indica un valor en la columna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="79e1c-118">List the default value of the parameter that the algorithm will use if you do not supply a value in the **Value** column.</span></span>|  
|<span data-ttu-id="79e1c-119">**Range**</span><span class="sxs-lookup"><span data-stu-id="79e1c-119">**Range**</span></span>|<span data-ttu-id="79e1c-120">Especifique el intervalo de valores posibles que puede indicar en la columna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="79e1c-120">List the range of possible values that you can enter into the **Value** column.</span></span> <span data-ttu-id="79e1c-121">Los intervalos pueden ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="79e1c-121">The ranges can be one of the following:</span></span><br /><br /> <span data-ttu-id="79e1c-122">Una lista discreta, como 1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="79e1c-122">A discrete list, such as 1, 2, 3</span></span><br /><br /> <span data-ttu-id="79e1c-123">Un intervalo inclusivo, como [0, 100]</span><span class="sxs-lookup"><span data-stu-id="79e1c-123">An inclusive range, such as [0, 100]</span></span><br /><br /> <span data-ttu-id="79e1c-124">Un intervalo exclusivo, como (0,...)</span><span class="sxs-lookup"><span data-stu-id="79e1c-124">An exclusive range, such as (0,...)</span></span><br /><br /> <span data-ttu-id="79e1c-125">Una combinación, como [0,...)</span><span class="sxs-lookup"><span data-stu-id="79e1c-125">A combination, such as [0,...)</span></span>|  
  
 <span data-ttu-id="79e1c-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="79e1c-126">**Description**</span></span>  
 <span data-ttu-id="79e1c-127">Describe el parámetro seleccionado en la lista **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="79e1c-127">Describes the selected parameter in the **Parameters** list.</span></span>  
  
 <span data-ttu-id="79e1c-128">**Add**</span><span class="sxs-lookup"><span data-stu-id="79e1c-128">**Add**</span></span>  
 <span data-ttu-id="79e1c-129">Haga clic para agregar a la lista parámetros específicos de algoritmo adicionales.</span><span class="sxs-lookup"><span data-stu-id="79e1c-129">Click to add additional, algorithm specific-parameters to the list.</span></span> <span data-ttu-id="79e1c-130">Después de agregar el parámetro, puede indicar el nombre correcto en la columna **Parámetro** y proporcionar un valor en la columna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="79e1c-130">After adding the parameter, you can enter the correct name in the **Parameter** column and provide a value in the **Value** column.</span></span>  
  
 <span data-ttu-id="79e1c-131">**Remove**</span><span class="sxs-lookup"><span data-stu-id="79e1c-131">**Remove**</span></span>  
 <span data-ttu-id="79e1c-132">Haga clic para eliminar un parámetro personalizado de la lista.</span><span class="sxs-lookup"><span data-stu-id="79e1c-132">Click to delete a custom parameter from the list.</span></span>  
  
 <span data-ttu-id="79e1c-133">Si elimina uno de los parámetros estándar de algoritmo de Analysis Services de la lista, el parámetro todavía se utilizará en el modelo, pero con los valores predeterminados para ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="79e1c-133">If you delete one of the standard Analysis Services algorithm parameters from the list, the parameter will still be used in the model, but with the default values for that parameter.</span></span> <span data-ttu-id="79e1c-134">El parámetro no se elimina permanentemente y aparecerá la próxima vez que abra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="79e1c-134">The parameter is not permanently deleted and will appear the next time that you open the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e1c-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79e1c-135">See Also</span></span>  
 <span data-ttu-id="79e1c-136">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="79e1c-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="79e1c-137">[Vista modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-models-view-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="79e1c-137">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="79e1c-138">Mover objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="79e1c-138">Moving Data Mining Objects</span></span>](data-mining/moving-data-mining-objects.md)  
  
  
