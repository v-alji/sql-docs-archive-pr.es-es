---
title: Pestaña gráfico de elevación (vista gráfico de precisión de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.liftchart.f1
ms.assetid: f1674e2e-d38e-40c7-b8d1-5585ce9a0168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7cdad01ff3549140bf4fed606b1e8f9eaed10dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752474"
---
# <a name="lift-chart-tab-mining-accuracy-chart-view"></a><span data-ttu-id="dfcd6-102">Pestaña Gráfico de elevación (vista Gráfico de precisión de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="dfcd6-102">Lift Chart Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="dfcd6-103">Utilice el panel **Gráfico de elevación** para ver un gráfico que compara todos los modelos de minería seleccionados en la estructura de minería de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-103">Use the **Lift Chart** pane to view a chart that compares all the selected mining models in the selected mining structure.</span></span>  
  
 <span data-ttu-id="dfcd6-104">Si el modelo predice un atributo discreto, el panel puede mostrar un gráfico de elevación o un gráfico de beneficios.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-104">If the model predicts a discrete attribute, the pane can display either a lift chart or a profit chart.</span></span> <span data-ttu-id="dfcd6-105">Para más información sobre los gráficos de elevación, vea [Gráfico de mejora respecto al modelo predictivo &#40;Analysis Services - Minería de datos&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="dfcd6-105">For information about lift charts, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="dfcd6-106">Para crear un gráfico de beneficios, debe proporcionar información adicional sobre el costo de la implementación de las recomendaciones del modelo de minería, así como los ingresos esperados.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-106">To create a profit chart, you must provide additional information about the cost of implementing the recommendations of the mining model, as well as the expected return.</span></span> <span data-ttu-id="dfcd6-107">Para más información, vea [Gráfico de beneficios &#40;Analysis Services - Minería de datos&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="dfcd6-107">For more information, see [Profit Chart &#40;Analysis Services - Data Mining&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="dfcd6-108">Si el modelo predice un atributo continuo, el panel mostrará un grafo de dispersión.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-108">If the model predicts a continuous attribute, the pane will display a scatter plot graph.</span></span>  
  
 <span data-ttu-id="dfcd6-109">Para obtener información general sobre los métodos para medir la precisión de un modelo de minería de datos, vea [Gráfico de mejora respecto al modelo predictivo &#40;Analysis Services - Minería de datos&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="dfcd6-109">For general information about methods of measuring the accuracy of a mining model, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dfcd6-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="dfcd6-110">Options</span></span>  
 <span data-ttu-id="dfcd6-111">**Tipo de gráfico**</span><span class="sxs-lookup"><span data-stu-id="dfcd6-111">**Chart Type**</span></span>  
 <span data-ttu-id="dfcd6-112">Establece el tipo de gráfico que se va a mostrar en el visor.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-112">Sets the type of chart to display in the viewer.</span></span> <span data-ttu-id="dfcd6-113">Puede seleccionar **Gráfico de elevación** o **Gráfico de beneficios**.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-113">You can select either **Lift Chart** or **Profit Chart**.</span></span>  
  
 <span data-ttu-id="dfcd6-114">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="dfcd6-114">**Settings**</span></span>  
 <span data-ttu-id="dfcd6-115">Abre el cuadro de diálogo **Configuración del gráfico de beneficios** , que se puede usar para configurar un gráfico de beneficios.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-115">Opens the **Profit Chart Settings** dialog box, which you can use to configure a profit chart.</span></span>  
  
 <span data-ttu-id="dfcd6-116">El gráfico de beneficios no está disponible si se ha seleccionado una columna predecible continua en la pestaña **Asignación de columnas** .</span><span class="sxs-lookup"><span data-stu-id="dfcd6-116">The profit chart is not available if a continuous predictable column was selected in the **Column Mapping** tab.</span></span>  
  
 <span data-ttu-id="dfcd6-117">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="dfcd6-117">**Copy**</span></span>  
 <span data-ttu-id="dfcd6-118">Copia el gráfico en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="dfcd6-118">Copies the chart to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcd6-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dfcd6-119">See Also</span></span>  
 <span data-ttu-id="dfcd6-120">[Diseñador de gráficos de precisión de minería de datos &#40;&#41;de minería de datos](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="dfcd6-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="dfcd6-121">[Tareas y procedimientos de prueba y validación &#40;&#41;de minería de datos](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="dfcd6-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="dfcd6-122">Prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="dfcd6-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
