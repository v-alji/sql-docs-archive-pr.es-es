---
title: Modificación de funciones definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 891c37b3-cb72-411f-9937-ee87e6d95f34
author: rothja
ms.author: jroth
ms.openlocfilehash: 1cf25fef91834e237f5cbaac26350220840830bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676893"
---
# <a name="modify-user-defined-functions"></a><span data-ttu-id="5ac76-102">Modificar funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="5ac76-102">Modify User-defined Functions</span></span>
  <span data-ttu-id="5ac76-103">Puede modificar funciones definidas por el usuario en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac76-103">You can modify user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5ac76-104">La modificación de las funciones definidas por el usuario como se describe a continuación no cambiará los permisos de las funciones ni afectará a las funciones, procedimientos almacenados, o desencadenadores dependientes.</span><span class="sxs-lookup"><span data-stu-id="5ac76-104">Modifying user-defined functions as described below will not change the functions' permissions, nor will it affect any dependent functions, stored procedures, or triggers.</span></span>  
  
 <span data-ttu-id="5ac76-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5ac76-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5ac76-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5ac76-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5ac76-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5ac76-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5ac76-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ac76-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5ac76-109">**Para modificar una función definida por el usuario, mediante:**</span><span class="sxs-lookup"><span data-stu-id="5ac76-109">**To modify a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="5ac76-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ac76-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5ac76-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ac76-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5ac76-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5ac76-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5ac76-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5ac76-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5ac76-114">ALTER FUNCTION no se puede utilizar para realizar ninguna de estas acciones:</span><span class="sxs-lookup"><span data-stu-id="5ac76-114">ALTER FUNCTION cannot be used to perform any of the following actions:</span></span>  
  
-   <span data-ttu-id="5ac76-115">Cambiar una función escalar a una función con valores de tabla, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="5ac76-115">Change a scalar-valued function to a table-valued function, or vice versa.</span></span>  
  
-   <span data-ttu-id="5ac76-116">Cambiar una función insertada a una función de múltiples instrucciones, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="5ac76-116">Change an inline function to a multistatement function, or vice versa.</span></span>  
  
-   <span data-ttu-id="5ac76-117">Cambiar una función de Transact-SQL en una función CLR, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="5ac76-117">Change a Transact-SQL function to a CLR function, or vice-versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5ac76-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ac76-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5ac76-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="5ac76-119">Permissions</span></span>  
 <span data-ttu-id="5ac76-120">Requiere el permiso ALTER para la función o para el esquema.</span><span class="sxs-lookup"><span data-stu-id="5ac76-120">Requires ALTER permission on the function or on the schema.</span></span> <span data-ttu-id="5ac76-121">Si la función especifica un tipo definido por el usuario, requiere el permiso EXECUTE para ese tipo.</span><span class="sxs-lookup"><span data-stu-id="5ac76-121">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5ac76-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ac76-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="5ac76-123">Para modificar una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="5ac76-123">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="5ac76-124">Haga clic en el signo más junto a la base de datos que contenga la función que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="5ac76-124">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="5ac76-125">Haga clic en el signo más junto a la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="5ac76-125">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="5ac76-126">Haga clic en el signo más junto a la carpeta que contenga la función que desea modificar:</span><span class="sxs-lookup"><span data-stu-id="5ac76-126">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="5ac76-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="5ac76-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="5ac76-128">Función con valor escalar</span><span class="sxs-lookup"><span data-stu-id="5ac76-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="5ac76-129">Función de agregado</span><span class="sxs-lookup"><span data-stu-id="5ac76-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="5ac76-130">Haga clic con el botón derecho en la función que quiere modificar y seleccione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="5ac76-130">Right-click the function you want to modify and select **Modify**.</span></span>  
  
5.  <span data-ttu-id="5ac76-131">En la ventana de consulta, realice los cambios necesarios en la instrucción ALTER FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="5ac76-131">In the Query Window, make the necessary changes to the ALTER FUNCTION statement.</span></span>  
  
6.  <span data-ttu-id="5ac76-132">En el menú **Archivo** , haga clic en **Guardar**_nombre_de_función_.</span><span class="sxs-lookup"><span data-stu-id="5ac76-132">On the **File** menu, click **Save**_function_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5ac76-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ac76-133">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="5ac76-134">Para modificar una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="5ac76-134">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="5ac76-135">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac76-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5ac76-136">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5ac76-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5ac76-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5ac76-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Scalar-Valued Function  
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetAccountingEndDate]()  
    RETURNS [datetime]   
    AS   
    BEGIN  
        RETURN DATEADD(millisecond, -2, CONVERT(datetime, '20040701', 112));  
    END;  
    ```  
  
    ```  
    -- Table-Valued Function   
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetContactInformation](@PersonID int)  
    RETURNS @retContactInformation TABLE   
    (  
        -- Columns returned by the function  
        [PersonID] int NOT NULL,   
        [FirstName] [nvarchar](50) NULL,   
        [LastName] [nvarchar](50) NULL,   
        [JobTitle] [nvarchar](50) NULL,  
        [BusinessEntityType] [nvarchar](50) NULL  
    )  
    AS   
    -- Returns the first name, last name, job title and business entity type for the specified contact.  
    -- Since a contact can serve multiple roles, more than one row may be returned.  
    BEGIN  
    IF @PersonID IS NOT NULL   
    BEGIN  
         IF EXISTS(SELECT * FROM [HumanResources].[Employee] e   
         WHERE e.[BusinessEntityID] = @PersonID)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, e.[JobTitle], 'Employee'  
              FROM [HumanResources].[Employee] AS e  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = e.[BusinessEntityID]  
              WHERE e.[BusinessEntityID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Purchasing].[Vendor] AS v  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Vendor Contact'   
              FROM [Purchasing].[Vendor] AS v  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Sales].[Store] AS s  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Store Contact'   
              FROM [Sales].[Store] AS s  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Person].[Person] AS p  
         INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
         WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, NULL, 'Consumer'   
              FROM [Person].[Person] AS p  
              INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
              WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL;   
         END  
    RETURN;  
    END;  
    ```  
  
 <span data-ttu-id="5ac76-138">Para obtener más información, vea [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ac76-138">For more information, see [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span></span>  
  
  
