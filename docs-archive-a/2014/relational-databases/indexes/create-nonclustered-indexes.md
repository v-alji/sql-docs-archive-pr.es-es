---
title: Creación de índices no agrupados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], nonclustered indexes
- nonclustered indexes [SQL Server], creating
- nonclustered indexes [SQL Server], UNIQUE constraint
- indexes [SQL Server], nonclustered
- nonclustered indexes [SQL Server], PRIMARY KEY constraint
ms.assetid: 9402029a-1227-46c4-93aa-c2122eb1b943
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fae0c06b1f562dc3fc518a319df1787b3384c0cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749834"
---
# <a name="create-nonclustered-indexes"></a><span data-ttu-id="1216f-102">Crear índices no clúster</span><span class="sxs-lookup"><span data-stu-id="1216f-102">Create Nonclustered Indexes</span></span>
  <span data-ttu-id="1216f-103">Puede crear índices no clúster en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1216f-103">You can create nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1216f-104">Un índice no clúster es una estructura de índice independiente de los datos almacenados en una tabla que reordena una o más columnas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="1216f-104">A nonclustered index is an index structure separate from the data stored in a table that reorders one or more selected columns.</span></span> <span data-ttu-id="1216f-105">Con frecuencia, los índices no clúster pueden ayudarle a encontrar datos más rápidamente que cuando se busca en la tabla subyacente; las consultas a veces pueden responderse completamente con los datos del índice no clúster o el índice no clúster puede apuntar el [!INCLUDE[ssDE](../../includes/ssde-md.md)] hacia las filas de la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="1216f-105">Nonclustered indexes can often help you find data more quickly than searching the underlying table; queries can sometimes be answered entirely by the data in the nonclustered index, or the nonclustered index can point the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to the rows in the underlying table.</span></span> <span data-ttu-id="1216f-106">Normalmente, los índices no clúster se crean para mejorar el rendimiento de las consultas usadas con frecuencia no cubiertas por el índice clúster o para buscar filas en una tabla sin un índice clúster (denominado montón).</span><span class="sxs-lookup"><span data-stu-id="1216f-106">Generally, nonclustered indexes are created to improve the performance of frequently used queries not covered by the clustered index or to locate rows in a table without a clustered index (called a heap).</span></span> <span data-ttu-id="1216f-107">Se pueden crear varios índices no clúster en una tabla o una vista indizada.</span><span class="sxs-lookup"><span data-stu-id="1216f-107">You can create multiple nonclustered indexes on a table or indexed view.</span></span>  
  
 <span data-ttu-id="1216f-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1216f-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1216f-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1216f-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1216f-110">Implementaciones típicas</span><span class="sxs-lookup"><span data-stu-id="1216f-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="1216f-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1216f-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1216f-112">**Para crear un índice no clúster, usando:**</span><span class="sxs-lookup"><span data-stu-id="1216f-112">**To create a nonclustered index, using:**</span></span>  
  
     [<span data-ttu-id="1216f-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1216f-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1216f-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1216f-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1216f-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1216f-115">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="1216f-116">Implementaciones típicas</span><span class="sxs-lookup"><span data-stu-id="1216f-116">Typical Implementations</span></span>  
 <span data-ttu-id="1216f-117">Los índices no clúster se implementan de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1216f-117">Nonclustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="1216f-118">**Restricciones UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="1216f-118">**UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="1216f-119">Cuando cree una restricción UNIQUE, se creará un índice no clúster único para exigir una restricción UNIQUE de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1216f-119">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="1216f-120">Puede especificarse un índice clúster único si todavía no existe un índice clúster en la tabla.</span><span class="sxs-lookup"><span data-stu-id="1216f-120">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span> <span data-ttu-id="1216f-121">Para más información, consulte [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="1216f-121">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="1216f-122">**Índice independiente de una restricción**</span><span class="sxs-lookup"><span data-stu-id="1216f-122">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="1216f-123">De forma predeterminada, se crea un índice no clúster si no hay ninguno clúster especificado.</span><span class="sxs-lookup"><span data-stu-id="1216f-123">By default, a nonclustered index is created if clustered is not specified.</span></span> <span data-ttu-id="1216f-124">El número máximo de índices no clúster que se pueden crear por tabla es 999.</span><span class="sxs-lookup"><span data-stu-id="1216f-124">The maximum number of nonclustered indexes that can be created per table is 999.</span></span> <span data-ttu-id="1216f-125">Se incluyen los índices creados por restricciones PRIMARY KEY o UNIQUE, pero no los índices XML.</span><span class="sxs-lookup"><span data-stu-id="1216f-125">This includes any indexes created by PRIMARY KEY or UNIQUE constraints, but does not include XML indexes.</span></span>  
  
-   <span data-ttu-id="1216f-126">**Índice no clúster en una vista indizada**</span><span class="sxs-lookup"><span data-stu-id="1216f-126">**Nonclustered index on an indexed view**</span></span>  
  
     <span data-ttu-id="1216f-127">Una vez creado un índice clúster único en una vista, se pueden crear índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="1216f-127">After a unique clustered index has been created on a view, nonclustered indexes can be created.</span></span> <span data-ttu-id="1216f-128">Para obtener más información, vea [Crear vistas indexadas](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="1216f-128">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1216f-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1216f-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1216f-130">Permisos</span><span class="sxs-lookup"><span data-stu-id="1216f-130">Permissions</span></span>  
 <span data-ttu-id="1216f-131">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="1216f-131">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="1216f-132">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="1216f-132">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1216f-133">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1216f-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-the-table-designer"></a><span data-ttu-id="1216f-134">Para crear un índice no clúster mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="1216f-134">To create a nonclustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="1216f-135">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea crear un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="1216f-135">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="1216f-136">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="1216f-136">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="1216f-137">Haga clic con el botón derecho en la tabla en la que quiere crear un índice no agrupado y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="1216f-137">Right-click the table on which you want to create a nonclustered index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="1216f-138">En el menú **Diseñador de tablas** , haga clic en **índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="1216f-138">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="1216f-139">En el cuadro de diálogo **Índices o claves** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1216f-139">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="1216f-140">Seleccione el nuevo índice en el cuadro de texto **Clave principal o única, o índice seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="1216f-140">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="1216f-141">En la cuadrícula, seleccione **Crear como CLUSTERED**y elija **No** en la lista desplegable que aparece a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1216f-141">In the grid, select **Create as Clustered**, and choose **No** from the drop-down list to the right of the property.</span></span>  
  
8.  <span data-ttu-id="1216f-142">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1216f-142">Click **Close**.</span></span>  
  
9. <span data-ttu-id="1216f-143">En el menú **Archivo** , haga clic en **Guardar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="1216f-143">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-object-explorer"></a><span data-ttu-id="1216f-144">Para crear un índice no clúster mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="1216f-144">To create a nonclustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="1216f-145">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea crear un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="1216f-145">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="1216f-146">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="1216f-146">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="1216f-147">Expanda la tabla en la que desea crear un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="1216f-147">Expand the table on which you want to create a nonclustered index.</span></span>  
  
4.  <span data-ttu-id="1216f-148">Haga clic con el botón derecho en la carpeta **Índices**, seleccione **Nuevo índice** y, luego, **Índice no agrupado...** .</span><span class="sxs-lookup"><span data-stu-id="1216f-148">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="1216f-149">En el cuadro de diálogo **Nuevo índice** , en la página **General** , escriba el nombre del nuevo índice en el cuadro **Nombre de índice** .</span><span class="sxs-lookup"><span data-stu-id="1216f-149">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="1216f-150">Debajo de **Columnas de clave de índice**, haga clic en **Agregar...** .</span><span class="sxs-lookup"><span data-stu-id="1216f-150">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="1216f-151">En el cuadro de diálogo **seleccionar columnas de**_TABLE_NAME_ , active las casillas de las columnas de tabla que se van a agregar al índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="1216f-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the nonclustered index.</span></span>  
  
8.  <span data-ttu-id="1216f-152">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1216f-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1216f-153">En el cuadro de diálogo **Nuevo índice** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1216f-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1216f-154">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1216f-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-nonclustered-index-on-a-table"></a><span data-ttu-id="1216f-155">Para crear un índice no clúster en una tabla</span><span class="sxs-lookup"><span data-stu-id="1216f-155">To create a nonclustered index on a table</span></span>  
  
1.  <span data-ttu-id="1216f-156">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1216f-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1216f-157">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1216f-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1216f-158">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1216f-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named IX_ProductVendor_VendorID and delete it if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
                WHERE name = N'IX_ProductVendor_VendorID')   
        DROP INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor;   
    GO  
    -- Create a nonclustered index called IX_ProductVendor_VendorID   
    -- on the Purchasing.ProductVendor table using the BusinessEntityID column.   
    CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
        ON Purchasing.ProductVendor (BusinessEntityID);   
    GO  
    ```  
  
 <span data-ttu-id="1216f-159">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1216f-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
