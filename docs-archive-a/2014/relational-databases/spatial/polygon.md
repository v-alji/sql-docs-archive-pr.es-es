---
title: Polygon | Microsoft Docs
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry subtypes [SQL Server]
- Polygon geometry subtype [SQL Server]
ms.assetid: b6a21c3c-fdb8-4187-8229-1c488454fdfb
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 040bb8a2558cc57b1b99a3ce984bec3c8925bc0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676952"
---
# <a name="polygon"></a><span data-ttu-id="15f16-102">Polygon</span><span class="sxs-lookup"><span data-stu-id="15f16-102">Polygon</span></span>
  <span data-ttu-id="15f16-103">Un `Polygon` es una superficie bidimensional almacenada como una secuencia de puntos que definen un anillo delimitador exterior y cero o más anillos interiores.</span><span class="sxs-lookup"><span data-stu-id="15f16-103">A `Polygon` is a two-dimensional surface stored as a sequence of points defining an exterior bounding ring and zero or more interior rings.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="15f16-104">Instancias de Polygon</span><span class="sxs-lookup"><span data-stu-id="15f16-104">Polygon instances</span></span>
 <span data-ttu-id="15f16-105">Una instancia de `Polygon` se puede formar a partir de un anillo que tenga al menos tres puntos distintos.</span><span class="sxs-lookup"><span data-stu-id="15f16-105">A `Polygon` instance can be formed from a ring that has at least three distinct points.</span></span> <span data-ttu-id="15f16-106">Una instancia de `Polygon` también puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="15f16-106">A `Polygon` instance can also be empty.</span></span>

 <span data-ttu-id="15f16-107">Los límites de una instancia de `Polygon` los define su anillo exterior junto con los anillos interiores que tenga.</span><span class="sxs-lookup"><span data-stu-id="15f16-107">The exterior and any interior rings of a `Polygon` define its boundary.</span></span> <span data-ttu-id="15f16-108">El espacio encerrado dentro de los anillos define el interior de la instancia de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="15f16-108">The space within the rings defines the interior of the `Polygon`.</span></span>

 <span data-ttu-id="15f16-109">En la ilustración siguiente se muestran ejemplos de instancias de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="15f16-109">The illustration below shows examples of `Polygon` instances.</span></span>

 <span data-ttu-id="15f16-110">![Ejemplos de instancias Polygon de geometry](../../database-engine/media/polygon.gif "Ejemplos de instancias Polygon de geometry")</span><span class="sxs-lookup"><span data-stu-id="15f16-110">![Examples of geometry Polygon instances](../../database-engine/media/polygon.gif "Examples of geometry Polygon instances")</span></span>

 <span data-ttu-id="15f16-111">Como se muestra en la ilustración:</span><span class="sxs-lookup"><span data-stu-id="15f16-111">As shown in the illustration:</span></span>

1.  <span data-ttu-id="15f16-112">La figura 1 es una instancia de `Polygon` cuyo límite está definido mediante un anillo exterior.</span><span class="sxs-lookup"><span data-stu-id="15f16-112">Figure 1 is a `Polygon` instance whose boundary is defined by an exterior ring.</span></span>

2.  <span data-ttu-id="15f16-113">La figura 2 es una instancia de `Polygon` cuyo límite está definido mediante un anillo exterior y dos anillos interiores.</span><span class="sxs-lookup"><span data-stu-id="15f16-113">Figure 2 is a `Polygon` instance whose boundary is defined by an exterior ring and two interior rings.</span></span> <span data-ttu-id="15f16-114">El área situada dentro de los anillos interiores forma parte del exterior de la instancia de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="15f16-114">The area inside the interior rings is part of the exterior of the `Polygon` instance.</span></span>

3.  <span data-ttu-id="15f16-115">La figura 3 es una instancia de `Polygon` válida porque la intersección de sus anillos interiores se realiza en un solo punto tangente.</span><span class="sxs-lookup"><span data-stu-id="15f16-115">Figure 3 is a valid `Polygon` instance because its interior rings intersect at a single tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="15f16-116">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="15f16-116">Accepted instances</span></span>
 <span data-ttu-id="15f16-117">Las instancias aceptadas de `Polygon` son las instancias que pueden almacenarse en una variable de tipo `geometry` o `geography` sin generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="15f16-117">Accepted `Polygon` instances are instances that can be stored in a `geometry` or `geography` variable without throwing an exception.</span></span> <span data-ttu-id="15f16-118">Se aceptan las siguientes instancias de `Polygon`:</span><span class="sxs-lookup"><span data-stu-id="15f16-118">The following are accepted `Polygon` instances:</span></span>

-   <span data-ttu-id="15f16-119">Una instancia vacía de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="15f16-119">An Empty `Polygon` instance</span></span>

-   <span data-ttu-id="15f16-120">Una instancia de `Polygon` que tiene un anillo exterior aceptable y cero o más anillos interiores aceptables.</span><span class="sxs-lookup"><span data-stu-id="15f16-120">A `Polygon` instance that has an acceptable exterior ring and zero or more acceptable interior rings</span></span>

 <span data-ttu-id="15f16-121">Deben cumplirse necesariamente los criterios siguientes para que un anillo sea aceptable.</span><span class="sxs-lookup"><span data-stu-id="15f16-121">The following criteria are needed for a ring to be acceptable.</span></span>

-   <span data-ttu-id="15f16-122">La instancia de `LineString` debe ser aceptada.</span><span class="sxs-lookup"><span data-stu-id="15f16-122">The `LineString` instance must be accepted.</span></span>

-   <span data-ttu-id="15f16-123">La instancia de `LineString` debe tener al menos cuatro puntos.</span><span class="sxs-lookup"><span data-stu-id="15f16-123">The `LineString` instance must have at least four points.</span></span>

-   <span data-ttu-id="15f16-124">Los puntos inicial y final de la instancia de `LineString` deben ser el mismo.</span><span class="sxs-lookup"><span data-stu-id="15f16-124">The starting and ending points of the `LineString` instance must be the same.</span></span>

 <span data-ttu-id="15f16-125">El siguiente ejemplo muestra instancias aceptadas de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="15f16-125">The following example shows accepted `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON EMPTY';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 1))';
DECLARE @g3 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 3 3, 0 3, 0 0))';
DECLARE @g4 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(3 0, 6 0, 6 3, 3 3, 3 0))';
DECLARE @g5 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
```

 <span data-ttu-id="15f16-126">Como muestran `@g4` y `@g5`, una instancia aceptada de `Polygon` puede no ser una instancia de `Polygon` válida.</span><span class="sxs-lookup"><span data-stu-id="15f16-126">As `@g4` and `@g5` show an accepted `Polygon` instance may not be a valid `Polygon` instance.</span></span> <span data-ttu-id="15f16-127">`@g5` también muestra que una instancia de Polygon solo necesita contener un anillo con cuatro puntos cualquiera para que se acepte.</span><span class="sxs-lookup"><span data-stu-id="15f16-127">`@g5` also shows that a Polygon instance needs to only contain a ring with any four points to be accepted.</span></span>

 <span data-ttu-id="15f16-128">Los ejemplos siguientes generan una excepción `System.FormatException`, porque las instancias de `Polygon` no se aceptan.</span><span class="sxs-lookup"><span data-stu-id="15f16-128">The following examples throw a `System.FormatException` because the `Polygon` instances are not accepted.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((1 1, 3 3, 1 1))';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 5))';
```

 <span data-ttu-id="15f16-129">`@g1` no se acepta porque la instancia de `LineString` para el anillo exterior no contiene suficientes puntos.</span><span class="sxs-lookup"><span data-stu-id="15f16-129">`@g1` is not accepted because the `LineString` instance for the exterior ring does not contain enough points.</span></span> <span data-ttu-id="15f16-130">`@g2` no se acepta porque el punto inicial de la instancia de `LineString` del anillo exterior no es igual que el punto final.</span><span class="sxs-lookup"><span data-stu-id="15f16-130">`@g2` is not accepted because the starting point of the exterior ring `LineString` instance is not the same as the ending point.</span></span> <span data-ttu-id="15f16-131">En el ejemplo siguiente hay un anillo exterior aceptable, pero el anillo interior no lo es.</span><span class="sxs-lookup"><span data-stu-id="15f16-131">The following example has an acceptable exterior ring, but the interior ring is not acceptable.</span></span> <span data-ttu-id="15f16-132">También en este caso se genera una excepción `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="15f16-132">This also throws a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 0 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="15f16-133">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="15f16-133">Valid instances</span></span>
 <span data-ttu-id="15f16-134">Los anillos interiores de una instancia de `Polygon` pueden tocarse a sí mismos y unos con otros en puntos tangentes únicos, pero si dichos anillos se cruzan, la instancia de `Polygon` no es válida.</span><span class="sxs-lookup"><span data-stu-id="15f16-134">The interior rings of a `Polygon` can touch both themselves and each other at single tangent points, but if the interior rings of a `Polygon` cross, the instance is not valid.</span></span>

 <span data-ttu-id="15f16-135">En el siguiente ejemplo se muestran instancias válidas de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="15f16-135">The following example shows valid `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, -5 -10, -10 0))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="15f16-136">`@g3` es válido porque los dos anillos interiores se tocan en un mismo punto y no se cruzan.</span><span class="sxs-lookup"><span data-stu-id="15f16-136">`@g3` is valid because the two interior rings touch at a single point and do not cross each other.</span></span> <span data-ttu-id="15f16-137">El siguiente ejemplo muestra instancias de `Polygon` no válidas.</span><span class="sxs-lookup"><span data-stu-id="15f16-137">The following example shows `Polygon` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (20 0, 0 10, 0 -20, 20 0))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (5 0, 1 5, 1 -5, 5 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, 0 -10, -10 0))';
DECLARE @g4 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 1 5, 0 -10, -10 0))';
DECLARE @g5 geometry = 'POLYGON((10 0, 0 10, 0 -10, 10 0), (-20 -20, -20 20, 20 20, 20 -20, -20 -20) )';
DECLARE @g6 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid(), @g5.STIsValid(), @g6.STIsValid();
```

 <span data-ttu-id="15f16-138">`@g1` no es válido porque el anillo interior toca el anillo exterior en dos lugares.</span><span class="sxs-lookup"><span data-stu-id="15f16-138">`@g1` is not valid because the inner ring touches the exterior ring in two places.</span></span> <span data-ttu-id="15f16-139">`@g2` no es válido porque el segundo anillo interior está dentro del interior del primer anillo interior.</span><span class="sxs-lookup"><span data-stu-id="15f16-139">`@g2` is not valid because the second inner ring in within the interior of the first inner ring.</span></span> <span data-ttu-id="15f16-140">`@g3` no es válido porque los dos anillos interiores se tocan en varios puntos consecutivos.</span><span class="sxs-lookup"><span data-stu-id="15f16-140">`@g3` is not valid because the two inner rings touch at multiple consecutive points.</span></span> <span data-ttu-id="15f16-141">`@g4` no es válido porque los interiores de los dos anillos interiores se superponen.</span><span class="sxs-lookup"><span data-stu-id="15f16-141">`@g4` is not valid because the interiors of the two inner rings overlap.</span></span> <span data-ttu-id="15f16-142">`@g5` no es válido porque el anillo exterior no es el primer anillo.</span><span class="sxs-lookup"><span data-stu-id="15f16-142">`@g5` is not valid because the exterior ring is not the first ring.</span></span> <span data-ttu-id="15f16-143">`@g6` no es válido porque el anillo no tiene al menos tres puntos distintos.</span><span class="sxs-lookup"><span data-stu-id="15f16-143">`@g6` is not valid because the ring does not have at least three distinct points.</span></span>

## <a name="examples"></a><span data-ttu-id="15f16-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="15f16-144">Examples</span></span>
 <span data-ttu-id="15f16-145">El ejemplo siguiente crea una instancia sencilla de `geometry``Polygon` con un hueco y un SRID de 10.</span><span class="sxs-lookup"><span data-stu-id="15f16-145">The following example creates a simple `geometry``Polygon` instance with a hole and SRID 10.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STPolyFromText('POLYGON((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1))', 10);
```

 <span data-ttu-id="15f16-146">Es posible especificar una instancia no válida y convertirla en una instancia de `geometry` válida.</span><span class="sxs-lookup"><span data-stu-id="15f16-146">Aninstance that is not valid may be entered and converted to a valid `geometry` instance.</span></span> <span data-ttu-id="15f16-147">En el ejemplo siguiente de `Polygon`, se superponen los anillos interiores y el exterior, y la instancia no es válida.</span><span class="sxs-lookup"><span data-stu-id="15f16-147">In the following example of a `Polygon`, the interior and exterior rings overlap and the instance is not valid.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('POLYGON((1 0, 0 1, 1 2, 2 1, 1 0), (2 0, 1 1, 2 2, 3 1, 2 0))');
```

 <span data-ttu-id="15f16-148">En el ejemplo siguiente, la instancia no válida se hace válida con `MakeValid()`.</span><span class="sxs-lookup"><span data-stu-id="15f16-148">In the following example, the invalid instance is made valid with `MakeValid()`.</span></span>

```
SET @g = @g.MakeValid();
SELECT @g.ToString();
```

 <span data-ttu-id="15f16-149">La instancia de `geometry` devuelta por el ejemplo anterior es de tipo `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="15f16-149">The `geometry` instance returned from the above example is a `MultiPolygon`.</span></span>

```
MULTIPOLYGON (((2 0, 3 1, 2 2, 1.5 1.5, 2 1, 1.5 0.5, 2 0)), ((1 0, 1.5 0.5, 1 1, 1.5 1.5, 1 2, 0 1, 1 0)))
```

 <span data-ttu-id="15f16-150">A continuación se muestra otro ejemplo de convertir una instancia no válida a una instancia de geometry válida.</span><span class="sxs-lookup"><span data-stu-id="15f16-150">Here is another example of converting an invalid instance to a valid geometry instance.</span></span> <span data-ttu-id="15f16-151">En el siguiente ejemplo la instancia de `Polygon` se ha creado con tres puntos que son exactamente iguales:</span><span class="sxs-lookup"><span data-stu-id="15f16-151">In the following example the `Polygon` instance has been created using three points that are exactly the same:</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('POLYGON((1 3, 1 3, 1 3, 1 3))');
SET @g = @g.MakeValid();
SELECT @g.ToString()
```

 <span data-ttu-id="15f16-152">La instancia de geometry devuelta es `Point(1 3)`.</span><span class="sxs-lookup"><span data-stu-id="15f16-152">The geometry instance returned above is a `Point(1 3)`.</span></span>  <span data-ttu-id="15f16-153">Si el objeto `Polygon` proporcionado es `POLYGON((1 3, 1 5, 1 3, 1 3))` , entonces `MakeValid()` devolverá `LINESTRING(1 3, 1 5)`.</span><span class="sxs-lookup"><span data-stu-id="15f16-153">If the `Polygon` given is `POLYGON((1 3, 1 5, 1 3, 1 3))` then `MakeValid()` would return `LINESTRING(1 3, 1 5)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="15f16-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15f16-154">See Also</span></span>
 <span data-ttu-id="15f16-155">[STArea &#40;tipo de datos de geometría&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) tipo de datos Geometry&#41;[STInteriorRingN &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) &#40;tipo de datos Geometry&#41;STPointOnSurface &#40;tipo de [datos Geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) los [datos espaciales](../spatial/spatial-data-sql-server.md) de [multipolígono](../spatial/polygon.md) &#40;SQL Server&#41;STIsValid &#40;[tipo de datos Geography](/sql/t-sql/spatial-geography/stisvalid-geography-data-type)&#41;[STIsValid &#40;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) tipo de datos Geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="15f16-155">[STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [MultiPolygon](../spatial/polygon.md) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span></span>


