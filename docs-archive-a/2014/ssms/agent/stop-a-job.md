---
title: Detener un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
ms.assetid: 4249328a-24d8-4284-9d1d-7d04ed90e3d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 78986e85dd8ee808f5fb621182d903a94bbc5eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743901"
---
# <a name="stop-a-job"></a><span data-ttu-id="e6b15-102">Stop a Job</span><span class="sxs-lookup"><span data-stu-id="e6b15-102">Stop a Job</span></span>
  <span data-ttu-id="e6b15-103">En este tema se describe cómo detener un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="e6b15-103">This topic describes how to stop a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="e6b15-104">Un trabajo es una serie especificada de acciones que realiza el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b15-104">A job is a specified series of actions that SQL Server Agent performs.</span></span>  
  
-   <span data-ttu-id="e6b15-105">**Antes de empezar:** ,</span><span class="sxs-lookup"><span data-stu-id="e6b15-105">**Before you begin:**  ,</span></span>  
  
     [<span data-ttu-id="e6b15-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e6b15-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e6b15-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e6b15-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e6b15-108">**Para detener un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="e6b15-108">**To stop a job, using:**</span></span>  
  
     [<span data-ttu-id="e6b15-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6b15-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e6b15-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6b15-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e6b15-111">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6b15-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e6b15-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e6b15-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e6b15-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e6b15-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e6b15-114">Si un trabajo está ejecutando un paso de tipo **CmdExec** o **PowerShell**, se forzará la finalización prematura del proceso en ejecución (por ejemplo, MyProgram.exe).</span><span class="sxs-lookup"><span data-stu-id="e6b15-114">If a job is currently executing a step of type **CmdExec** or **PowerShell**, the process that is being run (for example, MyProgram.exe) is forced to end prematurely.</span></span> <span data-ttu-id="e6b15-115">Esto puede provocar un comportamiento imprevisible como, por ejemplo, que se mantengan abiertos los archivos utilizados por el proceso.</span><span class="sxs-lookup"><span data-stu-id="e6b15-115">This can cause unpredictable behavior, such as files that are being used by the process being held open.</span></span>  
  
-   <span data-ttu-id="e6b15-116">Si se trata de un trabajo multiservidor, se expone una instrucción STOP para el trabajo en todos los servidores de destino correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e6b15-116">For a multiserver job, a STOP instruction for the job is posted to all target servers of the job.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e6b15-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e6b15-117">Security</span></span>  
 <span data-ttu-id="e6b15-118">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e6b15-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e6b15-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6b15-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-stop-a-job"></a><span data-ttu-id="e6b15-120">Para detener un trabajo</span><span class="sxs-lookup"><span data-stu-id="e6b15-120">To stop a job</span></span>  
  
1.  <span data-ttu-id="e6b15-121">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="e6b15-121">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e6b15-122">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desea detener y haga clic en **Detener trabajo**.</span><span class="sxs-lookup"><span data-stu-id="e6b15-122">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to stop, and then click **Stop Job**.</span></span>  
  
3.  <span data-ttu-id="e6b15-123">Si desea detener varios trabajos, haga clic con el botón derecho en **Monitor de actividad de trabajo**y, a continuación, haga clic en **Ver actividad de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="e6b15-123">If you want to stop multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="e6b15-124">En Monitor de actividad de trabajo, seleccione los trabajos que desee detener, haga clic con el botón derecho en la selección y, a continuación, haga clic en **Detener trabajos**.</span><span class="sxs-lookup"><span data-stu-id="e6b15-124">In the Job Activity Monitor, select the jobs you want to stop, right-click your selection, and then click **Stop Jobs**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e6b15-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6b15-125">Using Transact-SQL</span></span>  
  
### <a name="to-stop-a-job"></a><span data-ttu-id="e6b15-126">Para detener un trabajo</span><span class="sxs-lookup"><span data-stu-id="e6b15-126">To stop a job</span></span>  
  
1.  <span data-ttu-id="e6b15-127">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b15-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6b15-128">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e6b15-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e6b15-129">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e6b15-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- stops a job named Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_stop_job  
        N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="e6b15-130">Para obtener más información, vea [sp_stop_job &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6b15-130">For more information, see [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e6b15-131">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6b15-131">Using SQL Server Management Objects</span></span>  

### <a name="to-stop-a-job"></a><span data-ttu-id="e6b15-132">Para detener un trabajo</span><span class="sxs-lookup"><span data-stu-id="e6b15-132">To stop a job</span></span>
  
 <span data-ttu-id="e6b15-133">Llame al método `Stop` de la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6b15-133">Call the `Stop` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="e6b15-134">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="e6b15-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
