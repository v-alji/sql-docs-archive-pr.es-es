---
title: Referencia de la utilidad del símbolo del sistema (Motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server]
- command prompt utilities [SQL Server], about command prompt utilities
- command prompt [SQL Server]
- utilities [SQL Server], command prompt
- command prompt [SQL Server], utilities
ms.assetid: 48364bd9-6ea7-45e9-a332-acf3d81bbfae
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb5f15bb37bd4e15dd93404be3df47ce359586b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744460"
---
# <a name="command-prompt-utility-reference-database-engine"></a><span data-ttu-id="468d4-102">Referencia de la utilidad del símbolo del sistema (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="468d4-102">Command Prompt Utility Reference (Database Engine)</span></span>
  <span data-ttu-id="468d4-103">Las utilidades de símbolo del sistema permiten incluir en scripts las operaciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="468d4-103">Command prompt utilities enable you to script [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] operations.</span></span> <span data-ttu-id="468d4-104">La siguiente tabla contiene una lista de utilidades de símbolo del sistema que se suministran junto con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="468d4-104">The following table contains a list of command prompt utilities that ship with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="468d4-105">**Utilidad**</span><span class="sxs-lookup"><span data-stu-id="468d4-105">**Utility**</span></span>|<span data-ttu-id="468d4-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="468d4-106">**Description**</span></span>|<span data-ttu-id="468d4-107">**Instalada en**</span><span class="sxs-lookup"><span data-stu-id="468d4-107">**Installed in**</span></span>|  
|-----------------|---------------------|----------------------|  
|[<span data-ttu-id="468d4-108">bcp (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-108">bcp Utility</span></span>](bcp-utility.md)|<span data-ttu-id="468d4-109">Se usa para copiar datos entre una instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y un archivo de datos en un formato especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="468d4-109">Used to copy data between an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and a data file in a user-specified format.</span></span>|<span data-ttu-id="468d4-110">\<*drive*:>\Archivos de programa\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-110">\<*drive*:>\Program Files\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-111">dta (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-111">dta Utility</span></span>](dta/dta-utility.md)|<span data-ttu-id="468d4-112">Se utiliza para analizar una carga de trabajo y recomendar estructuras de diseño físico para optimizar el rendimiento del servidor para esa carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="468d4-112">Used to analyze a workload and recommend physical design structures to optimize server performance for that workload.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-113">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-113">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-114">dtexec (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-114">dtexec Utility</span></span>](../integration-services/packages/dtexec-utility.md)|<span data-ttu-id="468d4-115">Se usa para configurar y ejecutar un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="468d4-115">Used to configure and execute an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="468d4-116">Una versión de interfaz de usuario de esta utilidad del símbolo del sistema se denomina **DTExecUI**y abre la utilidad de ejecución de paquetes.</span><span class="sxs-lookup"><span data-stu-id="468d4-116">A user interface version of this command prompt utility is called **DTExecUI**, which brings up the Execute Package Utility.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-117">DTS\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-117">DTS\Binn</span></span>|  
|[<span data-ttu-id="468d4-118">dtutil (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-118">dtutil Utility</span></span>](../integration-services/dtutil-utility.md)|<span data-ttu-id="468d4-119">Se usa para administrar paquetes SSIS.</span><span class="sxs-lookup"><span data-stu-id="468d4-119">Used to manage SSIS packages.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-120">DTS\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-120">DTS\Binn</span></span>|  
|[<span data-ttu-id="468d4-121">Implementar soluciones de modelos con la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="468d4-121">Deploy Model Solutions with the Deployment Utility</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/deploy-model-solutions-with-the-deployment-utility)|<span data-ttu-id="468d4-122">Se utiliza para implementar proyectos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en instancias de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="468d4-122">Used to deploy [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects to instances of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-123">Tools\Binn\VShell\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="468d4-123">Tools\Binn\VShell\Common7\IDE</span></span>|  
|[<span data-ttu-id="468d4-124">osql (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-124">osql Utility</span></span>](osql-utility.md)|<span data-ttu-id="468d4-125">Permite especificar instrucciones, procedimientos del sistema y archivos de scripts de [!INCLUDE[tsql](../includes/tsql-md.md)] en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="468d4-125">Allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files at the command prompt.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-126">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-126">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-127">Utilidad de generador de perfiles</span><span class="sxs-lookup"><span data-stu-id="468d4-127">Profiler Utility</span></span>](profiler-utility.md)|<span data-ttu-id="468d4-128">Se utiliza para iniciar [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="468d4-128">Used to start [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] from a command prompt.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-129">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-129">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-130">Utilidad RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="468d4-130">RS.exe Utility &#40;SSRS&#41;</span></span>](../reporting-services/tools/rs-exe-utility-ssrs.md)|<span data-ttu-id="468d4-131">Se utiliza para ejecutar scripts diseñados para administrar servidores de informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="468d4-131">Used to run scripts designed for managing [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report servers.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-132">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-132">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-133">rsconfig (utilidad) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="468d4-133">rsconfig Utility &#40;SSRS&#41;</span></span>](../reporting-services/tools/rsconfig-utility-ssrs.md)|<span data-ttu-id="468d4-134">Se utiliza para configurar una conexión de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="468d4-134">Used to configure a report server connection.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-135">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-135">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-136">rskeymgmt (utilidad) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="468d4-136">rskeymgmt Utility &#40;SSRS&#41;</span></span>](../reporting-services/tools/rskeymgmt-utility-ssrs.md)|<span data-ttu-id="468d4-137">Se utiliza para administrar claves de cifrado en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="468d4-137">Used to manage encryption keys on a report server.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-138">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-138">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-139">sqlagent90 (aplicación)</span><span class="sxs-lookup"><span data-stu-id="468d4-139">sqlagent90 Application</span></span>](sqlagent90-application.md)|<span data-ttu-id="468d4-140">Se usa para iniciar el Agente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="468d4-140">Used to start [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from a command prompt.</span></span>|<span data-ttu-id="468d4-141">\<drive>:\Archivos de programa\Microsoft SQL Server\\<*nombre_instancia*>\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-141">\<drive>:\Program Files\Microsoft SQL Server\\<*instance_name*>\MSSQL\Binn</span></span>|  
|[<span data-ttu-id="468d4-142">Utilidad sqlcmd</span><span class="sxs-lookup"><span data-stu-id="468d4-142">sqlcmd Utility</span></span>](sqlcmd-utility.md)|<span data-ttu-id="468d4-143">Permite especificar instrucciones, procedimientos del sistema y archivos de scripts de [!INCLUDE[tsql](../includes/tsql-md.md)] en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="468d4-143">Allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files at the command prompt.</span></span>|<span data-ttu-id="468d4-144">\<*drive*:>\Archivos de programa\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-144">\<*drive*:>\Program Files\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-145">SQLdiag (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-145">SQLdiag Utility</span></span>](sqldiag-utility.md)|<span data-ttu-id="468d4-146">Se usa para recopilar información de diagnóstico para el Servicio de soporte y atención al cliente de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="468d4-146">Used to collect diagnostic information for [!INCLUDE[msCoName](../includes/msconame-md.md)] Customer Service and Support.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-147">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-147">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-148">Aplicación sqllogship</span><span class="sxs-lookup"><span data-stu-id="468d4-148">sqllogship Application</span></span>](sqllogship-application.md)|<span data-ttu-id="468d4-149">Las aplicaciones lo utilizan para realizar operaciones de copia de seguridad, copia y restauración, y tareas de limpieza asociadas en una configuración de trasvase de registros sin ejecutar trabajos de copia de seguridad, copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="468d4-149">Used by applications to perform backup, copy, and restore operations and associated clean-up tasks for a log shipping configuration without running the backup, copy, and restore jobs.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-150">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-150">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-151">SqlLocalDB (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-151">SqlLocalDB Utility</span></span>](sqllocaldb-utility.md)|<span data-ttu-id="468d4-152">Un modo de ejecución de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destinado a los desarrolladores de programas.</span><span class="sxs-lookup"><span data-stu-id="468d4-152">An execution mode of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] targeted to program developers.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-153">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-153">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-154">sqlmaint (utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-154">sqlmaint Utility</span></span>](sqlmaint-utility.md)|<span data-ttu-id="468d4-155">Se usa para ejecutar los planes de mantenimiento de bases de datos creados en versiones anteriores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="468d4-155">Used to execute database maintenance plans created in previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|<span data-ttu-id="468d4-156">\<drive>: \Archivos de Programa\microsoft SQL Server\MSSQL12. MSSQLSERVER\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-156">\<drive>:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn</span></span>|  
|[<span data-ttu-id="468d4-157">Utilidad sqlps</span><span class="sxs-lookup"><span data-stu-id="468d4-157">sqlps Utility</span></span>](sqlps-utility.md)|<span data-ttu-id="468d4-158">Se usa para ejecutar comandos y scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="468d4-158">Used to run PowerShell commands and scripts.</span></span> <span data-ttu-id="468d4-159">Carga y registra el proveedor de PowerShell de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="468d4-159">Loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-160">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-160">Tools\Binn</span></span>|  
|[<span data-ttu-id="468d4-161">sqlservr (aplicación)</span><span class="sxs-lookup"><span data-stu-id="468d4-161">sqlservr Application</span></span>](sqlservr-application.md)|<span data-ttu-id="468d4-162">Se usa para iniciar y detener una instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] desde el símbolo del sistema para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="468d4-162">Used to start and stop an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] from the command prompt for troubleshooting.</span></span>|<span data-ttu-id="468d4-163">\<drive>: \Archivos de Programa\microsoft SQL Server\MSSQL12. MSSQLSERVER\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="468d4-163">\<drive>:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn</span></span>|  
|[<span data-ttu-id="468d4-164">Ssms (Utilidad)</span><span class="sxs-lookup"><span data-stu-id="468d4-164">Ssms Utility</span></span>](../ssms/ssms-utility.md)|<span data-ttu-id="468d4-165">Se utiliza para iniciar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="468d4-165">Used to start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-166">Tools\Binn\VSShell\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="468d4-166">Tools\Binn\VSShell\Common7\IDE</span></span>|  
|[<span data-ttu-id="468d4-167">Utilidad tablediff</span><span class="sxs-lookup"><span data-stu-id="468d4-167">tablediff Utility</span></span>](tablediff-utility.md)|<span data-ttu-id="468d4-168">Se utiliza para comparar los datos de dos tablas y ver si no convergen, lo que es útil para solucionar problemas de una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="468d4-168">Used to compare the data in two tables for non-convergence, which is useful when troubleshooting a replication topology.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="468d4-169">COM</span><span class="sxs-lookup"><span data-stu-id="468d4-169">COM</span></span>|  
  
 <span data-ttu-id="468d4-170">**Para tener acceso a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager mediante [!INCLUDE[win8](../includes/win8-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="468d4-170">**To access [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager Using [!INCLUDE[win8](../includes/win8-md.md)]**</span></span>  
  
 <span data-ttu-id="468d4-171">Como el Administrador de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] es un complemento del programa [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console y no un programa independiente, el Administrador de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no aparece como una aplicación cuando se ejecuta [!INCLUDE[win8](../includes/win8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="468d4-171">Because [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager not does not appear as an application when running [!INCLUDE[win8](../includes/win8-md.md)].</span></span> <span data-ttu-id="468d4-172">Para abrir el Administrador de configuración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el botón de acceso **Buscar**, bajo **Aplicaciones**, escriba **SQLServerManager12.msc** (para [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]) o **SQLServerManager11.msc** (para [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]) y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="468d4-172">To open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager12.msc** (for [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]) or **SQLServerManager11.msc** for ([!INCLUDE[ssSQL11](../includes/sssql11-md.md)]), and then press **Enter**.</span></span>  
  
## <a name="command-prompt-utilities-syntax-conventions"></a><span data-ttu-id="468d4-173">Convenciones de la sintaxis de las herramientas del símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="468d4-173">Command Prompt Utilities Syntax Conventions</span></span>  
  
|<span data-ttu-id="468d4-174">**Convención**</span><span class="sxs-lookup"><span data-stu-id="468d4-174">**Convention**</span></span>|<span data-ttu-id="468d4-175">**Se usa para**</span><span class="sxs-lookup"><span data-stu-id="468d4-175">**Used for**</span></span>|  
|--------------------|------------------|  
|<span data-ttu-id="468d4-176">MAYÚSCULAS</span><span class="sxs-lookup"><span data-stu-id="468d4-176">UPPERCASE</span></span>|<span data-ttu-id="468d4-177">Instrucciones y términos usados en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="468d4-177">Statements and terms used at the operating system level.</span></span>|  
|`monospace`|<span data-ttu-id="468d4-178">Comandos y código de programación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="468d4-178">Sample commands and program code.</span></span>|  
|<span data-ttu-id="468d4-179">*cursiva*</span><span class="sxs-lookup"><span data-stu-id="468d4-179">*italic*</span></span>|<span data-ttu-id="468d4-180">Parámetros proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="468d4-180">User-supplied parameters.</span></span>|  
|<span data-ttu-id="468d4-181">**Negrita**</span><span class="sxs-lookup"><span data-stu-id="468d4-181">**bold**</span></span>|<span data-ttu-id="468d4-182">Comandos, parámetros y otros elementos de sintaxis que deben escribirse exactamente como se muestran.</span><span class="sxs-lookup"><span data-stu-id="468d4-182">Commands, parameters, and other syntax that must be typed exactly as shown.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="468d4-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="468d4-183">See Also</span></span>  
 <span data-ttu-id="468d4-184">[Replication Distribution Agent](../relational-databases/replication/agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="468d4-184">[Replication Distribution Agent](../relational-databases/replication/agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="468d4-185">[Replication Log Reader Agent](../relational-databases/replication/agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="468d4-185">[Replication Log Reader Agent](../relational-databases/replication/agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="468d4-186">[Replication Merge Agent](../relational-databases/replication/agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="468d4-186">[Replication Merge Agent](../relational-databases/replication/agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="468d4-187">[Agente de lectura de cola de replicación](../relational-databases/replication/agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="468d4-187">[Replication Queue Reader Agent](../relational-databases/replication/agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="468d4-188">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="468d4-188">Replication Snapshot Agent</span></span>](../relational-databases/replication/agents/replication-snapshot-agent.md)  
  
  