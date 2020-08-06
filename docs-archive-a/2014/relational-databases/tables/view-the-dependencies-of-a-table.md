---
title: Ver las dependencias de una tabla | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table dependencies [SQL Server]
- dependencies [SQL Server], tables
- displaying dependences
- viewing dependencies
ms.assetid: c4351ef5-e7d0-46e7-8367-88695e9974f8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f54b913124cdaa8a7dfeebac01ba070cc37d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678118"
---
# <a name="view-the-dependencies-of-a-table"></a><span data-ttu-id="e39cc-102">Ver las dependencias de una tabla</span><span class="sxs-lookup"><span data-stu-id="e39cc-102">View the Dependencies of a Table</span></span>
  <span data-ttu-id="e39cc-103">Puede ver las dependencias de una tabla en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e39cc-103">You can view a table's dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e39cc-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="e39cc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e39cc-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e39cc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e39cc-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e39cc-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e39cc-107">**Para ver las dependencias de una tabla con:**</span><span class="sxs-lookup"><span data-stu-id="e39cc-107">**To view a table's dependencies, using:**</span></span>  
  
     [<span data-ttu-id="e39cc-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e39cc-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e39cc-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e39cc-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e39cc-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e39cc-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e39cc-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e39cc-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e39cc-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="e39cc-112">Permissions</span></span>  
 <span data-ttu-id="e39cc-113">Necesita el permiso VIEW DEFINITION en la base de datos y el permiso SELECT en sys.sql_expression_dependencies para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e39cc-113">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="e39cc-114">De forma predeterminada, solo se permite el permiso SELECT a los miembros del rol fijo de base de datos db_owner.</span><span class="sxs-lookup"><span data-stu-id="e39cc-114">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="e39cc-115">Si se conceden los permisos SELECT y VIEW DEFINITION a otro usuario, el receptor puede ver todas las dependencias de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e39cc-115">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e39cc-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e39cc-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-table"></a><span data-ttu-id="e39cc-117">Para ver las dependencias de una tabla</span><span class="sxs-lookup"><span data-stu-id="e39cc-117">To view the dependencies of a table</span></span>  
  
1.  <span data-ttu-id="e39cc-118">En el **Explorador de objetos**, expanda **Bases de datos**, expanda una base de datos y, a continuación, **Tablas**.</span><span class="sxs-lookup"><span data-stu-id="e39cc-118">In **Object Explorer**, expand **Databases**, expand a database, and then expand **Tables**.</span></span>  
  
2.  <span data-ttu-id="e39cc-119">Haga clic con el botón derecho en una tabla y, después, haga clic en **Ver dependencias**.</span><span class="sxs-lookup"><span data-stu-id="e39cc-119">Right-click a table, and then click **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="e39cc-120">En el cuadro de diálogo **Dependencias del objeto** _\<object name>_ , seleccione **Objetos que dependen de**  _\<object name>_ u **Objetos de los que depende** _\<object name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="e39cc-120">In the **Object Dependencies**_\<object name>_ dialog box, select either **Objects that depend on** _\<object name>_, or **Objects on which**_\<object name>_**depends**.</span></span>  
  
4.  <span data-ttu-id="e39cc-121">Seleccione un objeto en la cuadrícula **Dependencias** .</span><span class="sxs-lookup"><span data-stu-id="e39cc-121">Select an object in the **Dependencies** grid.</span></span> <span data-ttu-id="e39cc-122">El tipo de objeto (por ejemplo, "Desencadenador" o "Procedimiento almacenado"), aparece en el cuadro **Tipo** .</span><span class="sxs-lookup"><span data-stu-id="e39cc-122">The type of object (such as "Trigger" or "Stored Procedure"), appears in the **Type** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e39cc-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e39cc-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-objects-that-depend-on-a-table"></a><span data-ttu-id="e39cc-124">Para ver los objetos que dependen de una tabla</span><span class="sxs-lookup"><span data-stu-id="e39cc-124">To view the objects that depend on a table</span></span>  
  
1.  <span data-ttu-id="e39cc-125">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e39cc-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e39cc-126">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e39cc-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e39cc-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e39cc-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');   
    GO  
  
    ```  
  
#### <a name="to-view-the-objects-on-which-a-table-depends"></a><span data-ttu-id="e39cc-128">Para ver los objetos de los que depende una tabla</span><span class="sxs-lookup"><span data-stu-id="e39cc-128">To view the objects on which a table depends</span></span>  
  
1.  <span data-ttu-id="e39cc-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e39cc-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e39cc-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e39cc-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e39cc-131">El ejemplo siguiente devuelve los objetos que dependen de la tabla `Production.Product`.</span><span class="sxs-lookup"><span data-stu-id="e39cc-131">The following example returns the objects that depend on the table `Production.Product`.</span></span> <span data-ttu-id="e39cc-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e39cc-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referenced_id = OBJECT_ID(N'Production.Product');   
    GO  
  
    ```  
  
 <span data-ttu-id="e39cc-133">Para obtener más información, vea [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e39cc-133">For additional information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span></span>  
  
  
