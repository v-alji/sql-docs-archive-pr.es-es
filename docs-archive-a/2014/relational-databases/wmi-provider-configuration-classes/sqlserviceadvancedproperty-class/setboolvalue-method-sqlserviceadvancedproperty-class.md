---
title: Establecer puntos de interrupción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.setbreakpoints.f1
helpviewer_keywords:
- Set Breakpoints dialog box
ms.assetid: 876e61b7-875c-43f4-bbce-d7eeb90f6730
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8115fcd845ee5ff415d13aa4fe36230234e33ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748701"
---
# <a name="set-breakpoints"></a>Establecer puntos de interrupción
  Utilice el cuadro de diálogo **Establecer puntos de interrupción** para especificar los eventos en los que se deben habilitar puntos de interrupción y para controlar el comportamiento del punto de interrupción.  
  
## <a name="options"></a>Opciones  
 **Enabled**  
 Seleccione esta opción para habilitar un punto de interrupción en un evento.  
  
 **Break Condition**  
 Vea una lista de los eventos disponibles en los que se establecen puntos de interrupción.  
  
 **Hit Count Type**  
 Especifique el momento en el que el punto de interrupción surte efecto.  
  
|Value|Descripción|  
|-----------|-----------------|  
|**Siempre**|La ejecución se suspende siempre cuando se alcanza el punto de interrupción.|  
|**Número de llamadas igual a**|La ejecución se suspende cuando el número de veces que ha ocurrido el punto de interrupción es igual al número de llamadas.|  
|**Recuento de visitas mayor que o igual a**|La ejecución se suspende cuando el número de veces que ha ocurrido el punto de interrupción es igual a o mayor que el número de llamadas.|  
|**Múltiplo del número de llamadas**|La ejecución se suspende cuando se produce un múltiplo de número de llamadas. Por ejemplo, si establece esta opción en 5, la ejecución se suspende cada cinco veces.|  
  
 **Número de llamadas**  
 Especifique el número de visitas en el que se desencadena una interrupción. Esta opción no está disponible si la interrupción está siempre activa.  
  
## <a name="see-also"></a>Consulte también  
 [Depurar el flujo de control](../../../integration-services/troubleshooting/debugging-control-flow.md)  
  
  
