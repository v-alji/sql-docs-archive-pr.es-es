---
title: Cuadro de diálogo Seleccionar color (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.selectcolor.f1
- "10090"
helpviewer_keywords:
- Select Color dialog box
ms.assetid: ac7089a3-5c7b-4f53-8348-180610e86da2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a2526b755fd4e08faf79998d351e824371fac2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749044"
---
# <a name="select-color-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="6fc38-102">Cuadro de diálogo Seleccionar color (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6fc38-102">Select Color Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6fc38-103">Use el cuadro de diálogo **Seleccionar color** para especificar las opciones de color para el fondo de una o varias celdas de una región de datos o un cuadro de texto de un gráfico.</span><span class="sxs-lookup"><span data-stu-id="6fc38-103">Use the **Select Color** dialog box to specify color options for the background of a single cell or multiple cells within a data region or a text box, or for a chart.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6fc38-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="6fc38-104">Options</span></span>  
 <span data-ttu-id="6fc38-105">**Selector de colores**</span><span class="sxs-lookup"><span data-stu-id="6fc38-105">**Color selector**</span></span>  
 <span data-ttu-id="6fc38-106">Elija una de las tres opciones para especificar cómo desea seleccionar los colores:</span><span class="sxs-lookup"><span data-stu-id="6fc38-106">Choose from three options that specify how you want to select colors:</span></span>  
  
-   <span data-ttu-id="6fc38-107">**Selector - Círculo de colores:** elija un color con los valores HSB (matiz/saturación/luminosidad).</span><span class="sxs-lookup"><span data-stu-id="6fc38-107">**Picker - Color circle** Choose a color using Hue/Saturation/Brightness (HSB) color values.</span></span>  
  
-   <span data-ttu-id="6fc38-108">**Selector - Cuadrado de colores:** elija un color con los valores RGB (rojo/verde/azul).</span><span class="sxs-lookup"><span data-stu-id="6fc38-108">**Picker - Color square** Choose a color using Red/Green/Blue (RGB) color values.</span></span>  
  
-   <span data-ttu-id="6fc38-109">**Paleta - Colores estándar:** elija un color de una lista predefinida de valores de color.</span><span class="sxs-lookup"><span data-stu-id="6fc38-109">**Palette - Standard colors** Choose a color from a predefined list of color values.</span></span>  
  
 <span data-ttu-id="6fc38-110">**Círculo de colores**</span><span class="sxs-lookup"><span data-stu-id="6fc38-110">**Color circle**</span></span>  
 <span data-ttu-id="6fc38-111">Se usa para los colores HSB porque los valores HSB se asignan a un sistema de coordenadas cilíndrico.</span><span class="sxs-lookup"><span data-stu-id="6fc38-111">Use for HSB colors because HSB values are mapped onto a cylindrical coordinate system.</span></span> <span data-ttu-id="6fc38-112">El matiz es el color propiamente dicho, la saturación es la pureza del color y la luminosidad es su luminosidad u oscuridad relativa.</span><span class="sxs-lookup"><span data-stu-id="6fc38-112">Hue is the actual color, saturation is purity of color, brightness is relative brightness or darkness.</span></span>  
  
 <span data-ttu-id="6fc38-113">Cuando se elige un color, el centro del círculo determina el color.</span><span class="sxs-lookup"><span data-stu-id="6fc38-113">When you pick a color, the center of the circle determines the color.</span></span> <span data-ttu-id="6fc38-114">Use el control deslizante de color para cambiar el matiz.</span><span class="sxs-lookup"><span data-stu-id="6fc38-114">Use the color slider to change the hue.</span></span> <span data-ttu-id="6fc38-115">Las coordenadas x e y representan los valores de saturación y luminosidad, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6fc38-115">The x and y coordinates represent saturation and brightness values respectively.</span></span>  
  
 <span data-ttu-id="6fc38-116">**Cuadrado de colores**</span><span class="sxs-lookup"><span data-stu-id="6fc38-116">**Color square**</span></span>  
 <span data-ttu-id="6fc38-117">Se usa para los colores RGB porque los valores RGB se asignan a un sistema de coordenadas cartesiano.</span><span class="sxs-lookup"><span data-stu-id="6fc38-117">Use for RGB colors because RGB values are mapped to a Cartesian coordinate system.</span></span> <span data-ttu-id="6fc38-118">R es el valor para el rojo, G es el valor para el verde y B es el valor para el azul.</span><span class="sxs-lookup"><span data-stu-id="6fc38-118">R is the value for Red, G is the value for Green, B is the value for Blue.</span></span>  
  
 <span data-ttu-id="6fc38-119">Cuando se elige un color, el centro del cuadrado determina el color.</span><span class="sxs-lookup"><span data-stu-id="6fc38-119">When you pick a color, the center of the square determines the color.</span></span> <span data-ttu-id="6fc38-120">Use el control deslizante de color para cambiar la gama del color elegido.</span><span class="sxs-lookup"><span data-stu-id="6fc38-120">Use the color slider to change the range of the chosen color.</span></span> <span data-ttu-id="6fc38-121">Las coordenadas x e y representan los otros dos colores.</span><span class="sxs-lookup"><span data-stu-id="6fc38-121">The x and y coordinates represent the other two colors.</span></span> <span data-ttu-id="6fc38-122">Por ejemplo, si elige el color verde, el control deslizante muestra la gama de valores de verde, y las coordenadas x e y representan los valores para el rojo y el azul, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6fc38-122">For example, if you pick green, the slider shows the range of green values, the x and y coordinates represent red and blue values respectively.</span></span>  
  
 <span data-ttu-id="6fc38-123">**Color de la paleta estándar**</span><span class="sxs-lookup"><span data-stu-id="6fc38-123">**Standard palette color**</span></span>  
 <span data-ttu-id="6fc38-124">Se usa para los colores con nombre de la [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumeración.</span><span class="sxs-lookup"><span data-stu-id="6fc38-124">Use for named colors from the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumeration.</span></span>  
  
 <span data-ttu-id="6fc38-125">**Sistema de colores**</span><span class="sxs-lookup"><span data-stu-id="6fc38-125">**Color system**</span></span>  
 <span data-ttu-id="6fc38-126">Especifique si desea colores RGB o HSB.</span><span class="sxs-lookup"><span data-stu-id="6fc38-126">Specify RGB or HSB colors.</span></span> <span data-ttu-id="6fc38-127">Esta opción cambia la presentación para mostrar valores RGB o HSB que se actualizan interactivamente cuando se utiliza un círculo o un cuadrado de colores para el **Selector de colores**.</span><span class="sxs-lookup"><span data-stu-id="6fc38-127">This choice changes the display to show RGB or HSB values, which are updated interactively when you use a color circle or color square for the **Color selector**.</span></span>  
  
 <span data-ttu-id="6fc38-128">El valor **Alpha** se muestra para algunas propiedades cuando un color puede incluir un valor de transparencia.</span><span class="sxs-lookup"><span data-stu-id="6fc38-128">The **Alpha** value displays for some properties when a color can include a transparency value.</span></span> <span data-ttu-id="6fc38-129">Por ejemplo, el relleno para las series del gráfico.</span><span class="sxs-lookup"><span data-stu-id="6fc38-129">For example, Chart series fill.</span></span> <span data-ttu-id="6fc38-130">Para las propiedades que no admiten la transparencia, este valor está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6fc38-130">For properties that do not support transparency, this value is disabled.</span></span>  
  
 <span data-ttu-id="6fc38-131">**Rojo**</span><span class="sxs-lookup"><span data-stu-id="6fc38-131">**Red**</span></span>  
 <span data-ttu-id="6fc38-132">El valor decimal para la parte roja del color RGB.</span><span class="sxs-lookup"><span data-stu-id="6fc38-132">The decimal value for the red part of the RGB color.</span></span> <span data-ttu-id="6fc38-133">Use el cuadro de número para cambiar el valor o escriba un valor entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="6fc38-133">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="6fc38-134">**Verde**</span><span class="sxs-lookup"><span data-stu-id="6fc38-134">**Green**</span></span>  
 <span data-ttu-id="6fc38-135">El valor decimal para la parte verde del color RGB.</span><span class="sxs-lookup"><span data-stu-id="6fc38-135">The decimal value for the green part of the RGB color.</span></span> <span data-ttu-id="6fc38-136">Use el cuadro de número para cambiar el valor o escriba un valor entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="6fc38-136">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="6fc38-137">**Azul**</span><span class="sxs-lookup"><span data-stu-id="6fc38-137">**Blue**</span></span>  
 <span data-ttu-id="6fc38-138">El valor decimal para la parte azul del color RGB.</span><span class="sxs-lookup"><span data-stu-id="6fc38-138">The decimal value for the blue part of the RGB color.</span></span> <span data-ttu-id="6fc38-139">Use el cuadro de número para cambiar el valor o escriba un valor entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="6fc38-139">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="6fc38-140">**Alpha**</span><span class="sxs-lookup"><span data-stu-id="6fc38-140">**Alpha**</span></span>  
 <span data-ttu-id="6fc38-141">El valor decimal para alfa o la transparencia del color.</span><span class="sxs-lookup"><span data-stu-id="6fc38-141">The decimal value for the alpha or transparency part of the color.</span></span> <span data-ttu-id="6fc38-142">Cuando este valor está habilitado, puede usar el control deslizante para ajustar el grado de transparencia que desee.</span><span class="sxs-lookup"><span data-stu-id="6fc38-142">When this value is enabled, you can use the slider switch to adjust the degree of transparency you want.</span></span>  
  
 <span data-ttu-id="6fc38-143">**Hue**</span><span class="sxs-lookup"><span data-stu-id="6fc38-143">**Hue**</span></span>  
 <span data-ttu-id="6fc38-144">El valor decimal para el matiz del color HSB.</span><span class="sxs-lookup"><span data-stu-id="6fc38-144">The decimal value for the hue of the HSB color.</span></span> <span data-ttu-id="6fc38-145">Use el cuadro de número para cambiar el valor o escriba un valor entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="6fc38-145">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="6fc38-146">**Saturación**</span><span class="sxs-lookup"><span data-stu-id="6fc38-146">**Saturation**</span></span>  
 <span data-ttu-id="6fc38-147">El valor decimal para la saturación del color HSB.</span><span class="sxs-lookup"><span data-stu-id="6fc38-147">The decimal value for the saturation of the HSB color.</span></span> <span data-ttu-id="6fc38-148">Use el cuadro de número para cambiar el valor o escriba un valor entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="6fc38-148">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="6fc38-149">**Brillo**</span><span class="sxs-lookup"><span data-stu-id="6fc38-149">**Brightness**</span></span>  
 <span data-ttu-id="6fc38-150">El valor decimal para la luminosidad del color HSB.</span><span class="sxs-lookup"><span data-stu-id="6fc38-150">The decimal value for the brightness of the HSB color.</span></span> <span data-ttu-id="6fc38-151">Use el cuadro de número para cambiar el valor o escriba un valor entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="6fc38-151">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="6fc38-152">**Muestra de color**</span><span class="sxs-lookup"><span data-stu-id="6fc38-152">**Color sample**</span></span>  
 <span data-ttu-id="6fc38-153">Muestra el color actual en la mitad izquierda del panel e interactivamente muestra el nuevo color que se está eligiendo en la mitad derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="6fc38-153">Shows the current color on the left half of the pane and interactively shows the new color you are choosing on the right half of the pane.</span></span> <span data-ttu-id="6fc38-154">Si no hay ningún color predeterminado, la mitad izquierda del panel es blanca.</span><span class="sxs-lookup"><span data-stu-id="6fc38-154">If there is no default color, the left half of the pane is white.</span></span> <span data-ttu-id="6fc38-155">La mayoría de las propiedades RDL no tienen ningún color predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6fc38-155">Most RDL properties have no default color.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc38-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6fc38-156">See Also</span></span>  
 <span data-ttu-id="6fc38-157">[Aplicar formato a los elementos de informe &#40;Generador de informes y SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6fc38-157">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6fc38-158">Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6fc38-158">Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;</span></span>](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md)  
  
  
