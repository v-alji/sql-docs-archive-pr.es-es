---
title: Especificar varias condiciones de búsqueda para una columna (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 2c006e36-56b1-4992-89b4-c6c0b19808f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a07322120bd3b3f543e6f54fa50cdf75aa32be59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672348"
---
# <a name="specify-multiple-search-conditions-for-one-column-visual-database-tools"></a><span data-ttu-id="66b18-102">Especificar varias condiciones de búsqueda para una columna (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="66b18-102">Specify Multiple Search Conditions for One Column (Visual Database Tools)</span></span>
  <span data-ttu-id="66b18-103">En algunas ocasiones, es posible que desee aplicar una serie de condiciones de búsqueda a la misma columna de datos.</span><span class="sxs-lookup"><span data-stu-id="66b18-103">In some instances, you might want to apply a number of search conditions to the same data column.</span></span> <span data-ttu-id="66b18-104">Por ejemplo, podría:</span><span class="sxs-lookup"><span data-stu-id="66b18-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="66b18-105">Buscar varios nombres diferentes en una tabla `employee` o empleados que tengan distintos salarios.</span><span class="sxs-lookup"><span data-stu-id="66b18-105">Search for several different names in an `employee` table or for employees who are in different salary ranges.</span></span> <span data-ttu-id="66b18-106">Este tipo de búsqueda requiere una condición OR.</span><span class="sxs-lookup"><span data-stu-id="66b18-106">This type of search requires an OR condition.</span></span>  
  
-   <span data-ttu-id="66b18-107">Buscar un título de un libro que empiece con la palabra "La" y contenga la palabra "Cocina".</span><span class="sxs-lookup"><span data-stu-id="66b18-107">Search for a book title that both starts with the word "The" and contains the word "Cook."</span></span> <span data-ttu-id="66b18-108">Este tipo de búsqueda requiere una condición AND.</span><span class="sxs-lookup"><span data-stu-id="66b18-108">This type of search requires an AND condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66b18-109">La información de este tema se aplica a las condiciones de búsqueda en las cláusulas WHERE y HAVING de una consulta.</span><span class="sxs-lookup"><span data-stu-id="66b18-109">The information in this topic applies to search conditions in both the WHERE and HAVING clauses of a query.</span></span> <span data-ttu-id="66b18-110">Los ejemplos se centran en las cláusulas WHERE, pero los principios se aplican a ambos tipos de condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="66b18-110">The examples focus on creating WHERE clauses, but the principles apply to both types of search conditions.</span></span>  
  
 <span data-ttu-id="66b18-111">Para buscar valores alternativos en la misma columna de datos, debe especificar una condición OR.</span><span class="sxs-lookup"><span data-stu-id="66b18-111">To search for alternative values in the same data column, you specify an OR condition.</span></span> <span data-ttu-id="66b18-112">Para buscar valores que cumplan varias condiciones, debe especificar una condición AND.</span><span class="sxs-lookup"><span data-stu-id="66b18-112">To search for values that meet several conditions, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="66b18-113">Especificar una condición OR</span><span class="sxs-lookup"><span data-stu-id="66b18-113">Specifying an OR Condition</span></span>  
 <span data-ttu-id="66b18-114">La condición OR permite especificar la búsqueda de varios valores alternativos en una columna.</span><span class="sxs-lookup"><span data-stu-id="66b18-114">Using an OR condition enables you to specify several alternative values to search for in a column.</span></span> <span data-ttu-id="66b18-115">Esta opción expande el ámbito de la búsqueda y puede devolver más filas que cuando se busca un solo valor.</span><span class="sxs-lookup"><span data-stu-id="66b18-115">This option expands the scope of the search and can return more rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="66b18-116">Con frecuencia, se puede utilizar el operador IN en lugar de buscar varios valores en la misma columna de datos.</span><span class="sxs-lookup"><span data-stu-id="66b18-116">You can often use the IN operator instead to search for multiple values in the same data column.</span></span>  
  
#### <a name="to-specify-an-or-condition"></a><span data-ttu-id="66b18-117">Para especificar una condición OR</span><span class="sxs-lookup"><span data-stu-id="66b18-117">To specify an OR condition</span></span>  
  
1.  <span data-ttu-id="66b18-118">En el [panel Criterios](visual-database-tools.md), agregue la columna en la que desea realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="66b18-118">In the [Criteria Pane](visual-database-tools.md), add the column to search.</span></span>  
  
2.  <span data-ttu-id="66b18-119">En la columna **Filtro** de la columna de datos que acaba de agregar, especifique la primera condición.</span><span class="sxs-lookup"><span data-stu-id="66b18-119">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="66b18-120">En la columna **O...** de la misma columna de datos, especifique la segunda condición.</span><span class="sxs-lookup"><span data-stu-id="66b18-120">In the **Or...** column for the same data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="66b18-121">El Diseñador de consultas y vistas crea una cláusula WHERE que contiene una condición OR similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="66b18-121">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
```  
SELECT fname, lname  
FROM employees  
WHERE (salary < 30000) OR (salary > 100000)  
```  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="66b18-122">Especificar una condición AND</span><span class="sxs-lookup"><span data-stu-id="66b18-122">Specifying an AND Condition</span></span>  
 <span data-ttu-id="66b18-123">La condición AND permite especificar que los valores de una columna deben satisfacer dos o más condiciones para que la fila se incluya en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="66b18-123">Using an AND condition enables you to specify that values in a column must meet two (or more) conditions for the row to be included in the result set.</span></span> <span data-ttu-id="66b18-124">Esta opción limita el ámbito de la búsqueda y normalmente devuelve menos filas que cuando se busca un solo valor.</span><span class="sxs-lookup"><span data-stu-id="66b18-124">This option narrows the scope of the search and usually returns fewer rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="66b18-125">Si va a buscar un intervalo de valores, puede utilizar el operador BETWEEN en lugar de unir dos condiciones con AND.</span><span class="sxs-lookup"><span data-stu-id="66b18-125">If you are searching for a range of values, you can use the BETWEEN operator instead of linking two conditions with AND.</span></span>  
  
#### <a name="to-specify-an-and-condition"></a><span data-ttu-id="66b18-126">Para especificar una condición AND</span><span class="sxs-lookup"><span data-stu-id="66b18-126">To specify an AND condition</span></span>  
  
1.  <span data-ttu-id="66b18-127">En el panel Criterios, agregue la columna en la que desea realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="66b18-127">In the Criteria pane, add the column to search.</span></span>  
  
2.  <span data-ttu-id="66b18-128">En la columna **Filtro** de la columna de datos que acaba de agregar, especifique la primera condición.</span><span class="sxs-lookup"><span data-stu-id="66b18-128">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="66b18-129">Vuelva a agregar la misma columna de datos en el panel Criterios insertándola en una fila vacía de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="66b18-129">Add the same data column to the Criteria pane again, placing it in an empty row of the grid.</span></span>  
  
4.  <span data-ttu-id="66b18-130">En la columna **Filtro** de la segunda instancia de la columna de datos, especifique la segunda condición.</span><span class="sxs-lookup"><span data-stu-id="66b18-130">In the **Filter** column for the second instance of the data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="66b18-131">El Diseñador de consultas crea una cláusula WHERE que contiene una condición AND similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="66b18-131">The Query Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
```  
SELECT title_id, title  
FROM titles  
WHERE (title LIKE '%Cook%') AND   
  (title LIKE '%Recipe%')  
```  
  
## <a name="see-also"></a><span data-ttu-id="66b18-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66b18-132">See Also</span></span>  
 <span data-ttu-id="66b18-133">[Convenciones para combinar condiciones de búsqueda en el panel criterios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="66b18-133">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="66b18-134">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="66b18-134">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
