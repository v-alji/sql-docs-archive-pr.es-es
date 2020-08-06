---
title: Agregar o quitar márgenes de un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d8bad99591964540bcd14fc5609560a3d324515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747477"
---
# <a name="add-or-remove-margins-from-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="b0b12-102">Agregar o quitar márgenes de un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="b0b12-102">Add or Remove Margins from a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b0b12-103">En los gráficos de dispersión y de columnas, el gráfico agrega automáticamente márgenes laterales en los extremos del eje X.</span><span class="sxs-lookup"><span data-stu-id="b0b12-103">In Column and Scatter chart types, the chart automatically adds side margins on the ends of the x-axis.</span></span> <span data-ttu-id="b0b12-104">En los gráficos de barras, el gráfico agrega automáticamente márgenes laterales en los extremos del eje Y.</span><span class="sxs-lookup"><span data-stu-id="b0b12-104">In Bar chart types, the chart automatically adds side margins on the ends of the y-axis.</span></span> <span data-ttu-id="b0b12-105">En todos los demás tipos de gráficos, el gráfico no agrega márgenes laterales.</span><span class="sxs-lookup"><span data-stu-id="b0b12-105">In all other chart types, the chart does not add side margins.</span></span> <span data-ttu-id="b0b12-106">No puede cambiar el tamaño del margen.</span><span class="sxs-lookup"><span data-stu-id="b0b12-106">You cannot change the size of the margin.</span></span>  
  
 <span data-ttu-id="b0b12-107">Este tema no se aplica a los tipos de gráficos circulares, de anillos, de embudo ni piramidales.</span><span class="sxs-lookup"><span data-stu-id="b0b12-107">This topic does not apply to pie, doughnut, funnel, or pyramid chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-or-disable-side-margins"></a><span data-ttu-id="b0b12-108">Habilitar o deshabilitar los márgenes laterales</span><span class="sxs-lookup"><span data-stu-id="b0b12-108">To enable or disable side margins</span></span>  
  
1.  <span data-ttu-id="b0b12-109">Haga clic con el botón derecho en el eje y seleccione **Propiedades del eje**.</span><span class="sxs-lookup"><span data-stu-id="b0b12-109">Right-click the axis and select **Axis Properties**.</span></span> <span data-ttu-id="b0b12-110">Se abre el cuadro de diálogo **Propiedades del eje vertical** u **horizontal** .</span><span class="sxs-lookup"><span data-stu-id="b0b12-110">The **Vertical** or **HorizontalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="b0b12-111">En la página **Opciones del eje** , establezca la propiedad **Márgenes laterales** :</span><span class="sxs-lookup"><span data-stu-id="b0b12-111">On the **Axis Options** page, set the **Side margins** property:</span></span>  
  
    -   <span data-ttu-id="b0b12-112">**Automático:** el gráfico determinará si se agrega un margen lateral basado en el tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="b0b12-112">**Auto** The chart will determine whether to add a side margin based on the chart type.</span></span>  
  
    -   <span data-ttu-id="b0b12-113">**Deshabilitado:** los gráficos de barras, columna y dispersión no tendrán márgenes laterales.</span><span class="sxs-lookup"><span data-stu-id="b0b12-113">**Disabled** Bar, column, and scatter charts will have no side margins.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0b12-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0b12-114">See Also</span></span>  
 <span data-ttu-id="b0b12-115">[Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b0b12-115">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b0b12-116">[Cuadro de diálogo Propiedades del eje, Opciones del eje &#40;Generador de informes y SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b0b12-116">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b0b12-117">[Especificar un intervalo de eje &#40;Generador de informes y SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b0b12-117">[Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b0b12-118">[Aplicar formato de fecha o de moneda a las etiquetas de los ejes &#40;Generador de informes y SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b0b12-118">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b0b12-119">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0b12-119">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
