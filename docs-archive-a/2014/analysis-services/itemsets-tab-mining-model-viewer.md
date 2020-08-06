---
title: Pestaña conjuntos (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.itemsets.f1
ms.assetid: 95b2b805-b142-4064-9c80-4b1b3fe2fe63
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b99b62b01b196fd62e1ef264e530487018f6a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669954"
---
# <a name="itemsets-tab-mining-model-viewer"></a><span data-ttu-id="49369-102">Pestaña Conjuntos de elementos (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="49369-102">Itemsets Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="49369-103">Puede utilizar el panel **Conjuntos de elementos** para ver los conjuntos de elementos frecuentes que contiene un modelo de minería de datos de reglas de asociación.</span><span class="sxs-lookup"><span data-stu-id="49369-103">You can use the **Itemsets** pane to view the frequent itemsets that an association rules mining model contains.</span></span> <span data-ttu-id="49369-104">Dado que un modelo de asociación puede contener muchos conjuntos de elementos, el visor dispone de controles para ayudarle a filtrar los conjuntos de elementos que se muestran en el visor.</span><span class="sxs-lookup"><span data-stu-id="49369-104">Because an association model can contain many itemsets, controls are provided in the viewer to help you filter the itemsets that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="49369-105">**Para obtener más información:** [Algoritmo de asociación de Microsoft](data-mining/microsoft-association-algorithm.md), [Examinar un modelo usando el Visor de reglas de asociación de Microsoft](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="49369-105">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="49369-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="49369-106">Options</span></span>  
 <span data-ttu-id="49369-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="49369-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="49369-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="49369-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="49369-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="49369-109">**Mining Model**</span></span>  
 <span data-ttu-id="49369-110">Elija esta opción para ver un modelo de minería de datos que se encuentra en la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="49369-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="49369-111">El modelo de minería de datos se abrirá en el visor asociado.</span><span class="sxs-lookup"><span data-stu-id="49369-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="49369-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="49369-112">**Viewer**</span></span>  
 <span data-ttu-id="49369-113">Elija un visor para ver el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="49369-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="49369-114">Puede utilizar el visor personalizado de los modelos de asociación o el visor de árbol de contenido genérico de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49369-114">You can use either the custom viewer for association models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="49369-115">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="49369-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="49369-116">**Soporte mínimo**</span><span class="sxs-lookup"><span data-stu-id="49369-116">**Minimum support**</span></span>  
 <span data-ttu-id="49369-117">Cambie este valor para establecer el soporte mínimo que un conjunto de elementos debe contener para aparecer en el visor.</span><span class="sxs-lookup"><span data-stu-id="49369-117">Change this value to set the minimum support that an itemset must contain to appear in the viewer.</span></span> <span data-ttu-id="49369-118">El valor predeterminado que se muestra al abrir el modelo por primera vez es calculado por el modelo, pero puede cambiarlo para ver más o menos conjuntos de elementos.</span><span class="sxs-lookup"><span data-stu-id="49369-118">The default value that is displayed when you first open the model is calculated by the model, but you can change it to see more or fewer itemsets.</span></span>  
  
 <span data-ttu-id="49369-119">**Tamaño mínimo del conjunto de elementos**</span><span class="sxs-lookup"><span data-stu-id="49369-119">**Minimum itemset size**</span></span>  
 <span data-ttu-id="49369-120">Cambie este valor para establecer el número mínimo de elementos que se debe incluir en un conjunto de elementos para que dicho el conjunto de elementos se pueda mostrar en el visor.</span><span class="sxs-lookup"><span data-stu-id="49369-120">Change this value to set the minimum number of items that must be included in an itemset before the itemset can be displayed in the viewer.</span></span>  
  
 <span data-ttu-id="49369-121">**Filtrar conjunto de elementos**</span><span class="sxs-lookup"><span data-stu-id="49369-121">**Filter Itemset**</span></span>  
 <span data-ttu-id="49369-122">Especifique un valor de cadena para filtrar el número de conjuntos de elementos que aparece en el visor.</span><span class="sxs-lookup"><span data-stu-id="49369-122">Type a string value to filter the number of itemsets that appear in the viewer.</span></span>  
  
 <span data-ttu-id="49369-123">También puede escribir expresiones regulares .NET como criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="49369-123">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="49369-124">Por ejemplo, la siguiente expresión devuelve todos los conjuntos de elementos que contienen 'Road Bottle Cage':</span><span class="sxs-lookup"><span data-stu-id="49369-124">For example, the following expression returns all itemsets that contain 'Road Bottle Cage':</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*`  
  
 <span data-ttu-id="49369-125">Observe que podría tener que actualizar la vista para ver los criterios de filtro aplicados.</span><span class="sxs-lookup"><span data-stu-id="49369-125">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="49369-126">También puede activar y desactivar la opción **Mostrar nombre largo** para actualizar la lista.</span><span class="sxs-lookup"><span data-stu-id="49369-126">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="49369-127">De forma predeterminada, los criterios de filtro se aplican a todo el nombre de la combinación de atributo-valor; por consiguiente, si solo está viendo el nombre del atributo, podría no ser obvio que los criterios de filtro se han aplicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="49369-127">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="49369-128">Utilice la lista desplegable **Mostrar** para seleccionar **Mostrar el valor y el nombre del atributo**, y compruebe que la lista de conjuntos de elementos se filtra correctamente.</span><span class="sxs-lookup"><span data-stu-id="49369-128">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="49369-129">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="49369-129">**Show**</span></span>  
 <span data-ttu-id="49369-130">Ajuste el modo en que desea que se muestre el conjunto de elementos en el visor.</span><span class="sxs-lookup"><span data-stu-id="49369-130">Adjust how the itemset is displayed in the viewer.</span></span> <span data-ttu-id="49369-131">Puede seleccionar una de las tres opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="49369-131">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="49369-132">Mostrar el valor y el nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="49369-132">Show attribute name and value</span></span>  
  
-   <span data-ttu-id="49369-133">Mostrar solo el valor del atributo</span><span class="sxs-lookup"><span data-stu-id="49369-133">Show attribute value only</span></span>  
  
-   <span data-ttu-id="49369-134">Mostrar solo el nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="49369-134">Show attribute name only</span></span>  
  
 <span data-ttu-id="49369-135">Observe que esta opción no consulta de nuevo el modelo; solo filtra los atributos o valores que se muestran.</span><span class="sxs-lookup"><span data-stu-id="49369-135">Note that this option does not requery the model; it only filters the attributes or values that are displayed.</span></span>  
  
 <span data-ttu-id="49369-136">**Mostrar nombre largo**</span><span class="sxs-lookup"><span data-stu-id="49369-136">**Show long name**</span></span>  
 <span data-ttu-id="49369-137">Seleccione esta opción para mostrar el nombre completo del conjunto de elementos tal como aparece en el contenido del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="49369-137">Select this option to display the full name of the itemset as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="49369-138">**Número máximo de filas**</span><span class="sxs-lookup"><span data-stu-id="49369-138">**Maximum rows**</span></span>  
 <span data-ttu-id="49369-139">Limite el número de conjuntos de elementos que se muestran en el visor.</span><span class="sxs-lookup"><span data-stu-id="49369-139">Limit the number of itemsets that are displayed in the viewer.</span></span> <span data-ttu-id="49369-140">De forma predeterminada, los conjuntos de elementos se clasifican por soporte en orden descendente, de modo que si se baja este valor, la lista se restringe a los conjuntos de elementos más comunes.</span><span class="sxs-lookup"><span data-stu-id="49369-140">By default, itemsets are ordered by support in descending order, so lowering this value restricts the list to the most common itemsets.</span></span>  
  
 <span data-ttu-id="49369-141">**Soporte técnico**</span><span class="sxs-lookup"><span data-stu-id="49369-141">**Support**</span></span>  
 <span data-ttu-id="49369-142">Muestra el soporte de cada conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="49369-142">Displays the support for each itemset.</span></span>  
  
 <span data-ttu-id="49369-143">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="49369-143">**Size**</span></span>  
 <span data-ttu-id="49369-144">Muestra el número de elementos que existe en cada conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="49369-144">Displays the number of items that exist in each itemset.</span></span>  
  
 <span data-ttu-id="49369-145">**Conjunto de elementos**</span><span class="sxs-lookup"><span data-stu-id="49369-145">**Itemset**</span></span>  
 <span data-ttu-id="49369-146">Muestra la descripción de cada conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="49369-146">Displays the description of each itemset.</span></span> <span data-ttu-id="49369-147">De forma predeterminada, los conjuntos de elementos se presentan en una lista de atributos y sus valores delimitada por comas.</span><span class="sxs-lookup"><span data-stu-id="49369-147">By default, itemsets are presented as a comma-delimited list of attributes and their values.</span></span> <span data-ttu-id="49369-148">Puede cambiar la manera en que se muestran utilizando la opción **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="49369-148">You can change the way they are displayed by using the **Show** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49369-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49369-149">See Also</span></span>  
 <span data-ttu-id="49369-150">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="49369-150">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="49369-151">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="49369-151">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="49369-152">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="49369-152">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
