---
title: Eliminar un filtro de un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filters [Analysis Services]
ms.assetid: 91220b21-adbc-49a9-b200-8bf0a724eff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 404c23c0e55bffba2ce8410c9c30d6ad1fa1991b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663793"
---
# <a name="delete-a-filter-from-a-mining-model"></a><span data-ttu-id="a73f3-102">Eliminar un filtro de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a73f3-102">Delete a Filter from a Mining Model</span></span>
  <span data-ttu-id="a73f3-103">Al crear un filtro en un modelo de minería de datos, puede crear modelos en un subconjunto de los datos en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a73f3-103">When you create a filter on a mining model, you can create models on a subset of the data in the data source view.</span></span> <span data-ttu-id="a73f3-104">Los filtros también son útiles para probar la precisión del modelo en un subconjunto de los datos originales.</span><span class="sxs-lookup"><span data-stu-id="a73f3-104">Filters are also useful for testing the accuracy of the model on a subset of the original data.</span></span>  
  
 <span data-ttu-id="a73f3-105">Sin embargo, debe eliminar el filtro si desea ver de nuevo el conjunto completo de casos.</span><span class="sxs-lookup"><span data-stu-id="a73f3-105">However, you must delete the filter if you want to view the complete set of cases again.</span></span> <span data-ttu-id="a73f3-106">Este procedimiento describe cómo quitar las condiciones de un filtro o eliminar éste por completo.</span><span class="sxs-lookup"><span data-stu-id="a73f3-106">This procedure describes how to remove conditions on a filter, or delete the filter completely.</span></span>  
  
### <a name="to-delete-a-condition-from-a-filter-on-a-mining-model"></a><span data-ttu-id="a73f3-107">Para eliminar una condición de un filtro en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a73f3-107">To delete a condition from a filter on a mining model</span></span>  
  
1.  <span data-ttu-id="a73f3-108">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en el Explorador de soluciones, haga clic en la estructura de minería de datos que contiene el modelo de minería que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="a73f3-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="a73f3-109">Haga clic en la pestaña **Modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="a73f3-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="a73f3-110">Seleccione el modelo y haga clic con el botón secundario del mouse para abrir el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a73f3-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="a73f3-111">O bien</span><span class="sxs-lookup"><span data-stu-id="a73f3-111">-or-</span></span>  
  
     <span data-ttu-id="a73f3-112">Seleccione el modelo.</span><span class="sxs-lookup"><span data-stu-id="a73f3-112">Select the model.</span></span> <span data-ttu-id="a73f3-113">En el menú **Minería de datos** , seleccione **Establecer filtro de modelos**.</span><span class="sxs-lookup"><span data-stu-id="a73f3-113">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="a73f3-114">En el cuadro de diálogo **Filtro del modelo** , haga clic con el botón derecho en la fila de la cuadrícula que contiene la condición que quiere eliminar.</span><span class="sxs-lookup"><span data-stu-id="a73f3-114">In the **Model Filter** dialog box, right-click the row in the grid that contains the condition you want to delete.</span></span>  
  
5.  <span data-ttu-id="a73f3-115">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a73f3-115">Select **Delete**.</span></span>  
  
### <a name="to-clear-the-filter-on-a-mining-model-in-the-filter-editor-dialog-box"></a><span data-ttu-id="a73f3-116">Para borrar el filtro de un modelo de minería de datos en el cuadro de diálogo Editor de filtros</span><span class="sxs-lookup"><span data-stu-id="a73f3-116">To clear the filter on a mining model in the Filter Editor dialog box</span></span>  
  
-   <span data-ttu-id="a73f3-117">En el cuadro de diálogo **Editor de filtros** , haga clic con el botón derecho en cualquier fila de la cuadrícula y seleccione **Eliminar todos**.</span><span class="sxs-lookup"><span data-stu-id="a73f3-117">In the **Filter Editor** dialog box, right-click any row in the grid, and select **Delete All**.</span></span>  
  
## <a name="working-with-model-filters-using-the-properties-window"></a><span data-ttu-id="a73f3-118">Trabajar con filtros de modelo utilizando la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="a73f3-118">Working with Model Filters Using the Properties Window</span></span>  
 <span data-ttu-id="a73f3-119">Si desea eliminar todo el filtro, no necesita abrir los cuadros de diálogo del editor de filtros.</span><span class="sxs-lookup"><span data-stu-id="a73f3-119">If you want to delete the whole filter, you do not need to open the filter editor dialog boxes.</span></span> <span data-ttu-id="a73f3-120">Las condiciones de filtrado que creó están disponibles en la propiedad `Filter` del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a73f3-120">The filter conditions that you created are available in the `Filter` property of the mining model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a73f3-121">Puede ver las propiedades de un modelo de minería de datos en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], pero no en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a73f3-121">You can view the properties of a mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], but not in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-clear-the-filter-on-a-mining-model-in-solution-explorer"></a><span data-ttu-id="a73f3-122">Para borrar el filtro de un modelo de minería de datos en el Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="a73f3-122">To clear the filter on a mining model in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="a73f3-123">En el Explorador de soluciones, haga clic en el modelo de minería de datos que contiene el filtro.</span><span class="sxs-lookup"><span data-stu-id="a73f3-123">In Solution Explorer, click the mining model that contains the filter.</span></span>  
  
2.  <span data-ttu-id="a73f3-124">En la ventana **propiedades** , haga clic con el botón secundario en el texto del filtro en la `Filter` propiedad y seleccione **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="a73f3-124">In the **Properties** window, right-click the filter text in the `Filter` property, and select **Select All**.</span></span>  
  
3.  <span data-ttu-id="a73f3-125">Presione la tecla Retroceso o Suprimir.</span><span class="sxs-lookup"><span data-stu-id="a73f3-125">Press the Backspace or Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a73f3-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a73f3-126">See Also</span></span>  
 <span data-ttu-id="a73f3-127">[Obtener detalles de los datos de los casos de un modelo de minería de datos](drill-through-to-case-data-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="a73f3-127">[Drill Through to Case Data from a Mining Model](drill-through-to-case-data-from-a-mining-model.md) </span></span>  
 <span data-ttu-id="a73f3-128">[Tareas y procedimientos del modelo de minería de datos](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="a73f3-128">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="a73f3-129">Filtros para modelos de minería &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a73f3-129">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
  
