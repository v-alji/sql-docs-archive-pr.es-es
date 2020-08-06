---
title: Datos espaciales (SQL Server) | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server], spatial storage design
- planar spatial data [SQL Server], designing
- spatial data types [SQL Server]
- geodetic spatial data [SQL Server]
- geometry data type [SQL Server], spatial storage design
- spatial storage [SQL Server]
- geodetic spatial data [SQL Server], designing
ms.assetid: 41a132a1-09e2-4426-b9df-225270cb8e15
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4d491420a9eca7c35b89b254a03381c6467c834c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676948"
---
# <a name="spatial-data-sql-server"></a><span data-ttu-id="68d69-102">Datos espaciales (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="68d69-102">Spatial Data (SQL Server)</span></span>
  <span data-ttu-id="68d69-103">Los datos espaciales representan información sobre la ubicación física y la forma de objetos geométricos.</span><span class="sxs-lookup"><span data-stu-id="68d69-103">Spatial data represents information about the physical location and shape of geometric objects.</span></span> <span data-ttu-id="68d69-104">Estos objetos pueden ser ubicaciones de punto u objetos más complejos como países, carreteras o lagos.</span><span class="sxs-lookup"><span data-stu-id="68d69-104">These objects can be point locations or more complex objects such as countries, roads, or lakes.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="68d69-105">admite dos tipos de datos espaciales: el tipo de datos `geometry` y el tipo de datos `geography`.</span><span class="sxs-lookup"><span data-stu-id="68d69-105">supports two spatial data types: the `geometry` data type and the `geography` data type.</span></span>  
  
-   <span data-ttu-id="68d69-106">El tipo `geometry` representa los datos en un sistema de coordenadas euclidiano (plano).</span><span class="sxs-lookup"><span data-stu-id="68d69-106">The `geometry` type represents data in a Euclidean (flat) coordinate system.</span></span>  
  
-   <span data-ttu-id="68d69-107">El tipo `geography` representa los datos en un sistema de coordenadas de tierra redonda.</span><span class="sxs-lookup"><span data-stu-id="68d69-107">The `geography` type represents data in a round-earth coordinate system.</span></span>  
  
 <span data-ttu-id="68d69-108">Ambos tipos de datos se implementan como tipos de datos .NET Common Language Runtime (CLR) en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68d69-108">Both data types are implemented as .NET common language runtime (CLR) data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="68d69-109">Para obtener una descripción detallada y ejemplos de las características espaciales introducidas en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], descargue las notas del producto [New Spatial Features in SQL Server 2012 (Nuevas características espaciales de SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="68d69-109">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="68d69-110">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="68d69-110">Related Tasks</span></span>  
 [<span data-ttu-id="68d69-111">Crear, construir y consultar instancias de Geometry</span><span class="sxs-lookup"><span data-stu-id="68d69-111">Create, Construct, and Query geometry Instances</span></span>](create-construct-and-query-geometry-instances.md)  
 <span data-ttu-id="68d69-112">Describe métodos que puede usar con instancias del tipo de datos geometry.</span><span class="sxs-lookup"><span data-stu-id="68d69-112">Describes the methods that you can use with instances of the geometry data type.</span></span>  
  
 [<span data-ttu-id="68d69-113">Creación, construcción y consulta de instancias de Geography</span><span class="sxs-lookup"><span data-stu-id="68d69-113">Create, Construct, and Query geography Instances</span></span>](create-construct-and-query-geography-instances.md)  
 <span data-ttu-id="68d69-114">Describe métodos que puede usar con instancias del tipo de datos geography.</span><span class="sxs-lookup"><span data-stu-id="68d69-114">Describes the methods that you can use with instances of the geography data type.</span></span>  
  
 [<span data-ttu-id="68d69-115">Consultar datos espaciales para el vecino más próximo</span><span class="sxs-lookup"><span data-stu-id="68d69-115">Query Spatial Data for Nearest Neighbor</span></span>](query-spatial-data-for-nearest-neighbor.md)  
 <span data-ttu-id="68d69-116">Describe el modelo de consulta común que se usa para buscar los objetos espaciales más cercanos a un objeto espacial concreto.</span><span class="sxs-lookup"><span data-stu-id="68d69-116">Describes the common query pattern that is used to find the closest spatial objects to a specific spatial object.</span></span>  
  
 [<span data-ttu-id="68d69-117">Crear, modificar y quitar índices espaciales</span><span class="sxs-lookup"><span data-stu-id="68d69-117">Create, Modify, and Drop Spatial Indexes</span></span>](create-modify-and-drop-spatial-indexes.md)  
 <span data-ttu-id="68d69-118">Proporciona información acerca de cómo crear, modificar y quitar un índice espacial.</span><span class="sxs-lookup"><span data-stu-id="68d69-118">Provides information about creating, altering, and dropping a spatial index.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="68d69-119">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="68d69-119">Related Content</span></span>  
 [<span data-ttu-id="68d69-120">Información general de los tipos de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="68d69-120">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
 <span data-ttu-id="68d69-121">Presenta los tipos de datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="68d69-121">Introduces the spatial data types.</span></span>  
  
-   [<span data-ttu-id="68d69-122">Point</span><span class="sxs-lookup"><span data-stu-id="68d69-122">Point</span></span>](point.md)  
  
-   [<span data-ttu-id="68d69-123">LineString</span><span class="sxs-lookup"><span data-stu-id="68d69-123">LineString</span></span>](linestring.md)  
  
-   [<span data-ttu-id="68d69-124">CircularString</span><span class="sxs-lookup"><span data-stu-id="68d69-124">CircularString</span></span>](circularstring.md)  
  
-   [<span data-ttu-id="68d69-125">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="68d69-125">CompoundCurve</span></span>](compoundcurve.md)  
  
-   [<span data-ttu-id="68d69-126">Polygon</span><span class="sxs-lookup"><span data-stu-id="68d69-126">Polygon</span></span>](polygon.md)  
  
-   [<span data-ttu-id="68d69-127">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="68d69-127">CurvePolygon</span></span>](curvepolygon.md)  
  
-   [<span data-ttu-id="68d69-128">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="68d69-128">MultiPoint</span></span>](multipoint.md)  
  
-   [<span data-ttu-id="68d69-129">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="68d69-129">MultiLineString</span></span>](multilinestring.md)  
  
-   [<span data-ttu-id="68d69-130">MultiPolígono</span><span class="sxs-lookup"><span data-stu-id="68d69-130">MultiPolygon</span></span>](multipolygon.md)  
  
-   [<span data-ttu-id="68d69-131">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="68d69-131">GeometryCollection</span></span>](geometrycollection.md)  
  
 [<span data-ttu-id="68d69-132">Información general sobre los índices espaciales</span><span class="sxs-lookup"><span data-stu-id="68d69-132">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
 <span data-ttu-id="68d69-133">Presenta los índices espaciales, y describe la teselación y los esquemas de teselación.</span><span class="sxs-lookup"><span data-stu-id="68d69-133">Introduces spatial indexes and describes tessellation and tessellation schemes.</span></span>  
  
  
