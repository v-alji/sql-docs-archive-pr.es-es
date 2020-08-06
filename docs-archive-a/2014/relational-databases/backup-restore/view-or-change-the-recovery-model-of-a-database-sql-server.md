---
title: Ver o cambiar el modelo de recuperación de una base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], recovery models
- recovery [SQL Server], recovery model
- backing up databases [SQL Server], recovery models
- recovery models [SQL Server], switching
- recovery models [SQL Server], viewing
- database restores [SQL Server], recovery models
- modifying database recovery models
ms.assetid: 94918d1d-7c10-4be7-bf9f-27e00b003a0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889080301109938f0514bd6b81265c100237ab60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747048"
---
# <a name="view-or-change-the-recovery-model-of-a-database-sql-server"></a><span data-ttu-id="bba0f-102">Ver o cambiar el modelo de recuperación de una base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bba0f-102">View or Change the Recovery Model of a Database (SQL Server)</span></span>
  <span data-ttu-id="bba0f-103">En este tema se describe cómo ver o cambiar el modelo de recuperación de una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bba0f-103">This topic describes how to view or change the recovery model of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bba0f-104">Un *modelo de recuperación* es una propiedad de base de datos que controla la forma en que se registran las transacciones, si el registro de transacciones requiere que se realice la copia de seguridad y si lo permite, y qué tipos de operaciones de restauración hay disponibles.</span><span class="sxs-lookup"><span data-stu-id="bba0f-104">A *recovery model* is a database property that controls how transactions are logged, whether the transaction log requires (and allows) backing up, and what kinds of restore operations are available.</span></span> <span data-ttu-id="bba0f-105">Existen tres modelos de recuperación: simple, completa y por medio de registros de operaciones masivas.</span><span class="sxs-lookup"><span data-stu-id="bba0f-105">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="bba0f-106">Normalmente, en las bases de datos se usa el modelo de recuperación completa o el modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="bba0f-106">Typically, a database uses the full recovery model or simple recovery model.</span></span> <span data-ttu-id="bba0f-107">El modelo de recuperación de las bases de datos se puede cambiar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="bba0f-107">A database can be switched to another recovery model at any time.</span></span> <span data-ttu-id="bba0f-108">La base de datos **modelo** establece el modelo de recuperación predeterminado de nuevas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bba0f-108">The **model** database sets the default recovery model of new databases.</span></span>  
  
 <span data-ttu-id="bba0f-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="bba0f-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bba0f-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="bba0f-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bba0f-111">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="bba0f-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="bba0f-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="bba0f-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bba0f-113">**Para ver o cambiar el modelo de recuperación de una base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="bba0f-113">**To view or change the recovery model of a database, using:**</span></span>  
  
     [<span data-ttu-id="bba0f-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bba0f-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bba0f-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bba0f-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="bba0f-116">**Recomendaciones de seguimiento:**  [Después de cambiar el modelo de recuperación](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="bba0f-116">**Follow Up Recommendations:**  [After You Change the Recovery Model](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="bba0f-117">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="bba0f-117">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bba0f-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="bba0f-118">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="bba0f-119">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="bba0f-119">Recommendations</span></span>  
  
-   <span data-ttu-id="bba0f-120">Antes de cambiar del modelo de recuperación completa o del modelo de recuperación optimizado para cargas masivas de registros, haga copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="bba0f-120">Before switching from the full recovery or bulk-logged recovery model, back up the transaction log.</span></span>  
  
-   <span data-ttu-id="bba0f-121">La recuperación a un momento dado no es posible con el modelo optimizado para cargas masivas de registros.</span><span class="sxs-lookup"><span data-stu-id="bba0f-121">Point-in-time recovery is not possible with bulk-logged model.</span></span> <span data-ttu-id="bba0f-122">Por tanto, si ejecuta transacciones bajo el modelo de recuperación optimizado para cargas masivas de registros que requieran una restauración del registro de transacciones, estas transacciones podrían estar expuestas a la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="bba0f-122">Therefore, if you run transactions under the bulk-logged recovery model that might require a transaction log restore, these transactions could be exposed to data loss.</span></span> <span data-ttu-id="bba0f-123">Para aumentar la capacidad de recuperación de datos en un escenario de recuperación ante desastres, se recomienda cambiar al modelo de recuperación optimizado para cargas masivas de registros solo en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="bba0f-123">To maximize data recoverability in a disaster-recovery scenario, we recommend that you switch to the bulk-logged recovery model only under the following conditions:</span></span>  
  
    -   <span data-ttu-id="bba0f-124">Los usuarios no están permitidos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bba0f-124">Users are currently not allowed in the database.</span></span>  
  
    -   <span data-ttu-id="bba0f-125">Todas las modificaciones realizadas durante el proceso masivo son recuperables sin depender de una copia de seguridad de registros; por ejemplo, ejecutando de nuevo los procesos masivos.</span><span class="sxs-lookup"><span data-stu-id="bba0f-125">All modifications made during bulk processing are recoverable without depending on taking a log backup; for example, by re-running the bulk processes.</span></span>  
  
     <span data-ttu-id="bba0f-126">Si satisface ambas condiciones, no se verá expuesto a ninguna pérdida de datos cuando restaure un registro de transacciones a partir de una copia de seguridad bajo el modelo de recuperación optimizado para cargas masivas de registros.</span><span class="sxs-lookup"><span data-stu-id="bba0f-126">If you satisfy these two conditions, you will not be exposed to any data loss while restoring a transaction log that was backed up under the bulk-logged recovery model..</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bba0f-127">Si cambia al modelo de recuperación completa durante una operación masiva, el registro de la operación masiva se modifica del registro mínimo al registro completo y viceversa.</span><span class="sxs-lookup"><span data-stu-id="bba0f-127">If you switch to the full recovery model during a bulk operation, the logging of the bulk operation changes from minimal logging to full logging, and vice versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bba0f-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="bba0f-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bba0f-129">Permisos</span><span class="sxs-lookup"><span data-stu-id="bba0f-129">Permissions</span></span>  
 <span data-ttu-id="bba0f-130">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bba0f-130">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bba0f-131">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bba0f-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-recovery-model"></a><span data-ttu-id="bba0f-132">Para ver o cambiar el modelo de recuperación</span><span class="sxs-lookup"><span data-stu-id="bba0f-132">To view or change the recovery model</span></span>  
  
1.  <span data-ttu-id="bba0f-133">Después de conectarse a la instancia apropiada de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="bba0f-133">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="bba0f-134">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="bba0f-134">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="bba0f-135">Haga clic con el botón derecho en la base de datos y haga clic en **Propiedades**, lo que abre el cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="bba0f-135">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="bba0f-136">En el panel **Seleccionar una página** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="bba0f-136">In the **Select a page** pane, click **Options**.</span></span>  
  
5.  <span data-ttu-id="bba0f-137">El modelo de recuperación actual se muestra en el cuadro de lista **Modelo de recuperación** .</span><span class="sxs-lookup"><span data-stu-id="bba0f-137">The current recovery model is displayed in the **Recovery model** list box.</span></span>  
  
6.  <span data-ttu-id="bba0f-138">Si lo desea, también puede seleccionar otra lista de modelos para cambiar el modelo de recuperación.</span><span class="sxs-lookup"><span data-stu-id="bba0f-138">Optionally, to change the recovery model select a different model list.</span></span> <span data-ttu-id="bba0f-139">Las opciones son **Completa**, **Registro masivo**o **Simple**.</span><span class="sxs-lookup"><span data-stu-id="bba0f-139">The choices are **Full**, **Bulk-logged**, or **Simple**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bba0f-140">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bba0f-140">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-recovery-model"></a><span data-ttu-id="bba0f-141">Para ver el modelo de recuperación</span><span class="sxs-lookup"><span data-stu-id="bba0f-141">To view the recovery model</span></span>  
  
1.  <span data-ttu-id="bba0f-142">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bba0f-142">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bba0f-143">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="bba0f-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bba0f-144">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bba0f-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bba0f-145">Este ejemplo muestra cómo consultar la vista de catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) para obtener información sobre el modelo de recuperación de la base de datos **modelo** .</span><span class="sxs-lookup"><span data-stu-id="bba0f-145">This example shows how to query the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to learn the recovery model of the **model** database.</span></span>  
  
```sql  
SELECT name, recovery_model_desc  
   FROM sys.databases  
      WHERE name = 'model' ;  
GO  
  
```  
  
#### <a name="to-change-the-recovery-model"></a><span data-ttu-id="bba0f-146">Para cambiar el modelo de recuperación</span><span class="sxs-lookup"><span data-stu-id="bba0f-146">To change the recovery model</span></span>  
  
1.  <span data-ttu-id="bba0f-147">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bba0f-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bba0f-148">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="bba0f-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bba0f-149">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bba0f-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bba0f-150">En este ejemplo se muestra cómo cambiar el modelo de recuperación de la base de datos `model` a `FULL` utilizando la opción `SET RECOVERY` de la instrucción de [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="bba0f-150">This example shows how to change the recovery model in the `model` database to `FULL` by using the `SET RECOVERY` option of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement.</span></span>  
  
```sql  
USE master ;  
ALTER DATABASE model SET RECOVERY FULL ;  
```  
  
##  <a name="follow-up-recommendations-after-you-change-the-recovery-model"></a><a name="FollowUp"></a><span data-ttu-id="bba0f-151">Recomendaciones de seguimiento: después de cambiar el modelo de recuperación</span><span class="sxs-lookup"><span data-stu-id="bba0f-151">Follow Up Recommendations: After You Change the Recovery Model</span></span>  
  
-   <span data-ttu-id="bba0f-152">**Después de cambiar entre el modelo de recuperación completa y el modelo de recuperación optimizado para cargas masivas de registros**</span><span class="sxs-lookup"><span data-stu-id="bba0f-152">**After switching between the full and bulk-logged recovery models**</span></span>  
  
    -   <span data-ttu-id="bba0f-153">Después de haber completado las operaciones masivas, vuelva a cambiar inmediatamente al modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="bba0f-153">After completing the bulk operations, immediately switch back to full recovery mode.</span></span>  
  
    -   <span data-ttu-id="bba0f-154">Después de cambiar del modelo de recuperación optimizado para cargas masivas de registros al modelo de recuperación completa, realice una copia de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="bba0f-154">After switching from the bulk-logged recovery model back to the full recovery model, back up the log.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bba0f-155">La estrategia de copia de seguridad sigue siendo la misma: siga realizando las copias de seguridad periódicas de la base de datos, del registro y diferenciales.</span><span class="sxs-lookup"><span data-stu-id="bba0f-155">Your backup strategy remains the same: continue performing periodic database, log, and differential backups.</span></span>  
  
-   <span data-ttu-id="bba0f-156">**Después de cambiar desde el modelo de recuperación simple**</span><span class="sxs-lookup"><span data-stu-id="bba0f-156">**After switching from the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="bba0f-157">Inmediatamente después de cambiar al modelo de recuperación completa o al optimizado para cargas masivas de registros, realice una copia de seguridad de la base de datos completa o diferencial para iniciar la cadena de registros.</span><span class="sxs-lookup"><span data-stu-id="bba0f-157">Immediately after switching to the full recovery model or bulk-logged recovery model, take a full or differential database backup to start the log chain.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bba0f-158">El cambio al modelo de recuperación completa o al modelo de recuperación optimizado para cargas masivas de registros solo surte efecto después de la primera copia de seguridad de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bba0f-158">The switch to the full or bulk-logged recovery model takes effect only after the first data backup.</span></span>  
  
    -   <span data-ttu-id="bba0f-159">Programe periódicamente copias de seguridad de registros y actualice el plan de restauración en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="bba0f-159">Schedule regular log backups, and update your restore plan accordingly.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="bba0f-160">Si no realiza la copia de seguridad con la frecuencia suficiente, el registro de transacciones se puede expandir hasta quedarse sin espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="bba0f-160">If you do not back up the log frequently enough, the transaction log can expand until it runs out of disk space.</span></span>  
  
-   <span data-ttu-id="bba0f-161">**Tras cambiar al modelo de recuperación simple**</span><span class="sxs-lookup"><span data-stu-id="bba0f-161">**After switching to the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="bba0f-162">Interrumpa cualquier trabajo programado para realizar copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="bba0f-162">Discontinue any scheduled jobs for backing up the transaction log.</span></span>  
  
    -   <span data-ttu-id="bba0f-163">Asegúrese de que estén programadas copias de seguridad periódicas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bba0f-163">Ensure periodic database backups are scheduled.</span></span> <span data-ttu-id="bba0f-164">Es esencial hacer copia de seguridad de la base de datos para proteger los datos y para truncar la parte inactiva del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="bba0f-164">Backing up your database is essential both to protect your data and to truncate the inactive portion of the transaction log.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="bba0f-165">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="bba0f-165">Related Tasks</span></span>  
  
-   [<span data-ttu-id="bba0f-166">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bba0f-166">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="bba0f-167">Realizar una copia de seguridad de un registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bba0f-167">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="bba0f-168">Crear un trabajo</span><span class="sxs-lookup"><span data-stu-id="bba0f-168">Create a Job</span></span>](../../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="bba0f-169">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="bba0f-169">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="bba0f-170">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="bba0f-170">Related Content</span></span>  
  
-   <span data-ttu-id="bba0f-171">[Planes de mantenimiento de bases de datos](../maintenance-plans/maintenance-plans.md) (en los Libros en pantalla de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="bba0f-171">[Database Maintenance Plans](../maintenance-plans/maintenance-plans.md) (in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba0f-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bba0f-172">See Also</span></span>  
 <span data-ttu-id="bba0f-173">[Modelos de recuperación &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bba0f-173">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="bba0f-174">[El registro de transacciones &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bba0f-174">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="bba0f-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bba0f-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="bba0f-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bba0f-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="bba0f-177">Modelos de recuperación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bba0f-177">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
