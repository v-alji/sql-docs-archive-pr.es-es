---
title: Aplicar formato a líneas, colores e imágenes (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.textboxproperties.border.f1
- "10502"
- "10094"
- sql12.rtp.rptdesigner.pictureproperties.border.f1
- "10063"
- sql12.rtp.rptdesigner.rectangleproperties.border.f1
- "10055"
- sql12.rtp.rptdesigner.subreportproperties.border.f1
- "10126"
- sql12.rtp.rptdesigner.shared.borderdv.f1
- "10066"
- sql12.rtp.rptdesigner.reportbody.border.f1
ms.assetid: 0f5f0d2a-9537-4152-b441-b40d7f04cf4c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 681ff6b46f692804aef5c7cbbc16e5abe99dbb2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743967"
---
# <a name="formatting-lines-colors-and-images-report-builder-and-ssrs"></a><span data-ttu-id="b0e03-102">Aplicar formato a líneas, colores e imágenes (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="b0e03-102">Formatting Lines, Colors, and Images (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="b0e03-103">le permite dar formato a las líneas, los colores, las regiones de datos, las imágenes y otros elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="b0e03-103">gives you the ability to format lines, colors, data regions, images, and other report items.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="borders-lines-and-gridlines"></a><span data-ttu-id="b0e03-104">Bordes, líneas y líneas de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="b0e03-104">Borders, Lines and Gridlines</span></span>  
 <span data-ttu-id="b0e03-105">Los bordes, las líneas y las líneas de cuadrícula pueden unir visualmente elementos de la página y facilitar a los lectores del informe la lectura del contenido de éste.</span><span class="sxs-lookup"><span data-stu-id="b0e03-105">Borders, lines, and gridlines can visually tie items together on the page and help your report readers easily read the contents of the report.</span></span> <span data-ttu-id="b0e03-106">Con los estilos de borde predefinidos puede agregar rápidamente un borde a un cuadro de texto, un grupo de cuadros de texto o una imagen.</span><span class="sxs-lookup"><span data-stu-id="b0e03-106">Using the predefined border styles, you can quickly add a border around a text box, a group of text boxes, or an image.</span></span> <span data-ttu-id="b0e03-107">Además, puede cambiar el estilo, el ancho y el color de los bordes, las líneas y las líneas de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="b0e03-107">In addition, you can change the style, width, and color for the borders, lines, and gridlines.</span></span> <span data-ttu-id="b0e03-108">Los bordes se agregan alrededor del elemento completo seleccionado o en uno de los bordes del elemento, por ejemplo, a lo largo del borde inferior de un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="b0e03-108">Borders are added around the entire item selected or around a border along an edge of the item, for example, a border along the bottom of a text box.</span></span>  
  
 <span data-ttu-id="b0e03-109">Para dar formato a los bordes y a las líneas de cuadrícula de un cuadro de texto, un diseño de informe o una imagen, use la pestaña **Borde** del cuadro de diálogo **Propiedades** del elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="b0e03-109">To format borders and gridlines in a text box, report layout, or around an image, use the **Border** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="b0e03-110">Por ejemplo, si quiere agregar un borde alrededor de una imagen, haga clic con el botón derecho en la imagen y, después, en el cuadro de diálogo **Propiedades de la imagen** , haga clic en **Borde**.</span><span class="sxs-lookup"><span data-stu-id="b0e03-110">For example, if you want to add a border around an image, right-click the image and then in the **Image Properties** dialog box, click **Border**.</span></span>  
  
 <span data-ttu-id="b0e03-111">Además de los marcos de borde estándar, también puede aplicar a los gráficos marcos de borde adicionales.</span><span class="sxs-lookup"><span data-stu-id="b0e03-111">In addition to the standard border frames, additional border frames can be applied to charts.</span></span> <span data-ttu-id="b0e03-112">Para más información, vea [Agregar un marco de borde a un gráfico &#40;Generador de informes y SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b0e03-112">For more information, see [Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="b0e03-113">También puede agregar un borde al propio informe.</span><span class="sxs-lookup"><span data-stu-id="b0e03-113">You can also add a border to the report itself.</span></span> <span data-ttu-id="b0e03-114">Para más información, vea [Agregar un borde a un informe &#40;Generador de informes y SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b0e03-114">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="applying-background-colors"></a><span data-ttu-id="b0e03-115">Aplicar colores de fondo</span><span class="sxs-lookup"><span data-stu-id="b0e03-115">Applying Background Colors</span></span>  
 <span data-ttu-id="b0e03-116">Se puede agregar un color sólido al fondo de todo el informe, de un cuadro de texto del informe o de una celda o grupo de celdas de una región de datos.</span><span class="sxs-lookup"><span data-stu-id="b0e03-116">A solid color can be added to the background of the entire report, a text box within the report, or to a cell or group of cells within a data region.</span></span> <span data-ttu-id="b0e03-117">El color de fondo predeterminado es el blanco; no obstante, puede seleccionar otro color en la pestaña **Relleno** del cuadro de diálogo **Propiedades** del elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="b0e03-117">By default, the background color is white; however, you can select a color from the **Fill** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="b0e03-118">Por ejemplo, si quiere cambiar el color de fondo de un cuadro de texto, haga clic con el botón derecho en el cuadro de texto y seleccione **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="b0e03-118">For example, if you want to change the background color of a text box, right-click the text box and select **Text Box Properties**.</span></span> <span data-ttu-id="b0e03-119">Haga clic en **Relleno** y, a continuación, seleccione el color que desea usar.</span><span class="sxs-lookup"><span data-stu-id="b0e03-119">Click **Fill** and then select the color you want.</span></span> <span data-ttu-id="b0e03-120">En este cuadro de diálogo, puede seleccionar un color de fondo para el elemento seleccionado o puede agregar una imagen para que aparezca como fondo.</span><span class="sxs-lookup"><span data-stu-id="b0e03-120">In this dialog box, you can select a background color for the selected item or you can add an image that appears in the background.</span></span>  
  
 <span data-ttu-id="b0e03-121">Cuando use el gráfico, también podrá especificar degradados y estilos de trama para los colores de fondo.</span><span class="sxs-lookup"><span data-stu-id="b0e03-121">When you use the chart, you can also specify gradients and pattern styles for background colors.</span></span> <span data-ttu-id="b0e03-122">Para más información, vea [Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b0e03-122">For more information, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="using-images-as-formatting"></a><span data-ttu-id="b0e03-123">Utilizar las imágenes como formato</span><span class="sxs-lookup"><span data-stu-id="b0e03-123">Using Images as Formatting</span></span>  
 <span data-ttu-id="b0e03-124">Se pueden agregar a una región de datos campos que contengan imágenes.</span><span class="sxs-lookup"><span data-stu-id="b0e03-124">Fields that contain images can be added to a data region.</span></span> <span data-ttu-id="b0e03-125">Si usa un campo de imagen, las imágenes aparecerán en el informe al ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="b0e03-125">If you use an image field, the images appear in the report with the report is run.</span></span>  
  
 <span data-ttu-id="b0e03-126">También puede agregar imágenes, como los logotipos, al fondo de su informe o a un rectángulo, cuadro de texto, tabla, matriz o algunas partes de un gráfico o a las secciones de página y al cuerpo de un informe.</span><span class="sxs-lookup"><span data-stu-id="b0e03-126">You can also add images such as logos to the background of your report or to a rectangle, text box, table, matrix, or some parts of a chart, or to the body and page sections of a report.</span></span> <span data-ttu-id="b0e03-127">Para obtener más información, vea [Imágenes &#40;Generador de informes y SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b0e03-127">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e03-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0e03-128">See Also</span></span>  
 <span data-ttu-id="b0e03-129">[Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b0e03-129">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b0e03-130">[Aplicar formato a números y fechas &#40;Generador de informes y SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b0e03-130">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b0e03-131">[Dar formato al texto en un cuadro de texto &#40;Generador de informes y SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b0e03-131">[Format Text in a Text Box &#40;Report Builder and SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b0e03-132">Cuadro de diálogo Relleno &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0e03-132">Fill Dialog Box &#40;Report Builder and SSRS&#41;</span></span>](../fill-dialog-box-report-builder-and-ssrs.md)  
  
  
