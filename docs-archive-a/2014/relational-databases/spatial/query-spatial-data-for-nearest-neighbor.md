---
title: Consulta de datos espaciales para el vecino más próximo | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 7af4ad5d-484e-45b4-aa16-83c33b358bb6
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 644b3e5cfdaeff7457639bc2da77260b64011735
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676950"
---
# <a name="query-spatial-data-for-nearest-neighbor"></a><span data-ttu-id="3f3c8-102">Consultar datos espaciales para el vecino más próximo</span><span class="sxs-lookup"><span data-stu-id="3f3c8-102">Query Spatial Data for Nearest Neighbor</span></span>
  <span data-ttu-id="3f3c8-103">Una consulta frecuente utilizada con datos espaciales es la de vecino más cercano.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-103">A common query used with spatial data is the Nearest Neighbor query.</span></span> <span data-ttu-id="3f3c8-104">Las consultas de vecino más cercano se emplean para encontrar los objetos espaciales más cercanos a un objeto espacial concreto.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-104">Nearest Neighbor queries are used to find the closest spatial objects to a specific spatial object.</span></span> <span data-ttu-id="3f3c8-105">Por ejemplo, un buscador de tiendas de un sitio web debe encontrar a menudo las ubicaciones de las tiendas más cercanas a la ubicación de un cliente.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-105">For example a store locater for a Web site often must find the closest store locations to a customer location.</span></span>  
  
 <span data-ttu-id="3f3c8-106">Se puede escribir una consulta de vecino más cercano en distintos formatos de consulta válidos, pero para que dicha consulta use un índice espacial se debe emplear la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-106">A Nearest Neighbor query can be written in a variety of valid query formats, but for the Nearest Neighbor query to use a spatial index the following syntax must be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f3c8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f3c8-107">Syntax</span></span>  
  
```vb  
SELECT TOP ( number )  
        [ WITH TIES ]  
        [ * | expression ]   
        [, ...]  
    FROM spatial_table_reference, ...   
        [ WITH   
            (   
                [ INDEX ( index_ref ) ]   
                [ , SPATIAL_WINDOW_MAX_CELLS = <value>]   
                [ ,... ]   
            )   
        ]  
    WHERE   
        column_ref.STDistance ( @spatial_ object )   
            {   
                [ IS NOT NULL ] | [ < const ] | [ > const ]   
                | [ <= const ] | [ >= const ] | [ <> const ] ]   
            }  
            [ AND { other_predicate } ]   
    }  
    ORDER BY column_ref.STDistance ( @spatial_ object ) [ ,...n ]  
[ ; ]  
  
```  
  
## <a name="nearest-neighbor-query-and-spatial-indexes"></a><span data-ttu-id="3f3c8-108">Consulta de vecino más cercano e índices espaciales</span><span class="sxs-lookup"><span data-stu-id="3f3c8-108">Nearest Neighbor Query and Spatial Indexes</span></span>  
 <span data-ttu-id="3f3c8-109">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], las cláusulas `TOP` y `ORDER BY` se usan para realizar una consulta de vecino más cercano en columnas de datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `TOP` and `ORDER BY` clauses are used to perform a Nearest Neighbor query on spatial data columns.</span></span> <span data-ttu-id="3f3c8-110">La cláusula `ORDER BY` contiene una llamada al método `STDistance()` para el tipo de datos de columna espacial.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-110">The `ORDER BY` clause contains a call to the `STDistance()` method for the spatial column data type.</span></span> <span data-ttu-id="3f3c8-111">La cláusula `TOP` indica el número de objetos que se va a devolver para la consulta.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-111">The `TOP` clause indicates the number of objects to return for the query.</span></span>  
  
 <span data-ttu-id="3f3c8-112">Se deben cumplir los siguientes requisitos para que una consulta de vecino más cercano utilice un índice espacial:</span><span class="sxs-lookup"><span data-stu-id="3f3c8-112">The following requirements must be met for a Nearest Neighbor query to use a spatial index:</span></span>  
  
1.  <span data-ttu-id="3f3c8-113">Debe haber un índice espacial en una de las columnas espaciales y el método `STDistance()` debe utilizar esa columna en las cláusulas `WHERE` y `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-113">A spatial index must be present on one of the spatial columns and the `STDistance()` method must use that column in the `WHERE` and `ORDER BY` clauses.</span></span>  
  
2.  <span data-ttu-id="3f3c8-114">La cláusula `TOP` no puede contener una instrucción `PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-114">The `TOP` clause cannot contain a `PERCENT` statement.</span></span>  
  
3.  <span data-ttu-id="3f3c8-115">La cláusula `WHERE` debe contener un método `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-115">The `WHERE` clause must contain a `STDistance()` method.</span></span>  
  
4.  <span data-ttu-id="3f3c8-116">Si hay varios predicados en la cláusula `WHERE`, el predicado que contiene el método `STDistance()` debe estar conectado por una conjunción `AND` a los demás predicados.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-116">If there are multiple predicates in the `WHERE` clause then the predicate containing `STDistance()` method must be connected by an `AND` conjunction to the other predicates.</span></span> <span data-ttu-id="3f3c8-117">El método `STDistance()` no puede estar en una parte opcional de la cláusula `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-117">The `STDistance()` method cannot be in an optional part of the `WHERE` clause.</span></span>  
  
5.  <span data-ttu-id="3f3c8-118">La primera expresión de la cláusula `ORDER BY` debe utilizar el método `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-118">The first expression in the `ORDER BY` clause must use the `STDistance()` method.</span></span>  
  
6.  <span data-ttu-id="3f3c8-119">El criterio de ordenación para la primera expresión `STDistance()` de la cláusula `ORDER BY` debe ser `ASC`.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-119">Sort order for the first `STDistance()` expression in the `ORDER BY` clause must be `ASC`.</span></span>  
  
7.  <span data-ttu-id="3f3c8-120">Todas las filas para las que `STDistance` devuelve `NULL` se deben filtrar.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-120">All the rows for which `STDistance` returns `NULL` must be filtered out.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3f3c8-121">Los métodos que toman los tipos de datos `geography` o `geometry` como argumentos devolverán `NULL` si los SRID no son los mismos para los tipos.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-121">Methods that take `geography` or `geometry` data types as arguments will return `NULL` if the SRIDs are not the same for the types.</span></span>  
  
 <span data-ttu-id="3f3c8-122">Se recomienda utilizar las nuevas teselaciones de índice espacial para los índices empleados en las consultas de vecino más cercano.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-122">It is recommended that the new spatial index tessellations be used for indexes used in Nearest Neighbor queries.</span></span> <span data-ttu-id="3f3c8-123">Para obtener más información sobre las teselaciones de índice espacial, vea [Datos espaciales &#40;SQL Server&#41;](spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3f3c8-123">For more information on spatial index tessellations, see [Spatial Data &#40;SQL Server&#41;](spatial-data-sql-server.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f3c8-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f3c8-124">Example</span></span>  
 <span data-ttu-id="3f3c8-125">En el ejemplo de código siguiente se muestra una consulta de vecino más cercano que puede utilizar un índice espacial.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-125">The following code example shows a Nearest Neighbor query that can use a spatial index.</span></span> <span data-ttu-id="3f3c8-126">En el ejemplo se utiliza la tabla `Person.Address` de la base de datos `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="3f3c8-126">The example uses the `Person.Address` table in `AdventureWorks2012` database.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
WHERE SpatialLocation.STDistance(@g) IS NOT NULL  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="3f3c8-127">Cree un índice espacial en la columna SpatialLocation para ver cómo una consulta de vecino más cercano utiliza un índice espacial.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-127">Create a spatial index on the column SpatialLocation to see how a Nearest Neighbor query uses a spatial index.</span></span> <span data-ttu-id="3f3c8-128">Para obtener más información sobre cómo crear índices espaciales, vea [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="3f3c8-128">For more information on creating spatial indexes, see [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f3c8-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f3c8-129">Example</span></span>  
 <span data-ttu-id="3f3c8-130">En el ejemplo de código siguiente se muestra una consulta de vecino más cercano que no puede utilizar un índice espacial.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-130">The following code example shows a Nearest Neighbor query that cannot use a spatial index.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="3f3c8-131">A la consulta le falta una cláusula `WHERE` que utilice `STDistance()` en un formato especificado en la sección de sintaxis, por lo que la consulta no puede utilizar un índice espacial.</span><span class="sxs-lookup"><span data-stu-id="3f3c8-131">The query lacks a `WHERE` clause that uses `STDistance()` in a form specified in the syntax section so the query cannot use a spatial index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3c8-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f3c8-132">See Also</span></span>  
 [<span data-ttu-id="3f3c8-133">Datos espaciales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3f3c8-133">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
