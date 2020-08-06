---
title: Establecer un intervalo de ajuste en un medidor (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0ece7297-6e2f-47fb-835d-b9e9cce53fe2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdc2a621c4406791838d97e93f47cd32fa9d5f94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747432"
---
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="bc88b-102">Establecer un intervalo de ajuste en un medidor (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="bc88b-102">Set a Snapping Interval on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bc88b-103">Un intervalo de ajuste define el múltiplo al que se redondean los valores.</span><span class="sxs-lookup"><span data-stu-id="bc88b-103">A snapping interval defines the multiple to which values are rounded.</span></span> <span data-ttu-id="bc88b-104">De forma predeterminada, el medidor señala el valor exacto del campo que se ha especificado en el panel de datos.</span><span class="sxs-lookup"><span data-stu-id="bc88b-104">By default, the gauge will point to the exact value of the field you have specified in the data pane.</span></span> <span data-ttu-id="bc88b-105">Sin embargo, puede que desee redondear el valor exacto hacia arriba o hacia abajo para que el puntero se ajuste a un intervalo preestablecido.</span><span class="sxs-lookup"><span data-stu-id="bc88b-105">However, you may want to round the exact value up or down so that the pointer will snap to a preset interval.</span></span> <span data-ttu-id="bc88b-106">Por ejemplo, si el valor del medidor es de 34,2 y especifica un intervalo de ajuste de 5, el puntero del medidor señalará 3,5.</span><span class="sxs-lookup"><span data-stu-id="bc88b-106">For example, if the value on your gauge is 34.2 and you specify a snapping interval of 5, the gauge pointer will point to 35.</span></span> <span data-ttu-id="bc88b-107">Si el valor del medidor es de 31,2 y especifica un intervalo de ajuste de 5, el puntero del medidor señalará 30.</span><span class="sxs-lookup"><span data-stu-id="bc88b-107">If the value on your gauge is 31.2 and you specify a snapping interval of 5, the gauge pointer will point to 30.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a><span data-ttu-id="bc88b-108">Para establecer un intervalo de ajuste en un medidor</span><span class="sxs-lookup"><span data-stu-id="bc88b-108">To set a snapping interval on a gauge</span></span>  
  
1.  <span data-ttu-id="bc88b-109">Haga clic en cualquier lugar en los números del medidor para resaltar la escala.</span><span class="sxs-lookup"><span data-stu-id="bc88b-109">Click anywhere on the numbers of the gauge to highlight the scale.</span></span>  
  
2.  <span data-ttu-id="bc88b-110">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="bc88b-110">Open the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc88b-111">Si no ve el panel Propiedades, haga clic en la pestaña **Ver** y, a continuación, active la casilla **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="bc88b-111">If you do not see the Properties pane, click the **View** tab and then select the **Properties** checkbox.</span></span>  
  
3.  <span data-ttu-id="bc88b-112">En la propiedad **punteros** , haga clic en el botón (...).</span><span class="sxs-lookup"><span data-stu-id="bc88b-112">In the **Pointers** property, click the (...) button.</span></span> <span data-ttu-id="bc88b-113">Se abre el Editor de la colección de punteros.</span><span class="sxs-lookup"><span data-stu-id="bc88b-113">The Pointer Collection Editor opens.</span></span>  
  
4.  <span data-ttu-id="bc88b-114">Establezca la propiedad **SnappingEnabled** en `True` .</span><span class="sxs-lookup"><span data-stu-id="bc88b-114">Set the **SnappingEnabled** property to `True`.</span></span>  
  
5.  <span data-ttu-id="bc88b-115">Establezca **SnappingInterval** en un valor que represente el intervalo de ajuste.</span><span class="sxs-lookup"><span data-stu-id="bc88b-115">Set the **SnappingInterval** to a value that represents the snapping interval.</span></span> <span data-ttu-id="bc88b-116">El puntero se ajustará al múltiplo de redondeo más cercano al valor que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="bc88b-116">The pointer will be snapped to the nearest round multiple of the value that you have specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc88b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc88b-117">See Also</span></span>  
 <span data-ttu-id="bc88b-118">[Aplicar formato a las escalas de un medidor &#40;Generador de informes y SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc88b-118">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bc88b-119">[Aplicar formato a los punteros de un medidor &#40;Generador de informes y SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc88b-119">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bc88b-120">Medidores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc88b-120">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
