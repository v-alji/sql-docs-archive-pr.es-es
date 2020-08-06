---
title: MultiLineString | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiLineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 95deeefe-d6c5-4a11-b347-379e4486e7b7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: fdd093d99d055df8e15fc22e3e570e6805e35d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676960"
---
# <a name="multilinestring"></a><span data-ttu-id="173d9-102">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="173d9-102">MultiLineString</span></span>
  <span data-ttu-id="173d9-103">Una `MultiLineString` es una colección de cero o más `geometry` instancias de o **geographyLineString** .</span><span class="sxs-lookup"><span data-stu-id="173d9-103">A `MultiLineString` is a collection of zero or more `geometry` or **geographyLineString** instances.</span></span>  
  
## <a name="multilinestring-instances"></a><span data-ttu-id="173d9-104">Instancias de MultiLineString</span><span class="sxs-lookup"><span data-stu-id="173d9-104">MultiLineString instances</span></span>  
 <span data-ttu-id="173d9-105">En la ilustración siguiente se muestran ejemplos de instancias de `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="173d9-105">The illustration below shows examples of `MultiLineString` instances.</span></span>  
  
 <span data-ttu-id="173d9-106">![Ejemplos de instancias MultiLineString de geometry](../../database-engine/media/multilinestring.gif "Ejemplos de instancias MultiLineString de geometry")</span><span class="sxs-lookup"><span data-stu-id="173d9-106">![Examples of geometry MultiLineString instances](../../database-engine/media/multilinestring.gif "Examples of geometry MultiLineString instances")</span></span>  
  
 <span data-ttu-id="173d9-107">Como se muestra en la ilustración:</span><span class="sxs-lookup"><span data-stu-id="173d9-107">As shown in the illustration:</span></span>  
  
-   <span data-ttu-id="173d9-108">La figura 1 es una `MultiLineString` instancia sencilla cuyo límite son los cuatro extremos de sus dos `LineString` elementos.</span><span class="sxs-lookup"><span data-stu-id="173d9-108">Figure 1 is a simple `MultiLineString` instance whose boundary is the four endpoints of its two `LineString` elements.</span></span>  
  
-   <span data-ttu-id="173d9-109">La figura 2 es una instancia sencilla de `MultiLineString` porque solo forman una intersección los extremos de los elementos `LineString`.</span><span class="sxs-lookup"><span data-stu-id="173d9-109">Figure 2 is a simple `MultiLineString` instance because only the endpoints of the `LineString` elements intersect.</span></span> <span data-ttu-id="173d9-110">El límite lo constituyen los dos extremos que no se superponen.</span><span class="sxs-lookup"><span data-stu-id="173d9-110">The boundary is the two non-overlapping endpoints.</span></span>  
  
-   <span data-ttu-id="173d9-111">La figura 3 es una instancia no sencilla de `MultiLineString` porque el interior de uno de sus elementos `LineString` forma parte de una intersección.</span><span class="sxs-lookup"><span data-stu-id="173d9-111">Figure 3 is a nonsimple `MultiLineString` instance because the interior of one of its `LineString` elements is intersected.</span></span> <span data-ttu-id="173d9-112">El límite de esta instancia de `MultiLineString` lo constituyen los cuatro extremos.</span><span class="sxs-lookup"><span data-stu-id="173d9-112">The boundary of this `MultiLineString` instance is the four endpoints.</span></span>  
  
-   <span data-ttu-id="173d9-113">La figura 4 es una instancia de `MultiLineString` no sencilla y sin cerrar.</span><span class="sxs-lookup"><span data-stu-id="173d9-113">Figure 4 is a nonsimple, nonclosed `MultiLineString` instance.</span></span>  
  
-   <span data-ttu-id="173d9-114">La figura 5 es una instancia de `MultiLineString` sencilla y sin cerrar.</span><span class="sxs-lookup"><span data-stu-id="173d9-114">Figure 5 is a simple, nonclosed `MultiLineString`.</span></span> <span data-ttu-id="173d9-115">No está cerrada porque sus `LineStrings` elementos no están cerrados.</span><span class="sxs-lookup"><span data-stu-id="173d9-115">It is not closed because its `LineStrings` elements are not closed.</span></span> <span data-ttu-id="173d9-116">Es sencilla porque ninguno de los interiores de ninguna de las instancias de `LineStrings` forma parte de una intersección.</span><span class="sxs-lookup"><span data-stu-id="173d9-116">It is simple because none of the interiors of any of the `LineStrings` instances intersect.</span></span>  
  
-   <span data-ttu-id="173d9-117">La figura 6 es una instancia de `MultiLineString` sencilla y cerrada.</span><span class="sxs-lookup"><span data-stu-id="173d9-117">Figure 6 is a simple, closed `MultiLineString` instance.</span></span> <span data-ttu-id="173d9-118">Está cerrada porque lo están todos sus elementos.</span><span class="sxs-lookup"><span data-stu-id="173d9-118">It is closed because all its elements are closed.</span></span> <span data-ttu-id="173d9-119">Es sencilla porque ninguno de sus elementos forma parte de una intersección con los interiores.</span><span class="sxs-lookup"><span data-stu-id="173d9-119">It is simple because none of its elements intersect at the interiors.</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="173d9-120">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="173d9-120">Accepted instances</span></span>  
 <span data-ttu-id="173d9-121">Para que se acepte una instancia de `MultiLineString`, debe estar vacío o estar formada solo por instancias de `LineString` aceptadas.</span><span class="sxs-lookup"><span data-stu-id="173d9-121">For a `MultiLineString` instance to be accepted it must either be empty or comprised of only `LineString` intances that are accepted.</span></span> <span data-ttu-id="173d9-122">Para obtener más información sobre `LineString` las instancias aceptadas, vea [LineString](../spatial/linestring.md).</span><span class="sxs-lookup"><span data-stu-id="173d9-122">For more information on accepted `LineString` instances, see [LineString](../spatial/linestring.md).</span></span> <span data-ttu-id="173d9-123">A continuación se enumeran ejemplos de instancias `MultiLineString` aceptadas.</span><span class="sxs-lookup"><span data-stu-id="173d9-123">The following are examples of accepted `MultiLineString` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
```  
  
 <span data-ttu-id="173d9-124">En el siguiente ejemplo se produce una excepción `System.FormatException` porque la segunda instancia de `LineString` no es válida.</span><span class="sxs-lookup"><span data-stu-id="173d9-124">The following example throws a `System.FormatException` because the second `LineString` instance is not valid.</span></span>  
  
```  
DECLARE @g geometry = 'MULTILINESTRING((1 1, 3 5),(-5 3))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="173d9-125">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="173d9-125">Valid instances</span></span>  
 <span data-ttu-id="173d9-126">Para que una instancia de `MultiLineString` sea válida debe cumplir los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="173d9-126">For a `MultiLineString` instance to be valid it must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="173d9-127">Todas las instancias que forman la instancia de `MultiLineString` deben ser instancias válidas de `LineString`.</span><span class="sxs-lookup"><span data-stu-id="173d9-127">All instances comprising the `MultiLineString` instance must be valid `LineString` instances.</span></span>  
  
2.  <span data-ttu-id="173d9-128">Dos de las instancias de `LineString` que forman la instancia de `MultiLineString` pueden superponerse durante un intervalo.</span><span class="sxs-lookup"><span data-stu-id="173d9-128">No two `LineString` instances comprising the `MultiLineString` instance may overlap over an interval.</span></span> <span data-ttu-id="173d9-129">Las instancias de `LineString` solo pueden formar una intersección o tocarse una a la otra o a otra instancia de `LineString` en un número finito de puntos.</span><span class="sxs-lookup"><span data-stu-id="173d9-129">The `LineString` instances can only intersect or touch themselves or other `LineString` instances at a finite number of points.</span></span>  
  
 <span data-ttu-id="173d9-130">En el ejemplo siguiente se muestran tres instancias válidas de `MultiLineString` y una instancia de `MultiLineString` que no es válida.</span><span class="sxs-lookup"><span data-stu-id="173d9-130">The following example shows three valid `MultiLineString` instances and one `MultiLineString` instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="173d9-131">`@g4` no es válida porque la segunda instancia de `LineString` se superpone a la primera instancia de `LineString` en un intervalo.</span><span class="sxs-lookup"><span data-stu-id="173d9-131">`@g4` is not valid because the second `LineString` instance overlaps the first `LineString` instance at an interval.</span></span> <span data-ttu-id="173d9-132">Se tocan en un número infinito de puntos.</span><span class="sxs-lookup"><span data-stu-id="173d9-132">They touch at an infinite number of points.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="173d9-133">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="173d9-133">Examples</span></span>  
 <span data-ttu-id="173d9-134">El ejemplo siguiente crea una instancia sencilla de `geometry``MultiLineString` que contiene dos elementos `LineString` con un SRID de 0.</span><span class="sxs-lookup"><span data-stu-id="173d9-134">The following example creates a simple `geometry``MultiLineString` instance containing two `LineString` elements with the SRID 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
```  
  
 <span data-ttu-id="173d9-135">Para crear instancias de esta instancia con otro SRID, utilice `STGeomFromText()` o `STMLineStringFromText()`.</span><span class="sxs-lookup"><span data-stu-id="173d9-135">To instantiate this instance with a different SRID, use `STGeomFromText()` or `STMLineStringFromText()`.</span></span> <span data-ttu-id="173d9-136">También puede utilizar `Parse()` y, a continuación, modificar el SRID, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="173d9-136">You can also use `Parse()` and then modify the SRID, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
SET @g.STSrid = 13;  
```  
  
## <a name="see-also"></a><span data-ttu-id="173d9-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="173d9-137">See Also</span></span>  
 <span data-ttu-id="173d9-138">[STLength &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="173d9-138">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span></span>  
 <span data-ttu-id="173d9-139">[STIsClosed &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="173d9-139">[STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span></span>  
 <span data-ttu-id="173d9-140">[LineString](../spatial/linestring.md) </span><span class="sxs-lookup"><span data-stu-id="173d9-140">[LineString](../spatial/linestring.md) </span></span>  
 [<span data-ttu-id="173d9-141">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="173d9-141">Spatial Data &#40;SQL Server&#41;</span></span>](../spatial/spatial-data-sql-server.md)  
  
  
