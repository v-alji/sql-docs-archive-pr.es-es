---
title: Imágenes, cuadros de texto, rectángulos y líneas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aa7ad08f-dd49-401e-9619-522e27055bb9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fb9a47bb3b8d68d48be42f8f0a2adddfc3ba130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745048"
---
# <a name="images-text-boxes-rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="9b24d-102">Imágenes, cuadros de texto rectángulos y líneas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="9b24d-102">Images, Text Boxes, Rectangles, and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9b24d-103">Además de regiones de datos como tablas, matrices y gráficos, los informes usan otros elementos de informe, como imágenes, cuadros de texto y rectángulos, para agregar interés visual, resaltar información clave o proporcionar información relacionada.</span><span class="sxs-lookup"><span data-stu-id="9b24d-103">In addition to data regions like tables, matrices, and charts, reports use other report items like images, text boxes, and rectangles to add visual interest, highlight key information, or provide related information.</span></span> <span data-ttu-id="9b24d-104">Puede cambiar el formato de un elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="9b24d-104">You can change the formatting of a report item.</span></span> <span data-ttu-id="9b24d-105">Por ejemplo, puede agregar un borde o un relleno, cambiar la visibilidad o la dirección inicial, o especificar una ubicación y un tamaño determinados para el elemento.</span><span class="sxs-lookup"><span data-stu-id="9b24d-105">For example, you can add a border or padding, change the initial visibility or direction, or specify an exact size and location for the item.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="9b24d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9b24d-106">In This Section</span></span>  
 [<span data-ttu-id="9b24d-107">Cuadros de texto &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b24d-107">Text Boxes &#40;Report Builder and SSRS&#41;</span></span>](text-boxes-report-builder-and-ssrs.md)  
 <span data-ttu-id="9b24d-108">Los cuadros de texto se pueden mostrar en cualquier lugar de un informe y pueden contener etiquetas, campos o datos calculados.</span><span class="sxs-lookup"><span data-stu-id="9b24d-108">Text boxes can be placed anywhere on a report and can contain labels, fields, or calculated data.</span></span> <span data-ttu-id="9b24d-109">Use expresiones para definir el valor que desea mostrar en un cuadro de texto cuando vea un informe.</span><span class="sxs-lookup"><span data-stu-id="9b24d-109">You use expressions to define the value to display in a text box when you view a report.</span></span>  
  
 <span data-ttu-id="9b24d-110">Todas las celdas de una tabla o matriz son también un cuadro de texto, al que se puede dar formato de la misma manera que a los cuadros de texto independientes de un informe.</span><span class="sxs-lookup"><span data-stu-id="9b24d-110">Every cell in a table or matrix is also a text box, which you can format in the same way that you format stand-alone text boxes.</span></span>  
  
 [<span data-ttu-id="9b24d-111">Rectángulos y líneas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b24d-111">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
 <span data-ttu-id="9b24d-112">Las**líneas** se muestran horizontal, vertical o diagonalmente.</span><span class="sxs-lookup"><span data-stu-id="9b24d-112">**Lines** display horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="9b24d-113">Una línea se define mediante un punto inicial y un punto final, y puede tener asignados varios estilos (por ejemplo, espesor y color).</span><span class="sxs-lookup"><span data-stu-id="9b24d-113">A line is defined with a start and end point and can have various styles (for example, weight and color) assigned to it.</span></span> <span data-ttu-id="9b24d-114">Una línea no tiene datos asociados.</span><span class="sxs-lookup"><span data-stu-id="9b24d-114">A line has no data associated with it.</span></span>  
  
 <span data-ttu-id="9b24d-115">Los**Rectángulos** se pueden usar como elementos gráficos o como contenedores para otros elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="9b24d-115">**Rectangles** can be used as a graphical element, or as a container for other report items.</span></span> <span data-ttu-id="9b24d-116">Como elemento gráfico, un rectángulo tiene las mismas propiedades que una línea.</span><span class="sxs-lookup"><span data-stu-id="9b24d-116">As a graphical element, a rectangle has the same properties as a line.</span></span> <span data-ttu-id="9b24d-117">Como contenedor, un rectángulo actúa como contenedor primario para todos los elementos de informe que se encuentran dentro de él.</span><span class="sxs-lookup"><span data-stu-id="9b24d-117">As a container, a rectangle acts as a parent container for all report items inside it.</span></span> <span data-ttu-id="9b24d-118">Situar los elementos de informe en un contenedor primario ayuda a controlar el modo en que dichos elementos aparecen en cada página del informe.</span><span class="sxs-lookup"><span data-stu-id="9b24d-118">Placing report items in a parent container helps control how they appear on each report page.</span></span>  
  
 [<span data-ttu-id="9b24d-119">Imágenes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b24d-119">Images &#40;Report Builder and SSRS&#41;</span></span>](images-report-builder-and-ssrs.md)  
 <span data-ttu-id="9b24d-120">Las imágenes muestran los datos de imagen binarios de un informe.</span><span class="sxs-lookup"><span data-stu-id="9b24d-120">Images display binary image data in a report.</span></span> <span data-ttu-id="9b24d-121">Debe proporcionar el origen para la imagen.</span><span class="sxs-lookup"><span data-stu-id="9b24d-121">You provide the source for the image.</span></span> <span data-ttu-id="9b24d-122">El origen puede ser una referencia de URL a una imagen almacenada en un servidor web, una referencia a datos de imagen incrustados o una referencia a datos de imagen binarios de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="9b24d-122">The source can be a URL reference to an image stored on a Web server, a reference to embedded image data, or a reference to binary image data in a database.</span></span> <span data-ttu-id="9b24d-123">El Generador de informes y el Diseñador de informes admiten archivos .bmp, .jpeg, .gif y .png.</span><span class="sxs-lookup"><span data-stu-id="9b24d-123">Report Builder and Report Designer support .bmp, .jpeg, .gif, and .png files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b24d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b24d-124">See Also</span></span>  
 [<span data-ttu-id="9b24d-125">Aplicar formato a los elementos de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b24d-125">Formatting Report Items &#40;Report Builder and SSRS&#41;</span></span>](formatting-report-items-report-builder-and-ssrs.md)  
  
  
