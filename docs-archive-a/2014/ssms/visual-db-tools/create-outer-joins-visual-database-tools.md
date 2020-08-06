---
title: Crear combinaciones externas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- joins [SQL Server], outer
ms.assetid: 18de47b1-f936-427d-b852-fe6d20334f71
author: stevestein
ms.author: sstein
ms.openlocfilehash: f02c0be049e2e75e1a657bb3c027d20430d562cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750426"
---
# <a name="create-outer-joins-visual-database-tools"></a><span data-ttu-id="b31e2-102">Crear combinaciones externas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b31e2-102">Create Outer Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="b31e2-103">De forma predeterminada, el [Diseñador de consultas y vistas](visual-database-tools.md) crea una combinación interna entre tablas.</span><span class="sxs-lookup"><span data-stu-id="b31e2-103">By default, the [Query and View Designer](visual-database-tools.md) creates an inner join between tables.</span></span> <span data-ttu-id="b31e2-104">Las combinaciones internas eliminan las filas que no coinciden con alguna fila de la otra tabla.</span><span class="sxs-lookup"><span data-stu-id="b31e2-104">Inner joins eliminate the rows that do not match with a row from the other table.</span></span> <span data-ttu-id="b31e2-105">Sin embargo, las combinaciones externas devuelven todas las filas de una de las tablas o vistas mencionadas en la cláusula FROM, como mínimo, siempre que tales filas cumplan alguna de las condiciones de búsqueda de WHERE o HAVING.</span><span class="sxs-lookup"><span data-stu-id="b31e2-105">Outer joins, however, return all rows from at least one of the tables or views mentioned in the FROM clause, as long as those rows meet any WHERE or HAVING search conditions.</span></span> <span data-ttu-id="b31e2-106">Si desea incluir filas de datos en el conjunto de resultados que no se correspondan con ninguna fila de la tabla combinada, puede crear una combinación externa.</span><span class="sxs-lookup"><span data-stu-id="b31e2-106">If you want to include data rows in the result set that do not have a match in the joined table, you can create an outer join.</span></span>  
  
 <span data-ttu-id="b31e2-107">Cuando se crea una combinación externa, el orden en que aparecen las tablas en la instrucción SQL (el que se muestra en el panel SQL) es importante.</span><span class="sxs-lookup"><span data-stu-id="b31e2-107">When you create an outer join, the order in which tables appear in the SQL statement (as reflected in the SQL pane) is significant.</span></span> <span data-ttu-id="b31e2-108">La primera tabla que se agrega se convierte en la tabla "de la izquierda", y la segunda en la "de la derecha".</span><span class="sxs-lookup"><span data-stu-id="b31e2-108">The first table you add becomes the "left" table and the second table becomes the "right" table.</span></span> <span data-ttu-id="b31e2-109">(El orden real en el que aparecen las tablas en el [panel Diagrama](diagram-pane-visual-database-tools.md) es irrelevante). Cuando se especifica una combinación externa izquierda o derecha, se hace referencia al orden en el que se agregaron las tablas a la consulta y al orden en el que aparecen en la instrucción SQL en el [panel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b31e2-109">(The actual order in which the tables appear in the [Diagram pane](diagram-pane-visual-database-tools.md) is not significant.) When you specify a left or right outer join, you are referring to the order in which the tables were added to the query and to the order in which they appear in the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-an-outer-join"></a><span data-ttu-id="b31e2-110">Para crear una combinación externa</span><span class="sxs-lookup"><span data-stu-id="b31e2-110">To create an outer join</span></span>  
  
1.  <span data-ttu-id="b31e2-111">Cree la combinación, ya sea automática o manualmente.</span><span class="sxs-lookup"><span data-stu-id="b31e2-111">Create the join, either automatically or manually.</span></span> <span data-ttu-id="b31e2-112">Para detalles, consulte [Combinar tablas automáticamente &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) o [Combinar tablas manualmente &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b31e2-112">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) or [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="b31e2-113">Seleccione la línea de combinación en el panel Diagrama y, a continuación, en el menú **Diseñador de consultas**, elija **Seleccionar todas las filas desde \<tablename>** y seleccione el comando que contiene la tabla en la que desea incluir filas adicionales.</span><span class="sxs-lookup"><span data-stu-id="b31e2-113">Select the join line in the Diagram pane, and then from the **Query Designer** menu, choose **Select All Rows from \<tablename>**, selecting the command that includes the table whose extra rows you want to include.</span></span>  
  
    -   <span data-ttu-id="b31e2-114">Elija la primera tabla para crear una combinación externa izquierda.</span><span class="sxs-lookup"><span data-stu-id="b31e2-114">Choose the first table to create a left outer join.</span></span>  
  
    -   <span data-ttu-id="b31e2-115">Elija la segunda tabla para crear una combinación externa derecha.</span><span class="sxs-lookup"><span data-stu-id="b31e2-115">Choose the second table to create a right outer join.</span></span>  
  
    -   <span data-ttu-id="b31e2-116">Elija ambas tablas para crear una combinación externa completa.</span><span class="sxs-lookup"><span data-stu-id="b31e2-116">Choose both tables to create a full outer join.</span></span>  
  
 <span data-ttu-id="b31e2-117">Cuando se especifica una combinación externa, el Diseñador de consultas y vistas modifica la línea de combinación para indicar que se trata de una combinación externa.</span><span class="sxs-lookup"><span data-stu-id="b31e2-117">When you specify an outer join, the Query and View Designer modifies the join line to indicate an outer join.</span></span>  
  
 <span data-ttu-id="b31e2-118">Asimismo, el Diseñador de consultas y vistas modifica la instrucción SQL en el panel SQL para reflejar el cambio en el tipo de combinación, como se muestra en la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="b31e2-118">In addition, the Query and View Designer modifies the SQL statement in the SQL pane to reflect the change in join type, as shown in the following statement:</span></span>  
  
```  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
```  
  
 <span data-ttu-id="b31e2-119">Puesto que las combinaciones externas incluyen filas no coincidentes, puede utilizarlas para buscar filas que infrinjan las restricciones FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="b31e2-119">Because an outer join includes unmatched rows, you can use it to find rows that violate foreign key constraints.</span></span> <span data-ttu-id="b31e2-120">Para ello, cree una combinación externa y, a continuación, agregue una condición de búsqueda para buscar las filas en las que la columna de clave principal de la tabla de la derecha sea NULL.</span><span class="sxs-lookup"><span data-stu-id="b31e2-120">To do so, you create an outer join and then add a search condition to find rows in which the primary key column of the rightmost table is null.</span></span> <span data-ttu-id="b31e2-121">Por ejemplo, la siguiente combinación externa busca las filas de la tabla `employee` que no tienen filas correspondientes en la tabla `jobs` :</span><span class="sxs-lookup"><span data-stu-id="b31e2-121">For example, the following outer join finds rows in the `employee` table that do not have corresponding rows in the `jobs` table:</span></span>  
  
```  
SELECT employee.emp_id, employee.job_id  
FROM employee LEFT OUTER JOIN jobs   
   ON employee.job_id = jobs.job_id  
WHERE (jobs.job_id IS NULL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b31e2-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b31e2-122">See Also</span></span>  
 <span data-ttu-id="b31e2-123">[Realizar consultas con combinaciones &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b31e2-123">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b31e2-124">Cuadro de diálogo Combinar &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b31e2-124">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
