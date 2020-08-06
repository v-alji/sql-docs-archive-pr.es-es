---
title: Incluir o excluir filas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- included rows
- search conditions [SQL Server], HAVING clause
- search criteria [SQL Server], including rows
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- search conditions [SQL Server], WHERE clause
- row included in search [SQL Server]
- excluding rows
ms.assetid: ba4e1202-31a2-444d-8365-c68a530ef223
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7b2d31c51296fa73a503e59a14adb60d79a61178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673960"
---
# <a name="include-or-exclude-rows-visual-database-tools"></a><span data-ttu-id="9699b-102">Incluir o excluir filas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9699b-102">Include or Exclude Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="9699b-103">Para restringir el número de filas que debe devolver una consulta SELECT, puede crear condiciones de búsqueda o criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="9699b-103">To restrict the number of rows a SELECT query should return, you create search conditions or filter criteria.</span></span> <span data-ttu-id="9699b-104">En SQL, las condiciones de búsqueda aparecen en la cláusula WHERE de la instrucción o, si está creando una consulta de funciones agregadas, en la cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="9699b-104">In SQL, search conditions appear in the WHERE clause of the statement, or if you are creating an aggregate query, in the HAVING clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9699b-105">También puede utilizar condiciones de búsqueda para indicar qué filas están afectadas por una consulta Update, Insert Results, Insert Values, Delete o Make Table.</span><span class="sxs-lookup"><span data-stu-id="9699b-105">You can also use search conditions to indicate which rows are affected by an Update, Insert Results, Insert Values, Delete, or Make Table query.</span></span>  
  
 <span data-ttu-id="9699b-106">Cuando se ejecuta la consulta, [!INCLUDE[ssDE](../../includes/ssde-md.md)] examina y aplica la condición de búsqueda a cada fila de las tablas en las que el usuario está buscando.</span><span class="sxs-lookup"><span data-stu-id="9699b-106">When the query runs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] examines and applies the search condition to each row in the tables you are searching.</span></span> <span data-ttu-id="9699b-107">Si la fila cumple la condición, se incluye en la consulta.</span><span class="sxs-lookup"><span data-stu-id="9699b-107">If the row meets the condition, it is included in the query.</span></span> <span data-ttu-id="9699b-108">Por ejemplo, una condición de búsqueda que encuentre todos los empleados de una región determinada podría ser:</span><span class="sxs-lookup"><span data-stu-id="9699b-108">For example, a search condition that would find all the employees in a particular region might be:</span></span>  
  
```  
region = 'UK'  
```  
  
 <span data-ttu-id="9699b-109">Para establecer los criterios para incluir una fila en un resultado, puede utilizar varias condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9699b-109">To establish the criteria for including a row in a result, you can use multiple search conditions.</span></span> <span data-ttu-id="9699b-110">Por ejemplo, el siguiente criterio de búsqueda consta de dos condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9699b-110">For example, the following search criterion consists of two search conditions.</span></span> <span data-ttu-id="9699b-111">La consulta incluye una fila en el conjunto de resultados solo si dicha fila satisface ambas condiciones.</span><span class="sxs-lookup"><span data-stu-id="9699b-111">The query includes a row in the result set only if that row satisfies both of the conditions.</span></span>  
  
```  
region = 'UK' AND product_line = 'Housewares'  
```  
  
 <span data-ttu-id="9699b-112">Puede combinar estas condiciones con AND u OR.</span><span class="sxs-lookup"><span data-stu-id="9699b-112">You can combine these conditions with AND or OR.</span></span> <span data-ttu-id="9699b-113">El ejemplo anterior utiliza AND.</span><span class="sxs-lookup"><span data-stu-id="9699b-113">The previous example uses AND.</span></span> <span data-ttu-id="9699b-114">En contraposición, el criterio siguiente utiliza OR.</span><span class="sxs-lookup"><span data-stu-id="9699b-114">In contrast, the following criterion uses OR.</span></span> <span data-ttu-id="9699b-115">El conjunto de resultados incluirá cualquier fila que satisfaga una de las condiciones de búsqueda o ambas:</span><span class="sxs-lookup"><span data-stu-id="9699b-115">The result set will include any row that satisfies either or both of the search conditions:</span></span>  
  
```  
region = 'UK' OR product_line = 'Housewares'  
```  
  
 <span data-ttu-id="9699b-116">Puede incluso combinar condiciones de búsqueda en una sola columna.</span><span class="sxs-lookup"><span data-stu-id="9699b-116">You can even combine search conditions on a single column.</span></span> <span data-ttu-id="9699b-117">Por ejemplo, el siguiente criterio combina dos condiciones en la columna región:</span><span class="sxs-lookup"><span data-stu-id="9699b-117">For example, the following criterion combines two conditions on the region column:</span></span>  
  
```  
region = 'UK' OR region = 'US'  
```  
  
 <span data-ttu-id="9699b-118">Para obtener más detalles sobre cómo combinar condiciones de búsqueda, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9699b-118">For details about combining search conditions, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9699b-119">Convenciones para combinar condiciones de búsqueda en el panel Criterios &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9699b-119">Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;</span></span>](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
  
-   [<span data-ttu-id="9699b-120">Especificar varias condiciones de búsqueda para una columna &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9699b-120">Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
-   [<span data-ttu-id="9699b-121">Especificar varias condiciones de búsqueda para varias columnas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9699b-121">Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md)  
  
-   [<span data-ttu-id="9699b-122">Combinar condiciones cuando AND tiene prioridad &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9699b-122">Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
  
-   [<span data-ttu-id="9699b-123">Combinar condiciones cuando OR tiene prioridad &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9699b-123">Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
  
## <a name="examples"></a><span data-ttu-id="9699b-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9699b-124">Examples</span></span>  
 <span data-ttu-id="9699b-125">A continuación se muestran algunos ejemplos de consultas que utilizan varios operadores y criterios de fila:</span><span class="sxs-lookup"><span data-stu-id="9699b-125">Here are some examples of queries using various operators and row criteria:</span></span>  
  
-   <span data-ttu-id="9699b-126">**Literal** Valor único de texto, numérico, de fecha o lógico.</span><span class="sxs-lookup"><span data-stu-id="9699b-126">**Literal** A single text, numeric, date, or logical value.</span></span> <span data-ttu-id="9699b-127">El ejemplo siguiente utiliza un literal para buscar todas las filas de empleados del Reino Unido:</span><span class="sxs-lookup"><span data-stu-id="9699b-127">The following example uses a literal to find all rows for employees in the United Kingdom:</span></span>  
  
    ```  
    WHERE region = 'UK'  
    ```  
  
-   <span data-ttu-id="9699b-128">**Referencia de columna** Compara los valores de una columna con los valores de la otra.</span><span class="sxs-lookup"><span data-stu-id="9699b-128">**Column reference** Compares the values in one column with the values in another.</span></span> <span data-ttu-id="9699b-129">El ejemplo siguiente busca en una tabla `products` todas las filas en las que el valor del costo de producción es inferior al costo de envío:</span><span class="sxs-lookup"><span data-stu-id="9699b-129">The following example searches a `products` table for all rows in which the value of the production cost is lower than the shipping cost:</span></span>  
  
    ```  
    WHERE prod_cost < ship_cost  
    ```  
  
-   <span data-ttu-id="9699b-130">**Función** Referencia a una función que el back-end de la base de datos puede resolver para calcular un valor de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9699b-130">**Function** A reference to a function that the database back-end can resolve to calculate a value for the search.</span></span> <span data-ttu-id="9699b-131">La función puede ser una función definida por el servidor de base de datos o una función definida por el usuario que devuelve un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="9699b-131">The function can be a function defined by the database server or a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="9699b-132">El siguiente ejemplo busca pedidos realizados hoy (la función GETDATE( ) devuelve la fecha actual):</span><span class="sxs-lookup"><span data-stu-id="9699b-132">The following example searches for orders placed today (the GETDATE( ) function returns the current date):</span></span>  
  
    ```  
    WHERE order_date = GETDATE()  
    ```  
  
-   <span data-ttu-id="9699b-133">**NULL** El siguiente ejemplo busca en una tabla `authors` todos los autores que tengan un nombre en el archivo:</span><span class="sxs-lookup"><span data-stu-id="9699b-133">**NULL** The following example searches an `authors` table for all authors who have a first name on file:</span></span>  
  
    ```  
    WHERE au_fname IS NOT NULL  
    ```  
  
-   <span data-ttu-id="9699b-134">**Cálculo** Resultado de un cálculo que puede incluir literales, referencias de columna u otras expresiones.</span><span class="sxs-lookup"><span data-stu-id="9699b-134">**Calculation** The result of a calculation that can involve literals, column references, or other expressions.</span></span> <span data-ttu-id="9699b-135">El siguiente ejemplo busca en una tabla `products` todas las filas en las que el precio de venta al público sea más del doble del costo de producción:</span><span class="sxs-lookup"><span data-stu-id="9699b-135">The following example searches a `products` table to find all rows in which the retail sales price is more than twice the production cost:</span></span>  
  
    ```  
    WHERE sales_price > (prod_cost * 2)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9699b-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9699b-136">See Also</span></span>  
 <span data-ttu-id="9699b-137">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9699b-137">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9699b-138">[Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9699b-138">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9699b-139">Realizar consultas con parámetros &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9699b-139">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
