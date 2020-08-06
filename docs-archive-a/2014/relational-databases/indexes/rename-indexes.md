---
title: Cambio de nombre de los índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- renaming indexes
- index names [SQL Server]
- indexes [SQL Server], renaming
ms.assetid: d3d612a1-ea1b-4d99-85d2-0a2ad54f4b0e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 184d6e20f7857c5ea3535e77e21a0630ffc7b678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677083"
---
# <a name="rename-indexes"></a><span data-ttu-id="5b3ee-102">Cambiar el nombre a los índices</span><span class="sxs-lookup"><span data-stu-id="5b3ee-102">Rename Indexes</span></span>
  <span data-ttu-id="5b3ee-103">En este tema se describe cómo cambiar el nombre de un índice en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b3ee-103">This topic describes how to rename an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b3ee-104">Al cambiar el nombre de un índice se reemplaza el nombre de índice actual por el nuevo nombre que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-104">Renaming an index replaces the current index name with the new name that you provide.</span></span> <span data-ttu-id="5b3ee-105">El nombre especificado debe ser único en la tabla o en la vista.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-105">The specified name must be unique within the table or view.</span></span> <span data-ttu-id="5b3ee-106">Por ejemplo, dos tablas pueden tener un índice con el nombre **XPK_1**, pero la misma tabla no puede tener dos índices con el nombre **XPK_1**.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-106">For example, two tables can have an index named **XPK_1**, but the same table cannot have two indexes named **XPK_1**.</span></span> <span data-ttu-id="5b3ee-107">No puede crear un índice con el mismo nombre que un índice existente deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-107">You cannot create an index with the same name as an existing disabled index.</span></span> <span data-ttu-id="5b3ee-108">Al cambiar el nombre de un índice no se hace que se reconstruya el índice.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-108">Renaming an index does not cause the index to be rebuilt.</span></span>  
  
 <span data-ttu-id="5b3ee-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5b3ee-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b3ee-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5b3ee-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b3ee-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5b3ee-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5b3ee-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b3ee-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b3ee-113">**Para cambiar el nombre de un índice, use:**</span><span class="sxs-lookup"><span data-stu-id="5b3ee-113">**To rename an index, using:**</span></span>  
  
     [<span data-ttu-id="5b3ee-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b3ee-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b3ee-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b3ee-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b3ee-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5b3ee-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5b3ee-117">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5b3ee-117">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5b3ee-118">Cuando cree una restricción PRIMARY KEY o UNIQUE en una tabla, se creará automáticamente un índice con el mismo nombre que la restricción para la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-118">When you create a PRIMARY KEY or UNIQUE constraint on a table, an index with the same name as the constraint is automatically created for the table.</span></span> <span data-ttu-id="5b3ee-119">Dado que los nombres de índice deben ser únicos en la tabla, no puede crear o cambiar el nombre de un índice para que tenga el mismo nombre que una restricción PRIMARY KEY o UNIQUE que ya existe en la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-119">Because index names must be unique within the table, you cannot create or rename an index to have the same name as an existing PRIMARY KEY or UNIQUE constraint on the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b3ee-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b3ee-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b3ee-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="5b3ee-121">Permissions</span></span>  
 <span data-ttu-id="5b3ee-122">Requiere el permiso ALTER en el índice.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-122">Requires ALTER permission on the index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b3ee-123">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b3ee-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-an-index-by-using-the-table-designer"></a><span data-ttu-id="5b3ee-124">Para cambiar el nombre de un índice mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="5b3ee-124">To rename an index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="5b3ee-125">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea cambiar el nombre de un índice.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-125">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="5b3ee-126">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="5b3ee-126">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5b3ee-127">Haga clic con el botón derecho en la tabla con el índice que quiera cambiar de nombre y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-127">Right-click the table on which you want to rename an index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="5b3ee-128">En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-128">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="5b3ee-129">Seleccione el índice que quiera cambiar de nombre en el cuadro de texto **Clave principal o única, o índice seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="5b3ee-129">Select the index you want to rename in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
6.  <span data-ttu-id="5b3ee-130">En la cuadrícula, haga clic en **Nombre** y escriba un nuevo nombre en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-130">In the grid, click **Name** and type a new name into the text box.</span></span>  
  
7.  <span data-ttu-id="5b3ee-131">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-131">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="5b3ee-132">En el menú **Archivo** , haga clic en **Guardar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-132">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-rename-an-index-by-using-object-explorer"></a><span data-ttu-id="5b3ee-133">Para cambiar el nombre de un índice mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="5b3ee-133">To rename an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="5b3ee-134">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea cambiar el nombre de un índice.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-134">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="5b3ee-135">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="5b3ee-135">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5b3ee-136">Haga clic en el signo más para expandir la tabla en la que desea cambiar el nombre de un índice.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-136">Click the plus sign to expand the table on which you want to rename an index.</span></span>  
  
4.  <span data-ttu-id="5b3ee-137">Haga clic en el signo más para expandir la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="5b3ee-137">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="5b3ee-138">Haga clic con el botón derecho en el índice que quiera cambiar de nombre y seleccione **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-138">Right-click the index you want to rename and select **Rename**.</span></span>  
  
6.  <span data-ttu-id="5b3ee-139">Escriba el nuevo nombre del índice y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-139">Type the index's new name and press Enter.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b3ee-140">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b3ee-140">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-an-index"></a><span data-ttu-id="5b3ee-141">Para cambiar el nombre de un índice</span><span class="sxs-lookup"><span data-stu-id="5b3ee-141">To rename an index</span></span>  
  
1.  <span data-ttu-id="5b3ee-142">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b3ee-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b3ee-143">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b3ee-144">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5b3ee-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    --Renames the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table to IX_VendorID.   
  
    EXEC sp_rename N'Purchasing.ProductVendor.IX_ProductVendor_VendorID', N'IX_VendorID', N'INDEX';   
    GO  
    ```  
  
 <span data-ttu-id="5b3ee-145">Para obtener más información, vea [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b3ee-145">For more information, see  [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
