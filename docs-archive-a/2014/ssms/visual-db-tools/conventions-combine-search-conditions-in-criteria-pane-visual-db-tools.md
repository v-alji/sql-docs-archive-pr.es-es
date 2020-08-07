---
title: Convenciones para combinar condiciones de búsqueda en el panel criterios (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- multiple OR clauses
- combining search conditions
- OR operator
- AND, Criteria pane
- multiple AND clauses
ms.assetid: d4859be5-ff5b-48b2-a101-ad40c6dbcc68
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684521baa87d5325366a0e18296cd35342a0e947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743861"
---
# <a name="conventions-for-combining-search-conditions-in-the-criteria-pane-visual-database-tools"></a><span data-ttu-id="3a833-102">Convenciones para combinar condiciones de búsqueda en el panel Criterios (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3a833-102">Conventions for Combining Search Conditions in the Criteria Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="3a833-103">Puede crear consultas que incluyan un número arbitrario de condiciones de búsqueda vinculadas con un número arbitrario de operadores AND y OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-103">You can create queries that include any number of search conditions, linked with any number of AND and OR operators.</span></span> <span data-ttu-id="3a833-104">Una consulta con una combinación de cláusulas AND y OR puede llegar a ser compleja, por lo que le será de ayuda entender cómo se interpreta una consulta cuando se ejecuta y cómo se representa en el [panel Criterios](visual-database-tools.md) y en el [panel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a833-104">A query with a combination of AND and OR clauses can become complex, so it is helpful to understand how such a query is interpreted when you execute it, and how such a query is represented in the [Criteria Pane](visual-database-tools.md) and [SQL Pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a833-105">Para detalles sobre las condiciones de búsqueda que solo contienen un operador AND u OR, consulte [Especificar varias condiciones de búsqueda para una columna &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) y [Especificar varias condiciones de búsqueda para varias columnas &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a833-105">For details about search conditions that contain only one AND or OR operator, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) and [Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="3a833-106">Más adelante encontrará información sobre:</span><span class="sxs-lookup"><span data-stu-id="3a833-106">Below you will find information about:</span></span>  
  
-   <span data-ttu-id="3a833-107">La prioridad de los operadores AND y OR en consultas que contienen los dos tipos de operador.</span><span class="sxs-lookup"><span data-stu-id="3a833-107">The precedence of AND and OR in queries that contain both.</span></span>  
  
-   <span data-ttu-id="3a833-108">Cómo se relacionan lógicamente entre sí las condiciones en las cláusulas AND y OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-108">How the conditions in AND and OR clauses relate logically to one another.</span></span>  
  
-   <span data-ttu-id="3a833-109">Cómo representa el Diseñador de consultas y vistas las consultas que contienen los operadores AND y OR en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="3a833-109">How the Query and View Designer represents in the Criteria Pane queries that contain both AND and OR.</span></span>  
  
 <span data-ttu-id="3a833-110">Para ayudarle a entender lo que se trata a continuación, suponga que trabaja con una tabla `employee` que contiene las columnas `hire_date`, `job_lvl`y `status`.</span><span class="sxs-lookup"><span data-stu-id="3a833-110">To help you understand the discussion below, imagine that you are working with an `employee` table containing the columns `hire_date`, `job_lvl`, and `status`.</span></span> <span data-ttu-id="3a833-111">En los ejemplos se supone que necesita conocer cierta información, como la antigüedad de un empleado en la compañía (es decir, la fecha de contratación del empleado), el tipo de trabajo que realiza (su categoría laboral) y su estado (por ejemplo, jubilado).</span><span class="sxs-lookup"><span data-stu-id="3a833-111">The examples assume that you need to know information such as how long an employee has worked with the company (that is, what the employee's hire date is), what type of job the employee performs (what the job level is), and the employee's status (for example, retired).</span></span>  
  
## <a name="precedence-of-and-and-or"></a><span data-ttu-id="3a833-112">Prioridad de AND y OR</span><span class="sxs-lookup"><span data-stu-id="3a833-112">Precedence of AND and OR</span></span>  
 <span data-ttu-id="3a833-113">Cuando se ejecuta una consulta, primero se evalúan las cláusulas vinculadas con operadores AND y después las vinculadas con operadores OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-113">When a query is executed, it evaluates first the clauses linked with AND, and then those linked with OR.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a833-114">El operador NOT tiene prioridad sobre AND y OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-114">The NOT operator takes precedence over both AND and OR.</span></span>  
  
 <span data-ttu-id="3a833-115">Por ejemplo, para buscar empleados con una antigüedad de más de cinco años en puestos de categoría inferior o empleados con puestos de categoría intermedia sin tener en cuenta su fecha de contratación, puede crear una cláusula WHERE como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a833-115">For example, to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs without regard for their hire date, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   job_lvl = 100 OR  
   job_lvl = 200  
  
```  
  
 <span data-ttu-id="3a833-116">Para pasar por alto la prioridad predeterminada de AND sobre OR, puede escribir las condiciones específicas entre paréntesis en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="3a833-116">To override the default precedence of AND over OR, you can put parentheses around specific conditions in the SQL pane.</span></span> <span data-ttu-id="3a833-117">Siempre se evalúan primero las condiciones que van entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="3a833-117">Conditions in parentheses are always evaluated first.</span></span> <span data-ttu-id="3a833-118">Por ejemplo, para buscar todos los empleados con una antigüedad superior a cinco años en puestos inferiores o intermedios, puede crear una cláusula WHERE como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a833-118">For example, to find all employees who have been with the company more than five years in either lower or middle-level jobs, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
> [!TIP]  
>  <span data-ttu-id="3a833-119">Para mayor claridad, se recomienda escribir siempre paréntesis al combinar las cláusulas AND y OR en lugar de basarse en las prioridades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="3a833-119">It is recommended that, for clarity, you always include parentheses when combining AND and OR clauses instead of relying on the default precedence.</span></span>  
  
## <a name="how-and-works-with-multiple-or-clauses"></a><span data-ttu-id="3a833-120">Cómo funciona AND con varias cláusulas OR</span><span class="sxs-lookup"><span data-stu-id="3a833-120">How AND Works with Multiple OR Clauses</span></span>  
 <span data-ttu-id="3a833-121">Comprender cómo se relacionan las cláusulas AND y OR cuando se combinan le ayudará a crear y comprender consultas complejas en el Diseñador de consultas y vistas.</span><span class="sxs-lookup"><span data-stu-id="3a833-121">Understanding how AND and OR clauses are related when combined can help you construct and understand complex queries in the Query and View Designer.</span></span>  
  
 <span data-ttu-id="3a833-122">Si vincula varias condiciones con el operador lógico AND, el primer conjunto de condiciones vinculadas con AND se aplica a todas las condiciones del segundo conjunto.</span><span class="sxs-lookup"><span data-stu-id="3a833-122">If you link multiple conditions using AND, the first set of conditions linked with AND applies to all the conditions in the second set.</span></span> <span data-ttu-id="3a833-123">Es decir, una condición vinculada con otra condición mediante AND se distribuye a todas las condiciones del segundo conjunto.</span><span class="sxs-lookup"><span data-stu-id="3a833-123">In other words, a condition linked with AND to another condition is distributed to all the conditions in the second set.</span></span> <span data-ttu-id="3a833-124">Por ejemplo, la siguiente representación esquemática muestra una condición AND vinculada a un conjunto de condiciones OR:</span><span class="sxs-lookup"><span data-stu-id="3a833-124">For example, the following schematic representation shows an AND condition linked to a set of OR conditions:</span></span>  
  
```  
A AND (B OR C)  
```  
  
 <span data-ttu-id="3a833-125">La representación anterior es equivalente lógicamente a la siguiente representación esquemática, que muestra cómo se aplica la condición AND al segundo conjunto de condiciones:</span><span class="sxs-lookup"><span data-stu-id="3a833-125">The representation above is logically equivalent to the following schematic representation, which shows how the AND condition is distributed to the second set of conditions:</span></span>  
  
```  
(A AND B) OR (A AND C)  
```  
  
 <span data-ttu-id="3a833-126">Este principio distributivo afecta al uso del Diseñador de consultas y vistas.</span><span class="sxs-lookup"><span data-stu-id="3a833-126">This distributive principle affects how you use the Query and View Designer.</span></span> <span data-ttu-id="3a833-127">Por ejemplo, suponga que busca todos empleados con una antigüedad superior a cinco años en puestos inferiores o intermedios.</span><span class="sxs-lookup"><span data-stu-id="3a833-127">For example, imagine that you are looking for all employees who have been with the company more than five years in either lower or middle-level jobs.</span></span> <span data-ttu-id="3a833-128">Escriba la siguiente cláusula WHERE en la instrucción del panel SQL:</span><span class="sxs-lookup"><span data-stu-id="3a833-128">You enter the following WHERE clause into the statement in the SQL pane:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
 <span data-ttu-id="3a833-129">La cláusula vinculada mediante AND se aplica a las dos cláusulas vinculadas mediante OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-129">The clause linked with AND applies to both clauses linked with OR.</span></span> <span data-ttu-id="3a833-130">Una forma explícita de expresar esto es repetir la condición AND una vez por cada condición de la cláusula OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-130">An explicit way to express this is to repeat the AND condition once for each condition in the OR clause.</span></span> <span data-ttu-id="3a833-131">La siguiente instrucción es más explícita (y más larga) que la instrucción anterior, pero es equivalente lógicamente a ella:</span><span class="sxs-lookup"><span data-stu-id="3a833-131">The following statement is more explicit (and longer) than the previous statement, but is logically equivalent to it:</span></span>  
  
```  
WHERE    (hire_date < '01/01/95' ) AND  
  (job_lvl = 100) OR   
  (hire_date < '01/01/95' ) AND   
  (job_lvl = 200)  
```  
  
 <span data-ttu-id="3a833-132">Se aplica el principio de distribuir cláusulas AND en cláusulas OR independientemente del número de condiciones individuales utilizadas.</span><span class="sxs-lookup"><span data-stu-id="3a833-132">The principle of distributing AND clauses to linked OR clauses applies no matter how many individual conditions are involved.</span></span> <span data-ttu-id="3a833-133">Por ejemplo, suponga que desea encontrar todos los empleados con puestos de categoría superior o intermedia con una antigüedad de más de cinco años o que estén jubilados.</span><span class="sxs-lookup"><span data-stu-id="3a833-133">For example, imagine that you want to find higher or middle-level employees who have been with the company more than five years or are retired.</span></span> <span data-ttu-id="3a833-134">La cláusula WHERE sería parecida a ésta:</span><span class="sxs-lookup"><span data-stu-id="3a833-134">The WHERE clause might look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 OR job_lvl = 300) AND  
   (hire_date < '01/01/95' ) OR (status = 'R')  
```  
  
 <span data-ttu-id="3a833-135">Después de distribuir estas condiciones vinculadas con AND, la cláusula WHERE se parecerá a ésta:</span><span class="sxs-lookup"><span data-stu-id="3a833-135">After the conditions linked with AND have been distributed, the WHERE clause will look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 200 AND status = 'R') OR  
   (job_lvl = 300 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 300 AND status = 'R')   
```  
  
## <a name="how-multiple-and-and-or-clauses-are-represented-in-the-criteria-pane"></a><span data-ttu-id="3a833-136">Cómo se representan varias cláusulas AND y OR en el panel Criterios</span><span class="sxs-lookup"><span data-stu-id="3a833-136">How Multiple AND and OR Clauses Are Represented in the Criteria Pane</span></span>  
 <span data-ttu-id="3a833-137">El Diseñador de consultas y vistas representa las condiciones de búsqueda en el [panel Criterios](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a833-137">The Query and View Designer represents your search conditions in the [Criteria Pane](visual-database-tools.md).</span></span> <span data-ttu-id="3a833-138">Sin embargo, en algunos casos en los que hay varias cláusulas vinculadas con AND y OR, la representación del panel Criterios podría no ser la esperada.</span><span class="sxs-lookup"><span data-stu-id="3a833-138">However, in some cases that involve multiple clauses linked with AND and OR, the representation in the Criteria Pane might not be what you expect.</span></span> <span data-ttu-id="3a833-139">Además, si modifica una consulta en el panel Criterios o el [panel Diagrama](diagram-pane-visual-database-tools.md), podría suceder que la instrucción SQL mostrada sea distinta de la que escribió.</span><span class="sxs-lookup"><span data-stu-id="3a833-139">In addition, if you modify your query in the Criteria Pane or [Diagram Pane](diagram-pane-visual-database-tools.md), you might find that your SQL statement has been changed from what you entered.</span></span>  
  
 <span data-ttu-id="3a833-140">En general, estas reglas definen cómo se van a mostrar las cláusulas AND y OR en el panel Criterios:</span><span class="sxs-lookup"><span data-stu-id="3a833-140">In general, these rules dictate how AND and OR clauses appear in the Criteria Pane:</span></span>  
  
-   <span data-ttu-id="3a833-141">Todas las condiciones vinculadas con AND aparecerán o bien en la misma columna **O...** o bien en la columna de cuadrícula **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="3a833-141">All conditions linked with AND appear in the **Filter** grid column or in the same **Or...** column.</span></span>  
  
-   <span data-ttu-id="3a833-142">Todas las condiciones vinculadas con OR aparecerán en columnas **O…** separadas.</span><span class="sxs-lookup"><span data-stu-id="3a833-142">All conditions linked with OR appear in separate **Or...** columns.</span></span>  
  
-   <span data-ttu-id="3a833-143">Si el resultado lógico de una combinación de cláusulas AND y OR es que AND se distribuye en varias cláusulas OR, esto se representará de forma explícita en el panel Criterios donde la cláusula AND se repetirá tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3a833-143">If the logical result of a combination of AND and OR clauses is that the AND is distributed into several OR clauses, the Criteria Pane represents this explicitly by repeating the AND clause as many times as necessary.</span></span>  
  
 <span data-ttu-id="3a833-144">Por ejemplo, podría crear en el panel SQL una condición de búsqueda como la siguiente, en la que dos cláusulas vinculadas mediante AND tienen prioridad sobre una tercera cláusula vinculada mediante OR:</span><span class="sxs-lookup"><span data-stu-id="3a833-144">For example, in the SQL pane you might create a search condition such as the following, in which two clauses linked with AND take precedence over a third one linked with OR:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  (job_lvl = 100) OR   
  (status = 'R')  
```  
  
 <span data-ttu-id="3a833-145">El Diseñador de consultas y vistas representa esta cláusula WHERE en el panel Criterios de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3a833-145">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="3a833-146">![Precedencia de la cláusula OR en el panel Criterios](../../database-engine/media//vs-criteriapane1.gif "Precedencia de la cláusula OR en el panel Criterios")</span><span class="sxs-lookup"><span data-stu-id="3a833-146">![OR clause precedence in the Criteria Pane](../../database-engine/media//vs-criteriapane1.gif "OR clause precedence in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="3a833-147">Sin embargo, si las cláusulas OR vinculadas tienen prioridad sobre una cláusula AND, se repetirá la cláusula AND para cada cláusula OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-147">However, if the linked OR clauses take precedence over an AND clause, the AND clause is repeated for each OR clause.</span></span> <span data-ttu-id="3a833-148">Esto hace que la cláusula AND se distribuya en cada cláusula OR.</span><span class="sxs-lookup"><span data-stu-id="3a833-148">This causes the AND clause to be distributed to each OR clause.</span></span> <span data-ttu-id="3a833-149">Por ejemplo, en el panel SQL podría crearse una cláusula WHERE como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a833-149">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ( (job_lvl = 100) OR   
  (status = 'R') )  
```  
  
 <span data-ttu-id="3a833-150">El Diseñador de consultas y vistas representa esta cláusula WHERE en el panel Criterios de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3a833-150">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="3a833-151">![Varias cláusulas AND y OR en el panel Criterios](../../database-engine/media//vs-criteriapane2.gif "Varias cláusulas AND y OR en el panel Criterios")</span><span class="sxs-lookup"><span data-stu-id="3a833-151">![Multiple AND and OR clauses in the Criteria Pane](../../database-engine/media//vs-criteriapane2.gif "Multiple AND and OR clauses in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="3a833-152">Si las cláusulas OR vinculadas solo incluyen una columna de datos, el Diseñador de consultas y vistas puede colocar la cláusula OR completa en una sola celda de la cuadrícula y así se evita la necesidad de repetir la cláusula AND.</span><span class="sxs-lookup"><span data-stu-id="3a833-152">If the linked OR clauses involve only one data column, the Query and View Designer can place the entire OR clause into a single cell of the grid, avoiding the need to repeat the AND clause.</span></span> <span data-ttu-id="3a833-153">Por ejemplo, en el panel SQL podría crearse una cláusula WHERE como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a833-153">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ((status = 'R') OR (status = 'A'))  
```  
  
 <span data-ttu-id="3a833-154">El Diseñador de consultas y vistas representa esta cláusula WHERE en el panel Criterios de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3a833-154">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="3a833-155">![Cláusulas OR vinculadas definidas en el panel Criterios](../../database-engine/media//vs-criteriapane3.gif "Cláusulas OR vinculadas definidas en el panel Criterios")</span><span class="sxs-lookup"><span data-stu-id="3a833-155">![Linked OR clauses defined in the Criteria Pane](../../database-engine/media//vs-criteriapane3.gif "Linked OR clauses defined in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="3a833-156">Si cambia la consulta (cambia, por ejemplo, uno de los valores en el panel Criterios), el Diseñador de consultas y vistas volverá a crear la instrucción SQL en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="3a833-156">If you make a change to the query (such as changing one of the values in the Criteria Pane), the Query and View Designer recreates the SQL statement in the SQL pane.</span></span> <span data-ttu-id="3a833-157">La nueva instrucción SQL reflejará lo que se muestra en el panel Criterios en lugar de lo que se indica en la instrucción original.</span><span class="sxs-lookup"><span data-stu-id="3a833-157">The recreated SQL statement will resemble the Criteria Pane display rather than your original statement.</span></span> <span data-ttu-id="3a833-158">Por ejemplo, si el panel Criterios contiene cláusulas AND distribuidas, se volverá a crear la instrucción resultante en el panel SQL con cláusulas AND explícitas.</span><span class="sxs-lookup"><span data-stu-id="3a833-158">For example, if the Criteria Pane contains distributed AND clauses, the resulting statement in the SQL pane will be recreated with explicit distributed AND clauses.</span></span> <span data-ttu-id="3a833-159">Para obtener información detallada, vea "Cómo funciona AND con varias cláusulas OR" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="3a833-159">For details, see "How AND Works with Multiple OR Clauses" earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a833-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a833-160">See Also</span></span>  
 [<span data-ttu-id="3a833-161">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3a833-161">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
