---
title: Propiedades del modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- data mining [Analysis Services], properties
- columns [data mining], properties
- Data Mining Designer
- properties [data mining]
ms.assetid: c5194619-8b31-42be-a95f-585711462945
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb086f4a978ca96de8e6fc99f889f718247629af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675649"
---
# <a name="mining-model-properties"></a><span data-ttu-id="7d9b2-102">Propiedades del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7d9b2-102">Mining Model Properties</span></span>
  <span data-ttu-id="7d9b2-103">Los modelos de minería de datos tienen las siguientes clases de propiedades:</span><span class="sxs-lookup"><span data-stu-id="7d9b2-103">Mining models have the following kinds of properties:</span></span>  
  
-   <span data-ttu-id="7d9b2-104">Las propiedades que se heredan de la estructura de minería de datos que define el tipo de datos y el tipo de contenido de los datos que usa el modelo;</span><span class="sxs-lookup"><span data-stu-id="7d9b2-104">Properties that are inherited from the mining structure that define the data type and content type of the data used by the model;</span></span>  
  
-   <span data-ttu-id="7d9b2-105">Las propiedades relacionadas con el algoritmo que se usa para crear el modelo de minería de datos, incluidos los parámetros de cliente;</span><span class="sxs-lookup"><span data-stu-id="7d9b2-105">Properties that are related to the algorithm used to create the mining model, including any customer parameters;</span></span>  
  
-   <span data-ttu-id="7d9b2-106">Las propiedades que definen un filtro en el modelo utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-106">Properties that define a filter on the model used to train the model.</span></span>  
  
 <span data-ttu-id="7d9b2-107">Las propiedades de un modelo de minería de datos se definen inicialmente al crear el modelo; sin embargo, puede modificar la mayoría de las propiedades posteriormente, incluidos los parámetros de algoritmo, los filtros y las propiedades de uso de la columna.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-107">The properties of a mining model are initially defined when you create the model; however, you can alter most properties later, including the algorithm parameters, filters, and column usage properties.</span></span> <span data-ttu-id="7d9b2-108">Puede cambiar las propiedades mediante la pestaña **Modelos de minería de datos** del Diseñador de minería de datos o bien usando AMO o XMLA.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-108">You change properties by using the **Mining Models** tab of Data Mining Designer, or by using AMO or XMLA.</span></span>  
  
 <span data-ttu-id="7d9b2-109">Siempre que cambia alguna propiedad de un modelo, debe volver a procesarlo para que refleje los cambios.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-109">Whenever you change any property of a model, you must reprocess the model for the changes to be reflected in the model.</span></span> <span data-ttu-id="7d9b2-110">Es necesario volver a procesar incluso si el cambio afecta solamente a los metadatos, como agregar un alias o una descripción de columna.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-110">Reprocessing is required even if the change only involves metadata, such as adding a column alias or description.</span></span>  
  
## <a name="properties-of-models"></a><span data-ttu-id="7d9b2-111">Propiedades de los modelos</span><span class="sxs-lookup"><span data-stu-id="7d9b2-111">Properties of Models</span></span>  
 <span data-ttu-id="7d9b2-112">En la tabla siguiente se describen las propiedades específicas de los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-112">The following table describes the properties that are specific to mining models.</span></span> <span data-ttu-id="7d9b2-113">Además, hay propiedades que puede establecer en columnas individuales de la minería de datos</span><span class="sxs-lookup"><span data-stu-id="7d9b2-113">Additionally, there are properties that you can set on individual columns in the mining</span></span>  
  
|<span data-ttu-id="7d9b2-114">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7d9b2-114">Property</span></span>|<span data-ttu-id="7d9b2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d9b2-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7d9b2-116">**Algoritmo**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-116">**Algorithm**</span></span>|<span data-ttu-id="7d9b2-117">Establece el tipo de algoritmo para el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-117">Sets the algorithm type for the mining model.</span></span>|  
|<span data-ttu-id="7d9b2-118">**AlgorithmParameters**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-118">**AlgorithmParameters**</span></span>|<span data-ttu-id="7d9b2-119">Establece los valores de los parámetros de algoritmo disponibles para cada tipo de algoritmo.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-119">Sets values for algorithm parameters that are available for each algorithm type.</span></span>|  
|<span data-ttu-id="7d9b2-120">**Filter**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-120">**Filter**</span></span>|<span data-ttu-id="7d9b2-121">Establece un filtro que se aplica a los datos que se utilizan para el aprendizaje y prueba del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-121">Sets a filter that is applied to the data that is used for training and testing the mining model.</span></span> <span data-ttu-id="7d9b2-122">La definición del filtro está almacenada con el modelo y se utiliza opcionalmente al crear consultas de predicción o al probar la exactitud del modelo.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-122">The filter definition is stored with the model and can be used optionally when you create prediction queries, or when you test the accuracy of the model.</span></span><br /><br /> <span data-ttu-id="7d9b2-123">El filtro de modelos no es opcional en el aprendizaje del modelo.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-123">The model filter is not optional when training the model.</span></span>|  
|<span data-ttu-id="7d9b2-124">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-124">**Name**</span></span>|<span data-ttu-id="7d9b2-125">Establece el nombre del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-125">Sets the name of the mining model.</span></span>|  
|<span data-ttu-id="7d9b2-126">**AllowDrillThrough**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-126">**AllowDrillThrough**</span></span>|<span data-ttu-id="7d9b2-127">Especifica si se habilita la obtención de detalles en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-127">Specifies whether drill through is enabled on the mining model.</span></span>|  
  
## <a name="properties-of-model-columns"></a><span data-ttu-id="7d9b2-128">Propiedades de las columnas de un modelo</span><span class="sxs-lookup"><span data-stu-id="7d9b2-128">Properties of Model Columns</span></span>  
 <span data-ttu-id="7d9b2-129">Puede configurar las siguientes propiedades específicas de la minería de datos para cada columna de un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-129">You can set the following data mining-specific properties for each column in a mining model.</span></span> <span data-ttu-id="7d9b2-130">Puede establecer estas propiedades con un valor diferente para cada modelo de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-130">You can set these properties to a different value for each mining model in a mining structure.</span></span>  
  
|<span data-ttu-id="7d9b2-131">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7d9b2-131">Property</span></span>|<span data-ttu-id="7d9b2-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d9b2-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7d9b2-133">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-133">**Description**</span></span>|<span data-ttu-id="7d9b2-134">Describe el propósito de la columna de minería.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-134">Describes the purpose of the mining column.</span></span>|  
|<span data-ttu-id="7d9b2-135">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-135">**Name**</span></span>|<span data-ttu-id="7d9b2-136">Establece el nombre de la columna del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-136">Sets the name of the mining model column.</span></span> <span data-ttu-id="7d9b2-137">Puede escribir un nuevo nombre que sirva de alias para la columna del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-137">You can type a new name, to provide an alias for the mining model column.</span></span>|  
|<span data-ttu-id="7d9b2-138">**ModelingFlags**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-138">**ModelingFlags**</span></span>|<span data-ttu-id="7d9b2-139">Configura las marcas específicas de algoritmo de la columna.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-139">Sets any algorithm-specific flags for the column.</span></span>|  
|<span data-ttu-id="7d9b2-140">**SourceColumnID**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-140">**SourceColumnID**</span></span>|<span data-ttu-id="7d9b2-141">Indica el nombre de la columna de estructura de minería de datos en la que se basa la columna de modelo.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-141">Indicates the name of the mining structure column on which the model column is based.</span></span><br /><br /> <span data-ttu-id="7d9b2-142">Esta propiedad es de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-142">This property is read-only.</span></span>|  
|<span data-ttu-id="7d9b2-143">**Uso**</span><span class="sxs-lookup"><span data-stu-id="7d9b2-143">**Usage**</span></span>|<span data-ttu-id="7d9b2-144">Establece la forma en que el modelo de minería de datos va a utilizar la columna.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-144">Sets how the column will be used by the mining model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d9b2-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d9b2-145">See Also</span></span>  
 <span data-ttu-id="7d9b2-146">[Columnas del modelo de minería de datos](mining-model-columns.md) </span><span class="sxs-lookup"><span data-stu-id="7d9b2-146">[Mining Model Columns](mining-model-columns.md) </span></span>  
 <span data-ttu-id="7d9b2-147">[Estructuras de minería de datos &#40;Analysis Services:&#41;de minería de datos](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7d9b2-147">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="7d9b2-148">[Tareas y procedimientos del modelo de minería de datos](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="7d9b2-148">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="7d9b2-149">[Cambiar las propiedades de un modelo de minería de datos](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="7d9b2-149">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="7d9b2-150">[Herramientas de minería de datos](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7d9b2-150">[Data Mining Tools](data-mining-tools.md) </span></span>  
 <span data-ttu-id="7d9b2-151">[Crear una estructura de minería de datos relacional](create-a-relational-mining-structure.md) </span><span class="sxs-lookup"><span data-stu-id="7d9b2-151">[Create a Relational Mining Structure](create-a-relational-mining-structure.md) </span></span>  
 [<span data-ttu-id="7d9b2-152">Crear un alias para una columna de modelo</span><span class="sxs-lookup"><span data-stu-id="7d9b2-152">Create an Alias for a Model Column</span></span>](create-an-alias-for-a-model-column.md)  
  
  
