---
title: Especificar colores coherentes en varios gráficos de formas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d52f68e9-2ba7-4bff-9053-4089e5164ab4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c2c89f0f8cda3b7d6ef6b2acbd0de66c87170357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662533"
---
# <a name="specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs"></a><span data-ttu-id="ee6b2-102">Especificar colores coherentes en varios gráficos de formas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="ee6b2-102">Specify Consistent Colors across Multiple Shape Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ee6b2-103">En los gráficos que no son de formas, se selecciona un nuevo color de la paleta en función del índice de series del gráfico.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-103">On non-shape charts, a new color is selected from the palette based on the index of series in the chart.</span></span> <span data-ttu-id="ee6b2-104">Por ejemplo, la primera serie del gráfico se asignará al primer color de la paleta.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-104">For example, the first series on your chart will be mapped to the first color in the palette.</span></span> <span data-ttu-id="ee6b2-105">Sin embargo, este comportamiento difiere para los gráficos de formas.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-105">However, this behavior differs for shape charts.</span></span> <span data-ttu-id="ee6b2-106">En los gráficos de formas, cada color de la paleta se asigna a un punto de datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-106">On shape charts, each color in the palette is mapped to a data point in the dataset.</span></span> <span data-ttu-id="ee6b2-107">Por ejemplo, el punto de datos 1 se asigna al primer color de la paleta, el punto de datos 2 se asigna al segundo color de la paleta, etc.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-107">For example, data point 1 is mapped to the first color in the palette, data point 2 is mapped to the second color palette and so on.</span></span>  
  
 <span data-ttu-id="ee6b2-108">Si un punto de datos no tiene ningún valor, se omite de la presentación en un gráfico de formas.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-108">If a data point has no value, it is omitted from display on a shape chart.</span></span> <span data-ttu-id="ee6b2-109">Esto significa que el punto de datos no se colorea.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-109">This means that the data point is skipped from being colored.</span></span> <span data-ttu-id="ee6b2-110">Por ejemplo, si el punto 2 tiene un valor de cero, el punto 1 se asignará al primer color de la paleta y el punto 3 se asignará al segundo color de la paleta.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-110">For example, if point 2 has a value of zero, point 1 will be mapped to the first color in the palette, and point 3 will be mapped to the second color in the palette.</span></span> <span data-ttu-id="ee6b2-111">Este método resulta útil porque los puntos vacíos del conjunto de datos de un gráfico circular no usan innecesariamente un color de la paleta cuando no es necesario dibujar el punto vacío.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-111">This approach is useful because the empty points in the dataset of a pie chart do not unnecessarily use a palette color when the empty point does not need to be drawn.</span></span>  
  
 <span data-ttu-id="ee6b2-112">Como efecto secundario, cuando se muestran varios gráficos circulares en un informe, dichos gráficos pueden mostrar colores diferentes para puntos de datos que tienen la misma agrupación de categoría.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-112">As a side effect, when multiple pie charts are displayed in a report, the pie charts may display different colors for data points that have the same category grouping.</span></span> <span data-ttu-id="ee6b2-113">Para solucionarlo, debe definir colores individuales que se asignen a un grupo de categorías en lugar de a valores de datos individuales.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-113">To resolve this, you need to define individual colors that map to a category group instead of individual data values.</span></span> <span data-ttu-id="ee6b2-114">Cómo lo haga depende de si los gráficos de formas son minigráficos en una tabla o matriz, o son gráficos de formas en el propio informe.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-114">How you do this depends on if the shape charts are sparklines in a table or matrix, or if they are shape charts in the report itself.</span></span>  
  
 <span data-ttu-id="ee6b2-115">La leyenda está conectada a la serie, de modo que cualquier color que especifique para ésta se mostrará automáticamente en la leyenda.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-115">The legend is connected to the series, so any color you specify for the series will automatically be shown on the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-consistent-colors-across-multiple-sparkline-shape-charts-in-a-table-or-matrix"></a><span data-ttu-id="ee6b2-116">Para especificar colores coherentes en varios gráficos de formas que son minigráficos en una tabla o matriz</span><span class="sxs-lookup"><span data-stu-id="ee6b2-116">To specify consistent colors across multiple sparkline shape charts in a table or matrix</span></span>  
  
1.  <span data-ttu-id="ee6b2-117">Haga clic en el gráfico para mostrar el panel Datos del gráfico.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-117">Click the chart to display the Chart Data pane.</span></span>  
  
2.  <span data-ttu-id="ee6b2-118">En el área **Grupos de categorías** , haga clic con el botón derecho en una categoría y, después, haga clic en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-118">In the **Category Groups** area, right-click a category and click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="ee6b2-119">En la pestaña General, en el cuadro **Sincronizar grupos en** , haga clic en el nombre de la categoría cuyos colores desea sincronizar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-119">On the General tab, in the **Synchronize groups in** box, click the name of the category for which you would like to synchronize colors, and then click **OK**.</span></span>  
  
### <a name="to-specify-consistent-colors-across-multiple-shape-charts"></a><span data-ttu-id="ee6b2-120">Para especificar colores coherentes en varios gráficos de formas</span><span class="sxs-lookup"><span data-stu-id="ee6b2-120">To specify consistent colors across multiple shape charts</span></span>  
  
1.  <span data-ttu-id="ee6b2-121">Haga clic con el botón derecho fuera del cuerpo del informe y seleccione **Propiedades del informe**.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-121">Right-click outside the body of the report, and select **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="ee6b2-122">En **Código**, escriba el código siguiente en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-122">In **Code**, type the following code into the textbox.</span></span>  
  
    ```  
    Private colorPalette As String() = {"Color1", "Color2", "Color3"}  
    Private count As Integer = 0  
    Private mapping As New System.Collections.Hashtable()  
    Public Function GetColor(ByVal groupingValue As String) As String  
        If mapping.ContainsKey(groupingValue) Then  
            Return mapping(groupingValue)  
        End If  
        Dim c As String = colorPalette(count Mod colorPalette.Length)  
        count = count + 1  
        mapping.Add(groupingValue, c)  
        Return c  
    End Function  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee6b2-123">Deberá reemplazar las cadenas de "Color1" por sus propios colores.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-123">You will need to replace the "Color1" strings with your own colors.</span></span> <span data-ttu-id="ee6b2-124">Puede usar colores con nombre, por ejemplo "Rojo", o un valor hexadecimal de seis dígitos que represente el color, como "#FFFFFF" para el negro.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-124">You can use named colors, for example "Red", or you can use six-digit hexadecimal value that represent the color, such as "#FFFFFF" for black.</span></span> <span data-ttu-id="ee6b2-125">Si ha definido más de tres colores, deberá extender la matriz de colores para que el número de colores de la matriz coincida con el número de puntos del gráfico de formas.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-125">If you have more than three colors defined, you will need to extend the array of colors so that the number of colors in the array matches the number of points in your shape chart.</span></span> <span data-ttu-id="ee6b2-126">Puede agregar nuevos colores a la matriz especificando una lista de valores de cadena separada por comas que contenga colores con nombre o representaciones hexadecimales de los colores.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-126">You can add new colors to the array by specifying a comma-separated list of string values that contain named colors or hexadecimal representations of colors.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="ee6b2-127">Haga clic con el botón derecho en el gráfico de formas y seleccione **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="ee6b2-127">Right-click on the shape chart and select **Series Properties**.</span></span>  
  
5.  <span data-ttu-id="ee6b2-128">En **Relleno**, haga clic en el botón **Expresión** (*fx*) para editar la expresión de la propiedad **Color** .</span><span class="sxs-lookup"><span data-stu-id="ee6b2-128">In **Fill**, click the **Expression** (*fx*) button to edit the expression for the **Color** property.</span></span>  
  
6.  <span data-ttu-id="ee6b2-129">Escriba la expresión siguiente, donde "MyCategoryField" es el campo que se muestra en el área **Grupos de categorías** :</span><span class="sxs-lookup"><span data-stu-id="ee6b2-129">Type the following expression, where "MyCategoryField" is the field that is displayed in the **Category Groups** area:</span></span>  
  
    ```  
    =Code.GetColor(Fields!MyCategoryField)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ee6b2-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee6b2-130">See Also</span></span>  
 <span data-ttu-id="ee6b2-131">[Aplicar formato a los colores de serie de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee6b2-131">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee6b2-132">[Agregar estilos con bisel, relieve y textura a un gráfico &#40;Generador de informes y SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ee6b2-132">[Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span></span>  
 <span data-ttu-id="ee6b2-133">[Definir los colores de un gráfico mediante una paleta &#40;Generador de informes y SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee6b2-133">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee6b2-134">[Agregar puntos vacíos al gráfico &#40;Generador de informes y SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee6b2-134">[Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee6b2-135">[Gráficos de formas &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee6b2-135">[Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee6b2-136">[Vincular varias regiones de datos al mismo conjunto de datos &#40;Generador de informes y SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee6b2-136">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee6b2-137">[Anidar regiones de datos &#40;Generador de informes y SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee6b2-137">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ee6b2-138">Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee6b2-138">Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
