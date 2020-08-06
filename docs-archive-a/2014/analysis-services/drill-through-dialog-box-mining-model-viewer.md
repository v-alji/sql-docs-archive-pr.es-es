---
title: Cuadro de diálogo obtener detalles (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.drillthrough.f1
ms.assetid: 42b78399-143d-4f44-90e0-b545ffb79e10
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1b00c62017de5a26c4507a04aeaf59aba7522146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676242"
---
# <a name="drill-through-dialog-box-mining-model-viewer"></a><span data-ttu-id="e2fce-102">Cuadro de diálogo Obtener detalles (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="e2fce-102">Drill Through Dialog Box (Mining Model Viewer)</span></span>
  <span data-ttu-id="e2fce-103">Cuando vea un modelo de minería de datos utilizando la pestaña **Visor de modelos de minería de datos** del Diseñador de minería de datos, podrá obtener detalles sobre los datos de los casos, siempre que el modelo tenga habilitada la obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="e2fce-103">When you view a mining model by using the **Mining Model Viewer** tab of Data Mining Designer, you can drill through into details about the case data, provided the model has drillthrough enabled.</span></span> <span data-ttu-id="e2fce-104">Además, si la estructura de minería de datos subyacente tiene habilitada la obtención de detalles, también podrá ver las columnas de la estructura de minería de datos, incluso si dichas columnas no se incluyeron en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e2fce-104">Moreover, if the underlying mining structure has drillthrough enabled, you can also see columns in the mining structure, even if those columns were not included in the mining model.</span></span> <span data-ttu-id="e2fce-105">En la lista de columnas, las columnas de estructura tienen como prefijo la etiqueta "Structure."</span><span class="sxs-lookup"><span data-stu-id="e2fce-105">In the column list, the structure columns are prefixed by the "Structure."</span></span> <span data-ttu-id="e2fce-106">.</span><span class="sxs-lookup"><span data-stu-id="e2fce-106">label.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2fce-107">No puede habilitar la obtención de detalles en una estructura de minería existente.</span><span class="sxs-lookup"><span data-stu-id="e2fce-107">You cannot enable drillthrough on an existing mining structure.</span></span> <span data-ttu-id="e2fce-108">En su lugar, debe volver a crear la estructura de minería de datos y habilitar la obtención de detalles durante el proceso de creación.</span><span class="sxs-lookup"><span data-stu-id="e2fce-108">Instead, you must re-create the mining structure and enable drillthrough during the creation process.</span></span>  
  
 <span data-ttu-id="e2fce-109">Para obtener información sobre cómo tener acceso a los datos de los casos desde cada visor de modelos de minería de datos que admitan la obtención de detalles, **vea** [Obtener detalles de datos de caso a partir de un modelo de minería de datos](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="e2fce-109">For information about how to access case data from each of the mining model viewers that support drillthrough, **see** [Drill Through to Case Data from a Mining Model](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e2fce-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="e2fce-110">Options</span></span>  
 <span data-ttu-id="e2fce-111">**Casos clasificados en**</span><span class="sxs-lookup"><span data-stu-id="e2fce-111">**Cases Classified To**</span></span>  
 <span data-ttu-id="e2fce-112">Muestra la definición de la regla, el conjunto de elementos y el clúster contenidos en el nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e2fce-112">Displays the definition of the rule, itemset, and cluster that are contained in the selected node.</span></span>  
  
 <span data-ttu-id="e2fce-113">**Lista de columnas**</span><span class="sxs-lookup"><span data-stu-id="e2fce-113">**Column list**</span></span>  
 <span data-ttu-id="e2fce-114">Muestra las columnas del modelo, seguidas por las columnas de estructura.</span><span class="sxs-lookup"><span data-stu-id="e2fce-114">Displays the columns in the model, followed by the structure columns.</span></span>  
  
 <span data-ttu-id="e2fce-115">**Nota** : las columnas de estructura solamente se muestran si la obtención de detalles está habilitada en la estructura de minería de datos y si se ha seleccionado la opción, **Columnas de modelo y estructura**.</span><span class="sxs-lookup"><span data-stu-id="e2fce-115">**Note** Structure columns are displayed only if drillthrough is enabled on the mining structure, and if you selected the option, **Model and Structure Columns**.</span></span> <span data-ttu-id="e2fce-116">Además, debe tener permisos de obtención de detalles en el modelo de minería de datos y en la estructura de minería de datos para ver las columnas.</span><span class="sxs-lookup"><span data-stu-id="e2fce-116">Moreover, you must have drillthrough permissions on both the mining model and the mining structure to view the columns.</span></span>  
  
 <span data-ttu-id="e2fce-117">Las columnas de estructura que no están incluidas en el modelo aparecen como \*\*Structure. \<column name> \*\*</span><span class="sxs-lookup"><span data-stu-id="e2fce-117">Structure columns that are not included in the model appear as **Structure.\<column name>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2fce-118">Puede hacer clic con el botón derecho en cualquier lugar de la cuadrícula de columnas y seleccionar **Copiar todo** para copiar en el Portapapeles los datos de la obtención de detalles, en formato delimitado por tabuladores.</span><span class="sxs-lookup"><span data-stu-id="e2fce-118">You can right-click anywhere in the column grid and select **Copy All** to copy the drillthrough data, in tab-delimited format, to the Clipboard.</span></span> <span data-ttu-id="e2fce-119">Los datos copiados incluyen solo los datos de los casos, no la definición del nodo.</span><span class="sxs-lookup"><span data-stu-id="e2fce-119">The copied data includes only the case data, not the node definition.</span></span>  
  
 <span data-ttu-id="e2fce-120">**Reproducir**</span><span class="sxs-lookup"><span data-stu-id="e2fce-120">**Play**</span></span>  
 <span data-ttu-id="e2fce-121">Haga clic en el botón de flecha verde para actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="e2fce-121">Click the green arrow button to refresh the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2fce-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2fce-122">See Also</span></span>  
 <span data-ttu-id="e2fce-123">[Consultas de obtención de detalles &#40;&#41;de minería de datos](data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e2fce-123">[Drillthrough Queries &#40;Data Mining&#41;](data-mining/drillthrough-queries-data-mining.md) </span></span>  
 <span data-ttu-id="e2fce-124">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="e2fce-124">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="e2fce-125">Tareas y procedimientos del Visor de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e2fce-125">Mining Model Viewer Tasks and How-tos</span></span>](data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  
  
