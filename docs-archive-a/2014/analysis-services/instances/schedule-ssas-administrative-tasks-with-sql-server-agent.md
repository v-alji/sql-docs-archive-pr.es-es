---
title: Programar tareas administrativas de SSAS con Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d1484b3-51d9-48a0-93d2-0c3e4ed22b87
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c78fa5fcebc0589ba863163b93ad2d10731b75a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746582"
---
# <a name="schedule-ssas-administrative-tasks-with-sql-server-agent"></a><span data-ttu-id="a6bd4-102">Programar tareas administrativas de SSAS con el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6bd4-102">Schedule SSAS Administrative Tasks with SQL Server Agent</span></span>
  <span data-ttu-id="a6bd4-103">Con el servicio Agente SQL Server, puede programar tareas administrativas de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se ejecutan en el orden y a las horas que se necesitan.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-103">Using the SQL Server Agent service, you can schedule [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrative tasks to run in the order and times that you need.</span></span> <span data-ttu-id="a6bd4-104">Las tareas programadas le ayudan a automatizar los procesos que se ejecutan en ciclos normales o predecibles.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-104">Scheduled tasks help you automate processes that run on regular or predictable cycles.</span></span> <span data-ttu-id="a6bd4-105">Puede programar tareas administrativas, como procesamiento de cubos, para que se ejecuten en momentos de poca actividad empresarial.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-105">You can schedule administrative tasks, such as cube processing, to run during times of slow business activity.</span></span> <span data-ttu-id="a6bd4-106">También puede determinar el orden en el que se ejecutarán las tareas creando pasos de trabajo en un trabajo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-106">You can also determine the order in which tasks run by creating job steps within a SQL Server Agent job.</span></span> <span data-ttu-id="a6bd4-107">Por ejemplo, puede procesar un cubo y luego realizar una copia de seguridad del cubo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-107">For example, you can process a cube and then perform a backup of the cube.</span></span>  
  
 <span data-ttu-id="a6bd4-108">Los pasos de trabajo le permiten controlar el flujo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-108">Job steps give you control over flow of execution.</span></span> <span data-ttu-id="a6bd4-109">Si se produce un error en un trabajo, puede configurar el Agente SQL Server para continuar ejecutando las tareas restantes o para detener la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-109">If one job fails, you can configure SQL Server Agent to continue to run the remaining tasks or to stop execution.</span></span> <span data-ttu-id="a6bd4-110">También puede configurar el Agente SQL Server para enviar notificaciones del éxito o el fracaso de la ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-110">You can also configure SQL Server Agent to send notifications about the success or failure of job execution.</span></span>  
  
 <span data-ttu-id="a6bd4-111">Este tema es un tutorial que muestra dos formas de usar el Agente SQL Server para ejecutar el script XMLA.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-111">This topic is a walkthrough that shows two ways of using SQL Server Agent to run XMLA script.</span></span> <span data-ttu-id="a6bd4-112">El primer ejemplo demuestra cómo programar el procesamiento de una sola dimensión.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-112">The first example demonstrates how to schedule processing of a single dimension.</span></span> <span data-ttu-id="a6bd4-113">El segundo ejemplo muestra cómo combinar tareas de procesamiento en un único script que se ejecuta según una programación.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-113">Example two shows how to combine processing tasks into a single script that runs on a schedule.</span></span> <span data-ttu-id="a6bd4-114">Para completar este tutorial, deberá cumplir los siguientes requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-114">To complete this walkthrough, you will need to meet the following prerequisites.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a6bd4-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a6bd4-115">Prerequisites</span></span>  
 <span data-ttu-id="a6bd4-116">Se debe instalar el servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-116">SQL Server Agent service must be installed.</span></span>  
  
 <span data-ttu-id="a6bd4-117">De forma predeterminada, trabajos se ejecutan con la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-117">By default, jobs run under the service account.</span></span> <span data-ttu-id="a6bd4-118">En [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , la cuenta predeterminada para Agente SQL Server es NT Service\SQLAgent $ \<instancename> .</span><span class="sxs-lookup"><span data-stu-id="a6bd4-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the default account for SQL Server Agent is NT Service\SQLAgent$\<instancename>.</span></span> <span data-ttu-id="a6bd4-119">Para realizar una tarea de copia de seguridad o de procesamiento, esta cuenta debe ser administrador del sistema en la instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-119">To perform a backup or processing task, this account must be a system administrator on the Analysis Services instance.</span></span> <span data-ttu-id="a6bd4-120">Para obtener más información, vea [conceder permisos de administrador de servidor &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span><span class="sxs-lookup"><span data-stu-id="a6bd4-120">For more information, see [Grant Server Administrator Permissions &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span></span>  
  
 <span data-ttu-id="a6bd4-121">También debe tener una base de datos de prueba para trabajar con ella.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-121">You should also have a test database to work with.</span></span> <span data-ttu-id="a6bd4-122">Puede implementar la base de datos de ejemplo multidimensional AdventureWorks o un proyecto del tutorial multidimensional de Analysis Services para usarlo en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-122">You can deploy the AdventureWorks multidimensional sample database or a project from the Analysis Services multidimensional tutorial to use in this walkthrough.</span></span> <span data-ttu-id="a6bd4-123">Para obtener más información, vea [instalar datos y proyectos de ejemplo para el tutorial de modelado multidimensional de Analysis Services](../install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="a6bd4-123">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](../install-sample-data-and-projects.md).</span></span>  
  
## <a name="example-1-processing-a-dimension-in-a-scheduled-task"></a><span data-ttu-id="a6bd4-124">Ejemplo 1: procesar una dimensión en una tarea programada</span><span class="sxs-lookup"><span data-stu-id="a6bd4-124">Example 1: Processing a dimension in a scheduled task</span></span>  
 <span data-ttu-id="a6bd4-125">Este ejemplo muestra cómo crear y programar un trabajo que procesa una dimensión.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-125">This example demonstrates how to create and schedule a job that processes a dimension.</span></span>  
  
 <span data-ttu-id="a6bd4-126">Una tarea programada de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] es un script XMLA incrustado en un trabajo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-126">An [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] scheduled task is an XMLA script that is embedded into a SQL Server Agent job.</span></span> <span data-ttu-id="a6bd4-127">Este trabajo se programa para ejecutarse en los momentos y con la frecuencia deseados.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-127">This job is scheduled to run at desired times and frequency.</span></span> <span data-ttu-id="a6bd4-128">Dado que el Agente SQL Server es parte de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se trabaja con el motor de base de datos y con [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para crear y programar una tarea administrativa.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-128">Because the SQL Server Agent is part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you work with both the Database Engine and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to create and schedule an administrative task.</span></span>  
  
###  <a name="create-a-script-for-processing-a-dimension-in-a-sql-server-agent-job"></a><a name="bkmk_CreateScript"></a><span data-ttu-id="a6bd4-129">Crear un script para procesar una dimensión en un trabajo de Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6bd4-129">Create a script for processing a dimension in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="a6bd4-130">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6bd4-130">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="a6bd4-131">Abra una carpeta de base de datos y busque una dimensión.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-131">Open a database folder and find a dimension.</span></span> <span data-ttu-id="a6bd4-132">Haga clic con el botón derecho en la dimensión y seleccione **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-132">Right-click the dimension and select **Process**.</span></span>  
  
2.  <span data-ttu-id="a6bd4-133">En el cuadro de diálogo **Procesar dimensión** , en la columna **Opciones de proceso** debajo de **Lista de objetos**, compruebe que la opción en esta columna sea **Procesar completo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-133">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="a6bd4-134">De lo contrario, en **Opciones de proceso**, haga clic en la opción y, después, seleccione **Proceso completo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-134">If it is not, under **Process Options**, click the option, and then select **Process Full** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="a6bd4-135">Haga clic **Script**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-135">Click **Script**.</span></span>  
  
     <span data-ttu-id="a6bd4-136">Este paso abre una ventana **Consulta XML** que contiene el script XMLA que procesa la dimensión.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-136">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="a6bd4-137">En el cuadro de diálogo **Procesar dimensión** , haga clic en **Cancelar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-137">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="a6bd4-138">En la ventana **Consulta XMLA** , resalte el script XMLA, haga clic con el botón derecho en el script resaltado y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-138">In the **XMLA Query** window, highlight the XMLA script, right-click the highlighted script, and select **Copy**.</span></span>  
  
     <span data-ttu-id="a6bd4-139">Este paso copia el script XMLA en el Portapapeles de Windows.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-139">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="a6bd4-140">Puede dejar el script XMLA en el portapapeles o pegarlo en el Bloc de notas u otro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-140">You can leave the XMLA script in the Clipboard or paste it into Notepad or another text editor.</span></span> <span data-ttu-id="a6bd4-141">A continuación, se muestra un ejemplo del script XMLA.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-141">The following is an example of the XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Account</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
###  <a name="create-and-schedule-the-dimension-processing-job"></a><a name="bkmk_ProcessJob"></a><span data-ttu-id="a6bd4-142">Crear y programar el trabajo de procesamiento de dimensiones</span><span class="sxs-lookup"><span data-stu-id="a6bd4-142">Create and schedule the dimension processing job</span></span>  
  
1.  <span data-ttu-id="a6bd4-143">Conéctese a una instancia del Motor de base de datos y, a continuación, abra el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-143">Connect to an instance of the Database Engine and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="a6bd4-144">Expanda **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-144">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a6bd4-145">Haga clic con el botón derecho en **Trabajos** y seleccione **Nuevo trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-145">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="a6bd4-146">En el cuadro de diálogo **Nuevo trabajo** , escriba un nombre de trabajo en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-146">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="a6bd4-147">En **Seleccione una página**, seleccione **Pasos**y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-147">Under **Select a page**, select **Steps**, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="a6bd4-148">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre de paso en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-148">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="a6bd4-149">En **servidor**, escriba **localhost** para una instancia predeterminada de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y \*\*localhost \\ \*\* \<*instance name*> para una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-149">In **Server**, type **localhost** for a default instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and **localhost\\**\<*instance name*> for a named instance.</span></span>  
  
     <span data-ttu-id="a6bd4-150">Si va a ejecutar el trabajo desde un equipo remoto, use el nombre de servidor y el nombre de instancia donde se ejecutará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-150">If you will be running the job from a remote computer, use the server name and instance name where the job will run.</span></span> <span data-ttu-id="a6bd4-151">Use el formato \<*server name*> para una instancia predeterminada y \<*server name*> \\ < *el nombre de instancia*> para una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-151">Use the format \<*server name*> for a default instance, and \<*server name*>\\<*instance name*> for a named instance.</span></span>  
  
8.  <span data-ttu-id="a6bd4-152">En **Tipo**, seleccione **Comando de SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-152">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
9. <span data-ttu-id="a6bd4-153">En **Comando**, haga clic con el botón derecho y seleccione **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-153">In **Command**, right-click and select **Paste**.</span></span> <span data-ttu-id="a6bd4-154">El script XMLA que generó en el paso anterior debe aparecer en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-154">The XMLA script that you generated in the previous step should appear in the command window.</span></span>  
  
10. <span data-ttu-id="a6bd4-155">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-155">Click **OK**.</span></span>  
  
11. <span data-ttu-id="a6bd4-156">En **Seleccione una página**, haga clic en **Programaciones**y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-156">Under **Select a page**, click **Schedules**, and then click **New**.</span></span>  
  
12. <span data-ttu-id="a6bd4-157">En el cuadro de diálogo **Nueva programación del trabajo** , escriba un nombre de programación en **Nombre**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-157">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a6bd4-158">Este paso crea una programación para domingo a las 12:00.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-158">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="a6bd4-159">El paso siguiente muestra cómo ejecutar manualmente el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-159">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="a6bd4-160">También puede especificar una programación que ejecuta el trabajo cuando lo está supervisando.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-160">You can also specify a schedule that executes the job when you are monitoring it.</span></span>  
  
13. <span data-ttu-id="a6bd4-161">En el cuadro de diálogo **Nuevo trabajo** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-161">In the **New Job** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="a6bd4-162">En el **Explorador de objetos**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que creó y, después, seleccione **Iniciar trabajo en el paso**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-162">In **Object Explorer**, expand **Jobs**, right-click the job you created, and then select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="a6bd4-163">Dado que el trabajo tiene un solo paso, el trabajo se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-163">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="a6bd4-164">Si el trabajo contuviera varios pasos, podría seleccionar el paso en el que el trabajo debe iniciarse.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-164">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
15. <span data-ttu-id="a6bd4-165">Cuando finalice el trabajo, haga clic **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-165">When the job finishes, click **Close**.</span></span>  
  
## <a name="example-2-batch-processing-a-dimension-and-a-partition-in-a-scheduled-task"></a><span data-ttu-id="a6bd4-166">Ejemplo 2: procesamiento por lotes de una dimensión y una partición en una tarea programada</span><span class="sxs-lookup"><span data-stu-id="a6bd4-166">Example 2: Batch processing a dimension and a partition in a scheduled task</span></span>  
 <span data-ttu-id="a6bd4-167">Los procedimientos de este ejemplo demuestran cómo crear y programar una trabajo que procese por lotes una dimensión de base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y al mismo tiempo procesar una partición de cubo que dependa de la dimensión para la agregación.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-167">The procedures in this example demonstrate how to create and schedule a job that batch processes an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database dimension, and at the same time to process a  cube partition that depends on the dimension for aggregation.</span></span> <span data-ttu-id="a6bd4-168">Para obtener más información sobre el procesamiento por lotes de objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vea [Procesamiento por lotes &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6bd4-168">For more information about batch processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Batch Processing &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span></span>  
  
###  <a name="create-a-script-for-batch-processing-a-dimension-and-partition-in-a-sql-server-agent-job"></a><a name="bkmk_BatchProcess"></a><span data-ttu-id="a6bd4-169">Crear un script para el procesamiento por lotes de una dimensión y una partición en un trabajo de Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6bd4-169">Create a script for batch processing a dimension and partition in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="a6bd4-170">Con la misma base de datos, expanda **Dimensiones**, haga clic con el botón derecho en la dimensión **Cliente** y seleccione **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-170">Using the same database, expand **Dimensions**, right-click the **Customer** dimension, and select **Process**.</span></span>  
  
2.  <span data-ttu-id="a6bd4-171">En el cuadro de diálogo **Procesar dimensión** , en la columna **Opciones de proceso** debajo de **Lista de objetos**, compruebe que la opción en esta columna sea **Procesar completo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-171">In the **Process Dimension** dialog box, in **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
3.  <span data-ttu-id="a6bd4-172">Haga clic **Script**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-172">Click **Script**.</span></span>  
  
     <span data-ttu-id="a6bd4-173">Este paso abre una ventana **Consulta XML** que contiene el script XMLA que procesa la dimensión.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-173">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="a6bd4-174">En el cuadro de diálogo **Procesar dimensión** , haga clic en **Cancelar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-174">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="a6bd4-175">Expanda **Cubos**, **Adventure Works**, **Grupos de medida**, **Venta por Internet**y **Particiones**; haga clic con el botón derecho en la última partición de la lista y seleccione **Proceso**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-175">Expand **Cubes**, expand **Adventure Works**, expand **Measure Groups**, expand **Internet Sales**, expand **Partitions**, right-click the last partition in the list, and then select **Process**.</span></span>  
  
6.  <span data-ttu-id="a6bd4-176">En el cuadro de diálogo **Procesar partición** , en la columna **Opciones de proceso** debajo de **Lista de objetos**, compruebe que la opción en esta columna sea **Procesar completo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-176">In the **Process Partition** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
7.  <span data-ttu-id="a6bd4-177">Haga clic **Script**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-177">Click **Script**.</span></span>  
  
     <span data-ttu-id="a6bd4-178">Este paso abre una segunda ventana **Consulta XML** que contiene el script XMLA que procesa la partición.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-178">This step opens a second **XML Query** window that contains the XMLA script that processes the partition.</span></span>  
  
8.  <span data-ttu-id="a6bd4-179">En el cuadro de diálogo **Procesar partición** , haga clic en **Cancelar** para cerrar el editor.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-179">In the **Process Partition** dialog box, click **Cancel** to close the editor.</span></span>  
  
     <span data-ttu-id="a6bd4-180">En este punto debe combinar los dos scripts y asegurarse de que la dimensión se procesa en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-180">At this point you must merge the two scripts, and ensure that the dimension is processed first.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="a6bd4-181">Si la partición se procesa en primer lugar, el procesamiento posterior de la dimensión provoca que la partición se quede sin procesar.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-181">If the partition is processed first, the subsequent dimension processing causes the partition to become unprocessed.</span></span> <span data-ttu-id="a6bd4-182">La partición requeriría un segundo procesamiento para alcanzar el estado de procesada.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-182">The partition would then require a second processing to reach a processed state.</span></span>  
  
9. <span data-ttu-id="a6bd4-183">En la ventana **Consulta XMLA** que contiene el script XMLA que procesa la partición, resalte el código que hay dentro de las etiquetas `Batch` y `Parallel` , haga clic con el botón derecho en el script resaltado y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-183">In the **XMLA Query** window that contains the XMLA script that processes the partition, highlight the code inside the `Batch` and `Parallel` tags, right-click the highlighted script, and select **Copy**.</span></span>  
  
    ```  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID> Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID> Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
    ```  
  
10. <span data-ttu-id="a6bd4-184">Abra la ventana **Consulta XMLA** que contiene el script XMLA que procesa la dimensión.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-184">Open the **XMLA Query** window that contains the XMLA script that processes the dimension.</span></span> <span data-ttu-id="a6bd4-185">Haga clic con el botón derecho en el script situado a la izquierda de la etiqueta `</Process>` y seleccione **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-185">Right-click within the script to the left of the `</Process>` tag and select **Paste**.</span></span>  
  
     <span data-ttu-id="a6bd4-186">El ejemplo siguiente muestra el script XMLA revisado.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-186">The following example shows the revised XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Customer</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID>Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
11. <span data-ttu-id="a6bd4-187">Resalte el script XMLA revisado, haga clic con el botón derecho en el script resaltado y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-187">Highlight the revised XMLA script, right-click the highlighted script, and select **Copy.**</span></span>  
  
12. <span data-ttu-id="a6bd4-188">Este paso copia el script XMLA en el Portapapeles de Windows.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-188">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="a6bd4-189">Puede dejar el script XMLA en el portapapeles, guardarlo en un archivo o pegarlo en el Bloc de notas u otro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-189">You can leave the XMLA script in the Clipboard, save it to a file, or paste it into Notepad or another text editor.</span></span>  
  
###  <a name="create-and-schedule-the-batch-processing-job"></a><a name="bkmk_Scheduling"></a><span data-ttu-id="a6bd4-190">Crear y programar el trabajo de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="a6bd4-190">Create and schedule the batch processing job</span></span>  
  
1.  <span data-ttu-id="a6bd4-191">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]y, a continuación, abra el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-191">Connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="a6bd4-192">Expanda **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-192">Expand **SQL Server Agent**.</span></span> <span data-ttu-id="a6bd4-193">Inicie el servicio, si no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-193">Start the service if is not running.</span></span>  
  
3.  <span data-ttu-id="a6bd4-194">Haga clic con el botón derecho en **Trabajos** y seleccione **Nuevo trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-194">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="a6bd4-195">En el cuadro de diálogo **Nuevo trabajo** , escriba un nombre de trabajo en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-195">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="a6bd4-196">En **Pasos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-196">In **Steps**, click **New**.</span></span>  
  
6.  <span data-ttu-id="a6bd4-197">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre de paso en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-197">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="a6bd4-198">En **Tipo**, seleccione **Comando de SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-198">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
8.  <span data-ttu-id="a6bd4-199">En **Ejecutar como**, seleccione la **Cuenta del servicio del Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-199">In **Run as**, select the **SQL Server Agent Service Account**.</span></span> <span data-ttu-id="a6bd4-200">Recuerde de la sección Requisitos previos que esta cuenta debe tener permisos de administrador en Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-200">Recall from the Prerequisites section that this account must have administrative permissions on Analysis Services.</span></span>  
  
9. <span data-ttu-id="a6bd4-201">En **Servidor**, especifique el nombre de servidor de la instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-201">In **Server**, specify the server name of the Analysis Services instance.</span></span>  
  
10. <span data-ttu-id="a6bd4-202">En **Comando**, haga clic con el botón derecho y seleccione **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-202">In **Command**, right-click and select **Paste**.</span></span>  
  
11. <span data-ttu-id="a6bd4-203">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-203">Click **OK**.</span></span>  
  
12. <span data-ttu-id="a6bd4-204">En la página **Programaciones** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-204">In the **Schedules** page, click **New**.</span></span>  
  
13. <span data-ttu-id="a6bd4-205">En el cuadro de diálogo **Nueva programación del trabajo** , escriba un nombre de programación en **Nombre**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-205">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a6bd4-206">Este paso crea una programación para domingo a las 12:00.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-206">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="a6bd4-207">El paso siguiente muestra cómo ejecutar manualmente el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-207">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="a6bd4-208">También puede seleccionar una programación que ejecutará el trabajo cuando lo esté supervisando.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-208">You can also select a schedule which will execute the job when you are monitoring it.</span></span>  
  
14. <span data-ttu-id="a6bd4-209">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-209">Click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="a6bd4-210">En el **Explorador de objetos**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que creó y seleccione **Iniciar trabajo en el paso**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-210">In **Object Explorer**, expand **Jobs**, right-click the job you created, and select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="a6bd4-211">Dado que el trabajo tiene un solo paso, el trabajo se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-211">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="a6bd4-212">Si el trabajo contuviera varios pasos, podría seleccionar el paso en el que el trabajo debe iniciarse.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-212">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
16. <span data-ttu-id="a6bd4-213">Cuando finalice el trabajo, haga clic **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a6bd4-213">When the job finishes, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6bd4-214">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6bd4-214">See Also</span></span>  
 <span data-ttu-id="a6bd4-215">[Opciones de procesamiento y configuración &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="a6bd4-215">[Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span></span>  
 [<span data-ttu-id="a6bd4-216">Crear scripts para tareas administrativas en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a6bd4-216">Script Administrative Tasks in Analysis Services</span></span>](../script-administrative-tasks-in-analysis-services.md)  
  
  
