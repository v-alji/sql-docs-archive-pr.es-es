---
title: Nueva compilación de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- sp_recompile
- WITH RECOMPILE clause
- recompiling stored procedures
- stored procedures [SQL Server], recompiling
ms.assetid: b90deb27-0099-4fe7-ba60-726af78f7c18
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a9bc0e1d4baecb7f4c66b83b57081ed3131123d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678151"
---
# <a name="recompile-a-stored-procedure"></a><span data-ttu-id="6490f-102">Volver a compilar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="6490f-102">Recompile a Stored Procedure</span></span>
  <span data-ttu-id="6490f-103">En este tema se describe cómo volver a compilar un procedimiento almacenado en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6490f-103">This topic describes how to recompile a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6490f-104">Hay tres maneras de hacerlo: `WITH RECOMPILE` la opción en la definición del procedimiento o cuando se llama al procedimiento, la `RECOMPILE` sugerencia de consulta en instrucciones individuales o el `sp_recompile` procedimiento almacenado del sistema.</span><span class="sxs-lookup"><span data-stu-id="6490f-104">There are three ways to do this: `WITH RECOMPILE` option in the procedure definition or when the procedure is called, the `RECOMPILE` query hint on individual statements, or by using the `sp_recompile` system stored procedure.</span></span> <span data-ttu-id="6490f-105">En este tema se describe el uso de la opción WITH RECOMPILE al crear una definición de procedimiento y ejecutar un procedimiento existente.</span><span class="sxs-lookup"><span data-stu-id="6490f-105">This topic describes using the WITH RECOMPILE option when creating a procedure definition and executing an existing procedure.</span></span> <span data-ttu-id="6490f-106">También se describe el uso del procedimiento almacenado del sistema sp_recompile para volver a compilar un procedimiento existente.</span><span class="sxs-lookup"><span data-stu-id="6490f-106">It also describes using the sp_recompile system stored procedure to recompile an existing procedure.</span></span>  
  
 <span data-ttu-id="6490f-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6490f-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6490f-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6490f-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6490f-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="6490f-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="6490f-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6490f-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6490f-111">**Para volver a compilar un procedimiento almacenado, usando:**</span><span class="sxs-lookup"><span data-stu-id="6490f-111">**To recompile a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="6490f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6490f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6490f-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6490f-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6490f-114">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="6490f-114">Recommendations</span></span>  
  
-   <span data-ttu-id="6490f-115">Cuando un procedimiento se compila por primera vez o se vuelve a compilar, el plan de consulta del procedimiento se optimiza para el estado actual de la base de datos y sus objetos.</span><span class="sxs-lookup"><span data-stu-id="6490f-115">When a procedure is compiled for the first time or recompiled, the procedure's query plan is optimized for the current state of the database and its objects.</span></span> <span data-ttu-id="6490f-116">Si una base de datos experimenta cambios significativos en sus datos o su estructura, al volver a compilar un procedimiento se actualiza y optimiza el plan de consulta del procedimiento para tener en cuenta esos cambios.</span><span class="sxs-lookup"><span data-stu-id="6490f-116">If a database undergoes significant changes to its data or structure, recompiling a procedure updates and optimizes the procedure's query plan for those changes.</span></span> <span data-ttu-id="6490f-117">Esto puede mejorar el rendimiento de procesamiento del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-117">This can improve the procedure's processing performance.</span></span>  
  
-   <span data-ttu-id="6490f-118">Hay ocasiones en las que se debe forzar la nueva compilación del procedimiento y otras en que se realiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6490f-118">There are times when procedure recompilation must be forced and other times when it occurs automatically.</span></span> <span data-ttu-id="6490f-119">La nueva compilación automática tiene lugar siempre que se reinicia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6490f-119">Automatic recompiling occurs whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted.</span></span> <span data-ttu-id="6490f-120">También se produce si una tabla subyacente a la que hace referencia el procedimiento ha experimentado cambios de diseño físico.</span><span class="sxs-lookup"><span data-stu-id="6490f-120">It also occurs if an underlying table referenced by the procedure has undergone physical design changes.</span></span>  
  
-   <span data-ttu-id="6490f-121">Otro motivo para forzar la nueva compilación de un procedimiento es contrarrestar el comportamiento de "examen de parámetros" de la compilación de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="6490f-121">Another reason to force a procedure to recompile is to counteract the "parameter sniffing" behavior of procedure compilation.</span></span> <span data-ttu-id="6490f-122">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecuta procedimientos, los valores de parámetros usados por el procedimiento cuando se compila se incluyen como parte de la generación del plan de consulta.</span><span class="sxs-lookup"><span data-stu-id="6490f-122">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes procedures, any parameter values that are used by the procedure when it compiles are included as part of generating the query plan.</span></span> <span data-ttu-id="6490f-123">Si esos valores representan los valores típicos con los que se llama al procedimiento posteriormente, el procedimiento se beneficia del plan de consulta cada vez que se compila y se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="6490f-123">If these values represent the typical ones with which the procedure is subsequently called, then the procedure benefits from the query plan every time that it compiles and executes.</span></span> <span data-ttu-id="6490f-124">Si los valores de parámetro del procedimiento suelen ser atípicos, forzar una nueva compilación del procedimiento y un nuevo plan basándose en diferentes valores de parámetro puede mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-124">If parameter values on the procedure are frequently atypical, forcing a recompile of the procedure and a new plan based on different parameter values can improve performance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6490f-125">incorpora nueva compilación de nivel de instrucciones de los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="6490f-125">features statement-level recompilation of procedures.</span></span> <span data-ttu-id="6490f-126">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vuelve a compilar procedimientos almacenados, solo se compila la instrucción que ha causado la nueva compilación, en lugar de todo el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompiles stored procedures, only the statement that caused the recompilation is compiled, instead of the complete procedure.</span></span>  
  
-   <span data-ttu-id="6490f-127">Si algunas consultas de un procedimiento suelen usar valores atípicos o temporales, se puede mejorar el rendimiento del procedimiento con la sugerencia de consulta RECOMPILE dentro de esas consultas.</span><span class="sxs-lookup"><span data-stu-id="6490f-127">If certain queries in a procedure regularly use atypical or temporary values, procedure performance can be improved by using the RECOMPILE query hint inside those queries.</span></span> <span data-ttu-id="6490f-128">Puesto que solo se volverán a compilar las consultas que usan la sugerencia de consulta en lugar del procedimiento completo, se imita el comportamiento de nueva compilación de nivel de instrucciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6490f-128">Since only the queries using the query hint will be recompiled instead of the complete procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]'s statement-level recompilation behavior is mimicked.</span></span> <span data-ttu-id="6490f-129">Además de usar los valores de parámetro actuales del procedimiento, la sugerencia de consulta RECOMPILE también emplea los valores de cualquier variable local del procedimiento almacenado al compilar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="6490f-129">But in addition to using the procedure's current parameter values, the RECOMPILE query hint also uses the values of any local variables inside the stored procedure when you compile the statement.</span></span> <span data-ttu-id="6490f-130">Para obtener más información, vea [Sugerencias de consulta (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="6490f-130">For more information, see [Query Hint (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6490f-131">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6490f-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6490f-132">Permisos</span><span class="sxs-lookup"><span data-stu-id="6490f-132">Permissions</span></span>  
 <span data-ttu-id="6490f-133">`WITH RECOMPILE`Desea</span><span class="sxs-lookup"><span data-stu-id="6490f-133">`WITH RECOMPILE` Option</span></span>  
 <span data-ttu-id="6490f-134">Si se usa esta opción cuando se crea la definición del procedimiento, se necesita el permiso CREATE PROCEDURE en la base de datos y el permiso ALTER en el esquema en el que se crea el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-134">If this option is used when the procedure definition is created, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="6490f-135">Si se usa esta opción en una instrucción EXECUTE, se necesitan permisos EXECUTE para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-135">If this option is used in an EXECUTE statement, it requires EXECUTE permissions on the procedure.</span></span> <span data-ttu-id="6490f-136">No se necesitan permisos en la propia instrucción EXECUTE, pero sí se necesitan permisos de ejecución en el procedimiento al que se hace referencia en la instrucción EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="6490f-136">Permissions are not required on the EXECUTE statement itself but execute permissions are required on the procedure referenced in the EXECUTE statement.</span></span> <span data-ttu-id="6490f-137">Para obtener más información, vea [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6490f-137">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
 <span data-ttu-id="6490f-138">`RECOMPILE`Sugerencia de consulta</span><span class="sxs-lookup"><span data-stu-id="6490f-138">`RECOMPILE` Query Hint</span></span>  
 <span data-ttu-id="6490f-139">Esta característica se emplea cuando se crea el procedimiento y la sugerencia se incluye en las instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-139">This feature is used when the procedure is created and the hint is included in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure.</span></span> <span data-ttu-id="6490f-140">Por tanto, necesita el permiso CREATE PROCEDURE en la base de datos y el permiso ALTER en el esquema en el que se va a crear el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-140">Therefore, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="6490f-141">`sp_recompile`Procedimiento almacenado del sistema</span><span class="sxs-lookup"><span data-stu-id="6490f-141">`sp_recompile` System Stored Procedure</span></span>  
 <span data-ttu-id="6490f-142">Necesita el permiso ALTER en el procedimiento especificado.</span><span class="sxs-lookup"><span data-stu-id="6490f-142">Requires ALTER permission on the specified procedure.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6490f-143">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6490f-143">Using Transact-SQL</span></span>  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="6490f-144">Para volver a compilar un procedimiento almacenado usando la opción WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="6490f-144">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="6490f-145">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6490f-145">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6490f-146">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6490f-146">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6490f-147">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6490f-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6490f-148">En este ejemplo se crea la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-148">This example creates the procedure definition.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspProductByVendor', 'P' ) IS NOT NULL   
    DROP PROCEDURE dbo.uspProductByVendor;  
GO  
CREATE PROCEDURE dbo.uspProductByVendor @Name varchar(30) = '%'  
WITH RECOMPILE  
AS  
    SET NOCOUNT ON;  
    SELECT v.Name AS 'Vendor name', p.Name AS 'Product name'  
    FROM Purchasing.Vendor AS v   
    JOIN Purchasing.ProductVendor AS pv   
      ON v.BusinessEntityID = pv.BusinessEntityID   
    JOIN Production.Product AS p   
      ON pv.ProductID = p.ProductID  
    WHERE v.Name LIKE @Name;  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="6490f-149">Para volver a compilar un procedimiento almacenado usando la opción WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="6490f-149">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="6490f-150">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6490f-150">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6490f-151">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6490f-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6490f-152">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6490f-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6490f-153">En este ejemplo se crea un procedimiento simple que devuelve todos los empleados (nombre y apellidos), sus puestos y los nombres de sus departamentos a partir de una vista.</span><span class="sxs-lookup"><span data-stu-id="6490f-153">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="6490f-154">Después, copie y pegue el segundo ejemplo de código en la ventana de consulta y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6490f-154">And then copy and paste the second code example into the query window and click **Execute**.</span></span> <span data-ttu-id="6490f-155">Esto ejecutará el procedimiento y volverá a compilar el plan de consulta del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-155">This executes the procedure and recompiles the procedure's query plan.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXECUTE HumanResources.uspGetAllEmployees WITH RECOMPILE;  
GO  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-sp_recompile"></a><span data-ttu-id="6490f-156">Para volver a compilar un procedimiento almacenado mediante sp_recompile</span><span class="sxs-lookup"><span data-stu-id="6490f-156">To recompile a stored procedure by using sp_recompile</span></span>  
  
1.  <span data-ttu-id="6490f-157">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6490f-157">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6490f-158">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6490f-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6490f-159">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6490f-159">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6490f-160">En este ejemplo se crea un procedimiento simple que devuelve todos los empleados (nombre y apellidos), sus puestos y los nombres de sus departamentos a partir de una vista.</span><span class="sxs-lookup"><span data-stu-id="6490f-160">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="6490f-161">Después, copie y pegue el ejemplo siguiente en la ventana de consulta y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6490f-161">Then, copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6490f-162">Esto no ejecuta el procedimiento, sino que lo marca para que se vuelva a compilar de forma que su plan de consulta se actualice la próxima vez que se ejecute el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6490f-162">This does not execute the procedure but it does mark the procedure to be recompiled so that its query plan is updated the next time that the procedure is executed.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_recompile N'HumanResources.uspGetAllEmployees';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6490f-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6490f-163">See Also</span></span>  
 <span data-ttu-id="6490f-164">[Crear un procedimiento almacenado](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6490f-164">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6490f-165">[Modificar un procedimiento almacenado](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6490f-165">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6490f-166">[Cambiar el nombre de un procedimiento almacenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6490f-166">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6490f-167">[Ver la definición de un procedimiento almacenado](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6490f-167">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6490f-168">[Ver las dependencias de un procedimiento almacenado](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6490f-168">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="6490f-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6490f-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
