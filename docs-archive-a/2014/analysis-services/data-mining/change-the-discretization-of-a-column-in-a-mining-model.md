---
title: Cambiar la discretización de una columna en un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discretization [Analysis Services]
- mining structures [Analysis Services], how-to topics
- discretized columns [data mining]
- bucketing problems [Analysis Services]
ms.assetid: 3c49862b-595d-4fa4-b890-e2e1bde1d74f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b20d6428afac5c1492fdc74aafd4d0c010159d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676270"
---
# <a name="change-the-discretization-of-a-column-in-a-mining-model"></a><span data-ttu-id="e8553-102">Cambiar la discretización de una columna en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e8553-102">Change the Discretization of a Column in a Mining Model</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="e8553-103">discretiza los valores de forma automática, es decir, los datos en columnas numéricas, en ciertos escenarios.</span><span class="sxs-lookup"><span data-stu-id="e8553-103">automatically discretizes values-that is to say, it bins data in numeric column-in certain scenarios.</span></span> <span data-ttu-id="e8553-104">Por ejemplo, si la información contiene datos numéricos continuos y crea un modelo de árbol de decisión, cada columna de datos continuos se discretizará automáticamente según la distribución de los datos.</span><span class="sxs-lookup"><span data-stu-id="e8553-104">For example, if your data contains continuous numeric data and you create a decision tree model, each column of continuous data will be automatically binned, depending on the distribution of the data.</span></span> <span data-ttu-id="e8553-105">Si desea controlar cómo se discretizan los datos, debe cambiar las propiedades en la columna de la estructura de minería de datos que controlan cómo se usan los datos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="e8553-105">If you want to control how the data is discretized, you must change the properties on the mining structure column that control how the data is used in the model.</span></span>  
  
 <span data-ttu-id="e8553-106">Para más información general sobre cómo configurar las propiedades de un modelo de minería de datos, vea [Columnas del modelo de minería de datos](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e8553-106">For general information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-display-the-properties-for-a-mining-model-column"></a><span data-ttu-id="e8553-107">Para mostrar las propiedades de una columna de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e8553-107">To display the properties for a mining model column</span></span>  
  
1.  <span data-ttu-id="e8553-108">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, haga clic con el botón derecho en el encabezado de columna que contiene el nombre del modelo de minería de datos o en la fila de la cuadrícula que contiene el nombre del algoritmo de minería de datos y luego seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e8553-108">In the **Mining Models** tab in Data Mining Designer, right-click the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="e8553-109">La ventana **Propiedades** muestra las propiedades que están asociadas al modelo de minería de datos en conjunto.</span><span class="sxs-lookup"><span data-stu-id="e8553-109">The **Properties** window displays the properties that are associated with the mining model as a whole.</span></span>  
  
2.  <span data-ttu-id="e8553-110">En la columna **Estructura** situada cerca del lado izquierdo de la pantalla, haga clic en la columna que contiene los datos numéricos continuos que desea discretizar.</span><span class="sxs-lookup"><span data-stu-id="e8553-110">In the **Structure** column near the left side of the screen, click the column that contains the continuous numeric data you want to discretize.</span></span>  
  
     <span data-ttu-id="e8553-111">La ventana **Propiedades** cambia para mostrar simplemente las propiedades asociadas a esa columna.</span><span class="sxs-lookup"><span data-stu-id="e8553-111">The **Properties** window changes to display just the properties associated with that column.</span></span>  
  
### <a name="to-change-the-discretization-method"></a><span data-ttu-id="e8553-112">Para cambiar el método de discretización</span><span class="sxs-lookup"><span data-stu-id="e8553-112">To change the discretization method</span></span>  
  
1.  <span data-ttu-id="e8553-113">En la ventana **propiedades de minería de datos** , haga clic en el cuadro de texto situado junto a **contenido**y seleccione `Discretized` en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e8553-113">In the **Mining Properties** window, click the text box next to **Content**, and select `Discretized` from the dropdown list.</span></span>  
  
     <span data-ttu-id="e8553-114">La ventana <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> y <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> ya están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="e8553-114">The <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> properties are now enabled.</span></span>  
  
2.  <span data-ttu-id="e8553-115">En la ventana **propiedades** , haga clic en el cuadro de texto situado junto a <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> y seleccione uno de los siguientes valores: `Automatic` , `EqualAreas` o `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="e8553-115">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> and select one of the following values: `Automatic`, `EqualAreas`, or `Cluster`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8553-116">Si el uso de la columna está establecido en `Ignore` , la ventana **propiedades** de la columna está en blanco.</span><span class="sxs-lookup"><span data-stu-id="e8553-116">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="e8553-117">El nuevo valor tendrá efecto cuando se seleccione otro elemento diferente en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="e8553-117">The new value will take effect when you select a different element in the designer.</span></span>  
  
3.  <span data-ttu-id="e8553-118">En la pestaña **Propiedades** , haga clic en el cuadro de texto situado junto a <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> y escriba un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="e8553-118">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and type a numeric value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8553-119">Si cambia estas propiedades, se debe volver a procesar la estructura, junto con cualquier modelo que desee que use el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="e8553-119">If you change these properties, the structure must be reprocessed, along with any models that you want to use the new setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8553-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8553-120">See Also</span></span>  
 [<span data-ttu-id="e8553-121">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e8553-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
