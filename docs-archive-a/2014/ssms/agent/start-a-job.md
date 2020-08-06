---
title: Iniciar un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], starting
- SQL Server Agent jobs, starting
- starting jobs
ms.assetid: cec9f7f7-d0a7-4239-9dc5-a69c011ebaa0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d5af895df518a915dacd953331b9139471933aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748468"
---
# <a name="start-a-job"></a><span data-ttu-id="88ee7-102">Iniciar un trabajo</span><span class="sxs-lookup"><span data-stu-id="88ee7-102">Start a Job</span></span>
  <span data-ttu-id="88ee7-103">En este tema se describe cómo iniciar la ejecución [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de un trabajo del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="88ee7-103">This topic describes how to start running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="88ee7-104">Un trabajo es una serie especificada de acciones que realiza el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88ee7-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="88ee7-105">se pueden ejecutar en un servidor local o en varios servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="88ee7-105">Agent jobs can run on one local server or on multiple remote servers.</span></span>  
  
-   <span data-ttu-id="88ee7-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="88ee7-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="88ee7-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="88ee7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="88ee7-108">**Para iniciar un trabajo,utilizando:**</span><span class="sxs-lookup"><span data-stu-id="88ee7-108">**To start a job, using:**</span></span>  
  
     [<span data-ttu-id="88ee7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="88ee7-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="88ee7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="88ee7-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="88ee7-111">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="88ee7-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="88ee7-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="88ee7-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="88ee7-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="88ee7-113">Security</span></span>  
 <span data-ttu-id="88ee7-114">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="88ee7-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="88ee7-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="88ee7-115">Using SQL Server Management Studio</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="88ee7-116">Para iniciar un trabajo</span><span class="sxs-lookup"><span data-stu-id="88ee7-116">To start a job</span></span>  
  
1.  <span data-ttu-id="88ee7-117">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="88ee7-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="88ee7-118">Expanda **Agente SQL Server** y **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-118">Expand **SQL Server Agent,** and expand **Jobs**.</span></span> <span data-ttu-id="88ee7-119">En función de cómo desea que se inicie el trabajo, realice uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="88ee7-119">Depending on how you want the job to start, do one of the following:</span></span>  
  
    -   <span data-ttu-id="88ee7-120">Si está trabajando en un solo servidor o en un servidor de destino, o está ejecutando un trabajo de servidor local en un servidor maestro, haga clic con el botón derecho en el trabajo que quiere iniciar y, después, haga clic en **Iniciar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-120">If you are working on a single server, or working on a target server, or running a local server job on a master server, right-click the job you want to start, and then click **Start Job**.</span></span>  
  
    -   <span data-ttu-id="88ee7-121">Si desea iniciar varios trabajos, haga clic con el botón derecho en **Monitor de actividad de trabajo**y, a continuación, haga clic en **Ver actividad de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-121">If you want to start multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="88ee7-122">En el Monitor de actividad de trabajo puede seleccionar varios trabajos, hacer clic con el botón derecho en su selección y hacer clic en **Iniciar trabajos**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-122">In the Job Activity Monitor you can select multiple jobs, right-click your selection, and click **Start Jobs**.</span></span>  
  
    -   <span data-ttu-id="88ee7-123">Si está trabajando en un servidor maestro y quiere que todos los servidores de destino ejecuten el trabajo simultáneamente, haga clic con el botón derecho en el trabajo que quiere iniciar, haga clic en **Iniciar trabajo**y, después, haga clic en **Iniciar en todos los servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-123">If you are working on a master server and want all targeted servers to run the job simultaneously, right-click the job you want to start, click **Start Job**, and then click **Start on all targeted servers**.</span></span>  
  
    -   <span data-ttu-id="88ee7-124">Si está trabajando en un servidor maestro y quiere especificar los servidores de destino para el trabajo, haga clic con el botón derecho en el trabajo que quiere iniciar, haga clic en **Iniciar trabajo**y, después, haga clic en **Iniciar en servidores de destino específicos**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-124">If you are working on a master server and want to specify target servers for the job, right-click the job you want to start, click **Start Job**, and then click **Start on specific target servers**.</span></span> <span data-ttu-id="88ee7-125">En el cuadro de diálogo **Exponer instrucciones de descarga** , active la casilla **Estos servidores de destino** y, a continuación, seleccione cada servidor de destino en el que debe ejecutarse este trabajo.</span><span class="sxs-lookup"><span data-stu-id="88ee7-125">In the **Post Download Instructions** dialog box, select the **These target servers** check box, and then select each target server on which this job should run.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="88ee7-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="88ee7-126">Using Transact-SQL</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="88ee7-127">Para iniciar un trabajo</span><span class="sxs-lookup"><span data-stu-id="88ee7-127">To start a job</span></span>  
  
1.  <span data-ttu-id="88ee7-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88ee7-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="88ee7-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="88ee7-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="88ee7-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- starts a job named Weekly Sales Data Backup.    
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_start_job N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="88ee7-131">Para más información, vea [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="88ee7-131">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="88ee7-132">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="88ee7-132">Using SQL Server Management Objects</span></span>  

### <a name="to-start-a-job"></a><span data-ttu-id="88ee7-133">Para iniciar un trabajo</span><span class="sxs-lookup"><span data-stu-id="88ee7-133">To start a job</span></span>
  
 <span data-ttu-id="88ee7-134">Llame al método `Start` de la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88ee7-134">Call the `Start` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="88ee7-135">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="88ee7-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
