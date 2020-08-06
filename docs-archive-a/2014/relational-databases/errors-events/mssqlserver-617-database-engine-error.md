---
title: MSSQLSERVER_617 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88e9feb7c3ac5d8cf646d2243319b2b160b7757e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746997"
---
# <a name="mssqlserver_617"></a>MSSQLSERVER_617
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre de producto|SQL Server|  
|Id. de evento|617|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|NODESHASH|  
|Texto del mensaje|No se encontró el descriptor del id. de objeto %ld del id. de base de datos %d en la tabla hash al intentar deshacer el hash. Falta una entrada en una tabla de trabajo. Vuelva a ejecutar la consulta. Si hay un cursor en el proceso, ciérrelo y vuelva a abrirlo.|  
  
## <a name="explanation"></a>Explicación  
 SQL Server no puede encontrar la tabla de trabajo para una entrada concreta.  
  
## <a name="user-action"></a>Acción del usuario  
  
1.  Si hay un cursor en el proceso, ciérrelo y vuelve a abrirlo.  
  
2.  Ejecute de nuevo la consulta.  
  
  
