---
title: Creación, construcción y consulta de instancias de Geometry | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- planar spatial data [SQL Server], getting started
- geometry data type [SQL Server], getting started
ms.assetid: c6b5c852-37d2-48d0-a8ad-e43bb80d6514
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 539f3f8bb1d9a1c277d6317cc571cf8bcb281833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663323"
---
# <a name="create-construct-and-query-geometry-instances"></a><span data-ttu-id="65a3d-102">Crear, construir y consultar instancias de Geometry</span><span class="sxs-lookup"><span data-stu-id="65a3d-102">Create, Construct, and Query geometry Instances</span></span>
  <span data-ttu-id="65a3d-103">El tipo de datos espacial plano `geometry` representa los datos en un sistema de coordenadas euclidiano (plano).</span><span class="sxs-lookup"><span data-stu-id="65a3d-103">The planar spatial data type, `geometry`, represents data in a Euclidean (flat) coordinate system.</span></span> <span data-ttu-id="65a3d-104">Implementan este tipo como un tipo de datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="65a3d-104">This type is implemented as a common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="65a3d-105">El tipo `geometry` está predefinido y está disponible en cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="65a3d-105">The `geometry` type is predefined and available in each database.</span></span> <span data-ttu-id="65a3d-106">Puede crear columnas de tabla de tipo `geometry` y operar con los datos `geometry` de la misma manera que con los demás tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="65a3d-106">You can create table columns of type `geometry` and operate on `geometry` data in the same manner as you would use other CLR types.</span></span>  
  
 <span data-ttu-id="65a3d-107">El tipo de datos `geometry` (plano) admitido por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cumple con las características simples de Geospatial Consortium (OGC) para la especificación SQL versión 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="65a3d-107">The `geometry` data type (planar) supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0.</span></span>  
  
 <span data-ttu-id="65a3d-108">Para obtener más información acerca de las especificaciones de OGC, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="65a3d-108">For more information on OGC specifications, see the following:</span></span>  
  
-   [<span data-ttu-id="65a3d-109">Especificaciones de OGC, Acceso a características simples, Parte 1 - Arquitectura común</span><span class="sxs-lookup"><span data-stu-id="65a3d-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)  
  
-   [<span data-ttu-id="65a3d-110">Especificaciones de OGC, acceso a características simples, parte 2: opciones de SQL</span><span class="sxs-lookup"><span data-stu-id="65a3d-110">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93629)  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="65a3d-111">admite un subconjunto del estándar GML 3.1 existente que se define en el siguiente esquema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span><span class="sxs-lookup"><span data-stu-id="65a3d-111">supports a subset of the existing GML 3.1 standard which is defined in the following schema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span></span>  
  
##  <a name="creating-or-constructing-a-new-geometry-instance"></a><a name="creating"></a> <span data-ttu-id="65a3d-112">Crear o construir una instancia de geometry</span><span class="sxs-lookup"><span data-stu-id="65a3d-112">Creating or constructing a new geometry instance</span></span>  
  
###  <a name="creating-a-new-geometry-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="65a3d-113">Crear una instancia de geometry a partir de una instancia existente</span><span class="sxs-lookup"><span data-stu-id="65a3d-113">Creating a New geometry Instance from an Existing Instance</span></span>  
 <span data-ttu-id="65a3d-114">El tipo de datos `geometry` proporciona numerosos métodos integrados que puede usar para crear nuevas instancias de `geometry` basadas en instancias existentes.</span><span class="sxs-lookup"><span data-stu-id="65a3d-114">The `geometry` data type provides numerous built-in methods you can use to create new `geometry` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="65a3d-115">**Para crear un búfer alrededor de un objeto geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-115">**To create a buffer around a geometry**</span></span>  
 [<span data-ttu-id="65a3d-116">STBuffer &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-116">STBuffer &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stbuffer-geometry-data-type)  
  
 [<span data-ttu-id="65a3d-117">BufferWithTolerance &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-117">BufferWithTolerance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/bufferwithtolerance-geometry-data-type)  
  
 <span data-ttu-id="65a3d-118">**Para crear una versión simplificada de un objeto geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-118">**To create a simplified version of a geometry**</span></span>  
 [<span data-ttu-id="65a3d-119">Reduce &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-119">Reduce &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/reduce-geometry-data-type)  
  
 <span data-ttu-id="65a3d-120">**Para crear la forma convexa de un objeto geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-120">**To create the convex hull of a geometry**</span></span>  
 [<span data-ttu-id="65a3d-121">STConvexHull &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-121">STConvexHull &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stconvexhull-geometry-data-type)  
  
 <span data-ttu-id="65a3d-122">**Para crear un objeto geometry a partir de la intersección de dos objetos geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-122">**To create a geometry from the intersection of two geometries**</span></span>  
 [<span data-ttu-id="65a3d-123">STIntersection &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-123">STIntersection &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersection-geometry-data-type)  
  
 <span data-ttu-id="65a3d-124">**Para crear un objeto geometry a partir de la unión de dos objetos geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-124">**To create a geometry from the union of two geometries**</span></span>  
 [<span data-ttu-id="65a3d-125">STUnion &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-125">STUnion &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stunion-geometry-data-type)  
  
 <span data-ttu-id="65a3d-126">**Para crear un objeto geometry a partir de los puntos en los que un objeto geometry no se superpone a otro**</span><span class="sxs-lookup"><span data-stu-id="65a3d-126">**To create a geometry from the points where one geometry does not overlap another**</span></span>  
 [<span data-ttu-id="65a3d-127">STDifference &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-127">STDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdifference-geometry-data-type)  
  
 <span data-ttu-id="65a3d-128">**Para crear un objeto geometry a partir de los puntos en los que dos objetos geometry no se superponen**</span><span class="sxs-lookup"><span data-stu-id="65a3d-128">**To create a geometry from the points where two geometries do not overlap**</span></span>  
 [<span data-ttu-id="65a3d-129">STSymDifference &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-129">STSymDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stsymdifference-geometry-data-type)  
  
 <span data-ttu-id="65a3d-130">**Para crear una instancia de Point arbitraria que se encuentra en un objeto geometry existente**</span><span class="sxs-lookup"><span data-stu-id="65a3d-130">**To create an arbitrary Point instance that lies on an existing geometry**</span></span>  
 [<span data-ttu-id="65a3d-131">STPointOnSurface &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-131">STPointOnSurface &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="65a3d-132">Construir una instancia de geometry a partir de datos Well-Known Text</span><span class="sxs-lookup"><span data-stu-id="65a3d-132">Constructing a geometry Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="65a3d-133">El tipo de datos `geometry` proporciona varios métodos integrados que generan un objeto geometry a partir de la representación WKT de Open Geospatial Consortium (OGC).</span><span class="sxs-lookup"><span data-stu-id="65a3d-133">The `geometry` data type provides several built-in methods that generate a geometry from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="65a3d-134">La norma WKT consiste en una cadena de texto que permite intercambiar datos de geometría de forma textual.</span><span class="sxs-lookup"><span data-stu-id="65a3d-134">The WKT standard is a text string that allows geometry data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="65a3d-135">**Para construir cualquier tipo de instancia de geometry a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-135">**To construct any type of geometry instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-136">STGeomFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-136">STGeomFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)  
  
 [<span data-ttu-id="65a3d-137">Parse &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-137">Parse &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/parse-geometry-data-type)  
  
 <span data-ttu-id="65a3d-138">**Para construir una instancia de geometry de tipo Point a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-138">**To construct a geometry Point instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-139">STPointFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-139">STPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="65a3d-140">**Para construir una instancia de geometry de tipo MultiPoint a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-140">**To construct a geometry MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-141">STMPointFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-141">STMPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="65a3d-142">**Para construir una instancia de geometry de tipo LineString a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-142">**To construct a geometry LineString instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-143">STLineFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-143">STLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="65a3d-144">**Para construir una instancia de geometry de tipo MultiLineString a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-144">**To construct a geometry MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-145">STMLineFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-145">STMLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="65a3d-146">**Para construir una instancia de geometry de tipo Polygon a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-146">**To construct a geometry Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-147">STPolyFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-147">STPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="65a3d-148">**Para construir una instancia de geometry de tipo MultiPolygon a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-148">**To construct a geometry MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-149">STMPolyFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-149">STMPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="65a3d-150">**Para construir una instancia de geometry de tipo GeometryCollection a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="65a3d-150">**To construct a geometry GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="65a3d-151">STGeomCollFromText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-151">STGeomCollFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromtext-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="65a3d-152">Construir una instancia de geometry a partir de datos Well-Known Binary</span><span class="sxs-lookup"><span data-stu-id="65a3d-152">Constructing a geometry Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="65a3d-153">WKB es un formato binario especificado por Open Geospatial Consortium (OGC) que permite intercambiar datos de tipo `geometry` entre una aplicación cliente y una base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="65a3d-153">WKB is a binary format specified by the Open Geospatial Consortium (OGC) that permits `geometry` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="65a3d-154">Las funciones siguientes aceptan datos WKB para construir las instancias de geometry:</span><span class="sxs-lookup"><span data-stu-id="65a3d-154">The following functions accept WKB input to construct geometries:</span></span>  
  
 <span data-ttu-id="65a3d-155">**Para construir cualquier tipo de instancia de geometry a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-155">**To construct any type of geometry instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-156">STGeomFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-156">STGeomFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromwkb-geometry-data-type)  
  
 <span data-ttu-id="65a3d-157">**Para construir una instancia de geometry de tipo Point a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-157">**To construct a geometry Point instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-158">STPointFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-158">STPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="65a3d-159">**Para construir una instancia de geometry de tipo MultiPoint a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-159">**To construct a geometry MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-160">STMPointFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-160">STMPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="65a3d-161">**Para construir una instancia de geometry de tipo LineString a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-161">**To construct a geometry LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-162">STLineFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-162">STLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="65a3d-163">**Para construir una instancia de geometry de tipo MultiLineString a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-163">**To construct a geometry MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-164">STMLineFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-164">STMLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="65a3d-165">**Para construir una instancia de geometry de tipo Polygon a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-165">**To construct a geometry Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-166">STPolyFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-166">STPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="65a3d-167">**Para construir una instancia de geometry de tipo MultiPolygon a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-167">**To construct a geometry MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-168">STMPolyFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-168">STMPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="65a3d-169">**Para construir una instancia de geometry de tipo GeometryCollection a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="65a3d-169">**To construct a geometry GeometryCollection instance from WKB input**</span></span>  
 [<span data-ttu-id="65a3d-170">STGeomCollFromWKB &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-170">STGeomCollFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromwkb-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="65a3d-171">Para construir una instancia de geometry a partir de datos de texto GML</span><span class="sxs-lookup"><span data-stu-id="65a3d-171">Constructing a geometry Instance from GML Text Input</span></span>  
 <span data-ttu-id="65a3d-172">El `geometry` tipo de datos proporciona un método que genera una `geometry` instancia de GML, una representación XML de objetos geométricos.</span><span class="sxs-lookup"><span data-stu-id="65a3d-172">The `geometry` data type provides a method that generates a `geometry` instance from GML, an XML representation of geometric objects.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="65a3d-173">admite un subconjunto de GML.</span><span class="sxs-lookup"><span data-stu-id="65a3d-173">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="65a3d-174">**Para construir un tipo de instancia de geometry a partir de datos GML**</span><span class="sxs-lookup"><span data-stu-id="65a3d-174">**To construct any type of geometry instance from GML input**</span></span>  
 [<span data-ttu-id="65a3d-175">GeomFromGml &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-175">GeomFromGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/geomfromgml-geometry-data-type)  
  
  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geometry-instance"></a><a name="returning"></a> <span data-ttu-id="65a3d-176">Devolver Well-Known Text y Well-Known Binary a partir una instancia de geometry</span><span class="sxs-lookup"><span data-stu-id="65a3d-176">Returning Well-Known Text and Well-Known Binary from a geometry Instance</span></span>  
 <span data-ttu-id="65a3d-177">Puede usar los métodos siguientes para devolver el formato WKT o WKB de una instancia de `geometry`:</span><span class="sxs-lookup"><span data-stu-id="65a3d-177">You can use the following methods to return either the WKT or WKB format of a `geometry` instance:</span></span>  
  
 <span data-ttu-id="65a3d-178">**Para devolver la representación WKT de una instancia de geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-178">**To return the WKT representation of a geometry instance**</span></span>  
 [<span data-ttu-id="65a3d-179">STAsText &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-179">STAsText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stastext-geometry-data-type)  
  
 [<span data-ttu-id="65a3d-180">ToString &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-180">ToString &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/tostring-geometry-data-type)  
  
 <span data-ttu-id="65a3d-181">**Para devolver la representación WKT de una instancia de geometry, incluidos cualesquiera valores Z y M.**</span><span class="sxs-lookup"><span data-stu-id="65a3d-181">**To return the WKT representation of a geometry instance including any Z and M values**</span></span>  
 [<span data-ttu-id="65a3d-182">AsTextZM &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-182">AsTextZM &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/astextzm-geometry-data-type)  
  
 <span data-ttu-id="65a3d-183">**Para devolver la representación WKB de una instancia de geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-183">**To return the WKB representation of a geometry instance**</span></span>  
 [<span data-ttu-id="65a3d-184">STAsBinary &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-184">STAsBinary &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stasbinary-geometry-data-type)  
  
 <span data-ttu-id="65a3d-185">**Para devolver la representación GML de una instancia de geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-185">**To return a GML representation of a geometry instance**</span></span>  
 [<span data-ttu-id="65a3d-186">AsGml &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-186">AsGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/asgml-geometry-data-type)  
  
  
  
##  <a name="querying-the-properties-and-behaviors-of-geometry-instances"></a><a name="querying"></a> <span data-ttu-id="65a3d-187">Consultar propiedades y comportamientos de instancias de geometry</span><span class="sxs-lookup"><span data-stu-id="65a3d-187">Querying the Properties and Behaviors of geometry Instances</span></span>  
 <span data-ttu-id="65a3d-188">Todas las `geometry` instancias de tienen varias propiedades que se pueden recuperar a través de los métodos que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona.</span><span class="sxs-lookup"><span data-stu-id="65a3d-188">All `geometry` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="65a3d-189">Los temas siguientes definen las propiedades y los comportamientos de tipos geometry, y los métodos para consultar cada uno.</span><span class="sxs-lookup"><span data-stu-id="65a3d-189">The following topics define the properties and behaviors of geometry types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="65a3d-190">Validez, tipo de instancia e información de GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="65a3d-190">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="65a3d-191">Una vez construida una instancia de `geometry`, puede usar los métodos siguientes para determinar si su formato es correcto, devolver el tipo de instancia o, si es una instancia de una colección, devolver una instancia de `geometry` específica.</span><span class="sxs-lookup"><span data-stu-id="65a3d-191">Once a `geometry` instance is constructed, you can use the following methods to determine if it is well-formed, return the instance type, or, if it is a collection instance, return a specific `geometry` instance.</span></span>  
  
 <span data-ttu-id="65a3d-192">**Para devolver el tipo de instancia de un objeto geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-192">**To return the instance type of a geometry**</span></span>  
 [<span data-ttu-id="65a3d-193">STGeometryType &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-193">STGeometryType &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeometrytype-geometry-data-type)  
  
 <span data-ttu-id="65a3d-194">**Para determinar si un objeto geometry es un tipo de instancia determinado**</span><span class="sxs-lookup"><span data-stu-id="65a3d-194">**To determine if a geometry is a given instance type**</span></span>  
 [<span data-ttu-id="65a3d-195">InstanceOf &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-195">InstanceOf &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/instanceof-geometry-data-type)  
  
 <span data-ttu-id="65a3d-196">**Para determinar si el formato de una instancia de geometry es correcto de acuerdo con su tipo de instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-196">**To determine if a geometry instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="65a3d-197">STIsValid &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-197">STIsValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)  
  
 <span data-ttu-id="65a3d-198">**Para convertir una instancia de geometry en una instancia de geometry con el formato correcto de acuerdo con su tipo de instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-198">**To convert a geometry instance to a well-formed geometry instance with an instance type**</span></span>  
 [<span data-ttu-id="65a3d-199">MakeValid &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-199">MakeValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type)  
  
 <span data-ttu-id="65a3d-200">**Para devolver el número de objetos geometry existente en una instancia de GeometryCollection**</span><span class="sxs-lookup"><span data-stu-id="65a3d-200">**To return the number of geometries in a geometry collection instance**</span></span>  
 [<span data-ttu-id="65a3d-201">STNumGeometries &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-201">STNumGeometries &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumgeometries-geometry-data-type)  
  
 <span data-ttu-id="65a3d-202">Para devolver un objeto geometry específico de una instancia de GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="65a3d-202">To return a specific geometry in a geometry collection instance</span></span>  
 <span data-ttu-id="65a3d-203">[STGeometryN &#40;tipo de datos geometry&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (tipo de datos geometry)</span><span class="sxs-lookup"><span data-stu-id="65a3d-203">[STGeometryN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (geometry Data type)</span></span>  
  
  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="65a3d-204">Número de puntos</span><span class="sxs-lookup"><span data-stu-id="65a3d-204">Number of Points</span></span>  
 <span data-ttu-id="65a3d-205">Todas las instancias no vacías `geometry` se componen de *puntos*.</span><span class="sxs-lookup"><span data-stu-id="65a3d-205">All nonempty `geometry` instances are comprised of *points*.</span></span> <span data-ttu-id="65a3d-206">Estos puntos representan las coordenadas X e Y del plano en el cual se dibujan los objetos geometry.</span><span class="sxs-lookup"><span data-stu-id="65a3d-206">These points represent the X- and Y-coordinates of the plane on which the geometries are drawn.</span></span> <span data-ttu-id="65a3d-207">El tipo de datos de `geometry` proporciona numerosos métodos integrados para consultar los puntos de una instancia.</span><span class="sxs-lookup"><span data-stu-id="65a3d-207">`geometry` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="65a3d-208">**Devolver el número de puntos que comprende una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-208">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="65a3d-209">STNumPoints &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-209">STNumPoints &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type)  
  
 <span data-ttu-id="65a3d-210">**Devolver un punto concreto en una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-210">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="65a3d-211">STPointN</span><span class="sxs-lookup"><span data-stu-id="65a3d-211">STPointN</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="65a3d-212">**Devolver un punto arbitrario que se encuentra en una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-212">**To return an arbitrary point that lies on an instance**</span></span>  
 [<span data-ttu-id="65a3d-213">STPointOnSurface</span><span class="sxs-lookup"><span data-stu-id="65a3d-213">STPointOnSurface</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
 <span data-ttu-id="65a3d-214">**Devolver el punto inicial de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-214">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="65a3d-215">STStartPoint</span><span class="sxs-lookup"><span data-stu-id="65a3d-215">STStartPoint</span></span>](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)  
  
 <span data-ttu-id="65a3d-216">**Devolver el punto final de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-216">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="65a3d-217">STEndpoint</span><span class="sxs-lookup"><span data-stu-id="65a3d-217">STEndpoint</span></span>](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)  
  
 <span data-ttu-id="65a3d-218">**Devolver la coordenada X de una instancia de Point**</span><span class="sxs-lookup"><span data-stu-id="65a3d-218">**To return the X-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="65a3d-219">STX &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-219">STX &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stx-geometry-data-type)  
  
 <span data-ttu-id="65a3d-220">**Para devolver la coordenada Y de una instancia de Point**</span><span class="sxs-lookup"><span data-stu-id="65a3d-220">**To return the Y-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="65a3d-221">STY</span><span class="sxs-lookup"><span data-stu-id="65a3d-221">STY</span></span>](/sql/t-sql/spatial-geometry/sty-geometry-data-type)  
  
 <span data-ttu-id="65a3d-222">**Para devolver el punto central geométrico de una instancia de Polygon, CurvePolygon o MultiPolygon**</span><span class="sxs-lookup"><span data-stu-id="65a3d-222">**To return the geometric center point of a Polygon, CurvePolygon, or MultiPolygon instance**</span></span>  
 [<span data-ttu-id="65a3d-223">STCentroid</span><span class="sxs-lookup"><span data-stu-id="65a3d-223">STCentroid</span></span>](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type)  
  
  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="65a3d-224">Dimensión</span><span class="sxs-lookup"><span data-stu-id="65a3d-224">Dimension</span></span>  
 <span data-ttu-id="65a3d-225">Una instancia de `geometry` no vacía puede ser no dimensional, unidimensional o bidimensional.</span><span class="sxs-lookup"><span data-stu-id="65a3d-225">A nonempty `geometry` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="65a3d-226">`geometries` no dimensionales, como `Point` y `MultiPoint`, no tienen ninguna longitud ni área.</span><span class="sxs-lookup"><span data-stu-id="65a3d-226">Zero-dimensional `geometries`, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="65a3d-227">Los objetos unidimensionales, como `LineString, CircularString, CompoundCurve` y `MultiLineString`, tienen longitud.</span><span class="sxs-lookup"><span data-stu-id="65a3d-227">One-dimensional objects, such as `LineString, CircularString, CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="65a3d-228">Las instancias bidimensionales, como `Polygon`, `CurvePolygon` y `MultiPolygon`, tienen área y longitud.</span><span class="sxs-lookup"><span data-stu-id="65a3d-228">Two-dimensional instances, such as `Polygon`, `CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="65a3d-229">Las instancias vacías informarán de una dimensión de -1 y `GeometryCollection` informará de un área dependiente de los tipos de su contenido.</span><span class="sxs-lookup"><span data-stu-id="65a3d-229">Empty instances will report a dimension of -1, and a `GeometryCollection` will report an area dependent on the types of its contents.</span></span>  
  
 <span data-ttu-id="65a3d-230">**Devolver la dimensión de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-230">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="65a3d-231">STDimension</span><span class="sxs-lookup"><span data-stu-id="65a3d-231">STDimension</span></span>](/sql/t-sql/spatial-geometry/stdimension-geometry-data-type)  
  
 <span data-ttu-id="65a3d-232">**Devolver la longitud de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-232">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="65a3d-233">STLength</span><span class="sxs-lookup"><span data-stu-id="65a3d-233">STLength</span></span>](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)  
  
 <span data-ttu-id="65a3d-234">**Devolver el área de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-234">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="65a3d-235">STArea</span><span class="sxs-lookup"><span data-stu-id="65a3d-235">STArea</span></span>](/sql/t-sql/spatial-geometry/starea-geometry-data-type)  
  
  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="65a3d-236">Vacía</span><span class="sxs-lookup"><span data-stu-id="65a3d-236">Empty</span></span>  
 <span data-ttu-id="65a3d-237">Una instancia *vacía* no `geometry` tiene ningún punto.</span><span class="sxs-lookup"><span data-stu-id="65a3d-237">An *empty*`geometry` instance does not have any points.</span></span> <span data-ttu-id="65a3d-238">La longitud de instancias de `LineString, CircularString`, `CompoundCurve` y `MultiLineString` es cero.</span><span class="sxs-lookup"><span data-stu-id="65a3d-238">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is zero.</span></span> <span data-ttu-id="65a3d-239">El área de las instancias de `Polygon`, `CurvePolygon` y `MultiPolygon` vacías es 0.</span><span class="sxs-lookup"><span data-stu-id="65a3d-239">The area of empty `Polygon`, `CurvePolygon`, and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="65a3d-240">**Para determinar si una instancia está vacía**</span><span class="sxs-lookup"><span data-stu-id="65a3d-240">**To determine if an instance is empty**</span></span>  
 <span data-ttu-id="65a3d-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="65a3d-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span></span>  
  
  
  
###  <a name="simple"></a><a name="simple"></a> <span data-ttu-id="65a3d-242">Simple</span><span class="sxs-lookup"><span data-stu-id="65a3d-242">Simple</span></span>  
 <span data-ttu-id="65a3d-243">Para `geometry` que un de la instancia sea *simple*, debe cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="65a3d-243">For a `geometry` of the instance to be *simple*, it must meet both of these requirements:</span></span>  
  
-   <span data-ttu-id="65a3d-244">Cada figura de la instancia no debe cortarse, excepto en sus extremos.</span><span class="sxs-lookup"><span data-stu-id="65a3d-244">Each figure of the instance must not intersect itself, except at its endpoints.</span></span>  
  
-   <span data-ttu-id="65a3d-245">Ninguna de las dos figuras de la instancia puede cortarse en un punto que no esté en ambos de sus límites.</span><span class="sxs-lookup"><span data-stu-id="65a3d-245">No two figures of the instance can intersect each other at a point that is not in both of their boundaries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65a3d-246">Los objetos geometry vacíos son siempre simples.</span><span class="sxs-lookup"><span data-stu-id="65a3d-246">Empty geometries are always simple.</span></span>  
  
 <span data-ttu-id="65a3d-247">**Determinar si una instancia es simple**</span><span class="sxs-lookup"><span data-stu-id="65a3d-247">**To determine if an instance is simple**</span></span>  
 <span data-ttu-id="65a3d-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="65a3d-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span></span>  
  
  
  
###  <a name="boundary-interior-and-exterior"></a><a name="boundary"></a> <span data-ttu-id="65a3d-249">Límite, interior y exterior</span><span class="sxs-lookup"><span data-stu-id="65a3d-249">Boundary, Interior, and Exterior</span></span>  
 <span data-ttu-id="65a3d-250">El *interior* de una `geometry` instancia es el espacio ocupado por la instancia y el *exterior* es el espacio no ocupado.</span><span class="sxs-lookup"><span data-stu-id="65a3d-250">The *interior* of a `geometry` instance is the space occupied by the instance, and the *exterior* is the space not occupied it.</span></span>  
  
 <span data-ttu-id="65a3d-251">El*límite* lo define OGC de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="65a3d-251">*Boundary* is defined by the OGC as follows:</span></span>  
  
-   <span data-ttu-id="65a3d-252">La instancias de `Point` y `MultiPoint` no tienen un límite.</span><span class="sxs-lookup"><span data-stu-id="65a3d-252">`Point` and `MultiPoint` instances do not have a boundary.</span></span>  
  
-   <span data-ttu-id="65a3d-253">Los límites de `LineString` y `MultiLineString` están formados por los puntos de inicio y de fin, quitando los que se producen un número par de veces.</span><span class="sxs-lookup"><span data-stu-id="65a3d-253">`LineString` and `MultiLineString` boundaries are formed by the start points and end points, removing those that occur an even number of times.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 1, 0 0, 1 0, 0 1), (1 1, 1 0))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="65a3d-254">El límite de una instancia de `Polygon` o `MultiPolygon` es el conjunto de sus anillos.</span><span class="sxs-lookup"><span data-stu-id="65a3d-254">The boundary of a `Polygon` or `MultiPolygon` instance is the set of its rings.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0), (1 1, 1 2, 2 2, 2 1, 1 1))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="65a3d-255">**Devolver el límite de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-255">**To return the boundary of an instance**</span></span>  
 [<span data-ttu-id="65a3d-256">STBoundary</span><span class="sxs-lookup"><span data-stu-id="65a3d-256">STBoundary</span></span>](/sql/t-sql/spatial-geometry/stboundary-geometry-data-type)  
  
  
  
###  <a name="envelope"></a><a name="envelope"></a> <span data-ttu-id="65a3d-257">Envolvente</span><span class="sxs-lookup"><span data-stu-id="65a3d-257">Envelope</span></span>  
 <span data-ttu-id="65a3d-258">El *sobre* de una `geometry` instancia, también conocido como el *cuadro de límite*, es el rectángulo alineado con el eje formado por las coordenadas mínima Y máxima (X, Y) de la instancia.</span><span class="sxs-lookup"><span data-stu-id="65a3d-258">The *envelope* of a `geometry` instance, also known as the *bounding box*, is the axis-aligned rectangle formed by the minimum and maximum (X,Y) coordinates of the instance.</span></span>  
  
 <span data-ttu-id="65a3d-259">**Para devolver la envolvente de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-259">**To return the envelope of an instance**</span></span>  
 [<span data-ttu-id="65a3d-260">STEnvelope</span><span class="sxs-lookup"><span data-stu-id="65a3d-260">STEnvelope</span></span>](/sql/t-sql/spatial-geometry/stenvelope-geometry-data-type)  
  
  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="65a3d-261">Clausura</span><span class="sxs-lookup"><span data-stu-id="65a3d-261">Closure</span></span>  
 <span data-ttu-id="65a3d-262">Una instancia *cerrada* `geometry` es una figura cuyos puntos de inicio y de finalización son los mismos.</span><span class="sxs-lookup"><span data-stu-id="65a3d-262">A *closed*`geometry` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="65a3d-263">Las instancias `Polygon` se consideran cerradas.</span><span class="sxs-lookup"><span data-stu-id="65a3d-263">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="65a3d-264">Las instancias `Point` no son cerradas.</span><span class="sxs-lookup"><span data-stu-id="65a3d-264">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="65a3d-265">Un anillo es una instancia de `LineString` simple y cerrada.</span><span class="sxs-lookup"><span data-stu-id="65a3d-265">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="65a3d-266">**Para determinar si una instancia está cerrada**</span><span class="sxs-lookup"><span data-stu-id="65a3d-266">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="65a3d-267">STIsClosed</span><span class="sxs-lookup"><span data-stu-id="65a3d-267">STIsClosed</span></span>](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)  
  
 <span data-ttu-id="65a3d-268">**Para determinar si una instancia es un anillo**</span><span class="sxs-lookup"><span data-stu-id="65a3d-268">**To determine if an instance is a ring**</span></span>  
 [<span data-ttu-id="65a3d-269">STIsRing</span><span class="sxs-lookup"><span data-stu-id="65a3d-269">STIsRing</span></span>](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)  
  
 <span data-ttu-id="65a3d-270">**Para devolver el anillo exterior de una instancia de Polygon**</span><span class="sxs-lookup"><span data-stu-id="65a3d-270">**To return the exterior ring of a Polygon instance**</span></span>  
 [<span data-ttu-id="65a3d-271">STExteriorRing</span><span class="sxs-lookup"><span data-stu-id="65a3d-271">STExteriorRing</span></span>](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type)  
  
 <span data-ttu-id="65a3d-272">**Para devolver el número de anillos interiores de un Polygon**</span><span class="sxs-lookup"><span data-stu-id="65a3d-272">**To return the number of interior rings in a Polygon**</span></span>  
 [<span data-ttu-id="65a3d-273">STNumInteriorRing</span><span class="sxs-lookup"><span data-stu-id="65a3d-273">STNumInteriorRing</span></span>](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type)  
  
 <span data-ttu-id="65a3d-274">**Devolver un anillo interior especificado de un Polygon**</span><span class="sxs-lookup"><span data-stu-id="65a3d-274">**To return a specified interior ring of a Polygon**</span></span>  
 [<span data-ttu-id="65a3d-275">STInteriorRingN</span><span class="sxs-lookup"><span data-stu-id="65a3d-275">STInteriorRingN</span></span>](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type)  
  
  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="65a3d-276">Identificador de referencia espacial (SRID)</span><span class="sxs-lookup"><span data-stu-id="65a3d-276">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="65a3d-277">El identificador de referencia espacial (SRID) es un identificador que especifica en qué sistema de coordenadas está representada la instancia de `geometry`.</span><span class="sxs-lookup"><span data-stu-id="65a3d-277">The spatial reference ID (SRID) is an identifier specifying which coordinate system the `geometry` instance is represented in.</span></span> <span data-ttu-id="65a3d-278">Dos instancias con SRID diferentes son incomparables.</span><span class="sxs-lookup"><span data-stu-id="65a3d-278">Two instances with different SRIDs are incomparable.</span></span>  
  
 <span data-ttu-id="65a3d-279">**Para establecer o devolver el SRID de una instancia**</span><span class="sxs-lookup"><span data-stu-id="65a3d-279">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="65a3d-280">STSrid</span><span class="sxs-lookup"><span data-stu-id="65a3d-280">STSrid</span></span>](/sql/t-sql/spatial-geometry/stsrid-geometry-data-type)  
  
 <span data-ttu-id="65a3d-281">Esta propiedad se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="65a3d-281">This property can be modified.</span></span>  
  
  
  
##  <a name="determining-relationships-between-geometry-instances"></a><a name="rel"></a> <span data-ttu-id="65a3d-282">Determinar las relaciones entre instancias de geometry</span><span class="sxs-lookup"><span data-stu-id="65a3d-282">Determining Relationships between geometry Instances</span></span>  
 <span data-ttu-id="65a3d-283">El tipo de datos `geometry` proporciona muchos métodos integrados que puede usar para determinar las relaciones entre dos instancias de `geometry`.</span><span class="sxs-lookup"><span data-stu-id="65a3d-283">The `geometry` data type provides many built-in methods you can use to determine relationships between two `geometry` instances.</span></span>  
  
 <span data-ttu-id="65a3d-284">**Para determinar si dos instancias comprenden el mismo conjunto de puntos**</span><span class="sxs-lookup"><span data-stu-id="65a3d-284">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="65a3d-285">STEquals</span><span class="sxs-lookup"><span data-stu-id="65a3d-285">STEquals</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="65a3d-286">**Para determinar si dos instancias no son contiguas**</span><span class="sxs-lookup"><span data-stu-id="65a3d-286">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="65a3d-287">STDisjoint</span><span class="sxs-lookup"><span data-stu-id="65a3d-287">STDisjoint</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="65a3d-288">**Para determinar si dos instancias contienen puntos que forman una intersección**</span><span class="sxs-lookup"><span data-stu-id="65a3d-288">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="65a3d-289">STIntersects</span><span class="sxs-lookup"><span data-stu-id="65a3d-289">STIntersects</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="65a3d-290">**Para determinar si dos instancias se tocan**</span><span class="sxs-lookup"><span data-stu-id="65a3d-290">**To determine if two instances touch**</span></span>  
 [<span data-ttu-id="65a3d-291">STTouches</span><span class="sxs-lookup"><span data-stu-id="65a3d-291">STTouches</span></span>](/sql/t-sql/spatial-geometry/sttouches-geometry-data-type)  
  
 <span data-ttu-id="65a3d-292">**Para determinar si dos instancias se superponen**</span><span class="sxs-lookup"><span data-stu-id="65a3d-292">**To determine if two instances overlap**</span></span>  
 [<span data-ttu-id="65a3d-293">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="65a3d-293">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="65a3d-294">**Para determinar si dos instancias se cruzan**</span><span class="sxs-lookup"><span data-stu-id="65a3d-294">**To determine if two instances cross**</span></span>  
 [<span data-ttu-id="65a3d-295">STCrosses</span><span class="sxs-lookup"><span data-stu-id="65a3d-295">STCrosses</span></span>](/sql/t-sql/spatial-geometry/stcrosses-geometry-data-type)  
  
 <span data-ttu-id="65a3d-296">**Para determinar si una instancia está dentro de otra**</span><span class="sxs-lookup"><span data-stu-id="65a3d-296">**To determine if one instance is within another**</span></span>  
 [<span data-ttu-id="65a3d-297">STWithin</span><span class="sxs-lookup"><span data-stu-id="65a3d-297">STWithin</span></span>](/sql/t-sql/spatial-geometry/stwithin-geometry-data-type)  
  
 <span data-ttu-id="65a3d-298">**Para determinar si una instancia contiene a otra**</span><span class="sxs-lookup"><span data-stu-id="65a3d-298">**To determine if one instance contains another**</span></span>  
 [<span data-ttu-id="65a3d-299">STContains</span><span class="sxs-lookup"><span data-stu-id="65a3d-299">STContains</span></span>](/sql/t-sql/spatial-geometry/stcontains-geometry-data-type)  
  
 <span data-ttu-id="65a3d-300">**Para determinar si una instancia se superpone a otra**</span><span class="sxs-lookup"><span data-stu-id="65a3d-300">**To determine if one instance overlaps another**</span></span>  
 [<span data-ttu-id="65a3d-301">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="65a3d-301">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="65a3d-302">**Para determinar si existe una relación espacial entre dos instancias**</span><span class="sxs-lookup"><span data-stu-id="65a3d-302">**To determine if two instances are spatially related**</span></span>  
 [<span data-ttu-id="65a3d-303">STRelate</span><span class="sxs-lookup"><span data-stu-id="65a3d-303">STRelate</span></span>](/sql/t-sql/spatial-geometry/strelate-geometry-data-type)  
  
 <span data-ttu-id="65a3d-304">**Para determinar la distancia más corta entre los puntos de dos objetos geometry**</span><span class="sxs-lookup"><span data-stu-id="65a3d-304">**To determine the shortest distance between points in two geometries**</span></span>  
 [<span data-ttu-id="65a3d-305">STDistance</span><span class="sxs-lookup"><span data-stu-id="65a3d-305">STDistance</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
  
  
##  <a name="geometry-instances-default-to-zero-srid"></a><a name="defaultsrid"></a> <span data-ttu-id="65a3d-306">Las instancias de geometry tienen como valor predeterminado SRID cero</span><span class="sxs-lookup"><span data-stu-id="65a3d-306">geometry Instances Default to Zero SRID</span></span>  
 <span data-ttu-id="65a3d-307">El SRID predeterminado para instancias de `geometry` en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es 0.</span><span class="sxs-lookup"><span data-stu-id="65a3d-307">The default SRID for `geometry` instances in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 0.</span></span> <span data-ttu-id="65a3d-308">Con los datos espaciales de `geometry`, no se necesita el SRID específico de la instancia espacial para realizar cálculos; por tanto, las instancias pueden encontrarse en un espacio plano indefinido.</span><span class="sxs-lookup"><span data-stu-id="65a3d-308">With `geometry` spatial data, the specific SRID of the spatial instance is not required to perform calculations; thus, instances can reside in undefined planar space.</span></span> <span data-ttu-id="65a3d-309">Para indicar el espacio plano indefinido en los cálculos de métodos de tipo de datos `geometry`, el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa SRID 0.</span><span class="sxs-lookup"><span data-stu-id="65a3d-309">To indicate undefined planar space in the calculations of `geometry` data type methods, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses SRID 0.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="65a3d-310">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="65a3d-310">Examples</span></span>  
 <span data-ttu-id="65a3d-311">En los dos ejemplos siguientes se muestra cómo agregar y consultar datos de geometry.</span><span class="sxs-lookup"><span data-stu-id="65a3d-311">The following two examples show how to add and query geometry data.</span></span>  
  
-   <span data-ttu-id="65a3d-312">En el primer ejemplo se crea una tabla con una columna de identidad y una columna de tipo `geometry` , `GeomCol1`.</span><span class="sxs-lookup"><span data-stu-id="65a3d-312">The first example creates a table with an identity column and a `geometry` column `GeomCol1`.</span></span> <span data-ttu-id="65a3d-313">Una tercera columna representa la columna de tipo `geometry` en su representación Well-Known Text (WKT) de Open Geospatial Consortium (OGC) y utiliza el método `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="65a3d-313">A third column renders the `geometry` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="65a3d-314">A continuación se insertan dos filas: una que contiene una instancia de `LineString` de `geometry`y otra que contiene una instancia de `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="65a3d-314">Two rows are then inserted: one row contains a `LineString` instance of `geometry`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeomCol1 geometry,   
        GeomCol2 AS GeomCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('LINESTRING (100 100, 20 180, 180 180)', 0));  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('POLYGON ((0 0, 150 0, 150 150, 0 150, 0 0))', 0));  
    GO  
    ```  
  
-   <span data-ttu-id="65a3d-315">En el segundo ejemplo se usa el método `STIntersection()` para devolver los puntos de intersección de las dos instancias de `geometry` insertadas previamente.</span><span class="sxs-lookup"><span data-stu-id="65a3d-315">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geometry` instances intersect.</span></span>  
  
    ```  
    DECLARE @geom1 geometry;  
    DECLARE @geom2 geometry;  
    DECLARE @result geometry;  
  
    SELECT @geom1 = GeomCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geom2 = GeomCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geom1.STIntersection(@geom2);  
    SELECT @result.STAsText();  
    ```  
  
  
  
## <a name="see-also"></a><span data-ttu-id="65a3d-316">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65a3d-316">See Also</span></span>  
 [<span data-ttu-id="65a3d-317">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="65a3d-317">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
