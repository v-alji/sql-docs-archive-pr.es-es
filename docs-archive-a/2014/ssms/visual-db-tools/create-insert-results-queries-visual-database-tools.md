---
title: Crear consultas de inserción de resultados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- result sets [SQL Server], queries
- results [SQL Server], query
- Insert Results query
- queries [SQL Server], results
ms.assetid: 8770d630-09cc-47ec-a0e9-e9de2d7bbc89
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02643c2cf3295debe740a696941f8730d4417254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745601"
---
# <a name="create-insert-results-queries-visual-database-tools"></a><span data-ttu-id="0e478-102">Crear consultas de inserción de resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0e478-102">Create Insert Results Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="0e478-103">Puede copiar filas de una tabla a otra o dentro de una misma tabla utilizando una consulta de inserción de resultados.</span><span class="sxs-lookup"><span data-stu-id="0e478-103">You can copy rows from one table to another or within a table using an Insert Results query.</span></span> <span data-ttu-id="0e478-104">Por ejemplo, en una tabla `titles` , puede utilizar una consulta de inserción de resultados para copiar la información de todos los títulos de una editorial en una segunda tabla y proporcionar esa tabla a la editorial.</span><span class="sxs-lookup"><span data-stu-id="0e478-104">For example, in a `titles` table, you can use an Insert Results query to copy information about all the titles for one publisher to a second table that you can make available to that publisher.</span></span> <span data-ttu-id="0e478-105">Una consulta de inserción de resultados es similar a una consulta de creación de tabla, con la diferencia de que la primera copia las filas en una tabla existente.</span><span class="sxs-lookup"><span data-stu-id="0e478-105">An Insert Results query is similar to Make Table Queries, but copies rows into an existing table.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="0e478-106">También puede copiar filas de una tabla a otra mediante las funciones de cortar y pegar.</span><span class="sxs-lookup"><span data-stu-id="0e478-106">You can also copy rows from one table to another using cut and paste.</span></span> <span data-ttu-id="0e478-107">Cree una consulta para cada tabla y ejecútelas.</span><span class="sxs-lookup"><span data-stu-id="0e478-107">Create a query for each table and run the queries.</span></span> <span data-ttu-id="0e478-108">Copie las filas que desee de una cuadrícula de resultados a la otra.</span><span class="sxs-lookup"><span data-stu-id="0e478-108">Copy the rows you want from one results grid to the other.</span></span>  
  
 <span data-ttu-id="0e478-109">Cuando se crea una consulta de inserción de resultados, se especifica:</span><span class="sxs-lookup"><span data-stu-id="0e478-109">When you create an Insert Results query, you specify:</span></span>  
  
-   <span data-ttu-id="0e478-110">La tabla de base de datos en la que se van a copiar las filas (la tabla de destino).</span><span class="sxs-lookup"><span data-stu-id="0e478-110">The database table to copy rows to (the destination table).</span></span>  
  
-   <span data-ttu-id="0e478-111">Las tablas de las que se van a copiar filas (tabla de origen).</span><span class="sxs-lookup"><span data-stu-id="0e478-111">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="0e478-112">Las tablas de origen forman parte de una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="0e478-112">The source table or tables become part of a subquery.</span></span> <span data-ttu-id="0e478-113">Si va a copiar datos dentro de una tabla, la tabla de origen es la misma que la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0e478-113">If you are copying within a table, the source table is the same as the destination table.</span></span>  
  
-   <span data-ttu-id="0e478-114">Las columnas de la tabla de origen cuyo contenido desea copiar.</span><span class="sxs-lookup"><span data-stu-id="0e478-114">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="0e478-115">Las columnas de la tabla de destino en las que se van a copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="0e478-115">The target columns in the destination table to copy the data to.</span></span>  
  
-   <span data-ttu-id="0e478-116">Las condiciones de búsqueda que definen las filas que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="0e478-116">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="0e478-117">El criterio de ordenación, si desea copiar las filas en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="0e478-117">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="0e478-118">Las opciones Agrupar por, si solo desea copiar información de resumen.</span><span class="sxs-lookup"><span data-stu-id="0e478-118">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="0e478-119">Por ejemplo, la siguiente consulta copia la información de títulos de la tabla `titles` a una tabla de almacenamiento denominada `archivetitles`.</span><span class="sxs-lookup"><span data-stu-id="0e478-119">For example, the following query copies title information from the `titles` table to an archive table called `archivetitles`.</span></span> <span data-ttu-id="0e478-120">La consulta copia el contenido de cuatro columnas de todos los títulos que pertenecen a una determinada editorial:</span><span class="sxs-lookup"><span data-stu-id="0e478-120">The query copies the contents of four columns for all titles belonging to a particular publisher:</span></span>  
  
```  
INSERT INTO archivetitles   
   (title_id, title, type, pub_id)  
SELECT title_id, title, type, pub_id  
FROM titles  
WHERE (pub_id = '0766')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0e478-121">Para insertar valores en una nueva fila, utilice una consulta de inserción de valores.</span><span class="sxs-lookup"><span data-stu-id="0e478-121">To insert values into a new row, use an Insert Values query.</span></span>  
  
 <span data-ttu-id="0e478-122">Puede copiar el contenido de columnas seleccionadas o de todas las columnas de una fila.</span><span class="sxs-lookup"><span data-stu-id="0e478-122">You can copy the contents of selected columns or of all columns in a row.</span></span> <span data-ttu-id="0e478-123">En ambos casos, los datos que se copian deben ser compatibles con las columnas de las filas en las que se van a copiar estos datos.</span><span class="sxs-lookup"><span data-stu-id="0e478-123">In either case, the data you are copying must be compatible with the columns in the rows you are copying to.</span></span> <span data-ttu-id="0e478-124">Por ejemplo, si copia el contenido de una columna como `price`, la columna de la fila donde realice la copia debe aceptar datos numéricos con decimales.</span><span class="sxs-lookup"><span data-stu-id="0e478-124">For example, if you copy the contents of a column such as `price`, the column in the row you are copying to must accept numeric data with decimal places.</span></span> <span data-ttu-id="0e478-125">Si copia una fila entera, la tabla de destino debe tener columnas compatibles en la misma posición física que la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="0e478-125">If you are copying an entire row, the destination table must have compatible columns in the same physical position as the source table.</span></span>  
  
 <span data-ttu-id="0e478-126">Cuando se crea una consulta de inserción de resultados, el panel Criterios varía para reflejar las opciones disponibles para la copia de datos.</span><span class="sxs-lookup"><span data-stu-id="0e478-126">When you create an Insert Results query, the Criteria pane changes to reflect options available for copying data.</span></span> <span data-ttu-id="0e478-127">Se agrega una columna Anexar que permite especificar las columnas en las que deben copiarse los datos.</span><span class="sxs-lookup"><span data-stu-id="0e478-127">An Append column is added to allow you to specify the columns into which data should be copied.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="0e478-128">No se puede deshacer la operación de ejecutar una consulta de inserción de resultados.</span><span class="sxs-lookup"><span data-stu-id="0e478-128">You cannot undo the action of executing an Insert Results query.</span></span> <span data-ttu-id="0e478-129">Como medida de precaución, haga una copia de seguridad de los datos antes de ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="0e478-129">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-results-query"></a><span data-ttu-id="0e478-130">Para crear una consulta de inserción de resultados</span><span class="sxs-lookup"><span data-stu-id="0e478-130">To create an Insert Results query</span></span>  
  
1.  <span data-ttu-id="0e478-131">Cree una nueva consulta y agregue la tabla cuyas filas desea copiar (la tabla de origen).</span><span class="sxs-lookup"><span data-stu-id="0e478-131">Create a new query and add the table from which you want to copy rows (the source table).</span></span> <span data-ttu-id="0e478-132">Si va a copiar datos dentro de una tabla, puede agregar la tabla de origen como tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0e478-132">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
2.  <span data-ttu-id="0e478-133">En el menú **Diseñador de consultas** , seleccione **Cambiar tipo**y, a continuación, haga clic en **Insertar resultados**.</span><span class="sxs-lookup"><span data-stu-id="0e478-133">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
3.  <span data-ttu-id="0e478-134">En el [cuadro de diálogo Elegir tabla de destino para Insertar resultados](visual-database-tools.md), seleccione la tabla en la que va a copiar filas (la tabla de destino).</span><span class="sxs-lookup"><span data-stu-id="0e478-134">In the [Choose Target Table for Insert Results Dialog Box](visual-database-tools.md), select the table to copy rows to (the destination table).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e478-135">El Diseñador de consultas y vistas no puede determinar con antelación las tablas y vistas que se pueden actualizar.</span><span class="sxs-lookup"><span data-stu-id="0e478-135">The Query and View Designer cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="0e478-136">Por tanto, en la lista **Nombre de la tabla** del cuadro de diálogo **Elegir tabla de destino para Insertar resultados** , se muestran todas las tablas y vistas disponibles en la conexión de datos que está consultando, incluso aquellas en las que no se pueden copiar filas.</span><span class="sxs-lookup"><span data-stu-id="0e478-136">Therefore, the **Table Name** list in the **Choose Table for Insert From Query** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
4.  <span data-ttu-id="0e478-137">En el rectángulo que representa la tabla o el objeto con valores de tabla, elija los nombres de las columnas cuyo contenido desea copiar.</span><span class="sxs-lookup"><span data-stu-id="0e478-137">In the rectangle representing the table or table-valued object, choose the names of the columns whose contents you want to copy.</span></span> <span data-ttu-id="0e478-138">Para copiar filas enteras, elija \*\* \* (todas las columnas)\*\*.</span><span class="sxs-lookup"><span data-stu-id="0e478-138">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="0e478-139">El Diseñador de consultas y vistas agrega las columnas elegidas a la columna **Columna** del panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="0e478-139">The Query and View Designer adds the columns you choose to the **Column** column of the Criteriapane.</span></span>  
  
5.  <span data-ttu-id="0e478-140">En la columna **Anexar** del panel Criterios, seleccione una columna de la tabla de destino para cada columna que vaya a copiar.</span><span class="sxs-lookup"><span data-stu-id="0e478-140">In the **Append** column of the Criteria pane, select a target column in the destination table for each column you are copying.</span></span> <span data-ttu-id="0e478-141">Elija \*TableName. \* \* si va a copiar filas enteras.</span><span class="sxs-lookup"><span data-stu-id="0e478-141">Choose *tablename.\** if you are copying entire rows.</span></span> <span data-ttu-id="0e478-142">Las columnas de la tabla de destino deben tener el mismo tipo de datos que las columnas de la tabla de origen o un tipo de datos compatible.</span><span class="sxs-lookup"><span data-stu-id="0e478-142">The columns in the destination table must have the same (or compatible) data types as the columns in the source table.</span></span>  
  
6.  <span data-ttu-id="0e478-143">Si desea copiar las filas en un orden determinado, especifique un criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="0e478-143">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="0e478-144">Para detalles, consulte [Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e478-144">For details, see [Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span></span>  
  
7.  <span data-ttu-id="0e478-145">Indique las filas que desea copiar especificando condiciones de búsqueda en la columna **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="0e478-145">Specify the rows to copy by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="0e478-146">Para detalles, consulte [Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e478-146">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="0e478-147">Si no especifica ninguna condición de búsqueda, se copiarán todas las filas de la tabla de origen en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0e478-147">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e478-148">Cuando se agrega una columna que se desea buscar al panel Criterios, el Diseñador de consultas y vistas la agrega también a la lista de columnas que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="0e478-148">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="0e478-149">Si desea utilizar una columna para realizar una búsqueda, pero sin copiarla, desactive la casilla situada junto al nombre de columna en el rectángulo que representa la tabla o el objeto con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0e478-149">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
8.  <span data-ttu-id="0e478-150">Si desea copiar información de resumen, especifique opciones Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="0e478-150">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="0e478-151">Para detalles, consulte [Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e478-151">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="0e478-152">Cuando se ejecuta una consulta de inserción de resultados, los resultados no se incluyen en el [panel Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e478-152">When you execute an Insert Results query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="0e478-153">En su lugar, aparece un mensaje que indica cuántas filas se han copiado.</span><span class="sxs-lookup"><span data-stu-id="0e478-153">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e478-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e478-154">See Also</span></span>  
 <span data-ttu-id="0e478-155">[Tipos de consultas &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0e478-155">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0e478-156">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0e478-156">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
