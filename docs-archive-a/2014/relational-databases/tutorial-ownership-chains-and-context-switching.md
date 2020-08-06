---
title: 'Tutorial: Cadenas de propiedad y cambios de contexto | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- context switching [SQL Server], tutorials
- ownership chains [SQL Server]
ms.assetid: db5d4cc3-5fc5-4cf5-afc1-8d4edc1d512b
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e9072a68dd3179e5900fda06d4fea58b484a37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670903"
---
# <a name="tutorial-ownership-chains-and-context-switching"></a><span data-ttu-id="6c08d-102">Tutorial: Ownership Chains and Context Switching</span><span class="sxs-lookup"><span data-stu-id="6c08d-102">Tutorial: Ownership Chains and Context Switching</span></span>
  <span data-ttu-id="6c08d-103">En este tutorial se usa un escenario para ilustrar los conceptos de seguridad de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relacionados con las cadenas de propiedad y el cambio de contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c08d-103">This tutorial uses a scenario to illustrate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security concepts involving ownership chains and user context switching.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c08d-104">Para ejecutar el código de este tutorial, debe estar configurada la seguridad de modo mixto y la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] debe estar instalada.</span><span class="sxs-lookup"><span data-stu-id="6c08d-104">To run the code in this tutorial you must have both Mixed Mode security configured and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database installed.</span></span> <span data-ttu-id="6c08d-105">Para obtener más información sobre la seguridad de modo mixto, consulte [Elegir un modo de autenticación](security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6c08d-105">For more information about Mixed Mode security, see [Choose an Authentication Mode](security/choose-an-authentication-mode.md).</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="6c08d-106">Escenario</span><span class="sxs-lookup"><span data-stu-id="6c08d-106">Scenario</span></span>  
 <span data-ttu-id="6c08d-107">En este escenario, dos usuarios necesitan cuentas para obtener acceso a los datos de los pedidos de compra almacenados en la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c08d-107">In this scenario, two users need accounts to access purchase order data stored in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="6c08d-108">Los requisitos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c08d-108">The requirements are as follows:</span></span>  
  
-   <span data-ttu-id="6c08d-109">La primera cuenta (TestManagerUser) debe poder ver todos los detalles de cada pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="6c08d-109">The first account (TestManagerUser) must be able to see all details in every purchase order.</span></span>  
  
-   <span data-ttu-id="6c08d-110">La segunda cuenta (TestEmployeeUser) debe poder ver el número de los pedidos de compra, la fecha de los pedidos, la fecha de envío, los números de identificación de los productos y los elementos pedidos y recibidos en cada pedido de compra, ordenados por número de pedido de compra, correspondientes a los elementos para los que se han recibido envíos parciales.</span><span class="sxs-lookup"><span data-stu-id="6c08d-110">The second account (TestEmployeeUser) must be able to see the purchase order number, order date, shipping date, product ID numbers, and the ordered and received items per purchase order, by purchase order number, for items where partial shipments have been received.</span></span>  
  
-   <span data-ttu-id="6c08d-111">El resto de cuentas deben conservar sus permisos.</span><span class="sxs-lookup"><span data-stu-id="6c08d-111">All other accounts must retain their current permissions.</span></span>  
  
 <span data-ttu-id="6c08d-112">Para cumplir los requisitos de este escenario, el ejemplo se ha dividido en cuatro partes que describen los conceptos de cadenas de propiedad y cambio de contexto:</span><span class="sxs-lookup"><span data-stu-id="6c08d-112">To fulfill the requirements of this scenario, the example is broken into four parts that demonstrate the concepts of ownership chains and context switching:</span></span>  
  
1.  <span data-ttu-id="6c08d-113">Configuración del entorno.</span><span class="sxs-lookup"><span data-stu-id="6c08d-113">Configuring the environment.</span></span>  
  
2.  <span data-ttu-id="6c08d-114">Creación de un procedimiento almacenado para obtener acceso a datos por pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="6c08d-114">Creating a stored procedure to access data by purchase order.</span></span>  
  
3.  <span data-ttu-id="6c08d-115">Acceso a los datos mediante un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="6c08d-115">Accessing the data through the stored procedure.</span></span>  
  
4.  <span data-ttu-id="6c08d-116">Restablecimiento del entorno.</span><span class="sxs-lookup"><span data-stu-id="6c08d-116">Resetting the environment.</span></span>  
  
 <span data-ttu-id="6c08d-117">Cada bloque de código incluido en este ejemplo se describe en línea.</span><span class="sxs-lookup"><span data-stu-id="6c08d-117">Each code block in this example is explained in line.</span></span> <span data-ttu-id="6c08d-118">Para copiar el ejemplo completo, vea [Ejemplo completo](#CompleteExample) al final de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="6c08d-118">To copy the complete example, see [Complete Example](#CompleteExample) at the end of this tutorial.</span></span>  
  
## <a name="1-configure-the-environment"></a><span data-ttu-id="6c08d-119">1. Configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="6c08d-119">1. Configure the Environment</span></span>  
 <span data-ttu-id="6c08d-120">Use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y el código siguiente para abrir la `AdventureWorks2012` base de datos y use la `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] instrucción para comprobar que el usuario DBO se muestra como contexto.</span><span class="sxs-lookup"><span data-stu-id="6c08d-120">Use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and the following code to open the `AdventureWorks2012` database, and use the `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] statement to check that the dbo user is displayed as the context.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
```  
  
 <span data-ttu-id="6c08d-121">Para obtener más información sobre la instrucción CURRENT_USER, consulte [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c08d-121">For more information about the CURRENT_USER statement, see [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span></span>  
  
 <span data-ttu-id="6c08d-122">Use este código como usuario dbo para crear dos usuarios en el servidor y en la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c08d-122">Use this code as the dbo user to create two users on the server and in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
GO  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
```  
  
 <span data-ttu-id="6c08d-123">Para obtener más información sobre la instrucción CREATE USER, consulte [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c08d-123">For more information about the CREATE USER statement, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="6c08d-124">Para obtener más información sobre la instrucción CREATE LOGIN, consulte [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c08d-124">For more information about the CREATE LOGIN statement, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
 <span data-ttu-id="6c08d-125">Use el código siguiente para cambiar la propiedad del esquema `Purchasing` a la cuenta `TestManagerUser` .</span><span class="sxs-lookup"><span data-stu-id="6c08d-125">Use the following code to change the ownership of the `Purchasing` schema to the `TestManagerUser` account.</span></span> <span data-ttu-id="6c08d-126">Esto permite que dicha cuenta use todo el acceso a las instrucciones del lenguaje de manipulación de datos (DML) (por ejemplo, los permisos `SELECT` e `INSERT` ) en los objetos que contiene.</span><span class="sxs-lookup"><span data-stu-id="6c08d-126">This allows that account to use all Data Manipulation Language (DML) statement access (such as `SELECT` and `INSERT` permissions) on the objects it contains.</span></span> <span data-ttu-id="6c08d-127">`TestManagerUser` también tiene la capacidad de crear procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="6c08d-127">`TestManagerUser` is also granted the ability to create stored procedures.</span></span>  
  
```  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
```  
  
 <span data-ttu-id="6c08d-128">Para obtener más información sobre la instrucción GRANT, consulte [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c08d-128">For more information about the GRANT statement, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="6c08d-129">Para obtener más información sobre los procedimientos almacenados, consulte [Procedimientos almacenados &#40;motor de base de datos&#41;](stored-procedures/stored-procedures-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="6c08d-129">For more information about stored procedures, see [Stored Procedures &#40;Database Engine&#41;](stored-procedures/stored-procedures-database-engine.md).</span></span> <span data-ttu-id="6c08d-130">Para obtener un póster de todos los [!INCLUDE[ssDE](../includes/ssde-md.md)] permisos, vea [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf) .</span><span class="sxs-lookup"><span data-stu-id="6c08d-130">For a poster of all [!INCLUDE[ssDE](../includes/ssde-md.md)] permissions, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>  
  
## <a name="2-create-a-stored-procedure-to-access-data"></a><span data-ttu-id="6c08d-131">2. Crear un procedimiento almacenado para obtener acceso a los datos</span><span class="sxs-lookup"><span data-stu-id="6c08d-131">2. Create a Stored Procedure to Access Data</span></span>  
 <span data-ttu-id="6c08d-132">Para cambiar el contexto dentro de una base de datos, use la instrucción EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="6c08d-132">To switch context within a database, use the EXECUTE AS statement.</span></span> <span data-ttu-id="6c08d-133">EXECUTE AS requiere permisos IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="6c08d-133">EXECUTE AS requires IMPERSONATE permissions.</span></span>  
  
 <span data-ttu-id="6c08d-134">Use la instrucción `EXECUTE AS` en el código siguiente para cambiar el contexto a `TestManagerUser` y crear un procedimiento almacenado que muestre únicamente los datos exigidos por `TestEmployeeUser`.</span><span class="sxs-lookup"><span data-stu-id="6c08d-134">Use the `EXECUTE AS` statement in the following code to change the context to `TestManagerUser` and create a stored procedure showing only the data required by `TestEmployeeUser`.</span></span> <span data-ttu-id="6c08d-135">Para cumplir los requisitos, el procedimiento almacenado acepta una variable para el número del pedido de compra y no muestra la información financiera, y la cláusula WHERE limita los resultados a los envíos parciales.</span><span class="sxs-lookup"><span data-stu-id="6c08d-135">To satisfy the requirements, the stored procedure accepts one variable for the purchase order number and does not display financial information, and the WHERE clause limits the results to partial shipments.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestManagerUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader a  
      INNER JOIN Purchasing.PurchaseOrderDetail b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END  
GO  
```  
  
 <span data-ttu-id="6c08d-136">En estos momentos, `TestEmployeeUser` no tiene acceso a ningún objeto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c08d-136">Currently `TestEmployeeUser` does not have access to any database objects.</span></span> <span data-ttu-id="6c08d-137">El código siguiente (todavía en el contexto de `TestManagerUser` ) permite que la cuenta de usuario consulte la información de tabla base mediante el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="6c08d-137">The following code (still in the `TestManagerUser` context) grants the user account the ability to query base-table information through the stored procedure.</span></span>  
  
```  
GRANT EXECUTE  
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO  
```  
  
 <span data-ttu-id="6c08d-138">El procedimiento almacenado forma parte del esquema de `Purchasing` , aunque no se especifica explícitamente ningún esquema, porque `TestManagerUser` se asigna de forma predeterminada al esquema `Purchasing` .</span><span class="sxs-lookup"><span data-stu-id="6c08d-138">The stored procedure is part of the `Purchasing` schema, even though no schema was explicitly specified, because `TestManagerUser` is assigned by default to the `Purchasing` schema.</span></span> <span data-ttu-id="6c08d-139">La información del catálogo del sistema se puede utilizar para buscar objetos, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6c08d-139">You can use system catalog information to locate objects, as shown in the following code.</span></span>  
  
```  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas a  
   INNER JOIN sys.objects b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
```  
  
 <span data-ttu-id="6c08d-140">Una vez finalizada esta sección del ejemplo, el código vuelve a cambiar el contexto a dbo mediante la instrucción `REVERT`.</span><span class="sxs-lookup"><span data-stu-id="6c08d-140">With this section of the example completed, the code switches context back to dbo using the `REVERT` statement.</span></span>  
  
```  
REVERT;  
GO  
```  
  
 <span data-ttu-id="6c08d-141">Para obtener más información sobre la instrucción REVERT, consulte [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c08d-141">For more information about the REVERT statement, see [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span></span>  
  
## <a name="3-access-data-through-the-stored-procedure"></a><span data-ttu-id="6c08d-142">3. Obtener acceso a los datos mediante el procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="6c08d-142">3. Access Data Through the Stored Procedure</span></span>  
 <span data-ttu-id="6c08d-143">`TestEmployeeUser` no tiene ningún permiso en los objetos de la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] aparte del inicio de sesión y los derechos asignados al rol de base de datos pública.</span><span class="sxs-lookup"><span data-stu-id="6c08d-143">`TestEmployeeUser` has no permissions on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database objects other than a login and the rights assigned to the public database role.</span></span> <span data-ttu-id="6c08d-144">El código siguiente devuelve un error cuando `TestEmployeeUser` intenta obtener acceso a las tablas base.</span><span class="sxs-lookup"><span data-stu-id="6c08d-144">The following code returns an error when `TestEmployeeUser` attempts to access base tables.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestEmployeeUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* This won't work */  
SELECT *  
FROM Purchasing.PurchaseOrderHeader;  
GO  
SELECT *  
FROM Purchasing.PurchaseOrderDetail;  
GO  
```  
  
 <span data-ttu-id="6c08d-145">Puesto que los objetos a los que hace referencia el procedimiento almacenado, creados en la última sección, pertenecen a `TestManagerUser` en virtud de la propiedad de esquema `Purchasing` , `TestEmployeeUser` puede tener acceso a las tablas base mediante el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="6c08d-145">Because the objects referenced by the stored procedure created in the last section are owned by `TestManagerUser` by virtue of the `Purchasing` schema ownership, `TestEmployeeUser` can access the base tables through the stored procedure.</span></span> <span data-ttu-id="6c08d-146">El código siguiente, que todavía usa el contexto `TestEmployeeUser` , pasa el pedido de compra 952 como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="6c08d-146">The following code, still using the `TestEmployeeUser` context, passes purchase order 952 as a parameter.</span></span>  
  
```  
EXEC Purchasing.usp_ShowWaitingItems 952  
GO  
```  
  
## <a name="4-reset-the-environment"></a><span data-ttu-id="6c08d-147">4. Restablecer el entorno</span><span class="sxs-lookup"><span data-stu-id="6c08d-147">4. Reset the Environment</span></span>  
 <span data-ttu-id="6c08d-148">El código siguiente usa el comando `REVERT` para devolver el contexto de la cuenta actual a `dbo`y, a continuación, restablece el entorno.</span><span class="sxs-lookup"><span data-stu-id="6c08d-148">The following code uses the `REVERT` command to return the context of the current account to `dbo`, and then resets the environment.</span></span>  
  
```  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
##  <a name="complete-example"></a><a name="CompleteExample"></a><span data-ttu-id="6c08d-149">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="6c08d-149">Complete Example</span></span>  
 <span data-ttu-id="6c08d-150">En esta sección se muestra el código de ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="6c08d-150">This section displays the complete example code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c08d-151">Este código no incluye los dos errores esperados que demuestran la incapacidad de `TestEmployeeUser` para seleccionar en las tablas base.</span><span class="sxs-lookup"><span data-stu-id="6c08d-151">This code does not include the two expected errors that demonstrate the inability of `TestEmployeeUser` to select from base tables.</span></span>  
  
```  
/*   
Script:       UserContextTutorial.sql  
Author:       Microsoft  
Last Updated: Books Online  
Conditions:   Execute as DBO or sysadmin in the AdventureWorks database  
Section 1:    Configure the Environment   
*/  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* Create server and database users */  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
  
GO  
  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
  
/*   
Section 2: Switch Context and Create Objects  
*/  
EXECUTE AS LOGIN = 'TestManagerUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader AS a  
      INNER JOIN Purchasing.PurchaseOrderDetail AS b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END;  
GO  
  
/* Give the employee the ability to run the procedure */  
GRANT EXECUTE   
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO   
  
/* Notice that the stored procedure is located in the Purchasing   
schema. This also demonstrates system catalogs */  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas AS a  
   INNER JOIN sys.objects AS b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
  
/* Go back to being the dbo user */  
REVERT;  
GO  
  
/*  
Section 3: Switch Context and Observe Security   
*/  
EXECUTE AS LOGIN = 'TestEmployeeUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
EXEC Purchasing.usp_ShowWaitingItems 952;  
GO  
  
/*   
Section 4: Clean Up Example  
*/  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c08d-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c08d-152">See Also</span></span>  
 [<span data-ttu-id="6c08d-153">Centro de seguridad para el Motor de base de datos de SQL Server y Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="6c08d-153">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
