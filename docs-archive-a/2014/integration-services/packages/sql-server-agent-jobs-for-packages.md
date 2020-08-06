---
title: Trabajos del Agente SQL Server para paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- jobs [Integration Services]
- automatic package execution
- scheduling packages [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: ecf7a5f9-b8a7-47f1-9ac0-bac07cb89e31
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eb9c1cf39ab5120958c33dfeff24588d59f71307
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673079"
---
# <a name="sql-server-agent-jobs-for-packages"></a><span data-ttu-id="f509b-102">Trabajos del Agente SQL Server para paquetes</span><span class="sxs-lookup"><span data-stu-id="f509b-102">SQL Server Agent Jobs for Packages</span></span>
  <span data-ttu-id="f509b-103">Puede automatizar y programar la ejecución de paquetes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mediante el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f509b-103">You can automate and schedule the execution of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="f509b-104">Puede programar paquetes que se implementan en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] y se almacena en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el almacén de paquetes de [!INCLUDE[ssIS](../../includes/ssis-md.md)] y el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="f509b-104">You can schedule packages that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, and are stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
## <a name="sections-in-this-topic"></a><span data-ttu-id="f509b-105">Secciones de este tema</span><span class="sxs-lookup"><span data-stu-id="f509b-105">Sections in This Topic</span></span>  
 <span data-ttu-id="f509b-106">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="f509b-106">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="f509b-107">Programar trabajos en el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="f509b-107">Scheduling jobs in SQL Server Agent</span></span>](#jobs)  
  
-   [<span data-ttu-id="f509b-108">Programar paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="f509b-108">Scheduling Integration Services packages</span></span>](#packages)  
  
-   [<span data-ttu-id="f509b-109">Solucionar problemas de los paquetes programados</span><span class="sxs-lookup"><span data-stu-id="f509b-109">Troubleshooting scheduled packages</span></span>](#trouble)  
  
##  <a name="scheduling-jobs-in-sql-server-agent"></a><a name="jobs"></a> <span data-ttu-id="f509b-110">Scheduling Jobs in SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f509b-110">Scheduling Jobs in SQL Server Agent</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f509b-111">es un servicio instalado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que permite automatizar y programar tareas ejecutando trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f509b-111">Agent is the service installed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that lets you automate and schedule tasks by running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="f509b-112">El servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe ejecutarse antes de que los trabajos pueden ejecutarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f509b-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service must be running before jobs can run automatically.</span></span> <span data-ttu-id="f509b-113">Para obtener más información, consulte [Configure SQL Server Agent](../../ssms/agent/configure-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-113">For more information, see [Configure SQL Server Agent](../../ssms/agent/configure-sql-server-agent.md).</span></span>  
  
 <span data-ttu-id="f509b-114">El nodo **Agente SQL Server** aparece en el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] al establecer conexión con una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f509b-114">The **SQL Server Agent** node appears in Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f509b-115">Para automatizar una tarea periódica, se crea un trabajo a través del cuadro de diálogo **Nuevo trabajo** .</span><span class="sxs-lookup"><span data-stu-id="f509b-115">To automate a recurring task, you create a job by using the **New Job** dialog box.</span></span> <span data-ttu-id="f509b-116">Para más información, vea [Implementar trabajos](../../ssms/agent/implement-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-116">For more information, see [Implement Jobs](../../ssms/agent/implement-jobs.md).</span></span>  
  
 <span data-ttu-id="f509b-117">Después de crear el trabajo, debe agregar al menos un paso.</span><span class="sxs-lookup"><span data-stu-id="f509b-117">After you create the job, you must add at least one step.</span></span> <span data-ttu-id="f509b-118">Un trabajo puede incluir varios pasos, y cada paso puede realizar una tarea distinta.</span><span class="sxs-lookup"><span data-stu-id="f509b-118">A job can include multiple steps, and each step can perform a different task.</span></span> <span data-ttu-id="f509b-119">Para más información, consulte [Manage Job Steps](../../ssms/agent/manage-job-steps.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-119">For more information, see [Manage Job Steps](../../ssms/agent/manage-job-steps.md).</span></span>  
  
 <span data-ttu-id="f509b-120">Después de crear el trabajo y los pasos del trabajo, puede crear una programación para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f509b-120">After you create the job and the job steps, you can create a schedule for running the job.</span></span> <span data-ttu-id="f509b-121">No obstante, también puede crear un trabajo sin programar que se ejecute manualmente.</span><span class="sxs-lookup"><span data-stu-id="f509b-121">However you can also create an unscheduled job that you run manually.</span></span> <span data-ttu-id="f509b-122">Para obtener más información, vea [Crear y adjuntar programaciones a trabajos](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-122">For more information, see [Create and Attach Schedules to Jobs](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span></span>  
  
 <span data-ttu-id="f509b-123">Puede mejorar el trabajo estableciendo opciones de notificación; por ejemplo, especificando un operador que envíe un mensaje de correo electrónico cuando finalice el trabajo o agregando alertas.</span><span class="sxs-lookup"><span data-stu-id="f509b-123">You can enhance the job by setting notification options, such as specifying an operator to send an e-mail message to when the job finishes, or adding alerts.</span></span> <span data-ttu-id="f509b-124">Para más información, consulte [Alertas](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-124">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
##  <a name="scheduling-integration-services-packages"></a><a name="packages"></a> <span data-ttu-id="f509b-125">Scheduling Integration Services Packages</span><span class="sxs-lookup"><span data-stu-id="f509b-125">Scheduling Integration Services Packages</span></span>  
 <span data-ttu-id="f509b-126">Después de crear un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para programar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , debe agregar al menos un paso y definir el tipo de paso en **Paquete SQL Server Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="f509b-126">When you create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job to schedule [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you must add at least one step and set the type of the step to **SQL Server Integration Services Package**.</span></span> <span data-ttu-id="f509b-127">Un trabajo puede incluir varios pasos, y cada paso puede ejecutar un paquete diferente.</span><span class="sxs-lookup"><span data-stu-id="f509b-127">A job can include multiple steps, and each step can run a different package.</span></span>  
  
 <span data-ttu-id="f509b-128">Ejecutar un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] desde un paso de trabajo es como ejecutar un paquete con las utilidades **dtexec** (dtexec.exe) y **DTExecUI** (dtexecui.exe).</span><span class="sxs-lookup"><span data-stu-id="f509b-128">Running an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package from a job step is like running a package by using the **dtexec** (dtexec.exe) and **DTExecUI** (dtexecui.exe) utilities.</span></span> <span data-ttu-id="f509b-129">En lugar de establecer las opciones de tiempo de ejecución de un paquete con opciones de la línea de comandos o con el cuadro de diálogo **Utilidad de ejecución de paquetes** , establezca las opciones de tiempo de ejecución en el cuadro de diálogo **Nuevo paso de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="f509b-129">Instead of setting the run-time options for a package by using command-line options or the **Execute Package Utility** dialog box, you set the run-time options in the **New Job Step** dialog box.</span></span> <span data-ttu-id="f509b-130">Para obtener más información acerca de las opciones para ejecutar un paquete, vea [dtexec Utility](dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-130">For more information about the options for running a package, see [dtexec Utility](dtexec-utility.md).</span></span>  
  
 <span data-ttu-id="f509b-131">Para más información, vea [Programar un paquete mediante el Agente SQL Server](../schedule-a-package-by-using-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-131">For more information, see [Schedule a Package by using SQL Server Agent](../schedule-a-package-by-using-sql-server-agent.md).</span></span>  
  
 <span data-ttu-id="f509b-132">Para ver un vídeo que muestra cómo usar el agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar un paquete, vea la página principal del vídeo [ Cómo automatizar la ejecución de paquetes SSIS usando el Agente SQL Server (vídeo de SQL Server)](https://go.microsoft.com/fwlink/?LinkId=141771) en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="f509b-132">For a video that demonstrates how to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run a package, see the video home page, [How to: Automate Package Execution by Using the SQL Server Agent (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=141771), in the MSDN Library.</span></span>  
  
##  <a name="troubleshooting"></a><a name="trouble"></a> <span data-ttu-id="f509b-133">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="f509b-133">Troubleshooting</span></span>  
 <span data-ttu-id="f509b-134">Es posible que un paso de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no pueda iniciar un paquete aunque el paquete se ejecute correctamente en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] y desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f509b-134">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step may fail to start a package even though the package runs successfully in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and from the command line.</span></span> <span data-ttu-id="f509b-135">Hay algunos motivos frecuentes para este problema y varias soluciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="f509b-135">There are some common reasons for this issue and several recommended solutions.</span></span> <span data-ttu-id="f509b-136">Para obtener más información, vea los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f509b-136">For more information, see the following resources.</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="f509b-137">Knowledge Base, [Un paquete SSIS no se ejecuta al llamarlo desde un paso de trabajo del Agente SQL Server](https://support.microsoft.com/kb/918760)</span><span class="sxs-lookup"><span data-stu-id="f509b-137">Knowledge Base article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760)</span></span>  
  
-   <span data-ttu-id="f509b-138">Vídeo [Solucionar problemas de ejecución de paquetes SSIS usando el Agente SQL Server (vídeo de SQL Server)](https://go.microsoft.com/fwlink/?LinkId=141772) en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="f509b-138">Video, [Troubleshooting: Package Execution Using SQL Server Agent (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=141772), in the MSDN Library.</span></span>  
  
 <span data-ttu-id="f509b-139">Una vez que un paso de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicia un paquete, se puede producir un error en la ejecución del paquete o el paquete se puede ejecutar correctamente pero con resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="f509b-139">After a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step starts a package, the package execution may fail or the package may run successfully but with unexpected results.</span></span> <span data-ttu-id="f509b-140">Puede usar las herramientas siguientes para solucionar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="f509b-140">You can use the following tools to troubleshoot these issues.</span></span>  
  
-   <span data-ttu-id="f509b-141">Para los paquetes almacenados en la base de datos MSDB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el almacén de paquetes de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o una carpeta del equipo local, puede usar el **Visor del archivo de registros** , así como los registros y los archivos de volcado de depuración generados durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="f509b-141">For packages that are stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] MSDB database, the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, or in a folder on your local machine, you can use the **Log File Viewer** as well as any logs and debug dump files that were generated during the execution of the package.</span></span>  
  
     <span data-ttu-id="f509b-142">**Para usar el Visor del archivo de registros, haga lo siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f509b-142">**To use the Log File Viewer, do the following.**</span></span>  
  
    1.  <span data-ttu-id="f509b-143">Haga clic con el botón derecho en el trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el Explorador de objetos y, después, haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="f509b-143">Right-click the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in Object Explorer and then click **View History**.</span></span>  
  
    2.  <span data-ttu-id="f509b-144">Busque la ejecución del trabajo en el cuadro **Resumen de archivos del registro** que tengan el mensaje **error del trabajo** en la columna **Mensaje** .</span><span class="sxs-lookup"><span data-stu-id="f509b-144">Locate the job execution in the **Log file summary** box with the **job failed** message in the **Message** column.</span></span>  
  
    3.  <span data-ttu-id="f509b-145">Expanda el nodo de trabajo y haga clic en el paso de trabajo para ver los detalles del mensaje en el área situada debajo del cuadro **Resumen de archivos del registro** .</span><span class="sxs-lookup"><span data-stu-id="f509b-145">Expand the job node, and click the job step to view the details of the message in the area below the **Log file summary** box.</span></span>  
  
-   <span data-ttu-id="f509b-146">Para los paquetes almacenados en la base de datos de SSISDB, puede usar el **Visor del archivo de registros** , así como los registros y los archivos de volcado de depuración generados durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="f509b-146">For packages that are stored in the SSISDB database, you can also use the **Log File Viewer** as well as any logs and debug dump files that were generated during the execution of the package.</span></span> <span data-ttu-id="f509b-147">También puede usar los informes del servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f509b-147">In addition, you can use the reports for the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="f509b-148">**Para buscar información en los informes sobre la ejecución del paquete asociada a la ejecución de un trabajo, haga lo siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f509b-148">**To find information in the reports for the package execution associated with a job execution, do the following.**</span></span>  
  
    1.  <span data-ttu-id="f509b-149">Siga los pasos anteriores para ver los detalles del mensaje para el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f509b-149">Follow the steps above to view the details of the message for the job step.</span></span>  
  
    2.  <span data-ttu-id="f509b-150">Busque el identificador de ejecución que aparece en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f509b-150">Locate the Execution ID listed in the message.</span></span>  
  
    3.  <span data-ttu-id="f509b-151">Expanda el nodo Catálogos de Integration Services del Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="f509b-151">Expand the Integration Services Catalog node in Object Explorer.</span></span>  
  
    4.  <span data-ttu-id="f509b-152">Haga clic con el botón secundario en SSISDB, apunte a Informes y a Informes estándar, y haga clic en Todas las ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="f509b-152">Right-click SSISDB, point to Reports, then Standard Reports, and then click All Executions.</span></span>  
  
    5.  <span data-ttu-id="f509b-153">En el informe **Todas las ejecuciones** , busque el identificador de ejecución en la columna **Id.**</span><span class="sxs-lookup"><span data-stu-id="f509b-153">In the **All Executions** report, locate the Execution ID in the **ID** column.</span></span> <span data-ttu-id="f509b-154">Haga clic en **Información general**, en **Todos los mensajes**o en **Rendimiento de la ejecución** para ver información sobre la ejecución de este paquete.</span><span class="sxs-lookup"><span data-stu-id="f509b-154">Click **Overview**, **All Messages**, or **Execution Performance** to view information about this package execution.</span></span>  
  
         <span data-ttu-id="f509b-155">Para obtener más información acerca de los informes Información general, Todos los mensajes y Rendimiento de la ejecución, vea [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="f509b-155">For more information about the Overview, All Messages, and Execution Performance reports, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="f509b-156">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="f509b-156">External Resources</span></span>  
  
-   <span data-ttu-id="f509b-157">Artículo de Knowledge Base, [Un paquete SSIS no se ejecuta al llamarlo desde un paso de trabajo del Agente SQL Server](https://support.microsoft.com/kb/918760), en el sitio web de [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f509b-157">Knowledge Base article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760), on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Web site</span></span>  
  
-   <span data-ttu-id="f509b-158">Vídeo [Solucionar problemas de ejecución de paquetes SSIS usando el Agente SQL Server (vídeo de SQL Server)](https://go.microsoft.com/fwlink/?LinkId=141772) en MSDN Library</span><span class="sxs-lookup"><span data-stu-id="f509b-158">Video, [Troubleshooting: Package Execution Using SQL Server Agent (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=141772), in the MSDN Library</span></span>  
  
-   <span data-ttu-id="f509b-159">Vídeo [ Cómo automatizar la ejecución de paquetes SSIS usando el Agente SQL Server (vídeo de SQL Server)](https://go.microsoft.com/fwlink/?LinkId=141771) en MSDN Library</span><span class="sxs-lookup"><span data-stu-id="f509b-159">Video, [How to: Automate Package Execution by Using the SQL Server Agent (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=141771), in the MSDN Library</span></span>  
  
-   <span data-ttu-id="f509b-160">Artículo técnico relativo a la [comprobación de trabajos del Agente SQL Server mediante Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=165675), en mssqltips.com</span><span class="sxs-lookup"><span data-stu-id="f509b-160">Technical article, [Checking SQL Server Agent jobs using Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=165675), on mssqltips.com</span></span>  
  
-   <span data-ttu-id="f509b-161">Artículo técnico relativo a la [alerta automática de los trabajos del Agente SQL cuando están habilitados o deshabilitados](https://go.microsoft.com/fwlink/?LinkId=165676), en mssqltips.com</span><span class="sxs-lookup"><span data-stu-id="f509b-161">Technical article, [Auto alert for SQL Agent jobs when they are enabled or disabled](https://go.microsoft.com/fwlink/?LinkId=165676), on mssqltips.com</span></span>  
  
-   <span data-ttu-id="f509b-162">Entrada de blog, [Configuring SQL Agent Jobs to Write to Windows Event Log](https://go.microsoft.com/fwlink/?LinkId=220745), en mssqltips.com.</span><span class="sxs-lookup"><span data-stu-id="f509b-162">Blog entry, [Configuring SQL Agent Jobs to Write to Windows Event Log](https://go.microsoft.com/fwlink/?LinkId=220745), on mssqltips.com.</span></span>  
  
  