---
title: Quitar el testigo de una sesión de creación de reflejo de la base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], turning off
- witness [SQL Server], removing
- database mirroring [SQL Server], witness
ms.assetid: f3ce7afc-8936-4d35-80ce-d0f8fbc318d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5ede54aca3588a6fcd7cee8759112b606eac752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746494"
---
# <a name="remove-the-witness-from-a-database-mirroring-session-sql-server"></a><span data-ttu-id="15f58-102">Quitar el testigo de una sesión de creación de reflejo de la base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="15f58-102">Remove the Witness from a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="15f58-103">En este tema se describe cómo quitar un testigo de una sesión de creación de reflejo de una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15f58-103">This topic describes how to remove a witness from a database mirroring session in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="15f58-104">En cualquier momento durante una sesión de creación de reflejo de la base de datos, el propietario de la base de datos puede desactivar el testigo.</span><span class="sxs-lookup"><span data-stu-id="15f58-104">At any time during a database mirroring session, the database owner can turn off the witness for a database mirroring session.</span></span>  
  
 <span data-ttu-id="15f58-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="15f58-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="15f58-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="15f58-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="15f58-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="15f58-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="15f58-108">**Para quitar el testigo, mediante:**</span><span class="sxs-lookup"><span data-stu-id="15f58-108">**To Replace remove the witness, using:**</span></span>  
  
     [<span data-ttu-id="15f58-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15f58-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="15f58-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15f58-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="15f58-111">**Seguimiento:**  [después de quitar el testigo](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="15f58-111">**Follow Up:**  [After Removing the Witness](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="15f58-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="15f58-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="15f58-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="15f58-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="15f58-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="15f58-114">Permissions</span></span>  
 <span data-ttu-id="15f58-115">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="15f58-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="15f58-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15f58-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="15f58-117">Para quitar el testigo</span><span class="sxs-lookup"><span data-stu-id="15f58-117">To remove the witness</span></span>  
  
1.  <span data-ttu-id="15f58-118">Conéctese a la instancia de servidor principal y, en el panel **Explorador de objetos** , haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="15f58-118">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="15f58-119">Expanda **Bases de datos**y seleccione la base de datos cuyo testigo desee quitar.</span><span class="sxs-lookup"><span data-stu-id="15f58-119">Expand **Databases**, and select the database whose witness you want to remove.</span></span>  
  
3.  <span data-ttu-id="15f58-120">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, luego, haga clic en **Reflejado**.</span><span class="sxs-lookup"><span data-stu-id="15f58-120">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="15f58-121">Así se abre la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="15f58-121">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="15f58-122">Para quitar el testigo, elimine su dirección de red del servidor del campo **Testigo** .</span><span class="sxs-lookup"><span data-stu-id="15f58-122">To remove the witness, delete its server network address from the **Witness** field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15f58-123">Si pasa del modo de alta seguridad con conmutación automática por error al modo de alto rendimiento, el campo **Testigo** se vacía de forma automática.</span><span class="sxs-lookup"><span data-stu-id="15f58-123">If you switch from high-safety mode with automatic failover to high-performance mode, the **Witness** field is automatically cleared.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="15f58-124">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15f58-124">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="15f58-125">Para quitar el testigo</span><span class="sxs-lookup"><span data-stu-id="15f58-125">To remove the witness</span></span>  
  
1.  <span data-ttu-id="15f58-126">Conéctese al [!INCLUDE[ssDE](../../includes/ssde-md.md)] en la instancia de servidor asociada.</span><span class="sxs-lookup"><span data-stu-id="15f58-126">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on either partner server instance.</span></span>  
  
2.  <span data-ttu-id="15f58-127">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="15f58-127">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="15f58-128">Emita la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="15f58-128">Issue the following statement:</span></span>  
  
     <span data-ttu-id="15f58-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *nombre_base_de_datos* SET WITNESS OFF</span><span class="sxs-lookup"><span data-stu-id="15f58-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET WITNESS OFF</span></span>  
  
     <span data-ttu-id="15f58-130">Donde *nombre_base_de_datos* es el nombre de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="15f58-130">where *database_name* is the name of the mirrored database.</span></span>  
  
     <span data-ttu-id="15f58-131">En el ejemplo siguiente se quita el testigo de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15f58-131">The following example removes the witness from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET WITNESS OFF ;  
    ```  
  
##  <a name="follow-up-after-removing-the-witness"></a><a name="FollowUp"></a><span data-ttu-id="15f58-132">Seguimiento: después de quitar el testigo</span><span class="sxs-lookup"><span data-stu-id="15f58-132">Follow Up: After Removing the Witness</span></span>  
 <span data-ttu-id="15f58-133">Al desactivar el testigo cambia el [modo de funcionamiento](database-mirroring-operating-modes.md)de acuerdo con la configuración de la seguridad de las transacciones:</span><span class="sxs-lookup"><span data-stu-id="15f58-133">Turning off the witness changes the [operating mode](database-mirroring-operating-modes.md)in accordance with the transaction-safety setting:</span></span>  
  
-   <span data-ttu-id="15f58-134">Si la seguridad de las transacciones está configurada en FULL (el valor predeterminado), la sesión utiliza el modo sincrónico de alta seguridad sin conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="15f58-134">If transaction safety is set to FULL (the default), the session uses high-safety, synchronous mode without automatic failover.</span></span>  
  
-   <span data-ttu-id="15f58-135">Si la seguridad de las transacciones está configurada en OFF, el funcionamiento de la sesión es asincrónico (en modo de alto rendimiento) sin requerir quórum.</span><span class="sxs-lookup"><span data-stu-id="15f58-135">If transaction safety is set to OFF, the session operates asynchronously (in high-performance mode) without requiring quorum.</span></span> <span data-ttu-id="15f58-136">Siempre que la seguridad de las transacciones se desactive, recomendamos desactivar también el testigo.</span><span class="sxs-lookup"><span data-stu-id="15f58-136">Whenever transaction safety is turned off, we strongly recommend also turning the witness off.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="15f58-137">La configuración de seguridad de las transacciones de la base de datos está registrada en cada asociado de la vista de catálogo [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) en las columnas **mirroring_safety_level** y **mirroring_safety_level_desc**.</span><span class="sxs-lookup"><span data-stu-id="15f58-137">The transaction safety setting of the database is recorded on each partner in the [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) catalog view in the **mirroring_safety_level** and **mirroring_safety_level_desc** columns.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="15f58-138">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="15f58-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="15f58-139">Agregar un testigo de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15f58-139">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="15f58-140">Agregar o reemplazar un testigo de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="15f58-140">Add or Replace a Database Mirroring Witness &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/add-or-replace-a-database-mirroring-witness-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="15f58-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15f58-141">See Also</span></span>  
 <span data-ttu-id="15f58-142">[Reflejo de la base de datos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="15f58-142">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="15f58-143">[Cambiar la seguridad de las transacciones en una sesión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="15f58-143">[Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="15f58-144">[Agregar un testigo de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="15f58-144">[Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="15f58-145">Testigo de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="15f58-145">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
