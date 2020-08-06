---
title: Información general de los tipos de datos espaciales | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], understanding
- geography data type [SQL Server], spatial data
- planar spatial data [SQL Server], geometry data type
- spatial data types [SQL Server]
ms.assetid: 1615db50-69de-4778-8be6-4e058c00ccd4
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c0548d974e83bfe2b1e103d4458b17078fba8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747532"
---
# <a name="spatial-data-types-overview"></a><span data-ttu-id="a3d7f-102">Información general de los tipos de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="a3d7f-102">Spatial Data Types Overview</span></span>
  <span data-ttu-id="a3d7f-103">Hay dos tipos de datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-103">There are two types of spatial data.</span></span> <span data-ttu-id="a3d7f-104">El tipo de datos `geometry` admite datos planos o euclidianos (de tierra plana).</span><span class="sxs-lookup"><span data-stu-id="a3d7f-104">The `geometry` data type supports planar, or Euclidean (flat-earth), data.</span></span> <span data-ttu-id="a3d7f-105">El tipo de datos `geometry` se ajusta tanto a las características simples de Geospatial Consortium (OGC) para la especificación SQL versión 1.1.0 como a SQL MM (estándar ISO).</span><span class="sxs-lookup"><span data-stu-id="a3d7f-105">The `geometry` data type both conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0 and is compliant with SQL MM (ISO standard).</span></span>

 <span data-ttu-id="a3d7f-106">Además, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] admite el tipo de datos `geography`, que almacena datos elípticos (tierra redonda), como coordenadas de latitud y longitud GPS.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-106">In addition, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports the `geography` data type, which stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="a3d7f-107">Para obtener una descripción detallada y ejemplos de las características espaciales introducidas en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], incluidas las mejoras en los tipos de datos espaciales, descargue las notas del producto [Nuevas características espaciales de SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="a3d7f-107">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including enhancements to the spatial data types, download the white paper, [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

##  <a name="spatial-data-objects"></a><a name="objects"></a> <span data-ttu-id="a3d7f-108">Objetos de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="a3d7f-108">Spatial Data Objects</span></span>
 <span data-ttu-id="a3d7f-109">Los tipos de datos `geometry` y `geography` admiten dieciséis objetos de datos espaciales o tipos de instancia.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-109">The `geometry` and `geography` data types support sixteen spatial data objects, or instance types.</span></span> <span data-ttu-id="a3d7f-110">Pero solo se pueden *crear instancias*de once de estos tipos de instancia; puede crear y trabajar con estas instancias (o crear instancias de ellas) en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-110">However, only eleven of these instance types are *instantiable*; you can create and work with these instances (or instantiate them) in a database.</span></span> <span data-ttu-id="a3d7f-111">Estas instancias obtienen determinadas propiedades de sus tipos de datos primarios que los distinguen como `Points` , **LineStrings, CircularStrings**, `CompoundCurves` , `Polygons` `CurvePolygons` o como varias `geometry` `geography` instancias de o en `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="a3d7f-111">These instances derive certain properties from their parent data types that distinguish them as `Points`, **LineStrings, CircularStrings**, `CompoundCurves`, `Polygons`, `CurvePolygons` or as multiple `geometry` or `geography` instances in a `GeometryCollection`.</span></span> <span data-ttu-id="a3d7f-112">El tipo `Geography` tiene un tipo de instancia adicional, `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-112">`Geography` type has an additional instance type, `FullGlobe`.</span></span>

 <span data-ttu-id="a3d7f-113">La figura siguiente describe la jerarquía de `geometry` en la que se basan los tipos de datos `geometry` y `geography`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-113">The figure below depicts the `geometry` hierarchy upon which the `geometry` and `geography` data types are based.</span></span> <span data-ttu-id="a3d7f-114">Los tipos de instancias de `geometry` y `geography` se indican en azul.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-114">The instantiable types of `geometry` and `geography` are indicated in blue.</span></span>

 <span data-ttu-id="a3d7f-115">![Jerarquía del tipo geometry](../../database-engine/media/geom-hierarchy.gif "Jerarquía del tipo geometry")</span><span class="sxs-lookup"><span data-stu-id="a3d7f-115">![Hierarchy of the geometry type](../../database-engine/media/geom-hierarchy.gif "Hierarchy of the geometry type")</span></span>

 <span data-ttu-id="a3d7f-116">Como indica la ilustración, los diez tipos de instancias de `geometry` los `geography` tipos de datos y son `Point` , `MultiPoint` , `LineString` , `CircularString` , `MultiLineString` , `CompoundCurve` , `Polygon` ,, `CurvePolygon` `MultiPolygon` y `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="a3d7f-116">As the figure indicates, the ten instantiable types of the `geometry` and `geography` data types are `Point`, `MultiPoint`, `LineString`, `CircularString`, `MultiLineString`, `CompoundCurve`, `Polygon`, `CurvePolygon`, `MultiPolygon`, and `GeometryCollection`.</span></span> <span data-ttu-id="a3d7f-117">Existe un tipo adicional a partir del que pueden crearse instancias para el tipo de datos Geography: `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-117">There is one additional instantiable type for the geography data type: `FullGlobe`.</span></span> <span data-ttu-id="a3d7f-118">Los `geometry` `geography` tipos y pueden reconocer una instancia concreta siempre que sea una instancia bien formada, incluso si la instancia no está definida explícitamente.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-118">The `geometry` and `geography` types can recognize a specific instance as long as it is a well-formed instance, even if the instance is not defined explicitly.</span></span> <span data-ttu-id="a3d7f-119">Por ejemplo, si define una `Point` instancia explícitamente mediante el método STPointFromText (), `geometry` y `geography` reconoce la instancia como, siempre y `Point` cuando la entrada del método tenga el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-119">For example, if you define a `Point` instance explicitly using the STPointFromText() method, `geometry` and `geography` recognize the instance as a `Point`, as long as the method input is well-formed.</span></span> <span data-ttu-id="a3d7f-120">Si define la misma instancia mediante el método `STGeomFromText()`, los tipos de datos `geometry` y `geography` reconocen la instancia como `Point`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-120">If you define the same instance using the `STGeomFromText()` method, both the `geometry` and `geography` data types recognize the instance as a `Point`.</span></span>

 <span data-ttu-id="a3d7f-121">Los subtipos de los tipos Geometry y Geography se dividen en tipos simples y de colección.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-121">The subtypes for geometry and geography types are divided into simple and collection types.</span></span>  <span data-ttu-id="a3d7f-122">Algunos métodos como `STNumCurves()` funcionan solo con los tipos simples.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-122">Some methods like `STNumCurves()` work only with simple types.</span></span>

 <span data-ttu-id="a3d7f-123">Los tipos simples incluyen:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-123">Simple types include:</span></span>

-   [<span data-ttu-id="a3d7f-124">Point</span><span class="sxs-lookup"><span data-stu-id="a3d7f-124">Point</span></span>](../spatial/point.md)

-   [<span data-ttu-id="a3d7f-125">LineString</span><span class="sxs-lookup"><span data-stu-id="a3d7f-125">LineString</span></span>](../spatial/linestring.md)

-   [<span data-ttu-id="a3d7f-126">CircularString</span><span class="sxs-lookup"><span data-stu-id="a3d7f-126">CircularString</span></span>](../spatial/circularstring.md)

-   [<span data-ttu-id="a3d7f-127">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a3d7f-127">CompoundCurve</span></span>](../spatial/compoundcurve.md)

-   [<span data-ttu-id="a3d7f-128">Polygon</span><span class="sxs-lookup"><span data-stu-id="a3d7f-128">Polygon</span></span>](../spatial/polygon.md)

-   [<span data-ttu-id="a3d7f-129">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="a3d7f-129">CurvePolygon</span></span>](../spatial/curvepolygon.md)

 <span data-ttu-id="a3d7f-130">Los tipos de colección incluyen:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-130">Collection types include:</span></span>

-   [<span data-ttu-id="a3d7f-131">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="a3d7f-131">MultiPoint</span></span>](../spatial/multipoint.md)

-   [<span data-ttu-id="a3d7f-132">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="a3d7f-132">MultiLineString</span></span>](../spatial/multilinestring.md)

-   [<span data-ttu-id="a3d7f-133">MultiPolígono</span><span class="sxs-lookup"><span data-stu-id="a3d7f-133">MultiPolygon</span></span>](../spatial/multipolygon.md)

-   [<span data-ttu-id="a3d7f-134">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="a3d7f-134">GeometryCollection</span></span>](../spatial/geometrycollection.md)


##  <a name="differences-between-the-geometry-and-geography-data-types"></a><a name="differences"></a> <span data-ttu-id="a3d7f-135">Diferencias entre los tipos de datos geometry y geography</span><span class="sxs-lookup"><span data-stu-id="a3d7f-135">Differences Between the geometry and geography Data Types</span></span>
 <span data-ttu-id="a3d7f-136">Los dos tipos de datos espaciales se comportan a menudo de manera bastante similar pero hay algunas diferencias clave en la manera en la que los datos se almacenan y se manipulan.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-136">The two types of spatial data often behave quite similarly, but there are some key differences in how the data is stored and manipulated.</span></span>

### <a name="how-connecting-edges-are-defined"></a><span data-ttu-id="a3d7f-137">Definición de bordes de conexión</span><span class="sxs-lookup"><span data-stu-id="a3d7f-137">How connecting edges are defined</span></span>
 <span data-ttu-id="a3d7f-138">Los datos de definición para los tipos `LineString` y `Polygon` son solo los vértices.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-138">The defining data for `LineString` and `Polygon` types are vertices only.</span></span>  <span data-ttu-id="a3d7f-139">El borde de conexión entre dos vértices en un tipo Geometría es una línea recta.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-139">The connecting edge between two vertices in a geometry type is a straight line.</span></span>  <span data-ttu-id="a3d7f-140">Sin embargo, el borde de conexión entre dos vértices en un tipo de geografía es un arco elíptico grande corto entre los dos vértices.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-140">However, the connecting edge between two vertices in a geography type is a short great elliptic arc between the two vertices.</span></span>  <span data-ttu-id="a3d7f-141">Una elipse grande es la intersección del elipsoide con un plano por su centro y un arco elíptico grande es un segmento de arco de la elipse grande.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-141">A great ellipse is the intersection of the ellipsoid with a plane through its center and a great elliptic arc is an arc segment on the great ellipse.</span></span>

### <a name="how-circular-arc-segments-are-defined"></a><span data-ttu-id="a3d7f-142">Definición de los segmentos de arco circular</span><span class="sxs-lookup"><span data-stu-id="a3d7f-142">How circular arc segments are defined</span></span>
 <span data-ttu-id="a3d7f-143">Los segmentos de arco circular para los tipos Geometry se definen en el plano de coordenadas cartesianas XY (se ignoran los valores Z).</span><span class="sxs-lookup"><span data-stu-id="a3d7f-143">Circular arc segments for geometry types are defined on the XY Cartesian coordinate plane (Z values are ignored).</span></span> <span data-ttu-id="a3d7f-144">Los segmentos de arco circular para los tipos Geography se definen mediante segmentos de curva en una esfera de referencia.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-144">Circular arc segments for geography types are defined by curve segments on a reference sphere.</span></span> <span data-ttu-id="a3d7f-145">Los paralelos de la esfera de referencia se pueden definir mediante dos arcos circulares complementarios en los que los puntos de ambos arcos tienen un ángulo de latitud constante.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-145">Any parallel on the reference sphere can be defined by two complementary circular arcs where the points for both arcs have a constant latitude angle.</span></span>

### <a name="measurements-in-spatial-data-types"></a><span data-ttu-id="a3d7f-146">Medidas en tipos de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="a3d7f-146">Measurements in spatial data types</span></span>
 <span data-ttu-id="a3d7f-147">En el sistema plano, o de tierra plana, las medidas de distancias y las áreas se proporcionan en la misma unidad de medida que las coordenadas.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-147">In the planar, or flat-earth, system, measurements of distances and areas are given in the same unit of measurement as coordinates.</span></span> <span data-ttu-id="a3d7f-148">Usando el tipo de datos `geometry`, la distancia entre (2, 2) y (5, 6) es 5 unidades, independientemente de las unidades usadas.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-148">Using the `geometry` data type, the distance between (2, 2) and (5, 6) is 5 units, regardless of the units used.</span></span>

 <span data-ttu-id="a3d7f-149">En el sistema elíptico o de tierra redonda, las coordenadas se proporcionan en grados de latitud y longitud.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-149">In the ellipsoidal, or round-earth system, coordinates are given in degrees of latitude and longitude.</span></span> <span data-ttu-id="a3d7f-150">Sin embargo, las longitudes y las áreas normalmente se miden en metros y metros cuadrados, aunque la medida puede depender del identificador de referencia espacial (SRID) de la instancia de `geography`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-150">However, lengths and areas are usually measured in meters and square meters, though the measurement may depend on the spatial reference identifier (SRID) of the `geography` instance.</span></span> <span data-ttu-id="a3d7f-151">La unidad de medida más común para el tipo de datos `geography` es el metro.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-151">The most common unit of measurement for the `geography` data type is meters.</span></span>

### <a name="orientation-of-spatial-data"></a><span data-ttu-id="a3d7f-152">Orientación de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="a3d7f-152">Orientation of spatial data</span></span>
 <span data-ttu-id="a3d7f-153">En el sistema plano, la orientación de anillo de un polígono no es un factor importante.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-153">In the planar system, the ring orientation of a polygon is not an important factor.</span></span> <span data-ttu-id="a3d7f-154">Por ejemplo, un polígono descrito por ((0, 0), (10, 0), (0, 20), (0, 0)) es igual que un polígono descrito por ((0, 0), (0, 20), (10, 0), (0, 0)).</span><span class="sxs-lookup"><span data-stu-id="a3d7f-154">For example, a polygon described by ((0, 0), (10, 0), (0, 20), (0, 0)) is the same as a polygon described by ((0, 0), (0, 20), (10, 0), (0, 0)).</span></span> <span data-ttu-id="a3d7f-155">Las características simples de OGC para la especificación de SQL no dictan una ordenación de anillos y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no exige la ordenación de anillos.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-155">The OGC Simple Features for SQL Specification does not dictate a ring ordering, and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not enforce ring ordering.</span></span>

 <span data-ttu-id="a3d7f-156">En un sistema elíptico, un polígono no tiene ningún significado, o es ambiguo, sin una orientación.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-156">In an ellipsoidal system, a polygon has no meaning, or is ambiguous, without an orientation.</span></span> <span data-ttu-id="a3d7f-157">Por ejemplo, ¿un anillo alrededor del ecuador describe el hemisferio norte o el hemisferio sur?</span><span class="sxs-lookup"><span data-stu-id="a3d7f-157">For example, does a ring around the equator describe the northern or southern hemisphere?</span></span> <span data-ttu-id="a3d7f-158">Si usamos el tipo de datos `geography` para almacenar la instancia espacial, debemos especificar la orientación del anillo y describir con precisión la ubicación de la instancia.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-158">If we use the `geography` data type to store the spatial instance, we must specify the orientation of the ring and accurately describe the location of the instance.</span></span> <span data-ttu-id="a3d7f-159">El interior del polígono de un sistema elipsoidal se define mediante la regla de la mano izquierda.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-159">The interior of the polygon in an ellipsoidal system is defined by the left-hand rule.</span></span>

 <span data-ttu-id="a3d7f-160">Cuando el nivel de compatibilidad es 100 o inferior en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , el `geography` tipo de datos tiene las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-160">When the compatibility level is 100 or below in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] then the `geography` data type has the following restrictions:</span></span>

-   <span data-ttu-id="a3d7f-161">Cada instancia de `geography` debe ajustarse en un hemisferio único.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-161">Each `geography` instance must fit inside a single hemisphere.</span></span> <span data-ttu-id="a3d7f-162">No se puede almacenar ningún objeto espacial mayor que un hemisferio.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-162">No spatial objects larger than a hemisphere can be stored.</span></span>

-   <span data-ttu-id="a3d7f-163">Cualquier instancia de `geography` de una representación Open Geospatial Consortium (OGC) Well-Known Text (WKT) o Well-Known Binary (WKB) que genera un objeto mayor que un hemisferio inicia una `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-163">Any `geography` instance from an Open Geospatial Consortium (OGC) Well-Known Text (WKT) or Well-Known Binary (WKB) representation that produces an object larger than a hemisphere throws an `ArgumentException`.</span></span>

-   <span data-ttu-id="a3d7f-164">Los `geography` métodos de tipo de datos que requieren la entrada de dos `geography` instancias, como STIntersection (), STUnion (), STDifference () y STSymDifference (), devolverán NULL si los resultados de los métodos no caben en un hemisferio único.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-164">The `geography` data type methods that require the input of two `geography` instances, such as STIntersection(), STUnion(), STDifference(), and STSymDifference(), will return null if the results from the methods do not fit inside a single hemisphere.</span></span> <span data-ttu-id="a3d7f-165">STBuffer() también devolverá NULL si la salida supera un único hemisferio.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-165">STBuffer() will also return null if the output exceeds a single hemisphere.</span></span>

 <span data-ttu-id="a3d7f-166">En [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` es un tipo especial de Polygon que abarca el mundo entero.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` is a special type of Polygon that covers the entire globe.</span></span> <span data-ttu-id="a3d7f-167">`FullGlobe` tiene un área, pero no tiene bordes o vértices.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-167">`FullGlobe` has an area, but no borders or vertices.</span></span>

### <a name="outer-and-inner-rings-not-important-in-geography-data-type"></a><span data-ttu-id="a3d7f-168">Anillos externos e internos no importantes en el tipo de datos Geography</span><span class="sxs-lookup"><span data-stu-id="a3d7f-168">Outer and inner rings not important in geography data type</span></span>
 <span data-ttu-id="a3d7f-169">Las características simples de OGC para la especificación de SQL analizan los anillos externos y los anillos internos, pero esta distinción tiene poco sentido para el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` tipo de datos; se puede tomar cualquier anillo de un polígono como anillo externo.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-169">The OGC Simple Features for SQL Specification discusses outer rings and inner rings, but this distinction makes little sense for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` data type; any ring of a polygon can be taken to be the outer ring.</span></span>

 <span data-ttu-id="a3d7f-170">Para obtener más información acerca de las especificaciones de OGC, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-170">For more information on OGC specifications, see the following:</span></span>

-   [<span data-ttu-id="a3d7f-171">Especificaciones de OGC, Acceso a características simples, Parte 1 - Arquitectura común</span><span class="sxs-lookup"><span data-stu-id="a3d7f-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93627)

-   [<span data-ttu-id="a3d7f-172">Especificaciones de OGC, acceso a características simples, parte 2: opciones de SQL</span><span class="sxs-lookup"><span data-stu-id="a3d7f-172">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)


##  <a name="circular-arc-segments"></a><a name="circular"></a> <span data-ttu-id="a3d7f-173">Segmentos de arco circular</span><span class="sxs-lookup"><span data-stu-id="a3d7f-173">Circular Arc Segments</span></span>
 <span data-ttu-id="a3d7f-174">Tres tipos instanciables pueden tomar segmentos de arco circular: `CircularString`, `CompoundCurve` y `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-174">Three instantiable types can take circular arc segments: `CircularString`, `CompoundCurve`, and `CurvePolygon`.</span></span>  <span data-ttu-id="a3d7f-175">Un segmento de arco circular se define mediante tres puntos en un plano bidimensional y el tercer punto no puede ser igual que el primero.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-175">A circular arc segment is defined by three points in a two dimensional plane and the third point cannot be the same as the first point.</span></span>

 <span data-ttu-id="a3d7f-176">Las figuras A y B muestran segmentos de arco circular.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-176">Figures A and B show typical circular arc segments.</span></span> <span data-ttu-id="a3d7f-177">Observe que cada uno de los tres puntos pertenece al perímetro de un círculo.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-177">Note how each of the three points lie on the perimeter of a circle.</span></span>

 <span data-ttu-id="a3d7f-178">Las figuras C y D muestran cómo se puede definir el segmento de una línea como segmento de arco circular.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-178">Figures C and D show how a line segment can be defined as a circular arc segment.</span></span>  <span data-ttu-id="a3d7f-179">Observe que esos tres puntos continúan siendo necesarios para definir el segmento de arco circular a diferencia de un segmento de línea normal que se puede definir mediante dos puntos únicamente.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-179">Note that three points are still needed to define the circular arc segment unlike a regular line segment which can be defined by just two points.</span></span>

 <span data-ttu-id="a3d7f-180">Los métodos que funcionan en tipos de segmentos de arco circular usan segmentos de línea recta para aproximarse al arco circular. El número de segmentos de línea utilizado para aproximarse al arco dependerá de su longitud y curvatura. Los valores Z se pueden almacenar para cada uno de los tipos de segmentos de arco circular; sin embargo, los métodos no usarán los valores Z en sus cálculos.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-180">Methods operating on circular arc segment types use straight line segments to approximate the circular arc. The number of line segments used to approximate the arc will depend on the length and curvature of the arc. Z values can be stored for each of the circular arc segment types; however, methods will not use the Z values in their calculations.</span></span>

> [!NOTE]
>  <span data-ttu-id="a3d7f-181">Si se dan valores Z para los segmentos de arco circular, deben ser iguales para todos los puntos del segmento de arco circular para que se acepte como entrada.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-181">If Z values are given for circular arc segments then they must be the same for all points in the circular arc segment for it to be accepted for input.</span></span> <span data-ttu-id="a3d7f-182">Por ejemplo: se acepta `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` , pero no se acepta `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` .</span><span class="sxs-lookup"><span data-stu-id="a3d7f-182">For example: `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` is accepted, but `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` is not accepted.</span></span>

### <a name="linestring-and-circularstring-comparison"></a><span data-ttu-id="a3d7f-183">Comparación de LineString y CircularString</span><span class="sxs-lookup"><span data-stu-id="a3d7f-183">LineString and CircularString comparison</span></span>
 <span data-ttu-id="a3d7f-184">En el siguiente diagrama se muestran triángulos isósceles idénticos (el triángulo A usa segmentos de línea para definir el triángulo y el triángulo B, segmentos de arco circular):</span><span class="sxs-lookup"><span data-stu-id="a3d7f-184">The following diagram shows identical isosceles triangles (triangle A uses line segments to define the triangle and triangle B uses circular arc segments to defined the triangle):</span></span>

 ![](../../database-engine/media/7e382f76-59da-4b62-80dc-caf93e637c14.png "7e382f76-59da-4b62-80dc-caf93e637c14")

 <span data-ttu-id="a3d7f-185">En este ejemplo se muestra cómo almacenar los triángulos isósceles anteriores tanto con una instancia de `LineString` como con una instancia de `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-185">This example shows how to store the above isosceles triangles using both a `LineString` instance and `CircularString` instance:</span></span>

```sql
DECLARE @g1 geometry;
DECLARE @g2 geometry;
SET @g1 = geometry::STGeomFromText('LINESTRING(1 1, 5 1, 3 5, 1 1)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(1 1, 3 1, 5 1, 4 3, 3 5, 2 3, 1 1)', 0);
IF @g1.STIsValid() = 1 AND @g2.STIsValid() = 1
  BEGIN
      SELECT @g1.ToString(), @g2.ToString()
      SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length]
  END
```

 <span data-ttu-id="a3d7f-186">Tenga en cuenta que una instancia de `CircularString` requiere siete puntos para definir el triángulo, pero una instancia de `LineString` requiere solo cuatro puntos para definir el triángulo.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-186">Notice that a `CircularString` instance requires seven points to define the triangle, but a `LineString` instance requires only four points to define the triangle.</span></span> <span data-ttu-id="a3d7f-187">Esto se debe a que una instancia de `CircularString` almacena los segmentos de arco circular y no los de línea.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-187">The reason for this is that a `CircularString` instance stores circular arc segments and not line segments.</span></span> <span data-ttu-id="a3d7f-188">Por tanto, los lados del triángulo almacenado en la instancia de `CircularString` son ABC, CDE y EFA mientras que los del triángulo almacenado en la instancia de `LineString` son AC, CE y EA.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-188">So the sides of the triangle stored in the `CircularString` instance are ABC, CDE, and EFA whereas the sides of the triangle stored in the `LineString` instance are AC, CE, and EA.</span></span>

 <span data-ttu-id="a3d7f-189">Tenga en cuenta el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-189">Consider the following code snippet:</span></span>

```sql
SET @g1 = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 4 0)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(0 0, 2 2, 4 0)', 0);
SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length];
```

 <span data-ttu-id="a3d7f-190">Este fragmento de código generará los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-190">This snippet will produce the following results:</span></span>

```
LS LengthCS Length
5.65685...6.28318...
```

 <span data-ttu-id="a3d7f-191">En la ilustración siguiente se muestra cómo se almacena cada tipo (se muestran las líneas rojas `LineString``@g1` , las líneas azules `CircularString``@g2` ):</span><span class="sxs-lookup"><span data-stu-id="a3d7f-191">The following illustration shows how each type is stored (red line shows `LineString``@g1`, blue line shows `CircularString``@g2`):</span></span>

 ![](../../database-engine/media/e52157b5-5160-4a4b-8560-50cdcf905b76.png "e52157b5-5160-4a4b-8560-50cdcf905b76")

 <span data-ttu-id="a3d7f-192">Como se muestra en la ilustración anterior, las instancias de `CircularString` usan menos puntos para almacenar límites curvos con mayor precisión que las instancias de `LineString` .</span><span class="sxs-lookup"><span data-stu-id="a3d7f-192">As the illustration above shows, `CircularString` instances use fewer points to store curve boundaries with greater precision than `LineString` instances.</span></span> <span data-ttu-id="a3d7f-193">Las instancias de `CircularString` son útiles para almacenar límites circulares como un radio de búsqueda de veinte millas desde un punto específico.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-193">`CircularString` instances are useful for storing circular boundaries like a twenty-mile search radius from a specific point.</span></span> <span data-ttu-id="a3d7f-194">Las instancias de `LineString` funcionan bien para almacenar límites que son lineales como un bloque de ciudad cuadrado.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-194">`LineString` instances are good for storing boundaries that are linear like a square city block.</span></span>

### <a name="linestring-and-compoundcurve-comparison"></a><span data-ttu-id="a3d7f-195">Comparación de LineString y CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a3d7f-195">LineString and CompoundCurve comparison</span></span>
 <span data-ttu-id="a3d7f-196">En los siguientes ejemplos de código se muestra cómo almacenar la misma figura con instancias de `LineString` y `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-196">The following code examples show how to store the same figure using `LineString` and `CompoundCurve` instances:</span></span>

```sql
SET @g = geometry::Parse('LINESTRING(2 2, 4 2, 4 4, 2 4, 2 2)');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2), (4 2, 4 4), (4 4, 2 4), (2 4, 2 2))');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2, 4 4, 2 4, 2 2))');
```

 <span data-ttu-id="a3d7f-197">or</span><span class="sxs-lookup"><span data-stu-id="a3d7f-197">or</span></span>

 <span data-ttu-id="a3d7f-198">En los ejemplos anteriores, una instancia de `LineString` o un instancia de `CompoundCurve` pudieron almacenar la figura.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-198">In the examples above, either a `LineString` instance or a `CompoundCurve` instance could store the figure.</span></span>  <span data-ttu-id="a3d7f-199">En el siguiente ejemplo se usa `CompoundCurve` para almacenar un segmento de gráfico circular:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-199">This next example uses a `CompoundCurve` to store a pie slice:</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(2 2, 1 3, 0 2),(0 2, 1 0, 2 2))');
```

 <span data-ttu-id="a3d7f-200">Una instancia de `CompoundCurve` puede almacenar el segmento de arco circular (2 2, 1 3, 0 2) directamente mientras que una instancia de `LineString` tendría que convertir la curva en varios segmentos de línea más pequeños.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-200">A `CompoundCurve` instance can store the circular arc segment (2 2, 1 3, 0 2) directly whereas a `LineString` instance would have to convert the curve into several smaller line segments.</span></span>

### <a name="circularstring-and-compoundcurve-comparison"></a><span data-ttu-id="a3d7f-201">Comparación de CircularString y CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a3d7f-201">CircularString and CompoundCurve comparison</span></span>
 <span data-ttu-id="a3d7f-202">En el siguiente ejemplo de código se muestra cómo se puede almacenar el segmento de gráfico circular en una instancia de `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-202">The following code example shows how the pie slice can be stored in a `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');
SELECT @g.ToString(), @g.STLength();
```

 <span data-ttu-id="a3d7f-203">Para almacenar el segmento de gráfico circular mediante una instancia de `CircularString` se requiere que se usen tres puntos para cada segmento de línea.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-203">To store the pie slice using a `CircularString` instance requires that three points be used for each line segment.</span></span>  <span data-ttu-id="a3d7f-204">Si no se conoce un punto intermedio, se debe calcular o se debe duplicar el extremo del segmento de línea como muestra el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-204">If an intermediate point is not known, it either has to be calculated or the endpoint of the line segment has to be doubled as the following snippet shows:</span></span>

```sql
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 3 6.3246, 3 6.3246, 0 7, -3 6.3246, 0 0, 0 0)');
```

 <span data-ttu-id="a3d7f-205">`CompoundCurve`las instancias `LineString` de permiten `CircularString` los componentes y para que solo se necesiten conocer dos puntos en los segmentos de línea del segmento de gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-205">`CompoundCurve` instances allow both `LineString` and `CircularString` components so that only two points to the line segments of the pie slice need to be known.</span></span>  <span data-ttu-id="a3d7f-206">En este ejemplo de código se muestra cómo usar `CompoundCurve` para almacenar la misma figura:</span><span class="sxs-lookup"><span data-stu-id="a3d7f-206">This code example shows how to use a `CompoundCurve` to store the same figure:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING( 3 6.3246, 0 7, -3 6.3246), (-3 6.3246, 0 0, 3 6.3246))');
SELECT @g.ToString(), @g.STLength();
```

### <a name="polygon-and-curvepolygon-comparison"></a><span data-ttu-id="a3d7f-207">Comparación de Polygon y CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="a3d7f-207">Polygon and CurvePolygon comparison</span></span>
 <span data-ttu-id="a3d7f-208">Las instancias de `CurvePolygon` pueden usar las instancias de `CircularString` y `CompoundCurve` cuando se definen sus anillos exterior e interior.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-208">`CurvePolygon` instances can use `CircularString` and `CompoundCurve` instances when defining their exterior and interior rings.</span></span>  <span data-ttu-id="a3d7f-209">Las instancias de `Polygon` no pueden usar los tipos de segmento de arco circular: `CircularString` y `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="a3d7f-209">`Polygon` instances cannot use the circular arc segment types: `CircularString` and `CompoundCurve`.</span></span>


## <a name="see-also"></a><span data-ttu-id="a3d7f-210">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3d7f-210">See Also</span></span>
 <span data-ttu-id="a3d7f-211">[&#40;de datos espaciales SQL Server&#41;](../spatial/spatial-data-sql-server.md) [tipo de datos Geometry referencia](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) del método de [tipo de datos Geography](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;Geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;Geography Data](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) Type&#41;[STGeomFromText &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;Geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span><span class="sxs-lookup"><span data-stu-id="a3d7f-211">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) [geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span></span>


