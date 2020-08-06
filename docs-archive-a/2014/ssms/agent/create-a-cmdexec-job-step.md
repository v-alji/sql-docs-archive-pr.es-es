---
title: Crear un paso de trabajo CmdExec | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CmdExec jobs
ms.assetid: b48da5b4-6fe7-4eb7-bade-dc7d697c6d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48c557b8ea4228d27b73d361c50aac62232d1e00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672352"
---
# <a name="create-a-cmdexec-job-step"></a><span data-ttu-id="5d84e-102">Create a CmdExec Job Step</span><span class="sxs-lookup"><span data-stu-id="5d84e-102">Create a CmdExec Job Step</span></span>
  <span data-ttu-id="5d84e-103">En este tema se describe cómo crear y definir un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] paso de trabajo [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] del agente en que usa un programa ejecutable o un comando del sistema operativo mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d84e-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that uses an executable program or operating system command by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="5d84e-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5d84e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5d84e-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5d84e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5d84e-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5d84e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5d84e-107">**Para crear un paso de trabajo de CmdExec, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="5d84e-107">**To create a CmdExec job step, using:**</span></span>  
  
     [<span data-ttu-id="5d84e-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d84e-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="5d84e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d84e-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="5d84e-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d84e-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d84e-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5d84e-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d84e-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5d84e-112">Security</span></span>  
 <span data-ttu-id="5d84e-113">De forma predeterminada, solo los miembros del rol fijo de servidor **sysadmin** pueden crear pasos de trabajo CmdExec.</span><span class="sxs-lookup"><span data-stu-id="5d84e-113">By default, only members of the **sysadmin** fixed server role can create CmdExec job steps.</span></span> <span data-ttu-id="5d84e-114">Estos pasos de trabajo se ejecutan en el contexto de la cuenta de servicio de Agente SQL Server salvo que el usuario **sysadmin** cree una cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="5d84e-114">These job steps run under the context of the SQL Server Agent service account unless the **sysadmin** user creates a proxy account.</span></span> <span data-ttu-id="5d84e-115">Los usuarios que no sean miembros del rol **sysadmin** pueden crear pasos de trabajo CmdExec si disponen de acceso a la cuenta de proxy CmdExec.</span><span class="sxs-lookup"><span data-stu-id="5d84e-115">Users who are not members of the **sysadmin** role can create CmdExec job steps if they have access to a CmdExec proxy account.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d84e-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="5d84e-116">Permissions</span></span>  
 <span data-ttu-id="5d84e-117">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5d84e-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5d84e-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d84e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="5d84e-119">Para crear un paso de trabajo de CmdExec</span><span class="sxs-lookup"><span data-stu-id="5d84e-119">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="5d84e-120">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="5d84e-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5d84e-121">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5d84e-121">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5d84e-122">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5d84e-122">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="5d84e-123">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre para el paso de trabajo en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="5d84e-123">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="5d84e-124">En la lista **Tipo** , elija **Sistema operativo (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="5d84e-124">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
6.  <span data-ttu-id="5d84e-125">En la lista **Ejecutar como** , seleccione la cuenta e proxy con las credenciales que utilizará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d84e-125">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="5d84e-126">De forma predeterminada, los pasos de trabajo de CmdExec se ejecutan en el contexto de la cuenta de servicio de Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d84e-126">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
7.  <span data-ttu-id="5d84e-127">En el cuadro **Procesar código de salida de un comando correcto** , escriba un valor de 0 a 999999.</span><span class="sxs-lookup"><span data-stu-id="5d84e-127">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
8.  <span data-ttu-id="5d84e-128">En el cuadro **Comando** , escriba el comando del sistema operativo o el programa ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5d84e-128">In the **Command** box, enter the operating system command or executable program.</span></span> <span data-ttu-id="5d84e-129">Vea "Usar T-Transact T-SQL" para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5d84e-129">See "Using Transact T-SQL for an example.</span></span>  
  
9. <span data-ttu-id="5d84e-130">Haga clic en la página **Avanzadas** para configurar las opciones del paso de trabajo como, por ejemplo: la acción que se realizará si el paso de trabajo es correcto o si es erróneo, el número de veces que Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intentará ejecutar el paso de trabajo y el archivo en el que Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede escribir la salida del paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d84e-130">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="5d84e-131">Solo los miembros del rol fijo de servidor **sysadmin** pueden escribir la salida de paso de trabajo en un archivo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5d84e-131">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="5d84e-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d84e-132">Using Transact-SQL</span></span>  
  
### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="5d84e-133">Para crear un paso de trabajo de CmdExec</span><span class="sxs-lookup"><span data-stu-id="5d84e-133">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="5d84e-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d84e-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5d84e-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5d84e-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5d84e-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5d84e-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses CmdExec  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'CMDEXEC',  
        @command = C:\clickme_scripts\SQL11\PostBOLReorg GetHsX.exe',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="5d84e-137">Para obtener más información, vea [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="5d84e-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="5d84e-138">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d84e-138">Using SQL Server Management Objects</span></span>  

### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="5d84e-139">Para crear un paso de trabajo de CmdExec</span><span class="sxs-lookup"><span data-stu-id="5d84e-139">To create a CmdExec job step</span></span>
  
 <span data-ttu-id="5d84e-140">Utilice la clase `JobStep` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d84e-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
