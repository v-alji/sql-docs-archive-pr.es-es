---
title: Definir los colores de un gráfico mediante una paleta (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7db137ed87b0c84e43577dcf2936a6287abd8e36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672737"
---
# <a name="define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs"></a><span data-ttu-id="756b5-102">Definir los colores de un gráfico mediante una paleta (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="756b5-102">Define Colors on a Chart Using a Palette (Report Builder and SSRS)</span></span>
  <span data-ttu-id="756b5-103">Para cambiar la paleta de colores de un gráfico, puede seleccionar una paleta predefinida o definir una paleta personalizada.</span><span class="sxs-lookup"><span data-stu-id="756b5-103">You can change the color palette for a chart by selecting a pre-defined palette or defining a custom palette.</span></span> <span data-ttu-id="756b5-104">Las paletas personalizadas son específicas de cada informe.</span><span class="sxs-lookup"><span data-stu-id="756b5-104">Custom palettes are report-specific.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-colors-on-the-chart-using-a-built-in-color-palette"></a><span data-ttu-id="756b5-105">Para cambiar los colores del gráfico mediante una paleta de colores integrada</span><span class="sxs-lookup"><span data-stu-id="756b5-105">To change the colors on the chart using a built-in color palette</span></span>  
  
1.  <span data-ttu-id="756b5-106">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="756b5-106">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="756b5-107">En la superficie de diseño, haga clic en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="756b5-107">On the design surface, click the chart.</span></span> <span data-ttu-id="756b5-108">Las propiedades del objeto de gráfico se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="756b5-108">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
     <span data-ttu-id="756b5-109">El nombre del objeto (de forma predeterminada,**Chart1** ) aparece en la lista desplegable de la parte superior del panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="756b5-109">The object name (**Chart1** by default) appears in the drop-down list at the top of the Properties pane.</span></span>  
  
3.  <span data-ttu-id="756b5-110">En la sección **Gráfico** , para la propiedad Palette, seleccione una nueva paleta en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="756b5-110">In the **Chart** section, for the Palette property, select a new palette from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="756b5-111">No puede cambiar los colores ni su orden en una paleta predefinida.</span><span class="sxs-lookup"><span data-stu-id="756b5-111">You cannot change the colors or order in a pre-defined palette.</span></span>  
  
### <a name="to-define-your-own-colors-on-the-chart-using-a-custom-color-palette"></a><span data-ttu-id="756b5-112">Para definir sus propios colores para el gráfico utilizando una paleta de colores personalizada</span><span class="sxs-lookup"><span data-stu-id="756b5-112">To define your own colors on the chart using a custom color palette</span></span>  
  
1.  <span data-ttu-id="756b5-113">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="756b5-113">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="756b5-114">En la superficie de diseño, haga clic en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="756b5-114">On the design surface, click the chart.</span></span> <span data-ttu-id="756b5-115">Las propiedades del objeto de gráfico se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="756b5-115">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="756b5-116">En la sección **gráfico** , para la `Palette` propiedad, seleccione **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="756b5-116">In the **Chart** section, for the `Palette` property, select **Custom**.</span></span>  
  
4.  <span data-ttu-id="756b5-117">En la propiedad CustomPaletteColors, haga clic en el botón Editar colección ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="756b5-117">In the CustomPaletteColors property, click the Edit Collection (**...**) button.</span></span> <span data-ttu-id="756b5-118">Se abre el **Editor de la colección ReportColorExpression** .</span><span class="sxs-lookup"><span data-stu-id="756b5-118">The **ReportColorExpression Collection Editor** opens.</span></span>  
  
5.  <span data-ttu-id="756b5-119">Haga clic **Agregar** para agregar un color.</span><span class="sxs-lookup"><span data-stu-id="756b5-119">Click **Add** to add a color.</span></span> <span data-ttu-id="756b5-120">Seleccione un color de la lista desplegable o seleccione Expresión y especifique un valor hexadecimal para un color específico, como ff6600 para "Anaranjado".</span><span class="sxs-lookup"><span data-stu-id="756b5-120">Select a color from the drop-down list or select Expression and specify a hex value for a specific color, such as ff6600 for "Orange".</span></span>  
  
     <span data-ttu-id="756b5-121">Para obtener más información sobre los valores hexadecimales, vea [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="756b5-121">For more information about hex values, see [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) on MSDN.</span></span>  
  
6.  <span data-ttu-id="756b5-122">Haga clic **Agregar** para agregar más colores a la paleta.</span><span class="sxs-lookup"><span data-stu-id="756b5-122">Click **Add** to add more colors to the palette.</span></span>  
  
7.  <span data-ttu-id="756b5-123">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="756b5-123">When you are done, click **OK**.</span></span>  
  
 <span data-ttu-id="756b5-124">Si está utilizando una paleta personalizada, puede cambiar el orden de los colores para cambiar el color de las distintas series del gráfico.</span><span class="sxs-lookup"><span data-stu-id="756b5-124">If you are using a custom palette, you can change the order of the colors to change the color of different series in the chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756b5-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="756b5-125">See Also</span></span>  
 <span data-ttu-id="756b5-126">[Aplicar formato a los colores de serie de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="756b5-126">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="756b5-127">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="756b5-127">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="756b5-128">Especificar colores coherentes en varios gráficos de formas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="756b5-128">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
