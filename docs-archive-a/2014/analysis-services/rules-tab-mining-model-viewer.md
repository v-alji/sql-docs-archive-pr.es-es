---
title: Pestaña reglas (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.rules.f1
ms.assetid: 705d5492-b58f-45d9-94d7-ed57b7025823
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0d86931865fd9352074669de93b14dacfc84537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669920"
---
# <a name="rules-tab-mining-model-viewer"></a><span data-ttu-id="31161-102">Pestaña Reglas (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="31161-102">Rules Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="31161-103">Utilice el panel **Reglas** en un modelo de asociación para ver las reglas que el algoritmo extrajo de los datos.</span><span class="sxs-lookup"><span data-stu-id="31161-103">Use the **Rules** pane in an association model to view the rules that the algorithm extracted from the data.</span></span> <span data-ttu-id="31161-104">Las reglas describen cómo se relacionan los elementos entre sí, y se pueden utilizar para crear recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="31161-104">Rules describe how items are related to each other, and can be used to create recommendations.</span></span>  
  
 <span data-ttu-id="31161-105">Puede utilizar las opciones del visor para filtrar el número de reglas que se muestra en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-105">You can use the options in the viewer to filter the number of rules that are displayed in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="31161-106">De forma predeterminada, solo las reglas que están por encima del umbral de probabilidad definidas en **Probabilidad mínima** se muestran en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-106">By default, only the rules that are above the probability threshold defined in **Minimum probability** are displayed in the viewer.</span></span> <span data-ttu-id="31161-107">No puede reducir más este valor utilizando el visor, porque el umbral de probabilidad del resultado de la regla se determina cuando se crea el modelo.</span><span class="sxs-lookup"><span data-stu-id="31161-107">You cannot make this value any smaller by using the viewer, because the probability threshold for rule output is determined when the model is created.</span></span> <span data-ttu-id="31161-108">Para más información, vea [Referencia técnica del algoritmo de asociación de Microsoft](data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="31161-108">For more information, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="31161-109">**Para obtener más información:** [Algoritmo de asociación de Microsoft](data-mining/microsoft-association-algorithm.md), [Examinar un modelo usando el Visor de reglas de asociación de Microsoft](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="31161-109">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="31161-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="31161-110">Options</span></span>  
 <span data-ttu-id="31161-111">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="31161-111">**Refresh viewer content**</span></span>  
 <span data-ttu-id="31161-112">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-112">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="31161-113">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="31161-113">**Mining Model**</span></span>  
 <span data-ttu-id="31161-114">Elija esta opción para ver un modelo de minería de datos que se encuentra en la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="31161-114">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="31161-115">El modelo de minería de datos se abrirá en el visor asociado.</span><span class="sxs-lookup"><span data-stu-id="31161-115">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="31161-116">**Visor**</span><span class="sxs-lookup"><span data-stu-id="31161-116">**Viewer**</span></span>  
 <span data-ttu-id="31161-117">Elija un visor para ver el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="31161-117">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="31161-118">Puede utilizar el visor personalizado de cada modelo de minería de datos o el **Visor de árbol de contenido genérico de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="31161-118">You can use the custom viewer for each mining model, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="31161-119">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="31161-119">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="31161-120">**Probabilidad mínima**</span><span class="sxs-lookup"><span data-stu-id="31161-120">**Minimum probability**</span></span>  
 <span data-ttu-id="31161-121">Cambie este valor para establecer la probabilidad mínima necesaria para que se muestre una regla en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-121">Change this value to set the minimum probability required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="31161-122">Si se aumenta el valor de probabilidad, se reducirá el número de reglas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="31161-122">Increasing the value for probability will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="31161-123">**Importancia mínima**</span><span class="sxs-lookup"><span data-stu-id="31161-123">**Minimum importance**</span></span>  
 <span data-ttu-id="31161-124">Cambie este valor para establecer la importancia mínima necesaria para que se muestre una regla en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-124">Change this value to set the minimum importance required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="31161-125">Si se aumenta el valor de importancia, se reducirá el número de reglas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="31161-125">Increasing the value for importance will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="31161-126">**Regla del filtro**</span><span class="sxs-lookup"><span data-stu-id="31161-126">**Filter Rule**</span></span>  
 <span data-ttu-id="31161-127">Especifique un valor de cadena para filtrar el número de reglas que aparece en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-127">Type a string value to filter the number of rules that appear in the viewer.</span></span>  
  
 <span data-ttu-id="31161-128">También puede escribir expresiones regulares .NET como criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="31161-128">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="31161-129">Por ejemplo, la siguiente expresión devuelve todas las reglas que contienen 'Road Bottle Cage' en el lado izquierdo de la regla:</span><span class="sxs-lookup"><span data-stu-id="31161-129">For example, the following expression returns all rules that contain 'Road Bottle Cage' on the left side of the rule:</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*->.*`  
  
 <span data-ttu-id="31161-130">Observe que podría tener que actualizar la vista para ver los criterios de filtro aplicados.</span><span class="sxs-lookup"><span data-stu-id="31161-130">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="31161-131">También puede activar y desactivar la opción **Mostrar nombre largo** para actualizar la lista.</span><span class="sxs-lookup"><span data-stu-id="31161-131">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="31161-132">De forma predeterminada, los criterios de filtro se aplican a todo el nombre de la combinación de atributo-valor; por consiguiente, si solo está viendo el nombre del atributo, podría no ser obvio que los criterios de filtro se han aplicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="31161-132">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="31161-133">Utilice la lista desplegable **Mostrar** para seleccionar **Mostrar el valor y el nombre del atributo**, y compruebe que la lista de conjuntos de elementos se filtra correctamente.</span><span class="sxs-lookup"><span data-stu-id="31161-133">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="31161-134">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="31161-134">**Show**</span></span>  
 <span data-ttu-id="31161-135">Ajuste el modo en que desea que se muestre la regla en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-135">Adjust the way that the rule is displayed in the viewer.</span></span> <span data-ttu-id="31161-136">Puede seleccionar una de las tres opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="31161-136">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="31161-137">Mostrar el valor y el nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="31161-137">Show the attribute name and value</span></span>  
  
-   <span data-ttu-id="31161-138">Mostrar solo el valor del atributo</span><span class="sxs-lookup"><span data-stu-id="31161-138">Show the attribute value only</span></span>  
  
-   <span data-ttu-id="31161-139">Mostrar solo el nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="31161-139">Show the attribute name only</span></span>  
  
 <span data-ttu-id="31161-140">**Mostrar nombre largo**</span><span class="sxs-lookup"><span data-stu-id="31161-140">**Show long name**</span></span>  
 <span data-ttu-id="31161-141">Se muestra el nombre completo de la regla tal como aparece en el contenido del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="31161-141">Show the full name of the rule as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="31161-142">**Número máximo de filas**</span><span class="sxs-lookup"><span data-stu-id="31161-142">**Maximum rows**</span></span>  
 <span data-ttu-id="31161-143">Limite el número de reglas que se muestra en el visor.</span><span class="sxs-lookup"><span data-stu-id="31161-143">Limit the number of rules that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="31161-144">**Probabilidad**</span><span class="sxs-lookup"><span data-stu-id="31161-144">**Probability**</span></span>  
 <span data-ttu-id="31161-145">Esta columna del gráfico muestra la probabilidad de cada regla.</span><span class="sxs-lookup"><span data-stu-id="31161-145">This column in the chart displays the probability for each rule.</span></span>  
  
 <span data-ttu-id="31161-146">Puede hacer clic en el encabezado de columna para ordenar por probabilidad.</span><span class="sxs-lookup"><span data-stu-id="31161-146">You can click the column heading to sort by probability.</span></span>  
  
 <span data-ttu-id="31161-147">**Importancia**</span><span class="sxs-lookup"><span data-stu-id="31161-147">**Importance**</span></span>  
 <span data-ttu-id="31161-148">Esta columna del gráfico muestra la importancia de cada regla.</span><span class="sxs-lookup"><span data-stu-id="31161-148">This column in the chart displays the importance for each rule.</span></span>  
  
 <span data-ttu-id="31161-149">Puede hacer clic en el encabezado de columna para ordenar por importancia.</span><span class="sxs-lookup"><span data-stu-id="31161-149">You can click the column heading to sort by importance.</span></span>  
  
 <span data-ttu-id="31161-150">**Regla**</span><span class="sxs-lookup"><span data-stu-id="31161-150">**Rule**</span></span>  
 <span data-ttu-id="31161-151">Esta columna del gráfico muestra la descripción de texto de cada regla, según el formato especificado mediante las opciones **Mostrar** y **Mostrar nombre largo**.</span><span class="sxs-lookup"><span data-stu-id="31161-151">This column in the chart displays the text description for each rule, according to the format specified by using the options, **Show** and **Show long name**.</span></span>  
  
 <span data-ttu-id="31161-152">Puede hacer clic en el encabezado de columna para ordenar por el texto de la regla.</span><span class="sxs-lookup"><span data-stu-id="31161-152">You can click the column heading to sort by the text of the rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31161-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31161-153">See Also</span></span>  
 <span data-ttu-id="31161-154">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="31161-154">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="31161-155">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="31161-155">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="31161-156">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="31161-156">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
