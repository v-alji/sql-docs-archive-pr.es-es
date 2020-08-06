---
title: Creación de índices filtrados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- filtered indexes [SQL Server], about filtered indexes
- designing indexes [SQL Server], filtered
- filtered indexes [SQL Server]
- nonclustered indexes [SQL Server], filtered
- indexes [SQL Server], filtered
ms.assetid: 25e1fcc5-45d7-4c53-8c79-5493dfaa1c74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77cf641ca84181496f26a995244029d0525ade63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749861"
---
# <a name="create-filtered-indexes"></a><span data-ttu-id="713c8-102">Crear índices filtrados</span><span class="sxs-lookup"><span data-stu-id="713c8-102">Create Filtered Indexes</span></span>
  <span data-ttu-id="713c8-103">En este tema se describe cómo crear un índice filtrado en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="713c8-103">This topic describes how to create a filtered index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="713c8-104">Un índice filtrado es un índice no clúster optimizado, especialmente indicado para atender consultas que realizan selecciones a partir un subconjunto bien definido de datos.</span><span class="sxs-lookup"><span data-stu-id="713c8-104">A filtered index is an optimized nonclustered index especially suited to cover queries that select from a well-defined subset of data.</span></span> <span data-ttu-id="713c8-105">Utiliza un predicado de filtro para indizar una parte de las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="713c8-105">It uses a filter predicate to index a portion of rows in the table.</span></span> <span data-ttu-id="713c8-106">Un índice filtrado bien diseñado puede mejorar el rendimiento de las consultas, así como reducir los costos de almacenamiento y mantenimiento del índice en comparación con los índices de tabla completa.</span><span class="sxs-lookup"><span data-stu-id="713c8-106">A well-designed filtered index can improve query performance as well as reduce index maintenance and storage costs compared with full-table indexes.</span></span>  
  
 <span data-ttu-id="713c8-107">Los índices filtrados pueden proporcionar las siguientes ventajas respecto a los índices de tabla completa:</span><span class="sxs-lookup"><span data-stu-id="713c8-107">Filtered indexes can provide the following advantages over full-table indexes:</span></span>  
  
-   <span data-ttu-id="713c8-108">**Mejor rendimiento de las consultas y mayor calidad del plan**</span><span class="sxs-lookup"><span data-stu-id="713c8-108">**Improved query performance and plan quality**</span></span>  
  
     <span data-ttu-id="713c8-109">Un índice filtrado bien diseñado mejora el rendimiento de las consultas y la calidad del plan de ejecución porque es menor que un índice no clúster de tabla completa y tiene estadísticas filtradas.</span><span class="sxs-lookup"><span data-stu-id="713c8-109">A well-designed filtered index improves query performance and execution plan quality because it is smaller than a full-table nonclustered index and has filtered statistics.</span></span> <span data-ttu-id="713c8-110">Las estadísticas filtradas son más precisas que las de tabla completa porque corresponden solamente a las filas del índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="713c8-110">The filtered statistics are more accurate than full-table statistics because they cover only the rows in the filtered index.</span></span>  
  
-   <span data-ttu-id="713c8-111">**Menor costo de mantenimiento de índices**</span><span class="sxs-lookup"><span data-stu-id="713c8-111">**Reduced index maintenance costs**</span></span>  
  
     <span data-ttu-id="713c8-112">El mantenimiento de un índice se realiza únicamente cuando las instrucciones de lenguaje de manipulación de datos (DML) afectan a los datos en el índice.</span><span class="sxs-lookup"><span data-stu-id="713c8-112">An index is maintained only when data manipulation language (DML) statements affect the data in the index.</span></span> <span data-ttu-id="713c8-113">Un índice filtrado reduce los costos de mantenimiento del índice en comparación con un índice no clúster de tabla completa, ya que es menor y el mantenimiento se realiza únicamente cuando cambian los datos del índice.</span><span class="sxs-lookup"><span data-stu-id="713c8-113">A filtered index reduces index maintenance costs compared with a full-table nonclustered index because it is smaller and is only maintained when the data in the index is changed.</span></span> <span data-ttu-id="713c8-114">Se puede disponer de una gran cantidad de índices filtrados, sobre todo cuando contienen datos que cambian con poca frecuencia.</span><span class="sxs-lookup"><span data-stu-id="713c8-114">It is possible to have a large number of filtered indexes, especially when they contain data that is changed infrequently.</span></span> <span data-ttu-id="713c8-115">De igual forma, si un índice filtrado contiene únicamente datos que se modifican a menudo, el tamaño menor del índice reduce el costo de actualización de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="713c8-115">Similarly, if a filtered index contains only the frequently modified data, the smaller size of the index reduces the cost of updating the statistics.</span></span>  
  
-   <span data-ttu-id="713c8-116">**Costos reducidos de almacenamiento de índices**</span><span class="sxs-lookup"><span data-stu-id="713c8-116">**Reduced index storage costs**</span></span>  
  
     <span data-ttu-id="713c8-117">La creación de un índice filtrado puede reducir la cantidad de almacenamiento en disco de índices no clúster, cuando no sea necesario un índice de tabla completa.</span><span class="sxs-lookup"><span data-stu-id="713c8-117">Creating a filtered index can reduce disk storage for nonclustered indexes when a full-table index is not necessary.</span></span> <span data-ttu-id="713c8-118">Puede reemplazar un índice no clúster de tabla completa con varios índices filtrados sin aumentar de forma considerable los requisitos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="713c8-118">You can replace a full-table nonclustered index with multiple filtered indexes without significantly increasing the storage requirements.</span></span>  
  
 <span data-ttu-id="713c8-119">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="713c8-119">**In This Topic**</span></span>  
  
-   <span data-ttu-id="713c8-120">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="713c8-120">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="713c8-121">Consideraciones de diseño</span><span class="sxs-lookup"><span data-stu-id="713c8-121">Design Considerations</span></span>](#Design)  
  
     [<span data-ttu-id="713c8-122">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="713c8-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="713c8-123">Seguridad</span><span class="sxs-lookup"><span data-stu-id="713c8-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="713c8-124">**Para crear un índice filtrado, use:**</span><span class="sxs-lookup"><span data-stu-id="713c8-124">**To create a filtered index, using:**</span></span>  
  
     [<span data-ttu-id="713c8-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="713c8-125">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="713c8-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="713c8-126">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="713c8-127">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="713c8-127">Before You Begin</span></span>  
  
###  <a name="design-considerations"></a><a name="Design"></a> <span data-ttu-id="713c8-128">Consideraciones de diseño</span><span class="sxs-lookup"><span data-stu-id="713c8-128">Design Considerations</span></span>  
  
-   <span data-ttu-id="713c8-129">Cuando una columna solamente tiene un número pequeño de valores pertinentes para las consultas, puede crear un índice filtrado en el subconjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="713c8-129">When a column only has a small number of relevant values for queries, you can create a filtered index on the subset of values.</span></span> <span data-ttu-id="713c8-130">Por ejemplo, cuando los valores en una columna son principalmente NULL y la consulta solamente selecciona entre valores distintos de NULL, puede crear un índice filtrado para las filas de datos distintos de NULL.</span><span class="sxs-lookup"><span data-stu-id="713c8-130">For example, when the values in a column are mostly NULL and the query selects only from the non-NULL values, you can create a filtered index for the non-NULL data rows.</span></span> <span data-ttu-id="713c8-131">El índice resultante será menor y tendrá costos de mantenimiento más reducidos que los de un índice no clúster de tabla completa definido en las mismas columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="713c8-131">The resulting index will be smaller and cost less to maintain than a full-table nonclustered index defined on the same key columns.</span></span>  
  
-   <span data-ttu-id="713c8-132">Cuando una tabla tiene filas de datos heterogéneos, se puede crear un índice filtrado para una o varias categorías de datos.</span><span class="sxs-lookup"><span data-stu-id="713c8-132">When a table has heterogeneous data rows, you can create a filtered index for one or more categories of data.</span></span> <span data-ttu-id="713c8-133">Esto puede mejorar el rendimiento de las consultas de estas filas de datos estrechando el foco de una consulta a un área concreta de la tabla.</span><span class="sxs-lookup"><span data-stu-id="713c8-133">This can improve the performance of queries on these data rows by narrowing the focus of a query to a specific area of the table.</span></span> <span data-ttu-id="713c8-134">También en este caso, el índice resultante será menor y tendrá costos de mantenimiento más reducidos que los de un índice no clúster de tabla completa.</span><span class="sxs-lookup"><span data-stu-id="713c8-134">Again, the resulting index will be smaller and cost less to maintain than a full-table nonclustered index.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="713c8-135">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="713c8-135">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="713c8-136">No se puede crear un índice filtrado en una vista.</span><span class="sxs-lookup"><span data-stu-id="713c8-136">You cannot create a filtered index on a view.</span></span> <span data-ttu-id="713c8-137">Sin embargo, el optimizador de consultas puede aprovechar un índice filtrado definido en una tabla a la que se hace referencia en una vista.</span><span class="sxs-lookup"><span data-stu-id="713c8-137">However, the query optimizer can benefit from a filtered index defined on a table that is referenced in a view.</span></span> <span data-ttu-id="713c8-138">El optimizador de consultas tiene en cuenta un índice filtrado para una consulta que selecciona en una vista si los resultados de la consulta serán correctos.</span><span class="sxs-lookup"><span data-stu-id="713c8-138">The query optimizer considers a filtered index for a query that selects from a view if the query results will be correct.</span></span>  
  
-   <span data-ttu-id="713c8-139">Los índices filtrados presentan las ventajas siguientes con respecto a las vistas indizadas:</span><span class="sxs-lookup"><span data-stu-id="713c8-139">Filtered indexes have the following advantages over indexed views:</span></span>  
  
    -   <span data-ttu-id="713c8-140">Menor costo de mantenimiento de índices.</span><span class="sxs-lookup"><span data-stu-id="713c8-140">Reduced index maintenance costs.</span></span> <span data-ttu-id="713c8-141">Por ejemplo, el procesador de consultas utiliza menos recursos de CPU para actualizar un índice filtrado que una vista indizada.</span><span class="sxs-lookup"><span data-stu-id="713c8-141">For example, the query processor uses fewer CPU resources to update a filtered index than an indexed view.</span></span>  
  
    -   <span data-ttu-id="713c8-142">Calidad del plan mejorada.</span><span class="sxs-lookup"><span data-stu-id="713c8-142">Improved plan quality.</span></span> <span data-ttu-id="713c8-143">Por ejemplo, durante la compilación de la consulta, el optimizador de consultas considera la posibilidad de usar un índice filtrado en más situaciones que la vista indizada equivalente.</span><span class="sxs-lookup"><span data-stu-id="713c8-143">For example, during query compilation, the query optimizer considers using a filtered index in more situations than the equivalent indexed view.</span></span>  
  
    -   <span data-ttu-id="713c8-144">El índice en línea se vuelve a generar.</span><span class="sxs-lookup"><span data-stu-id="713c8-144">Online index rebuilds.</span></span> <span data-ttu-id="713c8-145">Puede volver a generar los índices filtrados mientras están disponibles para las consultas.</span><span class="sxs-lookup"><span data-stu-id="713c8-145">You can rebuild filtered indexes while they are available for queries.</span></span> <span data-ttu-id="713c8-146">Esto no es posible en el caso de las vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="713c8-146">Online index rebuilds are not supported for indexed views.</span></span> <span data-ttu-id="713c8-147">Para obtener más información, vea la opción REBUILD de [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="713c8-147">For more information, see the REBUILD option for [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
    -   <span data-ttu-id="713c8-148">Índices no únicos.</span><span class="sxs-lookup"><span data-stu-id="713c8-148">Non-unique indexes.</span></span> <span data-ttu-id="713c8-149">Los índices filtrados pueden ser no únicos, mientras que las vistas indizadas deben ser únicas.</span><span class="sxs-lookup"><span data-stu-id="713c8-149">Filtered indexes can be non-unique, whereas indexed views must be unique.</span></span>  
  
-   <span data-ttu-id="713c8-150">Los índices filtrados se definen en una tabla y solamente admiten operadores de comparación simples.</span><span class="sxs-lookup"><span data-stu-id="713c8-150">Filtered indexes are defined on one table and only support simple comparison operators.</span></span> <span data-ttu-id="713c8-151">Cuando necesite una expresión de filtro que haga referencia a varias tablas o que tenga lógica compleja, deberá crear una vista.</span><span class="sxs-lookup"><span data-stu-id="713c8-151">If you need a filter expression that references multiple tables or has complex logic, you should create a view.</span></span>  
  
-   <span data-ttu-id="713c8-152">Una columna de la expresión del índice filtrado no tiene por qué ser una columna incluida o de clave en la definición del índice filtrado cuando la expresión del índice filtrado es equivalente al predicado de la consulta y la consulta no devuelve la columna de la expresión del índice filtrado con los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="713c8-152">A column in the filtered index expression does not need to be a key or included column in the filtered index definition if the filtered index expression is equivalent to the query predicate and the query does not return the column in the filtered index expression with the query results.</span></span>  
  
-   <span data-ttu-id="713c8-153">Una columna de la expresión del índice filtrado debe ser una columna incluida o de clave de la definición del índice filtrado cuando el predicado de la consulta usa la columna en una comparación no equivalente a la expresión del índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="713c8-153">A column in the filtered index expression should be a key or included column in the filtered index definition if the query predicate uses the column in a comparison that is not equivalent to the filtered index expression.</span></span>  
  
-   <span data-ttu-id="713c8-154">Una columna de la expresión del índice filtrado debe ser una columna incluida o de clave en la definición del índice filtrado si la columna está en el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="713c8-154">A column in the filtered index expression should be a key or included column in the filtered index definition if the column is in the query result set.</span></span>  
  
-   <span data-ttu-id="713c8-155">La clave de índice clúster de la tabla no tiene por qué ser una columna incluida o de clave de la definición del índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="713c8-155">The clustered index key of the table does not need to be a key or included column in the filtered index definition.</span></span> <span data-ttu-id="713c8-156">La clave de índice cluster se incluye de forma automática en todos los índices no clúster, incluidos los índices filtrados.</span><span class="sxs-lookup"><span data-stu-id="713c8-156">The clustered index key is automatically included in all nonclustered indexes, including filtered indexes.</span></span>  
  
-   <span data-ttu-id="713c8-157">Si el operador de comparación especificado en la expresión del índice filtrado del índice filtrado produce una conversión de datos implícita o explícita, se producirá un error cuando la conversión se realice en el lado izquierdo de un operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="713c8-157">If the comparison operator specified in the filtered index expression of the filtered index results in an implicit or explicit data conversion, an error will occur if the conversion occurs on the left side of a comparison operator.</span></span> <span data-ttu-id="713c8-158">Una posible solución es escribir la expresión del índice filtrado con el operador de conversión de datos (CAST o CONVERT) en el lado derecho del operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="713c8-158">A solution is to write the filtered index expression with the data conversion operator (CAST or CONVERT) on the right side of the comparison operator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="713c8-159">Seguridad</span><span class="sxs-lookup"><span data-stu-id="713c8-159">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="713c8-160">Permisos</span><span class="sxs-lookup"><span data-stu-id="713c8-160">Permissions</span></span>  
 <span data-ttu-id="713c8-161">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="713c8-161">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="713c8-162">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="713c8-162">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span> <span data-ttu-id="713c8-163">Para modificar la expresión de índice filtrado, utilice CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="713c8-163">To modify the filtered index expression, use CREATE INDEX WITH DROP_EXISTING.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="713c8-164">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="713c8-164">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="713c8-165">Para crear un índice filtrado</span><span class="sxs-lookup"><span data-stu-id="713c8-165">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="713c8-166">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea crear un índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="713c8-166">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create a filtered index.</span></span>  
  
2.  <span data-ttu-id="713c8-167">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="713c8-167">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="713c8-168">Haga clic en el signo más para expandir la tabla en la que desea crear un índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="713c8-168">Click the plus sign to expand the table on which you want to create a filtered index.</span></span>  
  
4.  <span data-ttu-id="713c8-169">Haga clic con el botón derecho en la carpeta **Índices**, seleccione **Nuevo índice** y, luego, **Índice no agrupado...** .</span><span class="sxs-lookup"><span data-stu-id="713c8-169">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="713c8-170">En el cuadro de diálogo **Nuevo índice** , en la página **General** , escriba el nombre del nuevo índice en el cuadro **Nombre de índice** .</span><span class="sxs-lookup"><span data-stu-id="713c8-170">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="713c8-171">Debajo de **Columnas de clave de índice**, haga clic en **Agregar...** .</span><span class="sxs-lookup"><span data-stu-id="713c8-171">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="713c8-172">En el cuadro de diálogo **seleccionar columnas de**_TABLE_NAME_ , active las casillas de las columnas de tabla que se van a agregar al índice único.</span><span class="sxs-lookup"><span data-stu-id="713c8-172">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
8.  <span data-ttu-id="713c8-173">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="713c8-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="713c8-174">En la página **Filtro**, debajo de **Expresión de filtro**, escriba la expresión SQL que usará para crear el índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="713c8-174">On the **Filter** page, under **Filter Expression**, enter SQL expression that you'll use to create the filtered index.</span></span>  
  
10. <span data-ttu-id="713c8-175">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="713c8-175">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="713c8-176">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="713c8-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="713c8-177">Para crear un índice filtrado</span><span class="sxs-lookup"><span data-stu-id="713c8-177">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="713c8-178">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="713c8-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="713c8-179">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="713c8-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="713c8-180">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="713c8-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Looks for an existing filtered index named "FIBillOfMaterialsWithEndDate"  
    -- and deletes it from the table Production.BillOfMaterials if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
        WHERE name = N'FIBillOfMaterialsWithEndDate'  
        AND object_id = OBJECT_ID (N'Production.BillOfMaterials'))  
    DROP INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials  
    GO  
    -- Creates a filtered index "FIBillOfMaterialsWithEndDate"  
    -- on the table Production.BillOfMaterials   
    -- using the columms ComponentID and StartDate.  
  
    CREATE NONCLUSTERED INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials (ComponentID, StartDate)  
        WHERE EndDate IS NOT NULL ;  
    GO  
    ```  
  
     <span data-ttu-id="713c8-181">El índice filtrado anterior es válido para la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="713c8-181">The filtered index above is valid for the following query.</span></span> <span data-ttu-id="713c8-182">Puede mostrar el plan de ejecución de consultas para determinar si el optimizador de consultas ha utilizado el índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="713c8-182">You can display the query execution plan to determine if the query optimizer used the filtered index.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ProductAssemblyID, ComponentID, StartDate   
    FROM Production.BillOfMaterials  
    WHERE EndDate IS NOT NULL   
        AND ComponentID = 5   
        AND StartDate > '01/01/2008' ;  
    GO  
    ```  
  
#### <a name="to-ensure-that-a-filtered-index-is-used-in-a-sql-query"></a><span data-ttu-id="713c8-183">Para asegurarse de que un índice filtrado se usa en una consulta SQL</span><span class="sxs-lookup"><span data-stu-id="713c8-183">To ensure that a filtered index is used in a SQL query</span></span>  
  
1.  <span data-ttu-id="713c8-184">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="713c8-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="713c8-185">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="713c8-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="713c8-186">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="713c8-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ComponentID, StartDate FROM Production.BillOfMaterials  
        WITH ( INDEX ( FIBillOfMaterialsWithEndDate ) )   
    WHERE EndDate IN ('20000825', '20000908', '20000918');   
    GO  
    ```  
  
 <span data-ttu-id="713c8-187">Para obtener más información, vea [CREATE INDEX&#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="713c8-187">For more information, see  [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
