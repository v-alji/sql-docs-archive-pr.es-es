---
title: Especificar el contenido y el tipo de datos de la columna (Asistente para minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0634be64-4c38-4381-9b19-fe9a5889306c
author: minewiskan
ms.author: owend
ms.openlocfilehash: e22f46808877391376f721bcab55ea4fd9074186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671714"
---
# <a name="specify-column-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="0c363-102">Especificar contenido y el tipo de datos de las columnas (Asistente para minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0c363-102">Specify Column Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="0c363-103">Utilice la página **Especificar el contenido y el tipo de datos de las columnas** para especificar el uso y el tipo de datos para cada columna seleccionada en la página anterior del asistente.</span><span class="sxs-lookup"><span data-stu-id="0c363-103">Use the **Specify Column Content and Data Type** page to specify the usage and data type for each column that you selected on the previous page of the wizard.</span></span> <span data-ttu-id="0c363-104">Si desea omitir la columna, haga clic en **Atrás** para volver a la página **Especificar los datos de aprendizaje**y desactive todas las casillas.</span><span class="sxs-lookup"><span data-stu-id="0c363-104">If you want to ignore the column, click **Back** to return to the page **Specify the Training Data**, and clear all checkboxes.</span></span>  
  
 <span data-ttu-id="0c363-105">El uso de una columna indica cómo se utilizarán los datos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="0c363-105">The usage of a column indicates how the data will be used in the model.</span></span> <span data-ttu-id="0c363-106">Una columna se puede utilizar como una clave para identificar una serie, como un valor de entrada que se va a utilizar en el análisis o como el valor que desea predecir.</span><span class="sxs-lookup"><span data-stu-id="0c363-106">A column can be used as a key to identify a series, as an input value to use in analysis, or as the value that you want to predict.</span></span> <span data-ttu-id="0c363-107">Las columnas se pueden utilizar para tareas de predicción y de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="0c363-107">Columns can be used for both prediction and input.</span></span>  
  
 <span data-ttu-id="0c363-108">El tipo de datos especifica información adicional sobre el tipo de datos que contiene la columna y cómo se utilizarán esos datos durante la fase de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="0c363-108">The data type specifies additional detail about the type of data that is contained in the column, and how the data will be used during training.</span></span> <span data-ttu-id="0c363-109">Algunos tipos de contenido requieren un tipo de datos concreto y viceversa.</span><span class="sxs-lookup"><span data-stu-id="0c363-109">Some content types require a specific data type, and vice versa.</span></span> <span data-ttu-id="0c363-110">Puede que también necesite especificar un tipo de datos determinado dependiendo del algoritmo que utilice al crear un modelo de minería.</span><span class="sxs-lookup"><span data-stu-id="0c363-110">You might also need to specify a particular data type depending on the algorithm that you use when you create a mining model.</span></span> <span data-ttu-id="0c363-111">Para obtener información sobre los tipos de contenido y los tipos de datos en estructuras y modelos de minería de datos, vea [Tipos de contenido &#40;minería de datos&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="0c363-111">For information about content types and data types in mining models and structures, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="0c363-112">**Para más información:** [Estructuras de minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Columnas del modelo de minería de datos](data-mining/mining-model-columns.md), [Asistente para minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Crear una estructura de minería de datos relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="0c363-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c363-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="0c363-113">Options</span></span>  
 <span data-ttu-id="0c363-114">**Estructura del modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="0c363-114">**Mining model structure**</span></span>  
 <span data-ttu-id="0c363-115">Muestra las columnas de las vistas y las tablas anidadas que seleccionó en la página anterior del asistente.</span><span class="sxs-lookup"><span data-stu-id="0c363-115">Displays the columns from the views and nested tables that you selected on the previous page of the wizard.</span></span>  
  
 <span data-ttu-id="0c363-116">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="0c363-116">**Columns**</span></span>  
 <span data-ttu-id="0c363-117">Enumera las columnas.</span><span class="sxs-lookup"><span data-stu-id="0c363-117">Lists the columns.</span></span>  
  
 <span data-ttu-id="0c363-118">**Tipo de contenido**</span><span class="sxs-lookup"><span data-stu-id="0c363-118">**Content type**</span></span>  
 <span data-ttu-id="0c363-119">Especifica el tipo de contenido para la columna.</span><span class="sxs-lookup"><span data-stu-id="0c363-119">Specify the content type for the column.</span></span> <span data-ttu-id="0c363-120">Si especificó que la columna es una clave en la página anterior del asistente, los valores siguientes estarán disponibles:</span><span class="sxs-lookup"><span data-stu-id="0c363-120">If you specified that the column is a key on the previous page of the wizard, the following values are available:</span></span>  
  
|<span data-ttu-id="0c363-121">Opción</span><span class="sxs-lookup"><span data-stu-id="0c363-121">Option</span></span>|<span data-ttu-id="0c363-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c363-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0c363-123">Clave</span><span class="sxs-lookup"><span data-stu-id="0c363-123">Key</span></span>|<span data-ttu-id="0c363-124">Especifica que la columna contiene un identificador único para la serie de casos.</span><span class="sxs-lookup"><span data-stu-id="0c363-124">Specify that the column contains a unique identifier for the case series.</span></span>|  
|<span data-ttu-id="0c363-125">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="0c363-125">Key Sequence</span></span>|<span data-ttu-id="0c363-126">Especifica que la columna contiene un identificador de secuencia.</span><span class="sxs-lookup"><span data-stu-id="0c363-126">Specify that the column contains a sequence identifier.</span></span>|  
|<span data-ttu-id="0c363-127">Key Time</span><span class="sxs-lookup"><span data-stu-id="0c363-127">Key Time</span></span>|<span data-ttu-id="0c363-128">Especifica que la columna contiene una fecha u otro número continuo único que se utiliza para identificar una fecha o una serie temporal.</span><span class="sxs-lookup"><span data-stu-id="0c363-128">Specify that the column contains a date or other unique continuous number that is used to identify a date or time series.</span></span>|  
  
 <span data-ttu-id="0c363-129">Si seleccionó la columna como una columna que no es de clave, los valores siguientes están disponibles, dependiendo del tipo de datos:</span><span class="sxs-lookup"><span data-stu-id="0c363-129">If you selected the column as a non-key column, the following values are available, depending on the data type:</span></span>  
  
|<span data-ttu-id="0c363-130">Opción</span><span class="sxs-lookup"><span data-stu-id="0c363-130">Option</span></span>|<span data-ttu-id="0c363-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c363-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0c363-132">Continuo</span><span class="sxs-lookup"><span data-stu-id="0c363-132">Continuous</span></span>|<span data-ttu-id="0c363-133">Especifica que la columna contiene los valores numéricos continuos.</span><span class="sxs-lookup"><span data-stu-id="0c363-133">Specify that the column contains continuous numeric values.</span></span>|  
|<span data-ttu-id="0c363-134">Discretized</span><span class="sxs-lookup"><span data-stu-id="0c363-134">Discretized</span></span>|<span data-ttu-id="0c363-135">Especifica que la columna contiene valores numéricos que se han discretizado o se pueden tratar como valores discretos.</span><span class="sxs-lookup"><span data-stu-id="0c363-135">Specify that the column contains numeric values that either have been discretized, or can be treated as discrete values.</span></span>|  
|<span data-ttu-id="0c363-136">Discrete</span><span class="sxs-lookup"><span data-stu-id="0c363-136">Discrete</span></span>|<span data-ttu-id="0c363-137">Especifica que la columna contiene texto u otros valores no numéricos.</span><span class="sxs-lookup"><span data-stu-id="0c363-137">Specify that the column contains text or other nonnumeric values.</span></span>|  
  
 <span data-ttu-id="0c363-138">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0c363-138">**Data type**</span></span>  
 <span data-ttu-id="0c363-139">Especifica el tipo de datos para la columna.</span><span class="sxs-lookup"><span data-stu-id="0c363-139">Specify the data type for the column.</span></span>  
  
 <span data-ttu-id="0c363-140">Puede disponer de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0c363-140">The following values are available:</span></span>  
  
-   `Boolean`  
  
-   `Date`  
  
-   `Double`  
  
-   `Long`  
  
-   `Text`  
  
 <span data-ttu-id="0c363-141">**Detectar**</span><span class="sxs-lookup"><span data-stu-id="0c363-141">**Detect**</span></span>  
 <span data-ttu-id="0c363-142">Analiza un ejemplo de datos en todas las columnas numéricas.</span><span class="sxs-lookup"><span data-stu-id="0c363-142">Analyze a sample of data in all numeric columns.</span></span> <span data-ttu-id="0c363-143">Reemplaza los valores **Tipo de contenido** especificados con un tipo de contenido recomendado.</span><span class="sxs-lookup"><span data-stu-id="0c363-143">Replaces specified **Content Type** values with a recommended content type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c363-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c363-144">See Also</span></span>  
 <span data-ttu-id="0c363-145">[Asistente para minería de datos (ayuda F1) &#40;Analysis Services: minería de datos&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="0c363-145">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="0c363-146">[Sugerir columnas relacionadas &#40;Asistente para minería de datos&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="0c363-146">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="0c363-147">[Especificar tipos de tablas &#40;Asistente para minería de datos&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="0c363-147">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="0c363-148">Especifique el contenido y el tipo de datos de la columna &#40;Asistente para minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="0c363-148">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
