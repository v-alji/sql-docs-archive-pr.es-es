---
title: 'Propiedades de paso de trabajo: nuevo paso de trabajo (página avanzadas) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepadvanced.f1
ms.assetid: bdecfd4f-bcd8-4ba2-8ada-fbb636314f40
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42820ffbdbb89261e839b5d1011f3a91b5841c86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748472"
---
# <a name="job-step-properties-new-job-step-advanced-page"></a><span data-ttu-id="2115f-102">Propiedades de paso de trabajo: Nuevo paso de trabajo (página Avanzado)</span><span class="sxs-lookup"><span data-stu-id="2115f-102">Job Step Properties: New Job Step (Advanced Page)</span></span>
  <span data-ttu-id="2115f-103">Utilice esta página para ver y cambiar las propiedades de un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] paso de trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="2115f-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2115f-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="2115f-104">Options</span></span>  
 <span data-ttu-id="2115f-105">**Acción en caso de éxito**</span><span class="sxs-lookup"><span data-stu-id="2115f-105">**On success action**</span></span>  
 <span data-ttu-id="2115f-106">Establece la acción que debe realizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si el paso de trabajo se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="2115f-106">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step succeeds.</span></span>  
  
 <span data-ttu-id="2115f-107">**Número de reintentos**</span><span class="sxs-lookup"><span data-stu-id="2115f-107">**Retry attempts**</span></span>  
 <span data-ttu-id="2115f-108">Establece el número de veces que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intenta volver a ejecutar un paso de trabajo con error.</span><span class="sxs-lookup"><span data-stu-id="2115f-108">Sets the number of times that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attempts to retry a failed job step.</span></span>  
  
 <span data-ttu-id="2115f-109">**Intervalo de reintento (minutos)**</span><span class="sxs-lookup"><span data-stu-id="2115f-109">**Retry interval (minutes)**</span></span>  
 <span data-ttu-id="2115f-110">Establece el tiempo que espera el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entre los reintentos.</span><span class="sxs-lookup"><span data-stu-id="2115f-110">Sets the amount of time for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to wait between retry attempts.</span></span>  
  
 <span data-ttu-id="2115f-111">**Acción en caso de error**</span><span class="sxs-lookup"><span data-stu-id="2115f-111">**On failure action**</span></span>  
 <span data-ttu-id="2115f-112">Establece la acción que debe realizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si el paso de trabajo no se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="2115f-112">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step fails.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="2115f-113">Opciones de pasos de trabajo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2115f-113">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="2115f-114">**Archivo de salida**</span><span class="sxs-lookup"><span data-stu-id="2115f-114">**Output file**</span></span>  
 <span data-ttu-id="2115f-115">Establece el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-115">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="2115f-116">Esta opción solo está disponible para los miembros del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="2115f-116">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="2115f-117">**...**</span><span class="sxs-lookup"><span data-stu-id="2115f-117">**...**</span></span>  
 <span data-ttu-id="2115f-118">Permite buscar el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-118">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2115f-119">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-119">**View**</span></span>  
 <span data-ttu-id="2115f-120">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , este botón está deshabilitado para ver los archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="2115f-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2115f-121">Para verlos, debe utilizar el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="2115f-121">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2115f-122">**Anexar la salida al archivo existente**</span><span class="sxs-lookup"><span data-stu-id="2115f-122">**Append output to existing file**</span></span>  
 <span data-ttu-id="2115f-123">Anexa la salida al contenido existente del archivo.</span><span class="sxs-lookup"><span data-stu-id="2115f-123">Append output to the existing contents of the file.</span></span> <span data-ttu-id="2115f-124">De lo contrario, el anterior contenido del archivo se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-124">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2115f-125">**Registro en tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-125">**Log to table**</span></span>  
 <span data-ttu-id="2115f-126">Registra la salida del paso de trabajo en la tabla **sysjobstepslogs** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2115f-126">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2115f-127">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-127">**View**</span></span>  
 <span data-ttu-id="2115f-128">Después de ejecutar el paso de trabajo al menos una vez, haga clic en **Ver** para consultar el resultado en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-128">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2115f-129">**Anexar salida a la entrada existente de la tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-129">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2115f-130">Anexa la salida al contenido existente de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-130">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2115f-131">De lo contrario, el anterior contenido de la tabla se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-131">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2115f-132">**Incluir salida de paso en historial**</span><span class="sxs-lookup"><span data-stu-id="2115f-132">**Include step output in history**</span></span>  
 <span data-ttu-id="2115f-133">Seleccione esta opción para incluir la salida del paso de trabajo en el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="2115f-133">Select this option to include output from the job step in the job history.</span></span>  
  
 <span data-ttu-id="2115f-134">**Ejecutar como usuario**</span><span class="sxs-lookup"><span data-stu-id="2115f-134">**Run as user**</span></span>  
 <span data-ttu-id="2115f-135">Si es miembro del rol fijo de servidor **sysadmin** , puede seleccionar otro inicio de sesión de SQL para ejecutar este paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-135">If you are a member of the **sysadmin** fixed server role, you can select another SQL login to run this job step.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="2115f-136">Opciones de pasos de trabajo del sistema operativo (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="2115f-136">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="2115f-137">**Archivo de salida**</span><span class="sxs-lookup"><span data-stu-id="2115f-137">**Output file**</span></span>  
 <span data-ttu-id="2115f-138">Establece el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-138">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2115f-139">**...**</span><span class="sxs-lookup"><span data-stu-id="2115f-139">**...**</span></span>  
 <span data-ttu-id="2115f-140">Permite buscar el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-140">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2115f-141">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-141">**View**</span></span>  
 <span data-ttu-id="2115f-142">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , este botón está deshabilitado para ver los archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="2115f-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2115f-143">Para verlos, debe utilizar el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="2115f-143">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2115f-144">**Anexar la salida al archivo existente**</span><span class="sxs-lookup"><span data-stu-id="2115f-144">**Append output to existing file**</span></span>  
 <span data-ttu-id="2115f-145">Anexa la salida del paso de trabajo al contenido anterior del archivo cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="2115f-145">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="2115f-146">**Registro en tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-146">**Log to table**</span></span>  
 <span data-ttu-id="2115f-147">Registra la salida del paso de trabajo en la tabla **sysjobstepslogs** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2115f-147">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2115f-148">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-148">**View**</span></span>  
 <span data-ttu-id="2115f-149">Después de ejecutar el paso de trabajo al menos una vez, haga clic en **Ver** para consultar el resultado en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-149">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2115f-150">**Anexar salida a la entrada existente de la tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-150">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2115f-151">Anexa la salida al contenido existente de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-151">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2115f-152">De lo contrario, el anterior contenido de la tabla se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-152">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2115f-153">**Incluir salida de paso en historial**</span><span class="sxs-lookup"><span data-stu-id="2115f-153">**Include step output in history**</span></span>  
 <span data-ttu-id="2115f-154">Seleccione esta opción para incluir la salida del paso de trabajo en el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="2115f-154">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="2115f-155">Opciones de pasos de trabajo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2115f-155">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="2115f-156">**Archivo de salida**</span><span class="sxs-lookup"><span data-stu-id="2115f-156">**Output file**</span></span>  
 <span data-ttu-id="2115f-157">Establece el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-157">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2115f-158">**...**</span><span class="sxs-lookup"><span data-stu-id="2115f-158">**...**</span></span>  
 <span data-ttu-id="2115f-159">Permite buscar el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-159">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2115f-160">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-160">**View**</span></span>  
 <span data-ttu-id="2115f-161">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , este botón está deshabilitado para ver los archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="2115f-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2115f-162">Para verlos, debe utilizar el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="2115f-162">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2115f-163">**Anexar la salida al archivo existente**</span><span class="sxs-lookup"><span data-stu-id="2115f-163">**Append output to existing file**</span></span>  
 <span data-ttu-id="2115f-164">Anexa la salida del paso de trabajo al contenido anterior del archivo cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="2115f-164">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="2115f-165">**Registro en tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-165">**Log to table**</span></span>  
 <span data-ttu-id="2115f-166">Registra la salida del paso de trabajo en la tabla **sysjobstepslogs** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2115f-166">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2115f-167">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-167">**View**</span></span>  
 <span data-ttu-id="2115f-168">Después de ejecutar el paso de trabajo al menos una vez, haga clic en **Ver** para consultar el resultado en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-168">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2115f-169">**Anexar salida a la entrada existente de la tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-169">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2115f-170">Anexa la salida al contenido existente de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-170">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2115f-171">De lo contrario, el anterior contenido de la tabla se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-171">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2115f-172">**Incluir salida de paso en historial**</span><span class="sxs-lookup"><span data-stu-id="2115f-172">**Include step output in history**</span></span>  
 <span data-ttu-id="2115f-173">Seleccione esta opción para incluir la salida del paso de trabajo en el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="2115f-173">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="2115f-174">Opciones de pasos de trabajo del Lector de cola de replicación</span><span class="sxs-lookup"><span data-stu-id="2115f-174">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="2115f-175">**Server**</span><span class="sxs-lookup"><span data-stu-id="2115f-175">**Server**</span></span>  
 <span data-ttu-id="2115f-176">Establece el servidor que se utiliza en un paso de trabajo de un lector de cola de replicación.</span><span class="sxs-lookup"><span data-stu-id="2115f-176">Sets the server to use for a replication queue reader job step.</span></span>  
  
 <span data-ttu-id="2115f-177">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="2115f-177">**Database**</span></span>  
 <span data-ttu-id="2115f-178">Establece la base de datos que se utiliza en un paso de trabajo de un lector de cola de replicación.</span><span class="sxs-lookup"><span data-stu-id="2115f-178">Sets the database to use for a replication queue reader job step.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-job-steps"></a><span data-ttu-id="2115f-179">Opciones de pasos de trabajo de SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2115f-179">Options for SQL Server Analysis Services Job Steps</span></span>  
 <span data-ttu-id="2115f-180">**Archivo de salida**</span><span class="sxs-lookup"><span data-stu-id="2115f-180">**Output file**</span></span>  
 <span data-ttu-id="2115f-181">Establece el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-181">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="2115f-182">Esta opción solo está disponible para los miembros del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="2115f-182">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="2115f-183">**...**</span><span class="sxs-lookup"><span data-stu-id="2115f-183">**...**</span></span>  
 <span data-ttu-id="2115f-184">Permite buscar el archivo que se utiliza para la salida desde el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-184">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2115f-185">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-185">**View**</span></span>  
 <span data-ttu-id="2115f-186">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], este botón está deshabilitado para ver los archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="2115f-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2115f-187">Para verlos, debe utilizar el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="2115f-187">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2115f-188">**Anexar la salida al archivo existente**</span><span class="sxs-lookup"><span data-stu-id="2115f-188">**Append output to existing file**</span></span>  
 <span data-ttu-id="2115f-189">Anexa la salida al contenido existente del archivo.</span><span class="sxs-lookup"><span data-stu-id="2115f-189">Append output to the existing contents of the file.</span></span> <span data-ttu-id="2115f-190">De lo contrario, el anterior contenido del archivo se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-190">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2115f-191">**Registro en tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-191">**Log to table**</span></span>  
 <span data-ttu-id="2115f-192">Registra la salida del paso de trabajo en la tabla **sysjobstepslogs** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2115f-192">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2115f-193">**Ver**</span><span class="sxs-lookup"><span data-stu-id="2115f-193">**View**</span></span>  
 <span data-ttu-id="2115f-194">Después de ejecutar el paso de trabajo al menos una vez, haga clic en **Ver** para consultar el resultado en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-194">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2115f-195">**Anexar salida a la entrada existente de la tabla**</span><span class="sxs-lookup"><span data-stu-id="2115f-195">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2115f-196">Anexa la salida al contenido existente de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2115f-196">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2115f-197">De lo contrario, el anterior contenido de la tabla se sobrescribe cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2115f-197">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2115f-198">**Incluir salida de paso en historial**</span><span class="sxs-lookup"><span data-stu-id="2115f-198">**Include step output in history**</span></span>  
 <span data-ttu-id="2115f-199">Seleccione esta opción para incluir la salida del paso de trabajo en el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="2115f-199">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2115f-200">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2115f-200">See Also</span></span>  
 [<span data-ttu-id="2115f-201">Administrar pasos de trabajo</span><span class="sxs-lookup"><span data-stu-id="2115f-201">Manage Job Steps</span></span>](manage-job-steps.md)  
  
  
