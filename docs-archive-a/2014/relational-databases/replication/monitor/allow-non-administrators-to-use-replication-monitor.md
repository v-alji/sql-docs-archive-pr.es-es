---
title: Permitir el uso del Monitor de replicación a los usuarios que no son administradores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, non-administrators access
ms.assetid: 1cf21d9e-831d-41a1-a5a0-83ff6d22fa86
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4a7699c555086d627e4c3a52ea70acf931ea1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670935"
---
# <a name="allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="d44c0-102">Permitir el uso del Monitor de replicación a los usuarios que no son administradores</span><span class="sxs-lookup"><span data-stu-id="d44c0-102">Allow Non-Administrators to Use Replication Monitor</span></span>
  <span data-ttu-id="d44c0-103">En este tema se describe cómo permitir a los usuarios que no son administradores que usen el Monitor de replicación en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d44c0-103">This topic describes how to allow non-administrators to use Replication Monitor in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d44c0-104">El Monitor de replicación solamente pueden utilizarlo usuarios que son miembros de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="d44c0-104">Replication Monitor can be used by users who are members of the following roles:</span></span>  
  
-   <span data-ttu-id="d44c0-105">El rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d44c0-105">The **sysadmin** fixed server role.</span></span>  
  
     <span data-ttu-id="d44c0-106">Estos usuarios pueden supervisar la replicación y tener control total sobre los cambios en las propiedades de la replicación, como programaciones del agente, perfiles del agente, etc.</span><span class="sxs-lookup"><span data-stu-id="d44c0-106">These users can monitor replication and have full control over changing replication properties such as agent schedules, agent profiles, and so on.</span></span>  
  
-   <span data-ttu-id="d44c0-107">El `replmonitor` rol de base de datos en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="d44c0-107">The `replmonitor` database role in the distribution database.</span></span>  
  
     <span data-ttu-id="d44c0-108">Estos usuarios pueden supervisar la replicación, pero no pueden cambiar ninguna de las propiedades de la replicación.</span><span class="sxs-lookup"><span data-stu-id="d44c0-108">These users can monitor replication, but cannot change any replication properties.</span></span>  
  
 <span data-ttu-id="d44c0-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d44c0-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d44c0-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d44c0-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d44c0-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d44c0-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d44c0-112">**Para permitir el uso del Monitor de replicación a los usuarios que no son administradores, mediante:**</span><span class="sxs-lookup"><span data-stu-id="d44c0-112">**To allow non-administrators to use Replication Monitor, using:**</span></span>  
  
     [<span data-ttu-id="d44c0-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d44c0-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d44c0-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d44c0-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d44c0-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d44c0-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d44c0-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d44c0-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d44c0-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="d44c0-117">Permissions</span></span>  
 <span data-ttu-id="d44c0-118">Para permitir el uso del monitor de replicación a los usuarios que no son administradores, un miembro del rol fijo de servidor **sysadmin** debe agregar el usuario a la base de datos de distribución y asignar ese usuario al `replmonitor` rol.</span><span class="sxs-lookup"><span data-stu-id="d44c0-118">To allow non-administrators to use Replication Monitor, a member of the **sysadmin** fixed server role must add the user to the distribution database and assign that user to the `replmonitor` role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d44c0-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d44c0-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="d44c0-120">Para permitir el uso del Monitor de replicación a los usuarios que no son administradores</span><span class="sxs-lookup"><span data-stu-id="d44c0-120">To allow non-administrators to use Replication Monitor</span></span>  
  
1.  <span data-ttu-id="d44c0-121">En [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conéctese al distribuidor y, a continuación, expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="d44c0-121">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the Distributor, and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d44c0-122">Expanda **Bases de datos**, expanda **Bases de datos del sistema**y, a continuación, expanda la base de datos de distribución (denominada, de forma predeterminada, **distribución** ).</span><span class="sxs-lookup"><span data-stu-id="d44c0-122">Expand **Databases**, expand **System Databases**, and then expand the distribution database (named **distribution** by default).</span></span>  
  
3.  <span data-ttu-id="d44c0-123">Expanda **Seguridad**, haga clic con el botón secundario en **Usuarios**y, a continuación, haga clic en **Nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="d44c0-123">Expand **Security**, right-click **Users**, and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="d44c0-124">Escriba un nombre de usuario e inicie la sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="d44c0-124">Enter a user name and login for the user.</span></span>  
  
5.  <span data-ttu-id="d44c0-125">Seleccione un esquema predeterminado de `replmonitor` .</span><span class="sxs-lookup"><span data-stu-id="d44c0-125">Select a default schema of `replmonitor`.</span></span>  
  
6.  <span data-ttu-id="d44c0-126">Active la `replmonitor` casilla de la cuadrícula **pertenencia al rol** de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d44c0-126">Select the `replmonitor` check box in the **Database role membership** grid.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d44c0-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d44c0-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-user-to-the-replmonitor-fixed-database-role"></a><span data-ttu-id="d44c0-128">Para agregar un usuario al rol fijo de base de datos replmonitor</span><span class="sxs-lookup"><span data-stu-id="d44c0-128">To add a user to the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="d44c0-129">En cualquier base de datos de distribución, ejecute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d44c0-129">At the Distributor on the distribution database, execute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span></span> <span data-ttu-id="d44c0-130">Si el usuario no aparece en `UserName` el conjunto de resultados, se debe conceder al usuario acceso a la base de datos de distribución mediante la instrucción [CREATE USER &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d44c0-130">If the user is not listed in `UserName` in the result set, the user must be granted access to the distribution database using the [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) statement.</span></span>  
  
2.  <span data-ttu-id="d44c0-131">En el distribuidor de la base de datos de distribución, ejecute [sp_helprolemember &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), especificando un valor de `replmonitor` para el **@rolename** parámetro.</span><span class="sxs-lookup"><span data-stu-id="d44c0-131">At the Distributor on the distribution database, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), specifying a value of `replmonitor` for the **@rolename** parameter.</span></span> <span data-ttu-id="d44c0-132">Si el usuario aparece en `MemberName` el conjunto de resultados, el usuario ya pertenece a este rol.</span><span class="sxs-lookup"><span data-stu-id="d44c0-132">If the user is listed in `MemberName` in the result set, the user already belongs to this role.</span></span>  
  
3.  <span data-ttu-id="d44c0-133">Si el usuario no pertenece al `replmonitor` rol, ejecute [sp_addrolemember &#40;&#41;de TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) en el distribuidor de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="d44c0-133">If the user does not belong to the `replmonitor` role, execute [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="d44c0-134">Especifique un valor de `replmonitor` para **@rolename** y el nombre del usuario de la base de datos o el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Inicio de sesión de Windows que se va a agregar para **@membername** .</span><span class="sxs-lookup"><span data-stu-id="d44c0-134">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows login being added for **@membername**.</span></span>  
  
#### <a name="to-remove-a-user-from-the-replmonitor-fixed-database-role"></a><span data-ttu-id="d44c0-135">Para quitar un usuario desde el rol fijo de base de datos replmonitor</span><span class="sxs-lookup"><span data-stu-id="d44c0-135">To remove a user from the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="d44c0-136">Para comprobar que el usuario pertenece al `replmonitor` rol, ejecute [sp_helprolemember &#40;&#41;de TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) en el distribuidor de la base de datos de distribución y especifique un valor de `replmonitor` para **@rolename** .</span><span class="sxs-lookup"><span data-stu-id="d44c0-136">To verify that the user belongs to the `replmonitor` role, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) at the Distributor on the distribution database, and specify a value of `replmonitor` for **@rolename**.</span></span> <span data-ttu-id="d44c0-137">Si el usuario no aparece en `MemberName` en el conjunto de resultados, el usuario no pertenece actualmente a este rol.</span><span class="sxs-lookup"><span data-stu-id="d44c0-137">If the user is not listed in `MemberName` in the result set, the user does not currently belong to this role.</span></span>  
  
2.  <span data-ttu-id="d44c0-138">Si el usuario pertenece al `replmonitor` rol, ejecute [sp_droprolemember &#40;&#41;de TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) en la base de datos de distribución del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d44c0-138">If the user does belong to the `replmonitor` role, execute [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="d44c0-139">Especifique un valor de `replmonitor` para **@rolename** y el nombre del usuario de la base de datos o el inicio de sesión de Windows que se va a quitar para **@membername** .</span><span class="sxs-lookup"><span data-stu-id="d44c0-139">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the Windows login being removed for **@membername**.</span></span>  
  
  
