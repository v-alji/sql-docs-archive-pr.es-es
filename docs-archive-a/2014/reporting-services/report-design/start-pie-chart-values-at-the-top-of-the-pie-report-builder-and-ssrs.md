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
# <a name="start-pie-chart-values-at-the-top-of-the-pie-report-builder-and-ssrs"></a>Iniciar los valores del gráfico circular desde la parte superior del gráfico (Generador de informes y SSRS)
  De forma predeterminada en los gráficos circulares, el primer valor del conjunto de datos se inicia en 90 grados desde la parte superior del círculo. Puede preferir que el primer valor se inicie desde arriba.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-start-the-pie-chart-at-the-top-of-the-pie"></a>Iniciar el gráfico circular desde la parte superior del círculo  
  
1.  Haga clic en el círculo.  
  
2.  Si el panel **Propiedades** no está abierto, en la pestaña **Ver** haga clic en **Propiedades**.  
  
3.  En el panel **propiedades** , en **atributos personalizados**, cambie **PieStartAngle** de **0** a **270**.  
  
4.  Haga clic en **Ejecutar** para obtener una vista previa del informe.  
  
 El primer valor se inicia ahora en la parte superior del gráfico circular.  
  
## <a name="see-also"></a>Consulte también  
 [Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md)   
 [Gráficos circulares &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md)  
  
  
