---
title: Pestaña matriz de clasificación (vista gráfico de precisión de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
ms.openlocfilehash: d202d552b25095d0d0845ff64f9c0e289f7bba0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670068"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a><span data-ttu-id="a7465-102">Pestaña Matriz de clasificación (vista Gráfico de precisión de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="a7465-102">Classification Matrix Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="a7465-103">La pestaña **matriz de clasificación** muestra una matriz de clasificación para cada modelo seleccionado en la cuadrícula modelos de la pestaña asignación de **columnas** . La matriz de clasificación solo está disponible si la columna de predicción que está seleccionada en la pestaña **asignación de columnas** no es continua.</span><span class="sxs-lookup"><span data-stu-id="a7465-103">The **Classification Matrix** tab displays a classification matrix for each model selected in the models grid on the **Column Mapping** tab. The classification matrix is only available if the predictable column that is selected in the **Column Mapping** tab is not continuous.</span></span> <span data-ttu-id="a7465-104">Para obtener una descripción más detallada de la pestaña **Matriz de clasificación** , vea [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a7465-104">For a more detailed description of the **Classification Matrix** tab, see [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7465-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="a7465-105">Options</span></span>  
 <span data-ttu-id="a7465-106">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="a7465-106">**Copy**</span></span>  
 <span data-ttu-id="a7465-107">Copia el contenido de cada matriz de clasificación al portapapeles.</span><span class="sxs-lookup"><span data-stu-id="a7465-107">Copies the content of each classification matrix to the clipboard.</span></span>  
  
 <span data-ttu-id="a7465-108">**Recuentos de \<model> en\< predictable column>**</span><span class="sxs-lookup"><span data-stu-id="a7465-108">**Counts for \<model> on \< predictable column>**</span></span>  
 <span data-ttu-id="a7465-109">Muestra una matriz de clasificación para cada modelo de minería de datos de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a7465-109">Displays a classification matrix for each mining model in the mining structure.</span></span> <span data-ttu-id="a7465-110">La matriz contiene las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="a7465-110">The matrix contains the following columns:</span></span>  
  
|<span data-ttu-id="a7465-111">Value</span><span class="sxs-lookup"><span data-stu-id="a7465-111">Value</span></span>|<span data-ttu-id="a7465-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7465-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a7465-113">**Previsto**</span><span class="sxs-lookup"><span data-stu-id="a7465-113">**Predicted**</span></span>|<span data-ttu-id="a7465-114">Contiene una fila de cada estado de la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="a7465-114">Contains a row for each state of the predictable column.</span></span>|  
|<span data-ttu-id="a7465-115">**\<states>reales**</span><span class="sxs-lookup"><span data-stu-id="a7465-115">**\<states> (actual)**</span></span>|<span data-ttu-id="a7465-116">Una columna para cada estado de la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="a7465-116">A column for each state in the predictable column.</span></span> <span data-ttu-id="a7465-117">Si el estado de la fila y la columna se corresponden, la celda representa el número de veces real que el estado existe en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a7465-117">If the state of the row and the column correspond, the cell represents the actual number of times the state exists in the database.</span></span> <span data-ttu-id="a7465-118">Si no se corresponden, la celda representa el error de la predicción.</span><span class="sxs-lookup"><span data-stu-id="a7465-118">If they do not correspond, the cell represents the error of the prediction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7465-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7465-119">See Also</span></span>  
 <span data-ttu-id="a7465-120">[Diseñador de gráficos de precisión de minería de datos &#40;&#41;de minería de datos](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a7465-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="a7465-121">[Tareas y procedimientos de prueba y validación &#40;&#41;de minería de datos](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a7465-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="a7465-122">Prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a7465-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
