---
title: Creación de un trabajo del Agente SQL Server para archivar mensajes y registros de eventos del Correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- archiving mail messages and attachments [SQL Server]
- removing mail messages and attachements
- Database Mail [SQL Server], archiving
- saving mail messages and attachments
ms.assetid: 8f8f0fba-f750-4533-9b76-a9cdbcdc3b14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b958b280c358a8aeb752600dee1c2aee31d14db1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671094"
---
# <a name="create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs"></a><span data-ttu-id="1c2fc-102">Crear un trabajo del Agente SQL Server para archivar mensajes y registros de eventos del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-102">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>
  <span data-ttu-id="1c2fc-103">Las tablas **msdb** mantienen copias de los mensajes del Correo electrónico de base de datos y sus datos adjuntos, además del registro de eventos del Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-103">Copies of Database Mail messages and their attachments are retained in **msdb** tables along with the Database Mail event log.</span></span> <span data-ttu-id="1c2fc-104">Puede reducir el tamaño de las tablas y eliminar los mensajes y eventos que ya no sean necesarios periódicamente.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-104">Periodically you might want to reduce the size of the tables and archive messages and events that are no longer needed.</span></span> <span data-ttu-id="1c2fc-105">Los procedimientos siguientes permiten crear un trabajo del Agente SQL Server para automatizar el proceso.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-105">The following procedures create a SQL Server Agent job to automate the process.</span></span>  
  
-   <span data-ttu-id="1c2fc-106">**Antes de empezar:**  , [Requisitos previos](#Prerequisites), [Recomendaciones](#Recommendations), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="1c2fc-106">**Before you begin:**  , [Prerequisites](#Prerequisites), [Recommendations](#Recommendations), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="1c2fc-107">**Para almacenar mensajes y los registros de Correo electrónico de base de datos mediante:**  [Agente SQL Server](#Process_Overview)</span><span class="sxs-lookup"><span data-stu-id="1c2fc-107">**To Archive Database Mail messages and logs using :**  [SQL Server Agent](#Process_Overview)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1c2fc-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1c2fc-108">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1c2fc-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-109">Prerequisites</span></span>  
 <span data-ttu-id="1c2fc-110">Las nuevas tablas para almacenar los datos del archivo se pueden ubicar en una base de datos de archivo especial.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-110">The new tables to store the archive data might be located in a special archive database.</span></span> <span data-ttu-id="1c2fc-111">De forma alternativa, las filas se pudieron exportar a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-111">Alternatively the rows could be exported to a text file.</span></span>  
 
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1c2fc-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="1c2fc-112">Recommendations</span></span>  
 <span data-ttu-id="1c2fc-113">En su entorno de producción, puede agregar otros procedimientos de comprobación de errores y enviar un mensaje de correo electrónico a los operadores si el trabajo provoca un error.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-113">In your production environment, you might want to add additional error checking and send an e-mail message to operators if the job fails.</span></span>  
  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1c2fc-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-114">Permissions</span></span>  
 <span data-ttu-id="1c2fc-115">Debe ser miembro del rol fijo de servidor **sysadmin** para ejecutar los procedimientos almacenados que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-115">You must be a member of the **sysadmin** fixed server role to execute the stored procedures described in this topic.</span></span>  
  
  
###  <a name="overview-of-the-process"></a><a name="Process_Overview"></a> <span data-ttu-id="1c2fc-116">Información general acerca del proceso de inicialización</span><span class="sxs-lookup"><span data-stu-id="1c2fc-116">Overview of the Process</span></span>  
  
-   <span data-ttu-id="1c2fc-117">En el primer procedimiento se crea con cuatro pasos un trabajo denominado Archivar mensajes del Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-117">The first procedure creates a job named Archive Database Mail with the following steps.</span></span>  
  
    1.  <span data-ttu-id="1c2fc-118">Copiar todos los mensajes de las tablas del Correo electrónico de base de datos en una nueva tabla con el nombre del mes anterior en el formato **DBMailArchive_** _<año_mes>_ .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-118">Copy all messages from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_**_<year_month>_.</span></span>  
  
    2.  <span data-ttu-id="1c2fc-119">Copiar todos los datos adjuntos relacionados con los mensajes copiados en el primer paso, de las tablas del Correo electrónico de base de datos en una nueva tabla con el nombre del mes anterior en el formato **DBMailArchive_Attachments_** _<año_mes>_ .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-119">Copy the attachments related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Attachments_**_<year_month>_.</span></span>  
  
    3.  <span data-ttu-id="1c2fc-120">Copiar todos los eventos del registro de eventos del Correo electrónico de base de datos relacionados con los mensajes copiados en el primer paso, de las tablas del Correo electrónico de base de datos en una nueva tabla con el nombre del mes anterior en el formato **DBMailArchive_Log_** _<año_mes>_ .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-120">Copy the events from the Database Mail event log that are related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Log_**_<year_month>_.</span></span>  
  
    4.  <span data-ttu-id="1c2fc-121">Eliminar los registros de los elementos de correo transferidos de las tablas del Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-121">Delete the records of the transferred mail items from the Database Mail tables.</span></span>  
  
    5.  <span data-ttu-id="1c2fc-122">Eliminar los eventos relacionados con los elementos de correo transferidos del registro de eventos del Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-122">Delete the events related to the transferred mail items from the Database Mail event log.</span></span>  
  
-   <span data-ttu-id="1c2fc-123">Programar el trabajo para ejecutar periódicamente.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-123">Schedule the job to run periodically.</span></span>  
 
  
## <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="1c2fc-124">Para crear un trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="1c2fc-124">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="1c2fc-125">En el Explorador de objetos, expanda el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , haga clic con el botón derecho en **Trabajos**y, después, haga clic en **Nuevo trabajo**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-125">In Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, and then click **New Job**.</span></span>  
  
2.  <span data-ttu-id="1c2fc-126">En el cuadro **Nombre** del cuadro de diálogo **Nuevo trabajo** , escriba **Archivar mensajes del Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-126">In the **New Job** dialog box, in the **Name** box, type **Archive Database Mail**.</span></span>  
  
3.  <span data-ttu-id="1c2fc-127">En el cuadro **Propietario** , confirme que el propietario es miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-127">In the **Owner** box, confirm that the owner is a member of the **sysadmin** fixed server role.</span></span>  
  
4.  <span data-ttu-id="1c2fc-128">En el cuadro **Categoría** , haga clic en **Mantenimiento de bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-128">In the **Category** box, click the **Database Maintenance**.</span></span>  
  
5.  <span data-ttu-id="1c2fc-129">En el cuadro **Descripción** , escriba **Archivar mensajes del Correo electrónico de base de datos**y, a continuación, haga clic en **Pasos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-129">In the **Description** box, type **Archive Database Mail messages**, and then click **Steps**.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-messages"></a><span data-ttu-id="1c2fc-130">Crear un paso para archivar los mensajes del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-130">To create a step to archive the Database Mail messages</span></span>  
  
1.  <span data-ttu-id="1c2fc-131">En la página **Pasos** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-131">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="1c2fc-132">En el cuadro **Nombre del paso** , escriba **Copiar elementos del Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-132">In the **Step name** box, type **Copy Database Mail Items**.</span></span>  
  
3.  <span data-ttu-id="1c2fc-133">En el cuadro **Tipo** , seleccione **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-133">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="1c2fc-134">En el cuadro **Base de datos** , seleccione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-134">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="1c2fc-135">En el cuadro **Comando** , escriba la instrucción siguiente para crear una tabla con el nombre del mes anterior y filas anteriores al inicio del mes actual:</span><span class="sxs-lookup"><span data-stu-id="1c2fc-135">In the **Command** box, type the following statement to create a table named after the previous month, containing rows older than the start of the current month:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_' + @LastMonth + '] FROM sysmail_allitems WHERE send_request_date < ''' + @CopyDate +'''';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="1c2fc-136">Haga clic en **Aceptar** para guardar el paso.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-136">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-attachments"></a><span data-ttu-id="1c2fc-137">Crear un paso para archivar los datos adjuntos del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-137">To create a step to archive the Database Mail attachments</span></span>  
  
1.  <span data-ttu-id="1c2fc-138">En la página **Pasos** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-138">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="1c2fc-139">En el cuadro **Nombre del paso** , escriba **Copiar datos adjuntos del Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-139">In the **Step name** box, type **Copy Database Mail Attachments**.</span></span>  
  
3.  <span data-ttu-id="1c2fc-140">En el cuadro **Tipo** , seleccione **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-140">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="1c2fc-141">En el cuadro **Base de datos** , seleccione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-141">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="1c2fc-142">En el cuadro **Comando** , escriba la instrucción siguiente para crear una tabla de datos adjuntos con el nombre del mes anterior y los archivos adjuntos correspondientes a los mensajes transferidos en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="1c2fc-142">In the **Command** box, type the following statement to create an attachments table named after the previous month, containing the attachments that correspond to the messages transferred in the previous step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Attachments_' + @LastMonth + '] FROM sysmail_attachments   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="1c2fc-143">Haga clic en **Aceptar** para guardar el paso.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-143">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-log"></a><span data-ttu-id="1c2fc-144">Crear un paso para archivar el registro del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-144">To create a step to archive the Database Mail log</span></span>  
  
1.  <span data-ttu-id="1c2fc-145">En la página **Pasos** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-145">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="1c2fc-146">En el cuadro **Nombre del paso** , escriba **Copiar el registro del Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-146">In the **Step name** box, type **Copy Database Mail Log**.</span></span>  
  
3.  <span data-ttu-id="1c2fc-147">En el cuadro **Tipo** , seleccione **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-147">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="1c2fc-148">En el cuadro **Base de datos** , seleccione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-148">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="1c2fc-149">En el cuadro **Comando** , escriba la instrucción siguiente para crear una tabla de registros con el nombre del mes anterior y las entradas de registro correspondientes a los mensajes transferidos en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="1c2fc-149">In the **Command** box, type the following statement to create a log table named after the previous month, containing the log entries that correspond to the messages transferred in the earlier step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Log_' + @LastMonth + '] FROM sysmail_Event_Log   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="1c2fc-150">Haga clic en **Aceptar** para guardar el paso.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-150">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-rows-from-database-mail"></a><span data-ttu-id="1c2fc-151">Crear un paso para quitar las filas archivadas del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-151">To create a step to remove the archived rows from Database Mail</span></span>  
  
1.  <span data-ttu-id="1c2fc-152">En la página **Pasos** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-152">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="1c2fc-153">En el cuadro **Nombre del paso** , escriba **Eliminar filas del Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-153">In the **Step name** box, type **Remove rows from Database Mail**.</span></span>  
  
3.  <span data-ttu-id="1c2fc-154">En el cuadro **Tipo** , seleccione **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-154">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="1c2fc-155">En el cuadro **Base de datos** , seleccione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-155">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="1c2fc-156">En el cuadro **Comando** , escriba la instrucción siguiente para quitar las filas anteriores al mes actual de las tablas del Correo electrónico de base de datos:</span><span class="sxs-lookup"><span data-stu-id="1c2fc-156">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail tables:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_mailitems_sp @sent_before = @CopyDate ;  
    ```  
  
6.  <span data-ttu-id="1c2fc-157">Haga clic en **Aceptar** para guardar el paso.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-157">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-items-from-database-mail-event-log"></a><span data-ttu-id="1c2fc-158">Crear un paso para quitar los elementos archivados del registro de eventos del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="1c2fc-158">To create a step to remove the archived items from Database Mail event log</span></span>  
  
1.  <span data-ttu-id="1c2fc-159">En la página **Pasos** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-159">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="1c2fc-160">En el cuadro **Nombre del paso** , escriba **Eliminar filas del registro de eventos del Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-160">In the **Step Name** box type **Remove rows from Database Mail event log**.</span></span>  
  
3.  <span data-ttu-id="1c2fc-161">En el cuadro **Tipo** , seleccione **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-161">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="1c2fc-162">En el cuadro **Comando** , escriba la instrucción siguiente para quitar las filas anteriores al mes actual del registro de eventos del Correo electrónico de base de datos:</span><span class="sxs-lookup"><span data-stu-id="1c2fc-162">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail event log:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_log_sp @logged_before = @CopyDate ;  
    ```  
  
5.  <span data-ttu-id="1c2fc-163">Haga clic en **Aceptar** para guardar el paso.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-163">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-schedule-the-job-to-run-periodically"></a><span data-ttu-id="1c2fc-164">Para programar el trabajo para ejecutar periódicamente</span><span class="sxs-lookup"><span data-stu-id="1c2fc-164">To schedule the job to run periodically</span></span>  
  
1.  <span data-ttu-id="1c2fc-165">En el cuadro de diálogo **Nuevo trabajo** , haga clic en **Programaciones**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-165">In the **New Job** dialog box, click **Schedules**.</span></span>  
  
2.  <span data-ttu-id="1c2fc-166">En la página **Programaciones** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-166">On the **Schedules** page, click **New**.</span></span>  
  
3.  <span data-ttu-id="1c2fc-167">En el cuadro **Nombre** , escriba **Archivar mensajes del Correo electrónico de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-167">In the **Name** box, type **Archive Database Mail**.</span></span>  
  
4.  <span data-ttu-id="1c2fc-168">En el cuadro **Tipo de programación** , seleccione **Periódica**.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-168">In the **Schedule type** box, select **Recurring**.</span></span>  
  
5.  <span data-ttu-id="1c2fc-169">En el área **Frecuencia** , seleccione las opciones para ejecutar el trabajo periódicamente, por ejemplo una vez al mes.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-169">In the **Frequency** area, select the options to run the job periodically, for example once every month.</span></span>  
  
6.  <span data-ttu-id="1c2fc-170">En el área **Frecuencia diaria**, seleccione **Sucede una vez a las \<time>** .</span><span class="sxs-lookup"><span data-stu-id="1c2fc-170">In the **Daily frequency** area, select **Occurs once at \<time>**.</span></span>  
  
7.  <span data-ttu-id="1c2fc-171">Compruebe que las demás opciones están configuradas tal como desea y, a continuación, haga clic en **Aceptar** para guardar la programación.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-171">Verify that the other options are configured as you wish, and then click **OK** to save the schedule.</span></span>  
  
8.  <span data-ttu-id="1c2fc-172">Haga clic en **Aceptar** para guardar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1c2fc-172">Click **OK** to save the job.</span></span>  
  
  
  
  
