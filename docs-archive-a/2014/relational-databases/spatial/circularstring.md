---
title: CircularString | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 9fe06b03-d98c-4337-9f89-54da98f49f9f
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c701cdc2e8538a5b91093e17714fd9f6508d1c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663329"
---
# <a name="circularstring"></a><span data-ttu-id="799ca-102">CircularString</span><span class="sxs-lookup"><span data-stu-id="799ca-102">CircularString</span></span>
  <span data-ttu-id="799ca-103">Una `CircularString` es una colección con cero o más segmentos de arco circular continuos.</span><span class="sxs-lookup"><span data-stu-id="799ca-103">A `CircularString` is a collection of zero or more continuous circular arc segments.</span></span> <span data-ttu-id="799ca-104">Un segmento de arco circular es un segmento curvado definido por tres puntos en un plano bidimensional; el primer punto no puede ser igual que el tercero.</span><span class="sxs-lookup"><span data-stu-id="799ca-104">A circular arc segment is a curved segment defined by three points in a two-dimensional plane; the first point cannot be the same as the third point.</span></span> <span data-ttu-id="799ca-105">Si los tres puntos de un segmento de arco circular son colineales, el segmento de arco se trata como un segmento de línea.</span><span class="sxs-lookup"><span data-stu-id="799ca-105">If all three points of a circular arc segment are collinear, the arc segment is treated as a line segment.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="799ca-106">Para obtener una descripción detallada y ejemplos de las nuevas características espaciales introducidas en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , incluido el `CircularString` subtipo, descargue las notas del producto [nuevas características espaciales en SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="799ca-106">For a detailed description and examples of the new spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CircularString` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

## <a name="circularstring-instances"></a><span data-ttu-id="799ca-107">Instancias de CircularString</span><span class="sxs-lookup"><span data-stu-id="799ca-107">CircularString instances</span></span>
 <span data-ttu-id="799ca-108">En el dibujo siguiente se muestran instancias válidas de `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="799ca-108">The drawing below shows valid `CircularString` instances:</span></span>

 ![](../../database-engine/media/5ff17e34-b578-4873-9d33-79500940d0bc.png "5ff17e34-b578-4873-9d33-79500940d0bc")

### <a name="accepted-instances"></a><span data-ttu-id="799ca-109">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="799ca-109">Accepted instances</span></span>
 <span data-ttu-id="799ca-110">Una `CircularString` instancia de se acepta si está vacía o contiene un número impar de puntos, n, donde n > 1.</span><span class="sxs-lookup"><span data-stu-id="799ca-110">A `CircularString` instance is accepted if it is either empty or contains an odd number of points, n, where n > 1.</span></span> <span data-ttu-id="799ca-111">Se aceptan las siguientes instancias de `CircularString`.</span><span class="sxs-lookup"><span data-stu-id="799ca-111">The following `CircularString` instances are accepted.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 2 0, 1 1)';
```

 <span data-ttu-id="799ca-112">`@g3` muestra que la instancia de `CircularString` se puede aceptar, pero no es válida.</span><span class="sxs-lookup"><span data-stu-id="799ca-112">`@g3` shows that `CircularString` instance may be accepted, but not valid.</span></span> <span data-ttu-id="799ca-113">La siguiente declaración de instancia de CircularString no se acepta.</span><span class="sxs-lookup"><span data-stu-id="799ca-113">The following CircularString instance declaration is not accepted.</span></span> <span data-ttu-id="799ca-114">Esta declaración inicia una excepción `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="799ca-114">This declaration throws a `System.FormatException`.</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="799ca-115">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="799ca-115">Valid instances</span></span>
 <span data-ttu-id="799ca-116">Una instancia de `CircularString` válida debe estar vacía o tener los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="799ca-116">A valid `CircularString` instance must be empty or have the following attributes:</span></span>

-   <span data-ttu-id="799ca-117">Debe contener al menos un segmento de arco circular (es decir, con un mínimo de tres puntos).</span><span class="sxs-lookup"><span data-stu-id="799ca-117">It must contain at least one circular arc segment (that is, have a minimum of three points).</span></span>

-   <span data-ttu-id="799ca-118">El último extremo de cada segmento de arco circular de la secuencia, salvo el último segmento, debe ser el primer extremo del siguiente segmento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="799ca-118">The last endpoint for each circular arc segment in the sequence, except for the last segment, must be the first endpoint for the next segment in the sequence.</span></span>

-   <span data-ttu-id="799ca-119">Debe tener un número impar de puntos.</span><span class="sxs-lookup"><span data-stu-id="799ca-119">It must have an odd number of points.</span></span>

-   <span data-ttu-id="799ca-120">No se puede superponer sobre un intervalo.</span><span class="sxs-lookup"><span data-stu-id="799ca-120">It cannot overlap itself over an interval.</span></span>

-   <span data-ttu-id="799ca-121">Aunque las instancias de `CircularString` pueden contener segmentos de línea, dichos segmentos deben estar definidos por tres puntos colineales.</span><span class="sxs-lookup"><span data-stu-id="799ca-121">Although `CircularString` instances may contain line segments, these line segments must be defined by three collinear points.</span></span>

 <span data-ttu-id="799ca-122">En el siguiente ejemplo se muestran instancias válidas de `CircularString`.</span><span class="sxs-lookup"><span data-stu-id="799ca-122">The following example shows valid `CircularString` instances.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1, 0 1)';
DECLARE @g4 geometry = 'CIRCULARSTRING(1 1, 2 2, 2 2)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(),@g4.STIsValid();
```

 <span data-ttu-id="799ca-123">Una instancia de `CircularString` debe contener al menos dos segmentos de arco circular para definir un círculo completo.</span><span class="sxs-lookup"><span data-stu-id="799ca-123">A `CircularString` instance must contain at least two circular arc segments to define a complete circle.</span></span> <span data-ttu-id="799ca-124">Una instancia de `CircularString` no puede utilizar solo un segmento de arco circular, por ejemplo (1 1, 3 1, 1 1), para definir un círculo completo.</span><span class="sxs-lookup"><span data-stu-id="799ca-124">A `CircularString` instance cannot use a single circular arc segment (such as (1 1, 3 1, 1 1)) to define a complete circle.</span></span> <span data-ttu-id="799ca-125">Utilice (1 1, 2 2, 3 1, 2 0, 1 1) para definir el círculo.</span><span class="sxs-lookup"><span data-stu-id="799ca-125">Use (1 1, 2 2, 3 1, 2 0, 1 1) to define the circle.</span></span>

 <span data-ttu-id="799ca-126">En el siguiente ejemplo se muestran instancias de CircularString no válidas.</span><span class="sxs-lookup"><span data-stu-id="799ca-126">The following example shows CircularString instances that are not valid.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING(1 1, 2 0, 1 1)';
DECLARE @g2 geometry = 'CIRCULARSTRING(0 0, 0 0, 0 0)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

### <a name="instances-with-collinear-points"></a><span data-ttu-id="799ca-127">Instancias con puntos colineales</span><span class="sxs-lookup"><span data-stu-id="799ca-127">Instances with collinear points</span></span>
 <span data-ttu-id="799ca-128">En los siguientes casos, un segmento de arco circular se tratará como un segmento de línea:</span><span class="sxs-lookup"><span data-stu-id="799ca-128">In the following cases a circular arc segment will be treated as a line segment:</span></span>

-   <span data-ttu-id="799ca-129">Cuando los tres puntos son colineales, por ejemplo (1 3, 4 4, 7 5).</span><span class="sxs-lookup"><span data-stu-id="799ca-129">When all three points are collinear (for example, (1 3, 4 4, 7 5)).</span></span>

-   <span data-ttu-id="799ca-130">Cuando los puntos primero y medio son el mismo, pero el tercer punto es diferente, por ejemplo (1 3, 1 3, 7 5).</span><span class="sxs-lookup"><span data-stu-id="799ca-130">When the first and middle point are the same, but the third point is different (for example, (1 3, 1 3, 7 5)).</span></span>

-   <span data-ttu-id="799ca-131">Cuando los puntos medio y último son el mismo, pero el primer punto es diferente, por ejemplo (1 3, 4 4, 4 4).</span><span class="sxs-lookup"><span data-stu-id="799ca-131">When the middle and last point are the same, but the first point is different (for example, (1 3, 4 4, 4 4)).</span></span>

## <a name="examples"></a><span data-ttu-id="799ca-132">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="799ca-132">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-circularstring"></a><span data-ttu-id="799ca-133">A.</span><span class="sxs-lookup"><span data-stu-id="799ca-133">A.</span></span> <span data-ttu-id="799ca-134">Crear instancias de una instancia de geometry con una CircularString vacía</span><span class="sxs-lookup"><span data-stu-id="799ca-134">Instantiating a Geometry Instance with an Empty CircularString</span></span>
 <span data-ttu-id="799ca-135">En este ejemplo se muestra cómo crear una instancia de `CircularString` vacía:</span><span class="sxs-lookup"><span data-stu-id="799ca-135">This example shows how to create an empty `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING EMPTY');
```

### <a name="b-instantiating-a-geometry-instance-using-a-circularstring-with-one-circular-arc-segment"></a><span data-ttu-id="799ca-136">B.</span><span class="sxs-lookup"><span data-stu-id="799ca-136">B.</span></span> <span data-ttu-id="799ca-137">Crear instancias de una instancia de geometry usando una CircularString con un segmento de arco circular</span><span class="sxs-lookup"><span data-stu-id="799ca-137">Instantiating a Geometry Instance Using a CircularString with One Circular Arc Segment</span></span>
 <span data-ttu-id="799ca-138">En el siguiente ejemplo se muestra cómo crear una instancia de `CircularString` con un único segmento de arco de circular (medio círculo):</span><span class="sxs-lookup"><span data-stu-id="799ca-138">The following example shows how to create a `CircularString` instance with a single circular arc segment (half-circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry:: STGeomFromText('CIRCULARSTRING(2 0, 1 1, 0 0)', 0);
SELECT @g.ToString();
```

### <a name="c-instantiating-a-geometry-instance-using-a-circularstring-with-multiple-circular-arc-segments"></a><span data-ttu-id="799ca-139">C.</span><span class="sxs-lookup"><span data-stu-id="799ca-139">C.</span></span> <span data-ttu-id="799ca-140">Crear instancias de una instancia de geometry usando una CircularString con varios segmentos de arco circular</span><span class="sxs-lookup"><span data-stu-id="799ca-140">Instantiating a Geometry Instance Using a CircularString with Multiple Circular Arc Segments</span></span>
 <span data-ttu-id="799ca-141">En el siguiente ejemplo se muestra cómo crear una instancia de `CircularString` con más de un segmento de arco circular (círculo completo):</span><span class="sxs-lookup"><span data-stu-id="799ca-141">The following example shows how to create a `CircularString` instance with more than one circular arc segment (full circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING(2 1, 1 2, 0 1, 1 0, 2 1)');
SELECT 'Circumference = ' + CAST(@g.STLength() AS NVARCHAR(10));  
```

 <span data-ttu-id="799ca-142">Esto genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="799ca-142">This produces the following output:</span></span>

```
Circumference = 6.28319
```

 <span data-ttu-id="799ca-143">Compare con el resultado obtenido cuando se utiliza `LineString` en lugar de `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="799ca-143">Compare the output when `LineString` is used instead of `CircularString`:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(2 1, 1 2, 0 1, 1 0, 2 1)', 0);
SELECT 'Perimeter = ' + CAST(@g.STLength() AS NVARCHAR(10));
```

 <span data-ttu-id="799ca-144">Esto genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="799ca-144">This produces the following output:</span></span>

```
Perimeter = 5.65685
```

 <span data-ttu-id="799ca-145">Observe que el valor del `CircularString` ejemplo es cercano a 2&#x03c0; (2 \* PI), que es la circunferencia real del círculo.</span><span class="sxs-lookup"><span data-stu-id="799ca-145">Notice that the value for the `CircularString` example is close to 2&#x03c0; (2 \* pi), which is the actual circumference of the circle.</span></span>

### <a name="d-declaring-and-instantiating-a-geometry-instance-with-a-circularstring-in-the-same-statement"></a><span data-ttu-id="799ca-146">D.</span><span class="sxs-lookup"><span data-stu-id="799ca-146">D.</span></span> <span data-ttu-id="799ca-147">Declarar y crear instancias de una instancia de geometry con una CircularString en la misma instrucción</span><span class="sxs-lookup"><span data-stu-id="799ca-147">Declaring and Instantiating a Geometry Instance with a CircularString in the Same Statement</span></span>
 <span data-ttu-id="799ca-148">Este fragmento de código muestra cómo declarar y crear instancias de una instancia de `geometry` con una `CircularString` en la misma instrucción:</span><span class="sxs-lookup"><span data-stu-id="799ca-148">This snippet shows how to declare and instantiate a `geometry` instance with a `CircularString` in the same statement:</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';
```

### <a name="e-instantiating-a-geography-instance-with-a-circularstring"></a><span data-ttu-id="799ca-149">E.</span><span class="sxs-lookup"><span data-stu-id="799ca-149">E.</span></span> <span data-ttu-id="799ca-150">Crear instancias de una instancia de geography con una CircularString</span><span class="sxs-lookup"><span data-stu-id="799ca-150">Instantiating a Geography Instance with a CircularString</span></span>
 <span data-ttu-id="799ca-151">En el siguiente ejemplo, se muestra cómo declarar y crear una instancia de `geography` con una `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="799ca-151">The following example shows how to declare and instantiate a `geography` instance with a `CircularString`:</span></span>

```sql
DECLARE @g geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';
```

### <a name="f-instantiating-a-geometry-instance-with-a-circularstring-that-is-a-straight-line"></a><span data-ttu-id="799ca-152">F.</span><span class="sxs-lookup"><span data-stu-id="799ca-152">F.</span></span> <span data-ttu-id="799ca-153">Crear instancias de una instancia de geometry con una CircularString que es una línea recta</span><span class="sxs-lookup"><span data-stu-id="799ca-153">Instantiating a Geometry Instance with a CircularString that is a Straight Line</span></span>
 <span data-ttu-id="799ca-154">En el siguiente ejemplo se muestra cómo crear una instancia de `CircularString` que es una línea recta:</span><span class="sxs-lookup"><span data-stu-id="799ca-154">The following example shows how to create a `CircularString` instance that is a straight line:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('CIRCULARSTRING(0 0, 1 2, 2 4)', 0);
```

## <a name="see-also"></a><span data-ttu-id="799ca-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="799ca-155">See Also</span></span>
 <span data-ttu-id="799ca-156">[Información general sobre tipos de datos espaciales](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;tipo de datos geography&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;tipo de datos Geometry](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)&#41;STIsValid &#40;tipo de datos [Geography](/sql/t-sql/spatial-geography/stisvalid-geography-data-type)&#41;STLength &#40;tipo de datos [Geometry&#41;STStartPoint](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) &#40;tipo de datos Geometry [&#41;STEndpoint &#40;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) tipo [de datos](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [Geometry&#41;STPointN](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [&#40;tipo de](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) datos [Geometry&#41;STNumPoints](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [&#40;tipo](linestring.md) [de datos Geometry](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [&#41;STIsRing](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)</span><span class="sxs-lookup"><span data-stu-id="799ca-156">[Spatial Data Types Overview](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span></span>


