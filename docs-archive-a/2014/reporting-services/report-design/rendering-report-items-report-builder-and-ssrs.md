---
title: Representar elementos de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 99ebb4dc-41cc-42ac-82dd-a2b0e31155a0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4e0b1dabee096cfbaab53227926633f8d7a3697
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672725"
---
# <a name="rendering-report-items-report-builder-and-ssrs"></a><span data-ttu-id="b784b-102">Representar elementos de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="b784b-102">Rendering Report Items (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b784b-103">El número, tamaño y ubicación de los elementos de informe afectan a la manera en que los representadores paginan el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="b784b-103">The number, size, and location of report items affect how the renderers paginate the report body.</span></span> <span data-ttu-id="b784b-104">A continuación se incluye una descripción de cómo se representan los distintos elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="b784b-104">Below is a description of how various report items are rendered.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="overlapping-report-items"></a><span data-ttu-id="b784b-105">Elementos de informe superpuestos</span><span class="sxs-lookup"><span data-stu-id="b784b-105">Overlapping Report Items</span></span>  
 <span data-ttu-id="b784b-106">Los elementos de informe superpuestos no se admiten en HTML, MHTML, Word, Excel, la vista previa ni el Visor de informes.</span><span class="sxs-lookup"><span data-stu-id="b784b-106">Overlapping report items are not supported in HTML, MHTML, Word, Excel, in Preview, or the Report Viewer.</span></span> <span data-ttu-id="b784b-107">Si existe algún elemento superpuesto, se mueve.</span><span class="sxs-lookup"><span data-stu-id="b784b-107">If overlapping items exist, they are moved.</span></span> <span data-ttu-id="b784b-108">A los elementos de informe se les aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b784b-108">The following rules are applied to overlapping report items:</span></span>  
  
-   <span data-ttu-id="b784b-109">Si es mayor la superposición vertical de los elementos de informe, uno de los elementos superpuestos se desplaza a la derecha.</span><span class="sxs-lookup"><span data-stu-id="b784b-109">If the vertical overlap of report items is greater, one of the overlapping items is moved to the right.</span></span> <span data-ttu-id="b784b-110">El elemento situado más a la izquierda permanece en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b784b-110">The left-most item remains where it is positioned.</span></span>  
  
-   <span data-ttu-id="b784b-111">Si es mayor la superposición horizontal de los elementos de informe, uno de los elementos se desplaza hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="b784b-111">If the horizontal overlap of report items is greater, one of the overlapping items is moved down.</span></span> <span data-ttu-id="b784b-112">El elemento situado más arriba permanece en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b784b-112">The top-most item remains where it is positioned.</span></span>  
  
-   <span data-ttu-id="b784b-113">Si la superposición vertical y la horizontal son iguales, uno de los elementos superpuestos se desplaza a la derecha.</span><span class="sxs-lookup"><span data-stu-id="b784b-113">If the vertical and horizontal overlap is equal, one of the overlapping items is moved to the right.</span></span> <span data-ttu-id="b784b-114">El elemento situado más a la izquierda permanece en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b784b-114">The left-most item remains where it is positioned.</span></span>  
  
-   <span data-ttu-id="b784b-115">Si se debe mover un elemento para corregir la superposición, los elementos de informe adyacentes se desplazan hacia abajo y/o a la derecha para conservar una cantidad mínima de espacio entre el elemento y los elementos de informe que finalizan sobre él y/o a su izquierda.</span><span class="sxs-lookup"><span data-stu-id="b784b-115">If an item must be moved to correct overlapping, adjacent report items move down and/or to the right to maintain a minimum amount of spacing between the item and the report items that end above it and/or to the left of it.</span></span> <span data-ttu-id="b784b-116">Por ejemplo, imagine que dos elementos de informe se superponen verticalmente y que un tercero está situado a 2 pulgadas a su derecha.</span><span class="sxs-lookup"><span data-stu-id="b784b-116">For example, suppose two report items overlap vertically and a third report item is 2 inches to the right of them.</span></span> <span data-ttu-id="b784b-117">Cuando el elemento de informe superpuesto se mueve hacia la derecha, el tercero se desplaza también hacia la derecha para conservar las 2 pulgadas existentes entre él y el elemento de informe de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="b784b-117">When the overlapping report item is moved to the right, the third report item moves to the right as well in order to maintain the 2 inches between itself and the report item to its left.</span></span>  
  
 <span data-ttu-id="b784b-118">Los elementos de informe superpuestos son compatibles con los formatos de saltos de página duros, incluyendo la impresión.</span><span class="sxs-lookup"><span data-stu-id="b784b-118">Overlapping report items are supported in hard page-break formats, including print.</span></span>  
  
## <a name="visibility-and-report-items"></a><span data-ttu-id="b784b-119">Visibilidad y elementos de informe</span><span class="sxs-lookup"><span data-stu-id="b784b-119">Visibility and Report Items</span></span>  
 <span data-ttu-id="b784b-120">Los elementos de informe se pueden ocultar o mostrar de forma predeterminada, o de forma condicional mediante expresiones.</span><span class="sxs-lookup"><span data-stu-id="b784b-120">Report items can be hidden or displayed by default, or hidden or displayed conditionally using expressions.</span></span> <span data-ttu-id="b784b-121">Opcionalmente, la visibilidad se puede cambiar haciendo clic en otro elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="b784b-121">Optionally, the visibility can be switched by clicking another report item.</span></span>  
  
 <span data-ttu-id="b784b-122">Se aplican las reglas de visibilidad siguientes al representar elementos de informe:</span><span class="sxs-lookup"><span data-stu-id="b784b-122">The following visibility rules apply when rendering report items:</span></span>  
  
-   <span data-ttu-id="b784b-123">Si un elemento de informe y su contenido están siempre ocultos (no se ocultan en función de una expresión o no se puede cambiar su visibilidad haciendo clic en otro elemento de informe), los elementos de informe situados a su derecha o por debajo no se mueven para rellenar el espacio vacío.</span><span class="sxs-lookup"><span data-stu-id="b784b-123">If a report item and its contents are always hidden (it is not hidden based on an expression or its visibility cannot be switched by clicking another report item), then other report items to the right or below it do not move to fill the empty space.</span></span> <span data-ttu-id="b784b-124">Por ejemplo, si un rectángulo y la imagen que contiene están ocultos, el elemento de informe que comienza a la derecha del rectángulo no se mueve a la izquierda para rellenar lo que parece espacio vacío.</span><span class="sxs-lookup"><span data-stu-id="b784b-124">For example, if a rectangle and the image contained within it are hidden, the report item that starts to the right of the rectangle does not move to the left to fill what appears to be empty space.</span></span> <span data-ttu-id="b784b-125">Se conserva el espacio ocupado por el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="b784b-125">The space occupied by the rectangle is preserved.</span></span>  
  
-   <span data-ttu-id="b784b-126">Si un elemento de informe y su contenido se ocultan condicionalmente (se ocultan en función de una expresión o su visibilidad se puede cambiar haciendo clic en otro elemento de informe), los elementos de informe situados a su derecha o por debajo se mueven a la izquierda para rellenar el espacio cuando se oculta el elemento.</span><span class="sxs-lookup"><span data-stu-id="b784b-126">If a report item and its contents are hidden conditionally (it is hidden based on an expression or its visibility is switched by clicking another report item), then report items to the right or below it move to the left to fill in the space when the item is hidden.</span></span>  
  
-   <span data-ttu-id="b784b-127">Si la visibilidad de un elemento de informe y su contenido se puede cambiar haciendo clic en otro elemento de informe, la paginación cambia para adaptarse al elemento de informe y su contenido solo cuando se muestra inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b784b-127">If the visibility of a report item and its contents can be switched by clicking another report item, then pagination changes to accommodate the report item and its contents only when it is initially displayed.</span></span>  
  
## <a name="keeping-report-items-together-on-a-single-page"></a><span data-ttu-id="b784b-128">Mantener unidos los elementos de informe en una sola página</span><span class="sxs-lookup"><span data-stu-id="b784b-128">Keeping Report Items Together on a Single Page</span></span>  
 <span data-ttu-id="b784b-129">Muchos de los elementos de informe incluidos en un informe se pueden conservar unidos en una sola página de forma implícita o explícita estableciendo las propiedades KeepWithGroup o KeepTogether.</span><span class="sxs-lookup"><span data-stu-id="b784b-129">Many report items within a report can be kept together on a single page implicitly or explicitly by setting the keep with group or keep together properties.</span></span> <span data-ttu-id="b784b-130">Los elementos de informe siempre se representan en la misma página si el elemento de informe no tiene ningún salto de página lógico y es más pequeño que el área de página utilizable.</span><span class="sxs-lookup"><span data-stu-id="b784b-130">Report items are always rendered on the same page if the report item does not have any logical page breaks and is smaller in size than the usable page area.</span></span> <span data-ttu-id="b784b-131">Si un elemento de informe no cabe por completo en la página en la que normalmente se iniciaría, se inserta un salto de página duro antes de dicho elemento, forzando a que se muestre en la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="b784b-131">If a report item does not fit completely on the page on which it would usually start, a hard page break is inserted before the report item, forcing it to the next page.</span></span> <span data-ttu-id="b784b-132">En los representadores de salto de página automático, la página aumenta de tamaño para dar cabida al elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="b784b-132">For soft page-break renderers, the page grows to accommodate the report item.</span></span>  
  
 <span data-ttu-id="b784b-133">Si el elemento de informe está oculto siempre, las reglas para mantener unidos los elementos se omiten.</span><span class="sxs-lookup"><span data-stu-id="b784b-133">When the report item is always hidden, the rules for keeping items together are ignored.</span></span>  
  
 <span data-ttu-id="b784b-134">Los siguientes elementos se mantienen siempre unidos:</span><span class="sxs-lookup"><span data-stu-id="b784b-134">The following items are always kept together:</span></span>  
  
-   <span data-ttu-id="b784b-135">Imágenes.</span><span class="sxs-lookup"><span data-stu-id="b784b-135">Images.</span></span>  
  
-   <span data-ttu-id="b784b-136">Líneas.</span><span class="sxs-lookup"><span data-stu-id="b784b-136">Lines.</span></span>  
  
-   <span data-ttu-id="b784b-137">Gráficos, medidores y mapas.</span><span class="sxs-lookup"><span data-stu-id="b784b-137">Charts, gauges, and maps.</span></span>  
  
-   <span data-ttu-id="b784b-138">Una fila única en una región de datos que aparece de forma separada en otra página, seleccionando la opción KeepWithGroup.</span><span class="sxs-lookup"><span data-stu-id="b784b-138">A single row in a data region that appears separately on another page, by selecting the keep with group option.</span></span> <span data-ttu-id="b784b-139">Esto mantendrá unida de forma implícita la fila única con al menos una instancia del grupo para que la fila no quede huérfana.</span><span class="sxs-lookup"><span data-stu-id="b784b-139">This will implicitly keep together the single row with at least one instance of the group so that the row is not orphaned.</span></span> <span data-ttu-id="b784b-140">Puede establecer esta opción en una región de datos o un grupo.</span><span class="sxs-lookup"><span data-stu-id="b784b-140">You can set this option on a data region or a group.</span></span>  
  
-   <span data-ttu-id="b784b-141">Área de encabezado de una región de datos.</span><span class="sxs-lookup"><span data-stu-id="b784b-141">Header area of a data region.</span></span>  
  
-   <span data-ttu-id="b784b-142">Área de encabezado de una región de datos y la primera fila de datos.</span><span class="sxs-lookup"><span data-stu-id="b784b-142">Header area of a data region and the first row of data.</span></span>  
  
-   <span data-ttu-id="b784b-143">Elementos de informe que se pueden activar o desactivar en una región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="b784b-143">Report items that can be toggled in a tablix data region.</span></span>  
  
### <a name="priority-order"></a><span data-ttu-id="b784b-144">Orden de prioridad</span><span class="sxs-lookup"><span data-stu-id="b784b-144">Priority Order</span></span>  
 <span data-ttu-id="b784b-145">Debido a las limitaciones de tamaño de la página, pueden surgir conflictos entre las reglas para mantener unidos los elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="b784b-145">Due to page size limitations, conflicts can arise between the rules for keeping report items together.</span></span> <span data-ttu-id="b784b-146">En este caso, se usa el orden de prioridad siguiente para mantener unidos los elementos al efectuar la representación:</span><span class="sxs-lookup"><span data-stu-id="b784b-146">When conflicts occur, the following priority order is used to keep items together when rendering:</span></span>  
  
-   <span data-ttu-id="b784b-147">Líneas, gráficos e imágenes.</span><span class="sxs-lookup"><span data-stu-id="b784b-147">Lines, charts, and images.</span></span>  
  
-   <span data-ttu-id="b784b-148">Control de líneas viudas y huérfanas.</span><span class="sxs-lookup"><span data-stu-id="b784b-148">Widow and orphan control.</span></span>  
  
-   <span data-ttu-id="b784b-149">Encabezados de columna y encabezados de fila repetidos.</span><span class="sxs-lookup"><span data-stu-id="b784b-149">Repeated column headers and row headers.</span></span>  
  
     <span data-ttu-id="b784b-150">Los encabezados tienen prioridad sobre los pies de página.</span><span class="sxs-lookup"><span data-stu-id="b784b-150">Headers take precedence over footers.</span></span> <span data-ttu-id="b784b-151">Los grupos repetidos internos tienen prioridad sobre los grupos externos.</span><span class="sxs-lookup"><span data-stu-id="b784b-151">Inner repeated groups have priority over outer groups.</span></span> <span data-ttu-id="b784b-152">Los elementos en los que se establece la propiedad `RepeatWith` y que están más cerca de la región de datos de destino tienen prioridad sobre los elementos situados más lejos de dicha región.</span><span class="sxs-lookup"><span data-stu-id="b784b-152">Items where the `RepeatWith` property is set that are closer to the target data region have priority over items that are farther away from the data region.</span></span>  
  
-   <span data-ttu-id="b784b-153">Elementos de informe pequeños, como cuadros de texto o rectángulos, con una propiedad KeepTogether explícita establecida en `true` .</span><span class="sxs-lookup"><span data-stu-id="b784b-153">Small report items, such as text boxes or rectangles, with an explicit KeepTogether property set to `true`.</span></span>  
  
-   <span data-ttu-id="b784b-154">Elementos de informe de gran tamaño, como subinformes o un miembro de Tablix no interno, con una propiedad KeepTogether explícita establecida en `true` .</span><span class="sxs-lookup"><span data-stu-id="b784b-154">Large report items, such as subreports or a non-innermost tablix member, with an explicit KeepTogether property set to `true`.</span></span>  
  
-   <span data-ttu-id="b784b-155">Las regiones de datos Tablix con una propiedad KeepTogether explícita establecida en `true` .</span><span class="sxs-lookup"><span data-stu-id="b784b-155">Tablix data regions with an explicit KeepTogether property set to `true`.</span></span>  
  
### <a name="subreports"></a><span data-ttu-id="b784b-156">Subinformes</span><span class="sxs-lookup"><span data-stu-id="b784b-156">Subreports</span></span>  
 <span data-ttu-id="b784b-157">Un subinforme se representa como un rectángulo que contiene otro informe definido en un archivo de informe .rdl independiente.</span><span class="sxs-lookup"><span data-stu-id="b784b-157">A subreport renders as a rectangle that contains another report that is defined in a separate report .rdl file.</span></span> <span data-ttu-id="b784b-158">El archivo de subinforme se debe publicar en un servidor de informes para que el informe primario pueda tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="b784b-158">The subreport file must be published to a report server before it can be accessed by the parent report.</span></span>  
  
 <span data-ttu-id="b784b-159">Se aplican las reglas siguientes al representar los subinformes:</span><span class="sxs-lookup"><span data-stu-id="b784b-159">The following rules apply when rendering subreports:</span></span>  
  
-   <span data-ttu-id="b784b-160">Los subinformes pueden crecer hasta tener el tamaño del cuerpo especificado en el archivo .rdl que define el subinforme.</span><span class="sxs-lookup"><span data-stu-id="b784b-160">Subreports can grow to the size of the body defined in the .rdl file that defines the subreport.</span></span> <span data-ttu-id="b784b-161">Por ejemplo, si el archivo RDL para el subinforme establece que el cuerpo del subinforme tiene 5 pulgadas de ancho, el subinforme tendrá 5 pulgadas de ancho dentro del informe primario.</span><span class="sxs-lookup"><span data-stu-id="b784b-161">For example, if the RDL for the subreport states that the subreport body is 5 inches wide, then the subreport will be 5 inches wide within the parent report.</span></span>  
  
-   <span data-ttu-id="b784b-162">Los subinformes heredan la configuración de las columnas del informe primario.</span><span class="sxs-lookup"><span data-stu-id="b784b-162">Subreports inherit column settings from the parent report.</span></span> <span data-ttu-id="b784b-163">Las configuraciones de columnas definidas en el archivo RDL original siempre se omiten.</span><span class="sxs-lookup"><span data-stu-id="b784b-163">Column settings that are defined in the original RDL are always ignored.</span></span>  
  
-   <span data-ttu-id="b784b-164">Solo se representa el cuerpo del subinforme.</span><span class="sxs-lookup"><span data-stu-id="b784b-164">Only the body of the subreport is rendered.</span></span> <span data-ttu-id="b784b-165">Las secciones de encabezado y de pie de página definidas en el archivo .rdl del subinforme no se representan cuando el subinforme se representa en el informe primario.</span><span class="sxs-lookup"><span data-stu-id="b784b-165">Header and footer sections that are defined in the subreport's .rdl file are not rendered when the subreport is rendered in the parent report.</span></span>  
  
-   <span data-ttu-id="b784b-166">Los subinformes tienen una propiedad KeepTogether explícita.</span><span class="sxs-lookup"><span data-stu-id="b784b-166">Subreports have an explicit KeepTogether property.</span></span> <span data-ttu-id="b784b-167">Cuando dicha propiedad se establece en `true`, todos los elementos del subinforme se mantendrán unidos en una página siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="b784b-167">When it is set to `true`, all the items in the subreport are kept together on one page when possible.</span></span>  
  
-   <span data-ttu-id="b784b-168">Si un subinforme no se puede ejecutar, se muestra en el informe como un cuadro de texto con un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b784b-168">If a subreport cannot run, it is displayed in the report as a text box with an error message.</span></span> <span data-ttu-id="b784b-169">Las propiedades de estilo aplicadas al subinforme se aplican en su lugar al cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="b784b-169">The style properties applied to the subreport are applied to the text box instead.</span></span>  
  
-   <span data-ttu-id="b784b-170">Si un salto de página divide el subinforme, el parámetro **Omitir borde en el salto de página** controla si los bordes del subinforme están cerrados o abiertos.</span><span class="sxs-lookup"><span data-stu-id="b784b-170">If the subreport is split by a page break, the **Omit border on page break** setting controls whether or not the borders on the subreport are closed or open.</span></span>  
  
 <span data-ttu-id="b784b-171">Para más información sobre los subinformes, vea [Subinformes &#40;Generador de informes y SSRS&#41;](subreports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b784b-171">For more information about subreports, see [Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b784b-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b784b-172">See Also</span></span>  
 <span data-ttu-id="b784b-173">[Paginación en Reporting Services &#40;Generador de informes y SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b784b-173">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b784b-174">[Comportamientos de la representación &#40;Generador de informes y SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b784b-174">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b784b-175">[Funcionalidad interactiva para diferentes extensiones de representación de informes &#40;Generador de informes y SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b784b-175">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 [<span data-ttu-id="b784b-176">Listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b784b-176">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  