---
title: Eliminación de vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- dropping views
- deleting views
- views [SQL Server], deleting
- removing views
ms.assetid: 6823c7f8-06ca-4bda-8482-7092f03d52a0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3e05724f7d6384d0407e915207ad60a1cdfb01b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662731"
---
# <a name="delete-views"></a><span data-ttu-id="c3091-102">Eliminar vistas</span><span class="sxs-lookup"><span data-stu-id="c3091-102">Delete Views</span></span>
  <span data-ttu-id="c3091-103">Puede eliminar (quitar) vistas de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3091-103">You can delete (drop) views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c3091-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c3091-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c3091-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c3091-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c3091-106">Cuando se quita una vista, la definición y otra información de la vista se elimina del catálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c3091-106">When you drop a view, the definition of the view and other information about the view is deleted from the system catalog.</span></span> <span data-ttu-id="c3091-107">También se eliminan todos los permisos de la vista.</span><span class="sxs-lookup"><span data-stu-id="c3091-107">All permissions for the view are also deleted.</span></span>  
  
-   <span data-ttu-id="c3091-108">Las vistas de una tabla que se ha quitado mediante `DROP TABLE` se deben quitar explícitamente con `DROP VIEW`.</span><span class="sxs-lookup"><span data-stu-id="c3091-108">Any view on a table that is dropped by using `DROP TABLE` must be dropped explicitly by using `DROP VIEW`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c3091-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c3091-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c3091-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="c3091-110">Permissions</span></span>  
 <span data-ttu-id="c3091-111">Se necesita el permiso ALTER en SCHEMA o el permiso CONTROL en OBJECT.</span><span class="sxs-lookup"><span data-stu-id="c3091-111">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c3091-112">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3091-112">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="c3091-113">Para eliminar una vista de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c3091-113">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="c3091-114">En el **Explorador de objetos**, expanda la base de datos que contiene la vista que desea eliminar y, a continuación, expanda la carpeta **Vistas** .</span><span class="sxs-lookup"><span data-stu-id="c3091-114">In **Object Explorer**, expand the database that contains the view you want to delete, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="c3091-115">Haga clic con el botón derecho en la vista que quiere eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c3091-115">Right-click the view you want to delete and click **Delete**.</span></span>  
  
3.  <span data-ttu-id="c3091-116">En el cuadro de diálogo **Eliminar objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3091-116">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c3091-117">Haga clic en **Mostrar dependencias** en el cuadro de diálogo **Eliminar objeto** para abrir el cuadro de diálogo **Dependencias** de _view_name_.</span><span class="sxs-lookup"><span data-stu-id="c3091-117">Click **Show Dependencies** in the **Delete Object** dialog box to open the _view_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="c3091-118">Esto mostrará todos los objetos que dependen de la vista y todos los objetos de los que depende la vista.</span><span class="sxs-lookup"><span data-stu-id="c3091-118">This will show all of the objects that depend on the view and all of the objects on which the view depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c3091-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c3091-119">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="c3091-120">Para eliminar una vista de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c3091-120">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="c3091-121">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3091-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3091-122">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c3091-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c3091-123">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c3091-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c3091-124">El ejemplo elimina la vista especificada solo si la vista ya existe.</span><span class="sxs-lookup"><span data-stu-id="c3091-124">The example deletes the specified view only if the view already exists.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    IF OBJECT_ID ('HumanResources.EmployeeHireDate', 'V') IS NOT NULL  
    DROP VIEW HumanResources.EmployeeHireDate;  
    GO  
    ```  
  
 <span data-ttu-id="c3091-125">Para obtener más información, vea [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c3091-125">For more information, see [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
  
