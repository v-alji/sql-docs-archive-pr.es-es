---
title: Ordenar datos en una tabla (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5fa6ad56-bf68-4aac-a226-52556173b7e2
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9a6636c2c11fc571e8d4c1bcbc25c1e02d815fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743637"
---
# <a name="sort-data-in-a-table-ssas-tabular"></a><span data-ttu-id="a7fa8-102">Ordenar datos en una tabla (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="a7fa8-102">Sort Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="a7fa8-103">Puede ordenar los datos por texto (de A a Z o de Z a A) y los números (de menor a mayor o viceversa) en una o varias columnas.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-103">You can sort data by text (A to Z or Z to A) and numbers (smallest to largest or largest to smallest) in one or more columns.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-text-column"></a><span data-ttu-id="a7fa8-104">Para ordenar los datos de una tabla según una columna de texto</span><span class="sxs-lookup"><span data-stu-id="a7fa8-104">To sort the data in a table based on a text column</span></span>  
  
1.  <span data-ttu-id="a7fa8-105">En el Diseñador de modelos, seleccione una columna de datos alfanuméricos o un rango de celdas de una columna, o asegúrese de que la celda activa está en una columna de la tabla que contenga datos alfanuméricos; a continuación, haga clic en la flecha del encabezado de la columna que desea usar para el filtrado.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-105">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="a7fa8-106">En el menú Autofiltro, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="a7fa8-106">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="a7fa8-107">Para clasificar en orden alfanumérico ascendente, haga clic en **Ordenar de A a Z**.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-107">To sort in ascending alphanumeric order, click **Sort A to Z**.</span></span>  
  
    -   <span data-ttu-id="a7fa8-108">Para clasificar en orden alfanumérico descendente, haga clic en **Ordenar de Z a A.**</span><span class="sxs-lookup"><span data-stu-id="a7fa8-108">To sort in descending alphanumeric order, click **Sort Z to A**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7fa8-109">En algunos casos, los datos importados de otra aplicación podrían tener espacios iniciales incrustados antes de los datos.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-109">In some cases, data imported from another application might have leading spaces inserted before data.</span></span> <span data-ttu-id="a7fa8-110">Debe quitar los espacios iniciales para ordenar los datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-110">You must remove the leading spaces in order to correctly sort the data.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-numeric-column"></a><span data-ttu-id="a7fa8-111">Para ordenar los datos en una tabla según una columna numérica</span><span class="sxs-lookup"><span data-stu-id="a7fa8-111">To sort the data in a table based on a numeric column</span></span>  
  
1.  <span data-ttu-id="a7fa8-112">En el Diseñador de modelos, seleccione una columna de datos alfanuméricos o un rango de celdas de una columna, o asegúrese de que la celda activa está en una columna de la tabla que contenga datos alfanuméricos; a continuación, haga clic en la flecha del encabezado de la columna que desea usar para el filtrado.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-112">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="a7fa8-113">En el menú Autofiltro, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="a7fa8-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="a7fa8-114">Para ordenar de los números bajos a los números altos, haga clic en **Ordenar de menor a mayor**.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-114">To sort from low numbers to high numbers, click **Sort Smallest to Largest**.</span></span>  
  
    -   <span data-ttu-id="a7fa8-115">Para ordenar de los números altos a los números bajos, haga clic en **Ordenar de mayor a menor**.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-115">To sort from high numbers to low numbers, click **Sort Largest to Smallest**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7fa8-116">Si los resultados no son los que esperaba, la columna podría contener números almacenados como texto y no como números.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-116">If the results are not what you expected, the column might contain numbers stored as text and not as numbers.</span></span> <span data-ttu-id="a7fa8-117">Por ejemplo, los números negativos importados de algunos sistemas contables o un número escrito con un símbolo ' inicial (apóstrofo) se almacenan en forma de texto.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-117">For example, negative numbers imported from some accounting systems, or a number entered with a leading ' (apostrophe), are stored as text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fa8-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7fa8-118">See Also</span></span>  
 <span data-ttu-id="a7fa8-119">[Filtrar y ordenar datos &#40;SSAS tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a7fa8-119">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="a7fa8-120">[Perspectivas &#40;SSAS tabular&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a7fa8-120">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a7fa8-121">Roles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="a7fa8-121">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
