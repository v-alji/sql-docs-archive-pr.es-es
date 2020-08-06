---
title: Ver información de intercalación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], view
ms.assetid: 1338b4ea-7142-44bc-a3b9-44e54431405f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 995e559cfd7ca871f5abd90751f2f79167bdf76f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677684"
---
# <a name="view-collation-information"></a><span data-ttu-id="2bf03-102">Ver información de intercalación</span><span class="sxs-lookup"><span data-stu-id="2bf03-102">View Collation Information</span></span>
    
##  <a name="you-can-view-the-collation-of-a-server-database-or-column-in-ssmanstudiofull-using-object-explorer-menu-options-or-by-using-tsql"></a><a name="Top"></a> <span data-ttu-id="2bf03-103">Puede ver la intercalación de un servidor, una base de datos o una columna en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mediante las opciones de menú del Explorador de objetos o mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bf03-103">You can view the collation of a server, database, or column in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
##  <a name="how-to-view-a-collation-setting"></a><a name="Procedures"></a> <span data-ttu-id="2bf03-104">Cómo ver una configuración de intercalación</span><span class="sxs-lookup"><span data-stu-id="2bf03-104">How to View a Collation Setting</span></span>  
 <span data-ttu-id="2bf03-105">Puede usar cualquiera de los siguientes medios:</span><span class="sxs-lookup"><span data-stu-id="2bf03-105">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="2bf03-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2bf03-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="2bf03-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2bf03-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2bf03-108">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2bf03-108">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2bf03-109">**Para ver una configuración de intercalación de un servidor (instancia de SQL Server) en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="2bf03-109">**To view a collation setting for a server (instance of SQL Server) in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="2bf03-110">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bf03-110">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2bf03-111">Haga clic con el botón derecho en la instancia y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-111">Right-click the instance and select **Properties**.</span></span>  
  
 <span data-ttu-id="2bf03-112">**Para ver una configuración de intercalación de una base de datos en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="2bf03-112">**To view a collation setting for a database in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="2bf03-113">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="2bf03-113">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2bf03-114">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-114">Expand **Databases**, right-click the database and select **Properties**.</span></span>  
  
 <span data-ttu-id="2bf03-115">**Para ver una configuración de intercalación de una columna en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="2bf03-115">**To view a collation setting for a column in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="2bf03-116">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="2bf03-116">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2bf03-117">Expanda **Bases de datos**, la base de datos y, por último, **Tablas**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-117">Expand **Databases**, expand the database and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="2bf03-118">Expanda la tabla que contiene la columna y, a continuación, **Columnas**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-118">Expand the table that contains the column and then expand **Columns**.</span></span>  
  
4.  <span data-ttu-id="2bf03-119">Haga clic con el botón derecho en la columna y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-119">Right-click the column and select **Properties**.</span></span> <span data-ttu-id="2bf03-120">Si la propiedad collation está vacía, la columna no es un tipo de datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2bf03-120">If the collation property is empty, the column is not a character data type.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2bf03-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2bf03-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="2bf03-122">**Para ver la configuración de intercalación de un servidor**</span><span class="sxs-lookup"><span data-stu-id="2bf03-122">**To view the collation setting of a server**</span></span>  
  
1.  <span data-ttu-id="2bf03-123">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y, en la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-123">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="2bf03-124">En la ventana de consulta, escriba la siguiente instrucción que usa la función de sistema SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="2bf03-124">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, SERVERPROPERTY('collation'));  
    ```  
  
3.  <span data-ttu-id="2bf03-125">También puede usar el procedimiento almacenado del sistema sp_helpsort.</span><span class="sxs-lookup"><span data-stu-id="2bf03-125">Alternatively, you can use the sp_helpsort system stored procedure.</span></span>  
  
    ```  
    EXECUTE sp_helpsort;  
    ```  
  
 <span data-ttu-id="2bf03-126">**Para ver todas las intercalaciones admitidas por [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2bf03-126">**To view all collations supported by [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span></span>  
  
1.  <span data-ttu-id="2bf03-127">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y, en la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-127">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="2bf03-128">En la ventana de consulta, escriba la siguiente instrucción que usa la función de sistema SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="2bf03-128">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT name, description FROM sys.fn_helpcollations();  
    ```  
  
 <span data-ttu-id="2bf03-129">**Para ver la configuración de intercalación de una base de datos**</span><span class="sxs-lookup"><span data-stu-id="2bf03-129">**To view the collation setting of a database**</span></span>  
  
1.  <span data-ttu-id="2bf03-130">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y, en la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-130">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="2bf03-131">En la ventana de consulta, escriba la siguiente instrucción que usa la vista de catálogo del sistema sys.databases.</span><span class="sxs-lookup"><span data-stu-id="2bf03-131">In the query window, enter the following statement that uses the sys.databases system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.databases;  
    ```  
  
3.  <span data-ttu-id="2bf03-132">También puede usar la función del sistema DATABASEPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="2bf03-132">Alternatively, you can use the DATABASEPROPERTYEX system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, DATABASEPROPERTYEX('database_name','collation'));  
    ```  
  
 <span data-ttu-id="2bf03-133">**Para ver la configuración de intercalación de una columna**</span><span class="sxs-lookup"><span data-stu-id="2bf03-133">**To view the collation setting of a column**</span></span>  
  
1.  <span data-ttu-id="2bf03-134">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y, en la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2bf03-134">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="2bf03-135">En la ventana de consulta, escriba la siguiente instrucción que usa la vista de catálogo del sistema sys.columns.</span><span class="sxs-lookup"><span data-stu-id="2bf03-135">In the query window, enter the following statement that uses the sys.columns system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.columns WHERE name = N'<insert character data type column name>';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2bf03-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bf03-136">See Also</span></span>  
 <span data-ttu-id="2bf03-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2bf03-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="2bf03-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2bf03-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="2bf03-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2bf03-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="2bf03-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2bf03-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span></span>  
 <span data-ttu-id="2bf03-141">[Prioridad de intercalación &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2bf03-141">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 [<span data-ttu-id="2bf03-142">sp_helpsort &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf03-142">sp_helpsort &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-helpsort-transact-sql)  
  
  
