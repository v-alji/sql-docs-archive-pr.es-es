---
title: Insertar o eliminar una fila (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b9642af3-b3ae-4f78-b0be-8f96b79fc313
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fdec24801d1fae3b95c7d75acb5a3add650d523b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749094"
---
# <a name="insert-or-delete-a-row-report-builder-and-ssrs"></a><span data-ttu-id="db5b2-102">Insertar o eliminar una fila (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="db5b2-102">Insert or Delete a Row (Report Builder and SSRS)</span></span>
  <span data-ttu-id="db5b2-103">Puede agregar o eliminar filas de una región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="db5b2-103">You can add or delete rows in a tablix data region.</span></span> <span data-ttu-id="db5b2-104">La región de datos Tablix puede ser una tabla, una matriz o una lista.</span><span class="sxs-lookup"><span data-stu-id="db5b2-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="db5b2-105">Los procedimientos siguientes no se aplican a las regiones de datos Gráfico y Medidor.</span><span class="sxs-lookup"><span data-stu-id="db5b2-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="db5b2-106">En una región de datos Tablix, puede agregar filas que están asociadas a un grupo (dentro de un grupo) o que no están asociadas a un grupo (fuera de un grupo).</span><span class="sxs-lookup"><span data-stu-id="db5b2-106">In a tablix data region, you can add rows that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="db5b2-107">Una fila que está dentro de un grupo se repite una vez para cada valor de grupo único.</span><span class="sxs-lookup"><span data-stu-id="db5b2-107">A row that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="db5b2-108">Por ejemplo, una fila dentro de un grupo que está basada en el valor de una columna de datos que contiene nombres de colores se repite una vez para cada nombre de color.</span><span class="sxs-lookup"><span data-stu-id="db5b2-108">For example, a row inside a group based on the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="db5b2-109">Para los grupos anidados, una fila puede estar fuera del grupo secundario, pero dentro del grupo primario.</span><span class="sxs-lookup"><span data-stu-id="db5b2-109">For nested groups, a row can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="db5b2-110">En este caso, la fila se repite una vez para cada valor único del grupo primario.</span><span class="sxs-lookup"><span data-stu-id="db5b2-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-the-row-and-column-handles-appear"></a><span data-ttu-id="db5b2-111">Para seleccionar una región de datos con objeto de que aparezcan los identificadores de columna y de fila</span><span class="sxs-lookup"><span data-stu-id="db5b2-111">To select a data region so the row and column handles appear</span></span>  
  
-   <span data-ttu-id="db5b2-112">En la vista Diseño, haga clic en la esquina superior izquierda de la región de datos Tablix para que los identificadores de columna y de fila aparezcan por encima y junto a ella.</span><span class="sxs-lookup"><span data-stu-id="db5b2-112">In Design view, click the upper left corner of the tablix data region so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="db5b2-113">Para obtener más información sobre las áreas de la región de datos, vea [listas &#40;generador de informes y SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="db5b2-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-row-in-a-selected-data-region"></a><span data-ttu-id="db5b2-114">Para insertar una fila en una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="db5b2-114">To insert a row in a selected data region</span></span>  
  
-   <span data-ttu-id="db5b2-115">Haga clic con el botón derecho en el identificador de fila donde quiera insertar una fila, haga clic en **Insertar fila**y, después, haga clic en **Por encima** o **Por debajo**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-115">Right-click a row handle where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
     <span data-ttu-id="db5b2-116">\- O bien</span><span class="sxs-lookup"><span data-stu-id="db5b2-116">\- or -</span></span>  
  
-   <span data-ttu-id="db5b2-117">Haga clic con el botón derecho en una celda de la región de datos donde quiera insertar una fila, haga clic en **Insertar fila**y, después, haga clic en **Por encima** o **Por debajo**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-117">Right-click a cell in the data region where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
### <a name="to-delete-a-row-from-a-selected-data-region"></a><span data-ttu-id="db5b2-118">Para eliminar una fila de una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="db5b2-118">To delete a row from a selected data region</span></span>  
  
-   <span data-ttu-id="db5b2-119">Seleccione las filas que quiere eliminar, haga clic con el botón derecho en el identificador de una de las filas seleccionadas y, después, haga clic en **Eliminar filas**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-119">Select the row or rows that you want to delete, right-click the handle for one of the rows you selected, and then click **Delete Rows**.</span></span>  
  
     <span data-ttu-id="db5b2-120">\- O bien</span><span class="sxs-lookup"><span data-stu-id="db5b2-120">\- or -</span></span>  
  
-   <span data-ttu-id="db5b2-121">Haga clic con el botón derecho en una celda de la región de datos de la que quiere eliminar una fila y, después, haga clic en **Eliminar filas**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-121">Right-click a cell in the data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
### <a name="to-insert-a-row-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="db5b2-122">Para insertar una fila en un grupo de una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="db5b2-122">To insert a row in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="db5b2-123">Haga clic con el botón derecho en una celda de grupo de filas en el área de grupo de filas de una región de datos Tablix donde quiera insertar una fila, haga clic en **Insertar fila**y, después, haga clic en **Por encima - Fuera del grupo**, **Por encima - Dentro del grupo**, **Por debajo - Dentro del grupo**o **Por debajo - Fuera del grupo**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-123">Right-click a row group cell in the row group area of a tablix data region where you want to insert a row, click **Insert Row**, and then click **Above - Outside Group**, **Above - Inside Group**, **Below - Inside Group**, or **Below - Outside Group**.</span></span>  
  
     <span data-ttu-id="db5b2-124">Una vez hecho esto, se agrega una fila dentro o fuera del grupo representado por la celda de grupo de filas sobre la que ha hecho clic.</span><span class="sxs-lookup"><span data-stu-id="db5b2-124">A row is added either inside or outside the group represented by the row group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-row-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="db5b2-125">Para eliminar una fila de un grupo en una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="db5b2-125">To delete a row from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="db5b2-126">Haga clic con el botón derecho en una celda de grupo de filas del área de grupo de filas de una región de datos Tablix de la que quiere eliminar una fila y, después, haga clic en **Eliminar filas**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-126">Right-click a row group cell in the row group area of a tablix data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db5b2-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db5b2-127">See Also</span></span>  
 <span data-ttu-id="db5b2-128">[Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="db5b2-128">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="db5b2-129">[Descripción de los grupos &#40;Generador de informes y SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="db5b2-129">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="db5b2-130">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="db5b2-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="db5b2-131">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="db5b2-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="db5b2-132">[Listas &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="db5b2-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="db5b2-133">Listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="db5b2-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
