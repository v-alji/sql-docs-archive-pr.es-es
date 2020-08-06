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
# <a name="error-handling-mdx"></a><span data-ttu-id="10be1-102">Control de errores (MDX)</span><span class="sxs-lookup"><span data-stu-id="10be1-102">Error Handling (MDX)</span></span>
  <span data-ttu-id="10be1-103">Todos los cubos pueden controlar la forma en que se administran los errores de los scripts de expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="10be1-103">Each cube can control how errors within a Multidimensional Expressions (MDX) script are handled.</span></span> <span data-ttu-id="10be1-104">El control de errores se realiza mediante el enumerador `ScriptErrorHandlingMode`.</span><span class="sxs-lookup"><span data-stu-id="10be1-104">Error handling is done through the `ScriptErrorHandlingMode` enumerator.</span></span> <span data-ttu-id="10be1-105">Los valores posibles que admite este enumerador son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="10be1-105">The possible values for this enumerator are:</span></span>  
  
 `IgnoreNone`  
 <span data-ttu-id="10be1-106">Hace que el servidor genere un error cuando [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] encuentra un error en el script MDX.</span><span class="sxs-lookup"><span data-stu-id="10be1-106">Causes the server to raise an error when [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] finds any error in the MDX script.</span></span>  
  
 `IgnoreAll`  
 <span data-ttu-id="10be1-107">Hace que el servidor omita todos los comandos del script MDX que contengan un error, incluidos los errores de sintaxis, de resolución de nombres y otros.</span><span class="sxs-lookup"><span data-stu-id="10be1-107">Causes the server to ignore all commands in the MDX script that contain an error, including syntax errors, name resolution errors, and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10be1-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10be1-108">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
