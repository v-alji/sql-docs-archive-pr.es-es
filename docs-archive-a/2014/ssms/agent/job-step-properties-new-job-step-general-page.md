---
title: 'Propiedades de paso de trabajo: nuevo paso de trabajo (página general) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepgeneral.f1
ms.assetid: 8d1885ba-4386-4528-8f2b-68c16852720c
author: stevestein
ms.author: sstein
ms.openlocfilehash: c76e1ecb69a1475ec102f143a6a1ca34fbf91e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675104"
---
# <a name="job-step-properties-new-job-step-general-page"></a><span data-ttu-id="0dc1c-102">Propiedades de paso de trabajo: Nuevo paso de trabajo (página General)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-102">Job Step Properties: New Job Step (General Page)</span></span>
  <span data-ttu-id="0dc1c-103">Utilice esta página para ver y cambiar las propiedades de un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] paso de trabajo del agente, o para definir un nuevo paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step, or to define a new job step.</span></span>  
  
 <span data-ttu-id="0dc1c-104">Para navegar a esta página, en el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , haga clic con el botón derecho en **Trabajos**, haga clic en **Nuevo trabajo**, seleccione la página **Pasos** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-104">To navigate to this page, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, click **New Jobs**, select the **Steps** page, and click **New**.</span></span> <span data-ttu-id="0dc1c-105">También puede navegar a esta página si hace clic con el botón derecho en un trabajo en el Explorador de objetos, hace clic en **Propiedades**, selecciona la página **Pasos** y hace clic en **Nuevo**, **Insertar**o **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-105">You can also navigate to this page by right-clicking a job in Object Explorer, clicking **Properties**, selecting the **Steps** page, and clicking **New**, **Insert**, or **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0dc1c-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="0dc1c-106">Options</span></span>  
 <span data-ttu-id="0dc1c-107">**Nombre del paso**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-107">**Step name**</span></span>  
 <span data-ttu-id="0dc1c-108">Establece el nombre del paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-108">Set the name of the job step.</span></span>  
  
 <span data-ttu-id="0dc1c-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-109">**Type**</span></span>  
 <span data-ttu-id="0dc1c-110">Establece el subsistema que utiliza el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-110">Set the subsystem that the job step uses.</span></span> <span data-ttu-id="0dc1c-111">En función del subsistema elegido, las opciones que se muestran para definir el paso de trabajo son diferentes.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-111">Based on the subsystem you choose, the options displayed for defining the job step change.</span></span>  
  
 <span data-ttu-id="0dc1c-112">**Ejecutar como**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-112">**Run as**</span></span>  
 <span data-ttu-id="0dc1c-113">Establece la cuenta de proxy del paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-113">Set the proxy account for the job step.</span></span> <span data-ttu-id="0dc1c-114">Los miembros del rol fijo de servidor sysadmin también pueden especificar la **cuenta de servicio del Agente SQL**.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-114">Members of the sysadmin fixed server role may also specify the **SQL Agent Service Account**.</span></span>  
  
 <span data-ttu-id="0dc1c-115">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-115">**Database**</span></span>  
 <span data-ttu-id="0dc1c-116">Establece la base de datos en la que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-116">Set the database that the job step runs in.</span></span> <span data-ttu-id="0dc1c-117">Esta opción no está disponible para todos los tipos de pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-117">This option is not available for all job step types.</span></span>  
  
 <span data-ttu-id="0dc1c-118">**Comando**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-118">**Command**</span></span>  
 <span data-ttu-id="0dc1c-119">Establece el comando que ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-119">Set the command that the job step runs.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="0dc1c-120">Opciones de pasos de trabajo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0dc1c-120">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="0dc1c-121">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-121">**Open**</span></span>  
 <span data-ttu-id="0dc1c-122">Carga el comando desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-122">Load the command from a file.</span></span>  
  
 <span data-ttu-id="0dc1c-123">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-123">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-124">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-124">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-125">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-125">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-126">Copia el texto seleccionado al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-126">Copy the selected text to the Clipboard.</span></span>  
  
 <span data-ttu-id="0dc1c-127">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-127">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-128">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-128">Paste the contents of the Clipboard.</span></span>  
  
 <span data-ttu-id="0dc1c-129">**Parse**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-129">**Parse**</span></span>  
 <span data-ttu-id="0dc1c-130">Comprueba la sintaxis del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-130">Check the syntax of the command.</span></span>  
  
## <a name="options-for-activex-script-job-steps"></a><span data-ttu-id="0dc1c-131">Opciones de pasos de trabajo de scripts ActiveX</span><span class="sxs-lookup"><span data-stu-id="0dc1c-131">Options for ActiveX Script Job Steps</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0dc1c-132">El subsistema de scripts ActiveX se quitará del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una versión futura de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dc1c-132">The ActiveX Scripting subsystem will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0dc1c-133">Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-133">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="0dc1c-134">**VBScript**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-134">**VBScript**</span></span>  
 <span data-ttu-id="0dc1c-135">Especifica [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition como lenguaje de los pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-135">Specify [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition as the language for the job steps.</span></span>  
  
 <span data-ttu-id="0dc1c-136">**JScript**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-136">**JScript**</span></span>  
 <span data-ttu-id="0dc1c-137">Especifica JScript como lenguaje de los pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-137">Specify JScript as the language for the job steps.</span></span>  
  
 <span data-ttu-id="0dc1c-138">**Otros**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-138">**Other**</span></span>  
 <span data-ttu-id="0dc1c-139">Escriba el nombre del lenguaje para los pasos de trabajo escritos en otro lenguaje de scripts.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-139">Type the name of the language for job steps written in another scripting language.</span></span>  
  
 <span data-ttu-id="0dc1c-140">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-140">**Open**</span></span>  
 <span data-ttu-id="0dc1c-141">Carga el comando desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-141">Load the command from a file.</span></span>  
  
 <span data-ttu-id="0dc1c-142">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-142">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-143">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-143">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-144">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-144">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-145">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-145">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-146">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-146">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-147">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-147">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="0dc1c-148">Opciones de pasos de trabajo del sistema operativo (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-148">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="0dc1c-149">**Procesar código de salida de un comando correcto**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-149">**Process exit code of a successful command**</span></span>  
 <span data-ttu-id="0dc1c-150">Escriba el código de salida que devuelve el comando para indicar un fin correcto.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-150">Type the exit code that the command returns to indicate success.</span></span>  
  
 <span data-ttu-id="0dc1c-151">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-151">**Open**</span></span>  
 <span data-ttu-id="0dc1c-152">Carga el comando desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-152">Load the command from a file.</span></span>  
  
 <span data-ttu-id="0dc1c-153">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-153">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-154">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-154">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-155">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-155">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-156">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-156">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-157">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-157">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-158">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-158">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="0dc1c-159">Opciones de pasos de trabajo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dc1c-159">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="0dc1c-160">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-160">**Open**</span></span>  
 <span data-ttu-id="0dc1c-161">Carga el script desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-161">Load the script from a file.</span></span>  
  
 <span data-ttu-id="0dc1c-162">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-162">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-163">Selecciona el texto del script.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-163">Select the text of the script.</span></span>  
  
 <span data-ttu-id="0dc1c-164">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-164">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-165">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-165">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-166">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-166">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-167">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-167">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-distributor-job-steps"></a><span data-ttu-id="0dc1c-168">Opciones de pasos de trabajo del Distribuidor de replicación</span><span class="sxs-lookup"><span data-stu-id="0dc1c-168">Options for Replication Distributor Job Steps</span></span>  
 <span data-ttu-id="0dc1c-169">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-169">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-170">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-170">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-171">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-171">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-172">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-172">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-173">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-173">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-174">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-174">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-merge-job-steps"></a><span data-ttu-id="0dc1c-175">Opciones de pasos de trabajo de mezclas de replicación</span><span class="sxs-lookup"><span data-stu-id="0dc1c-175">Options for Replication Merge Job Steps</span></span>  
 <span data-ttu-id="0dc1c-176">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-176">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-177">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-177">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-178">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-178">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-179">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-179">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-180">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-180">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-181">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-181">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="0dc1c-182">Opciones de pasos de trabajo del Lector de cola de replicación</span><span class="sxs-lookup"><span data-stu-id="0dc1c-182">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="0dc1c-183">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-183">**Database**</span></span>  
 <span data-ttu-id="0dc1c-184">La base de datos que se utiliza en el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-184">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="0dc1c-185">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-185">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-186">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-186">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-187">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-187">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-188">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-188">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-189">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-189">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-190">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-190">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-snapshot-job-steps"></a><span data-ttu-id="0dc1c-191">Opciones de pasos de trabajo de instantáneas de replicación</span><span class="sxs-lookup"><span data-stu-id="0dc1c-191">Options for Replication Snapshot Job Steps</span></span>  
 <span data-ttu-id="0dc1c-192">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-192">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-193">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-193">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-194">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-194">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-195">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-195">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-196">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-196">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-197">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-197">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-transaction-log-reader-job-steps"></a><span data-ttu-id="0dc1c-198">Opciones de pasos de trabajo del Registro del LOG de transacciones de replicación</span><span class="sxs-lookup"><span data-stu-id="0dc1c-198">Options for Replication Transaction-Log Reader Job Steps</span></span>  
 <span data-ttu-id="0dc1c-199">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-199">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-200">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-200">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-201">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-201">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-202">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-202">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-203">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-203">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-204">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-204">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-command-job-steps"></a><span data-ttu-id="0dc1c-205">Opciones de pasos de trabajo de Comando de SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0dc1c-205">Options for SQL Server Analysis Services Command Job Steps</span></span>  
 <span data-ttu-id="0dc1c-206">**Server**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-206">**Server**</span></span>  
 <span data-ttu-id="0dc1c-207">Establece el servidor donde se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-207">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="0dc1c-208">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-208">**Open**</span></span>  
 <span data-ttu-id="0dc1c-209">Carga el comando desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-209">Load the command from a file.</span></span>  
  
 <span data-ttu-id="0dc1c-210">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-210">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-211">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-211">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-212">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-212">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-213">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-213">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-214">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-214">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-215">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-215">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-query-job-steps"></a><span data-ttu-id="0dc1c-216">Opciones de pasos de trabajo de Consulta de SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0dc1c-216">Options for SQL Server Analysis Services Query Job Steps</span></span>  
 <span data-ttu-id="0dc1c-217">**Server**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-217">**Server**</span></span>  
 <span data-ttu-id="0dc1c-218">Establece el servidor donde se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-218">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="0dc1c-219">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-219">**Database**</span></span>  
 <span data-ttu-id="0dc1c-220">La base de datos que se utiliza en el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-220">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="0dc1c-221">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-221">**Open**</span></span>  
 <span data-ttu-id="0dc1c-222">Carga el comando desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-222">Load the command from a file.</span></span>  
  
 <span data-ttu-id="0dc1c-223">**Seleccionar todo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-223">**Select All**</span></span>  
 <span data-ttu-id="0dc1c-224">Selecciona el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-224">Select the text of the command.</span></span>  
  
 <span data-ttu-id="0dc1c-225">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-225">**Copy**</span></span>  
 <span data-ttu-id="0dc1c-226">Copia el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-226">Copy the selected text.</span></span>  
  
 <span data-ttu-id="0dc1c-227">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-227">**Paste**</span></span>  
 <span data-ttu-id="0dc1c-228">Pega el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-228">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-integration-services-package-execution-job-steps"></a><span data-ttu-id="0dc1c-229">Opciones de pasos de trabajo para la ejecución de paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="0dc1c-229">Options for Integration Services Package Execution Job Steps</span></span>  
  
### <a name="general-tab"></a><span data-ttu-id="0dc1c-230">Pestaña General</span><span class="sxs-lookup"><span data-stu-id="0dc1c-230">General Tab</span></span>  
 <span data-ttu-id="0dc1c-231">Especifique dónde se encuentra el paquete [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) y qué método de autenticación se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-231">Specify where the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package is located and what authentication method to use.</span></span> <span data-ttu-id="0dc1c-232">Cuando seleccione esta pestaña, aparecerán las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-232">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="0dc1c-233">**Origen del paquete**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-233">**Package source**</span></span>  
 <span data-ttu-id="0dc1c-234">Especifica dónde se almacena el paquete [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dc1c-234">Specify where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="0dc1c-235">Elija alguna de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0dc1c-235">Choose one of the following:</span></span>  
  
-   <span data-ttu-id="0dc1c-236">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-236">**SQL Server**</span></span>  
  
-   <span data-ttu-id="0dc1c-237">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-237">**File system**</span></span>  
  
-   <span data-ttu-id="0dc1c-238">**Almacén de paquetes SSIS**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-238">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="0dc1c-239">**Server**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-239">**Server**</span></span>  
 <span data-ttu-id="0dc1c-240">Escriba el nombre del servidor en donde se almacena el paquete [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dc1c-240">Type the server name where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="0dc1c-241">Esta opción solo está disponible cuando se especifica **SQL Server** o **Almacén de paquetes SSIS** para **Origen del paquete**.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-241">This option is only available when **SQL Server** or **SSIS Package Store** is specified for **Package Source**.</span></span>  
  
 <span data-ttu-id="0dc1c-242">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-242">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="0dc1c-243">Para los inicios de sesión en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se utiliza la autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-243">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="0dc1c-244">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-244">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="0dc1c-245">Para los inicios de sesión en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se utiliza la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dc1c-245">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="0dc1c-246">Si selecciona este método de autenticación, escriba el **nombre de usuario** y la **contraseña**adecuados.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-246">If this method of authentication is selected, enter the appropriate **User name** and **Password**.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0dc1c-247">se proporciona por motivos de compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-247">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="0dc1c-248">Para mejorar la seguridad, utilice la autenticación de Windows siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-248">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="0dc1c-249">**Package**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-249">**Package**</span></span>  
 <span data-ttu-id="0dc1c-250">Escriba la ubicación del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-250">Type the location of the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0dc1c-251">Para los paquetes de [!INCLUDE[ssIS](../../includes/ssis-md.md)] protegidos mediante contraseña, haga clic en la pestaña **Configuraciones** para escribir la contraseña en el cuadro de diálogo **Contraseña del paquete** .</span><span class="sxs-lookup"><span data-stu-id="0dc1c-251">For password-protected [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages, click the **Configurations** tab to enter the password in the **Package Password** dialog box.</span></span> <span data-ttu-id="0dc1c-252">En caso contrario, el trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ejecuta el paquete protegido mediante contraseña generará un error.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-252">Otherwise, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that executes the password-protected package will fail.</span></span>  
  
### <a name="configurations-tab"></a><span data-ttu-id="0dc1c-253">Configuraciones (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-253">Configurations Tab</span></span>  
 <span data-ttu-id="0dc1c-254">Especifique las opciones de configuración del paquete [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dc1c-254">Specify configuration options for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span> <span data-ttu-id="0dc1c-255">Cuando selecciona esta pestaña, dispone de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-255">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="0dc1c-256">**Archivos de configuración**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-256">**Configuration files**</span></span>  
 <span data-ttu-id="0dc1c-257">Presenta una lista de los archivos de configuración del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-257">Lists the configuration files for the package.</span></span>  
  
 <span data-ttu-id="0dc1c-258">**Add**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-258">**Add**</span></span>  
 <span data-ttu-id="0dc1c-259">Agrega un archivo de configuración para el paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-259">Add a configuration file for the package.</span></span>  
  
 <span data-ttu-id="0dc1c-260">**Remove**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-260">**Remove**</span></span>  
 <span data-ttu-id="0dc1c-261">Quita un archivo de configuración del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-261">Remove a configuration file for the package.</span></span>  
  
 <span data-ttu-id="0dc1c-262">**Subir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-262">**Move Up**</span></span>  
 <span data-ttu-id="0dc1c-263">Sube el archivo de configuración seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-263">Move the selected configuration file up.</span></span>  
  
 <span data-ttu-id="0dc1c-264">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-264">**Move Down**</span></span>  
 <span data-ttu-id="0dc1c-265">Baja el archivo de configuración seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-265">Move the selected configuration file down.</span></span>  
  
### <a name="command-files-tab"></a><span data-ttu-id="0dc1c-266">Archivos de comandos (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-266">Command Files Tab</span></span>  
 <span data-ttu-id="0dc1c-267">Seleccione los archivos de comandos del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-267">Select command files for the package.</span></span> <span data-ttu-id="0dc1c-268">Estos archivos se procesan en el orden en que aparecen en la lista.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-268">Command files are processed in the order in which they appear in the list.</span></span> <span data-ttu-id="0dc1c-269">Cuando seleccione esta pestaña, aparecerán las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-269">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="0dc1c-270">**Archivos de comandos**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-270">**Command files**</span></span>  
 <span data-ttu-id="0dc1c-271">Presenta una lista de los archivos de comandos del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-271">Lists the command files for the package.</span></span>  
  
 <span data-ttu-id="0dc1c-272">**Add**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-272">**Add**</span></span>  
 <span data-ttu-id="0dc1c-273">Agrega un archivo de comandos.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-273">Add a command file.</span></span>  
  
 <span data-ttu-id="0dc1c-274">**Remove**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-274">**Remove**</span></span>  
 <span data-ttu-id="0dc1c-275">Quita el archivo de comandos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-275">Remove the selected command file.</span></span>  
  
 <span data-ttu-id="0dc1c-276">**Subir**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-276">**Move Up**</span></span>  
 <span data-ttu-id="0dc1c-277">Sube el archivo de comandos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-277">Move the selected command file up.</span></span>  
  
 <span data-ttu-id="0dc1c-278">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-278">**Move Down**</span></span>  
 <span data-ttu-id="0dc1c-279">Baja el archivo de comandos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-279">Move the selected command file down.</span></span>  
  
### <a name="data-sources-tab"></a><span data-ttu-id="0dc1c-280">Orígenes de datos (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-280">Data Sources Tab</span></span>  
 <span data-ttu-id="0dc1c-281">En esta pestaña puede consultar los orígenes de datos especificados en el paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-281">View the data sources specified in the package on this tab.</span></span>  
  
 <span data-ttu-id="0dc1c-282">**Connection Manager**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-282">**Connection Manager**</span></span>  
 <span data-ttu-id="0dc1c-283">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-283">View the name of the data source.</span></span>  
  
 <span data-ttu-id="0dc1c-284">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-284">**Description**</span></span>  
 <span data-ttu-id="0dc1c-285">Muestra la descripción del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-285">View the description of the data source.</span></span>  
  
 <span data-ttu-id="0dc1c-286">**Cadena de conexión**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-286">**Connection String**</span></span>  
 <span data-ttu-id="0dc1c-287">Muestra la cadena de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-287">View the connection string for the data source.</span></span>  
  
### <a name="execution-options-tab"></a><span data-ttu-id="0dc1c-288">Opciones de ejecución (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-288">Execution Options Tab</span></span>  
 <span data-ttu-id="0dc1c-289">En esta pestaña puede consultar o cambiar las opciones de configuración del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-289">View or change the execution options for the package on this tab.</span></span>  
  
 <span data-ttu-id="0dc1c-290">**Rechazar el paquete cuando haya advertencias de validación**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-290">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="0dc1c-291">Active esta opción para rechazar la ejecución del paquete si se producen advertencias de validación.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-291">Select this option for package execution to fail if validation warnings occur.</span></span>  
  
 <span data-ttu-id="0dc1c-292">**Validar el paquete sin ejecutarlo**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-292">**Validate package without executing**</span></span>  
 <span data-ttu-id="0dc1c-293">Active esta opción para que el paso de trabajo valide, pero no ejecute, el paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-293">Select this option for the job step to validate, but not execute, the package.</span></span>  
  
 <span data-ttu-id="0dc1c-294">**Número máximo de ejecutables simultáneos**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-294">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="0dc1c-295">Número máximo de archivos ejecutables que se pueden ejecutar a la vez.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-295">Maximum number of executable files that can run at one time.</span></span>  
  
 <span data-ttu-id="0dc1c-296">**Habilitar puntos de comprobación de paquetes**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-296">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="0dc1c-297">Active esta opción para que el paso de trabajo utilice puntos de comprobación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-297">Select this option for the job step to use package checkpoints.</span></span>  
  
 <span data-ttu-id="0dc1c-298">**Archivo de punto de comprobación**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-298">**Checkpoint file**</span></span>  
 <span data-ttu-id="0dc1c-299">Escriba el nombre del archivo de punto de comprobación del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-299">Type the name of the package checkpoint file.</span></span>  
  
 <span data-ttu-id="0dc1c-300">**...**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-300">**...**</span></span>  
 <span data-ttu-id="0dc1c-301">Busque el archivo de punto de comprobación del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-301">Browse to find the package checkpoint file.</span></span>  
  
 <span data-ttu-id="0dc1c-302">**Omitir opciones de reinicio**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-302">**Override restart options**</span></span>  
 <span data-ttu-id="0dc1c-303">Active esta opción para especificar en este paso de trabajo opciones de reinicio diferentes de las opciones especificadas en el paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-303">Select this option to specify restart options for this job step that are different from the restart options specified in the package.</span></span>  
  
 <span data-ttu-id="0dc1c-304">**Opción de reinicio**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-304">**Restart option**</span></span>  
 <span data-ttu-id="0dc1c-305">Seleccione la acción que debe realizarse cuando se reinicia el paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-305">Select the action to take when the package restarts.</span></span>  
  
### <a name="logging-tab"></a><span data-ttu-id="0dc1c-306">Registro (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-306">Logging Tab</span></span>  
 <span data-ttu-id="0dc1c-307">En esta pestaña puede consultar o cambiar los proveedores de registro del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-307">View or change the log providers for the package on this tab.</span></span>  
  
 <span data-ttu-id="0dc1c-308">**Proveedor de registro**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-308">**Log Provider**</span></span>  
 <span data-ttu-id="0dc1c-309">Seleccione el valor de ClassID del proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-309">Select the ClassID for the log provider.</span></span>  
  
 <span data-ttu-id="0dc1c-310">**Cadena de configuración**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-310">**Configuration String**</span></span>  
 <span data-ttu-id="0dc1c-311">Escriba la cadena de configuración del proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-311">Type the configuration string for the log provider.</span></span>  
  
 <span data-ttu-id="0dc1c-312">**Remove**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-312">**Remove**</span></span>  
 <span data-ttu-id="0dc1c-313">Quita el proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-313">Removes the log provider.</span></span>  
  
### <a name="set-values-tab"></a><span data-ttu-id="0dc1c-314">Valores establecidos (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-314">Set Values Tab</span></span>  
 <span data-ttu-id="0dc1c-315">En esta pestaña puede consultar o cambiar valores de propiedades del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-315">View or change property values for the package on this tab.</span></span>  
  
 <span data-ttu-id="0dc1c-316">**Ruta de acceso de la propiedad**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-316">**Property path**</span></span>  
 <span data-ttu-id="0dc1c-317">Permite ver o cambiar la ruta de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-317">View or change the path for the property.</span></span>  
  
 <span data-ttu-id="0dc1c-318">**Valor**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-318">**Value**</span></span>  
 <span data-ttu-id="0dc1c-319">Permite ver o cambiar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-319">View or change the value for the property.</span></span>  
  
 <span data-ttu-id="0dc1c-320">**Remove**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-320">**Remove**</span></span>  
 <span data-ttu-id="0dc1c-321">Quita la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-321">Removes the property.</span></span>  
  
### <a name="verification-tab"></a><span data-ttu-id="0dc1c-322">Comprobación (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-322">Verification Tab</span></span>  
 <span data-ttu-id="0dc1c-323">En esta pestaña puede seleccionar las opciones de comprobación del paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-323">Select the verification options for the job step on this tab.</span></span>  
  
 <span data-ttu-id="0dc1c-324">**Ejecutar solo los paquetes firmados**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-324">**Execute only signed packages**</span></span>  
 <span data-ttu-id="0dc1c-325">Solo ejecuta paquetes con firma.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-325">Run only packages that have been signed.</span></span> <span data-ttu-id="0dc1c-326">Si se selecciona esta opción, el paso de trabajo se rechaza si es un paquete sin firma.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-326">When this option is selected, the job step fails if the package is unsigned.</span></span>  
  
 <span data-ttu-id="0dc1c-327">**Comprobar la compilación del paquete**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-327">**Verify package build**</span></span>  
 <span data-ttu-id="0dc1c-328">Solo ejecuta paquetes con un número de generación específico.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-328">Run only packages with a specific build number.</span></span> <span data-ttu-id="0dc1c-329">Si se selecciona esta opción, el paso de trabajo se rechaza si el paquete no tiene el número de generación especificado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-329">When this option is selected, the job step fails if the package does not have the specified build number.</span></span>  
  
 <span data-ttu-id="0dc1c-330">**Compilar**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-330">**Build**</span></span>  
 <span data-ttu-id="0dc1c-331">Escriba el número de generación del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-331">Type the build number of the package.</span></span>  
  
 <span data-ttu-id="0dc1c-332">**Comprobar el Id. del paquete**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-332">**Verify package ID**</span></span>  
 <span data-ttu-id="0dc1c-333">Ejecuta solo los paquetes que tienen un identificador concreto.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-333">Run only packages with a specific ID.</span></span> <span data-ttu-id="0dc1c-334">Si se selecciona esta opción, el paso de trabajo se rechaza si el paquete no tiene el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-334">When this option is selected, the job step fails if the package does not have the specified ID.</span></span>  
  
 <span data-ttu-id="0dc1c-335">**Id. de paquete**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-335">**Package ID**</span></span>  
 <span data-ttu-id="0dc1c-336">Escriba el Id. del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-336">Type the package ID.</span></span>  
  
 <span data-ttu-id="0dc1c-337">**Comprobar el Id. de versión**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-337">**Verify version ID**</span></span>  
 <span data-ttu-id="0dc1c-338">Ejecuta solo los paquetes que tienen un identificador de versión concreto.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-338">Run only packages with a specific version ID.</span></span> <span data-ttu-id="0dc1c-339">Si se selecciona esta opción, el paso de trabajo se rechaza si el paquete no tiene el identificador de versión especificado.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-339">When this option is selected, the job step fails if the package does not have the specified version ID.</span></span>  
  
 <span data-ttu-id="0dc1c-340">**Id. de la versión**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-340">**Version ID**</span></span>  
 <span data-ttu-id="0dc1c-341">Escriba el Id. de versión.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-341">Type the version ID.</span></span>  
  
### <a name="command-line-tab"></a><span data-ttu-id="0dc1c-342">Línea de comandos (pestaña)</span><span class="sxs-lookup"><span data-stu-id="0dc1c-342">Command Line Tab</span></span>  
 <span data-ttu-id="0dc1c-343">En esta pestaña puede especificar las opciones de línea de comandos del paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-343">Specify command-line options for the package.</span></span> <span data-ttu-id="0dc1c-344">Cuando selecciona esta pestaña, dispone de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-344">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="0dc1c-345">**Restaurar las opciones originales**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-345">**Restore the original options**</span></span>  
 <span data-ttu-id="0dc1c-346">Utiliza las opciones de línea de comandos establecidas en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-346">Use the command-line options set in this dialog.</span></span>  
  
 <span data-ttu-id="0dc1c-347">**Editar la línea de comandos manualmente**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-347">**Edit the command line manually**</span></span>  
 <span data-ttu-id="0dc1c-348">Debe especificar las opciones en la ventana de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-348">Specify options in the command-line window.</span></span>  
  
 <span data-ttu-id="0dc1c-349">**Línea de comandos**</span><span class="sxs-lookup"><span data-stu-id="0dc1c-349">**Command line**</span></span>  
 <span data-ttu-id="0dc1c-350">Escriba las opciones de línea de comandos que se van a utilizar en este paquete.</span><span class="sxs-lookup"><span data-stu-id="0dc1c-350">Type the command line options to use for this package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc1c-351">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0dc1c-351">See Also</span></span>  
 <span data-ttu-id="0dc1c-352">[Administrar pasos de trabajo](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="0dc1c-352">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="0dc1c-353">[Trabajos de Agente SQL Server para paquetes](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span><span class="sxs-lookup"><span data-stu-id="0dc1c-353">[SQL Server Agent Jobs for Packages](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span></span>  
 [<span data-ttu-id="0dc1c-354">Administración del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="0dc1c-354">Replication Agent Administration</span></span>](../../relational-databases/replication/agents/replication-agent-administration.md)  
  
  
