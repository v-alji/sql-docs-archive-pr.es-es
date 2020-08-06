---
title: Control de errores (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], exceptions
- exceptions [MDX]
ms.assetid: bc6ff0af-9fe6-44d6-bc3c-801d71ea41a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 357194b9f789fdeacfb65ce3c894d4747867eafb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675612"
---
# <a name="error-handling-mdx"></a>Control de errores (MDX)
  Todos los cubos pueden controlar la forma en que se administran los errores de los scripts de expresiones multidimensionales (MDX). El control de errores se realiza mediante el enumerador `ScriptErrorHandlingMode`. Los valores posibles que admite este enumerador son los siguientes:  
  
 `IgnoreNone`  
 Hace que el servidor genere un error cuando [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] encuentra un error en el script MDX.  
  
 `IgnoreAll`  
 Hace que el servidor omita todos los comandos del script MDX que contengan un error, incluidos los errores de sintaxis, de resolución de nombres y otros.  
  
## <a name="see-also"></a>Consulte también  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
