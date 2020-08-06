---
title: Propiedad State (clase SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- State Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a7456113d9ec4444507d1057892a65adf241992f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746813"
---
# <a name="state-property-sqlservice-class"></a>Propiedad State (clase SqlService)
  Obtiene o establece el estado actual del servicio.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
object  
.State [= value]  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 Objeto de la [clase SqlService](sqlservice-class.md) que representa el servicio.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 Valor uint32 que especifica el estado del servicio.  
  
 Los valores pueden ser alguno de los siguientes:  
  
 1  
 Detenido. El servicio está detenido.  
  
 2  
 Inicio pendiente. El servicio está a la espera de que se inicie.  
  
 3  
 Detención pendiente. El servicio está a la espera de que se detenga.  
  
 4  
 En ejecución. El servicio está ejecutándose.  
  
 5  
 Continuación pendiente. El servicio está a la espera de continuar.  
  
 6  
 Pausa pendiente. El servicio está a la espera de que se ponga en pausa.  
  
 7  
 En pausa. El servicio está en pausa.  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="see-also"></a>Consulte también  
 [Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
