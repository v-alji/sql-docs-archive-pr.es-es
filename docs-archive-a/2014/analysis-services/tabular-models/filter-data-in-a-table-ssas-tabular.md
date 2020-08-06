---
title: Filtrar datos en una tabla (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.customfilterdb.f1
- sql12.asvs.bidtoolset.autofiltermenu.f1
- sql12.asvs.bidtoolset.notallitemsshowing.f1
ms.assetid: 3223059d-f525-4835-bf88-ebc195d9dbdc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f4003457df4068713e75e6bb5c0ab78c15ac03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744377"
---
# <a name="filter-data-in-a-table-ssas-tabular"></a><span data-ttu-id="a5bff-102">Filtrar los datos de una tabla (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="a5bff-102">Filter Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="a5bff-103">Puede aplicar filtros al importar datos para controlar las filas que se cargan en una tabla.</span><span class="sxs-lookup"><span data-stu-id="a5bff-103">You can apply filters when you import data to control the rows that are loaded into a table.</span></span> <span data-ttu-id="a5bff-104">Después de haber importado los datos, no podrá eliminar filas individuales.</span><span class="sxs-lookup"><span data-stu-id="a5bff-104">After you have imported the data, you cannot delete individual rows.</span></span> <span data-ttu-id="a5bff-105">Sin embargo, puede aplicar filtros personalizados para controlar la manera en que se muestran las filas.</span><span class="sxs-lookup"><span data-stu-id="a5bff-105">However, you can apply custom filters to control the way that rows are displayed.</span></span> <span data-ttu-id="a5bff-106">Las filas que no cumplen los criterios de filtrado se ocultan.</span><span class="sxs-lookup"><span data-stu-id="a5bff-106">Rows that do not meet the filtering criteria are hidden.</span></span> <span data-ttu-id="a5bff-107">Puede filtrar por una o más columnas.</span><span class="sxs-lookup"><span data-stu-id="a5bff-107">You can filter by one or more columns.</span></span> <span data-ttu-id="a5bff-108">Los filtros son aditivos, lo que significa que cada filtro adicional se basa en el actual y reduce aún más el subconjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a5bff-108">Filters are additive, which means that each additional filter is based on the current filter and further reduces the subset of data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5bff-109">La ventana de vista previa del filtro limita el número de valores diferentes que se muestran.</span><span class="sxs-lookup"><span data-stu-id="a5bff-109">The filter preview window limits the number of different values displayed.</span></span> <span data-ttu-id="a5bff-110">Si se supera el límite, aparece un mensaje.</span><span class="sxs-lookup"><span data-stu-id="a5bff-110">If the limit is exceeded, a message is displayed.</span></span>  
  
### <a name="to-filter-data-based-on-column-values"></a><span data-ttu-id="a5bff-111">Para filtrar datos según los valores de las columnas</span><span class="sxs-lookup"><span data-stu-id="a5bff-111">To filter data based on column values</span></span>  
  
1.  <span data-ttu-id="a5bff-112">En el diseñador de modelos, seleccione una tabla y, a continuación, haga clic en la flecha del encabezado de la columna por la que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="a5bff-112">In the model designer, select a table, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="a5bff-113">En el menú Autofiltro, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="a5bff-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="a5bff-114">En la lista de valores de columna, Active o desactive uno o varios valores para filtrar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5bff-114">In the list of column values, select or clear one or more values to filter by, and then click **OK**.</span></span>  
  
         <span data-ttu-id="a5bff-115">Si el número de valores es sumamente grande, algunos elementos individuales podrían no mostrarse en la lista.</span><span class="sxs-lookup"><span data-stu-id="a5bff-115">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="a5bff-116">En su lugar, verá un mensaje similar a "Demasiados elementos para mostrar".</span><span class="sxs-lookup"><span data-stu-id="a5bff-116">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="a5bff-117">Haga clic en filtros de **números** o **filtros de texto** (en función del tipo de columna) y, a continuación, haga clic en los comandos del operador de comparación (como **es igual**a) o haga clic en **filtro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="a5bff-117">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as **Equals**), or click **Custom Filter**.</span></span> <span data-ttu-id="a5bff-118">En el cuadro de diálogo **Filtro personalizado** , cree el filtro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5bff-118">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
### <a name="to-clear-a-filter-for-a-column"></a><span data-ttu-id="a5bff-119">Para borrar un filtro para una columna</span><span class="sxs-lookup"><span data-stu-id="a5bff-119">To clear a filter for a column</span></span>  
  
1.  <span data-ttu-id="a5bff-120">Haga clic en la flecha del encabezado de la columna en la que desea borrar un filtro.</span><span class="sxs-lookup"><span data-stu-id="a5bff-120">Click the arrow in the header of the column for which you want to clear a filter.</span></span>  
  
2.  <span data-ttu-id="a5bff-121">Haga clic en \*\*Borrar \<Column Name> filtro de \*\*.</span><span class="sxs-lookup"><span data-stu-id="a5bff-121">Click **Clear Filter from \<Column Name>**.</span></span>  
  
### <a name="to-clear-all-filters-for-a-table"></a><span data-ttu-id="a5bff-122">Para borrar todos los filtros de una tabla</span><span class="sxs-lookup"><span data-stu-id="a5bff-122">To clear all filters for a table</span></span>  
  
1.  <span data-ttu-id="a5bff-123">En el diseñador de modelos, seleccione la tabla en la que desea borrar los filtros.</span><span class="sxs-lookup"><span data-stu-id="a5bff-123">In the model designer, select the table for which you want to clear filters.</span></span>  
  
2.  <span data-ttu-id="a5bff-124">Haga clic en el menú **Columna** y, a continuación, haga clic en **Borrar todos los filtros**.</span><span class="sxs-lookup"><span data-stu-id="a5bff-124">Click on the **Column** menu, and then click **Clear All Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5bff-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5bff-125">See Also</span></span>  
 <span data-ttu-id="a5bff-126">[Filtrar y ordenar datos &#40;SSAS tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a5bff-126">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="a5bff-127">[Perspectivas &#40;SSAS tabular&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a5bff-127">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a5bff-128">Roles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="a5bff-128">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
