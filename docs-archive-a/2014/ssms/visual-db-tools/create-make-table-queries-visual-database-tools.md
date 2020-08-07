---
title: Crear consultas de creación de tabla (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- table creation [SQL Server], Make Table query
- inserting tables
- Make Table query
- adding tables
ms.assetid: 4493cffa-7b2d-4c24-8ef0-d49329198972
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91c4a3bf45935053789d6e884b1af5b338b4c7c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745600"
---
# <a name="create-make-table-queries-visual-database-tools"></a><span data-ttu-id="65132-102">Crear consultas de creación de tabla (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="65132-102">Create Make Table Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="65132-103">Puede copiar filas en una nueva tabla mediante una consulta de creación de tabla, que sirve para crear subconjuntos de datos con los que trabajar o para copiar el contenido de una tabla de una base de datos a otra.</span><span class="sxs-lookup"><span data-stu-id="65132-103">You can copy rows into a new table using a Make Table query, which is useful for creating subsets of data to work with or copying the contents of a table from one database to another.</span></span> <span data-ttu-id="65132-104">La consulta de creación de tabla es similar a la consulta de inserción de resultados, con la diferencia de que en la primera se crea una nueva tabla en la que se copian las filas.</span><span class="sxs-lookup"><span data-stu-id="65132-104">A Make Table query is similar to an Insert Results query but creates a new table to copy rows into.</span></span>  
  
 <span data-ttu-id="65132-105">Cuando se crea una consulta de creación de tabla, se especifica:</span><span class="sxs-lookup"><span data-stu-id="65132-105">When you create a Make Table query, you specify:</span></span>  
  
-   <span data-ttu-id="65132-106">El nombre de la nueva tabla de base de datos (la tabla de destino).</span><span class="sxs-lookup"><span data-stu-id="65132-106">The name of the new database table (the destination table).</span></span>  
  
-   <span data-ttu-id="65132-107">Las tablas de las que se van a copiar filas (tabla de origen).</span><span class="sxs-lookup"><span data-stu-id="65132-107">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="65132-108">Puede copiar de una sola tabla o de tablas combinadas.</span><span class="sxs-lookup"><span data-stu-id="65132-108">You can copy from a single table or from joined tables.</span></span>  
  
-   <span data-ttu-id="65132-109">Las columnas de la tabla de origen cuyo contenido desea copiar.</span><span class="sxs-lookup"><span data-stu-id="65132-109">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="65132-110">El criterio de ordenación, si desea copiar las filas en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="65132-110">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="65132-111">Las condiciones de búsqueda que definen las filas que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="65132-111">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="65132-112">Las opciones Agrupar por, si solo desea copiar información de resumen.</span><span class="sxs-lookup"><span data-stu-id="65132-112">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="65132-113">Por ejemplo, en la consulta siguiente se crea una nueva tabla llamada `uk`_`customers` y se copia en ella información de la tabla `customers` .</span><span class="sxs-lookup"><span data-stu-id="65132-113">For example, the following query creates a new table called `uk`_`customers` and copies information from the `customers` table to it:</span></span>  
  
```  
SELECT *   
INTO uk_customers  
FROM customers  
WHERE country = 'UK'  
```  
  
 <span data-ttu-id="65132-114">Para utilizar una consulta de creación de tabla correctamente:</span><span class="sxs-lookup"><span data-stu-id="65132-114">In order to use a Make Table query successfully:</span></span>  
  
-   <span data-ttu-id="65132-115">La base de datos debe ser compatible con la sintaxis SELECT...INTO.</span><span class="sxs-lookup"><span data-stu-id="65132-115">Your database must support the SELECT...INTO syntax.</span></span>  
  
-   <span data-ttu-id="65132-116">Debe tener permiso para crear una tabla en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="65132-116">You must have permission to create a table in the target database.</span></span>  
  
### <a name="to-create-a-make-table-query"></a><span data-ttu-id="65132-117">Para crear una consulta de creación de tabla</span><span class="sxs-lookup"><span data-stu-id="65132-117">To create a Make Table query</span></span>  
  
1.  <span data-ttu-id="65132-118">Agregue la tabla o tablas de origen al panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="65132-118">Add the source table or tables to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="65132-119">En el menú **Diseñador de consultas** , seleccione **Tipo de cambio**y, a continuación, haga clic en **Crear tabla**.</span><span class="sxs-lookup"><span data-stu-id="65132-119">From the **Query Designer** menu, point to **Change Type**, and then click **Make Table**.</span></span>  
  
3.  <span data-ttu-id="65132-120">En el cuadro de diálogo **Crear tabla** , escriba el nombre de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="65132-120">In the **Make Table** dialog box, type the name of the destination table.</span></span> <span data-ttu-id="65132-121">El Diseñador de consultas y vistas no comprueba si el nombre ya está en uso o si se dispone de permiso para crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="65132-121">The Query and View Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
     <span data-ttu-id="65132-122">Para crear una tabla de destino en otra base de datos, especifique un nombre de tabla completo, incluido el nombre de la base de datos de destino, el propietario (si es necesario) y el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="65132-122">To create a destination table in another database, specify a fully qualified table name including the name of the target database, the owner (if required), and the name of the table.</span></span>  
  
4.  <span data-ttu-id="65132-123">Defina las columnas que se van a copiar agregándolas a la consulta.</span><span class="sxs-lookup"><span data-stu-id="65132-123">Specify the columns to copy by adding them to the query.</span></span> <span data-ttu-id="65132-124">Para detalles, consulte [Agregar columnas a las consultas &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="65132-124">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="65132-125">Las columnas se copian solo si se agregan a la consulta.</span><span class="sxs-lookup"><span data-stu-id="65132-125">Columns will be copied only if you add them to the query.</span></span> <span data-ttu-id="65132-126">Para copiar filas enteras, elija \*\* \* (todas las columnas)\*\*.</span><span class="sxs-lookup"><span data-stu-id="65132-126">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="65132-127">El Diseñador de consultas y vistas agrega las columnas elegidas a la columna **Columna** del panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="65132-127">The Query and View Designer adds the columns you choose to the **Column** column of the Criteria pane.</span></span>  
  
5.  <span data-ttu-id="65132-128">Si desea copiar las filas en un orden determinado, especifique un criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="65132-128">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="65132-129">Para detalles, consulte **Ordenar y agrupar los resultados de una consulta**.</span><span class="sxs-lookup"><span data-stu-id="65132-129">For details, see **Sorting and Grouping Query Results**.</span></span>  
  
6.  <span data-ttu-id="65132-130">Indique las filas que desea copiar especificando condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="65132-130">Specify the rows to copy by entering search conditions.</span></span> <span data-ttu-id="65132-131">Para detalles, consulte [Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="65132-131">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="65132-132">Si no especifica ninguna condición de búsqueda, se copiarán todas las filas de la tabla de origen en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="65132-132">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65132-133">Cuando se agrega una columna que se desea buscar al panel Criterios, el Diseñador de consultas y vistas la agrega también a la lista de columnas que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="65132-133">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="65132-134">Si desea utilizar una columna para realizar una búsqueda, pero sin copiarla, desactive la casilla situada junto al nombre de columna en el rectángulo que representa la tabla o el objeto con estructura de tabla.</span><span class="sxs-lookup"><span data-stu-id="65132-134">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-structured object.</span></span>  
  
7.  <span data-ttu-id="65132-135">Si desea copiar información de resumen, especifique opciones Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="65132-135">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="65132-136">Para detalles, consulte [Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="65132-136">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="65132-137">Cuando se ejecuta una consulta de creación de tabla, los resultados no se incluyen en el [panel Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="65132-137">When you execute a Make Table query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="65132-138">En su lugar, aparece un mensaje que indica cuántas filas se han copiado.</span><span class="sxs-lookup"><span data-stu-id="65132-138">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65132-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65132-139">See Also</span></span>  
 <span data-ttu-id="65132-140">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="65132-140">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="65132-141">Tipos de consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="65132-141">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
