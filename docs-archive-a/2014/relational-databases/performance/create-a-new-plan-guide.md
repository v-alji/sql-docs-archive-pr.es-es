---
title: Creación de una nueva guía de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.designer.newplanguide.f1
helpviewer_keywords:
- creating plan guides
- plan guides [SQL Server]. creating
ms.assetid: e1ad78bb-4857-40ea-a0c6-dcf5c28aef2f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60ba31e2a63575a316db5befb397bea59c0ad1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677610"
---
# <a name="create-a-new-plan-guide"></a><span data-ttu-id="fcc90-102">Crear una nueva guía de plan</span><span class="sxs-lookup"><span data-stu-id="fcc90-102">Create a New Plan Guide</span></span>
  <span data-ttu-id="fcc90-103">Puede crear una guía de plan en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcc90-103">You can create a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fcc90-104">Las guías de plan influyen en la optimización de las consultas adjuntando sugerencias de consulta o un plan de consulta fijo.</span><span class="sxs-lookup"><span data-stu-id="fcc90-104">Plan guides influence query optimization by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="fcc90-105">En la guía de plan, se especifica la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] que se desea optimizar y además una cláusula OPTION que incluye las sugerencias de consulta que se desean utilizar o un plan de consulta específico con el que desea optimizar la consulta.</span><span class="sxs-lookup"><span data-stu-id="fcc90-105">In the plan guide, you specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="fcc90-106">Cuando la consulta se ejecuta, el optimizador de consultas hace coincidir la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] con la guía de plan y además asocia en tiempo de ejecución la cláusula OPTION a la consulta o utiliza el plan de consulta especificado.</span><span class="sxs-lookup"><span data-stu-id="fcc90-106">When the query executes, the query optimizer matches the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide and either attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="fcc90-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="fcc90-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fcc90-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="fcc90-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fcc90-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fcc90-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fcc90-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fcc90-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fcc90-111">**Para crear una guía de plan, use:**</span><span class="sxs-lookup"><span data-stu-id="fcc90-111">**To create a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="fcc90-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fcc90-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fcc90-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fcc90-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fcc90-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fcc90-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fcc90-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fcc90-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fcc90-116">Los argumentos de sp_create_plan_guide deben indicarse en el orden que se muestra.</span><span class="sxs-lookup"><span data-stu-id="fcc90-116">The arguments to sp_create_plan_guide must be provided in the order that is shown.</span></span> <span data-ttu-id="fcc90-117">Cuando se incluyen valores para los parámetros de `sp_create_plan_guide`, deben especificarse todos los nombres de parámetro de forma explícita, o bien no especificarse ninguno.</span><span class="sxs-lookup"><span data-stu-id="fcc90-117">When you supply values for the parameters of `sp_create_plan_guide`, all parameter names must be specified explicitly, or none at all.</span></span> <span data-ttu-id="fcc90-118">Por ejemplo, si se especifica `@name =`, también deben especificarse `@stmt =` , `@type =`, etc.</span><span class="sxs-lookup"><span data-stu-id="fcc90-118">For example, if `@name =` is specified, then `@stmt =` , `@type =`, and so on, must also be specified.</span></span> <span data-ttu-id="fcc90-119">Del mismo modo, si se omite `@name =` y solo se indica el valor del parámetro, también deben omitirse los demás nombres de parámetro y solo se indicará su valor.</span><span class="sxs-lookup"><span data-stu-id="fcc90-119">Likewise, if `@name =` is omitted and only the parameter value is provided, the remaining parameter names must also be omitted, and only their values provided.</span></span> <span data-ttu-id="fcc90-120">Los nombres de argumento solo se incluyen con fines de descripción, para ayudar a entender la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="fcc90-120">Argument names are for descriptive purposes only, to help understand the syntax.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fcc90-121">no comprueba si el nombre del parámetro especificado coincide con el nombre del parámetro en la posición donde se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fcc90-121">does not verify that the specified parameter name matches the name for the parameter in the position where the name is used.</span></span>  
  
-   <span data-ttu-id="fcc90-122">Puede crearse más de una guía de plan OBJECT o SQL para la misma consulta y lote o módulo.</span><span class="sxs-lookup"><span data-stu-id="fcc90-122">You can create more than one OBJECT or SQL plan guide for the same query and batch or module.</span></span> <span data-ttu-id="fcc90-123">Sin embargo, en un momento dado, solo puede estar habilitada una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="fcc90-123">However, only one plan guide can be enabled at any given time.</span></span>  
  
-   <span data-ttu-id="fcc90-124">No se pueden crear guías de plan de tipo OBJECT para un valor @module_or_batch que hace referencia a un procedimiento almacenado, una función o un desencadenador DML que especifica la cláusula WITH ENCRYPTION o que es temporal.</span><span class="sxs-lookup"><span data-stu-id="fcc90-124">Plan guides of type OBJECT cannot be created for an @module_or_batch value that references a stored procedure, function, or DML trigger that specifies the WITH ENCRYPTION clause or that is temporary.</span></span>  
  
-   <span data-ttu-id="fcc90-125">Se producirá un error si se intenta quitar o modificar una función, procedimiento almacenado o desencadenador DML al que una guía de plan, habilitada o deshabilitada, haga referencia.</span><span class="sxs-lookup"><span data-stu-id="fcc90-125">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="fcc90-126">También se producirá un error si se intenta quitar una tabla que tenga definido un desencadenador al que haga referencia una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="fcc90-126">Trying to drop a table that has a trigger defined on it that is referenced by a plan guide also causes an error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fcc90-127">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fcc90-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fcc90-128">Permisos</span><span class="sxs-lookup"><span data-stu-id="fcc90-128">Permissions</span></span>  
 <span data-ttu-id="fcc90-129">Para crear una guía de plan de tipo OBJECT se requiere el permiso ALTER en el objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="fcc90-129">To create a plan guide of type OBJECT, requires ALTER permission on the referenced object.</span></span> <span data-ttu-id="fcc90-130">Para crear una guía de plan de tipo SQL o TEMPLATE, se requiere el permiso ALTER en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="fcc90-130">To create a plan guide of type SQL or TEMPLATE, requires ALTER permission on the current database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fcc90-131">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fcc90-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="fcc90-132">Para crear una guía de plan</span><span class="sxs-lookup"><span data-stu-id="fcc90-132">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="fcc90-133">Haga clic en el signo más para expandir la base de datos en la que desea crear una guía de plan y, a continuación, haga clic en el signo más para expandir la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="fcc90-133">Click the plus sign to expand the database in which you want to create a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="fcc90-134">Haga clic con el botón derecho en la carpeta **guías de plan** y seleccione **nueva guía de plan.**...</span><span class="sxs-lookup"><span data-stu-id="fcc90-134">Right-click the **Plan Guides** folder and select **New Plan Guide...**.</span></span>  
  
3.  <span data-ttu-id="fcc90-135">En el cuadro de diálogo **Nueva guía de plan** , en el cuadro **Nombre** , escriba el nombre de la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="fcc90-135">In the **New Plan Guide** dialog box, in the **Name** box, enter the name of the plan guide.</span></span>  
  
4.  <span data-ttu-id="fcc90-136">En el cuadro **Instrucción** , escriba la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] con la que se aplicará la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="fcc90-136">In the **Statement** box, enter the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is to be applied.</span></span>  
  
5.  <span data-ttu-id="fcc90-137">En la lista **Tipo de ámbito** , seleccione el tipo de entidad en el que aparecerá la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcc90-137">In the **Scope type** list, select the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="fcc90-138">Así se especifica el contexto para hacer coincidir la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] con la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="fcc90-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="fcc90-139">Los valores posibles son **OBJECT**, **SQL**y **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="fcc90-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
6.  <span data-ttu-id="fcc90-140">En el cuadro **Lote de ámbito** , escriba el texto del lote en el que aparecerá la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcc90-140">In the **Scope batch** box, enter the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="fcc90-141">El texto del lote no puede incluir una instrucción USE\`\`*database* .</span><span class="sxs-lookup"><span data-stu-id="fcc90-141">The batch text cannot include a USE\`\`*database* statement.</span></span> <span data-ttu-id="fcc90-142">El cuadro **Lote de ámbito** solo está disponible cuando **SQL** se ha seleccionado como tipo de ámbito.</span><span class="sxs-lookup"><span data-stu-id="fcc90-142">The **Scope batch** box is only available when **SQL** is selected as a scope type.</span></span> <span data-ttu-id="fcc90-143">Si no escribe nada en el cuadro Lote de ámbito cuando SQL es el tipo de ámbito, el valor del texto del lote se establece en el mismo valor que está en el cuadro **Instrucción** .</span><span class="sxs-lookup"><span data-stu-id="fcc90-143">If nothing is entered in the scope batch box when SQL is the scope type, then the value of the batch text is set to the same value as is in the **Statement** box.</span></span>  
  
7.  <span data-ttu-id="fcc90-144">En la lista **Nombre de esquema de ámbito** , escriba el nombre del esquema en el que está contenido el objeto.</span><span class="sxs-lookup"><span data-stu-id="fcc90-144">In the **Scope schema name** list, enter the name of the schema in which the object is contained.</span></span> <span data-ttu-id="fcc90-145">El cuadro **Nombre de esquema de ámbito** solo está disponible cuando se ha seleccionado **Objeto** como tipo de ámbito.</span><span class="sxs-lookup"><span data-stu-id="fcc90-145">The **Scope schema name** box is only available when **Object** is selected as a scope type.</span></span>  
  
8.  <span data-ttu-id="fcc90-146">En el cuadro **Nombre de objeto de ámbito** , escriba el nombre del procedimiento almacenado [!INCLUDE[tsql](../../includes/tsql-md.md)] , la función escalar definida por el usuario, la función con valores de tabla de múltiples instrucciones o el desencadenador DML en el que aparece la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcc90-146">In the **Scope object name** box, enter the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="fcc90-147">El cuadro **Nombre de objeto de ámbito** solo está disponible cuando se ha seleccionado **Objeto** como tipo de ámbito.</span><span class="sxs-lookup"><span data-stu-id="fcc90-147">The **Scope object name** box is only available when **Object** is selected as a scope type.</span></span>  
  
9. <span data-ttu-id="fcc90-148">En el cuadro **Parámetros** , escriba el nombre de parámetro y el tipo de datos de todos los parámetros incrustados en la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcc90-148">In the **Parameters** box, enter the parameter name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="fcc90-149">Solo se aplican los parámetros si se da una de las dos siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="fcc90-149">Parameters apply only when either of the following is true:</span></span>  
  
    -   <span data-ttu-id="fcc90-150">El tipo de ámbito es **SQL** o **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="fcc90-150">The scope type is **SQL** or **TEMPLATE**.</span></span> <span data-ttu-id="fcc90-151">Si es **TEMPLATE**, los parámetros no deben ser NULL.</span><span class="sxs-lookup"><span data-stu-id="fcc90-151">If **TEMPLATE**, parameters must not be NULL.</span></span>  
  
    -   <span data-ttu-id="fcc90-152">La instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] se envía mediante sp_executesql y se especifica un valor para el parámetro, o bien [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] envía internamente una instrucción después del proceso de parametrización.</span><span class="sxs-lookup"><span data-stu-id="fcc90-152">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is submitted by using sp_executesql and a value for the parameter is specified, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internally submits a statement after parameterizing it.</span></span>  
  
10. <span data-ttu-id="fcc90-153">En el cuadro **Sugerencias** , escriba las sugerencias de consulta o el plan de consulta que se va a aplicar a la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcc90-153">In the **Hints** box, enter the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="fcc90-154">Para especificar una o varias sugerencias de consulta, escriba una cláusula OPTION válida.</span><span class="sxs-lookup"><span data-stu-id="fcc90-154">To specify one or more query hints, enter a valid OPTION clause.</span></span>  
  
11. <span data-ttu-id="fcc90-155">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcc90-155">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fcc90-156">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fcc90-156">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="fcc90-157">Para crear una guía de plan</span><span class="sxs-lookup"><span data-stu-id="fcc90-157">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="fcc90-158">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcc90-158">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fcc90-159">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="fcc90-159">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fcc90-160">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="fcc90-160">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a plan guide named Guide1 based on a SQL statement  
    EXEC sp_create_plan_guide   
        @name = N'Guide1',   
        @stmt = N'SELECT TOP 1 *   
                  FROM Sales.SalesOrderHeader   
                  ORDER BY OrderDate DESC',   
        @type = N'SQL',  
        @module_or_batch = NULL,   
        @params = NULL,   
        @hints = N'OPTION (MAXDOP 1)';  
  
    ```  
  
 <span data-ttu-id="fcc90-161">Para obtener más información, vea [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fcc90-161">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span></span>  
  
  
