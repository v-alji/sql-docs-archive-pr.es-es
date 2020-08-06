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
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a>Establecer un intervalo de ajuste en un medidor (Generador de informes y SSRS)
  Un intervalo de ajuste define el múltiplo al que se redondean los valores. De forma predeterminada, el medidor señala el valor exacto del campo que se ha especificado en el panel de datos. Sin embargo, puede que desee redondear el valor exacto hacia arriba o hacia abajo para que el puntero se ajuste a un intervalo preestablecido. Por ejemplo, si el valor del medidor es de 34,2 y especifica un intervalo de ajuste de 5, el puntero del medidor señalará 3,5. Si el valor del medidor es de 31,2 y especifica un intervalo de ajuste de 5, el puntero del medidor señalará 30.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a>Para establecer un intervalo de ajuste en un medidor  
  
1.  Haga clic en cualquier lugar en los números del medidor para resaltar la escala.  
  
2.  Abra el panel de propiedades.  
  
    > [!NOTE]  
    >  Si no ve el panel Propiedades, haga clic en la pestaña **Ver** y, a continuación, active la casilla **propiedades** .  
  
3.  En la propiedad **punteros** , haga clic en el botón (...). Se abre el Editor de la colección de punteros.  
  
4.  Establezca la propiedad **SnappingEnabled** en `True` .  
  
5.  Establezca **SnappingInterval** en un valor que represente el intervalo de ajuste. El puntero se ajustará al múltiplo de redondeo más cercano al valor que ha especificado.  
  
## <a name="see-also"></a>Consulte también  
 [Aplicar formato a las escalas de un medidor &#40;Generador de informes y SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md)   
 [Aplicar formato a los punteros de un medidor &#40;Generador de informes y SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md)   
 [Medidores &#40;Generador de informes y SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md)  
  
  
