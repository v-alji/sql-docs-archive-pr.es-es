---
title: Ejecutar funciones definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- invoking user-defined functions
- user-defined functions [SQL Server], executing
ms.assetid: 0de7744d-9b73-463f-ae80-e31a020004b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4446f3b3a132488fdac6e859f30abaca40a193d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678116"
---
# <a name="execute-user-defined-functions"></a><span data-ttu-id="768c1-102">Ejecutar funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="768c1-102">Execute User-defined Functions</span></span>
  <span data-ttu-id="768c1-103">Puede ejecutar una función definida por el usuario en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="768c1-103">You can execute a user defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="768c1-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="768c1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="768c1-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="768c1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="768c1-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="768c1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="768c1-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="768c1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="768c1-108">**Para ejecutar una función definida por el usuario, usando:**</span><span class="sxs-lookup"><span data-stu-id="768c1-108">**To execute a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="768c1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="768c1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="768c1-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="768c1-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="768c1-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="768c1-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="768c1-112">En Transact-SQL, los parámetros se pueden proporcionar mediante *value* o @*parameter_name*=*value.*</span><span class="sxs-lookup"><span data-stu-id="768c1-112">In Transact-SQL, parameters can be supplied either by using *value* or by using @*parameter_name*=*value.*</span></span> <span data-ttu-id="768c1-113">Un parámetro no forma parte de una transacción; por tanto, si se cambia un parámetro en una transacción que se revierte posteriormente, el valor del parámetro no vuelve a su valor anterior.</span><span class="sxs-lookup"><span data-stu-id="768c1-113">A parameter is not part of a transaction; therefore, if a parameter is changed in a transaction that is later rolled back, the value of the parameter does not revert to its previous value.</span></span> <span data-ttu-id="768c1-114">El valor devuelto al procedimiento llamante es siempre el valor del parámetro en el momento en que finaliza el módulo llamado.</span><span class="sxs-lookup"><span data-stu-id="768c1-114">The value returned to the caller is always the value at the time the module returns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="768c1-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="768c1-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="768c1-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="768c1-116">Permissions</span></span>  
 <span data-ttu-id="768c1-117">No se requieren permisos para ejecutar la instrucción EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="768c1-117">Permissions are not required to run the EXECUTE statement.</span></span> <span data-ttu-id="768c1-118">Sin embargo, se requieren permisos para los elementos protegibles a los que se hace referencia en la cadena EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="768c1-118">However, permissions are required on the securables that are referenced within the EXECUTE string.</span></span> <span data-ttu-id="768c1-119">Por ejemplo, si la cadena contiene una instrucción INSERT, el autor de llamada de la instrucción EXECUTE debe tener el permiso INSERT en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="768c1-119">For example, if the string contains an INSERT statement, the caller of the EXECUTE statement must have INSERT permission on the target table.</span></span> <span data-ttu-id="768c1-120">Los permisos se comprueban cuando se encuentra la instrucción EXECUTE, incluso si la instrucción EXECUTE está incluida en un módulo.</span><span class="sxs-lookup"><span data-stu-id="768c1-120">Permissions are checked at the time EXECUTE statement is encountered, even if the EXECUTE statement is included within a module.</span></span> <span data-ttu-id="768c1-121">Para obtener más información, vea [execute &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="768c1-121">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="768c1-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="768c1-122">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-user-defined-function"></a><span data-ttu-id="768c1-123">Para ejecutar una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="768c1-123">To execute a user-defined function</span></span>  
  
1.  <span data-ttu-id="768c1-124">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="768c1-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="768c1-125">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="768c1-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="768c1-126">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="768c1-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Declares a variable and sets it to zero.  
    -- This variable is used to return the results of the function.  
    DECLARE @ret nvarchar(15)= NULL;   
  
    -- Executes the dbo.ufnGetSalesOrderStatusText function.  
    --The function requires a value for one parameter, @Status.   
    EXEC @ret = dbo.ufnGetSalesOrderStatusText @Status= 5;   
    --Returns the result in the message tab.  
    PRINT @ret;  
    ```  
  
 <span data-ttu-id="768c1-127">Para obtener más información, vea [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="768c1-127">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
  
