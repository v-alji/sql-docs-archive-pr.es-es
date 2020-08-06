---
title: Escribir el estado de un trabajo en el registro de aplicación de Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- SQL Server Agent jobs, status
- writing job status to log
- jobs [SQL Server Agent], status
- logs [SQL Server], jobs
ms.assetid: 3b813702-8f61-40ec-bf3b-ce9deb7e68be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67bdd7948d1722e49976d5e48b571c684431cd1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747399"
---
# <a name="write-the-job-status-to-the-windows-application-log"></a><span data-ttu-id="84a1d-102">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="84a1d-102">Write the Job Status to the Windows Application Log</span></span>
  <span data-ttu-id="84a1d-103">En este tema se describe cómo configurar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para escribir el estado de un trabajo en el registro de eventos de aplicación Windows mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="84a1d-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to write job status to the Windows application event log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="84a1d-104">Estas respuestas permiten a los administradores de las bases de datos saber cuándo se completan los trabajos y con qué frecuencia se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="84a1d-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="84a1d-105">Algunas respuestas de trabajos típicas son:</span><span class="sxs-lookup"><span data-stu-id="84a1d-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="84a1d-106">Notificar al operador mediante correo electrónico, localizador electrónico o un mensaje de **net send** .</span><span class="sxs-lookup"><span data-stu-id="84a1d-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span> <span data-ttu-id="84a1d-107">Use una de estas respuestas de trabajo si el operador debe realizar una acción de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="84a1d-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="84a1d-108">Por ejemplo, si un trabajo de copia de seguridad se realiza correctamente, se debe notificar de ello al operador para que quite la cinta de copia de seguridad y la guarde en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="84a1d-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="84a1d-109">Escribir un mensaje de evento en el registro de aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="84a1d-109">Writing an event message to the Windows application log.</span></span> <span data-ttu-id="84a1d-110">Puede utilizar esta respuesta solo para trabajos con errores.</span><span class="sxs-lookup"><span data-stu-id="84a1d-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="84a1d-111">Eliminar automáticamente el trabajo.</span><span class="sxs-lookup"><span data-stu-id="84a1d-111">Automatically deleting the job.</span></span> <span data-ttu-id="84a1d-112">Utilice esta respuesta de trabajo si está seguro de que no necesita volver a ejecutar este trabajo.</span><span class="sxs-lookup"><span data-stu-id="84a1d-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="84a1d-113">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="84a1d-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="84a1d-114">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="84a1d-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="84a1d-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="84a1d-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="84a1d-116">**Para escribir el estado de un trabajo en el registro de aplicaciones Windows, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="84a1d-116">**To write the job status to the Windows application log, using:**</span></span>  
  
     [<span data-ttu-id="84a1d-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84a1d-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="84a1d-118">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="84a1d-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="84a1d-119">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="84a1d-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="84a1d-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="84a1d-120">Security</span></span>  
 <span data-ttu-id="84a1d-121">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="84a1d-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="84a1d-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84a1d-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="84a1d-123">Para escribir el estado de un trabajo en el registro de aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="84a1d-123">To write job status to the Windows application log</span></span>  
  
1.  <span data-ttu-id="84a1d-124">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="84a1d-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="84a1d-125">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee editar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="84a1d-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="84a1d-126">Seleccione la página **Notificaciones** .</span><span class="sxs-lookup"><span data-stu-id="84a1d-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="84a1d-127">Seleccione **Escribir en el registro de eventos de aplicación Windows**y elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="84a1d-127">Check **Write to Windows application event log**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="84a1d-128">Haga clic en**Si el trabajo tiene éxito**para registrar el estado del trabajo cuando este se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="84a1d-128">Click**When the job succeeds**to log the job status when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="84a1d-129">Haga clic en**Si el trabajo no tiene éxito**para registrar el estado del trabajo cuando este no se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="84a1d-129">Click**When the job fails**to log the job status when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="84a1d-130">Haga clic en**Si el trabajo termina** para registrar el estado del trabajo independientemente del estado de finalización.</span><span class="sxs-lookup"><span data-stu-id="84a1d-130">Click**When the job completes** to log the job status regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="84a1d-131">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="84a1d-131">Using SQL Server Management Objects</span></span>  

### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="84a1d-132">Para escribir el estado de un trabajo en el registro de aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="84a1d-132">To write job status to the Windows application log</span></span>
  
 <span data-ttu-id="84a1d-133">Llame a la propiedad `EventLogLevel` de la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84a1d-133">Call the `EventLogLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
 <span data-ttu-id="84a1d-134">En el ejemplo de código siguiente se establece el trabajo para generar una entrada del registro de eventos del sistema operativo cuando finaliza la ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="84a1d-134">The following code example sets the job to generate an operating system event log entry when the job execution finishes.</span></span>  
  
```powershell
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = new-object Microsoft.SqlServer.Management.Smo.Agent.Job($srv.JobServer, "Test Job")  
$jb.EventLogLevel = [Microsoft.SqlServer.Management.Smo.Agent.CompletionAction]::Always  
```  
