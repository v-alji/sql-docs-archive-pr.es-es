---
title: Ejecutar los pasos Windows PowerShell del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f25f7549-c9b3-4618-85f2-c9a08adbe0e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8c100e2eaf1f9b706087bd991fbc268540c29a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672139"
---
# <a name="run-windows-powershell-steps-in-sql-server-agent"></a><span data-ttu-id="ca1bc-102">Ejecutar los pasos Windows PowerShell del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca1bc-102">Run Windows PowerShell Steps in SQL Server Agent</span></span>
  <span data-ttu-id="ca1bc-103">Use el Agente SQL Server para ejecutar scripts de SQL Server PowerShell en momentos programados.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-103">Use SQL Server Agent to run SQL Server PowerShell scripts at schedule times.</span></span>  
  
1.  <span data-ttu-id="ca1bc-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="ca1bc-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="ca1bc-105">**Para ejecutar PowerShell desde Agente SQL Server, mediante:**  [Paso de trabajo de PowerShell](#PShellJob), [paso de trabajo de símbolo del sistema](#CmdExecJob)</span><span class="sxs-lookup"><span data-stu-id="ca1bc-105">**To run PowerShell from SQL Server Agent, using:**  [PowerShell Job Step](#PShellJob), [Command Prompt Job Step](#CmdExecJob)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="ca1bc-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ca1bc-106">Before You Begin</span></span>  
 <span data-ttu-id="ca1bc-107">Hay varios tipos de pasos de trabajo del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca1bc-107">There are several types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="ca1bc-108">Cada tipo se asocia a un subsistema que implementa un entorno concreto, como un agente de replicación o un entorno del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-108">Each type is associated with a subsystem that implements a specific environment, such as a replication agent or command prompt environment.</span></span> <span data-ttu-id="ca1bc-109">Puede codificar scripts de Windows PowerShell y, a continuación, utilizar el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para incluir los scripts en trabajos que se ejecuten en los momentos programados o como respuesta a eventos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca1bc-109">You can code Windows PowerShell scripts, and then use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to include the scripts in jobs that run at scheduled times or in response to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="ca1bc-110">Los scripts de Windows PowerShell pueden ejecutarse mediante un paso de trabajo del símbolo del sistema o un paso de trabajo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-110">Windows PowerShell scripts can be run using either a command prompt job step or a PowerShell job step.</span></span>  
  
1.  <span data-ttu-id="ca1bc-111">Usar un paso de trabajo de PowerShell para hacer que el subsistema del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ejecute la utilidad `sqlps`, que inicia PowerShell 2.0 e importa el módulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-111">Use a PowerShell job step to have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem run the `sqlps` utility, which launches PowerShell 2.0 and imports the `sqlps` module.</span></span>  
  
2.  <span data-ttu-id="ca1bc-112">Usar un paso de trabajo de símbolo del sistema para ejecutar PowerShell.exe y especificar un script que importa el módulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-112">Use a command prompt job step to run PowerShell.exe, and specify a script that imports the `sqlps` module.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="ca1bc-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ca1bc-113">Limitations and Restrictions</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="ca1bc-114">Cada paso de trabajo del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que ejecuta PowerShell con el módulo `sqlps` inicia un proceso que consume aproximadamente 20 MB de memoria.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-114">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that runs PowerShell with the `sqlps` module launches a process which consumes approximately 20 MB of memory.</span></span> <span data-ttu-id="ca1bc-115">Si ejecuta muchos pasos de trabajo de Windows PowerShell simultáneos, el rendimiento se puede ver afectado adversamente.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-115">Running large numbers of concurrent Windows PowerShell job steps can adversely impact performance.</span></span>  
  
##  <a name="create-a-powershell-job-step"></a><a name="PShellJob"></a><span data-ttu-id="ca1bc-116">Crear un paso de trabajo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca1bc-116">Create a PowerShell Job Step</span></span>  
 <span data-ttu-id="ca1bc-117">**Para crear un paso de trabajo de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ca1bc-117">**To create a PowerShell job step**</span></span>  
  
1.  <span data-ttu-id="ca1bc-118">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="ca1bc-119">Para obtener más información acerca de cómo crear un trabajo, vea [Crear trabajos](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ca1bc-119">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="ca1bc-120">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="ca1bc-121">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre para el paso de trabajo en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="ca1bc-122">En la lista **Tipo** , haga clic en **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-122">In the **Type** list, click **PowerShell**.</span></span>  
  
5.  <span data-ttu-id="ca1bc-123">En la lista **Ejecutar como** , seleccione la cuenta de proxy con las credenciales que utilizará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
6.  <span data-ttu-id="ca1bc-124">En el cuadro **Comando** , especifique la sintaxis del script de PowerShell que se ejecutará para el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-124">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="ca1bc-125">También puede hacer clic en **Abrir** y seleccionar un archivo que contenga la sintaxis del script.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-125">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
7.  <span data-ttu-id="ca1bc-126">Haga clic en la página **Avanzadas** para establecer las siguientes opciones de paso de trabajo: acción que se llevará a cabo si el paso de trabajo progresa o no, número de veces que el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] debe intentar ejecutar el paso de trabajo y frecuencia de los intentos.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="create-a-command-prompt-job-step"></a><a name="CmdExecJob"></a><span data-ttu-id="ca1bc-127">Crear un paso de trabajo del símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="ca1bc-127">Create a Command Prompt Job Step</span></span>  
 <span data-ttu-id="ca1bc-128">**Para crear un paso de trabajo de CmdExec**</span><span class="sxs-lookup"><span data-stu-id="ca1bc-128">**To create a CmdExec job step**</span></span>  
  
1.  <span data-ttu-id="ca1bc-129">Expanda el **Agente SQL Server**, cree un trabajo o haga clic con el botón derecho en uno existente y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-129">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="ca1bc-130">Para obtener más información acerca de cómo crear un trabajo, vea [Crear trabajos](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ca1bc-130">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="ca1bc-131">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en la página **Pasos** y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-131">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="ca1bc-132">En el cuadro de diálogo **Nuevo paso de trabajo** , escriba un nombre para el paso de trabajo en **Nombre del paso**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-132">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="ca1bc-133">En la lista **Tipo** , elija **Sistema operativo (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-133">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
5.  <span data-ttu-id="ca1bc-134">En la lista **Ejecutar como** , seleccione la cuenta e proxy con las credenciales que utilizará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-134">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="ca1bc-135">De forma predeterminada, los pasos de trabajo de CmdExec se ejecutan en el contexto de la cuenta de servicio de Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-135">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
6.  <span data-ttu-id="ca1bc-136">En el cuadro **Procesar código de salida de un comando correcto** , escriba un valor de 0 a 999999.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-136">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
7.  <span data-ttu-id="ca1bc-137">En el cuadro **Comando** , escriba powershell.exe con parámetros que especifiquen el script de PowerShell que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-137">In the **Command** box, enter powershell.exe with parameters specifying the PowerShell script to be run.</span></span>  
  
8.  <span data-ttu-id="ca1bc-138">Haga clic en la página **Avanzadas** para configurar las opciones del paso de trabajo como, por ejemplo: la acción que se realizará si el paso de trabajo es correcto o si es erróneo, el número de veces que Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] intentará ejecutar el paso de trabajo y el archivo en el que Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] puede escribir la salida del paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-138">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="ca1bc-139">Solo los miembros del rol fijo de servidor **sysadmin** pueden escribir la salida de paso de trabajo en un archivo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-139">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1bc-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca1bc-140">See Also</span></span>  
 [<span data-ttu-id="ca1bc-141">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca1bc-141">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
