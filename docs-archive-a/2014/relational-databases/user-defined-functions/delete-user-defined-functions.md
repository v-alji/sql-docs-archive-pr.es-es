---
title: Eliminación de funciones definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: db1d668a-23b7-4757-a9c5-1bd848ba7f6d
author: rothja
ms.author: jroth
ms.openlocfilehash: e5f6b2b306c4fe8db08b088d9607cfb19ab0f25e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676896"
---
# <a name="delete-user-defined-functions"></a><span data-ttu-id="a0a4c-102">Eliminar funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="a0a4c-102">Delete User-defined Functions</span></span>
  <span data-ttu-id="a0a4c-103">Puede eliminar (quitar) las funciones definidas por el usuario en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a4c-103">You can delete (drop) user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="a0a4c-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a0a4c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a0a4c-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a0a4c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a0a4c-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a0a4c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a0a4c-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a0a4c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a0a4c-108">**Para eliminar una función definida por el usuario, usando:**</span><span class="sxs-lookup"><span data-stu-id="a0a4c-108">**To delete a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="a0a4c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0a4c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a0a4c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0a4c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a0a4c-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a0a4c-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a0a4c-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a0a4c-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a0a4c-113">No podrá eliminar la función si hay vistas o funciones de Transact-SQL en la base de datos que hagan referencia a esta función y que fueron creadas con SCHEMABINDING; tampoco funcionará si existen columnas calculadas o restricciones CHECK o DEFAULT que hacen referencia a la función.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-113">You will not be able to delete the function if there are Transact-SQL functions or views in the database that reference this function and were created by using SCHEMABINDING, or if there are computed columns, CHECK constraints, or DEFAULT constraints that reference the function.</span></span>  
  
-   <span data-ttu-id="a0a4c-114">No podrá eliminar la función si existen columnas calculadas que hagan referencia a esta función y que hayan sido indizadas.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-114">You will not be able to delete the function if there are computed columns that reference this function and have been indexed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a0a4c-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a0a4c-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a0a4c-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="a0a4c-116">Permissions</span></span>  
 <span data-ttu-id="a0a4c-117">Requiere el permiso ALTER en el esquema al que pertenece la función o el permiso CONTROL en la función.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-117">Requires ALTER permission on the schema to which the function belongs, or CONTROL permission on the function.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a0a4c-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0a4c-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="a0a4c-119">Para eliminar un perfil definido por la función</span><span class="sxs-lookup"><span data-stu-id="a0a4c-119">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="a0a4c-120">Haga clic en el signo más junto a la base de datos que contenga la función que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-120">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="a0a4c-121">Haga clic en el signo más junto a la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="a0a4c-121">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="a0a4c-122">Haga clic en el signo más junto a la carpeta que contenga la función que desea modificar:</span><span class="sxs-lookup"><span data-stu-id="a0a4c-122">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="a0a4c-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="a0a4c-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="a0a4c-124">Función con valor escalar</span><span class="sxs-lookup"><span data-stu-id="a0a4c-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="a0a4c-125">Función de agregado</span><span class="sxs-lookup"><span data-stu-id="a0a4c-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="a0a4c-126">Haga clic con el botón derecho en la función que quiera eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-126">Right-click the function you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="a0a4c-127">En el cuadro de diálogo **Eliminar objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-127">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a0a4c-128">Haga clic en **Mostrar dependencias** en el cuadro de diálogo **eliminar objeto** para abrir el cuadro de diálogo**dependencias** _function_name_.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-128">Click **Show Dependencies** in the **Delete Object** dialog box to open the _function_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="a0a4c-129">De este modo, mostrará todos los objetos que dependen de la función y todos los objetos de los que la función depende.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-129">This will show all of the objects that depend on the function and all of the objects on which the function depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a0a4c-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0a4c-130">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="a0a4c-131">Para eliminar un perfil definido por la función</span><span class="sxs-lookup"><span data-stu-id="a0a4c-131">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="a0a4c-132">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0a4c-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a0a4c-133">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a0a4c-134">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates function called "Sales.ufn_SalesByStore"  
    USE AdventureWorks2012;  
    GO  
    CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
    RETURNS TABLE  
    AS  
    RETURN   
    (  
        SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
        FROM Production.Product AS P   
        JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
        JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
        JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
        WHERE C.StoreID = @storeid  
        GROUP BY P.ProductID, P.Name  
    );  
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- determines if function exists in database  
    IF OBJECT_ID (N'Sales.fn_SalesByStore', N'IF') IS NOT NULL  
    -- deletes function  
        DROP FUNCTION Sales.fn_SalesByStore;  
    GO  
    ```  
  
 <span data-ttu-id="a0a4c-135">Para obtener más información, vea [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0a4c-135">For more information, see [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
  
