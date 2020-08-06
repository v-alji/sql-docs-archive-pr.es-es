---
title: Copiar columnas de una tabla a otra (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying columns
- columns [SQL Server], copying
ms.assetid: 5f5e70dc-69f9-44b8-bc48-b5d51ac20d77
author: stevestein
ms.author: sstein
ms.openlocfilehash: 37b98bf0910cbbb4c2a1d7fe01f11d52703ec88c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678140"
---
# <a name="copy-columns-from-one-table-to-another-database-engine"></a><span data-ttu-id="843cd-102">Copiar columnas de una tabla a otra (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="843cd-102">Copy Columns from One Table to Another (Database Engine)</span></span>
  <span data-ttu-id="843cd-103">En este tema se describe cómo copiar columnas de una tabla a otra, copiar solo la definición de la columna o copiar la definición y los datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843cd-103">This topic describes how to copy columns from one table to another, copying either just the column definition, or the definition and data in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="843cd-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="843cd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="843cd-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="843cd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="843cd-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="843cd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="843cd-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="843cd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="843cd-108">**Para copiar columnas mediante:**</span><span class="sxs-lookup"><span data-stu-id="843cd-108">**To coy columns, using:**</span></span>  
  
     [<span data-ttu-id="843cd-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="843cd-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="843cd-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="843cd-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="843cd-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="843cd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="843cd-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="843cd-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="843cd-113">Cuando se copia una columna con el tipo de datos de alias desde una base de datos a otra, el tipo de datos de alias podría no estar disponible en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="843cd-113">When you copy a column that has an alias data type from one database to another, the alias data type may not be available in the destination database.</span></span> <span data-ttu-id="843cd-114">En ese caso, se asignará a la columna el tipo de datos de base más parecido que esté disponible en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="843cd-114">In such a case, the column will be assigned the nearest matching base data type available in that database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="843cd-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="843cd-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="843cd-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="843cd-116">Permissions</span></span>  
 <span data-ttu-id="843cd-117">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="843cd-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="843cd-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="843cd-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="843cd-119">Para copiar definiciones de columna de una tabla a otra</span><span class="sxs-lookup"><span data-stu-id="843cd-119">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="843cd-120">Abra la tabla con columnas que quiere copiar y la tabla en la que la quiere copiar haciendo clic con el botón derecho en las tablas y, después, en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="843cd-120">Open the table with columns you want to copy and the one you want to copy into by right-clicking the tables, and then clicking **Design**.</span></span>  
  
2.  <span data-ttu-id="843cd-121">Haga clic en la pestaña de la tabla cuyas columnas desea copiar y seleccione esas columnas.</span><span class="sxs-lookup"><span data-stu-id="843cd-121">Click the tab for the table with the columns you want to copy and select those columns.</span></span>  
  
3.  <span data-ttu-id="843cd-122">En el menú **Edición** , haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="843cd-122">From the **Edit** menu, click **Copy**.</span></span>  
  
4.  <span data-ttu-id="843cd-123">Haga clic en la pestaña de la tabla en la que desea copiar las columnas.</span><span class="sxs-lookup"><span data-stu-id="843cd-123">Click the tab for the table into which you want to copy the columns.</span></span>  
  
5.  <span data-ttu-id="843cd-124">Seleccione la columna que desea que siga a las columnas insertadas y en el menú **Edición** , haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="843cd-124">Select the column you want to follow the inserted columns and, from the **Edit** menu, click **Paste**.</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="843cd-125">Para copiar columnas de datos de una tabla a otra</span><span class="sxs-lookup"><span data-stu-id="843cd-125">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="843cd-126">Siga las instrucciones para copiar las definiciones de columna mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="843cd-126">Follow the directions for copying column definitions above.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="843cd-127">Antes de empezar a copiar los datos de una tabla a otra, asegúrese de que los tipos de datos de las columnas de destino son compatibles con los tipos de datos de las columnas de origen.</span><span class="sxs-lookup"><span data-stu-id="843cd-127">Before you begin to copy data from one table to another, make sure that the data types in the destination columns are compatible with the data types of the source columns</span></span>  
  
2.  <span data-ttu-id="843cd-128">En el Explorador de objetos, haga clic con el botón secundario en **Vista** nodo y a continuación haga clic en **Nueva vista**.</span><span class="sxs-lookup"><span data-stu-id="843cd-128">In Object Explorer, right-click the **Views** node, and then click **New View**.</span></span>  
  
3.  <span data-ttu-id="843cd-129">En el menú **Diseñador de consultas** , seleccione **Cambiar tipo**y, a continuación, haga clic en **Insertar resultados**.</span><span class="sxs-lookup"><span data-stu-id="843cd-129">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
4.  <span data-ttu-id="843cd-130">En el cuadro de diálogo **Elegir tabla de destino para Insertar resultados** , seleccione la tabla a la que desea copiar los datos y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="843cd-130">In the **Choose Target Table for Insert Results** dialog box, select the table into which you want to copy the data, and then click **OK**.</span></span>  
  
     <span data-ttu-id="843cd-131">Si va a copiar datos dentro de una tabla, puede agregar la tabla de origen como tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="843cd-131">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="843cd-132">El**Diseñador de consultas** no puede determinar con antelación las tablas y las vistas que se pueden actualizar.</span><span class="sxs-lookup"><span data-stu-id="843cd-132">**Query Designer** cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="843cd-133">Por tanto, la lista de tablas del cuadro de diálogo **Elegir tabla de destino para Insertar resultados** mostrará todas las tablas y las vistas disponibles en la conexión de datos que está consultando, incluidas aquellas en las que no puede copiar filas.</span><span class="sxs-lookup"><span data-stu-id="843cd-133">Therefore, the list of tables in the **Choose Target Table for Insert Results** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
5.  <span data-ttu-id="843cd-134">Haga clic con el botón secundario en el cuerpo del panel Diagrama y, en el menú contextual, haga clic en **Agregar tabla a diagrama**.</span><span class="sxs-lookup"><span data-stu-id="843cd-134">Right-click in the body of the diagram pane and, from the shortcut menu, click **Add Table to Diagram**.</span></span>  
  
6.  <span data-ttu-id="843cd-135">En el cuadro de diálogo **Agregar tabla** , seleccione cada una de las tablas cuyos datos desea copiar, haga clic en **Agregar**y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="843cd-135">In the **Add Table** dialog box, select each table from which you want to copy data, click **Add**, and then click **Close**.</span></span>  
  
     <span data-ttu-id="843cd-136">Las tablas aparecen en el panel Diagrama en forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="843cd-136">The tables, in an abbreviated form, appear in the diagram pane.</span></span>  
  
7.  <span data-ttu-id="843cd-137">En las tablas abreviadas, active las casillas de todas las columnas de las que desea copiar datos.</span><span class="sxs-lookup"><span data-stu-id="843cd-137">In the abbreviated tables, check the boxes for any columns from which you want to copy data.</span></span>  
  
8.  <span data-ttu-id="843cd-138">En el panel Criterios, en la columna **Anexar** , elija para cada columna de destino una columna de la que desea copiar datos.</span><span class="sxs-lookup"><span data-stu-id="843cd-138">In the criteria pane, in the **Append** column, for each target column choose a column from which you want to copy data.</span></span>  
  
9. <span data-ttu-id="843cd-139">Indique las filas que desea copiar especificando condiciones de búsqueda en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="843cd-139">Specify the rows to copy by entering search conditions in the criteria pane.</span></span> <span data-ttu-id="843cd-140">Para obtener más información, vea [Especificar condiciones de búsqueda &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="843cd-140">For details, see [Specify Search Conditions &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="843cd-141">Si no especifica ninguna condición de búsqueda, se copiarán todas las filas de la tabla de origen en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="843cd-141">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
10. <span data-ttu-id="843cd-142">Si desea copiar información de Resumen, especifique opciones **de agrupar por** .</span><span class="sxs-lookup"><span data-stu-id="843cd-142">If you want to copy summary information, specify **Group By** options.</span></span> <span data-ttu-id="843cd-143">Para obtener más información, vea [Resumir o agregar los valores de todas las filas de una tabla &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="843cd-143">For details, see [Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span></span>  
  
11. <span data-ttu-id="843cd-144">Haga clic en el botón **Ejecutar SQL** para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="843cd-144">Click the **Execute SQL button** to run the query.</span></span>  
  
     <span data-ttu-id="843cd-145">Al ejecutar una consulta de inserción de resultados, los resultados no se muestran en el [Panel de resultados](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="843cd-145">When you execute an insert results query, no results are reported in the [Results Pane](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="843cd-146">En su lugar, aparece un mensaje que indica cuántas filas se han copiado.</span><span class="sxs-lookup"><span data-stu-id="843cd-146">Instead, a message appears indicating how many rows were copied.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="843cd-147">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="843cd-147">Using Transact-SQL</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="843cd-148">Para copiar definiciones de columna de una tabla a otra</span><span class="sxs-lookup"><span data-stu-id="843cd-148">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="843cd-149">No puede copiar columnas individuales desde una tabla a otra tabla existente mediante instrucciones Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="843cd-149">You cannot copy individual columns from one table to another existing table by using Transact-SQL statements.</span></span> <span data-ttu-id="843cd-150">Sin embargo, puede crear una nueva tabla en el grupo de archivos predeterminado e insertar en ella las filas resultantes de la consulta mediante SELECT...INTO.</span><span class="sxs-lookup"><span data-stu-id="843cd-150">However, you can create a new table in the default filegroup and inserts the resulting rows from the query into it by using SELECT INTO.</span></span> <span data-ttu-id="843cd-151">Para obtener más información, vea [Cláusula INTO &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="843cd-151">For more information, see [INTO Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="843cd-152">Para copiar columnas de datos de una tabla a otra</span><span class="sxs-lookup"><span data-stu-id="843cd-152">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="843cd-153">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="843cd-153">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="843cd-154">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="843cd-154">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="843cd-155">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="843cd-155">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.EmployeeSales  
    ( BusinessEntityID   varchar(11) NOT NULL,  
      SalesYTD money NOT NULL  
    );  
    GO  
    INSERT INTO dbo.EmployeeSales  
        SELECT BusinessEntityID, SalesYTD   
        FROM Sales.SalesPerson;  
    GO  
    ```  
  
  
