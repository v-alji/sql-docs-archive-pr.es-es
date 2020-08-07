---
title: Crear un paso de trabajo para script de ActiveX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ActiveX scripting jobs [SQL Server]
- job steps [Analysis Services]
ms.assetid: e6c46c6b-2d61-4571-bc8e-a831cd6e6302
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6604ba75af7acdd5bd2521433e8310c74150ce8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743909"
---
# <a name="create-an-activex-script-job-step"></a><span data-ttu-id="0b668-102">Create an ActiveX Script Job Step</span><span class="sxs-lookup"><span data-stu-id="0b668-102">Create an ActiveX Script Job Step</span></span>
  <span data-ttu-id="0b668-103">En este tema se describe cómo crear y definir un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] paso de trabajo del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que ejecute un script de ActiveX mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0b668-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that executes an ActiveX script by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="0b668-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="0b668-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0b668-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="0b668-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0b668-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0b668-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0b668-107">**Para crear un paso de trabajo de Transact-SQL, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="0b668-107">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="0b668-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0b668-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="0b668-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0b668-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="0b668-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b668-110">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="0b668-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="0b668-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0b668-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="0b668-112">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0b668-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0b668-113">Security</span></span>  
 <span data-ttu-id="0b668-114">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="0b668-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="0b668-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0b668-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="0b668-116">Para crear un paso de trabajo de script ActiveX</span><span class="sxs-lookup"><span data-stu-id="0b668-116">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="0b668-117">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="0b668-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0b668-118">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b668-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="0b668-119">Para obtener más información acerca de la creación de un trabajo, vea [Crear trabajos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="0b668-119">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="0b668-120">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0b668-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="0b668-121">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre para el paso de trabajo en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="0b668-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="0b668-122">En la lista **Tipo** , haga clic en **Script ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="0b668-122">In the **Type** list, click **ActiveX Script**.</span></span>  
  
6.  <span data-ttu-id="0b668-123">En la lista **Ejecutar como** , seleccione la cuenta de proxy con las credenciales que utilizará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="0b668-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="0b668-124">Seleccione el **lenguaje** en el que está escrita el script.</span><span class="sxs-lookup"><span data-stu-id="0b668-124">Select the **Language** in which the script was written.</span></span> <span data-ttu-id="0b668-125">Como alternativa, haga clic en **Otro** y especifique el nombre del lenguaje de scripting en el que se escribirá el script [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX.</span><span class="sxs-lookup"><span data-stu-id="0b668-125">Alternatively, click **Other** and then enter the name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX scripting language in which the script will be written.</span></span>  
  
8.  <span data-ttu-id="0b668-126">En el cuadro **Comando** , especifique la sintaxis de script que se ejecutará para el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0b668-126">In the **Command** box, enter the script syntax that will be executed for the job step.</span></span> <span data-ttu-id="0b668-127">También puede hacer clic en **Abrir** y seleccionar un archivo que contenga la sintaxis del script.</span><span class="sxs-lookup"><span data-stu-id="0b668-127">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
9. <span data-ttu-id="0b668-128">Haga clic en la página **Avanzadas** para establecer las siguientes opciones de paso de trabajo: acción que se llevará a cabo si el paso de trabajo progresa o no, número de veces que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe intentar ejecutar el paso de trabajo y frecuencia de los intentos.</span><span class="sxs-lookup"><span data-stu-id="0b668-128">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="0b668-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0b668-129">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="0b668-130">Para crear un paso de trabajo de script ActiveX</span><span class="sxs-lookup"><span data-stu-id="0b668-130">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="0b668-131">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b668-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0b668-132">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="0b668-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0b668-133">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0b668-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- create an ActiveX Script job step written in VBScript that creates a restore point  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a restore point',  
        @subsystem = N'ACTIVESCRIPTING',  
        @command = N'Const RESTORE_POINT = 20  
  
    strComputer = "."  
    Set objWMIService = GetObject("winmgmts:" _  
        & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\default")  
  
    Set objItem = objWMIService.Get("SystemRestore")  
    errResults = objItem.Restore(RESTORE_POINT)',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="0b668-134">Para obtener más información, vea [sp_add_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0b668-134">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="0b668-135">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b668-135">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="0b668-136">**Para crear un paso de trabajo de script ActiveX**</span><span class="sxs-lookup"><span data-stu-id="0b668-136">**To create an ActiveX Script job step**</span></span>  
  
 <span data-ttu-id="0b668-137">Utilice la clase `JobStep` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b668-137">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
