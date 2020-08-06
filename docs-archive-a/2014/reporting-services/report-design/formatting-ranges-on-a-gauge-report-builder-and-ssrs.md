---
title: Aplicar formato a los rangos de un medidor (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ffdec8ca-3e95-41cd-850b-9e8c83be4b49
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29574c58eef6f18d685b48dd8d695a5fc42c3e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743961"
---
# <a name="formatting-ranges-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="d697c-102">Aplicar formato a los rangos de un medidor (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="d697c-102">Formatting Ranges on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d697c-103">Un intervalo de medidor es una zona o área en la escala del medidor que indica una subsección importante de valores en el medidor.</span><span class="sxs-lookup"><span data-stu-id="d697c-103">A gauge range is a zone or area on the gauge scale that indicates an important subsection of values on the gauge.</span></span> <span data-ttu-id="d697c-104">Use un intervalo de medidor para indicar visualmente el momento en el que el valor de puntero entra en cierto intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="d697c-104">Using a gauge range, you can visually indicate when the pointer value has gone into a certain span of values.</span></span> <span data-ttu-id="d697c-105">Los intervalos están definidos por un valor inicial y un valor final.</span><span class="sxs-lookup"><span data-stu-id="d697c-105">Ranges are defined by a start value and an end value.</span></span>  
  
 <span data-ttu-id="d697c-106">También se pueden usar intervalos para definir secciones diferentes de un medidor.</span><span class="sxs-lookup"><span data-stu-id="d697c-106">You can also use ranges to define different sections of a gauge.</span></span> <span data-ttu-id="d697c-107">Por ejemplo, en un medidor con valores comprendidos entre 0 y 10, puede definir un intervalo rojo para los valores comprendidos entre 0 y 3, un intervalo amarillo para los valores comprendidos entre 4 y 7 y un intervalo verde para los valores comprendidos entre 8 y 10.</span><span class="sxs-lookup"><span data-stu-id="d697c-107">For example, on a gauge with values from 0 to 10, you can define a red range that has a value from 0 to 3, a yellow range that has a value from 4 to 7 and a green range that has a value from 8 to 10.</span></span> <span data-ttu-id="d697c-108">Si el valor inicial especificado es mayor que el valor final especificado, se intercambian los valores para que el valor inicial sea el valor final y el valor final sea el valor inicial.</span><span class="sxs-lookup"><span data-stu-id="d697c-108">If the start value that you specified is greater than the end value that you specified, the values are swapped so that the start value is the end value and the end value is the start value.</span></span>  
  
 <span data-ttu-id="d697c-109">Puede colocar el intervalo del mismo modo que coloca los punteros en una escala.</span><span class="sxs-lookup"><span data-stu-id="d697c-109">You can position the range in the same way that you position pointers on a scale.</span></span> <span data-ttu-id="d697c-110">Las propiedades **Posición** y **Distancia desde escala** determinan la posición del intervalo.</span><span class="sxs-lookup"><span data-stu-id="d697c-110">The **Position** and **Distance from scale** properties determine the position of the range.</span></span> <span data-ttu-id="d697c-111">Para obtener más información, vea [Medidores &#40;Generador de informes y SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d697c-111">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d697c-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d697c-112">See Also</span></span>  
 <span data-ttu-id="d697c-113">[Aplicar formato a las escalas de un medidor &#40;Generador de informes y SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d697c-113">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d697c-114">[Aplicar formato a los punteros de un medidor &#40;Generador de informes y SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d697c-114">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d697c-115">[Establecer un valor mínimo o máximo en un medidor &#40;Generador de informes y SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d697c-115">[Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d697c-116">[Tutorial: Agregar un KPI al informe &#40;Generador de informes&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d697c-116">[Tutorial: Adding a KPI to Your Report &#40;Report Builder&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="d697c-117">Medidores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d697c-117">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
