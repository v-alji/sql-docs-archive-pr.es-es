---
title: Creación de nombre de los índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- unique indexes
- designing indexes [SQL Server], unique
- clustered indexes, unique
- indexes [SQL Server], unique
- nonclustered indexes [SQL Server], unique
- unique indexes, design guidelines
ms.assetid: 56b5982e-cb94-46c0-8fbb-772fc275354a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c96c4e17a8ce0863452db171302d650f6114919
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749841"
---
# <a name="create-unique-indexes"></a><span data-ttu-id="7f917-102">Crear índices únicos</span><span class="sxs-lookup"><span data-stu-id="7f917-102">Create Unique Indexes</span></span>
  <span data-ttu-id="7f917-103">En este tema se describe cómo crear un índice único en una tabla de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f917-103">This topic describes how to create a unique index on a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7f917-104">Un índice único garantiza que la clave de índice no contiene valores duplicados y, por tanto, cada fila de la tabla es en cierta forma única.</span><span class="sxs-lookup"><span data-stu-id="7f917-104">A unique index guarantees that the index key contains no duplicate values and therefore every row in the table is in some way unique.</span></span> <span data-ttu-id="7f917-105">No existen diferencias significativas entre crear una restricción UNIQUE y crear un índice único que es independiente de una restricción.</span><span class="sxs-lookup"><span data-stu-id="7f917-105">There are no significant differences between creating a UNIQUE constraint and creating a unique index that is independent of a constraint.</span></span> <span data-ttu-id="7f917-106">La validación de datos se produce de igual modo y el optimizador de consultas no distingue entre un índice único creado mediante una restricción o creado manualmente.</span><span class="sxs-lookup"><span data-stu-id="7f917-106">Data validation occurs in the same manner, and the query optimizer does not differentiate between a unique index created by a constraint or manually created.</span></span> <span data-ttu-id="7f917-107">Sin embargo, la creación de una restricción UNIQUE en la columna aclara el objetivo del índice.</span><span class="sxs-lookup"><span data-stu-id="7f917-107">However, creating a UNIQUE constraint on the column makes the objective of the index clear.</span></span> <span data-ttu-id="7f917-108">Para obtener más información acerca de las restricciones UNIQUE, vea [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="7f917-108">For more information on UNIQUE constraints, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="7f917-109">Cuando cree o modifique un índice único, puede establecer una opción para omitir claves duplicadas.</span><span class="sxs-lookup"><span data-stu-id="7f917-109">When you create a unique index, you can set an option to ignore duplicate keys.</span></span> <span data-ttu-id="7f917-110">Si esta opción está establecida en **Sí** e intenta crear claves duplicadas al agregar datos que afectan a varias filas (con la instrucción INSERT), no se agregará la fila que contenga un duplicado.</span><span class="sxs-lookup"><span data-stu-id="7f917-110">If this option is set to **Yes** and you attempt to create duplicate keys by adding data that affects multiple rows (with the INSERT statement), the row containing a duplicate is not added.</span></span> <span data-ttu-id="7f917-111">Si el valor es **No**, se producirá un error en toda la operación de inserción y se revertirán todos los datos.</span><span class="sxs-lookup"><span data-stu-id="7f917-111">If it is set to **No**, the entire insert operation fails and all the data is rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f917-112">No puede crear un índice único en una sola columna si ésta contiene valores NULL en más de una fila.</span><span class="sxs-lookup"><span data-stu-id="7f917-112">You cannot create a unique index on a single column if that column contains NULL in more than one row.</span></span> <span data-ttu-id="7f917-113">De forma similar, no puede crear un índice único en varias columnas si la combinación de columnas contiene valores NULL en más de una fila.</span><span class="sxs-lookup"><span data-stu-id="7f917-113">Similarly, you cannot create a unique index on multiple columns if the combination of columns contains NULL in more than one row.</span></span> <span data-ttu-id="7f917-114">Estos valores se tratan como duplicados a efectos de indización.</span><span class="sxs-lookup"><span data-stu-id="7f917-114">These are treated as duplicate values for indexing purposes.</span></span>  
  
 <span data-ttu-id="7f917-115">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="7f917-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7f917-116">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7f917-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7f917-117">Ventajas de un índice único</span><span class="sxs-lookup"><span data-stu-id="7f917-117">Benefits of a Unique Index</span></span>](#Benefits)  
  
     [<span data-ttu-id="7f917-118">Implementaciones típicas</span><span class="sxs-lookup"><span data-stu-id="7f917-118">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="7f917-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7f917-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7f917-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7f917-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7f917-121">**Para crear un índice único en una tabla, use:**</span><span class="sxs-lookup"><span data-stu-id="7f917-121">**To create a unique index on a table, using:**</span></span>  
  
     [<span data-ttu-id="7f917-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f917-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7f917-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f917-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7f917-124">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7f917-124">Before You Begin</span></span>  
  
###  <a name="benefits-of-a-unique-index"></a><a name="Benefits"></a> <span data-ttu-id="7f917-125">Ventajas de un índice único</span><span class="sxs-lookup"><span data-stu-id="7f917-125">Benefits of a Unique Index</span></span>  
  
-   <span data-ttu-id="7f917-126">Los índices únicos para varias columnas garantizan que cada combinación de valores de la clave de índice sea única.</span><span class="sxs-lookup"><span data-stu-id="7f917-126">Multicolumn unique indexes guarantee that each combination of values in the index key is unique.</span></span> <span data-ttu-id="7f917-127">Por ejemplo, si se crea un índice único en una combinación de columnas **LastName**, **FirstName**y **MiddleName** , dos filas de la tabla no podrán tener la misma combinación de valores para estas columnas.</span><span class="sxs-lookup"><span data-stu-id="7f917-127">For example, if a unique index is created on a combination of **LastName**, **FirstName**, and **MiddleName** columns, no two rows in the table could have the same combination of values for these columns.</span></span>  
  
-   <span data-ttu-id="7f917-128">Siempre que los datos de cada columna sean únicos, puede crear un índice clúster único y varios índices no clúster únicos en la misma tabla.</span><span class="sxs-lookup"><span data-stu-id="7f917-128">Provided that the data in each column is unique, you can create both a unique clustered index and multiple unique nonclustered indexes on the same table.</span></span>  
  
-   <span data-ttu-id="7f917-129">Los índices únicos aseguran la integridad de los datos de las columnas definidas.</span><span class="sxs-lookup"><span data-stu-id="7f917-129">Unique indexes ensure the data integrity of the defined columns.</span></span>  
  
-   <span data-ttu-id="7f917-130">Los índices únicos proporcionan información adicional útil al optimizador de consultas, que puede generar planes más eficaces de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f917-130">Unique indexes provide additional information helpful to the query optimizer that can produce more efficient execution plans.</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="7f917-131">Implementaciones típicas</span><span class="sxs-lookup"><span data-stu-id="7f917-131">Typical Implementations</span></span>  
 <span data-ttu-id="7f917-132">Los índices únicos se implementan de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f917-132">Unique indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="7f917-133">**Restricción PRIMARY KEY o UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="7f917-133">**PRIMARY KEY or UNIQUE constraint**</span></span>  
  
     <span data-ttu-id="7f917-134">Cuando se crea una restricción PRIMARY KEY, se crea automáticamente un índice clúster único en las columnas si aún no existe un índice clúster en la tabla o no se ha especificado un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="7f917-134">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="7f917-135">La columna de clave principal no puede permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="7f917-135">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="7f917-136">Cuando cree una restricción UNIQUE, se creará un índice no clúster único para exigir una restricción UNIQUE de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7f917-136">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="7f917-137">Puede especificarse un índice clúster único si todavía no existe un índice clúster en la tabla.</span><span class="sxs-lookup"><span data-stu-id="7f917-137">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="7f917-138">Para obtener más información, consulte [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) y [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="7f917-138">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) and [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span></span>  
  
-   <span data-ttu-id="7f917-139">**Índice independiente de una restricción**</span><span class="sxs-lookup"><span data-stu-id="7f917-139">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="7f917-140">Es posible definir varios índices no clúster únicos en cualquier tabla.</span><span class="sxs-lookup"><span data-stu-id="7f917-140">Multiple unique nonclustered indexes can be defined on a table.</span></span>  
  
     <span data-ttu-id="7f917-141">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7f917-141">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="7f917-142">**Vistas indizadas**</span><span class="sxs-lookup"><span data-stu-id="7f917-142">**Indexed view**</span></span>  
  
     <span data-ttu-id="7f917-143">Para crear una vista indizada, se define un índice clúster único en una o varias columnas de la vista.</span><span class="sxs-lookup"><span data-stu-id="7f917-143">To create an indexed view, a unique clustered index is defined on one or more view columns.</span></span> <span data-ttu-id="7f917-144">La vista se ejecuta y el conjunto de resultados se almacena en el nivel hoja del índice, del mismo modo en que los datos de tabla se almacenan en un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="7f917-144">The view is executed and the result set is stored in the leaf level of the index in the same way table data is stored in a clustered index.</span></span> <span data-ttu-id="7f917-145">Para obtener más información, vea [Crear vistas indexadas](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="7f917-145">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7f917-146">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7f917-146">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7f917-147">Un índice único, una restricción UNIQUE o una restricción PRIMARY KEY no se pueden crear si existen valores de clave duplicados en los datos.</span><span class="sxs-lookup"><span data-stu-id="7f917-147">A unique index, UNIQUE constraint, or PRIMARY KEY constraint cannot be created if duplicate key values exist in the data.</span></span>  
  
-   <span data-ttu-id="7f917-148">Un índice no clúster único puede incluir columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="7f917-148">A unique nonclustered index can contain included nonkey columns.</span></span> <span data-ttu-id="7f917-149">Para más información, consulte [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="7f917-149">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7f917-150">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7f917-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7f917-151">Permisos</span><span class="sxs-lookup"><span data-stu-id="7f917-151">Permissions</span></span>  
 <span data-ttu-id="7f917-152">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="7f917-152">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="7f917-153">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="7f917-153">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7f917-154">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f917-154">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-index-by-using-the-table-designer"></a><span data-ttu-id="7f917-155">Para crear un índice único mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="7f917-155">To create a unique index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="7f917-156">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea crear un índice único.</span><span class="sxs-lookup"><span data-stu-id="7f917-156">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="7f917-157">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="7f917-157">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7f917-158">Haga clic con el botón derecho en la tabla en la que quiere crear un índice único y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="7f917-158">Right-click the table on which you want to create a unique index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="7f917-159">En el menú **Diseñador de tablas** , seleccione **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="7f917-159">On the **Table Designer** menu, select **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="7f917-160">En el cuadro de diálogo **Índices o claves** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f917-160">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="7f917-161">Seleccione el nuevo índice en el cuadro de texto **Clave principal o única, o índice seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="7f917-161">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="7f917-162">En la cuadrícula principal, en **(General)** , seleccione **Tipo** y luego **Índice** en la lista.</span><span class="sxs-lookup"><span data-stu-id="7f917-162">In the main grid, under **(General)**, select **Type** and then choose **Index** from the list.</span></span>  
  
8.  <span data-ttu-id="7f917-163">Seleccione **Columnas** y luego haga clic en el botón de puntos suspensivos **(...)** .</span><span class="sxs-lookup"><span data-stu-id="7f917-163">Select **Columns**, and then click the ellipsis **(...)**.</span></span>  
  
9. <span data-ttu-id="7f917-164">En el cuadro de diálogo **Columnas de índice** , debajo de **Nombre de columna**, seleccione las columnas que desea indizar.</span><span class="sxs-lookup"><span data-stu-id="7f917-164">In the **Index Columns** dialog box, under **Column Name**, select the columns you want to index.</span></span> <span data-ttu-id="7f917-165">Puede seleccionar hasta 16 columnas.</span><span class="sxs-lookup"><span data-stu-id="7f917-165">You can select up to 16 columns.</span></span> <span data-ttu-id="7f917-166">Para obtener un rendimiento óptimo, no seleccione más de una o dos columnas por cada índice.</span><span class="sxs-lookup"><span data-stu-id="7f917-166">For optimal performance, select only one or two columns per index.</span></span> <span data-ttu-id="7f917-167">Para cada columna que seleccione, puede indicar si el índice organiza los valores de esta columna en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="7f917-167">For each column you select, indicate whether the index arranges values of this column in ascending or descending order.</span></span>  
  
10. <span data-ttu-id="7f917-168">Cuando haya seleccionado todas las columnas del índice, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f917-168">When all columns for the index are selected, click **OK**.</span></span>  
  
11. <span data-ttu-id="7f917-169">En la cuadrícula, en **(General)** , seleccione **Es Unique** y luego **Sí** en la lista.</span><span class="sxs-lookup"><span data-stu-id="7f917-169">In the grid, under **(General)**, select **Is Unique** and then choose **Yes** from the list.</span></span>  
  
12. <span data-ttu-id="7f917-170">Opcional: en la cuadrícula principal, debajo de **Diseñador de tablas**, seleccione **Omitir claves duplicadas** y elija **Sí** en la lista.</span><span class="sxs-lookup"><span data-stu-id="7f917-170">Optional: In the main grid, under **Table Designer**, select **Ignore Duplicate Keys** and then choose **Yes** from the list.</span></span> <span data-ttu-id="7f917-171">Haga esto si desea omitir los intentos de agregar datos que crearían una clave duplicada en el índice único.</span><span class="sxs-lookup"><span data-stu-id="7f917-171">Do this if you want to ignore attempts to add data that would create a duplicate key in the unique index.</span></span>  
  
13. <span data-ttu-id="7f917-172">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7f917-172">Click **Close**.</span></span>  
  
14. <span data-ttu-id="7f917-173">En el menú **Archivo** , haga clic en **Guardar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="7f917-173">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="create-a-unique-index-by-using-object-explorer"></a><span data-ttu-id="7f917-174">Crear un índice único mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="7f917-174">Create a unique index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="7f917-175">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea crear un índice único.</span><span class="sxs-lookup"><span data-stu-id="7f917-175">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="7f917-176">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="7f917-176">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7f917-177">Expanda la tabla en la que desea crear un índice único.</span><span class="sxs-lookup"><span data-stu-id="7f917-177">Expand the table on which you want to create a unique index.</span></span>  
  
4.  <span data-ttu-id="7f917-178">Haga clic con el botón derecho en la carpeta **Índices**, seleccione **Nuevo índice** y, luego, **Índice no agrupado...** .</span><span class="sxs-lookup"><span data-stu-id="7f917-178">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="7f917-179">En el cuadro de diálogo **Nuevo índice** , en la página **General** , escriba el nombre del nuevo índice en el cuadro **Nombre de índice** .</span><span class="sxs-lookup"><span data-stu-id="7f917-179">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="7f917-180">Active la casilla **Único** .</span><span class="sxs-lookup"><span data-stu-id="7f917-180">Select the **Unique** check box.</span></span>  
  
7.  <span data-ttu-id="7f917-181">Debajo de **Columnas de clave de índice**, haga clic en **Agregar...** .</span><span class="sxs-lookup"><span data-stu-id="7f917-181">Under **Index key columns**, click **Add...**.</span></span>  
  
8.  <span data-ttu-id="7f917-182">En el cuadro de diálogo **seleccionar columnas de**_TABLE_NAME_ , active las casillas de las columnas de tabla que se van a agregar al índice único.</span><span class="sxs-lookup"><span data-stu-id="7f917-182">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
9. <span data-ttu-id="7f917-183">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f917-183">Click **OK**.</span></span>  
  
10. <span data-ttu-id="7f917-184">En el cuadro de diálogo **Nuevo índice** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f917-184">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7f917-185">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f917-185">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-index-on-a-table"></a><span data-ttu-id="7f917-186">Para crear un índice único en una tabla</span><span class="sxs-lookup"><span data-stu-id="7f917-186">To create a unique index on a table</span></span>  
  
1.  <span data-ttu-id="7f917-187">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f917-187">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7f917-188">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7f917-188">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7f917-189">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7f917-189">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named AK_UnitMeasure_Name and delete it if found  
    IF EXISTS (SELECT name from sys.indexes  
               WHERE name = N'AK_UnitMeasure_Name')   
       DROP INDEX AK_UnitMeasure_Name ON Production.UnitMeasure;   
    GO  
    -- Create a unique index called AK_UnitMeasure_Name  
    -- on the Production.UnitMeasure table using the Name column.  
    CREATE UNIQUE INDEX AK_UnitMeasure_Name   
       ON Production.UnitMeasure (Name);   
    GO  
    ```  
  
 <span data-ttu-id="7f917-190">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7f917-190">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
