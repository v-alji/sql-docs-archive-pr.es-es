---
title: LineString | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- LineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: e50d0b86-8b31-4285-be71-ad05c7712cbd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 5a0f77959cfe4492eca6c38951ba2868452d41ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676968"
---
# <a name="linestring"></a><span data-ttu-id="a08e8-102">LineString</span><span class="sxs-lookup"><span data-stu-id="a08e8-102">LineString</span></span>
  <span data-ttu-id="a08e8-103">`LineString` es un objeto unidimensional que representa una secuencia de puntos y los segmentos de línea que los conectan.</span><span class="sxs-lookup"><span data-stu-id="a08e8-103">A `LineString` is a one-dimensional object representing a sequence of points and the line segments connecting them.</span></span>

## <a name="linestring-instances"></a><span data-ttu-id="a08e8-104">Instancias de LineString</span><span class="sxs-lookup"><span data-stu-id="a08e8-104">LineString Instances</span></span>
 <span data-ttu-id="a08e8-105">En la ilustración siguiente se muestran ejemplos de instancias de `LineString`.</span><span class="sxs-lookup"><span data-stu-id="a08e8-105">The illustration below shows examples of `LineString` instances.</span></span>

 <span data-ttu-id="a08e8-106">![Ejemplos de instancias de LineString de geometry](../../database-engine/media/linestring.gif "Ejemplos de instancias de LineString de geometry")</span><span class="sxs-lookup"><span data-stu-id="a08e8-106">![Examples of geometry LineString instances](../../database-engine/media/linestring.gif "Examples of geometry LineString instances")</span></span>

 <span data-ttu-id="a08e8-107">Como se muestra en la ilustración:</span><span class="sxs-lookup"><span data-stu-id="a08e8-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="a08e8-108">La figura 1 es una instancia de `LineString` sencilla y sin cerrar.</span><span class="sxs-lookup"><span data-stu-id="a08e8-108">Figure 1 is a simple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="a08e8-109">La figura 2 es una instancia de `LineString` no sencilla y sin cerrar.</span><span class="sxs-lookup"><span data-stu-id="a08e8-109">Figure 2 is a nonsimple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="a08e8-110">La figura 3 es una instancia de `LineString` cerrada y sencilla; por ello, es un anillo.</span><span class="sxs-lookup"><span data-stu-id="a08e8-110">Figure 3 is a closed, simple `LineString` instance, and therefore is a ring.</span></span>

-   <span data-ttu-id="a08e8-111">La figura 4 es una instancia de `LineString` cerrada y no sencilla; por ello, no es un anillo.</span><span class="sxs-lookup"><span data-stu-id="a08e8-111">Figure 4 is a closed, nonsimple `LineString` instance, and therefore is not a ring.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="a08e8-112">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="a08e8-112">Accepted Instances</span></span>
 <span data-ttu-id="a08e8-113">Las instancias de `LineString` aceptadas se pueden especificar en una variable geometry, pero puede que no sean instancias de `LineString` válidas.</span><span class="sxs-lookup"><span data-stu-id="a08e8-113">Accepted `LineString` instances can be input into a geometry variable, but they may not be valid `LineString` instances.</span></span> <span data-ttu-id="a08e8-114">Los siguientes criterios se deben cumplir para que una instancia de `LineString` sea aceptada.</span><span class="sxs-lookup"><span data-stu-id="a08e8-114">The following criteria must be met for a `LineString` instance to be accepted.</span></span> <span data-ttu-id="a08e8-115">La instancia de estar formada como mínimo por dos puntos o debe estar vacía.</span><span class="sxs-lookup"><span data-stu-id="a08e8-115">The instance must be formed of at least two points or it must be empty.</span></span> <span data-ttu-id="a08e8-116">Se aceptan las siguientes instancias de LineString.</span><span class="sxs-lookup"><span data-stu-id="a08e8-116">The following LineString instances are accepted.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING EMPTY';
DECLARE @g2 geometry = 'LINESTRING(1 1,2 3,4 8, -6 3)';
DECLARE @g3 geometry = 'LINESTRING(1 1, 1 1)';
```

 <span data-ttu-id="a08e8-117">`@g3` muestra que se puede aceptar una instancia de `LineString`, pero no es válida.</span><span class="sxs-lookup"><span data-stu-id="a08e8-117">`@g3` shows that a `LineString` instance can be accepted, but not valid.</span></span>

 <span data-ttu-id="a08e8-118">No se acepta la siguiente instancia de `LineString`.</span><span class="sxs-lookup"><span data-stu-id="a08e8-118">The following `LineString` instance is not accepted.</span></span> <span data-ttu-id="a08e8-119">Producirá una `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="a08e8-119">It will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'LINESTRING(1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="a08e8-120">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="a08e8-120">Valid Instances</span></span>
 <span data-ttu-id="a08e8-121">Para que una instancia de `LineString` sea válida debe cumplir los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="a08e8-121">For a `LineString` instance to be valid it must meet the following criteria.</span></span>

1.  <span data-ttu-id="a08e8-122">La instancia de `LineString` debe ser aceptada.</span><span class="sxs-lookup"><span data-stu-id="a08e8-122">The `LineString` instance must be accepted.</span></span>

2.  <span data-ttu-id="a08e8-123">Si una instancia de `LineString` no está vacía debe contener dos puntos distintos por lo menos.</span><span class="sxs-lookup"><span data-stu-id="a08e8-123">If a `LineString` instance is not empty then it must contain at least two distinct points.</span></span>

3.  <span data-ttu-id="a08e8-124">La instancia de `LineString` no se puede superponer sobre un intervalo de dos o más puntos consecutivos.</span><span class="sxs-lookup"><span data-stu-id="a08e8-124">The `LineString` instance cannot overlap itself over an interval of two or more consecutive points.</span></span>

 <span data-ttu-id="a08e8-125">Las siguientes instancias de `LineString` son válidas.</span><span class="sxs-lookup"><span data-stu-id="a08e8-125">The following `LineString` instances are valid.</span></span>

```
DECLARE @g1 geometry= 'LINESTRING EMPTY';
DECLARE @g2 geometry= 'LINESTRING(1 1, 3 3)';
DECLARE @g3 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0)';
DECLARE @g4 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();

```

 <span data-ttu-id="a08e8-126">Las siguientes instancias de `LineString` no son válidas.</span><span class="sxs-lookup"><span data-stu-id="a08e8-126">The following `LineString` instances are not valid.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING(1 4, 3 4, 2 4, 2 0)';
DECLARE @g2 geometry = 'LINESTRING(1 1, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

> [!WARNING]
>  <span data-ttu-id="a08e8-127">La detección de superposiciones de `LineString` se basa en los cálculos de coma flotante, que no son exactos.</span><span class="sxs-lookup"><span data-stu-id="a08e8-127">The detection of `LineString` overlaps is based on floating-point calculations, which are not exact.</span></span>

## <a name="examples"></a><span data-ttu-id="a08e8-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a08e8-128">Examples</span></span>
 <span data-ttu-id="a08e8-129">En el ejemplo siguiente se muestra cómo crear una instancia de `geometry``LineString` con tres puntos y un SRID de 0:</span><span class="sxs-lookup"><span data-stu-id="a08e8-129">The following example shows how to create a `geometry``LineString` instance with three points and an SRID of 0:</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1, 2 4, 3 9)', 0);
```

 <span data-ttu-id="a08e8-130">Cada punto de la instancia de `LineString` puede contener valores Z (elevación) y M (medida).</span><span class="sxs-lookup"><span data-stu-id="a08e8-130">Each point in the `LineString` instance may contain Z (elevation) and M (measure) values.</span></span> <span data-ttu-id="a08e8-131">Este ejemplo agrega valores M a la instancia de `LineString` creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="a08e8-131">This example adds M values to the `LineString` instance created in the example above.</span></span> <span data-ttu-id="a08e8-132">M y Z pueden ser valores nulos.</span><span class="sxs-lookup"><span data-stu-id="a08e8-132">M and Z can be null values.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1 NULL 0, 2 4 NULL 12.3, 3 9 NULL 24.5)', 0);
```

 <span data-ttu-id="a08e8-133">En el ejemplo siguiente se muestra cómo crear una instancia de `geometry LineString` con dos puntos que son iguales.</span><span class="sxs-lookup"><span data-stu-id="a08e8-133">The following example shows how to create a `geometry LineString` instance with two points that are the same.</span></span> <span data-ttu-id="a08e8-134">Una llamada a `IsValid` indica que la instancia de `LineString` no es válida y una llamada a `MakeValid` convertirá la instancia de `LineString` en un `Point`.</span><span class="sxs-lookup"><span data-stu-id="a08e8-134">A call to `IsValid` indicates that the `LineString` instance is not valid and a call to `MakeValid` will convert the `LineString` instance into a `Point`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::STGeomFromText('LINESTRING(1 3, 1 3)',0);
IF @g.STIsValid() = 1
  BEGIN
     SELECT @g.ToString() + ' is a valid LineString.';  
  END
ELSE
  BEGIN
     SELECT @g.ToString() + ' is not a valid LineString.';
     SET @g = @g.MakeValid();
     SELECT @g.ToString() + ' is a valid Point.';  
  END

```

 <span data-ttu-id="a08e8-135">El fragmento de código anterior devolverá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a08e8-135">The above code snippet will return the following:</span></span>

```
LINESTRING(1 3, 1 3) is not a valid LineString
POINT(1 3) is a valid Point.
```

## <a name="see-also"></a><span data-ttu-id="a08e8-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a08e8-136">See Also</span></span>
 <span data-ttu-id="a08e8-137">[STLength &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;tipo](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) de datos Geometry&#41;[STEndpoint &#40;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) tipo de datos Geometry&#41;[STPointN &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) STNumPoints &#40;tipo de datos [Geometry](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [&#41;STIsRing &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;tipo de datos Geometry](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)&#41;[datos espaciales](../spatial/spatial-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a08e8-137">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


