---
title: Combinar condiciones cuando OR tiene prioridad (Visual Database Tools) | Microsoft Docs
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
- OR operator
ms.assetid: b30f5ac9-25e7-4163-80ed-44e4bccb455d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8be0d2f783c28662eb01f6bf191dc24d339534f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743859"
---
# <a name="combine-conditions-when-or-has-precedence-visual-database-tools"></a><span data-ttu-id="708f8-102">Combinar condiciones cuando OR tiene prioridad (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="708f8-102">Combine Conditions When OR Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="708f8-103">Para vincular condiciones con OR y darle prioridad sobre condiciones vinculadas con AND, debe repetir la condición AND para cada condición OR.</span><span class="sxs-lookup"><span data-stu-id="708f8-103">To link conditions with OR and give them precedence over conditions linked with AND, you must repeat the AND condition for each OR condition.</span></span>  
  
 <span data-ttu-id="708f8-104">Imagine, por ejemplo, que desea buscar todos los empleados que han estado en la compañía más de cinco años y que tienen puestos de nivel bajo o están jubilados.</span><span class="sxs-lookup"><span data-stu-id="708f8-104">For example, imagine that you want to find all employees who have been with the company more than five years and have lower-level jobs or are retired.</span></span> <span data-ttu-id="708f8-105">Esta consulta requiere tres condiciones, una única condición vinculada a dos condiciones adicionales con AND:</span><span class="sxs-lookup"><span data-stu-id="708f8-105">This query requires three conditions, a single condition linked to two additional conditions with AND:</span></span>  
  
-   <span data-ttu-id="708f8-106">Empleados con una fecha de contratación anterior a cinco años y</span><span class="sxs-lookup"><span data-stu-id="708f8-106">Employees with a hire date earlier than five years ago, and</span></span>  
  
-   <span data-ttu-id="708f8-107">Empleados con un puesto de nivel 100 o cuyo estado sea "R" (jubilado).</span><span class="sxs-lookup"><span data-stu-id="708f8-107">Employees with a job level of 100 or whose status is "R" (for retired).</span></span>  
  
 <span data-ttu-id="708f8-108">El siguiente procedimiento ilustra cómo crear este tipo de consulta en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="708f8-108">The following procedure illustrates how to create this type of query in the Criteria pane.</span></span>  
  
### <a name="to-combine-conditions-when-or-has-precedence"></a><span data-ttu-id="708f8-109">Para combinar condiciones cuando OR tiene precedencia</span><span class="sxs-lookup"><span data-stu-id="708f8-109">To combine conditions when OR has precedence</span></span>  
  
1.  <span data-ttu-id="708f8-110">En el [panel Criterios](visual-database-tools.md), agregue las columnas de datos en las que desee realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="708f8-110">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="708f8-111">Si desea buscar en la misma columna utilizando dos o más condiciones unidas con AND, debe agregar el nombre de la columna de datos una vez por cada valor que desee buscar.</span><span class="sxs-lookup"><span data-stu-id="708f8-111">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="708f8-112">Cree las condiciones que se van a vincular con OR especificando la primera de ellas en la columna de cuadrícula **Filtro** y la segunda (y siguientes) en columnas **O…** distintas.</span><span class="sxs-lookup"><span data-stu-id="708f8-112">Create the conditions to be linked with OR by entering the first one into the **Filter** grid column and the second (and subsequent ones) into separate **Or...** columns.</span></span> <span data-ttu-id="708f8-113">Por ejemplo, para vincular condiciones con OR que busquen en las columnas `job_lvl` y `status` , especifique `= 100` en la columna **Filtro** para `job_lvl` y `= 'R'` en la columna **O...** para `status`.</span><span class="sxs-lookup"><span data-stu-id="708f8-113">For example, to link conditions with OR that search the `job_lvl` and `status` columns, enter `= 100` in the **Filter** column for `job_lvl` and `= 'R'` in the **Or...** column for `status`.</span></span>  
  
     <span data-ttu-id="708f8-114">Al especificar estos valores en la cuadrícula, se genera la siguiente cláusula WHERE en la instrucción del panel SQL:</span><span class="sxs-lookup"><span data-stu-id="708f8-114">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) OR (status = 'R')  
    ```  
  
3.  <span data-ttu-id="708f8-115">Cree la condición AND especificándola una vez para cada condición OR.</span><span class="sxs-lookup"><span data-stu-id="708f8-115">Create the AND condition by entering it once for each OR condition.</span></span> <span data-ttu-id="708f8-116">Incluya todas las entradas en la misma columna de cuadrícula que la condición OR con la que se corresponden.</span><span class="sxs-lookup"><span data-stu-id="708f8-116">Place each entry in the same grid column as the OR condition it corresponds to.</span></span> <span data-ttu-id="708f8-117">Por ejemplo, para agregar una condición AND que busque en la columna `hire_date` y se aplique a ambas condiciones OR, especifique `< '1/1/91'` tanto en la columna Criterios como en la columna **O…** .</span><span class="sxs-lookup"><span data-stu-id="708f8-117">For example, to add an AND condition that searches the `hire_date` column and applies to both OR conditions, enter `< '1/1/91'` in both the Criteria column and the **Or...** column.</span></span>  
  
     <span data-ttu-id="708f8-118">Al especificar estos valores en la cuadrícula, se genera la siguiente cláusula WHERE en la instrucción del panel SQL:</span><span class="sxs-lookup"><span data-stu-id="708f8-118">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) AND   
      (hire_date < '01/01/91' ) OR  
      (status = 'R') AND   
      (hire_date < '01/01/91' )  
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="708f8-119">Puede repetir una condición AND agregándola una vez y después utilizar los comandos **Cortar** y **Pegar** del menú **Editar** para repetirla en otras condiciones OR.</span><span class="sxs-lookup"><span data-stu-id="708f8-119">You can repeat an AND condition by adding it once, and then using the **Cut** and **Paste** commands from the **Edit** menu to repeat it for other OR conditions.</span></span>  
  
 <span data-ttu-id="708f8-120">La cláusula WHERE creada por el Diseñador de consultas y vistas es equivalente a la siguiente cláusula WHERE, en la que se utilizan paréntesis para especificar la prioridad de OR frente a AND:</span><span class="sxs-lookup"><span data-stu-id="708f8-120">The WHERE clause created by the Query and View Designer is equivalent to the following WHERE clause, which uses parentheses to specify the precedence of OR over AND:</span></span>  
  
```  
WHERE (job_lvl = 100 OR status = 'R') AND  
   (hire_date < '01/01/91')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="708f8-121">Si especifica condiciones de búsqueda en el formato arriba mostrado en el [panel SQL](sql-pane-visual-database-tools.md), pero luego modifica la consulta en los paneles Diagrama o Criterios, el Diseñador de consultas y vistas volverá a crear la instrucción SQL para hacerla coincidir con la forma en que la condición AND se distribuye explícitamente a ambas condiciones OR.</span><span class="sxs-lookup"><span data-stu-id="708f8-121">If you enter the search conditions in the format shown immediately above in the [SQL Pane](sql-pane-visual-database-tools.md), but then make a change to the query in the Diagram or Criteria panes, the Query and View Designer recreates the SQL statement to match the form with the AND condition explicitly distributed to both OR conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708f8-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="708f8-122">See Also</span></span>  
 <span data-ttu-id="708f8-123">[Convenciones para combinar condiciones de búsqueda en el panel criterios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="708f8-123">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="708f8-124">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="708f8-124">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
