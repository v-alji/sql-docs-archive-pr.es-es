---
title: Ejecutar un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.executeprocedure.f1
- sql12.swb.executeprocedure.general.f1
helpviewer_keywords:
- stored procedures [SQL Server], parameters
- extended stored procedures [SQL Server], executing
- system stored procedures [SQL Server], executing
- stored procedures [SQL Server], executing
- user-defined stored procedures [SQL Server]
ms.assetid: a0b1337d-2059-4872-8c62-3f967d8b170f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c679ba7af3ac9f60d312b33c0346e50687387476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676395"
---
# <a name="execute-a-stored-procedure"></a><span data-ttu-id="4f0ac-102">Ejecutar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="4f0ac-102">Execute a Stored Procedure</span></span>
  <span data-ttu-id="4f0ac-103">En este tema se describe cómo ejecutar un procedimiento almacenado en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f0ac-103">This topic describes how to execute a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4f0ac-104">Hay dos formas diferentes de ejecutar un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-104">There are two different ways to execute a stored procedure.</span></span> <span data-ttu-id="4f0ac-105">El primer método y más común es que una aplicación o un usuario llame al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-105">The first and most common approach is for an application or user to call the procedure.</span></span> <span data-ttu-id="4f0ac-106">El segundo método consiste en establecer el procedimiento para que se ejecute automáticamente cuando se inicie una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-106">The second approach is to set the procedure to run automatically when an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="4f0ac-107">Cuando una aplicación o un usuario llama a un procedimiento, la palabra clave EXECUTE o EXEC de [!INCLUDE[tsql](../../includes/tsql-md.md)] se indica explícitamente en la llamada.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-107">When a procedure is called by an application or user, the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE or EXEC keyword is explicitly stated in the call.</span></span> <span data-ttu-id="4f0ac-108">Como alternativa, se puede llamar al procedimiento y ejecutarlo sin la palabra clave si el procedimiento es la primera instrucción del lote de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-108">Alternatively, the procedure can be called and executed without the keyword if the procedure is the first statement in the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch.</span></span>  
  
 <span data-ttu-id="4f0ac-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4f0ac-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4f0ac-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4f0ac-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4f0ac-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4f0ac-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4f0ac-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4f0ac-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4f0ac-114">**Para ejecutar un procedimiento almacenado, usando:**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-114">**To execute a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="4f0ac-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f0ac-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4f0ac-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f0ac-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f0ac-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4f0ac-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4f0ac-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4f0ac-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4f0ac-119">La intercalación de base de datos de llamada se usa al comparar los nombres de los procedimientos del sistema.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-119">The calling database collation is used when matching system procedure names.</span></span> <span data-ttu-id="4f0ac-120">Por tanto, en las llamadas a procedimientos use siempre el modelo exacto de mayúsculas y minúsculas de los nombres de procedimientos del sistema.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-120">Therefore, always use the exact case of system procedure names in procedure calls.</span></span> <span data-ttu-id="4f0ac-121">Por ejemplo, este código generará un error si se ejecuta en el contexto de una base de datos que tenga una intercalación que distinga mayúsculas de minúsculas:</span><span class="sxs-lookup"><span data-stu-id="4f0ac-121">For example, this code will fail if it is executed in the context of a database that has a case-sensitive collation:</span></span>  
  
    ```sql  
    EXEC SP_heLP; -- Will fail to resolve because SP_heLP does not equal sp_help  
    ```  
  
     <span data-ttu-id="4f0ac-122">Para mostrar los nombres exactos de los procedimientos del sistema, consulte las vistas de catálogo [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) y [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-122">To display the exact system procedure names, query the [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) and [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) catalog views.</span></span>  
  
-   <span data-ttu-id="4f0ac-123">Si un procedimiento definido por el usuario tiene el mismo nombre que un procedimiento del sistema, puede que el procedimiento definido por el usuario no se ejecute nunca.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-123">If a user-defined procedure has the same name as a system procedure, the user-defined procedure might not ever execute.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4f0ac-124">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4f0ac-124">Recommendations</span></span>  
  
-   <span data-ttu-id="4f0ac-125">Ejecutar procedimientos almacenados del sistema</span><span class="sxs-lookup"><span data-stu-id="4f0ac-125">Executing System Stored Procedures</span></span>  
  
     <span data-ttu-id="4f0ac-126">Los procedimientos del sistema comienzan por el prefijo **sp_** .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-126">System procedures begin with the prefix **sp_**.</span></span> <span data-ttu-id="4f0ac-127">Puesto que aparecen lógicamente en todas las bases de datos definidas por el usuario y por el sistema, se pueden ejecutar desde cualquier base de datos sin necesidad de que calificar totalmente el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-127">Because they logically appear in all user- and system- defined databases, they can be executed from any database without having to fully quality the procedure name.</span></span> <span data-ttu-id="4f0ac-128">Pero se recomienda calificar como de esquema todos los nombres de procedimientos del sistema con el nombre de esquema **sys** para evitar conflictos de nombres.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-128">However, we recommend schema-qualifying all system procedure names with the **sys** schema name to prevent name conflicts.</span></span> <span data-ttu-id="4f0ac-129">En el ejemplo siguiente se muestra el método recomendado para llamar a un procedimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-129">The following example demonstrates the recommended method of calling a system procedure.</span></span>  
  
    ```sql  
    EXEC sys.sp_who;  
    ```  
  
-   <span data-ttu-id="4f0ac-130">Ejecutar procedimientos almacenados definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="4f0ac-130">Executing User-defined Stored Procedures</span></span>  
  
     <span data-ttu-id="4f0ac-131">Al ejecutar un procedimiento definido por el usuario, se recomienda calificar el nombre del procedimiento con el nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-131">When executing a user-defined procedure, we recommend qualifying the procedure name with the schema name.</span></span> <span data-ttu-id="4f0ac-132">Esta práctica proporciona un pequeño aumento del rendimiento porque el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] no tiene que buscar en varios esquemas.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-132">This practice gives a small performance boost because the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] does not have to search multiple schemas.</span></span> <span data-ttu-id="4f0ac-133">También evita la ejecución del procedimiento incorrecto si una base de datos tiene procedimientos con el mismo nombre en varios esquemas.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-133">It also prevents executing the wrong procedure if a database has procedures with the same name in multiple schemas.</span></span>  
  
     <span data-ttu-id="4f0ac-134">En el ejemplo siguiente se muestra el método recomendado para ejecutar un procedimiento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-134">The following example demonstrates the recommended method to execute a user-defined procedure.</span></span> <span data-ttu-id="4f0ac-135">Observe que el procedimiento acepta un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-135">Notice that the procedure accepts one input parameter.</span></span> <span data-ttu-id="4f0ac-136">Para obtener más información sobre cómo especificar parámetros de entrada y salida, vea [Especificar parámetros](specify-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4f0ac-136">For information about specifying input and output parameters, see [Specify Parameters](specify-parameters.md).</span></span>  
  
    ```sql  
    USE AdventureWorks2012;  
    GO  
    EXEC dbo.uspGetEmployeeManagers @BusinessEntityID = 50;  
    ```  
  
     <span data-ttu-id="4f0ac-137">-O bien-</span><span class="sxs-lookup"><span data-stu-id="4f0ac-137">-Or-</span></span>  
  
    ```sql  
    EXEC AdventureWorks2012.dbo.uspGetEmployeeManagers 50;  
    GO  
    ```  
  
     <span data-ttu-id="4f0ac-138">Si se especifica un procedimiento definido por el usuario no calificado, el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] busca el procedimiento siguiendo este orden:</span><span class="sxs-lookup"><span data-stu-id="4f0ac-138">If a nonqualified user-defined procedure is specified, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] searches for the procedure in the following order:</span></span>  
  
    1.  <span data-ttu-id="4f0ac-139">El esquema **sys** de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-139">The **sys** schema of the current database.</span></span>  
  
    2.  <span data-ttu-id="4f0ac-140">El esquema predeterminado del autor de la llamada si se ejecuta en un lote o en SQL dinámico.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-140">The caller's default schema if it is executed in a batch or in dynamic SQL.</span></span> <span data-ttu-id="4f0ac-141">O bien, si el nombre del procedimiento no calificado aparece dentro del cuerpo de otra definición de procedimiento, a continuación se busca en el esquema que contiene este otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-141">Or, if the nonqualified procedure name appears inside the body of another procedure definition, the schema that contains this other procedure is searched next.</span></span>  
  
    3.  <span data-ttu-id="4f0ac-142">El esquema **dbo** de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-142">The **dbo** schema in the current database.</span></span>  
  
-   <span data-ttu-id="4f0ac-143">Ejecutar procedimientos almacenados automáticamente</span><span class="sxs-lookup"><span data-stu-id="4f0ac-143">Executing Stored Procedures Automatically</span></span>  
  
     <span data-ttu-id="4f0ac-144">Los procedimientos marcados para su ejecución automática se ejecutan cada vez que se inicia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y la base de datos **maestra** se recupera durante ese proceso de inicio.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-144">Procedures marked for automatic execution are executed every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts and the **master** database is recovered during that startup process.</span></span> <span data-ttu-id="4f0ac-145">Puede ser útil configurar procedimientos para que se ejecuten automáticamente a la hora de realizar operaciones de mantenimiento de bases de datos o para tener procedimientos que se ejecutan continuamente como procesos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-145">Setting up procedures to execute automatically can be useful for performing database maintenance operations or for having procedures run continuously as background processes.</span></span> <span data-ttu-id="4f0ac-146">Otra forma de usar la ejecución automática consiste en que el procedimiento realice tareas del sistema o de mantenimiento en **tempdb**, como crear una tabla temporal global.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-146">Another use for automatic execution is to have the procedure perform system or maintenance tasks in **tempdb**, such as creating a global temporary table.</span></span> <span data-ttu-id="4f0ac-147">De este modo, se garantiza que esa tabla temporal existirá siempre cuando se vuelva a crear **tempdb** durante el inicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-147">This makes sure that such a temporary table will always exist when **tempdb** is re-created during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
     <span data-ttu-id="4f0ac-148">Un procedimiento que se ejecuta automáticamente funciona con los mismos permisos que los miembros del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-148">A procedure that is automatically executed operates with the same permissions as members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="4f0ac-149">Todos los mensajes de error generados por el procedimiento se escriben en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-149">Any error messages generated by the procedure are written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
     <span data-ttu-id="4f0ac-150">No existe límite en cuanto al número de procedimientos de inicio que se pueden crear, aunque debe tener en cuenta que cada uno consume un subproceso de trabajo mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-150">There is no limit to the number of startup procedures you can have, but be aware that each consumes one worker thread while executing.</span></span> <span data-ttu-id="4f0ac-151">Si es necesario ejecutar múltiples procedimientos en el inicio, pero no es necesario que se ejecuten en paralelo, haga que un procedimiento sea el procedimiento de inicio y que éste llame a los restantes.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-151">If you must execute multiple procedures at startup but do not need to execute them in parallel, make one procedure the startup procedure and have that procedure call the other procedures.</span></span> <span data-ttu-id="4f0ac-152">De este modo, solo se utiliza un subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-152">This uses only one worker thread.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="4f0ac-153">No se devuelve ningún conjunto de resultados de un procedimiento que se ejecuta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-153">Do not return any result sets from a procedure that is executed automatically.</span></span> <span data-ttu-id="4f0ac-154">Puesto que el responsable de ejecutar el procedimiento es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no una aplicación o un usuario, no existe ningún destino para el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-154">Because the procedure is being executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instead of an application or user, there is nowhere for the result sets to go.</span></span>  
  
-   <span data-ttu-id="4f0ac-155">Establecer, borrar y controlar la ejecución automática</span><span class="sxs-lookup"><span data-stu-id="4f0ac-155">Setting, Clearing, and Controlling Automatic Execution</span></span>  
  
     <span data-ttu-id="4f0ac-156">Solo el administrador del sistema (**sa**) puede marcar un procedimiento para que se ejecute automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-156">Only the system administrator (**sa**) can mark a procedure to execute automatically.</span></span> <span data-ttu-id="4f0ac-157">Además, el procedimiento debe encontrarse en la base de datos **maestra** , pertenecer a **sa**y no incluir parámetros de entrada ni de salida.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-157">In addition, the procedure must be in the **master** database, owned by **sa**, and cannot have input or output parameters.</span></span>  
  
     <span data-ttu-id="4f0ac-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) para:</span><span class="sxs-lookup"><span data-stu-id="4f0ac-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to:</span></span>  
  
    1.  <span data-ttu-id="4f0ac-159">Designar un procedimiento existente como procedimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-159">Designate an existing procedure as a startup procedure.</span></span>  
  
    2.  <span data-ttu-id="4f0ac-160">Detener la ejecución de un procedimiento al iniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-160">Stop a procedure from executing at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f0ac-161">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4f0ac-161">Security</span></span>  
 <span data-ttu-id="4f0ac-162">Para obtener más información, vea [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) y [EXECUTE AS &#40;Cláusula de Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f0ac-162">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) and [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f0ac-163">Permisos</span><span class="sxs-lookup"><span data-stu-id="4f0ac-163">Permissions</span></span>  
 <span data-ttu-id="4f0ac-164">Para obtener más información, vea la sección "Permisos" de [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f0ac-164">For more information, see the "Permissions" section in [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f0ac-165">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f0ac-165">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="4f0ac-166">Para ejecutar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="4f0ac-166">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="4f0ac-167">En el **Explorador de objetos**, conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expándala y, a continuación, expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-167">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="4f0ac-168">Expanda la base de datos que desee, expanda **Programación**y, a continuación, expanda **Procedimientos almacenados**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-168">Expand the database that you want, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  
  
3.  <span data-ttu-id="4f0ac-169">Haga clic con el botón derecho en el procedimiento almacenado definido por el usuario que quiera y, luego, haga clic en **Ejecutar procedimiento almacenado**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-169">Right-click the user-defined stored procedure that you want and click **Execute Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="4f0ac-170">En el cuadro de diálogo **Ejecutar procedimiento** , especifique un valor para cada parámetro y si debe pasar o no un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-170">In the **Execute Procedure** dialog box, specify a value for each parameter and whether it should pass a null value.</span></span>  
  
     <span data-ttu-id="4f0ac-171">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-171">**Parameter**</span></span>  
     <span data-ttu-id="4f0ac-172">Indica el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-172">Indicates the name of the parameter.</span></span>  
  
     <span data-ttu-id="4f0ac-173">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-173">**Data Type**</span></span>  
     <span data-ttu-id="4f0ac-174">Indica el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-174">Indicates the data type of the parameter.</span></span>  
  
     <span data-ttu-id="4f0ac-175">**Parámetro de salida**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-175">**Output Parameter**</span></span>  
     <span data-ttu-id="4f0ac-176">Indica si se trata de un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-176">Indicates if this is an output parameter.</span></span>  
  
     <span data-ttu-id="4f0ac-177">**Pasar valor NULL**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-177">**Pass Null Value**</span></span>  
     <span data-ttu-id="4f0ac-178">Pase un valor NULL como valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-178">Pass a NULL as the value of the parameter.</span></span>  
  
     <span data-ttu-id="4f0ac-179">**Valor**</span><span class="sxs-lookup"><span data-stu-id="4f0ac-179">**Value**</span></span>  
     <span data-ttu-id="4f0ac-180">Escriba el valor del parámetro cuando llame al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-180">Type the value for the parameter when calling the procedure.</span></span>  
  
5.  <span data-ttu-id="4f0ac-181">Para ejecutar el procedimiento almacenado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-181">To execute the stored procedure, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4f0ac-182">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f0ac-182">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="4f0ac-183">Para ejecutar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="4f0ac-183">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="4f0ac-184">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f0ac-184">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f0ac-185">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-185">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f0ac-186">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-186">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4f0ac-187">En este ejemplo se muestra cómo ejecutar un procedimiento almacenado que espera un parámetro.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-187">This example shows how to execute a stored procedure that expects one parameter.</span></span> <span data-ttu-id="4f0ac-188">En el ejemplo se ejecuta el procedimiento almacenado `uspGetEmployeeManagers` con el valor  `6` como parámetro `@EmployeeID` .</span><span class="sxs-lookup"><span data-stu-id="4f0ac-188">The example executes the `uspGetEmployeeManagers` stored procedure with the value  `6` specified as the `@EmployeeID` parameter.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC dbo.uspGetEmployeeManagers 6;  
GO  
```  
  
#### <a name="to-set-or-clear-a-procedure-for-executing-automatically"></a><span data-ttu-id="4f0ac-189">Para establecer o borrar un procedimiento para que se ejecute automáticamente</span><span class="sxs-lookup"><span data-stu-id="4f0ac-189">To set or clear a procedure for executing automatically</span></span>  
  
1.  <span data-ttu-id="4f0ac-190">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f0ac-190">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f0ac-191">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-191">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f0ac-192">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-192">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4f0ac-193">En este ejemplo se muestra cómo usar [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) para establecer un procedimiento de manera que se ejecute automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-193">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to set a procedure for automatic execution.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionName = ] 'startup'   
    , @OptionValue = 'on';  
```  
  
#### <a name="to-stop-a-procedure-from-executing-automatically"></a><span data-ttu-id="4f0ac-194">Para que un procedimiento deje de ejecutarse automáticamente</span><span class="sxs-lookup"><span data-stu-id="4f0ac-194">To stop a procedure from executing automatically</span></span>  
  
1.  <span data-ttu-id="4f0ac-195">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f0ac-195">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f0ac-196">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-196">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f0ac-197">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-197">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4f0ac-198">En este ejemplo se muestra cómo usar [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) para que un procedimiento deje de ejecutarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-198">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to stop a procedure from executing automatically.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionValue = 'off';  
```  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="4f0ac-199">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4f0ac-199">Example (Transact-SQL)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0ac-200">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f0ac-200">See Also</span></span>  
 <span data-ttu-id="4f0ac-201">[Especificar parámetros](specify-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="4f0ac-201">[Specify Parameters](specify-parameters.md) </span></span>  
 <span data-ttu-id="4f0ac-202">[Establecer la opción de configuración del servidor Buscar procedimientos de inicio](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="4f0ac-202">[Configure the scan for startup procs Server Configuration Option](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span></span>  
 <span data-ttu-id="4f0ac-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f0ac-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="4f0ac-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f0ac-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="4f0ac-205">Procedimientos almacenados &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4f0ac-205">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures-database-engine.md)  
  
  
