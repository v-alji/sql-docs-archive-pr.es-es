---
title: MSSQLSERVER_15599 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 15f1b3eb6d97837f1c1c4a9944535cade5b31300
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675939"
---
# <a name="mssqlserver_15599"></a>MSSQLSERVER_15599
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre de producto|SQL Server|  
|Id. de evento|15599|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|SEC_LOCAL_TEMP_AUDIT_PERMISSIONS|  
|Texto del mensaje|No se pueden establecer permisos ni auditoría y en objetos temporales locales.|  
  
## <a name="explanation"></a>Explicación  
 La auditoría y los permisos no tienen ningún efecto cuando se establecen en objetos locales o globales temporales. Las instrucciones no producen un error (las operaciones vuelven correctamente), pero no tienen ningún efecto.  
  
 Este comportamiento no ha cambiado, pero a partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], este mensaje informativo alerta al usuario.  
  
## <a name="user-action"></a>Acción del usuario  
 No es necesaria ninguna acción, pero considere la posibilidad de quitar las instrucciones que intentan establecer la auditoría o los permisos en objetos locales o globales temporales.  
  
  
