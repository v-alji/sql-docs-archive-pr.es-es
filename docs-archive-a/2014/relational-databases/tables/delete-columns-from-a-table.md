---
title: Eliminación de columnas desde una tabla (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], deleting
- removing columns
- deleting columns
- dropping columns
ms.assetid: 0d8f6e4f-bc71-4fa3-8615-74249c8e072d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 62f9bca8ee53ae97bb1ac7f37e597b7814a0c370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674027"
---
# <a name="delete-columns-from-a-table"></a><span data-ttu-id="4c3a3-102">Eliminar columnas de una tabla</span><span class="sxs-lookup"><span data-stu-id="4c3a3-102">Delete Columns from a Table</span></span>
  <span data-ttu-id="4c3a3-103">En este tema se describe cómo eliminar columnas de tabla en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3a3-103">This topic describes how to delete table columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4c3a3-104">Cuando se elimina una columna de una tabla, dicha columna y todos los datos que contiene se eliminan de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-104">When you delete a column from a table, it and all the data it contains are deleted from the database.</span></span> <span data-ttu-id="4c3a3-105">Esta operación no se puede deshacer.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-105">This action cannot be undone.</span></span>  
  
 <span data-ttu-id="4c3a3-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4c3a3-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4c3a3-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4c3a3-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4c3a3-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4c3a3-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4c3a3-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4c3a3-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4c3a3-110">**Para eliminar una columna de una tabla con:**</span><span class="sxs-lookup"><span data-stu-id="4c3a3-110">**To delete a column from a table, using:**</span></span>  
  
     [<span data-ttu-id="4c3a3-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c3a3-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4c3a3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c3a3-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c3a3-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4c3a3-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4c3a3-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4c3a3-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4c3a3-115">No puede eliminar una columna que tenga una restricción CHECK.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-115">You cannot delete a column that has a CHECK constraint.</span></span> <span data-ttu-id="4c3a3-116">Primero debe eliminar la restricción.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-116">You must first delete the constraint.</span></span>  
  
 <span data-ttu-id="4c3a3-117">No puede eliminar una columna que tiene restricciones PRIMARY KEY o FOREIGN KEY u otras dependencias excepto si usa el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-117">You cannot delete a column that has PRIMARY KEY or FOREIGN KEY constraints or other dependencies except when using the Table Designer.</span></span> <span data-ttu-id="4c3a3-118">Al utilizar el Explorador de objetos o [!INCLUDE[tsql](../../includes/tsql-md.md)], primero debe quitar todas las dependencias de la columna.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-118">When using Object Explorer or [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first remove all dependencies on the column.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c3a3-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4c3a3-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c3a3-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="4c3a3-120">Permissions</span></span>  
 <span data-ttu-id="4c3a3-121">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4c3a3-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c3a3-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-columns-by-using-object-explorer"></a><span data-ttu-id="4c3a3-123">Para eliminar columnas mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="4c3a3-123">To delete columns by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="4c3a3-124">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3a3-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c3a3-125">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla de la que quiere eliminar columnas y elija **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-125">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Delete**.</span></span>  
  
3.  <span data-ttu-id="4c3a3-126">En el cuadro de diálogo **Eliminar objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-126">In **Delete Object** dialog box, click **OK**.</span></span>  
  
 <span data-ttu-id="4c3a3-127">Si la columna contiene restricciones u otras dependencias, aparecerá un mensaje de error en el cuadro de diálogo **Eliminar objeto** .</span><span class="sxs-lookup"><span data-stu-id="4c3a3-127">If the column contains constraints or other dependencies, an error message will display in the **Delete Object** dialog box.</span></span> <span data-ttu-id="4c3a3-128">Resuelva el error eliminando las restricciones a las que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-128">Resolve the error by deleting the referenced constraints.</span></span>  
  
#### <a name="to-delete-columns-by-using-table-designer"></a><span data-ttu-id="4c3a3-129">Para eliminar columnas mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="4c3a3-129">To delete columns by using Table Designer</span></span>  
  
1.  <span data-ttu-id="4c3a3-130">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla de la que quiere eliminar columnas y elija **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-130">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="4c3a3-131">Haga clic con el botón derecho en la columna que quiera eliminar y elija **Eliminar columna** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-131">Right-click the column you want to delete and choose **Delete Column** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="4c3a3-132">Si la columna participa en una relación (FOREIGN KEY o PRIMARY KEY), un cuadro de mensaje le pedirá que confirme la eliminación de las columnas seleccionadas y sus relaciones.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-132">If the column participates in a relationship (FOREIGN KEY or PRIMARY KEY), a message prompts you to confirm the deletion of the selected columns and their relationships.</span></span> <span data-ttu-id="4c3a3-133">Elija **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-133">Choose **Yes**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4c3a3-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c3a3-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-columns"></a><span data-ttu-id="4c3a3-135">Para eliminar columnas</span><span class="sxs-lookup"><span data-stu-id="4c3a3-135">To delete columns</span></span>  
  
1.  <span data-ttu-id="4c3a3-136">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3a3-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c3a3-137">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c3a3-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.doc_exb DROP COLUMN column_b ;  
    ```  
  
 <span data-ttu-id="4c3a3-139">Si la columna contiene restricciones u otras dependencias, se devolverá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-139">If the column contains constraints or other dependencies, an error message will be returned.</span></span> <span data-ttu-id="4c3a3-140">Resuelva el error eliminando las restricciones a las que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4c3a3-140">Resolve the error by deleting the referenced constraints.</span></span>  
  
 <span data-ttu-id="4c3a3-141">Para obtener otros ejemplos, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4c3a3-141">For additional examples, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
##  <a name="FollowUp"></a>  
