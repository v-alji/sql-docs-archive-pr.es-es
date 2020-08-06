---
title: Eliminación de claves principales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing primary keys
- deleting primary keys
- primary keys [SQL Server], deleting
ms.assetid: c472e465-7bdd-4d74-8fc9-e47fca007ccb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 44fa1271143f813364bfd2109f8147f1d04294a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678124"
---
# <a name="delete-primary-keys"></a><span data-ttu-id="21c36-102">Eliminar claves principales</span><span class="sxs-lookup"><span data-stu-id="21c36-102">Delete Primary Keys</span></span>
  <span data-ttu-id="21c36-103">Puede eliminar (quitar) una clave principal en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21c36-103">You can delete (drop) a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="21c36-104">Cuando se elimina la clave principal, se elimina el índice correspondiente.</span><span class="sxs-lookup"><span data-stu-id="21c36-104">When the primary key is deleted, the corresponding index is deleted.</span></span>  
  
 <span data-ttu-id="21c36-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="21c36-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="21c36-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="21c36-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="21c36-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="21c36-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="21c36-108">**Para eliminar una clave principal con:**</span><span class="sxs-lookup"><span data-stu-id="21c36-108">**To delete a primary key using:**</span></span>  
  
     [<span data-ttu-id="21c36-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="21c36-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="21c36-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="21c36-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="21c36-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="21c36-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="21c36-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="21c36-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="21c36-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="21c36-113">Permissions</span></span>  
 <span data-ttu-id="21c36-114">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="21c36-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="21c36-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="21c36-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-object-explorer"></a><span data-ttu-id="21c36-116">Para eliminar una restricción de clave principal mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="21c36-116">To delete a primary key constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="21c36-117">En el Explorador de objetos, expanda la tabla que contiene la clave principal y, a continuación, expanda **Claves**.</span><span class="sxs-lookup"><span data-stu-id="21c36-117">In Object Explorer, expand the table that contains the primary key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="21c36-118">Haga clic con el botón derecho en la clave y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="21c36-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="21c36-119">En el cuadro de diálogo **Eliminar objeto** , compruebe que se ha especificado la clave correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21c36-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-table-designer"></a><span data-ttu-id="21c36-120">Para eliminar una restricción de clave principal mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="21c36-120">To delete a primary key constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="21c36-121">En el Explorador de objetos, haga clic con el botón derecho en la tabla con la clave principal y, después, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="21c36-121">In Object Explorer, right-click the table with the primary key, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="21c36-122">En la cuadrícula de la tabla, haga clic con el botón derecho en la fila que contiene la clave principal y elija **Quitar clave principal** para desactivar el valor.</span><span class="sxs-lookup"><span data-stu-id="21c36-122">In the table grid, right-click the row with the primary key and choose **Remove Primary Key** to toggle the setting from on to off.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="21c36-123">Para deshacer esta acción, cierre la tabla sin guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="21c36-123">To undo this action, close the table without saving the changes.</span></span> <span data-ttu-id="21c36-124">Si se elimina una clave principal, no se podrá deshacer la acción sin perder todos los demás cambios realizados en la tabla.</span><span class="sxs-lookup"><span data-stu-id="21c36-124">Deleting a primary key cannot be undone without losing all other changes made to the table.</span></span>  
  
3.  <span data-ttu-id="21c36-125">En el menú **Archivo** , haga clic en **Guardar**_table name_.</span><span class="sxs-lookup"><span data-stu-id="21c36-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="21c36-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="21c36-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint"></a><span data-ttu-id="21c36-127">Para eliminar una restricción PRIMARY KEY</span><span class="sxs-lookup"><span data-stu-id="21c36-127">To delete a primary key constraint</span></span>  
  
1.  <span data-ttu-id="21c36-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21c36-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="21c36-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="21c36-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="21c36-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="21c36-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="21c36-131">El ejemplo primero identifica el nombre de la restricción de clave principal y luego elimina la restricción.</span><span class="sxs-lookup"><span data-stu-id="21c36-131">The example first identifies the name of the primary key constraint and then deletes the constraint.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Return the name of primary key.  
    SELECT name  
    FROM sys.key_constraints  
    WHERE type = 'PK' AND OBJECT_NAME(parent_object_id) = N'TransactionHistoryArchive';  
    GO  
    -- Delete the primary key constraint.  
    ALTER TABLE Production.TransactionHistoryArchive  
    DROP CONSTRAINT PK_TransactionHistoryArchive_TransactionID;   
    GO  
    ```  
  
 <span data-ttu-id="21c36-132">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) y [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21c36-132">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span></span>  
  
###  <a name="TsqlExample"></a>  
