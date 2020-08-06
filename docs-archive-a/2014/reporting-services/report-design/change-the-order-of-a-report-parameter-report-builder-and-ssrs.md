---
title: Cambiar el orden de un parámetro de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748641"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="f79bb-102">Cambiar el orden de un parámetro de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="f79bb-102">Change the Order of a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f79bb-103">Cambie el orden de los parámetros de informe cuando tenga un parámetro dependiente que aparece antes que el parámetro del que depende.</span><span class="sxs-lookup"><span data-stu-id="f79bb-103">Change the order of report parameters when you have a dependent parameter that is listed before the parameter it is dependent on.</span></span> <span data-ttu-id="f79bb-104">El orden de los parámetros es importante cuando se tienen parámetros en cascada, o cuando se desea mostrar a los usuarios el valor predeterminado de un parámetro antes de que elijan valores para otros parámetros.</span><span class="sxs-lookup"><span data-stu-id="f79bb-104">Parameter order is important when you have cascading parameters, or when you want to show users the default value for one parameter before they choose values for other parameters.</span></span> <span data-ttu-id="f79bb-105">Un parámetro de informe dependiente contiene una referencia, ya sea en su consulta de valores predeterminados o en su consulta de valores válidos, a un parámetro de consulta que señala a un parámetro de informe situado después de él en la lista de parámetros del panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="f79bb-105">A dependent report parameter contains a reference, in either its default values query or valid values query, to a query parameter that points to a report parameter that is after it in the parameter list in the Report Data pane.</span></span>  
  
 <span data-ttu-id="f79bb-106">El orden en que se muestran los parámetros en la barra de herramientas del visor de informes lo determina el orden de los parámetros en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="f79bb-106">The order that you see parameters display on the report viewer toolbar is determined by the order of the parameters in the Report Data pane.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a><span data-ttu-id="f79bb-107">Para cambiar el orden de los parámetros de informe</span><span class="sxs-lookup"><span data-stu-id="f79bb-107">To change the order of report parameters</span></span>  
  
1.  <span data-ttu-id="f79bb-108">En el panel Datos de informe, expanda el nodo Parámetros.</span><span class="sxs-lookup"><span data-stu-id="f79bb-108">In the Report Data pane, expand the Parameters node.</span></span>  
  
2.  <span data-ttu-id="f79bb-109">Haga clic en un parámetro y use los botones de flecha arriba y flecha abajo de la barra de herramientas del panel Datos de informe para mover el parámetro hacia arriba o hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="f79bb-109">Click a parameter and use the up and down arrow buttons on the Report Data pane toolbar to move the parameter higher or lower in the list.</span></span> <span data-ttu-id="f79bb-110">La siguiente imagen muestra el panel Datos de informe del Generador del informes.</span><span class="sxs-lookup"><span data-stu-id="f79bb-110">The following image shows the Report Data pane in Report Builder.</span></span>  
  
     <span data-ttu-id="f79bb-111">![panel Datos de informe](../media/reportdatapane.png "panel Datos de informe")</span><span class="sxs-lookup"><span data-stu-id="f79bb-111">![Report Data Pane](../media/reportdatapane.png "Report Data Pane")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f79bb-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f79bb-112">See Also</span></span>  
 <span data-ttu-id="f79bb-113">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="f79bb-113">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="f79bb-114">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="f79bb-114">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="f79bb-115">[Agregar parámetros en cascada a un informe &#40;Generador de informes y SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f79bb-115">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f79bb-116">[Tutorial: agregar un parámetro a un informe &#40;Generador de informes&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="f79bb-116">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="f79bb-117">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="f79bb-117">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="f79bb-118">Usar referencias a la colección de parámetros &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f79bb-118">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
