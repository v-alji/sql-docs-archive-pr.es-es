---
title: Eliminación de restricciones UNIQUE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2fe2264aed4eb2f292a6bd1e4e565cebe2a833f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674695"
---
# <a name="delete-unique-constraints"></a><span data-ttu-id="c3514-102">Eliminar restricciones UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c3514-102">Delete Unique Constraints</span></span>
  <span data-ttu-id="c3514-103">Puede eliminar una restricción UNIQUE en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3514-103">You can delete a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c3514-104">Al eliminar una restricción UNIQUE, se quita el requisito de unicidad para los valores escritos en una columna o una combinación de columnas incluidas en la expresión de la restricción y se elimina el índice único correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c3514-104">Deleting a unique constraint removes the requirement for uniqueness for values entered in the column or combination of columns included in the constraint expression and deletes the corresponding unique index.</span></span>  
  
 <span data-ttu-id="c3514-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c3514-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c3514-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="c3514-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c3514-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c3514-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c3514-108">**Para eliminar una restricción UNIQUE con:**</span><span class="sxs-lookup"><span data-stu-id="c3514-108">**To delete a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="c3514-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3514-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c3514-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c3514-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c3514-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c3514-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c3514-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c3514-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c3514-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="c3514-113">Permissions</span></span>  
 <span data-ttu-id="c3514-114">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c3514-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c3514-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3514-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a><span data-ttu-id="c3514-116">Para eliminar una restricción UNIQUE mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="c3514-116">To delete a unique constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="c3514-117">En el Explorador de objetos, expanda la tabla que contiene la restricción UNIQUE y, a continuación, expanda **Restricciones**.</span><span class="sxs-lookup"><span data-stu-id="c3514-117">In Object Explorer, expand the table that contains the unique constraint and then expand **Constraints**.</span></span>  
  
2.  <span data-ttu-id="c3514-118">Haga clic con el botón derecho en la clave y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c3514-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="c3514-119">En el cuadro de diálogo **Eliminar objeto** , compruebe que se ha especificado la clave correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3514-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a><span data-ttu-id="c3514-120">Para eliminar una restricción UNIQUE mediante el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="c3514-120">To delete a unique constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="c3514-121">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla con la restricción UNIQUE y haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="c3514-121">In **Object Explorer**, right-click the table with the unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="c3514-122">En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="c3514-122">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="c3514-123">En el cuadro de diálogo **Índices o claves** , seleccione la clave UNIQUE en la lista **Clave principal o única, o índice seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="c3514-123">In the **Indexes/Keys** dialog box, select the unique key in the **Selected Primary/Unique Key and Index** list.</span></span>  
  
4.  <span data-ttu-id="c3514-124">Haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c3514-124">Click **Delete**.</span></span>  
  
5.  <span data-ttu-id="c3514-125">En el menú **Archivo**, haga clic en **Guardar** _nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="c3514-125">On the **File** menu, click **Save** _table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c3514-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c3514-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-unique-constraint"></a><span data-ttu-id="c3514-127">Para eliminar una restricción UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c3514-127">To delete a unique constraint</span></span>  
  
1.  <span data-ttu-id="c3514-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3514-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3514-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c3514-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c3514-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c3514-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="c3514-131">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) y [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c3514-131">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
