---
title: Destino de Entrenamiento del modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e101a7e374f16b12b3a5aa30a49dbecd2632f06f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673825"
---
# <a name="data-mining-model-training-destination"></a><span data-ttu-id="b37d2-102">entrenamiento del modelo de minería de datos, destino</span><span class="sxs-lookup"><span data-stu-id="b37d2-102">Data Mining Model Training Destination</span></span>
  <span data-ttu-id="b37d2-103">El destino de Entrenamiento del modelo de minería de datos entrena los modelos de minería de datos pasando los datos que recibe el destino por los algoritmos de modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b37d2-103">The Data Mining Model Training destination trains data mining models by passing the data that the destination receives through the data mining model algorithms.</span></span> <span data-ttu-id="b37d2-104">Un destino puede entrenar varios modelos de minería de datos si los modelos se generan sobre la misma estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b37d2-104">Multiple data mining models can be trained by one destination if the models are built on the same data mining structure.</span></span> <span data-ttu-id="b37d2-105">Para obtener más información, consulte [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) y [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span><span class="sxs-lookup"><span data-stu-id="b37d2-105">For more information, see [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) and [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span></span>  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a><span data-ttu-id="b37d2-106">Configuración del destino de entrenamiento del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="b37d2-106">Configuration of the Data Mining Model Training Destination</span></span>  
 <span data-ttu-id="b37d2-107">Si una columna de nivel de caso de la estructura de destino y los modelos generados en la estructura tiene el tipo de contenido KEY TIME o KEY SEQUENCE, los datos de entrada se deben ordenar en esa columna.</span><span class="sxs-lookup"><span data-stu-id="b37d2-107">If a case level column of the target structure and the models built on the structure has the content type KEY TIME or KEY SEQUENCE, the input data must be sorted on that column.</span></span> <span data-ttu-id="b37d2-108">Por ejemplo, los modelos generados con el algoritmo de serie temporal de Microsoft usan el tipo de contenido KEY TIME.</span><span class="sxs-lookup"><span data-stu-id="b37d2-108">For example, models built using the Microsoft Time Series algorithm use the content type KEY TIME.</span></span> <span data-ttu-id="b37d2-109">Si no se ordenan los datos de entrada, el procesamiento del modelo puede producir un error.</span><span class="sxs-lookup"><span data-stu-id="b37d2-109">If input data is not sorted, the processing of the model may fail.</span></span> <span data-ttu-id="b37d2-110">Si los datos requieren que se ordenen, puede usar la transformación Ordenar en una etapa anterior del flujo de datos para ordenar los datos.</span><span class="sxs-lookup"><span data-stu-id="b37d2-110">If the data requires sorting, you can use a Sort transformation earlier in the data flow to sort the data.</span></span> <span data-ttu-id="b37d2-111">Este requisito no se aplica a las columnas con el tipo de contenido KEY.</span><span class="sxs-lookup"><span data-stu-id="b37d2-111">This requirement does not apply to columns with the KEY content type.</span></span> <span data-ttu-id="b37d2-112">Para obtener más información, vea [Tipos de contenido &#40;minería de datos&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) y [Transformación Ordenar](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="b37d2-112">For more information, see [Content Types &#40;Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) and [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b37d2-113">La entrada del destino de Entrenamiento del modelo de minería de datos se debe ordenar.</span><span class="sxs-lookup"><span data-stu-id="b37d2-113">The input to the Data Mining Model training destination must be sorted.</span></span> <span data-ttu-id="b37d2-114">Para ordenar los datos, puede incluir un destino de Ordenar en dirección ascendente desde el destino de Entrenamiento del modelo de minería de datos en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="b37d2-114">To sort the data, you can include a Sort destination upstream from the Data Mining Model Training destination in the data flow.</span></span> <span data-ttu-id="b37d2-115">Para más información, consulte [Sort Transformation](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="b37d2-115">For more information, see [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
 <span data-ttu-id="b37d2-116">Este destino tiene una entrada y ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="b37d2-116">This destination has one input and no output.</span></span>  
  
 <span data-ttu-id="b37d2-117">El destino de Entrenamiento del modelo de minería de datos usa un administrador de conexiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para conectarse al proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene la estructura y los modelos de minería de datos que entrena el destino.</span><span class="sxs-lookup"><span data-stu-id="b37d2-117">The Data Mining Model Training destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models that the destination trains.</span></span> <span data-ttu-id="b37d2-118">Para más información, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b37d2-118">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="b37d2-119">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b37d2-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b37d2-120">Para obtener más información sobre las propiedades que se pueden establecer en el cuadro de diálogo **Editor de entrenamiento de modelos de minería de datos** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="b37d2-120">For more information about the properties that you can set in the **Data Mining Model Training Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b37d2-121">Editor de entrenamiento de modelos de minería de datos &#40;pestaña Conexión&#41;</span><span class="sxs-lookup"><span data-stu-id="b37d2-121">Data Mining Model Training Editor &#40;Connection Tab&#41;</span></span>](../data-mining-model-training-editor-connection-tab.md)  
  
-   [<span data-ttu-id="b37d2-122">Editor de entrenamiento de modelos de minería de datos &#40;pestaña Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="b37d2-122">Data Mining Model Training Editor &#40;Columns Tab&#41;</span></span>](../data-mining-model-training-editor-columns-tab.md)  
  
 <span data-ttu-id="b37d2-123">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b37d2-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="b37d2-124">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b37d2-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b37d2-125">Common Properties</span><span class="sxs-lookup"><span data-stu-id="b37d2-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="b37d2-126">Propiedades personalizadas del destino de entrenamiento del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="b37d2-126">Data Mining Model Training Destination Custom Properties</span></span>](data-mining-model-training-destination-custom-properties.md)  
  
 <span data-ttu-id="b37d2-127">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="b37d2-127">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
