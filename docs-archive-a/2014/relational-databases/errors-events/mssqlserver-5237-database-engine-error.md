---
title: MSSQLSERVER_5237 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675881"
---
# <a name="mssqlserver_5237"></a>MSSQLSERVER_5237
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre de producto|SQL Server|  
|Id. de evento|5237|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE|  
|Texto del mensaje|Error de comprobación del conjunto de filas cruzadas de DBCC para el objeto 'NAME' (Id. de objeto O_ID) debido a un error de consulta interno.|  
  
## <a name="explanation"></a>Explicación  
 Un error interno ha provocado que DBCC no pueda ejecutar la consulta para comprobar las vistas indizadas.  
  
## <a name="user-action"></a>Acción del usuario  
 Vuelva a ejecutar el comando DBCC.  
  
  
