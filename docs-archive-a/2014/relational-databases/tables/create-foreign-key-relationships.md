---
title: Creación de relaciones de claves externas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], creating
ms.assetid: 867a54b8-5be4-46e6-9702-49ae6dabf67c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ee0de3311eb6abffcdb71ab725d0650fe96b04c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678132"
---
# <a name="create-foreign-key-relationships"></a><span data-ttu-id="9b08d-102">Crear relaciones de clave externa</span><span class="sxs-lookup"><span data-stu-id="9b08d-102">Create Foreign Key Relationships</span></span>
  <span data-ttu-id="9b08d-103">En este tema se describe cómo crear relaciones de clave externa en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b08d-103">This topic describes how to create foreign key relationships in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9b08d-104">Cuando se asocian filas de una tabla con filas de otra tabla, se crea una relación entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="9b08d-104">You create a relationship between two tables when you want to associate rows of one table with rows of another.</span></span>  
  
 <span data-ttu-id="9b08d-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9b08d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9b08d-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9b08d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9b08d-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9b08d-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9b08d-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9b08d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9b08d-109">**Para crear relaciones de clave externa mediante:**</span><span class="sxs-lookup"><span data-stu-id="9b08d-109">**To Create Foreign Key Relationships by using:**</span></span>  
  
     [<span data-ttu-id="9b08d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b08d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9b08d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b08d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9b08d-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9b08d-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9b08d-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9b08d-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9b08d-114">No es necesario que una restricción de clave externa esté vinculada únicamente a una restricción de clave principal de otra tabla; también puede definirse para que haga referencia a las columnas de una restricción UNIQUE de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="9b08d-114">A foreign key constraint does not have to be linked only to a primary key constraint in another table; it can also be defined to reference the columns of a UNIQUE constraint in another table.</span></span>  
  
-   <span data-ttu-id="9b08d-115">Si se especifica un valor distinto de NULL en la columna de una restricción FOREIGN KEY, el valor debe existir en la columna a que se hace referencia; de lo contrario, se devolverá un error de infracción de clave externa.</span><span class="sxs-lookup"><span data-stu-id="9b08d-115">When a value other than NULL is entered into the column of a FOREIGN KEY constraint, the value must exist in the referenced column; otherwise, a foreign key violation error message is returned.</span></span> <span data-ttu-id="9b08d-116">Para asegurarse de que todos los valores de la restricción de clave externa compuesta se comprueben, especifique NOT NULL en todas las columnas que participan.</span><span class="sxs-lookup"><span data-stu-id="9b08d-116">To make sure that all values of a composite foreign key constraint are verified, specify NOT NULL on all the participating columns.</span></span>  
  
-   <span data-ttu-id="9b08d-117">Las restricciones FOREIGN KEY solo pueden hacer referencia a las tablas de la misma base de datos en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="9b08d-117">FOREIGN KEY constraints can reference only tables within the same database on the same server.</span></span> <span data-ttu-id="9b08d-118">La integridad referencial entre bases de datos debe implementarse a través de desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="9b08d-118">Cross-database referential integrity must be implemented through triggers.</span></span> <span data-ttu-id="9b08d-119">Para obtener más información, vea [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b08d-119">For more information, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
-   <span data-ttu-id="9b08d-120">Las restricciones FOREIGN KEY pueden hacer referencia a otras columnas de la misma tabla.</span><span class="sxs-lookup"><span data-stu-id="9b08d-120">FOREIGN KEY constraints can reference another column in the same table.</span></span> <span data-ttu-id="9b08d-121">Esto recibe el nombre de autorreferencia.</span><span class="sxs-lookup"><span data-stu-id="9b08d-121">This is referred to as a self-reference.</span></span>  
  
-   <span data-ttu-id="9b08d-122">Una restricción FOREIGN KEY especificada en el nivel de columna solo puede incluir una columna de referencia.</span><span class="sxs-lookup"><span data-stu-id="9b08d-122">A FOREIGN KEY constraint specified at the column level can list only one reference column.</span></span> <span data-ttu-id="9b08d-123">Esta columna debe tener el mismo tipo de datos que la columna en la que se define la restricción.</span><span class="sxs-lookup"><span data-stu-id="9b08d-123">This column must have the same data type as the column on which the constraint is defined.</span></span>  
  
-   <span data-ttu-id="9b08d-124">Una restricción FOREIGN KEY especificada en el nivel de tabla debe tener el mismo número de columnas de referencia que la lista de columnas de la restricción.</span><span class="sxs-lookup"><span data-stu-id="9b08d-124">A FOREIGN KEY constraint specified at the table level must have the same number of reference columns as the number of columns in the constraint column list.</span></span> <span data-ttu-id="9b08d-125">El tipo de datos de cada columna de referencia debe ser también el mismo que el de la columna correspondiente de la lista de columnas.</span><span class="sxs-lookup"><span data-stu-id="9b08d-125">The data type of each reference column must also be the same as the corresponding column in the column list.</span></span>  
  
-   <span data-ttu-id="9b08d-126">El [!INCLUDE[ssDE](../../includes/ssde-md.md)] no tiene un límite predefinido para el número de restricciones FOREIGN KEY que una tabla que hace referencia a otras tablas puede contener, o para el número de restricciones FOREIGN KEY pertenecientes a otras tablas que hacen referencia a una tabla específica.</span><span class="sxs-lookup"><span data-stu-id="9b08d-126">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not have a predefined limit on either the number of FOREIGN KEY constraints a table can contain that reference other tables, or the number of FOREIGN KEY constraints that are owned by other tables that reference a specific table.</span></span> <span data-ttu-id="9b08d-127">No obstante, el número real de restricciones FOREIGN KEY que se puede utilizar está limitado por la configuración del hardware y por el diseño de la base de datos y de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b08d-127">Nevertheless, the actual number of FOREIGN KEY constraints that can be used is limited by the hardware configuration and by the design of the database and application.</span></span> <span data-ttu-id="9b08d-128">Se recomienda que la tabla no contenga más de 253 restricciones FOREIGN KEY y que no más de 253 restricciones FOREIGN KEY hagan referencia a ella.</span><span class="sxs-lookup"><span data-stu-id="9b08d-128">We recommend that a table contain no more than 253 FOREIGN KEY constraints, and that it be referenced by no more than 253 FOREIGN KEY constraints.</span></span>  
  
-   <span data-ttu-id="9b08d-129">Las restricciones FOREIGN KEY no se exigen en tablas temporales.</span><span class="sxs-lookup"><span data-stu-id="9b08d-129">FOREIGN KEY constraints are not enforced on temporary tables.</span></span>  
  
-   <span data-ttu-id="9b08d-130">Si la clave externa se define en una columna de tipo definido por el usuario CLR, la implementación del tipo debe admitir el orden binario.</span><span class="sxs-lookup"><span data-stu-id="9b08d-130">If a foreign key is defined on a CLR user-defined type column, the implementation of the type must support binary ordering.</span></span> <span data-ttu-id="9b08d-131">Para obtener más información, vea [Tipos definidos por el usuario de CLR](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="9b08d-131">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
-   <span data-ttu-id="9b08d-132">Una columna de tipo `varchar(max)` puede participar en una restricción FOREIGN KEY solo si la clave principal a la que hace referencia se define también como tipo `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="9b08d-132">A column of type `varchar(max)` can participate in a FOREIGN KEY constraint only if the primary key it references is also defined as type `varchar(max)`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b08d-133">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9b08d-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9b08d-134">Permisos</span><span class="sxs-lookup"><span data-stu-id="9b08d-134">Permissions</span></span>  
 <span data-ttu-id="9b08d-135">La creación de una tabla nueva con una clave externa requiere el permiso CREATE TABLE en la base de datos y el permiso ALTER en el esquema en el que se crea la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b08d-135">Creating a new table with a foreign key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="9b08d-136">La creación de una clave externa en una tabla existente requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b08d-136">Creating a foreign key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9b08d-137">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b08d-137">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-foreign-key-relationship-in-table-designer"></a><span data-ttu-id="9b08d-138">Para crear una relación de clave externa en el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="9b08d-138">To create a foreign key relationship in Table Designer</span></span>  
  
1.  <span data-ttu-id="9b08d-139">En el Explorador de objetos, haga clic con el botón derecho en la tabla que va a estar en el lado de la clave externa de la relación y, después, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-139">In Object Explorer, right-click the table that will be on the foreign-key side of the relationship and click **Design**.</span></span>  
  
     <span data-ttu-id="9b08d-140">La tabla se abre en el **Diseñador de tablas**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-140">The table opens in **Table Designer**.</span></span>  
  
2.  <span data-ttu-id="9b08d-141">En el menú **Diseñador de tablas** , haga clic en **Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-141">From the **Table Designer** menu, click **Relationships**.</span></span>  
  
3.  <span data-ttu-id="9b08d-142">En el cuadro de diálogo **Relaciones de clave externa** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-142">In the **Foreign-key Relationships** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="9b08d-143">La relación aparece en la lista **Relación seleccionada** con un nombre proporcionado por el sistema con el formato FK_\<*tablename*>_\<*tablename*>, donde *tablename* es el nombre de la tabla de clave externa.</span><span class="sxs-lookup"><span data-stu-id="9b08d-143">The relationship appears in the **Selected Relationship** list with a system-provided name in the format FK_\<*tablename*>_\<*tablename*>, where *tablename* is the name of the foreign key table.</span></span>  
  
4.  <span data-ttu-id="9b08d-144">Haga clic en la relación en la lista **Relación seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="9b08d-144">Click the relationship in the **Selected Relationship** list.</span></span>  
  
5.  <span data-ttu-id="9b08d-145">Haga clic en **Especificaciones de tablas y columnas** en la cuadrícula situada a la derecha y, después, haga clic en los puntos suspensivos ( **...** ) situados a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9b08d-145">Click **Tables and Columns Specification** in the grid to the right and click the ellipses (**...**) to the right of the property.</span></span>  
  
6.  <span data-ttu-id="9b08d-146">En el cuadro de diálogo **Tablas y columnas** , en la lista desplegable **Clave principal** , elija la tabla que estará en el lado de la clave principal de la relación.</span><span class="sxs-lookup"><span data-stu-id="9b08d-146">In the **Tables and Columns** dialog box, in the **Primary Key** drop-down list, choose the table that will be on the primary-key side of the relationship.</span></span>  
  
7.  <span data-ttu-id="9b08d-147">En la cuadrícula situada debajo, elija las columnas que contribuyen a la clave principal de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b08d-147">In the grid beneath, choose the columns contributing to the table's primary key.</span></span> <span data-ttu-id="9b08d-148">En la celda de la cuadrícula adyacente situada a la izquierda de cada columna, elija la columna de clave externa correspondiente de la tabla de clave externa.</span><span class="sxs-lookup"><span data-stu-id="9b08d-148">In the adjacent grid cell to the left of each column, choose the corresponding foreign-key column of the foreign-key table.</span></span>  
  
     <span data-ttu-id="9b08d-149">El**Diseñador de tablas** sugerirá un nombre para la relación.</span><span class="sxs-lookup"><span data-stu-id="9b08d-149">**Table Designer** suggests a name for the relationship.</span></span> <span data-ttu-id="9b08d-150">Para cambiar este nombre, edite el contenido del cuadro de texto **Nombre de la relación** .</span><span class="sxs-lookup"><span data-stu-id="9b08d-150">To change this name, edit the contents of the **Relationship Name** text box.</span></span>  
  
8.  <span data-ttu-id="9b08d-151">Elija **Aceptar** para crear la relación.</span><span class="sxs-lookup"><span data-stu-id="9b08d-151">Choose **OK** to create the relationship.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9b08d-152">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b08d-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-foreign-key-in-a-new-table"></a><span data-ttu-id="9b08d-153">Para crear una clave externa en una tabla nueva</span><span class="sxs-lookup"><span data-stu-id="9b08d-153">To create a foreign key in a new table</span></span>  
  
1.  <span data-ttu-id="9b08d-154">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b08d-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b08d-155">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b08d-156">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-156">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9b08d-157">El ejemplo crea una tabla y definir una restricción de clave externa en la columna `TempID` que hace referencia a la columna `SalesReasonID` de la tabla `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="9b08d-157">The example creates a table and defines a foreign key constraint on the column `TempID` that references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span> <span data-ttu-id="9b08d-158">Las cláusulas ON DELETE CASCADE y ON UPDATE CASCADE se usan para garantizar que los cambios realizados en la tabla `Sales.SalesReason` se propaguen automáticamente a la tabla `Sales.TempSalesReason` .</span><span class="sxs-lookup"><span data-stu-id="9b08d-158">The ON DELETE CASCADE and ON UPDATE CASCADE clauses are used to ensure that changes made to `Sales.SalesReason` table are automatically propagated to the `Sales.TempSalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Sales.TempSalesReason (TempID int NOT NULL, Name nvarchar(50),   
    CONSTRAINT PK_TempSales PRIMARY KEY NONCLUSTERED (TempID),   
    CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    );GO  
  
    ```  
  
#### <a name="to-create-a-foreign-key-in-an-existing-table"></a><span data-ttu-id="9b08d-159">Para crear una clave externa de una tabla existente</span><span class="sxs-lookup"><span data-stu-id="9b08d-159">To create a foreign key in an existing table</span></span>  
  
1.  <span data-ttu-id="9b08d-160">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b08d-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b08d-161">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b08d-162">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9b08d-162">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9b08d-163">El ejemplo crea una clave externa en la columna `TempID` que hace referencia a la columna `SalesReasonID` de la tabla `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="9b08d-163">The example creates a foreign key on the column `TempID` and references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Sales.TempSalesReason   
    ADD CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    ;  
    GO  
  
    ```  
  
     <span data-ttu-id="9b08d-164">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) y [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b08d-164">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
  
