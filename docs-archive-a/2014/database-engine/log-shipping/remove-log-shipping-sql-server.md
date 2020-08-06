---
title: Quitar el trasvase de registros (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], removing
- removing log shipping
- deleting log shipping
ms.assetid: 859373db-c744-4a4b-8479-45163f61e8cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 14fdc36c66073e89dcc2014aed4319a2ce78a98f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673242"
---
# <a name="remove-log-shipping-sql-server"></a><span data-ttu-id="4420a-102">Quitar el trasvase de registros de (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4420a-102">Remove Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="4420a-103">En este tema se describe cómo quitar el trasvase de registros en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4420a-103">This topic describes how to remove log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4420a-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4420a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4420a-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4420a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4420a-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4420a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4420a-107">**Para quitar el trasvase de registros, mediante:**</span><span class="sxs-lookup"><span data-stu-id="4420a-107">**To remove log shipping, using:**</span></span>  
  
     [<span data-ttu-id="4420a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4420a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4420a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4420a-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="4420a-110">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4420a-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4420a-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4420a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4420a-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4420a-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4420a-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="4420a-113">Permissions</span></span>  
 <span data-ttu-id="4420a-114">Los procedimientos almacenados de trasvase de registros requieren que se pertenezca al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4420a-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4420a-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4420a-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="4420a-116">Para quitar el trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="4420a-116">To remove log shipping</span></span>  
  
1.  <span data-ttu-id="4420a-117">Conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que sea actualmente el servidor principal de trasvase de registros y expándala.</span><span class="sxs-lookup"><span data-stu-id="4420a-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="4420a-118">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos principal de trasvase de registros y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4420a-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4420a-119">En **Seleccionar una página**, haga clic en **Trasvase de registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="4420a-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="4420a-120">Desactive la casilla **Habilitar ésta como base de datos principal en una configuración de trasvase de registros** .</span><span class="sxs-lookup"><span data-stu-id="4420a-120">Clear the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
5.  <span data-ttu-id="4420a-121">Haga clic en **Aceptar** para quitar el trasvase de registros de esta base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="4420a-121">Click **OK** to remove log shipping from this primary database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4420a-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4420a-122">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="4420a-123">Para quitar el trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="4420a-123">To Remove Log Shipping</span></span>  
  
1.  <span data-ttu-id="4420a-124">En el servidor principal de trasvase de registros, ejecute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) para eliminar la información sobre la base de datos secundaria en el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="4420a-124">On the log shipping primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="4420a-125">En el servidor secundario de trasvase de registros, ejecute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) para eliminar la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="4420a-125">On the log shipping secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4420a-126">Si no hay ninguna otra base de datos secundaria con el mismo identificador secundario, se invoca **sp_delete_log_shipping_secondary_primary** desde **sp_delete_log_shipping_secondary_database** y elimina la entrada del identificador secundario y los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="4420a-126">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="4420a-127">En el servidor principal de trasvase de registros, ejecute **sp_delete_log_shipping_primary_database** para eliminar la información sobre la configuración de trasvase de registros en el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="4420a-127">On the log shipping primary server, execute **sp_delete_log_shipping_primary_database** to delete information about the log shipping configuration from the primary server.</span></span> <span data-ttu-id="4420a-128">Esto también se elimina el trabajo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4420a-128">This also deletes the backup job.</span></span>  
  
4.  <span data-ttu-id="4420a-129">En el servidor principal de trasvase de registros, deshabilite el trabajo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4420a-129">On the log shipping primary server, disable the backup job.</span></span> <span data-ttu-id="4420a-130">Para obtener más información, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="4420a-130">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
5.  <span data-ttu-id="4420a-131">En el servidor secundario de trasvase de registros, deshabilite los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="4420a-131">On the log shipping secondary server, disable the copy and restore jobs.</span></span>  
  
6.  <span data-ttu-id="4420a-132">Opcionalmente, si ya utiliza la base de datos secundaria de trasvase de registros, puede eliminarla del servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="4420a-132">Optionally, if you are no longer using the log shipping secondary database, you can delete it from the secondary server.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4420a-133">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4420a-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4420a-134">Actualizar el trasvase de registros a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4420a-134">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="4420a-135">Configurar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4420a-135">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="4420a-136">Agregar una base de datos secundaria a la configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4420a-136">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="4420a-137">Quitar una base de datos secundaria desde una configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4420a-137">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="4420a-138">Supervisar el trasvase de registros &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4420a-138">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="4420a-139">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4420a-139">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="4420a-140">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="4420a-140">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
## <a name="see-also"></a><span data-ttu-id="4420a-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4420a-141">See Also</span></span>  
 <span data-ttu-id="4420a-142">[Acerca del trasvase de registros &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4420a-142">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="4420a-143">Tablas y procedimientos almacenados de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="4420a-143">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
