---
title: Agregar un marco de borde a un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c91d3de00caa4eab6ed1894042b2214b7dcf4b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749125"
---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="f75c8-102">Agregar un marco de borde a un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="f75c8-102">Add a Border Frame to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f75c8-103">Para dar un mayor impacto visual a un gráfico, considere la posibilidad de situar un marco de borde alrededor del gráfico.</span><span class="sxs-lookup"><span data-stu-id="f75c8-103">To give a chart more visual impact, consider using a border frame around the outside of the chart.</span></span> <span data-ttu-id="f75c8-104">Para seleccionar un marco de borde, puede usar el cuadro de diálogo **Propiedades del gráfico** o el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="f75c8-104">You can select a border frame by using the **Chart Properties** dialog box or by using the Properties pane.</span></span> <span data-ttu-id="f75c8-105">Los marcos de borde de gráfico no se pueden aplicar a ninguna otra región de datos.</span><span class="sxs-lookup"><span data-stu-id="f75c8-105">The chart border frames cannot be applied to any other data region.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a><span data-ttu-id="f75c8-106">Para aplicar un borde a un gráfico</span><span class="sxs-lookup"><span data-stu-id="f75c8-106">To apply a border to a chart</span></span>  
  
1.  <span data-ttu-id="f75c8-107">Haga clic con el botón derecho en cualquier lugar del gráfico y seleccione **Propiedades del gráfico**.</span><span class="sxs-lookup"><span data-stu-id="f75c8-107">Right-click anywhere on the chart and select **Chart Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f75c8-108">Si **Propiedades del gráfico**no está visible, seleccione **Gráfico** en el menú contextual y, después, seleccione **Propiedades del gráfico**.</span><span class="sxs-lookup"><span data-stu-id="f75c8-108">If you do not see the **Chart Properties**, point to **Chart** on the shortcut menu and select **Chart Properties**.</span></span>  
  
2.  <span data-ttu-id="f75c8-109">Seleccione **Borde**y haga clic en el tipo de borde que desea aplicar al gráfico.</span><span class="sxs-lookup"><span data-stu-id="f75c8-109">Select **Border**, and click the type of border to apply to the chart.</span></span>  
  
3.  <span data-ttu-id="f75c8-110">(Opcional) Seleccione un valor o escriba una expresión que represente el estilo del borde.</span><span class="sxs-lookup"><span data-stu-id="f75c8-110">(Optional) Select a value or type an expression that represents the style of the border.</span></span>  
  
4.  <span data-ttu-id="f75c8-111">(Opcional) Especifique el color de la línea que se dibujará alrededor del gráfico.</span><span class="sxs-lookup"><span data-stu-id="f75c8-111">(Optional) Specify the color of the line that will be drawn around the chart as the border.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f75c8-112">La lista **Color de línea** contiene los colores comunes.</span><span class="sxs-lookup"><span data-stu-id="f75c8-112">The **Line color** list contains common colors.</span></span> <span data-ttu-id="f75c8-113">Si quiere hacer su selección en una lista con más colores, haga clic en **Más colores** en la lista o haga clic en el botón de expresión (**fx**) situado junto a la lista para iniciar el editor **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="f75c8-113">If you want to select from a list of more colors, click **More colors** in the list or click the expression (**fx**) button next to the list to bring up the **Expression** editor.</span></span>  
  
5.  <span data-ttu-id="f75c8-114">(Opcional) Especifique el ancho del borde.</span><span class="sxs-lookup"><span data-stu-id="f75c8-114">(Optional) Specify the width of the border.</span></span> <span data-ttu-id="f75c8-115">Los valores válidos van de 0,25 pt a 20 pt.</span><span class="sxs-lookup"><span data-stu-id="f75c8-115">Valid values are between 0.25pt and 20pt.</span></span> <span data-ttu-id="f75c8-116">Considere la posibilidad de mantener el tamaño del borde entre 1 y 3 pt para conseguir el mejor efecto visual posible.</span><span class="sxs-lookup"><span data-stu-id="f75c8-116">Consider keeping the size of your border to between 1 and 3pt for the best visual effect.</span></span>  
  
6.  <span data-ttu-id="f75c8-117">(Opcional) Si el informe contiene un color de fondo distinto del blanco, plantéese la posibilidad de definir un color de página con el mismo color.</span><span class="sxs-lookup"><span data-stu-id="f75c8-117">(Optional) If your report contains a background color other than white, consider defining a page color that is the same color.</span></span> <span data-ttu-id="f75c8-118">El color de página es el color de fondo que se ve alrededor de la línea de borde.</span><span class="sxs-lookup"><span data-stu-id="f75c8-118">The page color is the background color outside of the border line.</span></span>  
  
7.  <span data-ttu-id="f75c8-119">(Opcional) Si elige un tipo de marco, especifique un estilo y un color para dicho marco.</span><span class="sxs-lookup"><span data-stu-id="f75c8-119">(Optional) If you choose a Frame type, specify a style and color for the frame.</span></span> <span data-ttu-id="f75c8-120">La lista **Color de relleno de marco** contiene los colores comunes.</span><span class="sxs-lookup"><span data-stu-id="f75c8-120">The **Frame fill color** list contains common colors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75c8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f75c8-121">See Also</span></span>  
 <span data-ttu-id="f75c8-122">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f75c8-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f75c8-123">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f75c8-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f75c8-124">Agregar estilos con bisel, relieve y textura a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f75c8-124">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
