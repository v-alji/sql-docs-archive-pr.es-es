---
title: Agregar estilos con bisel, relieve y textura a un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 737cfc80-b39e-497c-817b-b46693deb58f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 92c5d4af47b7889b9ba5ec421706848f8822075b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676365"
---
# <a name="add-bevel-emboss-and-texture-styles-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="0f8b0-102">Agregar estilos con bisel, relieve y textura a un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="0f8b0-102">Add Bevel, Emboss, and Texture Styles to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0f8b0-103">Cuando use determinados tipos de gráficos, puede especificar efectos de dibujo que aumenten el impacto visual del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-103">When using certain chart types, you can specify a drawing effect to increase the visual impact of your chart.</span></span> <span data-ttu-id="0f8b0-104">Estos efectos de dibujo solamente se aplican a las series del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-104">These drawing effects are only applied to the series of your chart.</span></span> <span data-ttu-id="0f8b0-105">No afectan a ningún otro elemento del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-105">They have no effect on any other chart element.</span></span>  
  
 <span data-ttu-id="0f8b0-106">Cuando use cualquier variante de un gráfico circular o de anillos, puede especificar un estilo de dibujo de borde suave o cóncavo, similar a los efectos de bisel o de relieve que se pueden aplicar a una imagen.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-106">When you are using any variant of a pie or doughnut chart, you can specify a soft edge or concave drawing style, similar to bevel or emboss effects that can be applied to an image.</span></span>  
  
 <span data-ttu-id="0f8b0-107">Cuando use cualquier variante de un gráfico de barras o de columnas, puede aplicar estilos de textura, como cilindros, cuñas y degradados a barras o columnas individuales.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-107">When you are using any variant of a bar or column chart, you can apply texture styles, such as cylinder, wedge, and light-to-dark, to the individual bars or columns.</span></span>  
  
 <span data-ttu-id="0f8b0-108">Además de estos estilos de dibujo, puede agregar bordes y sombras a muchos elementos del gráfico para crear una sensación de profundidad.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-108">In addition to these drawing styles, you can add borders and shadows to many chart elements to give the illusion of depth.</span></span> <span data-ttu-id="0f8b0-109">Para más información sobre otras maneras de dar formato al gráfico, vea [Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f8b0-109">For more information on other ways to format the chart, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-bevel-or-emboss-styles-to-a-pie-or-doughnut-chart"></a><span data-ttu-id="0f8b0-110">Para agregar estilos de bisel y de relieve a un gráfico circular o de anillos</span><span class="sxs-lookup"><span data-stu-id="0f8b0-110">To add bevel or emboss styles to a pie or doughnut chart</span></span>  
  
1.  <span data-ttu-id="0f8b0-111">En la pestaña **Vista** , seleccione **Propiedades** para abrir el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-111">On the **View** tab, select **Properties** to open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="0f8b0-112">Seleccione el gráfico circular o de anillos que desea mejorar.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-112">Select the pie or doughnut chart that you want to enhance.</span></span> <span data-ttu-id="0f8b0-113">Seleccione un campo de datos en el gráfico, no en el gráfico entero.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-113">Select a data field in the chart, not the entire chart.</span></span>  
  
3.  <span data-ttu-id="0f8b0-114">En el panel de propiedades, expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="0f8b0-114">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="0f8b0-115">Para PieDrawingStyle, seleccione un estilo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-115">For PieDrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f8b0-116">No puede tener estilos de relieve o bisel, y 3D en el mismo gráfico.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-116">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="0f8b0-117">Si ha habilitado 3D para el gráfico, no verá la propiedad PieDrawingStyle.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-117">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="0f8b0-118">![Gráfico circular con estilo de dibujo cóncavo](../media/rs-piedrawingeffects-concave.gif "Gráfico circular con estilo de dibujo cóncavo")</span><span class="sxs-lookup"><span data-stu-id="0f8b0-118">![Pie chart with concave drawing style](../media/rs-piedrawingeffects-concave.gif "Pie chart with concave drawing style")</span></span>  
  
### <a name="to-add-texture-styles-to-a-bar-or-column-chart"></a><span data-ttu-id="0f8b0-119">Para agregar estilos de textura a un gráfico de barras o de columnas</span><span class="sxs-lookup"><span data-stu-id="0f8b0-119">To add texture styles to a bar or column chart</span></span>  
  
1.  <span data-ttu-id="0f8b0-120">Seleccione el gráfico de barras o de columnas que desea mejorar.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-120">Select the bar or column chart that you want to enhance.</span></span> <span data-ttu-id="0f8b0-121">Seleccione un campo de datos en el gráfico, no en el gráfico entero.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-121">Select a data field in the chart, not the entire chart.</span></span>  
  
2.  <span data-ttu-id="0f8b0-122">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-122">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="0f8b0-123">Expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="0f8b0-123">Expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="0f8b0-124">Para DrawingStyle, seleccione un estilo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-124">For DrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f8b0-125">No puede tener estilos de relieve o bisel, y 3D en el mismo gráfico.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-125">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="0f8b0-126">Si ha habilitado 3D para el gráfico, no verá la propiedad PieDrawingStyle.</span><span class="sxs-lookup"><span data-stu-id="0f8b0-126">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="0f8b0-127">![Gráfico de barras con efecto de dibujo LightToDark](../media/rs-bardrawingeffects-lighttodark.gif "Gráfico de barras con efecto de dibujo LightToDark")</span><span class="sxs-lookup"><span data-stu-id="0f8b0-127">![Bar chart with LightToDark drawing effect](../media/rs-bardrawingeffects-lighttodark.gif "Bar chart with LightToDark drawing effect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f8b0-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f8b0-128">See Also</span></span>  
 <span data-ttu-id="0f8b0-129">[Gráficos de barras &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0f8b0-129">[Bar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0f8b0-130">[Gráficos de columnas &#40;Generador de informes y SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0f8b0-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0f8b0-131">[Gráficos circulares &#40;Generador de informes y SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0f8b0-131">[Pie Charts &#40;Report Builder and SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0f8b0-132">Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0f8b0-132">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
