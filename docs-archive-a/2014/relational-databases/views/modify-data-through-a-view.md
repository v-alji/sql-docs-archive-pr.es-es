---
title: Modificación de datos mediante una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- data modifications [SQL Server], views
- views [SQL Server], modifying data through
- modifying data [SQL Server], views
ms.assetid: 410e2812-4ebe-48b2-b95f-c7784f1c4336
author: stevestein
ms.author: sstein
ms.openlocfilehash: df1eb4a33d1d10e63363e52760dad805b20c0a8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662723"
---
# <a name="modify-data-through-a-view"></a><span data-ttu-id="f19e0-102">Modificar datos mediante una vista</span><span class="sxs-lookup"><span data-stu-id="f19e0-102">Modify Data Through a View</span></span>
  <span data-ttu-id="f19e0-103">Puede modificar los datos de una tabla base subyacente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f19e0-103">You can modify the data of an underlying base table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f19e0-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f19e0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f19e0-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f19e0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f19e0-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f19e0-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f19e0-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f19e0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f19e0-108">**Para modificar los datos de la tabla mediante una vista, use:**</span><span class="sxs-lookup"><span data-stu-id="f19e0-108">**To modify table data through a view, using:**</span></span>  
  
     [<span data-ttu-id="f19e0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f19e0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f19e0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f19e0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f19e0-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f19e0-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f19e0-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f19e0-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f19e0-113">Vea la sección ''Vistas actualizables'' de [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f19e0-113">See the section 'Updatable Views' in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f19e0-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f19e0-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f19e0-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="f19e0-115">Permissions</span></span>  
 <span data-ttu-id="f19e0-116">Requiere los permisos UPDATE, INSERT o DELETE en la tabla de destino, en función de la acción que se realizará.</span><span class="sxs-lookup"><span data-stu-id="f19e0-116">Requires UPDATE, INSERT, or DELETE permissions on the target table, depending on the action being performed.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f19e0-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f19e0-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-table-data-through-a-view"></a><span data-ttu-id="f19e0-118">Para modificar los datos de la tabla mediante una vista</span><span class="sxs-lookup"><span data-stu-id="f19e0-118">To modify table data through a view</span></span>  
  
1.  <span data-ttu-id="f19e0-119">En el **Explorador de objetos**, expanda la base de datos que contiene la vista y, a continuación, expanda **Vistas**.</span><span class="sxs-lookup"><span data-stu-id="f19e0-119">In **Object Explorer**, expand the database that contains the view and then expand **Views**.</span></span>  
  
2.  <span data-ttu-id="f19e0-120">Haga clic con el botón derecho en la vista y seleccione **Editar las primeras 200 filas**.</span><span class="sxs-lookup"><span data-stu-id="f19e0-120">Right-click the view and select **Edit Top 200 Rows**.</span></span>  
  
3.  <span data-ttu-id="f19e0-121">Quizás necesite modificar la instrucción SELECT en el panel **SQL** para devolver las filas que se modificarán.</span><span class="sxs-lookup"><span data-stu-id="f19e0-121">You may need to modify the SELECT statement in the **SQL** pane to return the rows to be modified.</span></span>  
  
4.  <span data-ttu-id="f19e0-122">En el panel de **Resultados** , busque la fila que se va a cambiar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="f19e0-122">In the **Results** pane, locate the row to be changed or deleted.</span></span> <span data-ttu-id="f19e0-123">Para eliminar la fila, haga clic con el botón derecho en ella y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f19e0-123">To delete the row, right-click the row and select **Delete**.</span></span> <span data-ttu-id="f19e0-124">Para cambiar los datos de una o más columnas, modifique los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="f19e0-124">To change data in one or more columns, modify the data in the column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f19e0-125">No se puede eliminar una fila si la vista hace referencia a más de una tabla base.</span><span class="sxs-lookup"><span data-stu-id="f19e0-125">You cannot delete a row if the view references more than one base table.</span></span> <span data-ttu-id="f19e0-126">Solo pueden actualizarse las columnas que pertenecen a una única tabla base.</span><span class="sxs-lookup"><span data-stu-id="f19e0-126">You can only update columns that belong to a single base table.</span></span>  
  
5.  <span data-ttu-id="f19e0-127">Para insertar una fila, desplácese hasta el final de las filas e inserte los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="f19e0-127">To insert a row, scroll down to the end of the rows and insert the new values.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f19e0-128">No se puede insertar una fila si la vista hace referencia a más de una tabla base.</span><span class="sxs-lookup"><span data-stu-id="f19e0-128">You cannot insert a row if the view references more than one base table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f19e0-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f19e0-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-table-data-through-a-view"></a><span data-ttu-id="f19e0-130">Para actualizar los datos de la tabla mediante una vista</span><span class="sxs-lookup"><span data-stu-id="f19e0-130">To update table data through a view</span></span>  
  
1.  <span data-ttu-id="f19e0-131">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f19e0-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f19e0-132">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f19e0-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f19e0-133">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f19e0-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f19e0-134">Este ejemplo cambia el valor de las columnas `StartDate` y `EndDate` de un empleado concreto mediante referencias a columnas de la vista `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="f19e0-134">This example changes the value in the `StartDate` and `EndDate` columns for a specific employee by referencing columns in the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="f19e0-135">Esta vista devuelve valores de dos tablas.</span><span class="sxs-lookup"><span data-stu-id="f19e0-135">This view returns values from two tables.</span></span> <span data-ttu-id="f19e0-136">Esta instrucción se realiza correctamente porque las columnas que se modificaron solo provienen de una de las tablas base.</span><span class="sxs-lookup"><span data-stu-id="f19e0-136">This statement succeeds because the columns being modified are from only one of the base tables.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    UPDATE HumanResources.vEmployeeDepartmentHistory  
    SET StartDate = '20110203', EndDate = GETDATE()   
    WHERE LastName = N'Smith' AND FirstName = 'Samantha';   
    GO  
    ```  
  
 <span data-ttu-id="f19e0-137">Para obtener más información, vea [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f19e0-137">For more information, see [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span></span>  
  
#### <a name="to-insert-table-data-through-a-view"></a><span data-ttu-id="f19e0-138">Para insertar datos de tabla mediante una vista</span><span class="sxs-lookup"><span data-stu-id="f19e0-138">To insert table data through a view</span></span>  
  
1.  <span data-ttu-id="f19e0-139">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f19e0-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f19e0-140">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f19e0-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f19e0-141">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f19e0-141">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f19e0-142">El ejemplo especifica las columnas relevantes de la vista `HumanResouces.Department` para insertar una nueva fila en la tabla base `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="f19e0-142">The example inserts a new row into the base table `HumanResouces.Department` by specifying the relevant columns from the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="f19e0-143">La instrucción se realiza correctamente porque solo se especifican las columnas de una tabla base y las demás columnas de la tabla base tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="f19e0-143">The statement succeeds because only columns from a single base table are specified and the other columns in the base table have default values.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    INSERT INTO HumanResources.vEmployeeDepartmentHistory (Department, GroupName)   
    VALUES ('MyDepartment', 'MyGroup');   
    GO  
    ```  
  
 <span data-ttu-id="f19e0-144">Para obtener más información, vea [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f19e0-144">For more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span></span>  
  
  
