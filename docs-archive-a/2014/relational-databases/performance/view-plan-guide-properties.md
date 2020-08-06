---
title: Ver propiedades de la guía de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.planguideprop.general.f1
helpviewer_keywords:
- plan guides [SQL Server], view plan guide properties
- viewing plan guide properties
ms.assetid: 8c0d2f39-59c1-4168-a649-65473f6a771b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af29c66690a43f89106c1f77aca8c3a02eff2ba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745733"
---
# <a name="view-plan-guide-properties"></a><span data-ttu-id="e77e0-102">Ver propiedades de la guía de plan</span><span class="sxs-lookup"><span data-stu-id="e77e0-102">View Plan Guide Properties</span></span>
  <span data-ttu-id="e77e0-103">Puede ver las propiedades de las guías de plan en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e77e0-103">You can view the properties of plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="e77e0-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="e77e0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e77e0-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e77e0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e77e0-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e77e0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e77e0-107">**Para ver las propiedades de las guías de plan, use:**</span><span class="sxs-lookup"><span data-stu-id="e77e0-107">**To view the properties of plan guides, using:**</span></span>  
  
     [<span data-ttu-id="e77e0-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e77e0-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e77e0-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e77e0-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e77e0-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e77e0-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e77e0-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e77e0-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e77e0-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="e77e0-112">Permissions</span></span>  
 <span data-ttu-id="e77e0-113">La visibilidad de los metadatos en las vistas de catálogo se limita a los elementos protegibles y que son propiedad de un usuario o para los que el usuario tiene algún permiso.</span><span class="sxs-lookup"><span data-stu-id="e77e0-113">The visibility of the metadata in catalog views is limited to securables that either a user owns or on which the user has been granted some permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e77e0-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e77e0-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="e77e0-115">Para ver las propiedades de una guía de plan</span><span class="sxs-lookup"><span data-stu-id="e77e0-115">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="e77e0-116">Haga clic en el signo más para expandir la base de datos en la que desea ver las propiedades de una guía de plan y haga clic en el signo más para expandir la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="e77e0-116">Click the plus sign to expand the database in which you want to view the properties of a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="e77e0-117">Haga clic en el signo más para expandir la carpeta **Guías de plan** .</span><span class="sxs-lookup"><span data-stu-id="e77e0-117">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="e77e0-118">Haga clic con el botón derecho en la guía de plan cuyas propiedades quiere ver y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e77e0-118">Right-click the plan guide of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="e77e0-119">Las propiedades siguientes se muestran en el cuadro de diálogo **Propiedades de la guía de plan** .</span><span class="sxs-lookup"><span data-stu-id="e77e0-119">The following properties show in the **Plan Guide Properties** dialog box.</span></span>  
  
     <span data-ttu-id="e77e0-120">**Sugerencias**</span><span class="sxs-lookup"><span data-stu-id="e77e0-120">**Hints**</span></span>  
     <span data-ttu-id="e77e0-121">Muestra las sugerencias de consulta o el plan de consulta que se va a aplicar a la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e77e0-121">Displays the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="e77e0-122">Cuando un plan de consulta se especifica como una sugerencia, se mostrará la salida del Plan de presentación XML.</span><span class="sxs-lookup"><span data-stu-id="e77e0-122">When a query plan is specified as a hint, the XML Showplan output for the plan is displayed.</span></span>  
  
     <span data-ttu-id="e77e0-123">**Está deshabilitado**</span><span class="sxs-lookup"><span data-stu-id="e77e0-123">**Is disabled**</span></span>  
     <span data-ttu-id="e77e0-124">Muestra el estado de la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="e77e0-124">Displays the status of the plan guide.</span></span> <span data-ttu-id="e77e0-125">Los valores posibles son **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="e77e0-125">Possible values are **True** and **False**.</span></span>  
  
     <span data-ttu-id="e77e0-126">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e77e0-126">**Name**</span></span>  
     <span data-ttu-id="e77e0-127">Muestra el nombre de la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="e77e0-127">Displays the name of the plan guide.</span></span>  
  
     <span data-ttu-id="e77e0-128">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="e77e0-128">**Parameters**</span></span>  
     <span data-ttu-id="e77e0-129">Cuando el tipo de ámbito es SQL o TEMPLATE, muestra el nombre y el tipo de dato de todos los parámetros incorporados en la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e77e0-129">When the scope type is SQL or TEMPLATE, displays the name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="e77e0-130">**Lote del ámbito**</span><span class="sxs-lookup"><span data-stu-id="e77e0-130">**Scope batch**</span></span>  
     <span data-ttu-id="e77e0-131">Muestra el texto del lote en el que aparece la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e77e0-131">Displays the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="e77e0-132">**Nombre de objeto del ámbito**</span><span class="sxs-lookup"><span data-stu-id="e77e0-132">**Scope object name**</span></span>  
     <span data-ttu-id="e77e0-133">Si el tipo de ámbito es OBJECT, muestra el nombre del procedimiento almacenado de [!INCLUDE[tsql](../../includes/tsql-md.md)] , función escalar definida por el usuario, función con valores de tabla de múltiples instrucciones o desencadenador DML en que aparece la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e77e0-133">When the scope type is OBJECT, displays the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="e77e0-134">**Nombre de esquema del ámbito**</span><span class="sxs-lookup"><span data-stu-id="e77e0-134">**Scope schema name**</span></span>  
     <span data-ttu-id="e77e0-135">Si el tipo de ámbito es OBJECT, muestra el nombre del esquema en el que está contenido el objeto.</span><span class="sxs-lookup"><span data-stu-id="e77e0-135">When the scope type is OBJECT, displays the name of the schema in which the object is contained.</span></span>  
  
     <span data-ttu-id="e77e0-136">**Tipo de ámbito**</span><span class="sxs-lookup"><span data-stu-id="e77e0-136">**Scope type**</span></span>  
     <span data-ttu-id="e77e0-137">Muestra el tipo de entidad en la que aparece la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e77e0-137">Displays the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="e77e0-138">Así se especifica el contexto para hacer coincidir la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] con la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="e77e0-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="e77e0-139">Los valores posibles son **OBJECT**, **SQL**y **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="e77e0-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
     <span data-ttu-id="e77e0-140">**Instrucción**</span><span class="sxs-lookup"><span data-stu-id="e77e0-140">**Statement**</span></span>  
     <span data-ttu-id="e77e0-141">Muestra la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] frente a la que se aplicará la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="e77e0-141">Displays the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is applied.</span></span>  
  
4.  <span data-ttu-id="e77e0-142">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e77e0-142">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e77e0-143">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e77e0-143">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="e77e0-144">Para ver las propiedades de una guía de plan</span><span class="sxs-lookup"><span data-stu-id="e77e0-144">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="e77e0-145">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e77e0-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e77e0-146">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e77e0-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e77e0-147">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e77e0-147">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- If a plan guide named "Guide1" already exists in the AdventureWorks2012 database, delete it.  
    USE AdventureWorks2012;  
    GO  
    IF OBJECT_ID(N'Guide1') IS NOT NULL  
       EXEC sp_control_plan_guide N'DROP', N'Guide1';  
    GO  
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
    GO  
    -- Gets the name, created date, and all other relevant property information on the plan guide created above.   
    SELECT name AS plan_guide_name,  
       create_date,  
       query_text,  
       scope_type_desc,  
       OBJECT_NAME(scope_object_id) AS scope_object_name,  
       scope_batch,  
       parameters,  
       hints,  
       is_disabled  
    FROM sys.plan_guides  
    WHERE name = N'Guide1';  
    GO  
    ```  
  
 <span data-ttu-id="e77e0-148">Para obtener más información, vea [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e77e0-148">For more information, see [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span></span>  
  
  
