---
title: Insertar o eliminar una columna (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9db79e2-7e7d-4359-a706-cb746c94182a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9a6f782dbb6cc1024583926aafe4bab1cfe2d042
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749097"
---
# <a name="insert-or-delete-a-column-report-builder-and-ssrs"></a><span data-ttu-id="27068-102">Insertar o eliminar una columna (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="27068-102">Insert or Delete a Column (Report Builder and SSRS)</span></span>
  <span data-ttu-id="27068-103">Puede agregar o eliminar columnas en una región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="27068-103">You can add or delete columns in a tablix data region.</span></span> <span data-ttu-id="27068-104">La región de datos Tablix puede ser una tabla, una matriz o una lista.</span><span class="sxs-lookup"><span data-stu-id="27068-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="27068-105">Los procedimientos siguientes no se aplican a las regiones de datos Gráfico y Medidor.</span><span class="sxs-lookup"><span data-stu-id="27068-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="27068-106">En una región de datos Tablix, puede agregar columnas que están asociadas a un grupo (dentro de un grupo) o que no están asociadas a un grupo (fuera de un grupo).</span><span class="sxs-lookup"><span data-stu-id="27068-106">In a tablix data region, you can add columns that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="27068-107">Una columna que está dentro de un grupo se repite una vez para cada valor de grupo único.</span><span class="sxs-lookup"><span data-stu-id="27068-107">A column that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="27068-108">Por ejemplo, una columna dentro de un grupo que está basada en el valor de una columna de datos que contiene nombres de colores se repite una vez para cada nombre de color.</span><span class="sxs-lookup"><span data-stu-id="27068-108">For example, a column inside a group based the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="27068-109">Para los grupos anidados, una columna puede estar fuera del grupo secundario, pero dentro del grupo primario.</span><span class="sxs-lookup"><span data-stu-id="27068-109">For nested groups, a column can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="27068-110">En este caso, la fila se repite una vez para cada valor único del grupo primario.</span><span class="sxs-lookup"><span data-stu-id="27068-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-that-the-row-and-column-handles-appear"></a><span data-ttu-id="27068-111">Para seleccionar una región de datos con objeto de que aparezcan los identificadores de columna y de fila</span><span class="sxs-lookup"><span data-stu-id="27068-111">To select a data region so that the row and column handles appear</span></span>  
  
-   <span data-ttu-id="27068-112">En la vista Diseño, haga clic en la esquina superior izquierda de la región de datos Tablix para que los identificadores de columna y de fila aparezcan por encima y junto a ella.</span><span class="sxs-lookup"><span data-stu-id="27068-112">In Design view, click the upper left corner of the tablix data region, so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="27068-113">Para obtener más información sobre las áreas de la región de datos, vea [listas &#40;generador de informes y SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27068-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-column-in-a-selected-data-region"></a><span data-ttu-id="27068-114">Para insertar una columna en una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="27068-114">To insert a column in a selected data region</span></span>  
  
-   <span data-ttu-id="27068-115">Haga clic con el botón derecho en el identificador de columna donde quiera insertar una columna, seleccione **Insertar columna**y, después, haga clic en **Izquierda** o **Derecha**.</span><span class="sxs-lookup"><span data-stu-id="27068-115">Right-click a column handle where you want to insert a column, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
     <span data-ttu-id="27068-116">-- o --</span><span class="sxs-lookup"><span data-stu-id="27068-116">-- or --</span></span>  
  
-   <span data-ttu-id="27068-117">Haga clic con el botón derecho en una celda de la región de datos donde quiera insertar una fila, seleccione **Insertar columna**y, después, haga clic en **Izquierda** o **Derecha**.</span><span class="sxs-lookup"><span data-stu-id="27068-117">Right-click a cell in the data region where you want to insert a row, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
### <a name="to-delete-a-column-from-a-selected-data-region"></a><span data-ttu-id="27068-118">Para eliminar una columna de una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="27068-118">To delete a column from a selected data region</span></span>  
  
-   <span data-ttu-id="27068-119">Seleccione las columnas que quiera eliminar, haga clic con el botón derecho en el identificador de una de las columnas seleccionadas y, después, haga clic en **Eliminar columnas**.</span><span class="sxs-lookup"><span data-stu-id="27068-119">Select the column or columns that you want to delete, right-click the handle for one of the columns you selected, and then click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="27068-120">-- o --</span><span class="sxs-lookup"><span data-stu-id="27068-120">-- or --</span></span>  
  
-   <span data-ttu-id="27068-121">Haga clic con el botón derecho en una celda de la región de datos de la que quiere eliminar una columna y, después, haga clic en **Eliminar columnas**.</span><span class="sxs-lookup"><span data-stu-id="27068-121">Right-click a cell in the data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
### <a name="to-insert-a-column-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="27068-122">Para insertar una columna en un grupo de una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="27068-122">To insert a column in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="27068-123">Haga clic con el botón derecho en una celda de grupo de columnas en el área de grupo de columnas de la región de datos Tablix donde quiera insertar una columna, seleccione **Insertar columna**y, después, haga clic en **Fuera del grupo - Izquierda**, **Dentro del grupo - Izquierda**, **Dentro del grupo - Derecha**o **Fuera del grupo - Derecha**.</span><span class="sxs-lookup"><span data-stu-id="27068-123">Right-click a column group cell in the column group area of a tablix data region where you want to insert a column, click **Insert Column**, and then click **Left - Outside Group**, **Left - Inside Group**, **Right - Inside Group**, or **Right - Outside Group**.</span></span>  
  
     <span data-ttu-id="27068-124">Una vez hecho esto, se agrega una columna dentro o fuera del grupo representado por la celda de grupo de columnas sobre la que ha hecho clic.</span><span class="sxs-lookup"><span data-stu-id="27068-124">A column is added either inside or outside the group represented by the column group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-column-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="27068-125">Para eliminar una columna de un grupo en una región de datos seleccionada</span><span class="sxs-lookup"><span data-stu-id="27068-125">To delete a column from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="27068-126">Haga clic con el botón derecho en una celda de grupo de columnas en el área de grupo de columnas de la región de datos Tablix de la que quiera eliminar una columna y, después, haga clic en **Eliminar columnas**.</span><span class="sxs-lookup"><span data-stu-id="27068-126">Right-click a column group cell in the column group area of a tablix data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27068-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27068-127">See Also</span></span>  
 <span data-ttu-id="27068-128">[Descripción de los grupos &#40;Generador de informes y SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27068-128">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27068-129">[Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27068-129">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27068-130">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27068-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27068-131">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27068-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27068-132">[Listas &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27068-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="27068-133">Listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="27068-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
