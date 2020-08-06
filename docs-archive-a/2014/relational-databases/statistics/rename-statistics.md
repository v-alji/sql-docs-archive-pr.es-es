---
title: Cambio de nombre de las estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- renaming statistics
- statistics [SQL Server], renaming
ms.assetid: a3bed7b7-3dc5-4b33-b1c6-67c27f573764
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1528dcec50a662524531065d597b004fe7f59e5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676407"
---
# <a name="rename-statistics"></a><span data-ttu-id="f00b8-102">Cambiar el nombre de las estadísticas</span><span class="sxs-lookup"><span data-stu-id="f00b8-102">Rename Statistics</span></span>
  <span data-ttu-id="f00b8-103">Puede cambiar el nombre de un objeto de estadísticas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f00b8-103">You can rename a statistics object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="f00b8-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f00b8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f00b8-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f00b8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f00b8-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f00b8-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f00b8-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f00b8-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f00b8-108">**Para cambiar el nombre de un objeto de estadísticas, con:**</span><span class="sxs-lookup"><span data-stu-id="f00b8-108">**To rename a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="f00b8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f00b8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f00b8-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f00b8-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f00b8-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f00b8-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f00b8-112">De forma predeterminada, al crear un índice se crea una estadística sobre las columnas de clave del índice.</span><span class="sxs-lookup"><span data-stu-id="f00b8-112">By default, creating an index creates a statistic on the key columns of that index.</span></span> <span data-ttu-id="f00b8-113">Por consiguiente, al cambiar el nombre del índice, se cambia automáticamente el nombre del objeto de estadísticas y viceversa.</span><span class="sxs-lookup"><span data-stu-id="f00b8-113">Therefore, renaming the index automatically renames the statistics object, and vice versa.</span></span>  
  
 <span data-ttu-id="f00b8-114">Al cambiar cualquier parte del nombre de un objeto se pueden interrumpir scripts y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="f00b8-114">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="f00b8-115">En lugar de cambiar el nombre, se recomienda que quite el objeto de estadísticas y que vuelva a crearlo con el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="f00b8-115">Instead of renaming, we recommend that you drop the statistics object and re-create it with the new name.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f00b8-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f00b8-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f00b8-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="f00b8-117">Permissions</span></span>  
 <span data-ttu-id="f00b8-118">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="f00b8-118">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f00b8-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f00b8-119">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-statistics-object"></a><span data-ttu-id="f00b8-120">Para cambiar el nombre de un objeto de estadísticas</span><span class="sxs-lookup"><span data-stu-id="f00b8-120">To rename a statistics object</span></span>  
  
1.  <span data-ttu-id="f00b8-121">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f00b8-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f00b8-122">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f00b8-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f00b8-123">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f00b8-123">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename N'AK_Employee_LoginID', N'AK_Emp_Login', N'STATISTICS';   
    GO  
    ```  
  
 <span data-ttu-id="f00b8-124">Para obtener más información, vea [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f00b8-124">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
