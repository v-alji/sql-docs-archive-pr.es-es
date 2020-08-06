---
title: Modificación de vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- views [SQL Server], modifying
- modifying views
- renaming views
ms.assetid: 2d3c14dc-43e5-4324-b8fb-f2692d330b16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10cf9ecc860d8f9b46a06ac679b0f1a8241000bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672853"
---
# <a name="modify-views"></a><span data-ttu-id="27127-102">Modificar vistas</span><span class="sxs-lookup"><span data-stu-id="27127-102">Modify Views</span></span>
  <span data-ttu-id="27127-103">Después de definir una vista, puede cambiar su definición en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sin tener que quitarla y volverla a crear si usa [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27127-103">After you define a view, you can modify its definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] without dropping and re-creating the view by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="27127-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="27127-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="27127-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="27127-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="27127-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="27127-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="27127-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="27127-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="27127-108">**Para modificar una vista, use:**</span><span class="sxs-lookup"><span data-stu-id="27127-108">**To modify a view, using:**</span></span>  
  
     [<span data-ttu-id="27127-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27127-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="27127-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27127-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="27127-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="27127-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="27127-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="27127-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="27127-113">La modificación de una vista no afecta a los objetos dependientes, como pueden ser los procedimientos almacenados o los desencadenadores, a menos que la definición de la vista cambie de tal modo que el objeto dependiente deje de ser válido.</span><span class="sxs-lookup"><span data-stu-id="27127-113">Modifying a view does not affect any dependent objects, such as stored procedures or triggers, unless the definition of the view changes in such a way that the dependent object is no longer valid.</span></span>  
  
-   <span data-ttu-id="27127-114">Si una vista que está actualmente en uso se modifica mediante ALTER VIEW, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] impone un bloqueo exclusivo de esquema sobre la vista.</span><span class="sxs-lookup"><span data-stu-id="27127-114">If a view currently used is modified by using ALTER VIEW, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes an exclusive schema lock on the view.</span></span> <span data-ttu-id="27127-115">Cuando se concede el bloqueo, y no hay usuarios activos de la vista, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] elimina todas las copias de la vista de la caché de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="27127-115">When the lock is granted, and there are no active users of the view, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] deletes all copies of the view from the procedure cache.</span></span> <span data-ttu-id="27127-116">Los planes existentes que hacen referencia a la vista permanecen en la caché, pero se vuelven a compilar cuando se llaman.</span><span class="sxs-lookup"><span data-stu-id="27127-116">Existing plans referencing the view remain in the cache but are recompiled when invoked.</span></span>  
  
-   <span data-ttu-id="27127-117">ALTER VIEW se puede aplicar a vistas indizadas; no obstante, quita incondicionalmente todos los índices de la vista.</span><span class="sxs-lookup"><span data-stu-id="27127-117">ALTER VIEW can be applied to indexed views; however, ALTER VIEW unconditionally drops all indexes on the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="27127-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="27127-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="27127-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="27127-119">Permissions</span></span>  
 <span data-ttu-id="27127-120">Para ejecutar ALTER VIEW, como mínimo, se necesita el permiso ALTER en OBJECT.</span><span class="sxs-lookup"><span data-stu-id="27127-120">To execute ALTER VIEW, at a minimum, ALTER permission on OBJECT is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="27127-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27127-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="27127-122">Para modificar una vista</span><span class="sxs-lookup"><span data-stu-id="27127-122">To modify a view</span></span>  
  
1.  <span data-ttu-id="27127-123">En el **Explorador de objetos**, haga clic en el signo más situado junto a la base de datos donde se encuentra la vista y, a continuación, haga clic en el signo más situado junto a la carpeta **Vistas** .</span><span class="sxs-lookup"><span data-stu-id="27127-123">In **Object Explorer**, click the plus sign next to the database where your view is located and then click the plus sign next to the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="27127-124">Haga clic con el botón derecho en la vista que quiere modificar y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="27127-124">Right-click on the view you wish to modify and select **Design**.</span></span>  
  
3.  <span data-ttu-id="27127-125">En el panel de diagrama del Diseñador de consultas, realice los cambios a la vista en una o más de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="27127-125">In the diagram pane of the query designer, make changes to the view in one or more of the following ways:</span></span>  
  
    1.  <span data-ttu-id="27127-126">Active o desactive las casillas de cualquier elemento que desee agregar o quitar.</span><span class="sxs-lookup"><span data-stu-id="27127-126">Select or clear the check boxes of any elements you wish to add or remove.</span></span>  
  
    2.  <span data-ttu-id="27127-127">Haga clic con el botón derecho en el panel de diagrama, seleccione **Agregar tabla** y, luego, las columnas adicionales que quiere agregar a la vista del cuadro de diálogo **Agregar tabla**.</span><span class="sxs-lookup"><span data-stu-id="27127-127">Right-click within the diagram pane, select **Add Table...**, and then select the additional columns you want to add to the view from the **Add Table** dialog box.</span></span>  
  
    3.  <span data-ttu-id="27127-128">Haga clic con el botón derecho en la barra de título de la tabla que quiere quitar y seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="27127-128">Right-click the title bar of the table you wish to remove and select **Remove**.</span></span>  
  
4.  <span data-ttu-id="27127-129">En el menú **Archivo** , haga clic en **Guardar**_view name_.</span><span class="sxs-lookup"><span data-stu-id="27127-129">On the **File** menu, click **Save**_view name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="27127-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27127-130">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="27127-131">Para modificar una vista</span><span class="sxs-lookup"><span data-stu-id="27127-131">To modify a view</span></span>  
  
1.  <span data-ttu-id="27127-132">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27127-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="27127-133">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="27127-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="27127-134">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="27127-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="27127-135">El ejemplo crea primero una vista y luego la modifica mediante ALTER VIEW.</span><span class="sxs-lookup"><span data-stu-id="27127-135">The example first creates a view and then modifies the view by using ALTER VIEW.</span></span> <span data-ttu-id="27127-136">La cláusula WHERE se agrega a la definición de la vista.</span><span class="sxs-lookup"><span data-stu-id="27127-136">A WHERE clause is added to the view definition.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    -- Create a view.  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
  
    -- Modify the view by adding a WHERE clause to limit the rows returned.  
    ALTER VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID  
    WHERE HireDate < CONVERT(DATETIME,'20020101',101) ;   
    GO  
    ```  
  
 <span data-ttu-id="27127-137">Para obtener más información, vea [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27127-137">For more information, see [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span></span>  
  
  
