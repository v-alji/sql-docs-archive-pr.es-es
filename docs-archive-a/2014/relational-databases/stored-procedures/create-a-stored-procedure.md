---
title: Creación de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- new stored procedures
- stored procedures [SQL Server], creating
- creating stored procedures
ms.assetid: 76e8a6ba-1381-4620-b356-4311e1331ca7
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6781840e6a6c84773f40a6cd0557ccb79b676eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676394"
---
# <a name="create-a-stored-procedure"></a><span data-ttu-id="d23ae-102">Crear un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="d23ae-102">Create a Stored Procedure</span></span>
  <span data-ttu-id="d23ae-103">En este tema se describe cómo se crea un procedimiento almacenado de [!INCLUDE[tsql](../../includes/tsql-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y la instrucción CREATE PROCEDURE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d23ae-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE statement.</span></span>  
  
##  <a name="Top"></a>   
-   <span data-ttu-id="d23ae-104">**Antes de empezar:**  [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="d23ae-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="d23ae-105">**Para crear un procedimiento con:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="d23ae-105">**To create a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d23ae-106">Permisos</span><span class="sxs-lookup"><span data-stu-id="d23ae-106">Permissions</span></span>  
 <span data-ttu-id="d23ae-107">Requiere el permiso CREATE PROCEDURE en la base de datos y el permiso ALTER en el esquema en el que se va a crear el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d23ae-107">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
##  <a name="how-to-create-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="d23ae-108">Crear un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="d23ae-108">How to Create a Stored Procedure</span></span>  
 <span data-ttu-id="d23ae-109">Puede usar cualquiera de los siguientes medios:</span><span class="sxs-lookup"><span data-stu-id="d23ae-109">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="d23ae-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d23ae-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="d23ae-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d23ae-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d23ae-112">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d23ae-112">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d23ae-113">**Para crear un procedimiento en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="d23ae-113">**To create a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="d23ae-114">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="d23ae-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d23ae-115">Expanda **Bases de datos**, la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] y, por último, **Programación**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="d23ae-116">Haga clic con el botón derecho en **Procedimientos almacenados**y, después, haga clic en **Nuevo procedimiento almacenado**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-116">Right-click **Stored Procedures**, and then click **New Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="d23ae-117">En el menú **Consulta** , haga clic en **Especificar valores para parámetros de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="d23ae-118">En el cuadro de diálogo **Especificar valores para parámetros de plantilla** , especifique los siguientes valores para los parámetros mostrados.</span><span class="sxs-lookup"><span data-stu-id="d23ae-118">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="d23ae-119">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d23ae-119">Parameter</span></span>|<span data-ttu-id="d23ae-120">Value</span><span class="sxs-lookup"><span data-stu-id="d23ae-120">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="d23ae-121">Autor</span><span class="sxs-lookup"><span data-stu-id="d23ae-121">Author</span></span>|<span data-ttu-id="d23ae-122">*Su nombre.*</span><span class="sxs-lookup"><span data-stu-id="d23ae-122">*Your name*</span></span>|  
    |<span data-ttu-id="d23ae-123">Create Date</span><span class="sxs-lookup"><span data-stu-id="d23ae-123">Create Date</span></span>|<span data-ttu-id="d23ae-124">*La fecha de hoy.*</span><span class="sxs-lookup"><span data-stu-id="d23ae-124">*Today's date*</span></span>|  
    |<span data-ttu-id="d23ae-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d23ae-125">Description</span></span>|<span data-ttu-id="d23ae-126">Devuelve datos de empleado.</span><span class="sxs-lookup"><span data-stu-id="d23ae-126">Returns employee data.</span></span>|  
    |<span data-ttu-id="d23ae-127">Procedure_name</span><span class="sxs-lookup"><span data-stu-id="d23ae-127">Procedure_name</span></span>|<span data-ttu-id="d23ae-128">HumanResources.uspGetEmployeesTest</span><span class="sxs-lookup"><span data-stu-id="d23ae-128">HumanResources.uspGetEmployeesTest</span></span>|  
    |@Param1|@LastName|  
    |@Datatype_For_Param1|<span data-ttu-id="d23ae-129">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="d23ae-129">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="d23ae-130">Default_Value_For_Param1</span><span class="sxs-lookup"><span data-stu-id="d23ae-130">Default_Value_For_Param1</span></span>|<span data-ttu-id="d23ae-131">NULL</span><span class="sxs-lookup"><span data-stu-id="d23ae-131">NULL</span></span>|  
    |@Param2|@FirstName|  
    |@Datatype_For_Param2|<span data-ttu-id="d23ae-132">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="d23ae-132">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="d23ae-133">Default_Value_For_Param2</span><span class="sxs-lookup"><span data-stu-id="d23ae-133">Default_Value_For_Param2</span></span>|<span data-ttu-id="d23ae-134">NULL</span><span class="sxs-lookup"><span data-stu-id="d23ae-134">NULL</span></span>|  
  
6.  <span data-ttu-id="d23ae-135">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-135">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="d23ae-136">En el **Editor de consultas**, reemplace la instrucción SELECT por la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="d23ae-136">In the **Query Editor**, replace the SELECT statement with the following statement:</span></span>  
  
    ```sql  
    SELECT FirstName, LastName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory  
    WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    ```  
  
8.  <span data-ttu-id="d23ae-137">Para probar la sintaxis, en el menú **Consulta** , haga clic en **Analizar**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-137">To test the syntax, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="d23ae-138">Si se devuelve un mensaje de error, compare las instrucciones con la información anterior y corrija lo que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d23ae-138">If an error message is returned, compare the statements with the information above and correct as needed.</span></span>  
  
9. <span data-ttu-id="d23ae-139">Para crear el procedimiento, en el menú **Consulta** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-139">To create the procedure, from  the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="d23ae-140">El procedimiento se crea como un objeto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d23ae-140">The procedure is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="d23ae-141">Para ver el procedimiento que aparece en el Explorador de objetos, haga clic con el botón derecho en **Procedimientos almacenados** y seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-141">To see the procedure listed in Object Explorer, right-click **Stored Procedures** and select **Refresh**.</span></span>  
  
11. <span data-ttu-id="d23ae-142">Para ejecutar el procedimiento, en el Explorador de objetos, haga clic con el botón derecho en el nombre del procedimiento almacenado **HumanResources.uspGetEmployeesTest** y seleccione **Ejecutar procedimiento almacenado**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-142">To run the procedure, in Object Explorer, right-click the stored procedure name **HumanResources.uspGetEmployeesTest** and select **Execute Stored Procedure**.</span></span>  
  
12. <span data-ttu-id="d23ae-143">En la ventana **Ejecutar procedimiento**, escriba Margheim como valor del parámetro @LastName y Diane como valor del parámetro @FirstName.</span><span class="sxs-lookup"><span data-stu-id="d23ae-143">In the **Execute Procedure** window, enter Margheim as the value for the parameter @LastName and enter the value Diane as the value for the parameter @FirstName.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d23ae-144">Valide todos los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d23ae-144">Validate all user input.</span></span> <span data-ttu-id="d23ae-145">No concatene ninguna entrada de usuario antes de validarla.</span><span class="sxs-lookup"><span data-stu-id="d23ae-145">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="d23ae-146">No ejecute nunca un comando creado a partir de una entrada de usuario no validada.</span><span class="sxs-lookup"><span data-stu-id="d23ae-146">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d23ae-147">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d23ae-147">Using Transact-SQL</span></span>  
 <span data-ttu-id="d23ae-148">**Para crear un procedimiento en el Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="d23ae-148">**To create a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="d23ae-149">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d23ae-149">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d23ae-150">En el menú **Archivo** , haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-150">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d23ae-151">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d23ae-152">En este ejemplo se crea el mismo procedimiento almacenado que antes con otro nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="d23ae-152">This example creates the same stored procedure as above using a different procedure name.</span></span>  
  
    ```sql
    USE AdventureWorks2012;  
    GO  
    CREATE PROCEDURE HumanResources.uspGetEmployeesTest2   
        @LastName nvarchar(50),   
        @FirstName nvarchar(50)   
    AS
  
        SET NOCOUNT ON;  
        SELECT FirstName, LastName, Department  
        FROM HumanResources.vEmployeeDepartmentHistory  
        WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    GO
    ```  
  
4.  <span data-ttu-id="d23ae-153">Para ejecutar el procedimiento, copie y pegue el ejemplo siguiente en una nueva ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d23ae-153">To run the procedure, copy and paste the following example into a new query window and click **Execute**.</span></span> <span data-ttu-id="d23ae-154">Observe que se muestran diferentes métodos para especificar los valores de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d23ae-154">Notice that different methods of specifying the parameter values are shown.</span></span>  
  
    ```sql
    EXECUTE HumanResources.uspGetEmployeesTest2 N'Ackerman', N'Pilar';  
    -- Or  
    EXEC HumanResources.uspGetEmployeesTest2 @LastName = N'Ackerman', @FirstName = N'Pilar';  
    GO  
    -- Or  
    EXECUTE HumanResources.uspGetEmployeesTest2 @FirstName = N'Pilar', @LastName = N'Ackerman';  
    GO
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d23ae-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d23ae-155">See Also</span></span>  
 [<span data-ttu-id="d23ae-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d23ae-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  