---
title: CompoundCurve | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae357f9b-e3e2-4cdf-af02-012acda2e466
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 6a899bbe9a17a64083592e1078e8cac93365f02b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663327"
---
# <a name="compoundcurve"></a><span data-ttu-id="c7e62-102">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c7e62-102">CompoundCurve</span></span>
  <span data-ttu-id="c7e62-103">Una `CompoundCurve` es una recopilación de cero o más instancias de `CircularString` o `LineString` de tipos de geometría o de geografía.</span><span class="sxs-lookup"><span data-stu-id="c7e62-103">A `CompoundCurve` is a collection of zero or more continuous `CircularString` or `LineString` instances of either geometry or geography types.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="c7e62-104">Para obtener una descripción detallada y ejemplos de las nuevas características espaciales de esta versión, incluido el `CompoundCurve` subtipo, descargue las notas del producto [nuevas características espaciales en SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="c7e62-104">For a detailed description and examples of the new spatial features in this release, including the `CompoundCurve` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

 <span data-ttu-id="c7e62-105">Se puede crear una instancia vacía de `CompoundCurve`, pero para que una `CompoundCurve` sea válida debe cumplir los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="c7e62-105">An empty `CompoundCurve` instance can be instantiated, but for a `CompoundCurve` to be valid it must meet the following criteria:</span></span>

1.  <span data-ttu-id="c7e62-106">Debe contener al menos una instancia de `CircularString` o de `LineString`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-106">It must contain at least one `CircularString` or `LineString` instance.</span></span>

2.  <span data-ttu-id="c7e62-107">La secuencia de instancias de `CircularString` o `LineString` debe ser continua.</span><span class="sxs-lookup"><span data-stu-id="c7e62-107">The sequence of `CircularString` or `LineString` instances must be continuous.</span></span>

 <span data-ttu-id="c7e62-108">Si un `CompoundCurve` contiene una secuencia de varias `CircularString` instancias de y `LineString` , el extremo final de cada instancia, salvo la última, debe ser el extremo inicial de la siguiente instancia de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c7e62-108">If a `CompoundCurve` contains a sequence of multiple `CircularString` and `LineString` instances, the ending endpoint for every instance except for the last instance must be the starting endpoint for the next instance in the sequence.</span></span> <span data-ttu-id="c7e62-109">Esto significa que si el punto final de una instancia anterior de la secuencia es (4 3 7 2), el punto inicial para la instancia siguiente de la secuencia debe ser (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="c7e62-109">This means that if the ending point of a prior instance in the sequence is (4 3 7 2), the starting point for the next instance in the sequence must be (4 3 7 2).</span></span> <span data-ttu-id="c7e62-110">Observe que los valores M (medida) y Z (elevación) para el punto también deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="c7e62-110">Note that Z(elevation) and M(measure) values for the point must also be the same.</span></span> <span data-ttu-id="c7e62-111">Si hay diferencia entre ambos puntos, se produce una excepción `System.FormatException` .</span><span class="sxs-lookup"><span data-stu-id="c7e62-111">If there is a difference in the two points, a `System.FormatException` is thrown.</span></span> <span data-ttu-id="c7e62-112">Los puntos de una `CircularString` no tienen que tener valor Z o M.</span><span class="sxs-lookup"><span data-stu-id="c7e62-112">Points in a `CircularString` do not have to have a Z or M value.</span></span> <span data-ttu-id="c7e62-113">Si no se proporcionan valores Z o M para el punto final de la instancia anterior, el punto inicial de la instancia siguiente no puede incluir valores Z o M.</span><span class="sxs-lookup"><span data-stu-id="c7e62-113">If no Z or M values are given for the ending point of the prior instance, the starting point of the next instance cannot include Z or M values.</span></span> <span data-ttu-id="c7e62-114">Si el punto final para la secuencia anterior es (4 3), el punto inicial para la secuencia siguiente debe ser (4 3); no puede ser (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="c7e62-114">If the ending point for the prior sequence is (4 3), the starting point for the next sequence must be (4 3); it cannot be (4 3 7 2).</span></span> <span data-ttu-id="c7e62-115">Todos los puntos de una instancia `CompoundCurve` deben tener el mismo valor Z, o bien, ningún valor Z.</span><span class="sxs-lookup"><span data-stu-id="c7e62-115">All points in a `CompoundCurve` instance must have either no Z value or the same Z value.</span></span>

## <a name="compoundcurve-instances"></a><span data-ttu-id="c7e62-116">Instancias de CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c7e62-116">CompoundCurve instances</span></span>
 <span data-ttu-id="c7e62-117">La siguiente ilustración muestra tipos válidos de `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-117">The following illustration shows valid `CompoundCurve` types.</span></span>

 ![](../../database-engine/media/f278742e-b861-4555-8b51-3d972b7602bf.png "f278742e-b861-4555-8b51-3d972b7602bf")

### <a name="accepted-instances"></a><span data-ttu-id="c7e62-118">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="c7e62-118">Accepted instances</span></span>
 <span data-ttu-id="c7e62-119">Se acepta la instancia `CompoundCurve` si es una instancia vacía o cumple los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="c7e62-119">`CompoundCurve` instance is accepted if it is an empty instance or meets the following criteria.</span></span>

1.  <span data-ttu-id="c7e62-120">Todas las instancias contenidas en la instancia `CompoundCurve` son instancias de segmento de arco circular aceptadas.</span><span class="sxs-lookup"><span data-stu-id="c7e62-120">All the instances contained by `CompoundCurve` instance are accepted circular arc segment instances.</span></span> <span data-ttu-id="c7e62-121">Para obtener más información sobre instancias de segmento de arco circular aceptadas, vea [LineString](linestring.md) y [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="c7e62-121">For more information on accepted circular arc segment instances, see [LineString](linestring.md) and [CircularString](circularstring.md).</span></span>

2.  <span data-ttu-id="c7e62-122">Todos los segmentos de arco circulares contenidos en la instancia `CompoundCurve` están conectados.</span><span class="sxs-lookup"><span data-stu-id="c7e62-122">All of the circular arc segments in the `CompoundCurve` instance are connected.</span></span> <span data-ttu-id="c7e62-123">El primer punto de cada segmento de arco circular siguiente coincide con el último punto del segmento de arco circular precedente.</span><span class="sxs-lookup"><span data-stu-id="c7e62-123">The first point for each succeeding circular arc segment is the same as the last point on the preceding circular arc segment.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c7e62-124">Esto incluye las coordenadas Z y M.</span><span class="sxs-lookup"><span data-stu-id="c7e62-124">This includes the Z and M coordinates.</span></span> <span data-ttu-id="c7e62-125">Por tanto, las cuatro coordenadas X, Y, Z y M deben coincidir para ambos puntos.</span><span class="sxs-lookup"><span data-stu-id="c7e62-125">So, all four coordinates X, Y, Z, and M must be the same.</span></span>

3.  <span data-ttu-id="c7e62-126">Ninguna de las instancias contenidas son instancias vacías.</span><span class="sxs-lookup"><span data-stu-id="c7e62-126">None of the contained instances are empty instances.</span></span>

 <span data-ttu-id="c7e62-127">El siguiente ejemplo muestra instancias aceptadas de `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-127">The following example shows accepted `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
```

 <span data-ttu-id="c7e62-128">El siguiente ejemplo muestra instancias de `CompoundCurve` no aceptadas.</span><span class="sxs-lookup"><span data-stu-id="c7e62-128">The following example shows `CompoundCurve` instances that are not accepted.</span></span> <span data-ttu-id="c7e62-129">Estas instancias producen una excepción `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-129">These instances throw `System.FormatException`.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING EMPTY)';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (1 0, 2 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="c7e62-130">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="c7e62-130">Valid instances</span></span>
 <span data-ttu-id="c7e62-131">Una instancia de `CompoundCurve` es válida si cumple los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="c7e62-131">A `CompoundCurve` instance is valid if it meets the following criteria.</span></span>

1.  <span data-ttu-id="c7e62-132">La instancia de `CompoundCurve` es aceptada.</span><span class="sxs-lookup"><span data-stu-id="c7e62-132">The `CompoundCurve` instance is accepted.</span></span>

2.  <span data-ttu-id="c7e62-133">Todas las instancias de segmento de arco circular contenidas en la instancia `CompoundCurve` son instancias válidas.</span><span class="sxs-lookup"><span data-stu-id="c7e62-133">All circular arc segment instances contained by the `CompoundCurve` instance are valid instances.</span></span>

 <span data-ttu-id="c7e62-134">En el siguiente ejemplo se muestran instancias válidas de `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-134">The following example shows valid `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();

```

 <span data-ttu-id="c7e62-135">`@g3` es válido porque la instancia `CircularString` es válida.</span><span class="sxs-lookup"><span data-stu-id="c7e62-135">`@g3` is valid because the `CircularString` instance is valid.</span></span> <span data-ttu-id="c7e62-136">Para obtener más información sobre la validez de la `CircularString` instancia, vea [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="c7e62-136">For more information on the validity of the `CircularString` instance, see [CircularString](circularstring.md).</span></span>

 <span data-ttu-id="c7e62-137">El siguiente ejemplo muestra instancias de `CompoundCurve` no válidas.</span><span class="sxs-lookup"><span data-stu-id="c7e62-137">The following example shows `CompoundCurve` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4, 3 5))';
DECLARE @g2 geometry = 'COMPOUNDCURVE((1 1, 1 1))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 2 3, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="c7e62-138">`@g1` no es válida porque la segunda instancia no es una instancia válida de LineString.</span><span class="sxs-lookup"><span data-stu-id="c7e62-138">`@g1` is not valid because the second instance is not a valid LineString instance.</span></span> <span data-ttu-id="c7e62-139">`@g2` no es válida porque la instancia de `LineString` no es válida.</span><span class="sxs-lookup"><span data-stu-id="c7e62-139">`@g2` is not valid because the `LineString` instance is not valid.</span></span> <span data-ttu-id="c7e62-140">`@g3` no es válida porque la instancia de `CircularString` no es válida.</span><span class="sxs-lookup"><span data-stu-id="c7e62-140">`@g3` is not valid because the `CircularString` instance is not valid.</span></span> <span data-ttu-id="c7e62-141">Para obtener más información sobre `CircularString` las instancias de y válidas `LineString` , vea [CircularString](circularstring.md) y [LineString](linestring.md).</span><span class="sxs-lookup"><span data-stu-id="c7e62-141">For more information on valid `CircularString` and `LineString` instances, see [CircularString](circularstring.md) and [LineString](linestring.md).</span></span>

## <a name="examples"></a><span data-ttu-id="c7e62-142">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c7e62-142">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-compooundcurve"></a><span data-ttu-id="c7e62-143">A.</span><span class="sxs-lookup"><span data-stu-id="c7e62-143">A.</span></span> <span data-ttu-id="c7e62-144">Crear una instancia de geometry con una CompoundCurve vacía</span><span class="sxs-lookup"><span data-stu-id="c7e62-144">Instantiating a geometry instance with an empty CompooundCurve</span></span>
 <span data-ttu-id="c7e62-145">En el ejemplo siguiente, se muestra cómo crear una instancia vacía de `CompoundCurve` :</span><span class="sxs-lookup"><span data-stu-id="c7e62-145">The following example shows how to create an empty `CompoundCurve` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE EMPTY');
```

### <a name="b-declaring-and-instantiating-a-geometry-instance-using-a-compoundcurve-in-the-same-statement"></a><span data-ttu-id="c7e62-146">B.</span><span class="sxs-lookup"><span data-stu-id="c7e62-146">B.</span></span> <span data-ttu-id="c7e62-147">Declarar y crear una instancia de geometry usando una CompoundCurve en la misma instrucción</span><span class="sxs-lookup"><span data-stu-id="c7e62-147">Declaring and instantiating a geometry instance using a CompoundCurve in the same statement</span></span>
 <span data-ttu-id="c7e62-148">En el siguiente ejemplo, se muestra cómo declarar e inicializar una instancia de `geometry` con una `CompoundCurve`en la misma instrucción:</span><span class="sxs-lookup"><span data-stu-id="c7e62-148">The following example shows how to declare and initialize a `geometry` instance with a `CompoundCurve`in the same statement:</span></span>

```sql
DECLARE @g geometry = 'COMPOUNDCURVE ((2 2, 0 0),CIRCULARSTRING (0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0))';
```

### <a name="c-instantiating-a-geography-instance-with-a-compoundcurve"></a><span data-ttu-id="c7e62-149">C.</span><span class="sxs-lookup"><span data-stu-id="c7e62-149">C.</span></span> <span data-ttu-id="c7e62-150">Crear una instancia de geography con una CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c7e62-150">Instantiating a geography instance with a CompoundCurve</span></span>
 <span data-ttu-id="c7e62-151">En el siguiente ejemplo, se muestra cómo declarar e inicializar una instancia `geography` con una `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="c7e62-151">The following example shows how to declare and initialize a `geography` instance with a `CompoundCurve`:</span></span>

```sql
DECLARE @g geography = 'COMPOUNDCURVE(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';
```

### <a name="d-storing-a-square-in-a-compoundcurve-instance"></a><span data-ttu-id="c7e62-152">D.</span><span class="sxs-lookup"><span data-stu-id="c7e62-152">D.</span></span> <span data-ttu-id="c7e62-153">Almacenar un cuadrado en una instancia de CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c7e62-153">Storing a square in a CompoundCurve instance</span></span>
 <span data-ttu-id="c7e62-154">En el siguiente ejemplo, se muestran dos maneras diferentes de utilizar una instancia `CompoundCurve` para almacenar un cuadrado.</span><span class="sxs-lookup"><span data-stu-id="c7e62-154">The following example uses two different ways to use a `CompoundCurve` instance to store a square.</span></span>

```sql
DECLARE @g1 geometry, @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3), (1 3, 3 3),(3 3, 3 1), (3 1, 1 1))');
SET @g2 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3, 3 3, 3 1, 1 1))');
SELECT @g1.STLength(), @g2.STLength();
```

 <span data-ttu-id="c7e62-155">Las longitudes de `@g1` y `@g2` son iguales.</span><span class="sxs-lookup"><span data-stu-id="c7e62-155">The lengths for both `@g1` and `@g2` are the same.</span></span> <span data-ttu-id="c7e62-156">Observe en el ejemplo que una instancia de `CompoundCurve` puede almacenar una o más instancias de `LineString`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-156">Notice from the example that a `CompoundCurve` instance can store one or more instances of `LineString`.</span></span>

### <a name="e-instantiating-a-geometry-instance-using-a-compoundcurve-with-multiple-circularstrings"></a><span data-ttu-id="c7e62-157">E.</span><span class="sxs-lookup"><span data-stu-id="c7e62-157">E.</span></span> <span data-ttu-id="c7e62-158">Crear una instancia de geometry usando una CompoundCurve con varias CircularStrings</span><span class="sxs-lookup"><span data-stu-id="c7e62-158">Instantiating a geometry instance using a CompoundCurve with multiple CircularStrings</span></span>
 <span data-ttu-id="c7e62-159">En el siguiente ejemplo, se muestra cómo utilizar dos instancias `CircularString` diferentes para inicializar una `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-159">The following example shows how to use two different `CircularString` instances to initialize a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT @g.STLength();
```

 <span data-ttu-id="c7e62-160">Esto genera el siguiente resultado: 12,566370... que equivale a 4&#x03c0; (4 \* PI).</span><span class="sxs-lookup"><span data-stu-id="c7e62-160">This produces the following output: 12.566370... which is the equivalent of 4&#x03c0; (4 \* pi).</span></span> <span data-ttu-id="c7e62-161">La instancia de `CompoundCurve` del ejemplo almacena un círculo de radio 2.</span><span class="sxs-lookup"><span data-stu-id="c7e62-161">The `CompoundCurve` instance in the example stores a circle with a radius of 2.</span></span> <span data-ttu-id="c7e62-162">Ambos ejemplos de código anteriores no tuvieron que utilizar una `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-162">Both of the previous code examples did not have to use a `CompoundCurve`.</span></span> <span data-ttu-id="c7e62-163">Para el primer ejemplo, habría sido más fácil utilizar una instancia de `LineString` , mientras que para el segundo ejemplo habría sido más fácil una instancia de `CircularString` .</span><span class="sxs-lookup"><span data-stu-id="c7e62-163">For the first example a `LineString` instance would have been simpler, and a `CircularString` instance would have been simpler for the second example.</span></span> <span data-ttu-id="c7e62-164">Sin embargo, el ejemplo siguiente muestra un caso donde `CompoundCurve` proporciona una mejor alternativa.</span><span class="sxs-lookup"><span data-stu-id="c7e62-164">However, the next example shows where a `CompoundCurve` provides a better alternative.</span></span>

### <a name="f-using-a-compoundcurve-to-store-a-semicircle"></a><span data-ttu-id="c7e62-165">F.</span><span class="sxs-lookup"><span data-stu-id="c7e62-165">F.</span></span> <span data-ttu-id="c7e62-166">Usar una CompoundCurve para almacenar un semicírculo</span><span class="sxs-lookup"><span data-stu-id="c7e62-166">Using a CompoundCurve to store a semicircle</span></span>
 <span data-ttu-id="c7e62-167">En el siguiente ejemplo, se utiliza una instancia de `CompoundCurve` para almacenar un semicírculo.</span><span class="sxs-lookup"><span data-stu-id="c7e62-167">The following example uses a `CompoundCurve` instance to store a semicircle.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))');
SELECT @g.STLength();
```

### <a name="g-storing-multiple-circularstring-and-linestring-instances-in-a-compoundcurve"></a><span data-ttu-id="c7e62-168">G.</span><span class="sxs-lookup"><span data-stu-id="c7e62-168">G.</span></span> <span data-ttu-id="c7e62-169">Almacenar varias instancias de CircularString y LineString en una CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c7e62-169">Storing multiple CircularString and LineString instances in a CompoundCurve</span></span>
 <span data-ttu-id="c7e62-170">En el siguiente ejemplo, se muestra cómo se pueden almacenar varias instancias de `CircularString` y `LineString` mediante una `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-170">The following example shows how multiple `CircularString` and `LineString` instances can be stored by using a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('COMPOUNDCURVE((3 5, 3 3), CIRCULARSTRING(3 3, 5 1, 7 3), (7 3, 7 5), CIRCULARSTRING(7 5, 5 7, 3 5))');
SELECT @g.STLength();
```

### <a name="h-storing-instances-with-z-and-m-values"></a><span data-ttu-id="c7e62-171">H.</span><span class="sxs-lookup"><span data-stu-id="c7e62-171">H.</span></span> <span data-ttu-id="c7e62-172">Almacenar instancias con valores Z y M</span><span class="sxs-lookup"><span data-stu-id="c7e62-172">Storing instances with Z and M values</span></span>
 <span data-ttu-id="c7e62-173">En el siguiente ejemplo, se muestra cómo utilizar una instancia `CompoundCurve` para almacenar una secuencia de instancias `CircularString` y `LineString` con valores Z y M.</span><span class="sxs-lookup"><span data-stu-id="c7e62-173">The following example shows how to use a `CompoundCurve` instance to store a sequence of `CircularString` and `LineString` instances with both Z and M values.</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(7 5 4 2, 5 7 4 2, 3 5 4 2), (3 5 4 2, 8 7 4 2))');
```

### <a name="i-illustrating-why-circularstring-instances-must-be-explicitly-declared"></a><span data-ttu-id="c7e62-174">I.</span><span class="sxs-lookup"><span data-stu-id="c7e62-174">I.</span></span> <span data-ttu-id="c7e62-175">Obligación de declarar las instancias de CircularString explícitamente</span><span class="sxs-lookup"><span data-stu-id="c7e62-175">Illustrating why CircularString instances must be explicitly declared</span></span>
 <span data-ttu-id="c7e62-176">En el siguiente ejemplo, se muestra por qué se deben declarar explícitamente las instancias de `CircularString` .</span><span class="sxs-lookup"><span data-stu-id="c7e62-176">The following example shows why `CircularString` instances must be explicitly declared.</span></span> <span data-ttu-id="c7e62-177">El programador está intentando almacenar un círculo en una instancia de `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="c7e62-177">The programmer is trying to store a circle in a `CompoundCurve` instance.</span></span>

```sql
DECLARE @g1 geometry;  
DECLARE @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 2 4, 0 2))');
SELECT 'Circle One', @g1.STLength() AS Perimeter;  -- gives an inaccurate amount
SET @g2 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT 'Circle Two', @g2.STLength() AS Perimeter;  -- now we get an accurate amount
```

 <span data-ttu-id="c7e62-178">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="c7e62-178">The output is as follows:</span></span>

```
Circle One11.940039...
Circle Two12.566370...
```

 <span data-ttu-id="c7e62-179">El perímetro para el círculo dos es aproximadamente 4&#x03c0; (4 \* PI), que es el valor real del perímetro.</span><span class="sxs-lookup"><span data-stu-id="c7e62-179">The perimeter for Circle Two is approximately 4&#x03c0; (4 \* pi), which is the actual value for the perimeter.</span></span> <span data-ttu-id="c7e62-180">Sin embargo, el perímetro para el círculo uno es significativamente inexacto.</span><span class="sxs-lookup"><span data-stu-id="c7e62-180">However, the perimeter for Circle One is significantly inaccurate.</span></span> <span data-ttu-id="c7e62-181">La instancia `CompoundCurve` del círculo uno almacena un segmento de arco circular (ABC) y dos segmentos de línea (CD, DA).</span><span class="sxs-lookup"><span data-stu-id="c7e62-181">Circle One's `CompoundCurve` instance stores one circular arc segment (ABC) and two line segments (CD, DA).</span></span> <span data-ttu-id="c7e62-182">La instancia `CompoundCurve` tiene que almacenar dos segmentos de arco circular (ABC, CDA) para definir un círculo.</span><span class="sxs-lookup"><span data-stu-id="c7e62-182">The `CompoundCurve` instance has to store two circular arc segments (ABC, CDA) to define a circle.</span></span> <span data-ttu-id="c7e62-183">Una instancia `LineString` define el segundo conjunto de puntos (4 2, 2 4, 0 2) en la instancia `CompoundCurve` del círculo uno.</span><span class="sxs-lookup"><span data-stu-id="c7e62-183">A `LineString` instance defines the second set of points (4 2, 2 4, 0 2) in Circle One's `CompoundCurve` instance.</span></span> <span data-ttu-id="c7e62-184">Es necesario declarar explícitamente una instancia `CircularString` dentro de una `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c7e62-184">You have to explicitly declare a `CircularString` instance inside a `CompoundCurve`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7e62-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7e62-185">See Also</span></span>
 <span data-ttu-id="c7e62-186">[STIsValid &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [punto](point.md) de [información general de tipos de datos espaciales](spatial-data-types-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c7e62-186">[STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [Spatial Data Types Overview](spatial-data-types-overview.md) [Point](point.md)</span></span>


