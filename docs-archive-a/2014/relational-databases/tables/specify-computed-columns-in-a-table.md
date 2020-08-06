---
title: Especificar columnas calculadas en una tabla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, define
ms.assetid: 731a4576-09c1-47f0-a8f6-edd0b55679f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22e4df8d67b61e50383ffd8e33f982990ff3f2ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675750"
---
# <a name="specify-computed-columns-in-a-table"></a><span data-ttu-id="2eb0d-102">Especificar columnas calculadas en una tabla</span><span class="sxs-lookup"><span data-stu-id="2eb0d-102">Specify Computed Columns in a Table</span></span>
  <span data-ttu-id="2eb0d-103">Una columna calculada es una columna virtual que no está almacenada físicamente en la tabla, a menos que la columna esté marcada con PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-103">A computed column is a virtual column that is not physically stored in the table, unless the column is marked PERSISTED.</span></span> <span data-ttu-id="2eb0d-104">Las expresiones de columnas calculadas pueden utilizar datos de otras columnas al calcular un valor para la columna a la que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-104">A computed column expression can use data from other columns to calculate a value for the column to which it belongs.</span></span> <span data-ttu-id="2eb0d-105">Puede especificar una expresión para una columna calculada en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb0d-105">You can specify an expression for a computed column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2eb0d-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2eb0d-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2eb0d-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2eb0d-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2eb0d-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2eb0d-108">Limitations and Restrictions</span></span>](#Limitations)  
  
     [<span data-ttu-id="2eb0d-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2eb0d-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2eb0d-110">**Para especificar una columna calculada con:**</span><span class="sxs-lookup"><span data-stu-id="2eb0d-110">**To specify a computed column, using:**</span></span>  
  
     [<span data-ttu-id="2eb0d-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2eb0d-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2eb0d-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2eb0d-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2eb0d-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2eb0d-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="2eb0d-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2eb0d-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2eb0d-115">Una columna calculada no puede utilizarse como definición de restricción DEFAULT o FOREIGN KEY ni como NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-115">A computed column cannot be used as a DEFAULT or FOREIGN KEY constraint definition or with a NOT NULL constraint definition.</span></span> <span data-ttu-id="2eb0d-116">No obstante, si el valor de columna calculada lo define una expresión determinista y se permite el tipo de datos del resultado en columnas de índice, se puede utilizar una columna calculada como columna de clave en un índice o como parte de cualquier restricción PRIMARY KEY o UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-116">However, if the computed column value is defined by a deterministic expression and the data type of the result is allowed in index columns, a computed column can be used as a key column in an index or as part of any PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="2eb0d-117">Por ejemplo, si la tabla tiene las columnas de tipo entero a y b, la columna calculada a + b se puede indizar, pero la columna calculada a + DATEPART(dd, GETDATE()) no, porque el valor podría variar en llamadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-117">For example, if the table has integer columns a and b, the computed column a + b may be indexed, but computed column a + DATEPART(dd, GETDATE()) cannot be indexed, because the value might change in subsequent invocations.</span></span>  
  
-   <span data-ttu-id="2eb0d-118">Una columna calculada no puede ser el destino de una instrucción INSERT o UPDATE.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-118">A computed column cannot be the target of an INSERT or UPDATE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2eb0d-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2eb0d-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2eb0d-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="2eb0d-120">Permissions</span></span>  
 <span data-ttu-id="2eb0d-121">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2eb0d-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2eb0d-122">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-add-a-new-computed-column"></a><a name="NewColumn"></a> <span data-ttu-id="2eb0d-123">Para agregar una nueva columna calculada</span><span class="sxs-lookup"><span data-stu-id="2eb0d-123">To add a new computed column</span></span>  
  
1.  <span data-ttu-id="2eb0d-124">En el **Explorador de objetos**, expanda la tabla para la que desea agregar la nueva columna calculada.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-124">In **Object Explorer**, expand the table for which you want to add the new computed column.</span></span> <span data-ttu-id="2eb0d-125">Haga clic con el botón derecho en **Columnas** y seleccione **Nueva columna**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-125">Right-click **Columns** and select **New Column**.</span></span>  
  
2.  <span data-ttu-id="2eb0d-126">Escriba el nombre de columna y acepte el tipo de datos predeterminado (`nchar`(10)).</span><span class="sxs-lookup"><span data-stu-id="2eb0d-126">Enter the column name and accept the default data type (`nchar`(10)).</span></span> <span data-ttu-id="2eb0d-127">El [!INCLUDE[ssDE](../../includes/ssde-md.md)] determina el tipo de datos de la columna calculada aplicando las reglas de prioridad de tipo de datos a las expresiones especificadas en la fórmula.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-127">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines the data type of the computed column by applying the rules of data type precedence to the expressions specified in the formula.</span></span> <span data-ttu-id="2eb0d-128">Por ejemplo, si la fórmula hace referencia a una columna de tipo `money` y una columna de tipo `int`, la columna calculada será de tipo `money` porque ese tipo de datos tiene mayor prioridad.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-128">For example, if the formula references a column of type `money` and a column of type `int`, the computed column will be of type `money` because that data type has the higher precedence.</span></span> <span data-ttu-id="2eb0d-129">Para obtener más información, vea [Prioridad de tipo de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2eb0d-129">For more information, see [Data Type Precedence &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span></span>  
  
3.  <span data-ttu-id="2eb0d-130">En la pestaña **Propiedades de columna** , expanda la propiedad **Especificación de columna calculada** .</span><span class="sxs-lookup"><span data-stu-id="2eb0d-130">In the **Column Properties** tab, expand the **Computed Column Specification** property.</span></span>  
  
4.  <span data-ttu-id="2eb0d-131">En la propiedad secundaria **(Fórmula)** , escriba la expresión de esta columna en la celda de la cuadrícula situada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-131">In the **(Formula)** child property, enter the expression for this column in the grid cell to the right.</span></span> <span data-ttu-id="2eb0d-132">Por ejemplo, en una columna `SalesTotal` , la fórmula que escribe puede ser `SubTotal+TaxAmt+Freight`, que suma el valor de estas columnas para cada fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-132">For example, in a `SalesTotal` column, the formula you enter might be `SubTotal+TaxAmt+Freight`, which adds the value in these columns for each row in the table.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2eb0d-133">Cuando una fórmula combina dos expresiones de tipos de datos distintos, las reglas de prioridad de tipo de datos especifican que el tipo de datos con la prioridad menor se convierta al tipo de datos con la prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-133">When a formula combines two expressions of different data types, the rules for data type precedence specify that the data type with the lower precedence is converted to the data type with the higher precedence.</span></span> <span data-ttu-id="2eb0d-134">Si la conversión no es una conversión implícita admitida, se devuelve el error "`Error validating the formula for column column_name.`".</span><span class="sxs-lookup"><span data-stu-id="2eb0d-134">If the conversion is not a supported implicit conversion, the error "`Error validating the formula for column column_name.`" is returned.</span></span> <span data-ttu-id="2eb0d-135">Use la función CAST o CONVERT para resolver el conflicto de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-135">Use the CAST or CONVERT function to resolve the data type conflict.</span></span> <span data-ttu-id="2eb0d-136">Por ejemplo, si una columna de tipo `nvarchar` se combina con una columna de tipo `int`, el tipo entero debe convertirse a `nvarchar` como se muestra en esta fórmula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-136">For example, if a column of type `nvarchar` is combined with a column of type `int`, the integer type must be converted to `nvarchar` as shown in this formula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span></span> <span data-ttu-id="2eb0d-137">Para obtener más información, vea [CAST y CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2eb0d-137">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
5.  <span data-ttu-id="2eb0d-138">Indique si los datos se van a conservar; para ello, elija **Sí** o **No** en el menú desplegable de la propiedad secundaria **Es persistente** .</span><span class="sxs-lookup"><span data-stu-id="2eb0d-138">Indicate whether the data is persisted by choosing **Yes** or **No** from the drop-down for the **Is Persisted** child property.</span></span>  
  
6.  <span data-ttu-id="2eb0d-139">En el menú **Archivo**, haga clic en \***Guardar**_nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-139">On the **File** menu, click **Save**_table name_.</span></span>  
  
#### <a name="to-add-a-computed-column-definition-to-an-existing-column"></a><span data-ttu-id="2eb0d-140">Para agregar una definición de columna calculada a una columna existente</span><span class="sxs-lookup"><span data-stu-id="2eb0d-140">To add a computed column definition to an existing column</span></span>  
  
1.  <span data-ttu-id="2eb0d-141">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla que contenga la columna que quiera cambiar y expanda la carpeta **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="2eb0d-141">In **Object Explorer**, right-click the table with the column for which you want to change and expand the **Columns** folder.</span></span>  
  
2.  <span data-ttu-id="2eb0d-142">Haga clic con el botón derecho en la columna para la que quiera especificar una fórmula de columna calculada y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-142">Right-click the column for which you want to specify a computed column formula and click **Delete**.</span></span> <span data-ttu-id="2eb0d-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="2eb0d-144">Agregue una nueva columna y especifique la fórmula de columna calculada siguiendo el procedimiento anterior para agregar una nueva columna calculada.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-144">Add a new column and specify the computed column formula by following the previous procedure to add a new computed column.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2eb0d-145">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2eb0d-145">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-computed-column-when-creating-a-table"></a><span data-ttu-id="2eb0d-146">Para agregar una columna calculada al crear una tabla</span><span class="sxs-lookup"><span data-stu-id="2eb0d-146">To add a computed column when creating a table</span></span>  
  
1.  <span data-ttu-id="2eb0d-147">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb0d-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2eb0d-148">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2eb0d-149">Copie y pegue el ejemplo siguiente en la ventana de consulta y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-149">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="2eb0d-150">En el ejemplo se crea una tabla con una columna calculada que multiplica el valor de la columna `QtyAvailable` tantas veces como indique el valor de la columna `UnitPrice` .</span><span class="sxs-lookup"><span data-stu-id="2eb0d-150">The example creates a table with a computed column that multiplies the value in the `QtyAvailable` column times the value in the `UnitPrice` column.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products   
    (  
        ProductID int IDENTITY (1,1) NOT NULL  
      , QtyAvailable smallint  
      , UnitPrice money  
      , InventoryValue AS QtyAvailable * UnitPrice  
    );  
  
    -- Insert values into the table.  
    INSERT INTO dbo.Products (QtyAvailable, UnitPrice)  
    VALUES (25, 2.00), (10, 1.5);  
  
    -- Display the rows in the table.  
    SELECT ProductID, QtyAvailable, UnitPrice, InventoryValue  
    FROM dbo.Products;  
  
    ```  
  
#### <a name="to-add-a-new-computed-column-to-an-existing-table"></a><span data-ttu-id="2eb0d-151">Para agregar una nueva columna calculada a una tabla existente</span><span class="sxs-lookup"><span data-stu-id="2eb0d-151">To add a new computed column to an existing table</span></span>  
  
1.  <span data-ttu-id="2eb0d-152">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb0d-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2eb0d-153">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2eb0d-154">Copie y pegue el ejemplo siguiente en la ventana de consulta y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-154">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="2eb0d-155">En el ejemplo siguiente se agrega una columna nueva a la tabla creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-155">The following example adds a new column to the table created in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.35);  
  
    ```  
  
#### <a name="to-change-an-existing-column-to-a-computed-column"></a><span data-ttu-id="2eb0d-156">Para cambiar una columna existente a una columna calculada</span><span class="sxs-lookup"><span data-stu-id="2eb0d-156">To change an existing column to a computed column</span></span>  
  
1.  <span data-ttu-id="2eb0d-157">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb0d-157">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2eb0d-158">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2eb0d-159">Para cambiar una columna existente a una columna calculada, debe quitar y volver a crear la columna calculada.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-159">To change an existing column to a computed column you must drop and re-create the computed column.</span></span> <span data-ttu-id="2eb0d-160">Copie y pegue el ejemplo siguiente en la ventana de consulta y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-160">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="2eb0d-161">En el ejemplo siguiente se modifica la columna agregada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="2eb0d-161">The following example modifies the column added in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products DROP COLUMN RetailValue;  
    GO  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.5);  
  
    ```  
  
     <span data-ttu-id="2eb0d-162">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2eb0d-162">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
