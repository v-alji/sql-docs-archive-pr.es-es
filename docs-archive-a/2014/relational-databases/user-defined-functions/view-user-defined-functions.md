---
title: Ver funciones definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.udfproperties.general.f1
- sql12.swb.functionproperties.general.f1
helpviewer_keywords:
- displaying user-defined functions
- viewing user-defined functions
- user-defined functions [SQL Server], viewing
- status information [SQL Server], user-defined functions
ms.assetid: a45dfab5-6384-4311-b935-2e23a70c5c10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5248f75540b72b489a7605b2cca34144dfcfedbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661855"
---
# <a name="view-user-defined-functions"></a><span data-ttu-id="607a1-102">Ver funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="607a1-102">View User-defined Functions</span></span>
  <span data-ttu-id="607a1-103">Puede obtener información sobre la definición o las propiedades de una función definida por el usuario en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="607a1-103">You can gain information about the definition or properties of a user-defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="607a1-104">Es posible que necesite ver la definición de la función para entender cómo se derivan sus datos de las tablas de origen o para ver los datos que ella misma define.</span><span class="sxs-lookup"><span data-stu-id="607a1-104">You may need to see the definition of the function to understand how its data is derived from the source tables or to see the data defined by the function.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="607a1-105">Si cambia el nombre de un objeto al que hace referencia una función, deberá modificar esa función para que el texto refleje el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="607a1-105">If you change the name of an object referenced by a function, you must modify that function so that its text reflects the new name.</span></span> <span data-ttu-id="607a1-106">Por tanto, antes de cambiar el nombre de un objeto, muestre primero las dependencias del objeto para determinar si alguna función va a verse afectada por el cambio propuesto.</span><span class="sxs-lookup"><span data-stu-id="607a1-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any functions are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="607a1-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="607a1-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="607a1-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="607a1-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="607a1-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="607a1-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="607a1-110">**Para obtener información acerca de una función, usando:**</span><span class="sxs-lookup"><span data-stu-id="607a1-110">**To get information about a function, using:**</span></span>  
  
     [<span data-ttu-id="607a1-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="607a1-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="607a1-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="607a1-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="607a1-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="607a1-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="607a1-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="607a1-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="607a1-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="607a1-115">Permissions</span></span>  
 <span data-ttu-id="607a1-116">El uso de **sys.sql_expression_dependencies** para buscar todas las dependencias de una función necesita el permiso VIEW DEFINITION en la base de datos y el permiso SELECT en **sys.sql_expression_dependencies** para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="607a1-116">Using **sys.sql_expression_dependencies** to find all the dependencies on a function requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="607a1-117">Las definiciones de objetos del sistema, como las que se devuelven en OBJECT_DEFINITION, son visibles de forma pública.</span><span class="sxs-lookup"><span data-stu-id="607a1-117">System object definitions, like the ones returned in OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="607a1-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="607a1-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-a-user-defined-functions-properties"></a><span data-ttu-id="607a1-119">Para mostrar las propiedades de una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="607a1-119">To show a user-defined function's properties</span></span>  
  
1.  <span data-ttu-id="607a1-120">En el **Explorador de objetos**, haga clic en el signo más situado junto a la base de datos que contiene la función cuyas propiedades desea ver y haga clic en el signo más para expandir la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="607a1-120">In **Object Explorer**, click the plus sign next to the database that contains the function to which you want to view the properties, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="607a1-121">Haga clic en el signo más para expandir la carpeta **Funciones** .</span><span class="sxs-lookup"><span data-stu-id="607a1-121">Click the plus sign to expand the **Functions** folder.</span></span>  
  
3.  <span data-ttu-id="607a1-122">Haga clic en el signo más para expandir la carpeta que contiene la función cuyas propiedades desea ver:</span><span class="sxs-lookup"><span data-stu-id="607a1-122">Click the plus sign to expand the folder that contains the function to which you want to view the properties:</span></span>  
  
    -   <span data-ttu-id="607a1-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="607a1-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="607a1-124">Función con valor escalar</span><span class="sxs-lookup"><span data-stu-id="607a1-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="607a1-125">Función de agregado</span><span class="sxs-lookup"><span data-stu-id="607a1-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="607a1-126">Haga clic con el botón derecho en la función cuyas propiedades quiere ver y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="607a1-126">Right-click the function of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="607a1-127">Las propiedades siguientes aparecen en el cuadro de diálogo **Propiedades de la función:** _nombre de función_.</span><span class="sxs-lookup"><span data-stu-id="607a1-127">The following properties appear in the **Function Properties -** _function_name_ dialog box.</span></span>  
  
     <span data-ttu-id="607a1-128">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="607a1-128">**Database**</span></span>  
     <span data-ttu-id="607a1-129">Nombre de la base de datos que contiene esta función.</span><span class="sxs-lookup"><span data-stu-id="607a1-129">The name of the database containing this function.</span></span>  
  
     <span data-ttu-id="607a1-130">**Server**</span><span class="sxs-lookup"><span data-stu-id="607a1-130">**Server**</span></span>  
     <span data-ttu-id="607a1-131">Nombre de la instancia de servidor actual.</span><span class="sxs-lookup"><span data-stu-id="607a1-131">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="607a1-132">**User**</span><span class="sxs-lookup"><span data-stu-id="607a1-132">**User**</span></span>  
     <span data-ttu-id="607a1-133">Nombre del usuario de esta conexión.</span><span class="sxs-lookup"><span data-stu-id="607a1-133">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="607a1-134">**Fecha de creación**</span><span class="sxs-lookup"><span data-stu-id="607a1-134">**Created date**</span></span>  
     <span data-ttu-id="607a1-135">Muestra la fecha de creación de la función.</span><span class="sxs-lookup"><span data-stu-id="607a1-135">Displays the date the function was created.</span></span>  
  
     <span data-ttu-id="607a1-136">**Ejecutar como**</span><span class="sxs-lookup"><span data-stu-id="607a1-136">**Execute As**</span></span>  
     <span data-ttu-id="607a1-137">Contexto de ejecución para la función.</span><span class="sxs-lookup"><span data-stu-id="607a1-137">Execution context for the function.</span></span>  
  
     <span data-ttu-id="607a1-138">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="607a1-138">**Name**</span></span>  
     <span data-ttu-id="607a1-139">Nombre de la función actual.</span><span class="sxs-lookup"><span data-stu-id="607a1-139">The name of the current function.</span></span>  
  
     <span data-ttu-id="607a1-140">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="607a1-140">**Schema**</span></span>  
     <span data-ttu-id="607a1-141">Muestra el esquema al que pertenece la función.</span><span class="sxs-lookup"><span data-stu-id="607a1-141">Displays the schema that owns the function.</span></span>  
  
     <span data-ttu-id="607a1-142">**Objeto de sistema**</span><span class="sxs-lookup"><span data-stu-id="607a1-142">**System object**</span></span>  
     <span data-ttu-id="607a1-143">Indica si la función es un objeto de sistema.</span><span class="sxs-lookup"><span data-stu-id="607a1-143">Indicates whether the function is a system object.</span></span> <span data-ttu-id="607a1-144">Los valores son True y False.</span><span class="sxs-lookup"><span data-stu-id="607a1-144">Values are True and False.</span></span>  
  
     <span data-ttu-id="607a1-145">**Valores NULL ANSI**</span><span class="sxs-lookup"><span data-stu-id="607a1-145">**ANSI NULLs**</span></span>  
     <span data-ttu-id="607a1-146">Indica si el objeto se ha creado con la opción Valores NULL ANSI.</span><span class="sxs-lookup"><span data-stu-id="607a1-146">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="607a1-147">**Cifrado**</span><span class="sxs-lookup"><span data-stu-id="607a1-147">**Encrypted**</span></span>  
     <span data-ttu-id="607a1-148">Indica si la función está cifrada.</span><span class="sxs-lookup"><span data-stu-id="607a1-148">Indicates whether the function is encrypted.</span></span> <span data-ttu-id="607a1-149">Los valores son True y False.</span><span class="sxs-lookup"><span data-stu-id="607a1-149">Values are True and False.</span></span>  
  
     <span data-ttu-id="607a1-150">**Tipo de función**</span><span class="sxs-lookup"><span data-stu-id="607a1-150">**Function Type**</span></span>  
     <span data-ttu-id="607a1-151">Tipo de la función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="607a1-151">The type of user defined function.</span></span>  
  
     <span data-ttu-id="607a1-152">**Identificador entre comillas**</span><span class="sxs-lookup"><span data-stu-id="607a1-152">**Quoted identifier**</span></span>  
     <span data-ttu-id="607a1-153">Indica si el objeto se ha creado con la opción Identificador entre comillas.</span><span class="sxs-lookup"><span data-stu-id="607a1-153">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="607a1-154">**Enlazada a un esquema**</span><span class="sxs-lookup"><span data-stu-id="607a1-154">**Schema bound**</span></span>  
     <span data-ttu-id="607a1-155">Indica si la función está enlazada a un esquema.</span><span class="sxs-lookup"><span data-stu-id="607a1-155">Indicates whether the function is schema-bound.</span></span> <span data-ttu-id="607a1-156">Los valores son True y False.</span><span class="sxs-lookup"><span data-stu-id="607a1-156">Values are True and False.</span></span> <span data-ttu-id="607a1-157">Para obtener más información sobre las funciones enlazadas a esquema, vea la sección SCHEMABINDING de [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="607a1-157">For information about schema-bound functions, see the SCHEMABINDING section of [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="607a1-158">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="607a1-158">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-function"></a><span data-ttu-id="607a1-159">Para obtener la definición y propiedades de una función</span><span class="sxs-lookup"><span data-stu-id="607a1-159">To get the definition and properties of a function</span></span>  
  
1.  <span data-ttu-id="607a1-160">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="607a1-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="607a1-161">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="607a1-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="607a1-162">Copie y pegue uno de los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="607a1-162">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the function name, definition, and relevant properties  
    SELECT sm.object_id,   
       OBJECT_NAME(sm.object_id) AS object_name,   
       o.type,   
       o.type_desc,   
       sm.definition,  
       sm.uses_ansi_nulls,  
       sm.uses_quoted_identifier,  
       sm.is_schema_bound,  
       sm.execute_as_principal_id  
    -- using the two system tables sys.sql_modules and sys.objects  
    FROM sys.sql_modules AS sm  
    JOIN sys.objects AS o ON sm.object_id = o.object_id  
    -- from the function 'dbo.ufnGetProductDealerPrice'  
    WHERE sm.object_id = OBJECT_ID('dbo.ufnGetProductDealerPrice')  
    ORDER BY o.type;  
    GO  
  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the definition of the function dbo.ufnGetProductDealerPrice  
    SELECT OBJECT_DEFINITION (OBJECT_ID('dbo.ufnGetProductDealerPrice')) AS ObjectDefinition;  
    GO  
    ```  
  
 <span data-ttu-id="607a1-163">Para obtener más información, vea [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) y [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="607a1-163">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) and [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-function"></a><span data-ttu-id="607a1-164">Para obtener las dependencias de una función</span><span class="sxs-lookup"><span data-stu-id="607a1-164">To get the dependencies of a function</span></span>  
  
1.  <span data-ttu-id="607a1-165">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="607a1-165">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="607a1-166">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="607a1-166">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="607a1-167">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="607a1-167">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get all of the dependency information  
    SELECT OBJECT_NAME(sed.referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(sed.referencing_id, sed.referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        sed.referencing_class_desc, sed.referenced_class_desc,  
        sed.referenced_server_name, sed.referenced_database_name, sed.referenced_schema_name,  
        sed.referenced_entity_name,   
        COALESCE(COL_NAME(sed.referenced_id, sed.referenced_minor_id), '(n/a)') AS referenced_column_name,  
        sed.is_caller_dependent, sed.is_ambiguous  
    -- from the two system tables sys.sql_expression_dependencies and sys.object  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    -- on the function dbo.ufnGetProductDealerPrice  
    WHERE sed.referencing_id = OBJECT_ID('dbo.ufnGetProductDealerPrice');  
    GO  
    ```  
  
 <span data-ttu-id="607a1-168">Para obtener más información, vea [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) y [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="607a1-168">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
