---
title: Solucionar problemas de gráficos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b931b50545ba2b8d7c4c06cc5c48d6415a05470a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746761"
---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a><span data-ttu-id="b6cac-102">Solucionar problemas de gráficos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="b6cac-102">Troubleshoot Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b6cac-103">Estos temas pueden resultar útiles al trabajar con gráficos.</span><span class="sxs-lookup"><span data-stu-id="b6cac-103">These issues can be helpful when working with charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a><span data-ttu-id="b6cac-104">¿Por qué mi gráfico cuenta, y no suma, los valores del eje de valores?</span><span class="sxs-lookup"><span data-stu-id="b6cac-104">Why does my chart count, not sum, the values on the value axis?</span></span>  
 <span data-ttu-id="b6cac-105">Para que se dibujen correctamente, la mayoría de los tipos de gráficos requieren valores numéricos a lo largo del eje de valores, que normalmente es el eje Y.</span><span class="sxs-lookup"><span data-stu-id="b6cac-105">Most chart types require numeric values along the value axis, which is typically the y-axis, in order to draw correctly.</span></span> <span data-ttu-id="b6cac-106">Si el tipo de datos del campo de valores es `String`, el gráfico no puede mostrar un valor numérico, aun cuando haya números en los campos.</span><span class="sxs-lookup"><span data-stu-id="b6cac-106">If the data type of your value field is `String`, the chart cannot display a numeric value, even if there are numerals in the fields.</span></span> <span data-ttu-id="b6cac-107">En su lugar, el gráfico muestra un recuento del número total de filas que contienen un valor en ese campo.</span><span class="sxs-lookup"><span data-stu-id="b6cac-107">Instead, the chart displays a count of the total number of rows that contain a value in that field.</span></span> <span data-ttu-id="b6cac-108">Para evitar este comportamiento, asegúrese de que los campos que usa para la serie de valores tienen tipos de datos numéricos, en lugar de cadenas que contienen números con formato.</span><span class="sxs-lookup"><span data-stu-id="b6cac-108">To avoid this behavior, make sure that the fields that you use for value series have numeric data types, as opposed to strings that contain formatted numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cac-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6cac-109">See Also</span></span>  
 [<span data-ttu-id="b6cac-110">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b6cac-110">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
