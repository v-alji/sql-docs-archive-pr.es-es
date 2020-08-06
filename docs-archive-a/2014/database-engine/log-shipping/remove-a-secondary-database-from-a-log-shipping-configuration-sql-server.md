---
title: Quitar una base de datos secundaria desde una configuración del trasvase de registros (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- deleting secondary databases
- secondary databases [SQL Server], in log shipping
- removing secondary databases
- secondary data files [SQL Server], removing
- log shipping [SQL Server], secondary databases
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 119f2762d41d0787b6b3279507e9671e89fddfca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674311"
---
# <a name="remove-a-secondary-database-from-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="226e8-102">Quitar una base de datos secundaria desde una configuración del trasvase de registros (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="226e8-102">Remove a Secondary Database from a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="226e8-103">En este tema se describe cómo quitar una base de datos secundaria de trasvase de registros en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="226e8-103">This topic describes how to remove a log shipping secondary database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="226e8-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="226e8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="226e8-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="226e8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="226e8-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="226e8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="226e8-107">**Para quitar una base de datos secundaria de trasvase de registros con:**</span><span class="sxs-lookup"><span data-stu-id="226e8-107">**To remove a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="226e8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="226e8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="226e8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="226e8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="226e8-110">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="226e8-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="226e8-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="226e8-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="226e8-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="226e8-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="226e8-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="226e8-113">Permissions</span></span>  
 <span data-ttu-id="226e8-114">Los procedimientos almacenados de trasvase de registros requieren que se pertenezca al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="226e8-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="226e8-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="226e8-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-a-log-shipping-secondary-database"></a><span data-ttu-id="226e8-116">Para quitar una base de datos secundaria de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="226e8-116">To remove a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="226e8-117">Conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que sea actualmente el servidor principal de trasvase de registros y expándala.</span><span class="sxs-lookup"><span data-stu-id="226e8-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="226e8-118">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos principal de trasvase de registros y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="226e8-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="226e8-119">En **Seleccionar una página**, haga clic en **Trasvase de registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="226e8-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="226e8-120">En **Instancias de servidores secundarios y bases de datos**, haga clic en la base de datos que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="226e8-120">Under **Secondary server instances and databases**, click the database you want to remove.</span></span>  
  
5.  <span data-ttu-id="226e8-121">Haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="226e8-121">Click **Remove**.</span></span>  
  
6.  <span data-ttu-id="226e8-122">Haga clic en **Aceptar** para actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="226e8-122">Click **OK** to update the configuration.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="226e8-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="226e8-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-secondary-database"></a><span data-ttu-id="226e8-124">Para quitar una base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="226e8-124">To Remove a Secondary Database</span></span>  
  
1.  <span data-ttu-id="226e8-125">En el servidor principal, ejecute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) para eliminar la información sobre la base de datos secundaria en el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="226e8-125">On the primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="226e8-126">En el servidor secundario, ejecute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) para eliminar la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="226e8-126">On the secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="226e8-127">Si no hay ninguna otra base de datos secundaria con el mismo identificador secundario, se invoca **sp_delete_log_shipping_secondary_primary** desde **sp_delete_log_shipping_secondary_database** y elimina la entrada del identificador secundario y los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="226e8-127">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="226e8-128">En el servidor secundario, deshabilite los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="226e8-128">On the secondary server, disable the copy and restore jobs.</span></span> <span data-ttu-id="226e8-129">Para obtener más información, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="226e8-129">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="226e8-130">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="226e8-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="226e8-131">Actualizar el trasvase de registros a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="226e8-131">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="226e8-132">Configurar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="226e8-132">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="226e8-133">Agregar una base de datos secundaria a la configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="226e8-133">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="226e8-134">Quitar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="226e8-134">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="226e8-135">Ver el informe de trasvase de registros &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="226e8-135">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="226e8-136">Supervisar el trasvase de registros &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="226e8-136">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="226e8-137">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="226e8-137">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="226e8-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="226e8-138">See Also</span></span>  
 <span data-ttu-id="226e8-139">[Acerca del trasvase de registros &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="226e8-139">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="226e8-140">Tablas y procedimientos almacenados de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="226e8-140">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
