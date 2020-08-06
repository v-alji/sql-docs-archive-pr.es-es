---
title: Eliminación de restricciones CHECK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- CHECK constraints, deleting
- constraints [SQL Server], deleting
- constraints [SQL Server], check
- deleting constraints
ms.assetid: 5f86c1a6-f5fa-4e77-a892-f6ae96fc0ab3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28a7f72993cbf2ed0a8cc76534380090ef0d0a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672871"
---
# <a name="delete-check-constraints"></a><span data-ttu-id="16047-102">Eliminar restricciones CHECK</span><span class="sxs-lookup"><span data-stu-id="16047-102">Delete Check Constraints</span></span>
  <span data-ttu-id="16047-103">Puede eliminar una restricción CHECK en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16047-103">You can delete a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="16047-104">Al eliminar las restricciones CHECK se quitan las limitaciones de los valores de datos que se admiten en las columnas incluidas en la expresión de restricción.</span><span class="sxs-lookup"><span data-stu-id="16047-104">Deleting check constraints removes the limitations on data values that are accepted in the column or columns included in the constraint expression.</span></span>  
  
 <span data-ttu-id="16047-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="16047-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="16047-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="16047-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="16047-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="16047-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="16047-108">**Para eliminar una restricción CHECK con:**</span><span class="sxs-lookup"><span data-stu-id="16047-108">**To delete a check constraint, using:**</span></span>  
  
     [<span data-ttu-id="16047-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16047-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="16047-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16047-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="16047-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="16047-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="16047-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="16047-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="16047-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="16047-113">Permissions</span></span>  
 <span data-ttu-id="16047-114">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="16047-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="16047-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16047-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="16047-116">Para eliminar una restricción CHECK</span><span class="sxs-lookup"><span data-stu-id="16047-116">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="16047-117">En el **Explorador de objetos**, expanda la tabla con la restricción CHECK.</span><span class="sxs-lookup"><span data-stu-id="16047-117">In **Object Explorer**, expand the table with the check constraint.</span></span>  
  
2.  <span data-ttu-id="16047-118">Expanda  **Restricciones**.</span><span class="sxs-lookup"><span data-stu-id="16047-118">Expand  **Constraints**.</span></span>  
  
3.  <span data-ttu-id="16047-119">Haga clic con el botón derecho en la restricción y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="16047-119">Right-click the constraint and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="16047-120">En el cuadro de diálogo **Eliminar objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="16047-120">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="16047-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16047-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="16047-122">Para eliminar una restricción CHECK</span><span class="sxs-lookup"><span data-stu-id="16047-122">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="16047-123">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16047-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="16047-124">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="16047-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="16047-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="16047-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT CHK_ColumnD_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="16047-126">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="16047-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
