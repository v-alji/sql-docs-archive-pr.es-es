---
title: Controlar saltos de página, encabezados, columnas y filas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b8fa41f-a727-4f23-8efb-fd9bb0d4cd1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7dae06129ee5dc9962538e8d025dca9966325f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675204"
---
# <a name="controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs"></a><span data-ttu-id="ed5b3-102">Controlar saltos de página, encabezados, columnas y filas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="ed5b3-102">Controlling Page Breaks, Headings, Columns, and Rows (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ed5b3-103">Un salto de página divide un informe en páginas independientes que se pueden ver e imprimir.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-103">A page break divides a report into separate pages for viewing and printing.</span></span> <span data-ttu-id="ed5b3-104">Los saltos de página determinan cómo se ajusta el contenido a una página del informe para su vista óptima al ofrecer una vista previa de un informe o exportarlo a un formato de archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-104">Page breaks determine how the content is fitted to a report page for optimal viewing when you preview a report or export it to a different file format.</span></span>  
  
 <span data-ttu-id="ed5b3-105">Al agregar los saltos de página, también se mejora el rendimiento de los informes grandes durante su procesado.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-105">Adding page breaks also improves the performance of large reports when the are processed.</span></span> <span data-ttu-id="ed5b3-106">Se muestra una página representada, mientras el resto de las páginas se representan en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-106">A rendered page is displayed while the rest of the pages are rendered in the background.</span></span> <span data-ttu-id="ed5b3-107">Esto permite empezar a ver las páginas iniciales del informe mientras se espera a que estén disponibles las otras páginas.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-107">This allows you to begin viewing the initial pages of the report while waiting for additional pages to become available.</span></span>  
  
 <span data-ttu-id="ed5b3-108">Los saltos de página se pueden agregar a los elementos de informe, como una tabla, matriz, lista, gráfico, medidor o imagen.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-108">Page breaks can be added to report items such as a table, matrix, list, chart, gauge, or image.</span></span> <span data-ttu-id="ed5b3-109">También puede agregar saltos de página a los grupos de una tabla, matriz o lista.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-109">You can also add page breaks to groups in a table, matrix, or list.</span></span> <span data-ttu-id="ed5b3-110">Los saltos de página se pueden agregar antes de los grupos, después o entre ellos.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-110">Page breaks can be added before, after, and between groups.</span></span> <span data-ttu-id="ed5b3-111">Los saltos de página entre grupos no se agregan al informe de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ed5b3-111">Page breaks between groups are not added to the report by default.</span></span>  
  
 <span data-ttu-id="ed5b3-112">Para más información, vea [Mostrar encabezados de fila y de columna en varias páginas &#40;Generador de informes y SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) y [Mantener visibles los encabezados al desplazarse a través de un informe &#40;Generador de informes y SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ed5b3-112">For more information, see [Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) and [Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed5b3-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed5b3-113">See Also</span></span>  
 <span data-ttu-id="ed5b3-114">[Enumera &#40;Generador de informes y SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ed5b3-114">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ed5b3-115">[Controlar la presentación de la región de datos Tablix en una página de informe &#40;Generador de informes y SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span><span class="sxs-lookup"><span data-stu-id="ed5b3-115">[Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span></span>  
 <span data-ttu-id="ed5b3-116">[Panel de agrupación &#40;Generador de informes&#41;](grouping-pane-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ed5b3-116">[Grouping Pane &#40;Report Builder&#41;](grouping-pane-report-builder.md) </span></span>  
 [<span data-ttu-id="ed5b3-117">Mostrar encabezados y pies de página con un grupo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ed5b3-117">Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;</span></span>](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md)  
  
  
