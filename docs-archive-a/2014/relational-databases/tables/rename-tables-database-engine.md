---
title: Cambio de nombre de las tablas (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table renaming [SQL Server]
- table names [SQL Server]
- tables [SQL Server], Visual Database Tools
- renaming tables
ms.assetid: 2f5c922d-4d71-4694-9fca-28dd99375799
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e73bbb92d8fd3fdcaa7756ce1dcb74d8cd598b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675752"
---
# <a name="rename-tables-database-engine"></a><span data-ttu-id="4dfd3-102">Cambiar el nombre a las tablas (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="4dfd3-102">Rename Tables (Database Engine)</span></span>
  <span data-ttu-id="4dfd3-103">Puede cambiar el nombre de una tabla en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dfd3-103">You can rename a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4dfd3-104">Piénselo bien antes de cambiar el nombre de una tabla.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-104">Think carefully before you rename a table.</span></span> <span data-ttu-id="4dfd3-105">Si las consultas, vistas, funciones definidas por el usuario, procedimientos almacenados o programas existentes hacen referencia a esta tabla, la modificación del nombre hará que estos objetos dejen de ser válidos.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="4dfd3-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4dfd3-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4dfd3-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4dfd3-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4dfd3-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4dfd3-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4dfd3-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4dfd3-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4dfd3-110">**Para cambiar el nombre de una tabla con:**</span><span class="sxs-lookup"><span data-stu-id="4dfd3-110">**To rename a table, using:**</span></span>  
  
     [<span data-ttu-id="4dfd3-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4dfd3-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4dfd3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4dfd3-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4dfd3-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4dfd3-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4dfd3-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4dfd3-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4dfd3-115">Cambiar el nombre de una tabla automáticamente no cambiará las referencias a esa tabla.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-115">Renaming a table will not automatically rename references to that table.</span></span> <span data-ttu-id="4dfd3-116">Es necesario modificar de forma manual los objetos que hacen referencia a la tabla cuyo nombre se ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-116">You must manually modify any objects that reference the renamed table.</span></span> <span data-ttu-id="4dfd3-117">Por ejemplo, si se cambia el nombre de una tabla y en un desencadenador existe una referencia a esa tabla, es necesario modificar el desencadenador para reflejar el nuevo nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-117">For example, if you rename a table and that table is referenced in a trigger, you must modify the trigger to reflect the new table name.</span></span> <span data-ttu-id="4dfd3-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) para enumerar las dependencias de la tabla antes de cambiarle el nombre.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the table before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4dfd3-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4dfd3-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4dfd3-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="4dfd3-120">Permissions</span></span>  
 <span data-ttu-id="4dfd3-121">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4dfd3-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4dfd3-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="4dfd3-123">Para cambiar el nombre de una tabla</span><span class="sxs-lookup"><span data-stu-id="4dfd3-123">To rename a table</span></span>  
  
1.  <span data-ttu-id="4dfd3-124">En el Explorador de objetos, haga clic con el botón derecho en la tabla cuyo nombre quiere cambiar y seleccione **Diseño** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-124">In Object Explorer, right-click the table you want to rename and choose **Design** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4dfd3-125">En el menú **Ver** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-125">From the **View** menu, choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="4dfd3-126">En el campo del valor **Nombre** de la ventana **Propiedades** , escriba un nuevo nombre para la tabla.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-126">In the field for the **Name** value in the **Properties** window, type a new name for the table.</span></span>  
  
4.  <span data-ttu-id="4dfd3-127">Para cancelar esta acción, presione la tecla ESC antes de salir del campo.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-127">To cancel this action, press the ESC key before leaving this field.</span></span>  
  
5.  <span data-ttu-id="4dfd3-128">En el menú **archivo** , elija **Guardar**_nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-128">From the **File** menu choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4dfd3-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4dfd3-129">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="4dfd3-130">Para cambiar el nombre de una tabla</span><span class="sxs-lookup"><span data-stu-id="4dfd3-130">To rename a table</span></span>  
  
1.  <span data-ttu-id="4dfd3-131">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dfd3-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4dfd3-132">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4dfd3-133">En el siguiente ejemplo se cambia el nombre de la tabla `SalesTerritory` por `SalesTerr` en el esquema `Sales` .</span><span class="sxs-lookup"><span data-stu-id="4dfd3-133">The following example renames the `SalesTerritory` table to `SalesTerr` in the `Sales` schema.</span></span> <span data-ttu-id="4dfd3-134">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    EXEC sp_rename 'Sales.SalesTerritory', 'SalesTerr';  
    ```  
  
 <span data-ttu-id="4dfd3-135">Para ver otros ejemplos, vea [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4dfd3-135">For additional examples, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
