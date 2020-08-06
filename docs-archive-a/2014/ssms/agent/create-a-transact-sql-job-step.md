---
title: Crear un paso de trabajo de Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: 69c571a7-debe-4063-9d38-e4b6a1e8e84c
author: stevestein
ms.author: sstein
ms.openlocfilehash: b83ee944d2ca5c10ff1b77f3e6e6da6054b5c99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748487"
---
# <a name="create-a-transact-sql-job-step"></a><span data-ttu-id="018cd-102">Create a Transact-SQL Job Step</span><span class="sxs-lookup"><span data-stu-id="018cd-102">Create a Transact-SQL Job Step</span></span>
  <span data-ttu-id="018cd-103">En este tema se describe cómo crear un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] paso de trabajo del agente que ejecute [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="018cd-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="018cd-104">Estos scripts de pasos de trabajo pueden llamar a procedimientos almacenados y procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="018cd-104">These job step scripts may call stored procedures and extended stored procedures.</span></span> <span data-ttu-id="018cd-105">Un solo paso de trabajo de [!INCLUDE[tsql](../../includes/tsql-md.md)] puede contener varios procesos por lotes y comandos GO incrustados.</span><span class="sxs-lookup"><span data-stu-id="018cd-105">A single [!INCLUDE[tsql](../../includes/tsql-md.md)] job step can contain multiple batches and embedded GO commands.</span></span> <span data-ttu-id="018cd-106">Para obtener más información acerca de la creación de un trabajo, vea [Crear trabajos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="018cd-106">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
 <span data-ttu-id="018cd-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="018cd-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="018cd-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="018cd-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="018cd-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="018cd-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="018cd-110">**Para crear un paso de trabajo de Transact-SQL, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="018cd-110">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="018cd-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="018cd-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="018cd-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="018cd-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="018cd-113">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="018cd-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="018cd-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="018cd-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="018cd-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="018cd-115">Security</span></span>  
 <span data-ttu-id="018cd-116">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="018cd-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="018cd-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="018cd-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="018cd-118">Para crear un paso de trabajo de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="018cd-118">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="018cd-119">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="018cd-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="018cd-120">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="018cd-120">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="018cd-121">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="018cd-121">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="018cd-122">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre para el paso de trabajo en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="018cd-122">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="018cd-123">En la lista **Tipo** , haga clic en **Transact-SQL Script (TSQL)**.</span><span class="sxs-lookup"><span data-stu-id="018cd-123">In the **Type** list, click **Transact-SQL Script (TSQL)**.</span></span>  
  
6.  <span data-ttu-id="018cd-124">En el cuadro **Comando** , escriba el nombre de los lotes de comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] , o bien haga clic en **Abrir** para seleccionar un archivo [!INCLUDE[tsql](../../includes/tsql-md.md)] para utilizarlo como comando.</span><span class="sxs-lookup"><span data-stu-id="018cd-124">In the **Command** box, type the [!INCLUDE[tsql](../../includes/tsql-md.md)] command batches, or click **Open** to select a [!INCLUDE[tsql](../../includes/tsql-md.md)] file to use as the command.</span></span>  
  
7.  <span data-ttu-id="018cd-125">Haga clic en **Analizar** para comprobar la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="018cd-125">Click **Parse** to check your syntax.</span></span>  
  
8.  <span data-ttu-id="018cd-126">El mensaje "Análisis correcto" aparece cuando la sintaxis es correcta.</span><span class="sxs-lookup"><span data-stu-id="018cd-126">The message "Parse succeeded" is displayed when your syntax is correct.</span></span> <span data-ttu-id="018cd-127">Si se encuentra un error, corrija la sintaxis antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="018cd-127">If an error is found, correct the syntax before continuing.</span></span>  
  
9. <span data-ttu-id="018cd-128">Haga clic en la página **Avanzadas** para establecer las opciones de los pasos de trabajo, como qué acción realizar si el paso de trabajo funciona o no correctamente, cuántas veces el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe intentar ejecutar el paso de trabajo y el archivo o la tabla en la que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede escribir la salida de paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="018cd-128">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file or table where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="018cd-129">Solo los miembros del rol fijo de servidor **sysadmin** pueden escribir la salida de paso de trabajo en un archivo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="018cd-129">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span> <span data-ttu-id="018cd-130">Todos los usuarios del Agente SQL Server pueden registrar la salida en una tabla.</span><span class="sxs-lookup"><span data-stu-id="018cd-130">All SQL Server Agent users can log output to a table.</span></span>  
  
10. <span data-ttu-id="018cd-131">Si es miembro del rol fijo de servidor **sysadmin** y desea ejecutar este paso de trabajo con otro inicio de sesión de SQL, seleccione el inicio de sesión de SQL en la lista **Ejecutar como usuario** .</span><span class="sxs-lookup"><span data-stu-id="018cd-131">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="018cd-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="018cd-132">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="018cd-133">Para crear un paso de trabajo de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="018cd-133">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="018cd-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="018cd-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="018cd-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="018cd-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="018cd-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="018cd-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses Transact-SQL  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="018cd-137">Para obtener más información, vea [sp_add_jobstep &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="018cd-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="018cd-138">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="018cd-138">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="018cd-139">**Para crear un paso de trabajo de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="018cd-139">**To create a Transact-SQL job step**</span></span>  
  
 <span data-ttu-id="018cd-140">Utilice la clase `JobStep` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="018cd-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
