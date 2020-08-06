---
title: Creación de índices clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], clustered indexes
- clustered indexes, creating
- clustered indexes, PRIMARY KEY constraint
- clustered indexes, UNIQUE constraint
- indexes [SQL Server], clustered
ms.assetid: 47148383-c2c7-4f08-a9e4-7016bf2d1d13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 567ff9a01bd93323149168b9e3aa0f34d78aee39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671992"
---
# <a name="create-clustered-indexes"></a><span data-ttu-id="daada-102">Crear índices clúster</span><span class="sxs-lookup"><span data-stu-id="daada-102">Create Clustered Indexes</span></span>
  <span data-ttu-id="daada-103">Puede crear índices clúster en las tablas de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daada-103">You can create clustered indexes on tables in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="daada-104">Con pocas excepciones, todas las tablas deben tener un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="daada-104">With few exceptions, every table should have a clustered index.</span></span> <span data-ttu-id="daada-105">Además de mejorar el rendimiento de las consultas, un índice clúster se puede recompilar o reorganizar a petición para controlar la fragmentación de las tablas.</span><span class="sxs-lookup"><span data-stu-id="daada-105">Besides improving query performance, a clustered index can be rebuilt or reorganized on demand to control table fragmentation.</span></span> <span data-ttu-id="daada-106">También se puede crear un índice clúster en una vista.</span><span class="sxs-lookup"><span data-stu-id="daada-106">A clustered index can also be created on a view.</span></span> <span data-ttu-id="daada-107">(Los índices agrupados se definen en el tema [Índices agrupados y no agrupados descritos](clustered-and-nonclustered-indexes-described.md)).</span><span class="sxs-lookup"><span data-stu-id="daada-107">(Clustered indexes are defined in the topic [Clustered and Nonclustered Indexes Described](clustered-and-nonclustered-indexes-described.md).)</span></span>  
  
 <span data-ttu-id="daada-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="daada-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="daada-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="daada-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="daada-110">Implementaciones típicas</span><span class="sxs-lookup"><span data-stu-id="daada-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="daada-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="daada-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="daada-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="daada-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="daada-113">**Para crear un índice clúster en una tabla, usando:**</span><span class="sxs-lookup"><span data-stu-id="daada-113">**To create a clustered index on a table, using:**</span></span>  
  
     [<span data-ttu-id="daada-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daada-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="daada-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daada-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="daada-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="daada-116">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="daada-117">Implementaciones típicas</span><span class="sxs-lookup"><span data-stu-id="daada-117">Typical Implementations</span></span>  
 <span data-ttu-id="daada-118">Los clúster se implementan de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="daada-118">Clustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="daada-119">**Restricciones PRIMARY KEY y UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="daada-119">**PRIMARY KEY and UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="daada-120">Cuando se crea una restricción PRIMARY KEY, se crea automáticamente un índice clúster único en las columnas si aún no existe un índice clúster en la tabla o no se ha especificado un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="daada-120">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="daada-121">La columna de clave principal no puede permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="daada-121">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="daada-122">Cuando cree una restricción UNIQUE, se creará un índice no clúster único para exigir una restricción UNIQUE de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="daada-122">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="daada-123">Puede especificarse un índice clúster único si todavía no existe un índice clúster en la tabla.</span><span class="sxs-lookup"><span data-stu-id="daada-123">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="daada-124">Un índice creado como parte de la restricción recibe automáticamente el mismo nombre que la restricción.</span><span class="sxs-lookup"><span data-stu-id="daada-124">An index created as part of the constraint is automatically given the same name as the constraint name.</span></span> <span data-ttu-id="daada-125">Para obtener más información, consulte [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) y [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="daada-125">For more information, see [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) and [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="daada-126">**Índice independiente de una restricción**</span><span class="sxs-lookup"><span data-stu-id="daada-126">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="daada-127">Puede crear un índice clúster en una columna que no sea la de clave principal si se especificó una restricción de clave principal no agrupada.</span><span class="sxs-lookup"><span data-stu-id="daada-127">You can create a clustered index on a column other than primary key column if a nonclustered primary key constraint was specified.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="daada-128">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="daada-128">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="daada-129">Cuando se crea una estructura de índice clúster, se requiere espacio en disco para ambas estructuras, la antigua (origen) y la nueva (destino), en los archivos y grupos de archivos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="daada-129">When a clustered index structure is created, disk space for both the old (source) and new (target) structures is required in their respective files and filegroups.</span></span> <span data-ttu-id="daada-130">La asignación de la antigua estructura no se cancela hasta que se valide la transacción completa.</span><span class="sxs-lookup"><span data-stu-id="daada-130">The old structure is not deallocated until the complete transaction commits.</span></span> <span data-ttu-id="daada-131">Puede que también se necesite espacio en disco temporal para ordenar.</span><span class="sxs-lookup"><span data-stu-id="daada-131">Additional temporary disk space for sorting may also be required.</span></span> <span data-ttu-id="daada-132">Para más información, consulte [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span><span class="sxs-lookup"><span data-stu-id="daada-132">For more information, see [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span></span>  
  
-   <span data-ttu-id="daada-133">Si se crea un índice clúster en un montón con varios índices no clúster existentes, se deben volver a generar todos los índices no clúster de manera que contengan el valor de clave de agrupación en clústeres en lugar del identificador de fila (RID).</span><span class="sxs-lookup"><span data-stu-id="daada-133">If a clustered index is created on a heap with several existing nonclustered indexes, all the nonclustered indexes must be rebuilt so that they contain the clustering key value instead of the row identifier (RID).</span></span> <span data-ttu-id="daada-134">De forma similar, si se quita un índice clúster de una tabla con varios índices no clúster, se vuelven a generar todos los índices no clúster como parte de la operación DROP.</span><span class="sxs-lookup"><span data-stu-id="daada-134">Similarly, if a clustered index is dropped on a table that has several nonclustered indexes, the nonclustered indexes are all rebuilt as part of the DROP operation.</span></span> <span data-ttu-id="daada-135">Si las tablas son de gran tamaño, la operación puede prolongarse significativamente.</span><span class="sxs-lookup"><span data-stu-id="daada-135">This may take significant time on large tables.</span></span>  
  
     <span data-ttu-id="daada-136">La mejor manera de generar índices en tablas de gran tamaño es empezar con el índice clúster y, a continuación, generar los índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="daada-136">The preferred way to build indexes on large tables is to start with the clustered index and then build any nonclustered indexes.</span></span> <span data-ttu-id="daada-137">Considere la posibilidad de establecer la opción ONLINE en ON al crear índices en tablas existentes.</span><span class="sxs-lookup"><span data-stu-id="daada-137">Consider setting the ONLINE option to ON when you create indexes on existing tables.</span></span> <span data-ttu-id="daada-138">Cuando se establece en ON, no se mantienen los bloqueos de tabla de larga duración.</span><span class="sxs-lookup"><span data-stu-id="daada-138">When set to ON, long-term table locks are not held.</span></span> <span data-ttu-id="daada-139">Así se habilita la continuación de consultas o actualizaciones de la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="daada-139">This enables queries or updates to the underlying table to continue.</span></span> <span data-ttu-id="daada-140">Para más información, consulte [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="daada-140">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="daada-141">La clave de índice de un índice clúster no puede contener columnas `varchar` con datos existentes en la unidad de asignación ROW_OVERFLOW_DATA.</span><span class="sxs-lookup"><span data-stu-id="daada-141">The index key of a clustered index cannot contain `varchar` columns that have existing data in the ROW_OVERFLOW_DATA allocation unit.</span></span> <span data-ttu-id="daada-142">Si se crea un índice clúster en una columna `varchar` y los datos existentes están en la unidad de asignación IN_ROW_DATA, no se realizarán correctamente las siguientes acciones de inserción o actualización de la columna que intenten insertar los datos de manera no consecutiva.</span><span class="sxs-lookup"><span data-stu-id="daada-142">If a clustered index is created on a `varchar` column and the existing data is in the IN_ROW_DATA allocation unit, subsequent insert or update actions on the column that would push the data off-row will fail.</span></span> <span data-ttu-id="daada-143">Para obtener información sobre las tablas que pueden contener datos de desbordamiento de fila, use la función de administración dinámica [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="daada-143">To obtain information about tables that might contain row-overflow data, use the [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) dynamic management function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="daada-144">Seguridad</span><span class="sxs-lookup"><span data-stu-id="daada-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="daada-145">Permisos</span><span class="sxs-lookup"><span data-stu-id="daada-145">Permissions</span></span>  
 <span data-ttu-id="daada-146">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="daada-146">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="daada-147">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="daada-147">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="daada-148">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daada-148">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-object-explorer"></a><span data-ttu-id="daada-149">Para crear un índice clúster mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="daada-149">To create a clustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="daada-150">En el Explorador de objetos, expanda la tabla en la que desea crear un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="daada-150">In Object Explorer, expand the table on which you want to create a clustered index.</span></span>  
  
2.  <span data-ttu-id="daada-151">Haga clic con el botón derecho en la carpeta **Índices**, seleccione **Nuevo índice** y, luego, **Índice no agrupado...** .</span><span class="sxs-lookup"><span data-stu-id="daada-151">Right-click the **Indexes** folder, point to **New Index**, and select **Clustered Index...**.</span></span>  
  
3.  <span data-ttu-id="daada-152">En el cuadro de diálogo **Nuevo índice** , en la página **General** , escriba el nombre del nuevo índice en el cuadro **Nombre de índice** .</span><span class="sxs-lookup"><span data-stu-id="daada-152">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
4.  <span data-ttu-id="daada-153">Debajo de **Columnas de clave de índice**, haga clic en **Agregar...** .</span><span class="sxs-lookup"><span data-stu-id="daada-153">Under **Index key columns**, click **Add...**.</span></span>  
  
5.  <span data-ttu-id="daada-154">En el cuadro de diálogo **seleccionar columnas de**_TABLE_NAME_ , active la casilla de la columna de la tabla que se va a agregar al índice clúster.</span><span class="sxs-lookup"><span data-stu-id="daada-154">In the **Select Columns from**_table_name_ dialog box, select the check box of the table column to be added to the clustered index.</span></span>  
  
6.  <span data-ttu-id="daada-155">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="daada-155">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="daada-156">En el cuadro de diálogo **Nuevo índice** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="daada-156">In the **New Index** dialog box, click **OK**.</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-the-table-designer"></a><span data-ttu-id="daada-157">Para crear un índice clúster mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="daada-157">To create a clustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="daada-158">En el Explorador de objetos, expanda la base de datos en la que desea crear una tabla con un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="daada-158">In Object Explorer, expand the database on which you want to create a table with a clustered index.</span></span>  
  
2.  <span data-ttu-id="daada-159">Haga clic con el botón derecho en la carpeta **Tablas** y, luego, haga clic en **Nueva tabla...** .</span><span class="sxs-lookup"><span data-stu-id="daada-159">Right-click the **Tables** folder and click **New Table...**.</span></span>  
  
3.  <span data-ttu-id="daada-160">Cree una tabla nueva como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="daada-160">Create a new table as you normally would.</span></span> <span data-ttu-id="daada-161">Para obtener más información, vea [Crear tablas &#40;motor de base de datos&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="daada-161">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span>  
  
4.  <span data-ttu-id="daada-162">Haga clic con el botón derecho en la nueva tabla creada anteriormente y, luego, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="daada-162">Right-click the new table created above and click **Design**.</span></span>  
  
5.  <span data-ttu-id="daada-163">En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="daada-163">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
6.  <span data-ttu-id="daada-164">En el cuadro de diálogo **Índices o claves** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="daada-164">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
7.  <span data-ttu-id="daada-165">Seleccione el nuevo índice en el cuadro de texto **Clave principal o única, o índice seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="daada-165">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
8.  <span data-ttu-id="daada-166">En la cuadrícula, seleccione **Crear como CLUSTERED**y seleccione **Sí** en la lista desplegable que aparece a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="daada-166">In the grid, select **Create as Clustered**, and choose **Yes** from the drop-down list to the right of the property.</span></span>  
  
9. <span data-ttu-id="daada-167">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="daada-167">Click **Close**.</span></span>  
  
10. <span data-ttu-id="daada-168">En el menú **Archivo** , haga clic en **Guardar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="daada-168">On the **File** menu, click **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="daada-169">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daada-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-clustered-index"></a><span data-ttu-id="daada-170">Para crear un índice clúster</span><span class="sxs-lookup"><span data-stu-id="daada-170">To create a clustered index</span></span>  
  
1.  <span data-ttu-id="daada-171">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daada-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="daada-172">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="daada-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="daada-173">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="daada-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Create a new table with three columns.  
    CREATE TABLE dbo.TestTable  
        (TestCol1 int NOT NULL,  
         TestCol2 nchar(10) NULL,  
         TestCol3 nvarchar(50) NULL);  
    GO  
    -- Create a clustered index called IX_TestTable_TestCol1  
    -- on the dbo.TestTable table using the TestCol1 column.  
    CREATE CLUSTERED INDEX IX_TestTable_TestCol1   
        ON dbo.TestTable (TestCol1);   
    GO  
    ```  
  
 <span data-ttu-id="daada-174">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="daada-174">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daada-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="daada-175">See Also</span></span>  
 <span data-ttu-id="daada-176">[Crear claves principales](../tables/create-primary-keys.md) </span><span class="sxs-lookup"><span data-stu-id="daada-176">[Create Primary Keys](../tables/create-primary-keys.md) </span></span>  
 [<span data-ttu-id="daada-177">Crear restricciones UNIQUE</span><span class="sxs-lookup"><span data-stu-id="daada-177">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
