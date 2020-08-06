---
title: Agregar un salto de página (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3846cd48-2787-47e9-b13b-7fc45a205f68
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55d6be3ae47827c5a8ff4a5b36e3ff2ce80e1034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662561"
---
# <a name="add-a-page-break-report-builder-and-ssrs"></a><span data-ttu-id="c2d3c-102">Agregar un salto de página (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="c2d3c-102">Add a Page Break (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c2d3c-103">Puede agregar un salto de página a los rectángulos, las regiones de datos o los grupos situados dentro de las regiones de datos para controlar la cantidad de información de cada página.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-103">You can add a page break to rectangles, data regions, or groups within data regions to control the amount of information on each page.</span></span> <span data-ttu-id="c2d3c-104">El hecho de agregar saltos de página puede mejorar el rendimiento de los informes publicados porque solo es necesario procesar los elementos de cada página para ver el informe.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-104">Adding page breaks can improve the performance of published reports because only the items on each page have to be processed as you view the report.</span></span> <span data-ttu-id="c2d3c-105">Cuando el informe entero está en una sola página, se deben procesar todos los elementos antes de poder verlo.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-105">When the whole report is a single page, all items must be processed before you can view the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-break-to-a-data-region"></a><span data-ttu-id="c2d3c-106">Para agregar un salto de página a una región de datos</span><span class="sxs-lookup"><span data-stu-id="c2d3c-106">To add a page break to a data region</span></span>  
  
1.  <span data-ttu-id="c2d3c-107">En la superficie de diseño, haga clic con el botón derecho en el controlador de tabla de la región de datos y luego haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-107">On the design surface, right-click the corner handle of the data region and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="c2d3c-108">En la pestaña **General** , en **Opciones de salto de página**, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2d3c-108">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="c2d3c-109">**Agregar un salto de página antes**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-109">**Add a page break before**.</span></span> <span data-ttu-id="c2d3c-110">Seleccione esta opción cuando desee agregar un salto de página antes de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-110">Select this option when you want to add a page break before the table.</span></span>  
  
    -   <span data-ttu-id="c2d3c-111">**Agregar un salto de página después**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-111">**Add a page break after**.</span></span> <span data-ttu-id="c2d3c-112">Seleccione esta opción cuando desee agregar un salto de página después de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-112">Select this option when you want to add a page break after the table.</span></span>  
  
    -   <span data-ttu-id="c2d3c-113">**Ajustar la tabla a una sola página si es posible**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-113">**Fit table on one page if possible**.</span></span> <span data-ttu-id="c2d3c-114">Seleccione esta opción cuando desee que los datos permanezcan en una página.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-114">Select this option when you want the data to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-rectangle"></a><span data-ttu-id="c2d3c-115">Para agregar un salto de página a un rectángulo</span><span class="sxs-lookup"><span data-stu-id="c2d3c-115">To add a page break to a rectangle</span></span>  
  
1.  <span data-ttu-id="c2d3c-116">En la superficie de diseño, haga clic con el botón derecho en el rectángulo en que quiere agregar un salto de página y, luego, haga clic en **Propiedades del rectángulo**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-116">On the design surface, right-click the rectangle where you want to add a page break, and then click **Rectangle Properties**.</span></span>  
  
2.  <span data-ttu-id="c2d3c-117">En la pestaña **General** , en **Opciones de salto de página**, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2d3c-117">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="c2d3c-118">**Agregar un salto de página antes**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-118">**Add a page break before**.</span></span> <span data-ttu-id="c2d3c-119">Seleccione esta opción cuando desee agregar un salto de página antes del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-119">Select this option when you want to add a page break before the rectangle.</span></span>  
  
    -   <span data-ttu-id="c2d3c-120">**Agregar un salto de página después**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-120">**Add a page break after**.</span></span> <span data-ttu-id="c2d3c-121">Seleccione esta opción cuando desee agregar un salto de página después del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-121">Select this option when you want to add a page break after the rectangle.</span></span>  
  
    -   <span data-ttu-id="c2d3c-122">**Omitir borde en el salto de página**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-122">**Omit border on page break**.</span></span> <span data-ttu-id="c2d3c-123">Seleccione esta opción cuando no desee un borde en el salto de página.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-123">Select this option when you do not want a border on the page break.</span></span>  
  
    -   <span data-ttu-id="c2d3c-124">**Mantener el contenido en una sola página, si es posible**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-124">**Keep contents together on a single page, if possible**.</span></span> <span data-ttu-id="c2d3c-125">Seleccione esta opción si desea que el contenido del rectángulo permanezca en una página.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-125">Select this option when you want contents inside the rectangle to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-row-group-in-a-table-matrix-or-list"></a><span data-ttu-id="c2d3c-126">Para agregar un salto de página a un grupo de filas de una tabla, una matriz o una lista</span><span class="sxs-lookup"><span data-stu-id="c2d3c-126">To add a page break to a row group in a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="c2d3c-127">En el panel Agrupación, haga clic con el botón derecho en un grupo de filas y, luego, haga clic en **Propiedades de grupo**.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-127">In the Grouping pane, right-click a row group, and then click **Group Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c2d3c-128">Los saltos de página se omiten en los grupos de columnas.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-128">Page breaks are ignored on column groups.</span></span>  
  
2.  <span data-ttu-id="c2d3c-129">En la pestaña **Saltos de página** , seleccione **Entre cada instancia de un grupo** para agregar un salto de página entre cada instancia de un grupo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-129">On the **Page Breaks** tab, select **Between each instance of a group** to add a page break between each instance of a group in the table.</span></span>  
  
3.  <span data-ttu-id="c2d3c-130">Opcionalmente, seleccione **También al principio de un grupo** o **También al final de un grupo** para especificar que se agregue un salto de página cuando un grupo se inicie o finalice en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-130">Optionally, select **Also at the start of a group** or **Also at the end of a group** to specify that a page break be added when a group starts or ends in the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d3c-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2d3c-131">See Also</span></span>  
 <span data-ttu-id="c2d3c-132">[Paginación en Reporting Services &#40;Generador de informes y SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2d3c-132">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c2d3c-133">[Comportamientos de la representación &#40;Generador de informes y SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2d3c-133">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c2d3c-134">Encabezados y pies de página &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c2d3c-134">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
