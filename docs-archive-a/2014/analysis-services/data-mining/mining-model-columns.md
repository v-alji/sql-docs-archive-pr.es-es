---
title: Columnas del modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining model columns
- columns [data mining]
- REGRESSOR column
- columns [data mining], modeling flags
- modeling flags [data mining]
- MODEL_EXISTENCE_ONLY column
- usage property [data mining]
ms.assetid: fab47643-5bfd-424e-a0f7-69e665db6bab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f936f3f4e0b8f65326e9a6e84f75e6f4e82657f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746061"
---
# <a name="mining-model-columns"></a><span data-ttu-id="d618c-102">Columnas del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d618c-102">Mining Model Columns</span></span>
  <span data-ttu-id="d618c-103">Un modelo de minería de datos aplica un algoritmo de modelo de minería a los datos que se representan en una estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d618c-103">A data mining model applies a mining model algorithm to the data that is represented by a mining structure.</span></span> <span data-ttu-id="d618c-104">Al igual que la estructura, el modelo de minería de datos contiene columnas.</span><span class="sxs-lookup"><span data-stu-id="d618c-104">Like the mining structure, the mining model contains columns.</span></span> <span data-ttu-id="d618c-105">La estructura de minería contiene el modelo de minería de datos y éste hereda todos los valores de las propiedades que define la estructura.</span><span class="sxs-lookup"><span data-stu-id="d618c-105">A mining model is contained within the mining structure, and inherits all the values of the properties that are defined by the mining structure.</span></span> <span data-ttu-id="d618c-106">El modelo puede utilizar todas las columnas que contiene la estructura de minería de datos o un subconjunto de las columnas.</span><span class="sxs-lookup"><span data-stu-id="d618c-106">The model can use all the columns that the mining structure contains or a subset of the columns.</span></span>  
  
 <span data-ttu-id="d618c-107">En una columna de minería de datos puede definir dos elementos adicionales de información: uso y marcas de modelado.</span><span class="sxs-lookup"><span data-stu-id="d618c-107">You can define two additional pieces of information on a mining model column: usage, and modeling flags.</span></span>  
  
-   <span data-ttu-id="d618c-108">El**uso** es una propiedad que define cómo el modelo va a usar la columna.</span><span class="sxs-lookup"><span data-stu-id="d618c-108">**Usage** is a property that defines how the model uses the column.</span></span> <span data-ttu-id="d618c-109">Las columnas se pueden usar como columnas de entrada, de clave o de predicción.</span><span class="sxs-lookup"><span data-stu-id="d618c-109">Columns can be used as input columns, key columns, or predictable columns.</span></span>  
  
-   <span data-ttu-id="d618c-110">Las**marcas de modelado** proporcionan al algoritmo información adicional sobre los datos que se definen en la tabla de casos, de forma que el algoritmo pueda generar un modelo más preciso.</span><span class="sxs-lookup"><span data-stu-id="d618c-110">**Modeling flags** provide the algorithm with additional information about the data that is defined in the case table, so that the algorithm can build a more accurate model.</span></span> <span data-ttu-id="d618c-111">Puede definir marcas de modelado mediante programación con el lenguaje DMX (Extensiones de minería de datos) o en el **Diseñador de minería de datos** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d618c-111">You can define modeling flags programmatically by using the Data Mining Extensions (DMX) language, or in **Data Mining Designer** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="d618c-112">La siguiente lista describe las marcas de modelado que puede definir en una columna de modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d618c-112">The following list describes the modeling flags that you can define on a mining model column.</span></span>  
  
 `MODEL_EXISTENCE_ONLY`  
 <span data-ttu-id="d618c-113">Indica que la presencia del atributo es más importante que los valores que están en la columna de atributos.</span><span class="sxs-lookup"><span data-stu-id="d618c-113">Indicates that the presence of the attribute is more important than the values that are in the attribute column.</span></span> <span data-ttu-id="d618c-114">Por ejemplo, considere una tabla de casos que contenga una lista de elementos de pedido asociados con un cliente determinado.</span><span class="sxs-lookup"><span data-stu-id="d618c-114">For example, consider a case table that contains a list of order items that are associated with a particular customer.</span></span> <span data-ttu-id="d618c-115">Los datos de la tabla incluyen el tipo de producto, el Id. y el costo de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="d618c-115">The table data includes the product type, ID, and cost of each item.</span></span> <span data-ttu-id="d618c-116">Para el modelado, el hecho de que el cliente haya adquirido un elemento de pedido concreto podría ser más importante que el costo del propio elemento.</span><span class="sxs-lookup"><span data-stu-id="d618c-116">For modeling purposes, the fact that the customer purchased a particular order item may be more important than the cost of the order item itself.</span></span> <span data-ttu-id="d618c-117">En este caso, la columna de costo debería marcarse como `MODEL_EXISTENCE_ONLY`.</span><span class="sxs-lookup"><span data-stu-id="d618c-117">In this case, the cost column should be marked as `MODEL_EXISTENCE_ONLY`.</span></span>  
  
 `REGRESSOR`  
 <span data-ttu-id="d618c-118">Indica que el algoritmo puede usar la columna especificada en la fórmula de regresión de algoritmos de regresión.</span><span class="sxs-lookup"><span data-stu-id="d618c-118">Indicates that the algorithm can use the specified column in the regression formula of regression algorithms.</span></span> <span data-ttu-id="d618c-119">Esta marca se admite en los algoritmos de árboles de decisión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] y de serie temporal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d618c-119">This flag is supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series algorithms.</span></span>  
  
 <span data-ttu-id="d618c-120">Para más información sobre la configuración de la propiedad de uso y la definición de marcas de modelado mediante programación con DMX, vea [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span><span class="sxs-lookup"><span data-stu-id="d618c-120">For more information about setting the usage property and defining modeling flags programmatically with DMX, see [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span></span> <span data-ttu-id="d618c-121">Para más información sobre la configuración de la propiedad de uso y la definición de marcas de modelado en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vea [Mover objetos de minería de datos](moving-data-mining-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d618c-121">For more information about setting the usage property and defining modeling flags in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Moving Data Mining Objects](moving-data-mining-objects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d618c-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d618c-122">See Also</span></span>  
 <span data-ttu-id="d618c-123">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d618c-123">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="d618c-124">[Estructuras de minería de datos &#40;Analysis Services:&#41;de minería de datos](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d618c-124">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="d618c-125">[Cambiar las propiedades de un modelo de minería de datos](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="d618c-125">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="d618c-126">[Excluir una columna de un modelo de minería de datos](exclude-a-column-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="d618c-126">[Exclude a Column from a Mining Model](exclude-a-column-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="d618c-127">Columnas de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d618c-127">Mining Structure Columns</span></span>](mining-structure-columns.md)  
  
  
