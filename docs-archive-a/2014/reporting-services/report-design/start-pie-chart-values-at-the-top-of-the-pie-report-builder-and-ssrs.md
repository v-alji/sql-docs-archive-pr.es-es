---
title: Iniciar los valores del gráfico circular desde la parte superior del gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0e6fb59-ca4e-4d70-97cb-0ad183da21d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed010eeaf3e4d581cce2f7242144c4f73ec2895b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662527"
---
# <a name="start-pie-chart-values-at-the-top-of-the-pie-report-builder-and-ssrs"></a><span data-ttu-id="2d411-102">Iniciar los valores del gráfico circular desde la parte superior del gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="2d411-102">Start Pie Chart Values at the Top of the Pie (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2d411-103">De forma predeterminada en los gráficos circulares, el primer valor del conjunto de datos se inicia en 90 grados desde la parte superior del círculo.</span><span class="sxs-lookup"><span data-stu-id="2d411-103">By default in pie charts, the first value in the dataset starts at 90 degrees from the top of the pie.</span></span> <span data-ttu-id="2d411-104">Puede preferir que el primer valor se inicie desde arriba.</span><span class="sxs-lookup"><span data-stu-id="2d411-104">You may prefer that the first value start from the top.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-start-the-pie-chart-at-the-top-of-the-pie"></a><span data-ttu-id="2d411-105">Iniciar el gráfico circular desde la parte superior del círculo</span><span class="sxs-lookup"><span data-stu-id="2d411-105">To Start the Pie Chart at the Top of the Pie</span></span>  
  
1.  <span data-ttu-id="2d411-106">Haga clic en el círculo.</span><span class="sxs-lookup"><span data-stu-id="2d411-106">Click the pie itself.</span></span>  
  
2.  <span data-ttu-id="2d411-107">Si el panel **Propiedades** no está abierto, en la pestaña **Ver** haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2d411-107">If the **Properties** pane is not open, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2d411-108">En el panel **propiedades** , en **atributos personalizados**, cambie **PieStartAngle** de **0** a **270**.</span><span class="sxs-lookup"><span data-stu-id="2d411-108">In the **Properties** pane, under **Custom Attributes**, change **PieStartAngle** from **0** to **270**.</span></span>  
  
4.  <span data-ttu-id="2d411-109">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="2d411-109">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="2d411-110">El primer valor se inicia ahora en la parte superior del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="2d411-110">The first value now starts at the top of the pie chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d411-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d411-111">See Also</span></span>  
 <span data-ttu-id="2d411-112">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2d411-112">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2d411-113">Gráficos circulares &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2d411-113">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
