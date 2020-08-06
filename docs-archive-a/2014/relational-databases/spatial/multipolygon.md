---
title: MultiPolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPolygon geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 2c5db358-2a16-49d9-aac5-a74e86813932
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f18fd2485c9b2e62586d9f3e81f76f6cf680dbfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676956"
---
# <a name="multipolygon"></a><span data-ttu-id="b9d29-102">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="b9d29-102">MultiPolygon</span></span>
  <span data-ttu-id="b9d29-103">Una instancia de `MultiPolygon` es una colección de cero o más instancias de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="b9d29-103">A `MultiPolygon` instance is a collection of zero or more `Polygon` instances.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="b9d29-104">Instancias Polygon</span><span class="sxs-lookup"><span data-stu-id="b9d29-104">Polygon Instances</span></span>
 <span data-ttu-id="b9d29-105">En la ilustración siguiente se muestran ejemplos de instancias de `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="b9d29-105">The illustration below shows examples of `MultiPolygon` instances.</span></span>

 <span data-ttu-id="b9d29-106">![Ejemplos de instancias MultiPolygon de geometry](../../database-engine/media/multipolygon.gif "Ejemplos de instancias MultiPolygon de geometry")</span><span class="sxs-lookup"><span data-stu-id="b9d29-106">![Examples of geometry MultiPolygon instances](../../database-engine/media/multipolygon.gif "Examples of geometry MultiPolygon instances")</span></span>

 <span data-ttu-id="b9d29-107">Como se muestra en la ilustración:</span><span class="sxs-lookup"><span data-stu-id="b9d29-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="b9d29-108">La Figura 1 es una instancia de `MultiPolygon` con dos elementos `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="b9d29-108">Figure 1 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="b9d29-109">El límite se define mediante los dos anillos exteriores y los tres interiores.</span><span class="sxs-lookup"><span data-stu-id="b9d29-109">The boundary is defined by the two exterior rings and the three interior rings.</span></span>

-   <span data-ttu-id="b9d29-110">La Figura 2 es una instancia de `MultiPolygon` con dos elementos `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="b9d29-110">Figure 2 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="b9d29-111">El límite se define mediante los dos anillos exteriores y los tres interiores.</span><span class="sxs-lookup"><span data-stu-id="b9d29-111">The boundary is defined by the two exterior rings and the three interior rings.</span></span> <span data-ttu-id="b9d29-112">Los dos elementos `Polygon` forman una intersección en un punto tangente.</span><span class="sxs-lookup"><span data-stu-id="b9d29-112">The two `Polygon` elements intersect at a tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="b9d29-113">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="b9d29-113">Accepted Instances</span></span>
 <span data-ttu-id="b9d29-114">Una instancia `MultiPolygon` es una instancia aceptada si se cumple una de las siguientes condiciones.</span><span class="sxs-lookup"><span data-stu-id="b9d29-114">A `MultiPolygon` instance is accepted one of the following conditions is met.</span></span>

-   <span data-ttu-id="b9d29-115">Es una instancia `MultiPolygon` vacía.</span><span class="sxs-lookup"><span data-stu-id="b9d29-115">It is an empty `MultiPolygon` instance.</span></span>

-   <span data-ttu-id="b9d29-116">Todas las instancias que comprenden la instancia `MultiPolygon` son instancias `Polygon` aceptadas.</span><span class="sxs-lookup"><span data-stu-id="b9d29-116">All instances comprising the `MultiPolygon` instance are accepted `Polygon` instances.</span></span> <span data-ttu-id="b9d29-117">Para obtener más información sobre `Polygon` las instancias aceptadas, vea [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="b9d29-117">For more information on accepted `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

 <span data-ttu-id="b9d29-118">Los ejemplos siguientes muestran instancias `MultiPolygon` aceptadas.</span><span class="sxs-lookup"><span data-stu-id="b9d29-118">The following examples show accepted `MultiPolygon` instances.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
```

 <span data-ttu-id="b9d29-119">En el siguiente ejemplo se muestra una instancia MultiPolygon que producirá una excepción `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="b9d29-119">The following example shows a MultiPolygon instance that will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3)))';
```

 <span data-ttu-id="b9d29-120">La segunda instancia en MultiPolygon es una instancia LineString y no una instancia Polygon aceptada.</span><span class="sxs-lookup"><span data-stu-id="b9d29-120">The second instance in the MultiPolygon is a LineString instance and not an accepted Polygon instance.</span></span>

### <a name="valid-instances"></a><span data-ttu-id="b9d29-121">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="b9d29-121">Valid Instances</span></span>
 <span data-ttu-id="b9d29-122">Una instancia `MultiPolygon` es válida si es una instancia `MultiPolygon` vacía o si cumple los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="b9d29-122">A `MultiPolygon` instance is valid if it is an empty `MultiPolygon` instance or if it meets the following criteria.</span></span>

1.  <span data-ttu-id="b9d29-123">Todas las instancias que comprenden la instancia `MultiPolygon` son instancias `Polygon` válidas.</span><span class="sxs-lookup"><span data-stu-id="b9d29-123">All of the instances comprising the `MultiPolygon` instance are valid `Polygon` instances.</span></span> <span data-ttu-id="b9d29-124">Para `Polygon` las instancias válidas, vea [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="b9d29-124">For valid `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

2.  <span data-ttu-id="b9d29-125">Ninguna de las instancias `Polygon` que comprenden la instancia `MultiPolygon` se superponen.</span><span class="sxs-lookup"><span data-stu-id="b9d29-125">None of the `Polygon` instances comprising the `MultiPolygon` instance overlap.</span></span>

 <span data-ttu-id="b9d29-126">En el siguiente ejemplo se muestran dos instancias `MultiPolygon` válidas y una instancia `MultiPolygon` no válida.</span><span class="sxs-lookup"><span data-stu-id="b9d29-126">The following example shows two valid `MultiPolygon` instances and one invalid `MultiPolygon` instance.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="b9d29-127">`@g2` es válido porque las dos instancias de `Polygon` se tocan solo en un punto tangente.</span><span class="sxs-lookup"><span data-stu-id="b9d29-127">`@g2` is valid because the two `Polygon` instances touch only at a tangent point.</span></span> <span data-ttu-id="b9d29-128">`@g3` no es válido porque los interiores de las dos instancias de `Polygon` se superponen.</span><span class="sxs-lookup"><span data-stu-id="b9d29-128">`@g3` is not valid because the interiors of the two `Polygon` instances overlap each other.</span></span>

## <a name="examples"></a><span data-ttu-id="b9d29-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b9d29-129">Examples</span></span>
 <span data-ttu-id="b9d29-130">El ejemplo siguiente muestra la creación de una instancia de `geometry``MultiPolygon` y devuelve el valor Well-Known Text (WKT) del segundo componente.</span><span class="sxs-lookup"><span data-stu-id="b9d29-130">The following example shows the creation of a `geometry``MultiPolygon` instance and returns the Well-Known Text (WKT) of the second component.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON(((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1)), ((9 9, 9 10, 10 9, 9 9)))');
SELECT @g.STGeometryN(2).STAsText();
```

 <span data-ttu-id="b9d29-131">Este ejemplo crea instancias de una instancia de `MultiPolygon` vacía.</span><span class="sxs-lookup"><span data-stu-id="b9d29-131">This example instantiates an empty `MultiPolygon` instance.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON EMPTY');
```

## <a name="see-also"></a><span data-ttu-id="b9d29-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9d29-132">See Also</span></span>
 <span data-ttu-id="b9d29-133">[Polygon](../spatial/polygon.md) [STArea &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;tipo](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) de datos Geometry&#41;[STPointOnSurface &#40;tipo de datos Geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [datos espaciales](../spatial/spatial-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9d29-133">[Polygon](../spatial/polygon.md) [STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


