---
title: Eliminación de un índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- dropping indexes
- indexes [SQL Server], dropping
- index deletions [SQL Server]
ms.assetid: fd38a0ed-26c4-4c76-9ef7-e0a16147329d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4552ba701782e5790f95f54c0c1c66f82573f1e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749830"
---
# <a name="delete-an-index"></a><span data-ttu-id="bf0ff-102">Eliminar un índice</span><span class="sxs-lookup"><span data-stu-id="bf0ff-102">Delete an Index</span></span>
  <span data-ttu-id="bf0ff-103">En este tema se describe cómo eliminar (quitar) un índice en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf0ff-103">This topic describes how to delete (drop) an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="bf0ff-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="bf0ff-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bf0ff-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="bf0ff-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bf0ff-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="bf0ff-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bf0ff-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="bf0ff-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bf0ff-108">**Para eliminar un índice, use:**</span><span class="sxs-lookup"><span data-stu-id="bf0ff-108">**To delete an index, using:**</span></span>  
  
     [<span data-ttu-id="bf0ff-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bf0ff-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bf0ff-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bf0ff-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bf0ff-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="bf0ff-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bf0ff-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="bf0ff-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="bf0ff-113">Los índices creados como resultado de una restricción PRIMARY KEY o UNIQUE no se pueden eliminar con este método.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-113">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be deleted by using this method.</span></span> <span data-ttu-id="bf0ff-114">En su lugar, se debe eliminar la restricción.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-114">Instead, the constraint must be deleted.</span></span> <span data-ttu-id="bf0ff-115">Para quitar la restricción y el índice correspondiente, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) con la cláusula DROP CONSTRAINT en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf0ff-115">To remove the constraint and corresponding index, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) with the DROP CONSTRAINT clause in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bf0ff-116">Para obtener más información, consulte [Delete Primary Keys](../tables/delete-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="bf0ff-116">For more information, see [Delete Primary Keys](../tables/delete-primary-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bf0ff-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="bf0ff-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bf0ff-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="bf0ff-118">Permissions</span></span>  
 <span data-ttu-id="bf0ff-119">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-119">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="bf0ff-120">Este permiso se concede de forma predeterminada al rol fijo de servidor **sysadmin** y a los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="bf0ff-120">This permission is granted by default to the **sysadmin** fixed server role and the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bf0ff-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bf0ff-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-index-by-using-object-explorer"></a><span data-ttu-id="bf0ff-122">Para eliminar un índice mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="bf0ff-122">To delete an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="bf0ff-123">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea eliminar un índice.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-123">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="bf0ff-124">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="bf0ff-124">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="bf0ff-125">Expanda la tabla que contiene el índice que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-125">Expand the table that contains the index you want to delete.</span></span>  
  
4.  <span data-ttu-id="bf0ff-126">Expanda la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="bf0ff-126">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="bf0ff-127">Haga clic con el botón derecho en el índice que quiere eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-127">Right-click the index you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="bf0ff-128">En el cuadro de diálogo **Eliminar objeto** , compruebe que el índice correcto se encuentra en la cuadrícula **Objeto que se va a eliminar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-128">In the **Delete Object** dialog box, verify that the correct index is in the **Object to be deleted** grid and click **OK**.</span></span>  
  
#### <a name="to-delete-an-index-using-table-designer"></a><span data-ttu-id="bf0ff-129">Para eliminar un índice mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="bf0ff-129">To delete an index using Table Designer</span></span>  
  
1.  <span data-ttu-id="bf0ff-130">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea eliminar un índice.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-130">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="bf0ff-131">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="bf0ff-131">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="bf0ff-132">Haga clic con el botón secundario en la tabla que contiene el índice que desee eliminar y haga clic en Diseño.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-132">Right-click the table that contains the index you want to delete and click Design.</span></span>  
  
4.  <span data-ttu-id="bf0ff-133">En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-133">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="bf0ff-134">En el cuadro de diálogo **Índices o claves** , seleccione el índice que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-134">In the **Indexes/Keys** dialog box, select the index you want to delete.</span></span>  
  
6.  <span data-ttu-id="bf0ff-135">Haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-135">Click **Delete**.</span></span>  
  
7.  <span data-ttu-id="bf0ff-136">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-136">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="bf0ff-137">En el menú **Archivo** , seleccione **Guardar**_nombre_tabla_.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-137">On the **File** menu, select **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bf0ff-138">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bf0ff-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-index"></a><span data-ttu-id="bf0ff-139">Para eliminar un índice</span><span class="sxs-lookup"><span data-stu-id="bf0ff-139">To delete an index</span></span>  
  
1.  <span data-ttu-id="bf0ff-140">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf0ff-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bf0ff-141">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bf0ff-142">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bf0ff-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- delete the IX_ProductVendor_BusinessEntityID index  
    -- from the Purchasing.ProductVendor table  
    DROP INDEX IX_ProductVendor_BusinessEntityID   
        ON Purchasing.ProductVendor;  
    GO  
    ```  
  
 <span data-ttu-id="bf0ff-143">Para obtener más información, vea [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf0ff-143">For more information, see [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span></span>  
  
  
