---
title: Crear un paso de trabajo de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [Analysis Services]
ms.assetid: 03d4bb86-514b-4a55-97b9-c2c0fa08b428
author: stevestein
ms.author: sstein
ms.openlocfilehash: ed0e63c22d4cad270bcb544b03decba269e4f43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745649"
---
# <a name="create-an-analysis-services-job-step"></a><span data-ttu-id="cf633-102">Create an Analysis Services Job Step</span><span class="sxs-lookup"><span data-stu-id="cf633-102">Create an Analysis Services Job Step</span></span>
  <span data-ttu-id="cf633-103">En este tema se describe cómo crear y definir los pasos de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que ejecutan comandos y consultas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] u Objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cf633-103">This topic describes how to create and define [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services commands and queries by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="cf633-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="cf633-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cf633-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="cf633-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cf633-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cf633-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cf633-107">**Para crear pasos de trabajo de SQL Server utilizando comandos y/o consultas de Analysis Services, con:**</span><span class="sxs-lookup"><span data-stu-id="cf633-107">**To create a SQL Server job steps using Analysis Services commands and/or queries, with:**</span></span>  
  
     [<span data-ttu-id="cf633-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf633-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="cf633-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf633-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="cf633-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cf633-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cf633-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="cf633-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cf633-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="cf633-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cf633-113">Si el paso de trabajo utiliza un comando de Analysis Services, la instrucción de comando debe ser un método **Execute** de XML for Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cf633-113">If the job step uses an Analysis Services command, the command statement must be an XML for Analysis Services **Execute** method.</span></span> <span data-ttu-id="cf633-114">Puede que la instrucción no contenga un sobre SOAP (Protocolo simple de acceso a objetos) completo o un método **Discover** de XML for Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cf633-114">The statement may not contain a complete Simple Object Access Protocol (SOAP) envelope or an XML for Analysis **Discover** method.</span></span> <span data-ttu-id="cf633-115">Mientras [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] admite sobres SOAP (Protocolo simple de acceso a objetos) completos y el método **Discover** , los pasos de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no los admiten.</span><span class="sxs-lookup"><span data-stu-id="cf633-115">While [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] supports complete SOAP envelopes and the **Discover** method, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps do not.</span></span> <span data-ttu-id="cf633-116">Para más información sobre XML for Analysis Services, consulte [Información general de XML for Analysis (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf633-116">For more information about XML for Analysis Services, see [XML for Analysis Overview (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span></span>  
  
-   <span data-ttu-id="cf633-117">Si el paso de trabajo utiliza una consulta de Analysis Services, la instrucción de consulta debe ser una consulta de expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="cf633-117">If the job step uses an Analysis Services query, the query statement must be a multidimensional expressions (MDX) query.</span></span> <span data-ttu-id="cf633-118">Para obtener más información sobre MDX, consulte [aspectos básicos de las consultas mdx &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="cf633-118">For more information about MDX, see [MDX Query Fundamentals &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cf633-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cf633-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cf633-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="cf633-120">Permissions</span></span>  
  
-   <span data-ttu-id="cf633-121">Para ejecutar un paso de trabajo que utilice el subsistema de Analysis Services, un usuario debe ser miembro del rol fijo de servidor **sysadmin** o tener acceso a una cuenta de proxy válida definida para utilizar este subsistema.</span><span class="sxs-lookup"><span data-stu-id="cf633-121">To run a job step that uses the Analysis Services subsystem, a user must be a member of the **sysadmin** fixed server role or have access to a valid proxy account defined to use this subsystem.</span></span> <span data-ttu-id="cf633-122">Además, la cuenta de servicio o el proxy del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deben ser un administrador de Analysis Services y una cuenta de dominio de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="cf633-122">In addition, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account or the proxy must be an Analysis Services administrator and a valid Windows domain account.</span></span>  
  
-   <span data-ttu-id="cf633-123">Los miembros del rol fijo de servidor **sysadmin** son los únicos que pueden escribir la salida de un paso de trabajo en un archivo.</span><span class="sxs-lookup"><span data-stu-id="cf633-123">Only members of the **sysadmin** fixed server role can write job step output to a file.</span></span> <span data-ttu-id="cf633-124">Si ejecutan el paso de trabajo usuarios miembros del rol de base de datos **SQLAgentUserRole** en la base de datos **msdb** , solo se podrá escribir la salida en una tabla.</span><span class="sxs-lookup"><span data-stu-id="cf633-124">If the job step is run by users who are members of the **SQLAgentUserRole** database role in the **msdb** database, then the output can be written only to a table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="cf633-125">El agente escribe la salida del paso de trabajo en la tabla **sysjobstepslog** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="cf633-125">Agent writes job step output to the **sysjobstepslog** table in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="cf633-126">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="cf633-126">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="cf633-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf633-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="cf633-128">Para crear un paso de trabajo de comando de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cf633-128">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="cf633-129">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="cf633-129">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cf633-130">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cf633-130">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="cf633-131">Para más información sobre cómo crear un trabajo, consulte [Crear trabajos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="cf633-131">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="cf633-132">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cf633-132">In the **Job Properties** dialog box, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="cf633-133">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un **Nombre del paso**del trabajo.</span><span class="sxs-lookup"><span data-stu-id="cf633-133">In the **New Job Step** dialog box, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="cf633-134">En la lista **Tipo** , haga clic en **Comando de SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="cf633-134">In the **Type** list, click **SQL Server Analysis Services Command**.</span></span>  
  
6.  <span data-ttu-id="cf633-135">En la lista **Ejecutar como** , seleccione un proxy que se haya definido para utilizar el subsistema de comandos de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cf633-135">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Command subsystem.</span></span> <span data-ttu-id="cf633-136">Los usuarios miembros del rol fijo de servidor **sysadmin** también pueden seleccionar **Cuenta del servicio del Agente SQL** para ejecutar este paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cf633-136">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="cf633-137">Seleccione el **Servidor** en el que se ejecutará el paso de trabajo o escriba su nombre.</span><span class="sxs-lookup"><span data-stu-id="cf633-137">Select the **Server** where the job step will run, or type the server name.</span></span>  
  
8.  <span data-ttu-id="cf633-138">En el cuadro **Comando** , escriba la instrucción que se debe ejecutar o haga clic en **Abrir** para seleccionar una instrucción.</span><span class="sxs-lookup"><span data-stu-id="cf633-138">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="cf633-139">Haga clic en la página **Avanzadas** para definir opciones para este paso de trabajo, como la acción que debe realizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si el paso de trabajo se realiza correctamente o con errores, las veces que se debe intentar ejecutar el paso de trabajo y el lugar en el que se debe escribir la salida.</span><span class="sxs-lookup"><span data-stu-id="cf633-139">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="cf633-140">Para crear un paso de trabajo de consulta de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cf633-140">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="cf633-141">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="cf633-141">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cf633-142">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cf633-142">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="cf633-143">Para más información sobre cómo crear un trabajo, consulte [Crear trabajos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="cf633-143">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="cf633-144">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cf633-144">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="cf633-145">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre para el paso de trabajo en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="cf633-145">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="cf633-146">En la lista **Tipo** , haga clic en **Consulta de SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="cf633-146">In the **Type** list, click **SQL Server Analysis Services Query**.</span></span>  
  
6.  <span data-ttu-id="cf633-147">En la lista **Ejecutar como** , seleccione un proxy que se haya definido para utilizar el subsistema de consultas de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cf633-147">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Query subsystem.</span></span> <span data-ttu-id="cf633-148">Los usuarios miembros del rol fijo de servidor **sysadmin** también pueden seleccionar **Cuenta del servicio del Agente SQL** para ejecutar este paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cf633-148">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="cf633-149">Seleccione el **Servidor** y la **Base de datos** en los que se ejecutará el paso de trabajo o escriba sus nombres.</span><span class="sxs-lookup"><span data-stu-id="cf633-149">Select the **Server** and the **Database** where the job step will run, or type the server or database name.</span></span>  
  
8.  <span data-ttu-id="cf633-150">En el cuadro **Comando** , escriba la instrucción que se debe ejecutar o haga clic en **Abrir** para seleccionar una instrucción.</span><span class="sxs-lookup"><span data-stu-id="cf633-150">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="cf633-151">Haga clic en la página **Avanzadas** para definir opciones para este paso de trabajo, como la acción que debe realizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si el paso de trabajo se realiza correctamente o con errores, las veces que se debe intentar ejecutar el paso de trabajo y el lugar en el que se debe escribir la salida.</span><span class="sxs-lookup"><span data-stu-id="cf633-151">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="cf633-152">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf633-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="cf633-153">Para crear un paso de trabajo de comando de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cf633-153">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="cf633-154">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf633-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf633-155">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cf633-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cf633-156">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cf633-156">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses XMLA to create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database ',  
        @subsystem = N'ANALYSISCOMMAND',  
        @command = N' <Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
        <ParentObject>  
            <DatabaseID>AdventureWorks2012</DatabaseID>  
        </ParentObject>  
        <ObjectDefinition>  
            <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
                <ID>AdventureWorks2012</ID>  
                <Name>Adventure Works 2012</Name>  
                <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorks2012;Integrated Security=True</ConnectionString>  
                <ImpersonationInfo>  
                    <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
                </ImpersonationInfo>  
                <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
                <Timeout>PT0S</Timeout>  
            </DataSource>  
        </ObjectDefinition>  
    </Create>', ;  
    GO  
    ```  
  
 <span data-ttu-id="cf633-157">Para obtener más información, vea [sp_add_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cf633-157">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="cf633-158">Para crear un paso de trabajo de consulta de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cf633-158">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="cf633-159">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf633-159">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf633-160">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cf633-160">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cf633-161">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cf633-161">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses MDX to return data  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Returns the Internet sales amount by state',  
        @subsystem = N'ANALYSISQUERY',  
        @command = N' SELECT  
       [Measures].[Internet Sales Amount] ON COLUMNS,  
       [Customer].[State-Province].Members ON ROWS  
    FROM [AdventureWorks2012]',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="cf633-162">Para obtener más información, vea [sp_add_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cf633-162">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="cf633-163">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cf633-163">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="cf633-164">**Para crear un paso de trabajo para script de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cf633-164">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="cf633-165">Utilice la clase `JobStep` con un lenguaje de programación que seleccione, por ejemplo XMLA o MDX.</span><span class="sxs-lookup"><span data-stu-id="cf633-165">Use the `JobStep` class by using a programming language that you choose, such as XMLA or MDX.</span></span> <span data-ttu-id="cf633-166">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf633-166">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
