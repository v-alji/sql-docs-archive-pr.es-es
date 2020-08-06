---
title: Cambio de nombre de las columnas (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], names
- renaming columns
- column names [SQL Server]
ms.assetid: 7c71ec9f-0180-4398-b32a-4bfb7592e75d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6871ab82eaa17aa5e392e6b2bb3f5c60058f9af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675755"
---
# <a name="rename-columns-database-engine"></a><span data-ttu-id="fde07-102">Cambiar el nombre a las columnas (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="fde07-102">Rename Columns (Database Engine)</span></span>
  <span data-ttu-id="fde07-103">Puede cambiar una columna de la tabla en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fde07-103">You can rename a table column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fde07-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="fde07-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fde07-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="fde07-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fde07-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fde07-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fde07-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fde07-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fde07-108">**Para cambiar el nombre de las columnas, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="fde07-108">**To rename columns, using:**</span></span>  
  
     [<span data-ttu-id="fde07-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fde07-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fde07-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fde07-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fde07-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fde07-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fde07-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fde07-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="fde07-113">Cambiar el nombre de una columna automáticamente no cambiará las referencias a esa columna.</span><span class="sxs-lookup"><span data-stu-id="fde07-113">Renaming a column will not automatically rename references to that column.</span></span> <span data-ttu-id="fde07-114">Es necesario modificar de forma manual los objetos que hacen referencia a la columna cuyo nombre se ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="fde07-114">You must modify any objects that reference the renamed column manually.</span></span> <span data-ttu-id="fde07-115">Por ejemplo, si se cambia el nombre de una columna de una tabla y en un desencadenador existe una referencia a esa columna, es necesario modificar el desencadenador para reflejar el nuevo nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="fde07-115">For example, if you rename a table column and that column is referenced in a trigger, you must modify the trigger to reflect the new column name.</span></span> <span data-ttu-id="fde07-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) para ver las dependencias del objeto antes de cambiarle el nombre.</span><span class="sxs-lookup"><span data-stu-id="fde07-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the object before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fde07-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fde07-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fde07-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="fde07-118">Permissions</span></span>  
 <span data-ttu-id="fde07-119">Requiere el permiso ALTER en el objeto.</span><span class="sxs-lookup"><span data-stu-id="fde07-119">Requires ALTER permission on the object.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fde07-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fde07-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-column-using-object-explorer"></a><span data-ttu-id="fde07-121">Para cambiar el nombre de una columna mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="fde07-121">To rename a column using Object Explorer</span></span>  
  
1.  <span data-ttu-id="fde07-122">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fde07-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fde07-123">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla en la que quiere cambiar nombres de columnas y elija **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="fde07-123">In **Object Explorer**, right-click the table in which you want to rename columns and choose **Rename**.</span></span>  
  
3.  <span data-ttu-id="fde07-124">Escriba un nuevo nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="fde07-124">Type a new column name.</span></span>  
  
#### <a name="to-rename-a-column-using-table-designer"></a><span data-ttu-id="fde07-125">Para cambiar el nombre de una columna mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="fde07-125">To rename a column using Table Designer</span></span>  
  
1.  <span data-ttu-id="fde07-126">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla en la que quiere cambiar nombres de columnas y elija **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="fde07-126">In **Object Explorer**, right-click the table to which you want to rename columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="fde07-127">En **Nombre de columna**, seleccione el nombre que desea cambiar y escriba uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="fde07-127">Under **Column Name**, select the name you want to change and type a new one.</span></span>  
  
3.  <span data-ttu-id="fde07-128">En el menú **Archivo**, haga clic en \***Guardar**_nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="fde07-128">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fde07-129">También puede cambiar el nombre de una columna en la pestaña **Propiedades de columna** . Seleccione la columna cuyo nombre desea cambiar y escriba un nuevo valor en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="fde07-129">You can also change the name of a column in the **Column Properties** tab. Select the column whose name you want to change and type a new value for **Name**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fde07-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fde07-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="fde07-131">**Para cambiar el nombre de una columna**</span><span class="sxs-lookup"><span data-stu-id="fde07-131">**To rename a column**</span></span>  
  
#### <a name="to-rename-a-column"></a><span data-ttu-id="fde07-132">Para cambiar el nombre de una columna</span><span class="sxs-lookup"><span data-stu-id="fde07-132">To rename a column</span></span>  
  
1.  <span data-ttu-id="fde07-133">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fde07-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fde07-134">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="fde07-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fde07-135">En el siguiente ejemplo se cambia el nombre de la columna `TerritoryID` de la tabla `Sales.SalesTerritory` por `TerrID`.</span><span class="sxs-lookup"><span data-stu-id="fde07-135">The following example renames the column `TerritoryID` in the table `Sales.SalesTerritory` to `TerrID`.</span></span> <span data-ttu-id="fde07-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="fde07-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename 'Sales.SalesTerritory.TerritoryID', 'TerrID', 'COLUMN';  
    GO  
    ```  
  
 <span data-ttu-id="fde07-137">Para obtener más información, vea [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fde07-137">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
