---
title: GeometryCollection | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 71d2234a9b73b7647554e364fe3864f089a47a0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676970"
---
# <a name="geometrycollection"></a><span data-ttu-id="9128c-102">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="9128c-102">GeometryCollection</span></span>
  <span data-ttu-id="9128c-103">Un `GeometryCollection` es una colección de cero o más `geometry` o `geography` instancias.</span><span class="sxs-lookup"><span data-stu-id="9128c-103">A `GeometryCollection` is a collection of zero or more `geometry` or `geography` instances.</span></span> <span data-ttu-id="9128c-104">Un `GeometryCollection` puede estar vacío.</span><span class="sxs-lookup"><span data-stu-id="9128c-104">A `GeometryCollection` can be empty.</span></span>  
  
## <a name="geometrycollection-instances"></a><span data-ttu-id="9128c-105">Instancias de GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="9128c-105">GeometryCollection Instances</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="9128c-106">Instancias aceptadas</span><span class="sxs-lookup"><span data-stu-id="9128c-106">Accepted Instances</span></span>  
 <span data-ttu-id="9128c-107">Para que se acepte una instancia de `GeometryCollection`, debe ser una instancia de `GeometryCollection` vacía o todas las instancias que comprenden la instancia de `GeometryCollection` deben ser instancias aceptadas.</span><span class="sxs-lookup"><span data-stu-id="9128c-107">For a `GeometryCollection` instance to be accepted, it must either be an empty `GeometryCollection` instance or all the instances comprising the `GeometryCollection` instance must be accepted instances.</span></span> <span data-ttu-id="9128c-108">El siguiente ejemplo muestra instancias aceptadas.</span><span class="sxs-lookup"><span data-stu-id="9128c-108">The following example shows accepted instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 <span data-ttu-id="9128c-109">El siguiente ejemplo inicia una `System.FormatException` porque la instancia de `LinesString` en la instancia `GeometryCollection` no se acepta.</span><span class="sxs-lookup"><span data-stu-id="9128c-109">The following example throws a `System.FormatException` because the `LinesString` instance in the `GeometryCollection` instance is not accepted.</span></span>  
  
```  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="9128c-110">Instancias válidas</span><span class="sxs-lookup"><span data-stu-id="9128c-110">Valid Instances</span></span>  
 <span data-ttu-id="9128c-111">Una instancia de `GeometryCollection` es válida cuando todas las instancias que comprenden la instancia de  `GeometryCollection` son válidas.</span><span class="sxs-lookup"><span data-stu-id="9128c-111">A `GeometryCollection` instance is valid when all instances that comprise the `GeometryCollection` instance are valid.</span></span> <span data-ttu-id="9128c-112">A continuación se muestran tres instancias de `GeometryCollection` válidas y una instancia que no es válida.</span><span class="sxs-lookup"><span data-stu-id="9128c-112">The following shows three valid `GeometryCollection` instances and one instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="9128c-113">`@g4` no es válida porque la instancia de `Polygon` en la instancia de `GeometryCollection` no es válida.</span><span class="sxs-lookup"><span data-stu-id="9128c-113">`@g4` is not valid because the `Polygon` instance in the `GeometryCollection` instance is not valid.</span></span>  
  
 <span data-ttu-id="9128c-114">Para obtener más información de las instancias aceptadas y las instancias válidas, vea [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md)y [MultiPolygon](multipolygon.md).</span><span class="sxs-lookup"><span data-stu-id="9128c-114">For more information on accepted and valid instances, see [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md), and [MultiPolygon](multipolygon.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9128c-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9128c-115">Examples</span></span>  
 <span data-ttu-id="9128c-116">El ejemplo siguiente crea `geometry``GeometryCollection` con valores de Z en SRID 1 que contiene una instancia `Point` y una instancia `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="9128c-116">The following example instantiates a `geometry``GeometryCollection` with Z values in SRID 1 containing a `Point` instance and a `Polygon` instance.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="9128c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9128c-117">See Also</span></span>  
 [<span data-ttu-id="9128c-118">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9128c-118">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
