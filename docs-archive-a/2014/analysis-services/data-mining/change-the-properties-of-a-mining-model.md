---
title: Cambiar las propiedades de un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- properties [data mining]
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 395e6a4cb9c0f0dac0f0c717dfe0695033cad050
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663195"
---
# <a name="change-the-properties-of-a-mining-model"></a><span data-ttu-id="28969-102">Cambiar las propiedades de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="28969-102">Change the Properties of a Mining Model</span></span>
  <span data-ttu-id="28969-103">Algunas propiedades del modelo de minería de datos se aplican al modelo en su conjunto, mientras que otras se aplican a columnas individuales.</span><span class="sxs-lookup"><span data-stu-id="28969-103">Some mining model properties apply to the model as a whole, and other model properties apply to individual columns.</span></span> <span data-ttu-id="28969-104">Ejemplos de propiedades que se aplican a todo el modelo son las propiedades `Drillthrough`, que especifica si los datos de los casos deben estar disponibles para las consultas, y `Description`.</span><span class="sxs-lookup"><span data-stu-id="28969-104">Examples of properties that apply to the entire model would be the `Drillthrough` property, which specifies whether the case data should be available for querying, and the `Description` property.</span></span> <span data-ttu-id="28969-105">Entre las propiedades que se aplican a la columna se incluyen `Usage` y `ModelingFlags`, que controlan cómo se utilizan los datos en la columna dentro del modelo.</span><span class="sxs-lookup"><span data-stu-id="28969-105">Properties that apply to the column include `Usage` and `ModelingFlags`, which control how data in the column is used within the model.</span></span>  
  
 <span data-ttu-id="28969-106">Las propiedades del modelo siguientes disponen de editores avanzados que se pueden utilizar para crear expresiones o configurar propiedades complejas del modelo.</span><span class="sxs-lookup"><span data-stu-id="28969-106">The following model properties have advanced editors that you can use to create expressions or configure complex model properties.</span></span> <span data-ttu-id="28969-107">Las propiedades siguientes proporcionan:</span><span class="sxs-lookup"><span data-stu-id="28969-107">The following properties provide:</span></span>  
  
-   <span data-ttu-id="28969-108">`Filter`propiedad: abre el [cuadro de diálogo filtro de conjunto de datos o filtro de modelo](../data-set-filter-or-model-filter-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="28969-108">`Filter` property: Opens the [Data Set Filter or Model Filter Dialog Box](../data-set-filter-or-model-filter-dialog-box.md).</span></span>  
  
-   <span data-ttu-id="28969-109">`AlgorithmParameters`propiedad: abre el [cuadro de diálogo parámetros de algoritmo &#40;vista modelos de minería de datos&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span><span class="sxs-lookup"><span data-stu-id="28969-109">`AlgorithmParameters` property: Opens the [Algorithm Parameters Dialog Box &#40;Mining Models View&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span></span>  
  
 <span data-ttu-id="28969-110">Para obtener información sobre cómo configurar las propiedades de un modelo de minería de datos, vea [Columnas del modelo de minería de datos](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="28969-110">For information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model"></a><span data-ttu-id="28969-111">Para cambiar las propiedades de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="28969-111">To change the properties of a mining model</span></span>  
  
1.  <span data-ttu-id="28969-112">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, haga clic con el botón derecho en el encabezado de columna que contiene el nombre del modelo de minería de datos o en la fila de la cuadrícula que contiene el nombre del algoritmo de minería de datos y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="28969-112">In the **Mining Models** tab in Data Mining Designer, right-click either the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="28969-113">En la ventana **Propiedades** situada en el lado derecho de la pantalla, resalte el valor correspondiente a la propiedad que desee cambiar y, a continuación, escriba el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="28969-113">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
     <span data-ttu-id="28969-114">El nuevo valor tendrá efecto cuando se seleccione otro elemento diferente en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="28969-114">The new value will take effect when you select a different element in the designer.</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model-column"></a><span data-ttu-id="28969-115">Para cambiar las propiedades de una columna del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="28969-115">To change the properties of a mining model column</span></span>  
  
1.  <span data-ttu-id="28969-116">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, haga clic con el botón derecho en la celda de cuadrícula situada en la intersección de la columna de la estructura de minería de datos con el modelo de minería de datos y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="28969-116">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the grid at the intersection of the mining structure column and the mining model, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="28969-117">En la ventana **Propiedades** situada en el lado derecho de la pantalla, resalte el valor correspondiente a la propiedad que desee cambiar y, a continuación, escriba el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="28969-117">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="28969-118">Si el uso de la columna está establecido en `Ignore` , la ventana **propiedades** de la columna está en blanco.</span><span class="sxs-lookup"><span data-stu-id="28969-118">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="28969-119">El nuevo valor tendrá efecto cuando se seleccione otro elemento diferente en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="28969-119">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28969-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28969-120">See Also</span></span>  
 [<span data-ttu-id="28969-121">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="28969-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
