---
title: Agregar una media móvil a un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bc16d0cb45a3240148f931009a836c231b442b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662562"
---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="bda73-102">Agregar una media móvil a un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="bda73-102">Add a Moving Average to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bda73-103">Una media móvil es una media de los datos de la serie, calculada en un período de tiempo definido.</span><span class="sxs-lookup"><span data-stu-id="bda73-103">A moving average is an average of the data in your series, calculated over a defined period of time.</span></span> <span data-ttu-id="bda73-104">La media móvil se puede mostrar en el gráfico para identificar tendencias significativas.</span><span class="sxs-lookup"><span data-stu-id="bda73-104">The moving average can be shown on the chart to identify significant trends.</span></span>  
  
 <span data-ttu-id="bda73-105">La fórmula de la media móvil es el indicador de precio más habitual en los análisis técnicos.</span><span class="sxs-lookup"><span data-stu-id="bda73-105">The Moving Average formula is the most popular price indicator used in technical analyses.</span></span> <span data-ttu-id="bda73-106">También se pueden derivar de una serie del gráfico muchas otras fórmulas, como el promedio, la mediana y la desviación estándar.</span><span class="sxs-lookup"><span data-stu-id="bda73-106">Many other formulas, including mean, median and standard deviation, can also be derived from a series on the chart.</span></span> <span data-ttu-id="bda73-107">Al especificar una media móvil, cada fórmula puede tener uno o varios parámetros que deberá especificar.</span><span class="sxs-lookup"><span data-stu-id="bda73-107">When specifying a moving average, each formula may have one or more parameters that must be specified.</span></span>  
  
 <span data-ttu-id="bda73-108">Cuando se agrega una fórmula de media móvil en modo de diseño, la serie de líneas que se agrega es solo un marcador de posición visual.</span><span class="sxs-lookup"><span data-stu-id="bda73-108">When a moving average formula is added in Design mode, the line series that is added is only a visual placeholder.</span></span> <span data-ttu-id="bda73-109">El gráfico calculará los puntos de datos de cada fórmula durante el procesamiento del informe.</span><span class="sxs-lookup"><span data-stu-id="bda73-109">The chart will calculate the data points of each formula during report processing.</span></span>  
  
 <span data-ttu-id="bda73-110">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], no está disponible la compatibilidad integrada para las líneas de tendencia.</span><span class="sxs-lookup"><span data-stu-id="bda73-110">Built-in support for trend lines is not available in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a><span data-ttu-id="bda73-111">Para agregar una media móvil calculada a una serie del gráfico</span><span class="sxs-lookup"><span data-stu-id="bda73-111">To add a calculated moving average to a series on the chart</span></span>  
  
1.  <span data-ttu-id="bda73-112">Haga clic con el botón secundario en el área **Valores** y, a continuación, haga clic en **Agregar serie calculada**.</span><span class="sxs-lookup"><span data-stu-id="bda73-112">Right-click on a field in the **Values** area and click **Add Calculated Series**.</span></span> <span data-ttu-id="bda73-113">Se abre el cuadro de diálogo **Propiedades de la serie calculada** .</span><span class="sxs-lookup"><span data-stu-id="bda73-113">The **Calculated Series Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="bda73-114">Seleccione la opción **Media móvil** en la lista desplegable **Fórmula** .</span><span class="sxs-lookup"><span data-stu-id="bda73-114">Select the **Moving average** option from the **Formula** drop-down list.</span></span>  
  
3.  <span data-ttu-id="bda73-115">Especifique un valor entero para el **Período** que representa el período de la media móvil.</span><span class="sxs-lookup"><span data-stu-id="bda73-115">Specify an integer value for the **Period** that represents the period of the moving average.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bda73-116">El período es el número de días usado para calcular una media móvil.</span><span class="sxs-lookup"><span data-stu-id="bda73-116">The period is the number of days used to calculate a moving average.</span></span> <span data-ttu-id="bda73-117">Si en el eje X no se especifican valores de fecha y hora, el período de tiempo lo representa el número de puntos de datos usados para calcular una media móvil.</span><span class="sxs-lookup"><span data-stu-id="bda73-117">If date/time values are not specified on the x-axis, the period is represented by the number of data points used to calculate a moving average.</span></span> <span data-ttu-id="bda73-118">Si solo hay un punto de datos, la fórmula de la media móvil no se calcula.</span><span class="sxs-lookup"><span data-stu-id="bda73-118">If there is only one data point, the moving average formula does not calculate.</span></span> <span data-ttu-id="bda73-119">La media móvil se calcula a partir del segundo punto.</span><span class="sxs-lookup"><span data-stu-id="bda73-119">The moving average is calculated starting at the second point.</span></span> <span data-ttu-id="bda73-120">Si especifica la opción **Empezar desde el primer punto** , el gráfico iniciará la media móvil en el primer punto.</span><span class="sxs-lookup"><span data-stu-id="bda73-120">If you specify the **Start from first point** option, the chart will start the moving average at the first point.</span></span> <span data-ttu-id="bda73-121">Si solo hay un punto de datos, el punto de la media móvil calculada será idéntico al primer punto de la serie original.</span><span class="sxs-lookup"><span data-stu-id="bda73-121">If there is only one data point, the point in the calculated moving average will be identical to the first point in your original series.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda73-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bda73-122">See Also</span></span>  
 <span data-ttu-id="bda73-123">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bda73-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bda73-124">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bda73-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bda73-125">Agregar puntos vacíos al gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bda73-125">Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;</span></span>](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  
