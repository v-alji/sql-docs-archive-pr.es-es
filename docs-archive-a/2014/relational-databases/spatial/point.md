---
title: Punto | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Point geometry subtype [SQL Server]
- geometry data type [SQL Server], spatial data
ms.assetid: 2a596ec4-8b2f-4962-bcb4-e5c8f77edad5
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4b12069d84e00738e3ddac8c414f33903f4f0999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676953"
---
# <a name="point"></a><span data-ttu-id="9c2f5-102">Punto</span><span class="sxs-lookup"><span data-stu-id="9c2f5-102">Point</span></span>
  <span data-ttu-id="9c2f5-103">En los datos espaciales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un `Point` es un objeto no dimensional que representa una ubicación única y contiene valores Z (elevación) y M (medida).</span><span class="sxs-lookup"><span data-stu-id="9c2f5-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data, a `Point` is a 0-dimensional object representing a single location and may contain Z (elevation) and M (measure) values.</span></span>  
  
## <a name="geography-data-type"></a><span data-ttu-id="9c2f5-104">Tipo de datos geography</span><span class="sxs-lookup"><span data-stu-id="9c2f5-104">Geography Data Type</span></span>  
 <span data-ttu-id="9c2f5-105">El tipo Point para el tipo de datos geography representa una ubicación única donde *Lat* representa la latitud y *Long* la longitud.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-105">The Point type for the geography data type represents a single location where *Lat* represents latitude and *Long* represents longitude.</span></span> <span data-ttu-id="9c2f5-106">Los valores de latitud y longitud se miden en grados.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-106">The values for latitude and longitude are measured in degrees.</span></span> <span data-ttu-id="9c2f5-107">Los valores de latitud siempre quedan en el intervalo [-90, 90] y, si se especifican valores fuera de este, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-107">Values for latitude always lie in the interval [-90, 90], and values that are inputted outside this range will throw an exception.</span></span> <span data-ttu-id="9c2f5-108">Los valores de longitud siempre quedan en el intervalo [-180, 180], y los especificados fuera de este se ajustan para entrar dentro.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-108">Values for longitude always lie in the interval (-180, 180], and values inputted outside this range are wrapped around to fit in this range.</span></span> <span data-ttu-id="9c2f5-109">Por ejemplo, si se especifica 190 para la longitud, se ajustará al valor -170.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-109">For example, if 190 is inputted for longitude, then it will be wrapped to the value -170.</span></span> <span data-ttu-id="9c2f5-110">*SRID* representa el identificador de referencia espacial de la instancia de **geography** que desea devolver.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-110">*SRID* represents the spatial reference ID of the **geography** instance that you wish to return.</span></span>  
  
## <a name="geometry-data-type"></a><span data-ttu-id="9c2f5-111">Tipo de datos geometry</span><span class="sxs-lookup"><span data-stu-id="9c2f5-111">Geometry Data Type</span></span>  
 <span data-ttu-id="9c2f5-112">El tipo point del tipo de datos geometry representa una sola ubicación donde *X* representa la coordenada X del punto que se va a generar e *Y* representa la coordenada Y del punto que se va a generar.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-112">The Point type for the geometry data type represents a single location where *X* represents the X-coordinate of the Point being generated and *Y* represents the Y-coordinate of the Point being generated.</span></span> <span data-ttu-id="9c2f5-113">*SRID* representa el identificador de referencia espacial de la instancia de **geometry** que desea devolver.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-113">*SRID* represents the spatial reference ID of the **geometry** instance that you wish to return.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9c2f5-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9c2f5-114">Examples</span></span>  
 <span data-ttu-id="9c2f5-115">El ejemplo siguiente crea una instancia de `geometry Point`que representa el punto (3, 4) con un SRID de 0.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-115">The following example creates a `geometry Point`instance representing the point (3, 4) with an SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT (3 4)', 0);  
```  
  
 <span data-ttu-id="9c2f5-116">El ejemplo siguiente crea una instancia de `geometry``Point` que representa el punto (3, 4) con un valor Z (elevación) de 7, un valor M (medida) de 2,5 y el SRID predeterminado de 0.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-116">The next example creates a `geometry``Point` instance representing the point (3, 4) with a Z (elevation) value of 7, an M (measure) value of 2.5, and the default SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 7 2.5)');  
```  
  
 <span data-ttu-id="9c2f5-117">El último ejemplo devuelve los valores X, Y, Z y M para la instancia de `geometry``Point` .</span><span class="sxs-lookup"><span data-stu-id="9c2f5-117">The final example returns the X, Y, Z, and M values for the `geometry``Point` instance.</span></span>  
  
```  
SELECT @g.STX;  
SELECT @g.STY;  
SELECT @g.Z;  
SELECT @g.M;  
```  
  
 <span data-ttu-id="9c2f5-118">Los valores Z y M se pueden especificar explícitamente como NULL, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9c2f5-118">Z and M values may be explicitly specified as NULL, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 NULL NULL)');  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c2f5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c2f5-119">See Also</span></span>  
 <span data-ttu-id="9c2f5-120">[Point](multipoint.md) </span><span class="sxs-lookup"><span data-stu-id="9c2f5-120">[MultiPoint](multipoint.md) </span></span>  
 <span data-ttu-id="9c2f5-121">[STX &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="9c2f5-121">[STX &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span></span>  
 <span data-ttu-id="9c2f5-122">[STY &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="9c2f5-122">[STY &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span></span>  
 [<span data-ttu-id="9c2f5-123">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9c2f5-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
