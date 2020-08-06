---
title: Crear un paso de trabajo para script de PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], job steps
- jobs [SQL Server Agent], PowerShell
- job steps [PowerShell]
- SQL Server Agent jobs, PowerShell steps
ms.assetid: 50afcf84-fae0-4eb5-9b0f-f2cf144c1433
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4232cdfa584fdcc2e13786ecc9bd00f0c6fe7066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672354"
---
# <a name="create-a-powershell-script-job-step"></a><span data-ttu-id="2b2ea-102">Create a PowerShell Script Job Step</span><span class="sxs-lookup"><span data-stu-id="2b2ea-102">Create a PowerShell Script Job Step</span></span>
  <span data-ttu-id="2b2ea-103">En este tema se describe cómo crear y definir un paso de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ejecute un script de PowerShell en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b2ea-103">This topic describes how to create and define a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes a PowerShell script in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2b2ea-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2b2ea-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2b2ea-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2b2ea-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2b2ea-107">**Para crear un paso de trabajo para script de PowerShell, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-107">**To create a PowerShell Script job step, using:**</span></span>  
  
     [<span data-ttu-id="2b2ea-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b2ea-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="2b2ea-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b2ea-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="2b2ea-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b2ea-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2b2ea-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2b2ea-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2b2ea-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2b2ea-112">Security</span></span>  
 <span data-ttu-id="2b2ea-113">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="2b2ea-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2b2ea-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b2ea-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="2b2ea-115">Para crear un paso de trabajo para script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b2ea-115">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="2b2ea-116">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2b2ea-117">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-117">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="2b2ea-118">Para obtener más información acerca de la creación de un trabajo, vea [Crear trabajos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2b2ea-118">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="2b2ea-119">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-119">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="2b2ea-120">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre para el paso de trabajo en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-120">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="2b2ea-121">En la lista **Tipo** , haga clic en **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-121">In the **Type** list, click **PowerShell**.</span></span>  
  
6.  <span data-ttu-id="2b2ea-122">En la lista **Ejecutar como** , seleccione la cuenta de proxy con las credenciales que utilizará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-122">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="2b2ea-123">En el cuadro **Comando** , especifique la sintaxis del script de PowerShell que se ejecutará para el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-123">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="2b2ea-124">También puede hacer clic en **Abrir** y seleccionar un archivo que contenga la sintaxis del script.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-124">Alternately, click **Open** and select a file containing the script syntax.</span></span> <span data-ttu-id="2b2ea-125">Para un ejemplo de un script de PowerShell, consulte **Usar Transact-SQL** más adelante.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-125">For an example of a PowerShell script, see **Using Transact-SQL** below.</span></span>  
  
8.  <span data-ttu-id="2b2ea-126">Haga clic en la página **Avanzadas** para establecer las siguientes opciones de paso de trabajo: acción que se llevará a cabo si el paso de trabajo progresa o no, número de veces que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe intentar ejecutar el paso de trabajo y frecuencia de los intentos.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="2b2ea-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b2ea-127">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="2b2ea-128">Para crear un paso de trabajo para script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b2ea-128">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="2b2ea-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b2ea-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2b2ea-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2b2ea-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a PowerShell job step that finds the processes that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="2b2ea-132">Para obtener más información, vea [sp_add_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2b2ea-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="2b2ea-133">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b2ea-133">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="2b2ea-134">**Para crear un paso de trabajo para script de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-134">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="2b2ea-135">Utilice la clase `JobStep` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-135">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
