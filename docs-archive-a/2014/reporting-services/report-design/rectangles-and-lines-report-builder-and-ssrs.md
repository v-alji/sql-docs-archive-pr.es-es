---
title: Rectángulos y líneas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d6226b0c-0398-4185-8565-96099876fc21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 96b795c3edeabb938e836be3486e28e08737a8e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676345"
---
# <a name="rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="fd8fd-102">Rectángulos y líneas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="fd8fd-102">Rectangles and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fd8fd-103">Los rectángulos y las líneas pueden crear efectos visuales en un informe.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-103">Rectangles and lines can create visual effects within a report.</span></span> <span data-ttu-id="fd8fd-104">Puede configurar las propiedades de presentación de estos elementos de informe desde la sección Borde de la pestaña Inicio, así como configurar otras propiedades utilizando el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-104">You can set display properties on these report items from the Border section of the Home tab, and set other properties by using the Properties pane.</span></span> <span data-ttu-id="fd8fd-105">Puede agregar a un rectángulo características como un color o una imagen de fondo, una información sobre herramientas o un marcador.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-105">You can add features like a background color or image, a tooltip, or a bookmark to a rectangle.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="rectangles-and-lines-as-report-parts"></a><a name="RectanglesLinesReportParts"></a> <span data-ttu-id="fd8fd-106">Rectángulos y líneas como elementos de informe</span><span class="sxs-lookup"><span data-stu-id="fd8fd-106">Rectangles and Lines as Report Parts</span></span>  
 <span data-ttu-id="fd8fd-107">Puede publicar rectángulos con los elementos que contienen por separado del informe como elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-107">You can publish rectangles with the items that they contain separately from the report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="fd8fd-108">No puede publicar los elementos de informe contenidos en el rectángulo como elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-108">You cannot publish the report items within the rectangle as report parts.</span></span> <span data-ttu-id="fd8fd-109">Cuando los usuarios agregan el rectángulo a un informe, obtienen el rectángulo y los elementos que contiene.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-109">When people add the rectangle to a report, they get the rectangle and the items it contains.</span></span>  
  

  
##  <a name="using-a-rectangle-as-a-container"></a><a name="RectangleAsContainer"></a><span data-ttu-id="fd8fd-110">Usar un rectángulo como contenedor</span><span class="sxs-lookup"><span data-stu-id="fd8fd-110">Using a Rectangle as a Container</span></span>  
 <span data-ttu-id="fd8fd-111">Puede usar un rectángulo como contenedor de otros elementos.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-111">You can use a rectangle as a container for other items.</span></span> <span data-ttu-id="fd8fd-112">Cuando se mueve un rectángulo, los elementos que contiene se mueven con él.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-112">When you move the rectangle, the items that are contained within the rectangle move along with it.</span></span> <span data-ttu-id="fd8fd-113">Un elemento del rectángulo muestra el nombre del rectángulo en su propiedad **Parent** .</span><span class="sxs-lookup"><span data-stu-id="fd8fd-113">An item within the rectangle shows the name of the rectangle in its **Parent** property.</span></span> <span data-ttu-id="fd8fd-114">Para más información sobre el uso de un rectángulo como contenedor, vea [Agregar un rectángulo o un contenedor &#40;Generador de informes y SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) y [Mostrar los mismos datos en una matriz y en un gráfico &#40;Generador de informes&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="fd8fd-114">For more information about using a rectangle as a container, see [Add a Rectangle or Container &#40;Report Builder and SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd8fd-115">Un rectángulo es solamente un contenedor para los elementos que crea en el rectángulo o que arrastra hasta él.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="fd8fd-116">Si dibuja un rectángulo alrededor de un elemento que ya existe en la superficie de diseño, el rectángulo no actuará como su contenedor.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span> <span data-ttu-id="fd8fd-117">El rectángulo no aparecerá enumerado en la propiedad Parent del elemento.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-117">The rectangle will not be listed in the item's Parent property.</span></span>  
  
 <span data-ttu-id="fd8fd-118">Cuando utilice rectángulos para contener elementos de informe, valore cómo se verán afectados los elementos en conjunto durante la representación de un informe.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-118">When using rectangles to contain report items, consider how the items will be affected as a whole during report rendering.</span></span> <span data-ttu-id="fd8fd-119">Los elementos de informe que contienen filas de datos repetidas (por ejemplo, tablas) se expandirán para alojar los datos devueltos por una consulta. Esto afectará a la ubicación de otros elementos dentro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-119">Report items that contain repeated rows of data (for example, tables) will expand to accommodate the data that is returned by a query, and this affects the positioning of other items in the rectangle.</span></span> <span data-ttu-id="fd8fd-120">Una tabla desplazará los elementos hacia abajo si están ubicados debajo de la región de datos.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-120">A table will push items down if they are positioned below the data region.</span></span> <span data-ttu-id="fd8fd-121">Para fijarlos en su sitio, se puede incluir el elemento de informe en un rectángulo cuyo borde superior esté por encima del borde inferior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-121">To anchor an item in place, you can place the report item inside of a rectangle that has an upper edge above the lower edge of the table.</span></span> <span data-ttu-id="fd8fd-122">Para más información, vea [Comportamientos de la representación &#40;Generador de informes y SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fd8fd-122">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="adding-a-report-border"></a><a name="ReportBorder"></a> <span data-ttu-id="fd8fd-123">Agregar un borde al informe</span><span class="sxs-lookup"><span data-stu-id="fd8fd-123">Adding a Report Border</span></span>  
 <span data-ttu-id="fd8fd-124">Puede agregar un borde a un informe agregando bordes a los encabezados, pies de página y cuerpo del informe, sin tener que agregar líneas o rectángulos.</span><span class="sxs-lookup"><span data-stu-id="fd8fd-124">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span> <span data-ttu-id="fd8fd-125">Para más información, vea [Agregar un borde a un informe &#40;Generador de informes y SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fd8fd-125">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="fd8fd-126">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="fd8fd-126">How-To Topics</span></span>  
 [<span data-ttu-id="fd8fd-127">Agregar un borde a un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fd8fd-127">Add a Border to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-to-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="fd8fd-128">Agregar un rectángulo o un contenedor &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fd8fd-128">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="fd8fd-129">Agregar y modificar una línea &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fd8fd-129">Add and Modify a Line &#40;Report Builder and SSRS&#41;</span></span>](add-and-modify-a-line-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd8fd-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd8fd-130">See Also</span></span>  
 [<span data-ttu-id="fd8fd-131">Agregar un rectángulo o un contenedor &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fd8fd-131">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
  
