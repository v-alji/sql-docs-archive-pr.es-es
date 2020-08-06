---
title: Algunas réplicas de disponibilidad están desconectadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bb6535b513770b9b4718a0e8372c0a5bc3cba84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673281"
---
# <a name="some-availability-replicas-are-disconnected"></a>Algunas réplicas de disponibilidad están desconectadas
    
## <a name="introduction"></a>Introducción  
  
|||  
|-|-|  
|**Nombre de directiva**|Estado de conexión de las réplicas de disponibilidad|  
|**Problema**|Algunas réplicas de disponibilidad están desconectadas.|  
|**Categoría**|**Warning (ADVERTENCIA)**|  
|**Faceta**|grupo de disponibilidad|  
  
## <a name="description"></a>Descripción  
 Esta directiva acumula el estado de todas las réplicas de disponibilidad y comprueba las que están en estado DISCONNECTED. La directiva está en mal estado cuando cualquier réplica de disponibilidad está en estado DISCONNECTED. De lo contrario, la directiva está en un estado correcto.  
  
> [!NOTE]  
>   Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [Algunas réplicas de disponibilidad están desconectadas](https://go.microsoft.com/fwlink/p/?LinkId=220855) en TechNet Wiki.  
  
## <a name="possible-causes"></a>Causas posibles  
 En este grupo de disponibilidad, al menos una réplica secundaria no está conectada con la réplica principal. El estado de conexión es DISCONNECTED.  
  
## <a name="possible-solution"></a>Solución posible  
 Use el estado de directiva de la réplica de disponibilidad para buscar la réplica de disponibilidad que está en estado DISCONNECTED y, a continuación, resuelva el problema en la réplica de disponibilidad.  
  
## <a name="see-also"></a>Consulte también  
 [Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
