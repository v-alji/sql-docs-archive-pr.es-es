---
title: Administración de la tabla suspect_pages (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
- restoring pages [SQL Server]
- pages [SQL Server], suspect
- pages [SQL Server], restoring
- suspect_pages system table
- suspect pages [SQL Server]
- restoring [SQL Server], pages
ms.assetid: f394d4bc-1518-4e61-97fc-bf184d972e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dd7aea63ae85a16e23ff532c7e18ace3c376a707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677704"
---
# <a name="manage-the-suspect_pages-table-sql-server"></a><span data-ttu-id="5b5f6-102">Administrar la tabla suspect_pages (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5b5f6-102">Manage the suspect_pages Table (SQL Server)</span></span>
  <span data-ttu-id="5b5f6-103">En este tema se describe cómo administrar la tabla **suspect_pages** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] por medio de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b5f6-103">This topic describes how to manage the **suspect_pages** table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b5f6-104">La tabla **suspect_pages** sirve para conservar información sobre las páginas sospechosas y es de gran utilidad para decidir si es necesaria una restauración.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-104">The **suspect_pages** table is used for maintaining information about suspect pages, and is relevant in helping to decide whether a restore is necessary.</span></span> <span data-ttu-id="5b5f6-105">La tabla [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) reside en la [base de datos msdb](../databases/msdb-database.md).</span><span class="sxs-lookup"><span data-stu-id="5b5f6-105">The [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) table resides in the [msdb database](../databases/msdb-database.md).</span></span>  
  
 <span data-ttu-id="5b5f6-106">Una página se considera "sospechosa" cuando [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encuentra uno de los errores siguientes al intentar leer una página de datos:</span><span class="sxs-lookup"><span data-stu-id="5b5f6-106">A page is considered "suspect" when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encounters one of the following errors when it tries to read a data page:</span></span>  
  
-   <span data-ttu-id="5b5f6-107">Un [error 823](../errors-events/mssqlserver-823-database-engine-error.md) producido por una comprobación de redundancia cíclica (CRC) emitido por el sistema operativo, como un error de disco (ciertos errores de hardware)</span><span class="sxs-lookup"><span data-stu-id="5b5f6-107">An [823 error](../errors-events/mssqlserver-823-database-engine-error.md) that was caused by a cyclic redundancy check (CRC) issued by the operating system, such as a disk error (certain hardware errors)</span></span>  
  
-   <span data-ttu-id="5b5f6-108">Un [error 824](../errors-events/mssqlserver-824-database-engine-error.md), como una página rasgada (cualquier error lógico)</span><span class="sxs-lookup"><span data-stu-id="5b5f6-108">An [824 error](../errors-events/mssqlserver-824-database-engine-error.md), such as a torn page (any logical error)</span></span>  
  
 <span data-ttu-id="5b5f6-109">El identificador de página de cada página sospechosa se registra en la tabla **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="5b5f6-109">The page ID of every suspect page is recorded in the **suspect_pages** table.</span></span> <span data-ttu-id="5b5f6-110">[!INCLUDE[ssDE](../../includes/ssde-md.md)] registra todas las páginas sospechosas que encuentra durante el procesamiento normal, como en estos casos:</span><span class="sxs-lookup"><span data-stu-id="5b5f6-110">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] records any suspect pages encountered during regular processing, such as the following:</span></span>  
  
-   <span data-ttu-id="5b5f6-111">Una consulta tiene que leer una página.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-111">A query has to read a page.</span></span>  
  
-   <span data-ttu-id="5b5f6-112">Durante una operación DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-112">During a DBCC CHECKDB operation.</span></span>  
  
-   <span data-ttu-id="5b5f6-113">Durante una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-113">During a backup operation.</span></span>  
  
 <span data-ttu-id="5b5f6-114">La tabla **suspect_pages** también se actualiza cuando es necesario durante una operación de restauración, una operación de reparación de DBCC o una operación de quitar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-114">The **suspect_pages** table is also updated as necessary during a restore operation, a DBCC repair operation, or a drop database operation.</span></span>  
  
 <span data-ttu-id="5b5f6-115">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b5f6-116">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b5f6-117">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5b5f6-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5b5f6-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b5f6-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b5f6-119">**Para administrar la tabla suspect_pages, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-119">**To manage the suspect_pages table, using:**</span></span>  
  
     [<span data-ttu-id="5b5f6-120">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b5f6-120">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b5f6-121">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b5f6-121">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b5f6-122">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5b5f6-122">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5b5f6-123">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5b5f6-123">Recommendations</span></span>  
  
-   <span data-ttu-id="5b5f6-124">**Errores registrados en la tabla suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-124">**Errors Recorded in suspect_pages Table**</span></span>  
  
     <span data-ttu-id="5b5f6-125">La tabla **suspect_pages** contiene una fila por cada página que causó un error 824, hasta un límite de 1000 filas.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-125">The **suspect_pages** table contains one row per page that failed with an 824 error, up to a limit of 1,000 rows.</span></span> <span data-ttu-id="5b5f6-126">En la siguiente tabla se muestran los errores registrados en la columna **event_type** de la tabla **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="5b5f6-126">The following table shows errors logged in the **event_type** column of the **suspect_pages** table.</span></span>  
  
    |<span data-ttu-id="5b5f6-127">Descripción del error</span><span class="sxs-lookup"><span data-stu-id="5b5f6-127">Error description</span></span>|<span data-ttu-id="5b5f6-128">Valor**event_type**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-128">**event_type** value</span></span>|  
    |-----------------------|---------------------------|  
    |<span data-ttu-id="5b5f6-129">Error 823 producido por un error de CRC del sistema operativo, o error 824 que no sea una suma de comprobación no válida o una página rasgada (por ejemplo, un Id. de página no válido)</span><span class="sxs-lookup"><span data-stu-id="5b5f6-129">823 error caused by an operating system CRC error  or 824 error other than a bad checksum or a torn page (for example, a bad page ID)</span></span>|<span data-ttu-id="5b5f6-130">1</span><span class="sxs-lookup"><span data-stu-id="5b5f6-130">1</span></span>|  
    |<span data-ttu-id="5b5f6-131">Suma de comprobación errónea</span><span class="sxs-lookup"><span data-stu-id="5b5f6-131">Bad checksum</span></span>|<span data-ttu-id="5b5f6-132">2</span><span class="sxs-lookup"><span data-stu-id="5b5f6-132">2</span></span>|  
    |<span data-ttu-id="5b5f6-133">Página rasgada</span><span class="sxs-lookup"><span data-stu-id="5b5f6-133">Torn page</span></span>|<span data-ttu-id="5b5f6-134">3</span><span class="sxs-lookup"><span data-stu-id="5b5f6-134">3</span></span>|  
    |<span data-ttu-id="5b5f6-135">Restaurada (la página se restauró después de marcarse como errónea)</span><span class="sxs-lookup"><span data-stu-id="5b5f6-135">Restored (The page was restored after it was marked bad)</span></span>|<span data-ttu-id="5b5f6-136">4</span><span class="sxs-lookup"><span data-stu-id="5b5f6-136">4</span></span>|  
    |<span data-ttu-id="5b5f6-137">Reparada (DBCC, AlwaysOn o la creación de reflejos han reparado la página).</span><span class="sxs-lookup"><span data-stu-id="5b5f6-137">Repaired (DBCC, AlwaysOn, or mirroring repaired the page)</span></span>|<span data-ttu-id="5b5f6-138">5</span><span class="sxs-lookup"><span data-stu-id="5b5f6-138">5</span></span>|  
    |<span data-ttu-id="5b5f6-139">Desasignada por DBCC</span><span class="sxs-lookup"><span data-stu-id="5b5f6-139">Deallocated by DBCC</span></span>|<span data-ttu-id="5b5f6-140">7</span><span class="sxs-lookup"><span data-stu-id="5b5f6-140">7</span></span>|  
  
     <span data-ttu-id="5b5f6-141">En la tabla **suspect_pages** también se registran errores transitorios.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-141">The **suspect_pages** table also records transient errors.</span></span> <span data-ttu-id="5b5f6-142">El origen de los errores transitorios puede ser un error de E/S (por ejemplo, un cable desconectado) o una página que genera un error temporal en una prueba de suma de comprobación repetida.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-142">Sources of transient errors include an I/O error (for example, a cable was disconnected) or a page that temporarily fails a repeated checksum test.</span></span>  
  
-   <span data-ttu-id="5b5f6-143">**Cómo actualiza el motor de base de datos la tabla suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-143">**How the Database Engine Updates the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="5b5f6-144">El [!INCLUDE[ssDE](../../includes/ssde-md.md)] realiza las siguientes acciones en la tabla **suspect_pages** :</span><span class="sxs-lookup"><span data-stu-id="5b5f6-144">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes the following actions on the **suspect_pages** table:</span></span>  
  
    -   <span data-ttu-id="5b5f6-145">Si la tabla no está llena, se actualiza para cada error 824, para indicar que se ha producido un error, y el contador de errores se incrementa.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-145">If the table is not full, it is updated for every 824 error, to indicate that an error has occurred, and the error counter is incremented.</span></span> <span data-ttu-id="5b5f6-146">Si una página tiene un error después de ser corregida mediante reparación, restauración o desasignación, su contador **number_of_errors** se incrementa y la columna **last_update** se actualiza.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-146">If a page has an error after it is fixed by being repaired, restored, or deallocated, its **number_of_errors** count is incremented and its **last_update** column is updated</span></span>  
  
    -   <span data-ttu-id="5b5f6-147">Después de corregir una página de la lista con una operación de restauración o de reparación, la operación actualiza la fila **suspect_pages** para indicar que la página está reparada (**event_type** = 5) o restaurada (**event_type** = 4).</span><span class="sxs-lookup"><span data-stu-id="5b5f6-147">After a listed page is fixed by a restore or a repair operation, the operation updates the **suspect_pages** row to indicate that the page is repaired (**event_type** = 5) or restored (**event_type** = 4).</span></span>  
  
    -   <span data-ttu-id="5b5f6-148">Si se ejecuta una comprobación DBCC, esta marca las páginas sin errores como reparadas (**event_type** = 5) o desasignadas (**event_type** = 7).</span><span class="sxs-lookup"><span data-stu-id="5b5f6-148">If a DBCC check is run, the check marks any error-free pages as repaired (**event_type** = 5) or deallocated (**event_type** = 7).</span></span>  
  
-   <span data-ttu-id="5b5f6-149">**Actualizaciones automáticas de la tabla suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-149">**Automatic Updates to the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="5b5f6-150">Un asociado de creación de reflejo de la base de datos o réplica de disponibilidad AlwaysOn actualiza la tabla **suspect_pages** después de un error en un intento de leer una página de un archivo de datos por una de las razones siguientes.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-150">A database mirroring partner or AlwaysOn availability replica updates the **suspect_pages** table after an attempt to read a page from a data file fails for one of the following reasons.</span></span>  
  
    -   <span data-ttu-id="5b5f6-151">Error 823 error producido por un error de CRC del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="5b5f6-151">An 823 error that is caused by an operating system CRC error.</span></span>  
  
    -   <span data-ttu-id="5b5f6-152">Error 824, (error lógico, como una página rasgada)</span><span class="sxs-lookup"><span data-stu-id="5b5f6-152">An 824 error (logical corruption such as a torn page).</span></span>  
  
     <span data-ttu-id="5b5f6-153">Las siguientes acciones también actualizan automáticamente las filas de la tabla **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="5b5f6-153">The following actions also automatically update rows in the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="5b5f6-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS actualiza la tabla **suspect_pages** para indicar cada página que se ha reparado o desasignado.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS updates the **suspect_pages** table to indicate each page that it has deallocated or repaired.</span></span>  
  
    -   <span data-ttu-id="5b5f6-155">Una operación de restauración RESTORE completa, de archivos o de páginas marca las entradas de página como restauradas.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-155">A full, file, or page RESTORE marks the page entries as restored.</span></span>  
  
     <span data-ttu-id="5b5f6-156">Las siguientes acciones eliminan automáticamente filas de la tabla **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="5b5f6-156">The following actions automatically delete rows from the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="5b5f6-157">ALTER DATABASE REMOVE FILE</span><span class="sxs-lookup"><span data-stu-id="5b5f6-157">ALTER DATABASE REMOVE FILE</span></span>  
  
    -   <span data-ttu-id="5b5f6-158">DROP DATABASE</span><span class="sxs-lookup"><span data-stu-id="5b5f6-158">DROP DATABASE</span></span>  
  
-   <span data-ttu-id="5b5f6-159">**Rol de mantenimiento del administrador de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="5b5f6-159">**Maintenance Role of the Database Administrator**</span></span>  
  
     <span data-ttu-id="5b5f6-160">Los administradores de bases de datos son responsables de la administración de la tabla, sobre todo de eliminar las filas antiguas.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-160">Database administrators are responsible for managing the table, primarily by deleting old rows.</span></span> <span data-ttu-id="5b5f6-161">La tabla **suspect_pages** tiene un tamaño limitado; si se llena, los errores nuevos no se registrarán.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-161">The **suspect_pages** table is limited in size, and if it fills, new errors are not logged.</span></span> <span data-ttu-id="5b5f6-162">Para evitar que esta tabla se llene, el administrador de la base de datos o el administrador del sistema debe borrar manualmente las entradas antiguas de la tabla eliminando filas.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-162">To prevent this table from filling up, the database administrator or system administrator must manually clear out old entries from this table by deleting rows.</span></span> <span data-ttu-id="5b5f6-163">Por tanto, recomendamos que elimine o archive periódicamente las filas cuyo **event_type** se ha restaurado o reparado o las filas que tengan un valor **last_update** antiguo.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-163">Therefore, we recommend that you periodically delete or archive rows that have an **event_type** of restored or repaired, or rows that have an old **last_update** value.</span></span>  
  
     <span data-ttu-id="5b5f6-164">Para supervisar la actividad en la tabla suspect_pages, puede usar la clase de eventos [Database Suspect Data Page](../event-classes/database-suspect-data-page-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="5b5f6-164">To monitor the activity on the suspect_pages table, you can use the [Database Suspect Data Page Event Class](../event-classes/database-suspect-data-page-event-class.md).</span></span> <span data-ttu-id="5b5f6-165">A veces, se agregan filas a la tabla **suspect_pages** debido a errores transitorios.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-165">Rows are sometimes added to the **suspect_pages** table because of transient errors.</span></span> <span data-ttu-id="5b5f6-166">Si se agregan muchas filas a la tabla, sin embargo, es probable que haya un problema con el subsistema de E/S.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-166">If many rows are being added to the table, however, a problem probably exists with the I/O subsystem.</span></span> <span data-ttu-id="5b5f6-167">Si observa un aumento repentino en el número de filas que se agregan a la tabla, recomendamos que investigue los posibles problemas en el subsistema de E/S.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-167">If you notice a sudden increase in the number of rows being added to the table, we recommend that you investigate possible problems in your I/O subsystem.</span></span>  
  
     <span data-ttu-id="5b5f6-168">Un administrador de la base de datos también puede insertar o actualizar registros.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-168">A database administrator can also insert or update records.</span></span> <span data-ttu-id="5b5f6-169">Por ejemplo, actualizar una fila puede resultar útil cuando el administrador de la base de datos sabe que una determinada página sospechosa está intacta realmente, pero desea preservar el registro durante un tiempo.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-169">For example, updating a row might useful when the database administrator knows that a particular suspect page is actually intact, but wants to preserve the record for a while.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b5f6-170">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b5f6-170">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b5f6-171">Permisos</span><span class="sxs-lookup"><span data-stu-id="5b5f6-171">Permissions</span></span>  
 <span data-ttu-id="5b5f6-172">Cualquier persona con acceso a **msdb** puede leer los datos de la tabla **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="5b5f6-172">Anyone with access to **msdb** can read the data in the **suspect_pages** table.</span></span> <span data-ttu-id="5b5f6-173">Cualquier persona con el permiso UPDATE en la tabla suspect_pages puede actualizar sus registros.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-173">Anyone with UPDATE permission on the suspect_pages table can update its records.</span></span> <span data-ttu-id="5b5f6-174">Los miembros del rol fijo de base de datos **db_owner** de **msdb** o el rol fijo de servidor **sysadmin** pueden insertar, actualizar y eliminar registros.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-174">Members the **db_owner** fixed database role on **msdb** or the **sysadmin** fixed server role can insert, update, and delete records.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b5f6-175">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b5f6-175">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="5b5f6-176">Para administrar la tabla suspect_pages</span><span class="sxs-lookup"><span data-stu-id="5b5f6-176">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="5b5f6-177">En el **Explorador de objetos**, conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expándala y, a continuación, expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-177">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="5b5f6-178">Expanda **Bases de datos del sistema**, expanda **msdb**, expanda **Tablas**y, por último, expanda **Tablas del sistema**.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-178">Expand **System Databases**, expand **msdb**, expand **Tables**, and then expand **System Tables**.</span></span>  
  
3.  <span data-ttu-id="5b5f6-179">Expanda **dbo.suspect_pages** y haga clic con el botón derecho en **Editar las 200 primeras filas**.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-179">Expand **dbo.suspect_pages** and right-click **Edit Top 200 Rows**.</span></span>  
  
4.  <span data-ttu-id="5b5f6-180">En la ventana de consulta, edite, actualice o elimine las filas que desee.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-180">In the query window, edit, update, or delete the rows that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b5f6-181">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b5f6-181">Using Transact-SQL</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="5b5f6-182">Para administrar la tabla suspect_pages</span><span class="sxs-lookup"><span data-stu-id="5b5f6-182">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="5b5f6-183">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b5f6-183">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b5f6-184">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-184">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b5f6-185">Copie y pegue los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5b5f6-185">Copy and paste the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="5b5f6-186">En este ejemplo se eliminan algunas filas de la tabla `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="5b5f6-186">This example deletes some of the rows from the `suspect_pages` table.</span></span>  
  
```  
-- Delete restored, repaired, or deallocated pages.  
DELETE FROM msdb..suspect_pages  
   WHERE (event_type = 4 OR event_type = 5 OR event_type = 7);  
GO  
  
```  
  
 <span data-ttu-id="5b5f6-187">E este ejemplo se devuelve las páginas no válidas de la tabla `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="5b5f6-187">This example returns the bad pages in the `suspect_pages` table.</span></span>  
  
```  
-- Select nonspecific 824, bad checksum, and torn page errors.  
SELECT * FROM msdb..suspect_pages  
   WHERE (event_type = 1 OR event_type = 2 OR event_type = 3);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b5f6-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b5f6-188">See Also</span></span>  
 <span data-ttu-id="5b5f6-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b5f6-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 <span data-ttu-id="5b5f6-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b5f6-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="5b5f6-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b5f6-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="5b5f6-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b5f6-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="5b5f6-193">[Restaurar páginas &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b5f6-193">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 <span data-ttu-id="5b5f6-194">[suspect_pages &#40;&#41;de Transact-SQL](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b5f6-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span></span>  
 <span data-ttu-id="5b5f6-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="5b5f6-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span></span>  
 [<span data-ttu-id="5b5f6-196">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="5b5f6-196">MSSQLSERVER_824</span></span>](../errors-events/mssqlserver-824-database-engine-error.md)  
  
  
