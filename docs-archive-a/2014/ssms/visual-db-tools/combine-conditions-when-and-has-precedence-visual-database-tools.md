---
title: Combinar condiciones cuando AND tiene prioridad (Visual Database Tools) | Microsoft Docs
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
- combining search conditions
- AND, Criteria pane
ms.assetid: 450eb2eb-6ea3-405b-8dd2-1ff926c016e7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 917d5381bc83083ee1fa3c07375945c0908da521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743862"
---
# <a name="combine-conditions-when-and-has-precedence-visual-database-tools"></a><span data-ttu-id="b30e3-102">Combinar condiciones cuando AND tiene prioridad (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b30e3-102">Combine Conditions When AND Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="b30e3-103">Para combinar condiciones con AND, agregue la columna a la consulta dos veces (una para cada condición).</span><span class="sxs-lookup"><span data-stu-id="b30e3-103">To combine conditions with AND, you add the column to the query twice--once for each condition.</span></span> <span data-ttu-id="b30e3-104">Para combinar condiciones con OR, debe incluir la primera de ellas en la columna Filtro y las demás en una columna **O…** .</span><span class="sxs-lookup"><span data-stu-id="b30e3-104">To combine conditions with OR, you put the first one in the Filter column and additional conditions into an **Or...** column.</span></span>  
  
 <span data-ttu-id="b30e3-105">Imagine, por ejemplo, que desea buscar los empleados que llevan trabajando más de cinco años en la compañía en puestos de bajo nivel o los empleados con puestos de nivel intermedio independientemente de su fecha de contratación.</span><span class="sxs-lookup"><span data-stu-id="b30e3-105">For example, imagine that you want to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs regardless of their hire date.</span></span> <span data-ttu-id="b30e3-106">Esta consulta requiere tres condiciones, dos de ellas unidas con AND:</span><span class="sxs-lookup"><span data-stu-id="b30e3-106">This query requires three conditions, two of them linked with AND:</span></span>  
  
-   <span data-ttu-id="b30e3-107">Empleados con una fecha de contratación anterior a cinco años AND con un puesto de nivel 100.</span><span class="sxs-lookup"><span data-stu-id="b30e3-107">Employees with a hire date earlier than five years ago AND with a job level of 100.</span></span>  
  
     <span data-ttu-id="b30e3-108">O bien</span><span class="sxs-lookup"><span data-stu-id="b30e3-108">-or-</span></span>  
  
-   <span data-ttu-id="b30e3-109">Empleados con un puesto de nivel 200.</span><span class="sxs-lookup"><span data-stu-id="b30e3-109">Employees with a job level of 200.</span></span>  
  
### <a name="to-combine-conditions-when-and-has-precedence"></a><span data-ttu-id="b30e3-110">Para combinar condiciones cuando AND tiene precedencia</span><span class="sxs-lookup"><span data-stu-id="b30e3-110">To combine conditions when AND has precedence</span></span>  
  
1.  <span data-ttu-id="b30e3-111">En el [panel Criterios](visual-database-tools.md), agregue las columnas de datos en las que desee realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b30e3-111">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="b30e3-112">Si desea buscar en la misma columna utilizando dos o más condiciones unidas con AND, debe agregar el nombre de la columna de datos una vez por cada valor que desee buscar.</span><span class="sxs-lookup"><span data-stu-id="b30e3-112">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="b30e3-113">En la columna **Filtro** , especifique todas las condiciones que desea vincular con AND.</span><span class="sxs-lookup"><span data-stu-id="b30e3-113">In the **Filter** column, enter all the conditions that you want to link with AND.</span></span> <span data-ttu-id="b30e3-114">Por ejemplo, para vincular condiciones con AND que busquen en las columnas `hire_date` y `job_lvl` , deberán especificarse los valores `< '1/1/91'` y `= 100`, respectivamente, en la columna Filtro.</span><span class="sxs-lookup"><span data-stu-id="b30e3-114">For example, to link conditions with AND that search the `hire_date` and `job_lvl` columns, enter the values `< '1/1/91'` and `= 100`, respectively, in the Filter column.</span></span>  
  
     <span data-ttu-id="b30e3-115">Estas entradas de la cuadrícula generan la siguiente cláusula WHERE en la instrucción del [panel SQL](sql-pane-visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="b30e3-115">These grid entries produce the following WHERE clause in the statement in the [SQL Pane](sql-pane-visual-database-tools.md):</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91') AND  
      (job_lvl = 100)  
    ```  
  
3.  <span data-ttu-id="b30e3-116">En la columna de cuadrícula **O...** , especifique las condiciones que desea unir con OR.</span><span class="sxs-lookup"><span data-stu-id="b30e3-116">In the **Or...** grid column, enter conditions that you want to link with OR.</span></span> <span data-ttu-id="b30e3-117">Por ejemplo, para agregar una condición que busque otro valor en la columna `job_lvl` , especifique un valor adicional en la columna **O…** (por ejemplo, `= 200`).</span><span class="sxs-lookup"><span data-stu-id="b30e3-117">For example, to add a condition that searches for another value in the `job_lvl` column, enter an additional value in the **Or...** column, such as `= 200`.</span></span>  
  
     <span data-ttu-id="b30e3-118">Al agregar un valor a la columna **O…** , se agrega otra condición a la cláusula WHERE en la instrucción del panel SQL:</span><span class="sxs-lookup"><span data-stu-id="b30e3-118">Adding a value in the **Or...** column adds another condition to the WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91' ) AND  
      (job_lvl = 100) OR   
      (job_lvl = 200)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b30e3-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b30e3-119">See Also</span></span>  
 <span data-ttu-id="b30e3-120">[Combinar condiciones cuando OR tiene prioridad &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b30e3-120">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b30e3-121">[Convenciones para combinar condiciones de búsqueda en el panel criterios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b30e3-121">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 <span data-ttu-id="b30e3-122">[Reglas para especificar valores de búsqueda &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b30e3-122">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b30e3-123">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b30e3-123">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
