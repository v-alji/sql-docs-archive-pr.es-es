---
title: Agregar un total a un grupo o a una región de datos Tablix (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cf1b96c3-7f0f-4c94-ad08-5239c77ccfe4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f626621a37a327ae32664ab9444e72ce4931ac0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662555"
---
# <a name="add-a-total-to-a-group-or-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="05bcc-102">Agregar un total a un grupo o a una región de datos Tablix (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="05bcc-102">Add a Total to a Group or Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="05bcc-103">Puede agregar totales en una región de datos Tablix solo para un grupo o para toda la región de datos.</span><span class="sxs-lookup"><span data-stu-id="05bcc-103">You can add totals in a tablix data region for a group or for the entire data region.</span></span> <span data-ttu-id="05bcc-104">De forma predeterminada, un total es la suma de los datos numéricos no NULL de un grupo o de la región de datos, una vez aplicados los filtros.</span><span class="sxs-lookup"><span data-stu-id="05bcc-104">By default, a total is the sum of the numeric, non-null data in a group or in the data region, after filters are applied.</span></span> <span data-ttu-id="05bcc-105">Para agregar totales a un grupo, haga clic en **Agregar total** en el menú contextual del grupo en el panel Agrupación.</span><span class="sxs-lookup"><span data-stu-id="05bcc-105">To add totals for a group, click **Add Total** on the shortcut menu for the group in the Grouping pane.</span></span> <span data-ttu-id="05bcc-106">Para agregar totales a una celda individual en el área del cuerpo Tablix, haga clic en **Agregar total** en el menú contextual de la celda.</span><span class="sxs-lookup"><span data-stu-id="05bcc-106">To add totals for an individual cell in the tablix body area, click **Add Total** on the shortcut menu for the cell.</span></span> <span data-ttu-id="05bcc-107">El comando **Agregar total** es contextual y solo está habilitado para los campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="05bcc-107">The **Add Total** command is context-sensitive and enabled only for numeric fields.</span></span> <span data-ttu-id="05bcc-108">En función de la celda de Tablix seleccionada, puede agregar un total para una única celda, seleccionando una celda en el área del cuerpo de Tablix, o para el grupo completo, seleccionando una celda en el área del grupo de filas o del grupo de columnas de Tablix.</span><span class="sxs-lookup"><span data-stu-id="05bcc-108">Depending on the tablix cell that you select, you can add a total for a single cell by selecting a cell in the tablix body area or for the entire group by selecting a cell in the tablix row group area or the tablix column group area.</span></span> <span data-ttu-id="05bcc-109">Para obtener más información sobre las áreas de Tablix, vea [Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05bcc-109">For more information about tablix areas, see [Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="05bcc-110">Después de agregar un total, puede cambiar la función Sum predeterminada por una función de agregado diferente de la lista de funciones de informe integradas.</span><span class="sxs-lookup"><span data-stu-id="05bcc-110">After you add a total, you can change the default function Sum to a different aggregate function from the list of built-in report functions.</span></span> <span data-ttu-id="05bcc-111">Para obtener más información, vea [referencia a las funciones de agregado &#40;generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).[!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05bcc-111">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).[!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]</span></span>  
  
### <a name="to-add-a-total-for-an-individual-value-in-the-tablix-body-area"></a><span data-ttu-id="05bcc-112">Para agregar un total a un valor individual en el área del cuerpo de Tablix</span><span class="sxs-lookup"><span data-stu-id="05bcc-112">To add a total for an individual value in the tablix body area</span></span>  
  
-   <span data-ttu-id="05bcc-113">En el área del cuerpo de la región de datos Tablix, haga clic con el botón secundario en la celda donde desea agregar el total.</span><span class="sxs-lookup"><span data-stu-id="05bcc-113">In the tablix data region body area, right-click the cell where you want to add the total.</span></span> <span data-ttu-id="05bcc-114">La celda debe contener un campo numérico.</span><span class="sxs-lookup"><span data-stu-id="05bcc-114">The cell must contain a numeric field.</span></span> <span data-ttu-id="05bcc-115">Seleccione **Agregar total**y, a continuación, haga clic en **Fila** o **Columna**.</span><span class="sxs-lookup"><span data-stu-id="05bcc-115">Point to **Add Total**, and then click **Row** or **Column**.</span></span>  
  
     <span data-ttu-id="05bcc-116">Se agrega a la región de datos una nueva fila o columna fuera del grupo actual, con un total predeterminado para el campo de la celda en la que hizo clic.</span><span class="sxs-lookup"><span data-stu-id="05bcc-116">A new row or column outside the current group is added to the data region, with a default total for the field in the cell you clicked.</span></span>  
  
     <span data-ttu-id="05bcc-117">Si la región de datos Tablix es una tabla, automáticamente se agrega una fila.</span><span class="sxs-lookup"><span data-stu-id="05bcc-117">If the tablix data region is a table, a row is automatically added.</span></span>  
  
### <a name="to-add-totals-for-a-row-group"></a><span data-ttu-id="05bcc-118">Para agregar totales a un grupo de filas</span><span class="sxs-lookup"><span data-stu-id="05bcc-118">To add totals for a row group</span></span>  
  
-   <span data-ttu-id="05bcc-119">En el área de grupo de filas de la región de datos Tablix, haga clic con el botón derecho en una celda del área de grupo de filas cuyos totales quiere calcular, seleccione **Agregar total**y, luego, haga clic en **Antes** o **Después**.</span><span class="sxs-lookup"><span data-stu-id="05bcc-119">In the tablix data region row group area, right-click a cell in the row group area for which you want totals, point to **Add Total**, and then click **Before** or **After**.</span></span>  
  
     <span data-ttu-id="05bcc-120">Se agrega a la región de datos una nueva fila fuera del grupo actual y, a continuación, se agrega un total predeterminado para cada campo numérico de la fila.</span><span class="sxs-lookup"><span data-stu-id="05bcc-120">A new row outside the current group is added to the data region, and then a default total is added for each numeric field in the row.</span></span>  
  
### <a name="to-add-totals-for-a-column-group"></a><span data-ttu-id="05bcc-121">Para agregar totales a un grupo de columnas</span><span class="sxs-lookup"><span data-stu-id="05bcc-121">To add totals for a column group</span></span>  
  
-   <span data-ttu-id="05bcc-122">En el área de grupo de filas de la región de datos Tablix, haga clic con el botón derecho en la celda del área de grupo de columnas cuyos totales quiere calcular, seleccione **Agregar total**y, luego, haga clic en **Antes** o **Después**.</span><span class="sxs-lookup"><span data-stu-id="05bcc-122">In the tablix data region row group area, right-click a cell in the column group area for which you want totals, then point to **Add Total**, and click **Before** or **After**.</span></span>  
  
     <span data-ttu-id="05bcc-123">Se agrega a la región de datos una nueva columna fuera del grupo actual y, a continuación, se agrega un total predeterminado para cada campo numérico de la columna.</span><span class="sxs-lookup"><span data-stu-id="05bcc-123">A new column outside the current group is added to the data region, and then a default total is added for each numeric field in the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05bcc-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05bcc-124">See Also</span></span>  
 <span data-ttu-id="05bcc-125">[Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md) </span><span class="sxs-lookup"><span data-stu-id="05bcc-125">[Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md) </span></span>  
 <span data-ttu-id="05bcc-126">[&#40;de la región de datos Tablix Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05bcc-126">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05bcc-127">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05bcc-127">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05bcc-128">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05bcc-128">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05bcc-129">[Enumera &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05bcc-129">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="05bcc-130">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05bcc-130">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  