---
title: Cambio de nombre de las vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- renaming views
ms.assetid: 5eed0488-81d2-40e8-8fdf-b0a640a591d0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc76ced033a69788270c3fa9277bcca6972e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744618"
---
# <a name="rename-views"></a><span data-ttu-id="03c51-102">Cambiar el nombre de las vistas</span><span class="sxs-lookup"><span data-stu-id="03c51-102">Rename Views</span></span>
  <span data-ttu-id="03c51-103">Puede cambiar el nombre de una vista en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03c51-103">You can rename a view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="03c51-104">Si cambia el nombre de una vista, pueden producirse errores en el código y las aplicaciones que dependen de la misma.</span><span class="sxs-lookup"><span data-stu-id="03c51-104">If you rename a view, code and applications that depend on the view may fail.</span></span> <span data-ttu-id="03c51-105">Los elementos afectados pueden ser otras vistas, consultas, procedimientos almacenados, funciones definidas por el usuario y aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="03c51-105">These include other views, queries, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="03c51-106">Tenga en cuenta que estos errores se producirán en cascada.</span><span class="sxs-lookup"><span data-stu-id="03c51-106">Note that these failures will cascade.</span></span>  
  
 <span data-ttu-id="03c51-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="03c51-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03c51-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="03c51-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03c51-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="03c51-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="03c51-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="03c51-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03c51-111">**Para cambiar el nombre de una vista, use:**</span><span class="sxs-lookup"><span data-stu-id="03c51-111">**To rename a view, using:**</span></span>  
  
     [<span data-ttu-id="03c51-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03c51-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03c51-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03c51-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="03c51-114">**Seguimiento:**  [Después de cambiar el nombre de una vista](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="03c51-114">**Follow Up:**  [After renaming a view](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03c51-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="03c51-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="03c51-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="03c51-116">Prerequisites</span></span>  
 <span data-ttu-id="03c51-117">Obtiene una lista de todas las dependencias de la vista.</span><span class="sxs-lookup"><span data-stu-id="03c51-117">Obtain a list of all dependencies on the view.</span></span> <span data-ttu-id="03c51-118">Cualquier objeto, script o aplicación que haga referencia a la vista debe modificarse para reflejar el nuevo nombre de la vista.</span><span class="sxs-lookup"><span data-stu-id="03c51-118">Any objects, scripts or applications that reference the view must be modified to reflect the new name of the view.</span></span> <span data-ttu-id="03c51-119">Para más información, consulte [Get Information About a View](get-information-about-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="03c51-119">For more information, see [Get Information About a View](get-information-about-a-view.md).</span></span> <span data-ttu-id="03c51-120">Se recomienda quitar la vista y volver a crearla con un nuevo nombre en lugar de cambiarle el nombre.</span><span class="sxs-lookup"><span data-stu-id="03c51-120">We recommend that you drop the view and recreate it with a new name instead of renaming the view.</span></span> <span data-ttu-id="03c51-121">Al volver a crear la vista, se actualiza la información de dependencia para los objetos a los que se hace referencia en la vista.</span><span class="sxs-lookup"><span data-stu-id="03c51-121">By recreating the view, you update the dependency information for the objects that are referenced in the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03c51-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="03c51-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03c51-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="03c51-123">Permissions</span></span>  
 <span data-ttu-id="03c51-124">Requiere el permiso ALTER en SCHEMA o el permiso CONTROL en OBJECT, y el permiso CREATE VIEW en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="03c51-124">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT is required, and CREATE VIEW permission in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03c51-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03c51-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-view"></a><span data-ttu-id="03c51-126">Para cambiar el nombre de una vista</span><span class="sxs-lookup"><span data-stu-id="03c51-126">To rename a view</span></span>  
  
1.  <span data-ttu-id="03c51-127">En el **Explorador de objetos**, expanda la base de datos que contiene la vista cuyo nombre desea cambiar y, a continuación, expanda la carpeta **Vista** .</span><span class="sxs-lookup"><span data-stu-id="03c51-127">In **Object Explorer**, expand the database that contains the view you wish to rename and then expand the **View** folder.</span></span>  
  
2.  <span data-ttu-id="03c51-128">Haga clic con el botón derecho en la vista cuyo nombre quiere cambiar y seleccione **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="03c51-128">Right-click the view you wish to rename and select **Rename**.</span></span>  
  
3.  <span data-ttu-id="03c51-129">Escriba el nuevo nombre de la vista.</span><span class="sxs-lookup"><span data-stu-id="03c51-129">Enter the view's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03c51-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03c51-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="03c51-131">**Para cambiar el nombre de una vista**</span><span class="sxs-lookup"><span data-stu-id="03c51-131">**To rename a view**</span></span>  
  
 <span data-ttu-id="03c51-132">Aunque puede usar **sp_rename** para cambiar el nombre de la vista, se recomienda eliminar la vista existente y volver a crearla con el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="03c51-132">While you can use **sp_rename** to change the name of the view, we recommend that you delete the existing view and then re-create it with the new name.</span></span>  
  
 <span data-ttu-id="03c51-133">Para obtener más información, vea [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) y [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03c51-133">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) and [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
##  <a name="follow-up-after-renaming-a-view"></a><a name="FollowUp"></a> <span data-ttu-id="03c51-134">Seguimiento: Después de cambiar el nombre de una vista</span><span class="sxs-lookup"><span data-stu-id="03c51-134">Follow Up: After Renaming a View</span></span>  
 <span data-ttu-id="03c51-135">Asegúrese de que todos los objetos, scripts y aplicaciones que hacen referencia al nombre antiguo de la vista usan el nombre nuevo.</span><span class="sxs-lookup"><span data-stu-id="03c51-135">Ensure that all objects, scripts, and applications that reference the view's old name now use the new name.</span></span>  
  
  
