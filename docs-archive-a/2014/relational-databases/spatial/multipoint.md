---
title: MultiPoint | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b741071b7986aceea4e49d4fde8293ef2c96fc2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676957"
---
# <a name="multipoint"></a><span data-ttu-id="1e6b2-102">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="1e6b2-102">MultiPoint</span></span>
  <span data-ttu-id="1e6b2-103">Un `MultiPoint` es una colección de cero o más puntos.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-103">A `MultiPoint` is a collection of zero or more points.</span></span> <span data-ttu-id="1e6b2-104">El límite de una instancia de `MultiPoint` está vacío.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-104">The boundary of a `MultiPoint` instance is empty.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1e6b2-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1e6b2-105">Examples</span></span>  
 <span data-ttu-id="1e6b2-106">El ejemplo siguiente crea una instancia de `geometry MultiPoint` con SRID 23 y dos puntos: un punto con las coordenadas (2, 3), un punto con las coordenadas (7, 8) y un valor de Z de 9,5.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-106">The following example creates a `geometry MultiPoint` instance with SRID 23 and two points: one point with the coordinates (2, 3), one point with the coordinates (7, 8), and a Z value of 9.5.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="1e6b2-107">Esta instancia de `MultiPoint` también se puede expresar usando `STMPointFromText()` como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-107">This `MultiPoint` instance can also be expressed using `STMPointFromText()` as shown below.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="1e6b2-108">El ejemplo siguiente usa el método `STGeometryN()` para recuperar una descripción del primer punto de la colección.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-108">The following example uses the method `STGeometryN()` to retrieve a description of the first point in the collection.</span></span>  
  
```  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e6b2-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e6b2-109">See Also</span></span>  
 <span data-ttu-id="1e6b2-110">[Elija](point.md) </span><span class="sxs-lookup"><span data-stu-id="1e6b2-110">[Point](point.md) </span></span>  
 [<span data-ttu-id="1e6b2-111">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e6b2-111">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
