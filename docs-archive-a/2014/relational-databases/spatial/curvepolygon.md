---
title: CurvePolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e000a1d8-a049-4542-bfeb-943fd6ab3969
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b90fdbd9a0bc80dfc6a82416d0193b2951fe13ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663322"
---
# <a name="curvepolygon"></a><span data-ttu-id="5a402-102">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="5a402-102">CurvePolygon</span></span>
  <span data-ttu-id="5a402-103">Un `CurvePolygon` es una superficie cerrada topológicamente definida por un anillo de límite exterior y cero o más anillos interiores</span><span class="sxs-lookup"><span data-stu-id="5a402-103">A `CurvePolygon` is a topologically closed surface defined by an exterior bounding ring and zero or more interior rings</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5a402-104">Para obtener una descripción detallada y ejemplos de las características espaciales introducidas en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , incluido el `CurvePolygon` subtipo, descargue las notas del producto [nuevas características espaciales en SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="5a402-104">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CurvePolygon` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="5a402-105">Los siguientes criterios definen atributos de una `CurvePolygon` instancia de:</span><span class="sxs-lookup"><span data-stu-id="5a402-105">The following criteria define attributes of a `CurvePolygon` instance:</span></span>  
  
-   <span data-ttu-id="5a402-106">El límite de la instancia de `CurvePolygon` se define mediante el anillo exterior y todos los anillos interiores.</span><span class="sxs-lookup"><span data-stu-id="5a402-106">The boundary of the `CurvePolygon` instance is defined by the exterior ring and all interior rings.</span></span>  
  
-   <span data-ttu-id="5a402-107">El interior de la instancia de `CurvePolygon` es el espacio entre el anillo exterior y todos los anillos interiores.</span><span class="sxs-lookup"><span data-stu-id="5a402-107">The interior of the `CurvePolygon` instance is the space between the exterior ring and all of the interior rings.</span></span>  
  
 <span data-ttu-id="5a402-108">Una instancia de `CurvePolygon` difiere de una instancia de `Polygon` en que una instancia de `CurvePolygon` puede contener los siguientes segmentos de arco circular: `CircularString` y `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="5a402-108">A `CurvePolygon` instance differs from a `Polygon` instance in that a `CurvePolygon` instance may contain the following circular arc segments: `CircularString` and `CompoundCurve`.</span></span>  
  
## <a name="compoundcurve-instances"></a><span data-ttu-id="5a402-109">Instancias de CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="5a402-109">CompoundCurve instances</span></span>  
 <span data-ttu-id="5a402-110">La ilustración siguiente muestra figuras `CurvePolygon` válidas:</span><span class="sxs-lookup"><span data-stu-id="5a402-110">Illustration below shows valid `CurvePolygon` figures:</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="5a402-111">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="5a402-111">Accepted instances</span></span>  
 <span data-ttu-id="5a402-112">Para que una instancia de `CurvePolygon` se acepte, tiene que estar vacía o solo contener anillos de arco circulares aceptados.</span><span class="sxs-lookup"><span data-stu-id="5a402-112">For a `CurvePolygon` instance to be accepted, it needs to be either empty or contain only circular arc rings that are accepted.</span></span> <span data-ttu-id="5a402-113">Un anillo de arco circular aceptado cumple los siguientes requisitos.</span><span class="sxs-lookup"><span data-stu-id="5a402-113">An accepted circular arc ring meets the following requirements.</span></span>  
  
1.  <span data-ttu-id="5a402-114">Es una instancia de `LineString`, `CircularString` o `CompoundCurve` aceptada.</span><span class="sxs-lookup"><span data-stu-id="5a402-114">Is an accepted `LineString`, `CircularString`, or `CompoundCurve` instance.</span></span> <span data-ttu-id="5a402-115">Para obtener más información sobre instancias aceptadas, vea [LineString](linestring.md), [CircularString](circularstring.md)y [CompoundCurve](compoundcurve.md).</span><span class="sxs-lookup"><span data-stu-id="5a402-115">For more information on accepted instances, see [LineString](linestring.md), [CircularString](circularstring.md), and [CompoundCurve](compoundcurve.md).</span></span>  
  
2.  <span data-ttu-id="5a402-116">Tiene cuatro puntos como mínimo.</span><span class="sxs-lookup"><span data-stu-id="5a402-116">Has at least four points.</span></span>  
  
3.  <span data-ttu-id="5a402-117">Los puntos inicial y final tienen las mismas coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="5a402-117">The start and end point have the same X and Y coordinates.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5a402-118">Se omiten los valores Z y M.</span><span class="sxs-lookup"><span data-stu-id="5a402-118">Z and M values are ignored.</span></span>  
  
 <span data-ttu-id="5a402-119">El siguiente ejemplo muestra instancias aceptadas de `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="5a402-119">The following example shows accepted `CurvePolygon` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0, 0 0))';  
DECLARE @g3 geometry = 'CURVEPOLYGON((0 0 1, 0 0 2, 0 0 3, 0 0 3))'  
DECLARE @g4 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
DECLARE @g5 geography = 'CURVEPOLYGON((-122.3 47, 122.3 -47, 125.7 -49, 121 -38, -122.3 47))';  
```  
  
 <span data-ttu-id="5a402-120">`@g3` aunque los puntos inicial y final tengan distintos valores Z porque se omiten los valores Z.</span><span class="sxs-lookup"><span data-stu-id="5a402-120">`@g3` is accepted even though the start and end points have different Z values because Z values are ignored.</span></span> <span data-ttu-id="5a402-121">Se acepta `@g5` aunque la instancia del tipo `geography` no sea válida.</span><span class="sxs-lookup"><span data-stu-id="5a402-121">`@g5` is accepted even though the `geography` type instance is not valid.</span></span>  
  
 <span data-ttu-id="5a402-122">Los ejemplos siguientes inician `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="5a402-122">The following examples throw `System.FormatException`.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON((0 5, 0 0, 0 0, 0 0))';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0))';  
```  
  
 <span data-ttu-id="5a402-123">`@g1` no se acepta porque los puntos inicial y final no tienen el mismo valor Y.</span><span class="sxs-lookup"><span data-stu-id="5a402-123">`@g1` is not accepted because the start and end points do not have the same Y value.</span></span> <span data-ttu-id="5a402-124">`@g2` no se acepta porque el anillo no tiene suficientes puntos.</span><span class="sxs-lookup"><span data-stu-id="5a402-124">`@g2` is not accepted because the ring does not have enough points.</span></span>  
  
### <a name="valid-instances"></a><span data-ttu-id="5a402-125">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="5a402-125">Valid instances</span></span>  
 <span data-ttu-id="5a402-126">Para que una instancia de `CurvePolygon` sea válida los anillos exterior e interior deben cumplir los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="5a402-126">For a `CurvePolygon` instance to be valid both exterior and interior rings must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="5a402-127">Solo pueden tocar en puntos de tangencia únicos.</span><span class="sxs-lookup"><span data-stu-id="5a402-127">They may only touch at single tangent points.</span></span>  
  
2.  <span data-ttu-id="5a402-128">No pueden cruzarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="5a402-128">They cannot cross each other.</span></span>  
  
3.  <span data-ttu-id="5a402-129">Cada anillo debe contener cuatro puntos como mínimo.</span><span class="sxs-lookup"><span data-stu-id="5a402-129">Each ring must contain at least four points.</span></span>  
  
4.  <span data-ttu-id="5a402-130">Cada anillo debe ser un tipo de curva aceptable.</span><span class="sxs-lookup"><span data-stu-id="5a402-130">Each ring must be an acceptable curve type.</span></span>  
  
 <span data-ttu-id="5a402-131">Las instancias de `CurvePolygon` tienen también que cumplir criterios concretos en función de que sean tipos de datos `geometry` o `geography`.</span><span class="sxs-lookup"><span data-stu-id="5a402-131">`CurvePolygon` instances also need to meet specific criteria depending on whether they are `geometry` or `geography` data types.</span></span>  
  
#### <a name="geometry-data-type"></a><span data-ttu-id="5a402-132">Tipo de datos geometry</span><span class="sxs-lookup"><span data-stu-id="5a402-132">Geometry data type</span></span>  
 <span data-ttu-id="5a402-133">Una instancia de **geometryCurvePolygon** válida debe tener los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="5a402-133">A valid **geometryCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="5a402-134">Todos los anillos interiores deben estar contenidos en el anillo exterior.</span><span class="sxs-lookup"><span data-stu-id="5a402-134">All the interior rings must be contained within the exterior ring.</span></span>  
  
2.  <span data-ttu-id="5a402-135">Puede tener varios anillos interiores, pero un anillo interior no puede contener otro anillo interior.</span><span class="sxs-lookup"><span data-stu-id="5a402-135">May have multiple interior rings, but an interior ring cannot contain another interior ring.</span></span>  
  
3.  <span data-ttu-id="5a402-136">Ningún anillo puede cruzarse consigo mismo ni con otros.</span><span class="sxs-lookup"><span data-stu-id="5a402-136">No ring can cross itself or another ring.</span></span>  
  
4.  <span data-ttu-id="5a402-137">Los anillos solo pueden tocar en puntos de tangencia únicos (el número de puntos donde el contacto de los anillos debe ser finito).</span><span class="sxs-lookup"><span data-stu-id="5a402-137">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
5.  <span data-ttu-id="5a402-138">El interior del polígono debe estar conectado.</span><span class="sxs-lookup"><span data-stu-id="5a402-138">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="5a402-139">En el siguiente ejemplo se muestran instancias válidas de **geometryCurvePolygon** .</span><span class="sxs-lookup"><span data-stu-id="5a402-139">The following example shows valid **geometryCurvePolygon** instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
SELECT @g1.STIsValid(), @g2.STIsValid();  
```  
  
 <span data-ttu-id="5a402-140">Las instancias de CurvePolygon tienen las mismas reglas de validez que las de Poligon con la excepción de que las instancias de CurvePolygon pueden aceptar los nuevos tipos de segmento de arco circular.</span><span class="sxs-lookup"><span data-stu-id="5a402-140">CurvePolygon instances have the same validity rules as Polygon instances with the exception that CurvePolygon instances may accept the new circular arc segment types.</span></span> <span data-ttu-id="5a402-141">Para obtener más ejemplos de instancias que son válidas o que no lo son, vea [Polygon](polygon.md).</span><span class="sxs-lookup"><span data-stu-id="5a402-141">For more examples of instances that are valid or not valid, see [Polygon](polygon.md).</span></span>  
  
#### <a name="geography-data-type"></a><span data-ttu-id="5a402-142">Tipo de datos geography</span><span class="sxs-lookup"><span data-stu-id="5a402-142">Geography data type</span></span>  
 <span data-ttu-id="5a402-143">Una instancia de **geographyCurvePolygon** válida debe tener los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="5a402-143">A valid **geographyCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="5a402-144">El interior del polígono está conectado siguiendo la regla de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="5a402-144">The interior of the polygon is connected using the left-hand rule.</span></span>  
  
2.  <span data-ttu-id="5a402-145">Ningún anillo puede cruzarse consigo mismo ni con otros.</span><span class="sxs-lookup"><span data-stu-id="5a402-145">No ring can cross itself or another ring.</span></span>  
  
3.  <span data-ttu-id="5a402-146">Los anillos solo pueden tocar en puntos de tangencia únicos (el número de puntos donde el contacto de los anillos debe ser finito).</span><span class="sxs-lookup"><span data-stu-id="5a402-146">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
4.  <span data-ttu-id="5a402-147">El interior del polígono debe estar conectado.</span><span class="sxs-lookup"><span data-stu-id="5a402-147">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="5a402-148">En el siguiente ejemplo se muestra una instancia de CurvePolygon geography válida.</span><span class="sxs-lookup"><span data-stu-id="5a402-148">The following example shows a valid geography CurvePolygon instance.</span></span>  
  
```  
DECLARE @g geography = 'CURVEPOLYGON((-122.3 47, 122.3 47, 125.7 49, 121 38, -122.3 47))';  
SELECT @g.STIsValid();  
```  
  
## <a name="examples"></a><span data-ttu-id="5a402-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5a402-149">Examples</span></span>  
  
### <a name="a-instantiating-a-geometry-instance-with-an-empty-curvepolygon"></a><span data-ttu-id="5a402-150">A.</span><span class="sxs-lookup"><span data-stu-id="5a402-150">A.</span></span> <span data-ttu-id="5a402-151">Crear una instancia de una instancia de geometry con un CurvePolygon vacío</span><span class="sxs-lookup"><span data-stu-id="5a402-151">Instantiating a Geometry Instance with an Empty CurvePolygon</span></span>  
 <span data-ttu-id="5a402-152">En este ejemplo se muestra cómo crear una instancia de `CurvePolygon` vacía:</span><span class="sxs-lookup"><span data-stu-id="5a402-152">This example shows how to create an empty `CurvePolygon` instance:</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON EMPTY');  
```  
  
### <a name="b-declaring-and-instantiating-a-geometry-instance-with-a-curvepolygon-in-the-same-statement"></a><span data-ttu-id="5a402-153">B.</span><span class="sxs-lookup"><span data-stu-id="5a402-153">B.</span></span> <span data-ttu-id="5a402-154">Declarar y crear instancias de una instancia geometry con un CurvePolygon en la misma instrucción</span><span class="sxs-lookup"><span data-stu-id="5a402-154">Declaring and Instantiating a Geometry Instance with a CurvePolygon in the Same Statement</span></span>  
 <span data-ttu-id="5a402-155">Este fragmento de código muestra cómo declarar e inicializar una instancia de geometry con un `CurvePolygon` en la misma instrucción:</span><span class="sxs-lookup"><span data-stu-id="5a402-155">This code snippet shows how to declare and initialize a geometry instance with a `CurvePolygon` in the same statement:</span></span>  
  
```sql  
DECLARE @g geometry = 'CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))'  
```  
  
### <a name="c-instantiating-a-geography-instance-with-a-curvepolygon"></a><span data-ttu-id="5a402-156">C.</span><span class="sxs-lookup"><span data-stu-id="5a402-156">C.</span></span> <span data-ttu-id="5a402-157">Crear instancias de una instancia de geography con un CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="5a402-157">Instantiating a Geography Instance with a CurvePolygon</span></span>  
 <span data-ttu-id="5a402-158">Este fragmento de código muestra cómo declarar e inicializar una instancia de `geography` con un `CurvePolygon`:</span><span class="sxs-lookup"><span data-stu-id="5a402-158">This code snippet shows how to declare and initialize a `geography` instance with a `CurvePolygon`:</span></span>  
  
```sql  
DECLARE @g geography = 'CURVEPOLYGON(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';  
```  
  
### <a name="d-storing-a-curvepolygon-with-only-an-exterior-bounding-ring"></a><span data-ttu-id="5a402-159">D.</span><span class="sxs-lookup"><span data-stu-id="5a402-159">D.</span></span> <span data-ttu-id="5a402-160">Almacenar un CurvePolygon con solo un anillo de límite exterior</span><span class="sxs-lookup"><span data-stu-id="5a402-160">Storing a CurvePolygon with Only an Exterior Bounding Ring</span></span>  
 <span data-ttu-id="5a402-161">En este ejemplo se muestra cómo almacenar un círculo simple en una instancia de `CurvePolygon` (solo se utiliza un anillo de límite exterior para definir el círculo):</span><span class="sxs-lookup"><span data-stu-id="5a402-161">This example shows how to store a simple circle in a `CurvePolygon` instance (only an exterior bounding ring is used to define the circle):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
### <a name="e-storing-a-curvepolygon-containing-interior-rings"></a><span data-ttu-id="5a402-162">E.</span><span class="sxs-lookup"><span data-stu-id="5a402-162">E.</span></span> <span data-ttu-id="5a402-163">Almacenar un CurvePolygon que contiene anillos interiores</span><span class="sxs-lookup"><span data-stu-id="5a402-163">Storing a CurvePolygon Containing Interior Rings</span></span>  
 <span data-ttu-id="5a402-164">En este ejemplo se crea un anillo en una instancia de `CurvePolygon` (se usa un anillo de límite exterior y un anillo interior para definir el anillo):</span><span class="sxs-lookup"><span data-stu-id="5a402-164">This example creates a donut in a `CurvePolygon` instance (both an exterior bounding ring and an interior ring is used to define the donut):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 4, 4 0, 8 4, 4 8, 0 4), CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
 <span data-ttu-id="5a402-165">Este ejemplo muestra una instancia de `CurvePolygon` válida y una instancia no válida al usar los anillos interiores:</span><span class="sxs-lookup"><span data-stu-id="5a402-165">This example shows both a valid `CurvePolygon` instance and an invalid instance when using interior rings:</span></span>  
  
```sql  
DECLARE @g1 geometry, @g2 geometry;  
SET @g1 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (-2 2, 2 2, 2 -2, -2 -2, -2 2))');  
IF @g1.STIsValid() = 1  
  BEGIN  
     SELECT @g1.STArea();  
  END  
SET @g2 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (0 5, 5 0, 0 -5, -5 0, 0 5))');  
IF @g2.STIsValid() = 1  
  BEGIN  
     SELECT @g2.STArea();  
  END  
SELECT @g1.STIsValid() AS G1, @g2.STIsValid() AS G2;  
```  
  
 <span data-ttu-id="5a402-166">@g1 y @g2 usan el mismo anillo de límite exterior: un círculo con un radio de 5 y los dos usan un cuadrado para un anillo interior.</span><span class="sxs-lookup"><span data-stu-id="5a402-166">Both @g1 and @g2 use the same exterior bounding ring: a circle with a radius of 5 and they both use a square for an interior ring.</span></span>  <span data-ttu-id="5a402-167">Sin embargo, la instancia de @g1 es válida, pero la instancia de @g2 no lo es.</span><span class="sxs-lookup"><span data-stu-id="5a402-167">However, the instance @g1 is valid, but the instance @g2 is invalid.</span></span>  <span data-ttu-id="5a402-168">La razón de que @g2 no sea válida es que el anillo interior divide el espacio interior limitado por el anillo exterior en cuatro regiones independientes.</span><span class="sxs-lookup"><span data-stu-id="5a402-168">The reason that @g2 is invalid is that the interior ring splits the interior space bounded by the exterior ring into four separate regions.</span></span>  <span data-ttu-id="5a402-169">El siguiente dibujo muestra lo que ha sucedido:</span><span class="sxs-lookup"><span data-stu-id="5a402-169">The following drawing shows what occurred:</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a402-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a402-170">See Also</span></span>  
 <span data-ttu-id="5a402-171">[Polygon](polygon.md) </span><span class="sxs-lookup"><span data-stu-id="5a402-171">[Polygon](polygon.md) </span></span>  
 <span data-ttu-id="5a402-172">[CircularString](circularstring.md) </span><span class="sxs-lookup"><span data-stu-id="5a402-172">[CircularString](circularstring.md) </span></span>  
 <span data-ttu-id="5a402-173">[CompoundCurve](compoundcurve.md) </span><span class="sxs-lookup"><span data-stu-id="5a402-173">[CompoundCurve](compoundcurve.md) </span></span>  
 <span data-ttu-id="5a402-174">[Referencia de los métodos del tipo de datos geometry](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a402-174">[geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span></span>  
 <span data-ttu-id="5a402-175">[Referencia de los métodos del tipo de datos geography](/sql/t-sql/spatial-geography/spatial-types-geography) </span><span class="sxs-lookup"><span data-stu-id="5a402-175">[geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) </span></span>  
 [<span data-ttu-id="5a402-176">Información general de los tipos de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="5a402-176">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
