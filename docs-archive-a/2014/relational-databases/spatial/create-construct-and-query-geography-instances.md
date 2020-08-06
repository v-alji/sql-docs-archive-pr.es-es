---
title: Creación, construcción y consulta de instancias de Geography | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server]
- geodetic data type [SQL Server]
- geography data type [SQL Server], about geography data type
ms.assetid: b585851e-d15b-411f-adeb-aeabeb777c0b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: d744457cc517a6172cca96b27eae1f456deca24e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663325"
---
# <a name="create-construct-and-query-geography-instances"></a><span data-ttu-id="c3971-102">Crear, construir y consultar instancias de Geography</span><span class="sxs-lookup"><span data-stu-id="c3971-102">Create, Construct, and Query geography Instances</span></span>
  <span data-ttu-id="c3971-103">El tipo de datos espacial geography, `geography`, representa los datos en un sistema de coordenadas de tierra redonda.</span><span class="sxs-lookup"><span data-stu-id="c3971-103">The geography spatial data type, `geography`, represents data in a round-earth coordinate system.</span></span> <span data-ttu-id="c3971-104">Se implementa como un tipo de datos de .NET CLR (Common Language Runtime) en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3971-104">This type is implemented as a .NET common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c3971-105">El tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` almacena los datos elipsoidales (globo), como coordenadas de latitud y longitud de GPS.</span><span class="sxs-lookup"><span data-stu-id="c3971-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` data type stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>  
  
 <span data-ttu-id="c3971-106">El tipo `geography` está predefinido y está disponible en cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3971-106">The `geography` type is predefined and available in each database.</span></span> <span data-ttu-id="c3971-107">Puede crear columnas de tabla de tipo `geography` y operar con los datos `geography` de la misma manera que con los demás tipos proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="c3971-107">You can create table columns of type `geography` and operate on `geography` data in the same manner as you would use other system-supplied types.</span></span>  
  
##  <a name="creating-or-constructing-a-new-geography-instance"></a><a name="creating"></a> <span data-ttu-id="c3971-108">Crear o construir una instancia de geography</span><span class="sxs-lookup"><span data-stu-id="c3971-108">Creating or constructing a new geography instance</span></span>  
  
###  <a name="creating-a-new-geography-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="c3971-109">Crear una instancia de geography a partir de una instancia existente</span><span class="sxs-lookup"><span data-stu-id="c3971-109">Creating a New geography Instance from an Existing Instance</span></span>  
 <span data-ttu-id="c3971-110">El tipo de datos `geography` proporciona numerosos métodos integrados que puede usar para crear nuevas instancias de `geography` basadas en instancias existentes.</span><span class="sxs-lookup"><span data-stu-id="c3971-110">The `geography` data type provides numerous built-in methods you can use to create new `geography` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="c3971-111">**Crear un búfer alrededor de un objeto geography**</span><span class="sxs-lookup"><span data-stu-id="c3971-111">**To create a buffer around a geography**</span></span>  
 [<span data-ttu-id="c3971-112">STBuffer &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-112">STBuffer &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stbuffer-geography-data-type)  
  
 <span data-ttu-id="c3971-113">**Para crear un búfer alrededor de un objeto geography, permitiendo una tolerancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-113">**To create a buffer around a geography, allowing for a tolerance**</span></span>  
 [<span data-ttu-id="c3971-114">BufferWithTolerance &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-114">BufferWithTolerance &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/bufferwithtolerance-geography-data-type)  
  
 <span data-ttu-id="c3971-115">**Crear una geografía a partir de la intersección de dos instancias de geografía**</span><span class="sxs-lookup"><span data-stu-id="c3971-115">**To create a geography from the intersection of two geography instances**</span></span>  
 [<span data-ttu-id="c3971-116">STIntersection &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-116">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="c3971-117">**Crear una geografía a partir de la unión de dos instancias de geografía**</span><span class="sxs-lookup"><span data-stu-id="c3971-117">**To create a geography from the union of two geography instances**</span></span>  
 [<span data-ttu-id="c3971-118">STUnion &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-118">STUnion &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stunion-geography-data-type)  
  
 <span data-ttu-id="c3971-119">**Para crear un objeto geography a partir de los puntos en los que un objeto geography no se superpone a otro**</span><span class="sxs-lookup"><span data-stu-id="c3971-119">**To create a geography from the points where one geography does not overlap another**</span></span>  
 [<span data-ttu-id="c3971-120">STDifference &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-120">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="c3971-121">Construir una instancia de geography a partir de datos Well-Known Text</span><span class="sxs-lookup"><span data-stu-id="c3971-121">Constructing a geography Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="c3971-122">El tipo de datos `geography` proporciona varios métodos integrados que generan un objeto geography a partir de la representación WKT de Open Geospatial Consortium (OGC).</span><span class="sxs-lookup"><span data-stu-id="c3971-122">The `geography` data type provides several built-in methods that generate a geography from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="c3971-123">La norma WKT consiste en una cadena de texto que permite intercambiar datos de geography de forma textual.</span><span class="sxs-lookup"><span data-stu-id="c3971-123">The WKT standard is a text string that allows geography data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="c3971-124">**Para construir cualquier tipo de instancia de geography a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-124">**To construct any type of geography instance from WKT input**</span></span>  
 [<span data-ttu-id="c3971-125">STGeomFromText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-125">STGeomFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)  
  
 [<span data-ttu-id="c3971-126">Parse &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-126">Parse &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/parse-geography-data-type)  
  
 <span data-ttu-id="c3971-127">**Para construir una instancia de geography de tipo Point a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-127">**To construct a geography Point instance from WKT input**</span></span>  
 [<span data-ttu-id="c3971-128">STPointFromText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-128">STPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromtext-geography-data-type)  
  
 <span data-ttu-id="c3971-129">**Para construir una instancia de geography de tipo MultiPoint a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-129">**To construct a geography MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="c3971-130">STMPointFromText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-130">STMPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromtext-geography-data-type)  
  
 <span data-ttu-id="c3971-131">**Para construir una instancia de geography de tipo LineString a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-131">**To construct a geography LineString instance from WKT input**</span></span>  
 <span data-ttu-id="c3971-132">STLineFromText (tipo de datos geography)</span><span class="sxs-lookup"><span data-stu-id="c3971-132">STLineFromText (geography Data Type)</span></span>  
  
 <span data-ttu-id="c3971-133">**Para construir una instancia de geography de tipo MultiLineString a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-133">**To construct a geography MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="c3971-134">STMLineFromText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-134">STMLineFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromtext-geography-data-type)  
  
 <span data-ttu-id="c3971-135">**Para construir una instancia de geography de tipo Polygon a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-135">**To construct a geography Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="c3971-136">STPolyFromText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-136">STPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="c3971-137">**Para construir una instancia de geography de tipo MultiPolygon a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-137">**To construct a geography MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="c3971-138">STMPolyFromText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-138">STMPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="c3971-139">**Para construir una instancia de geography de tipo GeometryCollection a partir de datos WKT**</span><span class="sxs-lookup"><span data-stu-id="c3971-139">**To construct a geography GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="c3971-140">STGeomCollFromText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-140">STGeomCollFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomcollfromtext-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="c3971-141">Construir una instancia de geography a partir de datos Well-Known Binary</span><span class="sxs-lookup"><span data-stu-id="c3971-141">Constructing a geography Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="c3971-142">WKB es un formato binario especificado por OGC que permite intercambiar datos de tipo `Geography` entre una aplicación cliente y una base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="c3971-142">WKB is a binary format specified by the OGC that permits `Geography` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="c3971-143">Las funciones siguientes aceptan datos WKB para construir las instancias de geography:</span><span class="sxs-lookup"><span data-stu-id="c3971-143">The following functions accept WKB input to construct geography instances:</span></span>  
  
 <span data-ttu-id="c3971-144">**Para construir cualquier tipo de instancia de geography a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-144">**To construct any type of geography instance from WKB input**</span></span>  
 [<span data-ttu-id="c3971-145">STGeomFromWKB &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-145">STGeomFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromwkb-geography-data-type)  
  
 <span data-ttu-id="c3971-146">**Para construir una instancia de geography de tipo Point a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-146">**To construct a geography Point instance from WKB input**</span></span>  
 [<span data-ttu-id="c3971-147">STPointFromWKB &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-147">STPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="c3971-148">**Para construir una instancia de geography de tipo MultiPoint a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-148">**To construct a geography MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="c3971-149">STMPointFromWKB &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-149">STMPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="c3971-150">**Para construir una instancia de geography de tipo LineString a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-150">**To construct a geography LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="c3971-151">STLineFromWKB &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-151">STLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="c3971-152">**Para construir una instancia de geography de tipo MultiLineString a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-152">**To construct a geography MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="c3971-153">STMLineFromWKB &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-153">STMLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="c3971-154">**Para construir una instancia de geography de tipo Polygon a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-154">**To construct a geography Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="c3971-155">STPolyFromWKB &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-155">STPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="c3971-156">**Para construir una instancia de geography de tipo MultiPolygon a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-156">**To construct a geography MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="c3971-157">STMPolyFromWKB &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-157">STMPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="c3971-158">**Para construir una instancia de geography de tipo GeometryCollection a partir de datos WKB**</span><span class="sxs-lookup"><span data-stu-id="c3971-158">**To construct a geography GeometryCollection instance from WKB input**</span></span>  
 <span data-ttu-id="c3971-159">[STGeomCollFromWKB &#40;tipo de datos geography&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (tipo de datos geography)</span><span class="sxs-lookup"><span data-stu-id="c3971-159">[STGeomCollFromWKB &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (geography Data Type)</span></span>  
  
###  <a name="constructing-a-geography-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="c3971-160">Para construir una instancia de geography a partir de datos de texto GML</span><span class="sxs-lookup"><span data-stu-id="c3971-160">Constructing a geography Instance from GML Text Input</span></span>  
 <span data-ttu-id="c3971-161">El `geography` tipo de datos proporciona un método que genera una `geography` instancia de GML, una representación XML de una `geography` instancia de.</span><span class="sxs-lookup"><span data-stu-id="c3971-161">The `geography` data type provides a method that generates a `geography` instance from GML, an XML representation of a `geography` instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3971-162">admite un subconjunto de GML.</span><span class="sxs-lookup"><span data-stu-id="c3971-162">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="c3971-163">Para obtener más información sobre el lenguaje de marcado de geografía, vea las especificaciones de OGC: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span><span class="sxs-lookup"><span data-stu-id="c3971-163">For more information on Geography Markup Language, see the OGC Specification: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 <span data-ttu-id="c3971-164">**Para construir cualquier tipo de instancia de geography a partir de datos de GML**</span><span class="sxs-lookup"><span data-stu-id="c3971-164">**To construct any type of geography instance from GML input**</span></span>  
 [<span data-ttu-id="c3971-165">GeomFromGML &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-165">GeomFromGML &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/geomfromgml-geography-data-type)  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geography-instance"></a><a name="returning"></a> <span data-ttu-id="c3971-166">Devolver Well-Known Text y Well-Known Binary a partir una instancia de geography</span><span class="sxs-lookup"><span data-stu-id="c3971-166">Returning Well-Known Text and Well-Known Binary from a geography Instance</span></span>  
 <span data-ttu-id="c3971-167">Puede usar los métodos siguientes para devolver el formato WKT o WKB de una instancia de `geography`:</span><span class="sxs-lookup"><span data-stu-id="c3971-167">You can use the following methods to return either the WKT or WKB format of a `geography` instance:</span></span>  
  
 <span data-ttu-id="c3971-168">**Para devolver la representación WKT de una instancia de geography**</span><span class="sxs-lookup"><span data-stu-id="c3971-168">**To return the WKT representation of a geography instance**</span></span>  
 [<span data-ttu-id="c3971-169">STAsText &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-169">STAsText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stastext-geography-data-type)  
  
 [<span data-ttu-id="c3971-170">ToString &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-170">ToString &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/tostring-geography-data-type)  
  
 <span data-ttu-id="c3971-171">**Para devolver la representación WKT de una instancia de geography, incluidos cualesquiera valores Z y M.**</span><span class="sxs-lookup"><span data-stu-id="c3971-171">**To return the WKT representation of a geography instance including any Z and M values**</span></span>  
 [<span data-ttu-id="c3971-172">AsTextZM &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-172">AsTextZM &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/astextzm-geography-data-type)  
  
 <span data-ttu-id="c3971-173">**Para devolver la representación WKB de una instancia de geography**</span><span class="sxs-lookup"><span data-stu-id="c3971-173">**To return the WKB representation of a geography instance**</span></span>  
 [<span data-ttu-id="c3971-174">STAsBinary &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-174">STAsBinary &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stasbinary-geography-data-type)  
  
 <span data-ttu-id="c3971-175">**Para devolver la representación GML de una instancia de geography**</span><span class="sxs-lookup"><span data-stu-id="c3971-175">**To return a GML representation of a geography instance**</span></span>  
 [<span data-ttu-id="c3971-176">AsGml &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-176">AsGml &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/asgml-geography-data-type)  
  
##  <a name="querying-the-properties-and-behaviors-of-geography-instances"></a><a name="query"></a> <span data-ttu-id="c3971-177">Consultar propiedades y comportamientos de instancias de geography</span><span class="sxs-lookup"><span data-stu-id="c3971-177">Querying the Properties and Behaviors of geography Instances</span></span>  
 <span data-ttu-id="c3971-178">Todas las `geography` instancias de tienen varias propiedades que se pueden recuperar a través de los métodos que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona.</span><span class="sxs-lookup"><span data-stu-id="c3971-178">All `geography` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="c3971-179">Los temas siguientes definen las propiedades y los comportamientos de los tipos geography y los métodos para consultar cada uno.</span><span class="sxs-lookup"><span data-stu-id="c3971-179">The following topics define the properties and behaviors of geography types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="c3971-180">Validez, tipo de instancia e información de GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="c3971-180">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="c3971-181">Una vez construida una instancia de `geography`, puede usar los métodos siguientes para devolver el tipo de instancia o, si es una instancia de `GeometryCollection`, devolver una instancia de `geography` específica.</span><span class="sxs-lookup"><span data-stu-id="c3971-181">After a `geography` instance is constructed, you can use the following methods to return the instance type, or if it is a `GeometryCollection` instance, return a specific `geography` instance.</span></span>  
  
 <span data-ttu-id="c3971-182">**Para devolver el tipo de instancia de una geografía**</span><span class="sxs-lookup"><span data-stu-id="c3971-182">**To return the instance type of a geography**</span></span>  
 [<span data-ttu-id="c3971-183">STGeometryType &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-183">STGeometryType &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeometrytype-geography-data-type)  
  
 <span data-ttu-id="c3971-184">**Para determinar si una geografía es un tipo de instancia determinado**</span><span class="sxs-lookup"><span data-stu-id="c3971-184">**To determine if a geography is a given instance type**</span></span>  
 [<span data-ttu-id="c3971-185">InstanceOf &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-185">InstanceOf &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/instanceof-geography-data-type)  
  
 <span data-ttu-id="c3971-186">**Para determinar si el formato de una instancia de geografía es correcto de acuerdo con su tipo de instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-186">**To determine if a geography instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="c3971-187">STNumGeometries &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-187">STNumGeometries &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumgeometries-geography-data-type)  
  
 <span data-ttu-id="c3971-188">**Para devolver un objeto geography específico de una instancia de GeometryCollection**</span><span class="sxs-lookup"><span data-stu-id="c3971-188">**To return a specific geography in a GeometryCollection instance**</span></span>  
 <span data-ttu-id="c3971-189">[STGeometryN &#40;tipo de datos geography&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (tipo de datos geography)</span><span class="sxs-lookup"><span data-stu-id="c3971-189">[STGeometryN &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (geography Data Type)</span></span>  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="c3971-190">Número de puntos</span><span class="sxs-lookup"><span data-stu-id="c3971-190">Number of Points</span></span>  
 <span data-ttu-id="c3971-191">Todas las instancias no vacías `geography` se componen de *puntos*.</span><span class="sxs-lookup"><span data-stu-id="c3971-191">All nonempty `geography` instances are comprised of *points*.</span></span> <span data-ttu-id="c3971-192">Estos puntos representan las coordenadas de latitud y longitud de la tierra en la que se dibujan las instancias de `geography`.</span><span class="sxs-lookup"><span data-stu-id="c3971-192">These points represent the latitude and longitude coordinates of the earth on which the `geography` instances are drawn.</span></span> <span data-ttu-id="c3971-193">El tipo de datos `geography` proporciona numerosos métodos integrados para consultar los puntos de una instancia.</span><span class="sxs-lookup"><span data-stu-id="c3971-193">The data type `geography` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="c3971-194">**Devolver el número de puntos que comprende una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-194">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="c3971-195">STNumPoints &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-195">STNumPoints &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumpoints-geography-data-type)  
  
 <span data-ttu-id="c3971-196">**Devolver un punto concreto en una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-196">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="c3971-197">STPointN &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-197">STPointN &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="c3971-198">**Devolver el punto inicial de una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-198">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="c3971-199">STStartPoint &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-199">STStartPoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ststartpoint-geography-data-type)  
  
 <span data-ttu-id="c3971-200">**Devolver el punto final de una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-200">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="c3971-201">STEndpoint &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-201">STEndpoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stendpoint-geography-data-type)  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="c3971-202">Dimensión</span><span class="sxs-lookup"><span data-stu-id="c3971-202">Dimension</span></span>  
 <span data-ttu-id="c3971-203">Una instancia de `geography` no vacía puede ser no dimensional, unidimensional o bidimensional.</span><span class="sxs-lookup"><span data-stu-id="c3971-203">A nonempty `geography` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="c3971-204">`geography`Las instancias de no dimensionales, como `Point` y `MultiPoint` , no tienen ninguna longitud ni área.</span><span class="sxs-lookup"><span data-stu-id="c3971-204">Zero-dimensional `geography` instances, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="c3971-205">Los objetos unidimensionales, como `LineString, CircularString`, `CompoundCurve` y `MultiLineString`, tienen longitud.</span><span class="sxs-lookup"><span data-stu-id="c3971-205">One-dimensional objects, such as `LineString, CircularString`, `CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="c3971-206">Las instancias bidimensionales, como `Polygon, CurvePolygon` y `MultiPolygon`, tienen área y longitud.</span><span class="sxs-lookup"><span data-stu-id="c3971-206">Two-dimensional instances, such as `Polygon, CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="c3971-207">Las instancias vacías informan de una dimensión de -1 y `GeometryCollection` informa de la dimensión máxima de su contenido.</span><span class="sxs-lookup"><span data-stu-id="c3971-207">Empty instances report a dimension of -1, and a `GeometryCollection` reports the maximum dimension of its contents.</span></span>  
  
 <span data-ttu-id="c3971-208">**Devolver la dimensión de una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-208">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="c3971-209">STDimension &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-209">STDimension &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdimension-geography-data-type)  
  
 <span data-ttu-id="c3971-210">**Devolver la longitud de una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-210">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="c3971-211">STLength &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-211">STLength &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlength-geography-data-type)  
  
 <span data-ttu-id="c3971-212">**Devolver el área de una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-212">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="c3971-213">STArea &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-213">STArea &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/starea-geography-data-type)  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="c3971-214">Vacía</span><span class="sxs-lookup"><span data-stu-id="c3971-214">Empty</span></span>  
 <span data-ttu-id="c3971-215">Una instancia *vacía* no `geography` tiene ningún punto.</span><span class="sxs-lookup"><span data-stu-id="c3971-215">An *empty*`geography` instance does not have any points.</span></span> <span data-ttu-id="c3971-216">La longitud de las instancias de `LineString, CircularString`, `CompoundCurve` y `MultiLineString` vacías es 0.</span><span class="sxs-lookup"><span data-stu-id="c3971-216">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is 0.</span></span> <span data-ttu-id="c3971-217">El área de las instancias de `Polygon, CurvePolygon` y `MultiPolygon` vacías es 0.</span><span class="sxs-lookup"><span data-stu-id="c3971-217">The area of empty `Polygon, CurvePolygon` and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="c3971-218">**Para determinar si una instancia está vacía**</span><span class="sxs-lookup"><span data-stu-id="c3971-218">**To determine if an instance is empty**</span></span>  
 [<span data-ttu-id="c3971-219">STIsEmpty &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-219">STIsEmpty &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisempty-geography-data-type)  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="c3971-220">Clausura</span><span class="sxs-lookup"><span data-stu-id="c3971-220">Closure</span></span>  
 <span data-ttu-id="c3971-221">Una instancia *cerrada* `geography` es una figura cuyos puntos de inicio y de finalización son los mismos.</span><span class="sxs-lookup"><span data-stu-id="c3971-221">A *closed*`geography` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="c3971-222">Las instancias `Polygon` se consideran cerradas.</span><span class="sxs-lookup"><span data-stu-id="c3971-222">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="c3971-223">Las instancias `Point` no son cerradas.</span><span class="sxs-lookup"><span data-stu-id="c3971-223">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="c3971-224">Un anillo es una instancia de `LineString` simple y cerrada.</span><span class="sxs-lookup"><span data-stu-id="c3971-224">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="c3971-225">**Para determinar si una instancia está cerrada**</span><span class="sxs-lookup"><span data-stu-id="c3971-225">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="c3971-226">STIsClosed &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-226">STIsClosed &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisclosed-geography-data-type)  
  
 <span data-ttu-id="c3971-227">**Para devolver el número de anillos en una instancia de Polygon**</span><span class="sxs-lookup"><span data-stu-id="c3971-227">**To return the number of rings in a Polygon instance**</span></span>  
 [<span data-ttu-id="c3971-228">NumRings &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-228">NumRings &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/numrings-geography-data-type)  
  
 <span data-ttu-id="c3971-229">**Para devolver un anillo especificado de una instancia de Geography**</span><span class="sxs-lookup"><span data-stu-id="c3971-229">**To return a specified ring of a geography instance**</span></span>  
 [<span data-ttu-id="c3971-230">RingN &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-230">RingN &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ringn-geography-data-type)  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="c3971-231">Identificador de referencia espacial (SRID)</span><span class="sxs-lookup"><span data-stu-id="c3971-231">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="c3971-232">El identificador de referencia espacial (SRID) es un identificador que especifica en qué sistema de coordenadas elíptico está representada la instancia `geography`.</span><span class="sxs-lookup"><span data-stu-id="c3971-232">The spatial reference ID (SRID) is an identifier specifying which ellipsoidal coordinate system the `geography` instance is represented in.</span></span> <span data-ttu-id="c3971-233">No se pueden comparar dos instancias `geography` con SRID diferentes.</span><span class="sxs-lookup"><span data-stu-id="c3971-233">Two `geography` instances with different SRIDs cannot be compared.</span></span>  
  
 <span data-ttu-id="c3971-234">**Para establecer o devolver el SRID de una instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-234">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="c3971-235">STSrid &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-235">STSrid &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsrid-geography-data-type)  
  
 <span data-ttu-id="c3971-236">Esta propiedad se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="c3971-236">This property can be modified.</span></span>  
  
##  <a name="determining-relationships-between-geography-instances"></a><a name="rel"></a> <span data-ttu-id="c3971-237">Determinar las relaciones entre instancias de geography</span><span class="sxs-lookup"><span data-stu-id="c3971-237">Determining Relationships between geography Instances</span></span>  
 <span data-ttu-id="c3971-238">El tipo de datos `geography` proporciona muchos métodos integrados que puede usar para determinar las relaciones entre dos instancias de `geography`.</span><span class="sxs-lookup"><span data-stu-id="c3971-238">The `geography` data type provides many built-in methods you can use to determine relationships between two `geography` instances.</span></span>  
  
 <span data-ttu-id="c3971-239">**Para determinar si dos instancias comprenden el mismo conjunto de puntos**</span><span class="sxs-lookup"><span data-stu-id="c3971-239">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="c3971-240">STEquals &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-240">STEquals &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="c3971-241">**Para determinar si dos instancias no son contiguas**</span><span class="sxs-lookup"><span data-stu-id="c3971-241">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="c3971-242">STDisjoint &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-242">STDisjoint &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="c3971-243">**Para determinar si dos instancias contienen puntos que forman una intersección**</span><span class="sxs-lookup"><span data-stu-id="c3971-243">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="c3971-244">STIntersects &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-244">STIntersects &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="c3971-245">**Determinar los puntos en los que dos instancias tienen la intersección**</span><span class="sxs-lookup"><span data-stu-id="c3971-245">**To determine the point or points where two instances intersect**</span></span>  
 [<span data-ttu-id="c3971-246">STIntersection &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-246">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="c3971-247">**Determinar la distancia más corta entre los puntos de dos instancias geográficas**</span><span class="sxs-lookup"><span data-stu-id="c3971-247">**To determine the shortest distance between points in two geography instances**</span></span>  
 [<span data-ttu-id="c3971-248">STDistance &#40;tipo de datos geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-248">STDistance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
 <span data-ttu-id="c3971-249">**Determinar la diferencia en puntos entre dos instancias geográficas**</span><span class="sxs-lookup"><span data-stu-id="c3971-249">**To determine the difference in points between two geography instances**</span></span>  
 [<span data-ttu-id="c3971-250">STDifference &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-250">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
 <span data-ttu-id="c3971-251">**Para obtener la diferencia simétrica, o puntos únicos, de una instancia de geography comparada con otra instancia**</span><span class="sxs-lookup"><span data-stu-id="c3971-251">**To derive the symmetric difference, or unique points, of one geography instance compared with another instance**</span></span>  
 [<span data-ttu-id="c3971-252">STSymDifference &#40;tipo de datos geography&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-252">STSymDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsymdifference-geography-data-type)  
  
##  <a name="geography-instances-must-use-supported-srid"></a><a name="supportedsrid"></a> <span data-ttu-id="c3971-253">Las instancias de geography deben usar SRID compatibles</span><span class="sxs-lookup"><span data-stu-id="c3971-253">geography Instances Must Use Supported SRID</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3971-254">admite SRID basados en las normas de EPSG.</span><span class="sxs-lookup"><span data-stu-id="c3971-254">supports SRIDs based on the EPSG standards.</span></span> <span data-ttu-id="c3971-255">Se debe usar un SID compatible con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para instancias de `geography` cuando se realicen cálculos o se usen los métodos con datos espaciales de geografía.</span><span class="sxs-lookup"><span data-stu-id="c3971-255">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-supported SRID for `geography` instances must be used when performing calculations or using methods with geography spatial data.</span></span> <span data-ttu-id="c3971-256">El SRID debe coincidir con uno de los SRID mostrados en la vista de catálogo **sys.spatial_reference_systems** .</span><span class="sxs-lookup"><span data-stu-id="c3971-256">The SRID must match one of the SRIDs displayed in the **sys.spatial_reference_systems** catalog view.</span></span> <span data-ttu-id="c3971-257">Como se mencionó anteriormente, al realizar cálculos en sus datos espaciales usando el tipo de datos `geography`, sus resultados dependerán de qué elipsoide se usó en la creación de sus datos, ya que cada elipsoide está asignado a un identificador de referencia espacial concreto (SRID).</span><span class="sxs-lookup"><span data-stu-id="c3971-257">As mentioned previously, when you perform calculations on your spatial data using the `geography` data type, your results will depend on which ellipsoid was used in the creation of your data, as each ellipsoid is assigned a specific spatial reference identifier (SRID).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3971-258">usa el SRID predeterminado de 4326, que se asigna al sistema de referencia espacial WGS 84, al usar métodos en instancias de `geography`.</span><span class="sxs-lookup"><span data-stu-id="c3971-258">uses the default SRID of 4326, which maps to the WGS 84 spatial reference system, when using methods on `geography` instances.</span></span> <span data-ttu-id="c3971-259">Si usa datos de un sistema de referencia espacial distinto de WGS 84 (o SRID 4326), tendrá que determinar el SRID concreto para sus datos espaciales de geography.</span><span class="sxs-lookup"><span data-stu-id="c3971-259">If you use data from a spatial reference system other than WGS 84 (or SRID 4326), you will need to determine the specific SRID for your geography spatial data.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="c3971-260">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c3971-260">Examples</span></span>  
 <span data-ttu-id="c3971-261">En los ejemplos siguientes se muestra cómo agregar y consultar datos geography.</span><span class="sxs-lookup"><span data-stu-id="c3971-261">The following examples show how to add and query geography data.</span></span>  
  
-   <span data-ttu-id="c3971-262">En el primer ejemplo se crea una tabla con una columna de identidad y una columna de tipo `geography` , `GeogCol1`.</span><span class="sxs-lookup"><span data-stu-id="c3971-262">The first example creates a table with an identity column and a `geography` column `GeogCol1`.</span></span> <span data-ttu-id="c3971-263">Una tercera columna representa la columna de tipo `geography` en su representación Well-Known Text (WKT) de Open Geospatial Consortium (OGC) y utiliza el método `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="c3971-263">A third column renders the `geography` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="c3971-264">A continuación se insertan dos filas: una que contiene una instancia de `LineString` de `geography`y otra que contiene una instancia de `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="c3971-264">Two rows are then inserted: one row contains a `LineString` instance of `geography`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeogCol1 geography,   
        GeogCol2 AS GeogCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326));  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326));  
    GO  
    ```  
  
-   <span data-ttu-id="c3971-265">En el segundo ejemplo se usa el método `STIntersection()` para devolver los puntos de intersección de las dos instancias de `geography` insertadas previamente.</span><span class="sxs-lookup"><span data-stu-id="c3971-265">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geography` instances intersect.</span></span>  
  
    ```  
    DECLARE @geog1 geography;  
    DECLARE @geog2 geography;  
    DECLARE @result geography;  
  
    SELECT @geog1 = GeogCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geog2 = GeogCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geog1.STIntersection(@geog2);  
    SELECT @result.STAsText();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c3971-266">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3971-266">See Also</span></span>  
 [<span data-ttu-id="c3971-267">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3971-267">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
