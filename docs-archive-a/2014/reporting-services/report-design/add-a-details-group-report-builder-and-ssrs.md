---
title: Agregar un grupo de detalles (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ef8efba-6d48-4aeb-a3b9-a02ba5a44614
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24b1f6af1aaf336a69a0068636ced60c364e556d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672766"
---
# <a name="add-a-details-group-report-builder-and-ssrs"></a><span data-ttu-id="c583a-102">Agregar un grupo de detalles (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="c583a-102">Add a Details Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c583a-103">Los datos detallados de un conjunto de datos de informe se especifican como un grupo sin expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="c583a-103">The detail data from a report dataset is specified as a group with no group expression.</span></span> <span data-ttu-id="c583a-104">Agregue un grupo de detalles a una región de datos Tablix existente si desea mostrar los datos detallados para una matriz, volver a incluir datos detallados que ha eliminado de una tabla o lista, o agregar grupos de detalles adicionales.</span><span class="sxs-lookup"><span data-stu-id="c583a-104">Add a detail group to an existing tablix data region when you want to display the detail data for a matrix, add back detail data that you have deleted from a table or list, or to add additional detail groups.</span></span> <span data-ttu-id="c583a-105">Para obtener más información sobre los grupos, vea [Descripción de los grupos &#40;Generador de informes y SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c583a-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="c583a-106">Para agregar un grupo de detalles a una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="c583a-106">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="c583a-107">En la superficie de diseño, haga clic en cualquier lugar de una región de datos Tablix para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="c583a-107">On the design surface, click anywhere in a tablix data region to select it.</span></span> <span data-ttu-id="c583a-108">El panel Agrupación muestra los grupos de filas y de columnas para la región de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c583a-108">The Grouping pane displays the row and column groups for the selected data region.</span></span>  
  
2.  <span data-ttu-id="c583a-109">En el panel Agrupación, haga clic con el botón secundario en un grupo que sea el grupo secundario más interior.</span><span class="sxs-lookup"><span data-stu-id="c583a-109">In the Grouping pane, right-click a group that is an innermost child group.</span></span> <span data-ttu-id="c583a-110">Haga clic en **Agregar grupo**y, a continuación, haga clic en **Grupo secundario**.</span><span class="sxs-lookup"><span data-stu-id="c583a-110">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="c583a-111">Se abre el cuadro de diálogo **Grupo de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="c583a-111">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c583a-112">En **Expresión de grupo**, deje en blanco la expresión.</span><span class="sxs-lookup"><span data-stu-id="c583a-112">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="c583a-113">Los grupos de detalles no tienen ninguna expresión.</span><span class="sxs-lookup"><span data-stu-id="c583a-113">A details group has no expression.</span></span>  
  
4.  <span data-ttu-id="c583a-114">Seleccione **Mostrar datos detallados**.</span><span class="sxs-lookup"><span data-stu-id="c583a-114">Select **Show detail data**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="c583a-115">Se agrega un nuevo grupo de detalles como un grupo secundario en el panel Agrupación, y el identificador de fila para el grupo seleccionado en el paso 1 muestra el icono de grupo de detalles.</span><span class="sxs-lookup"><span data-stu-id="c583a-115">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="c583a-116">Para obtener más información sobre los identificadores, vea [Celdas, filas y columnas de la región de datos Tablix &#40;Generador de informes y SSRS&#41;](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c583a-116">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c583a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c583a-117">See Also</span></span>  
 <span data-ttu-id="c583a-118">[Agregar o eliminar un grupo en una región de datos &#40;Generador de informes y SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c583a-118">[Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c583a-119">[Descripción de los grupos &#40;Generador de informes y SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c583a-119">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c583a-120">[Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c583a-120">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c583a-121">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c583a-121">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c583a-122">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c583a-122">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c583a-123">[Enumera &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c583a-123">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c583a-124">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c583a-124">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
