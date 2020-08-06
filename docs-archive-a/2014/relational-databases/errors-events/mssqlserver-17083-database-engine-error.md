---
title: MSSQLSERVER_17083 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17083 (Database Engine error)
ms.assetid: 6c83737d-0531-4fd9-88f6-2da5a150532d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 598cf9b0182178aa13a6d8b965ac10bedaaf5d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675930"
---
# <a name="mssqlserver_17083"></a>MSSQLSERVER_17083
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre de producto|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Id. de evento|17083|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|P3_HEKATON_NOT_ATOMIC|  
|Texto del mensaje|El cuerpo de un procedimiento almacenado compilado de forma nativa debe ser un bloque ATOMIC.|  
  
## <a name="explanation"></a>Explicación  
 El cuerpo de un procedimiento almacenado compilado de forma nativa no tenía un bloque ATOMIC.  
  
## <a name="user-action"></a>Acción del usuario  
 Un procedimiento almacenado compilado de forma nativa debe incluir un bloque ATOMIC. Por ejemplo:  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).  
  
## <a name="see-also"></a>Consulte también  
 [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
