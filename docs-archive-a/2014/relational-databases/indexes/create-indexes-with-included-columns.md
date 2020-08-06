---
title: Creación de índices con columnas incluidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index size [SQL Server]
- index keys [SQL Server]
- index columns [SQL Server]
- size [SQL Server], indexes
- key columns [SQL Server]
- included columns
- nonclustered indexes [SQL Server], included columns
- designing indexes [SQL Server], included columns
- nonkey columns
ms.assetid: d198648d-fea5-416d-9f30-f9d4aebbf4ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5a464f9791ea635236069555647229bf1f0d79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749849"
---
# <a name="create-indexes-with-included-columns"></a><span data-ttu-id="e40f0-102">Crear índices con columnas incluidas</span><span class="sxs-lookup"><span data-stu-id="e40f0-102">Create Indexes with Included Columns</span></span>
  <span data-ttu-id="e40f0-103">En este tema se describe cómo agregar columnas incluidas (o sin clave) para ampliar la funcionalidad de índices no clúster en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e40f0-103">This topic describes how to add included (or nonkey) columns to extend the functionality of nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e40f0-104">Al incluir columnas sin clave, puede crear índices no clúster que abarcan más consultas.</span><span class="sxs-lookup"><span data-stu-id="e40f0-104">By including nonkey columns, you can create nonclustered indexes that cover more queries.</span></span> <span data-ttu-id="e40f0-105">Esto se debe a que las columnas sin clave tienen las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="e40f0-105">This is because the nonkey columns have the following benefits:</span></span>  
  
-   <span data-ttu-id="e40f0-106">Pueden ser tipos de datos que no están permitidos como columnas de clave de índice.</span><span class="sxs-lookup"><span data-stu-id="e40f0-106">They can be data types not allowed as index key columns.</span></span>  
  
-   <span data-ttu-id="e40f0-107">El [!INCLUDE[ssDE](../../includes/ssde-md.md)] no las tiene en cuenta cuando calcula el número de columnas de clave de índice o el tamaño de las claves de índice.</span><span class="sxs-lookup"><span data-stu-id="e40f0-107">They are not considered by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] when calculating the number of index key columns or index key size.</span></span>  
  
 <span data-ttu-id="e40f0-108">Un índice con columnas sin clave puede mejorar significativamente el rendimiento de una consulta cuando todas las columnas de la consulta se incluyen como columnas de clave o columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-108">An index with nonkey columns can significantly improve query performance when all columns in the query are included in the index either as key or nonkey columns.</span></span> <span data-ttu-id="e40f0-109">Las mejoras en el rendimiento se consiguen porque el optimizador de consultas puede localizar todos los valores de las columnas del índice, sin tener acceso a los datos de la tabla o del índice clúster, lo que da como resultado menos operaciones de E/S de disco.</span><span class="sxs-lookup"><span data-stu-id="e40f0-109">Performance gains are achieved because the query optimizer can locate all the column values within the index; table or clustered index data is not accessed resulting in fewer disk I/O operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e40f0-110">Cuando un índice contiene todas las columnas a las que hace referencia una consulta, normalmente se dice que *abarca la consulta*.</span><span class="sxs-lookup"><span data-stu-id="e40f0-110">When an index contains all the columns referenced by a query it is typically referred to as *covering the query*.</span></span>  
  
 <span data-ttu-id="e40f0-111">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="e40f0-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e40f0-112">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e40f0-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e40f0-113">Recomendaciones de diseño</span><span class="sxs-lookup"><span data-stu-id="e40f0-113">Design Recommendations</span></span>](#DesignRecs)  
  
     [<span data-ttu-id="e40f0-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e40f0-114">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e40f0-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e40f0-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e40f0-116">**Para crear un índice con columnas sin clave, use:**</span><span class="sxs-lookup"><span data-stu-id="e40f0-116">**To create an index with nonkey columns, using:**</span></span>  
  
     [<span data-ttu-id="e40f0-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e40f0-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e40f0-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e40f0-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e40f0-119">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e40f0-119">Before You Begin</span></span>  
  
###  <a name="design-recommendations"></a><a name="DesignRecs"></a> <span data-ttu-id="e40f0-120">Recomendaciones de diseño</span><span class="sxs-lookup"><span data-stu-id="e40f0-120">Design Recommendations</span></span>  
  
-   <span data-ttu-id="e40f0-121">Rediseñe índices no clúster con un tamaño de las claves de índice grande para que solo las columnas utilizadas para búsquedas sean columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-121">Redesign nonclustered indexes with a large index key size so that only columns used for searching and lookups are key columns.</span></span> <span data-ttu-id="e40f0-122">Convierta todas las demás columnas que abarcan la consulta en columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-122">Make all other columns that cover the query into nonkey columns.</span></span> <span data-ttu-id="e40f0-123">De esta forma, tendrá todas las columnas necesarias para abarcar la consulta pero la clave de índice en sí será pequeña y eficaz.</span><span class="sxs-lookup"><span data-stu-id="e40f0-123">In this way, you will have all columns needed to cover the query, but the index key itself is small and efficient.</span></span>  
  
-   <span data-ttu-id="e40f0-124">Incluya columnas sin clave en un índice no clúster para evitar que se superen las limitaciones actuales de tamaño del índice de un máximo de 16 columnas de clave y un tamaño máximo de clave de índice de 900 bytes.</span><span class="sxs-lookup"><span data-stu-id="e40f0-124">Include nonkey columns in a nonclustered index to avoid exceeding the current index size limitations of a maximum of 16 key columns and a maximum index key size of 900 bytes.</span></span> <span data-ttu-id="e40f0-125">El [!INCLUDE[ssDE](../../includes/ssde-md.md)] no tiene en cuenta las columnas sin clave al calcular el número de columnas de clave de índice o el tamaño de las claves de índice.</span><span class="sxs-lookup"><span data-stu-id="e40f0-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not consider nonkey columns when calculating the number of index key columns or index key size.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e40f0-126">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e40f0-126">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e40f0-127">Las columnas sin clave solo pueden definirse en índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="e40f0-127">Nonkey columns can only be defined on nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="e40f0-128">Todos los tipos de datos excepto `text`, `ntext` e `image` se pueden usar como columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-128">All data types except `text`, `ntext`, and `image` can be used as nonkey columns.</span></span>  
  
-   <span data-ttu-id="e40f0-129">Las columnas calculadas que son deterministas, y precisas o imprecisas, pueden ser columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-129">Computed columns that are deterministic and either precise or imprecise can be nonkey columns.</span></span> <span data-ttu-id="e40f0-130">Para obtener más información, vea [Indexes on Computed Columns](indexes-on-computed-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e40f0-130">For more information, see [Indexes on Computed Columns](indexes-on-computed-columns.md).</span></span>  
  
-   <span data-ttu-id="e40f0-131">Las columnas calculadas derivadas de los tipos de datos `image`, `ntext` y `text` pueden ser columnas sin clave siempre que se permita el tipo de datos de la columna calculada como columna de índice sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-131">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey columns as long as the computed column data type is allowed as a nonkey index column.</span></span>  
  
-   <span data-ttu-id="e40f0-132">Las columnas sin clave no se pueden quitar de una tabla, a menos que antes se quite el índice de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e40f0-132">Nonkey columns cannot be dropped from a table unless that table's index is dropped first.</span></span>  
  
-   <span data-ttu-id="e40f0-133">Las columnas sin clave no se pueden cambiar, excepto para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e40f0-133">Nonkey columns cannot be changed, except to do the following:</span></span>  
  
    -   <span data-ttu-id="e40f0-134">Cambiar la nulabilidad de NOT NULL a NULL.</span><span class="sxs-lookup"><span data-stu-id="e40f0-134">Change the nullability of the column from NOT NULL to NULL.</span></span>  
  
    -   <span data-ttu-id="e40f0-135">Aumentar la longitud de las columnas `varchar`, `nvarchar` o `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="e40f0-135">Increase the length of `varchar`, `nvarchar`, or `varbinary` columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e40f0-136">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e40f0-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e40f0-137">Permisos</span><span class="sxs-lookup"><span data-stu-id="e40f0-137">Permissions</span></span>  
 <span data-ttu-id="e40f0-138">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="e40f0-138">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="e40f0-139">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="e40f0-139">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e40f0-140">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e40f0-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="e40f0-141">Para crear un índice con columnas sin clave</span><span class="sxs-lookup"><span data-stu-id="e40f0-141">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="e40f0-142">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea crear un índice con columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-142">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create an index with nonkey columns.</span></span>  
  
2.  <span data-ttu-id="e40f0-143">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="e40f0-143">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e40f0-144">Haga clic en el signo más para expandir la tabla en la que desea crear un índice con columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-144">Click the plus sign to expand the table on which you want to create an index with nonkey columns.</span></span>  
  
4.  <span data-ttu-id="e40f0-145">Haga clic con el botón derecho en la carpeta **Índices**, seleccione **Nuevo índice** y, luego, **Índice no agrupado...** .</span><span class="sxs-lookup"><span data-stu-id="e40f0-145">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="e40f0-146">En el cuadro de diálogo **Nuevo índice** , en la página **General** , escriba el nombre del nuevo índice en el cuadro **Nombre de índice** .</span><span class="sxs-lookup"><span data-stu-id="e40f0-146">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="e40f0-147">En la pestaña **Columnas de clave de índice**, haga clic en **Agregar...** .</span><span class="sxs-lookup"><span data-stu-id="e40f0-147">Under the **Index key columns** tab, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="e40f0-148">En el cuadro de diálogo **seleccionar columnas de**_TABLE_NAME_ , active las casillas de las columnas de tabla que se van a agregar al índice.</span><span class="sxs-lookup"><span data-stu-id="e40f0-148">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index.</span></span>  
  
8.  <span data-ttu-id="e40f0-149">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e40f0-149">Click **OK**.</span></span>  
  
9. <span data-ttu-id="e40f0-150">En la pestaña **Columnas incluidas**, haga clic en **Agregar...** .</span><span class="sxs-lookup"><span data-stu-id="e40f0-150">Under the **Included columns** tab, click **Add...**.</span></span>  
  
10. <span data-ttu-id="e40f0-151">En el cuadro de diálogo **seleccionar columnas de**_TABLE_NAME_ , active las casillas de las columnas de tabla que se van a agregar al índice como columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="e40f0-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index as nonkey columns.</span></span>  
  
11. <span data-ttu-id="e40f0-152">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e40f0-152">Click **OK**.</span></span>  
  
12. <span data-ttu-id="e40f0-153">En el cuadro de diálogo **Nuevo índice** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e40f0-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e40f0-154">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e40f0-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="e40f0-155">Para crear un índice con columnas sin clave</span><span class="sxs-lookup"><span data-stu-id="e40f0-155">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="e40f0-156">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e40f0-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e40f0-157">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e40f0-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e40f0-158">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e40f0-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates a nonclustered index on the Person.Address table with four included (nonkey) columns.   
    -- index key column is PostalCode and the nonkey columns are  
    -- AddressLine1, AddressLine2, City, and StateProvinceID.  
    CREATE NONCLUSTERED INDEX IX_Address_PostalCode  
    ON Person.Address (PostalCode)  
    INCLUDE (AddressLine1, AddressLine2, City, StateProvinceID);  
    GO  
    ```  
  
 <span data-ttu-id="e40f0-159">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e40f0-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
