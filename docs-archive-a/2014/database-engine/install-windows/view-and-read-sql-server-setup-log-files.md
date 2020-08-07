---
title: Ver y leer los archivos de registro de instalación de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- displaying log files
- Setup [SQL Server], logs
- installation log files [SQL Server]
- installing SQL Server, logs
- errors [SQL Server], Setup
- logs [SQL Server], Setup
ms.assetid: 9d77af64-9084-4375-908a-d90f99535062
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 70f9bbb9a8ed72503dc6fe90077232748b2c4ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745400"
---
# <a name="view-and-read-sql-server-setup-log-files"></a><span data-ttu-id="34cde-102">Ver y leer los archivos de registro de instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="34cde-102">View and Read SQL Server Setup Log Files</span></span>
  <span data-ttu-id="34cde-103">Cada ejecución del programa de instalación crea archivos de registro con una nueva carpeta de registro con marca de tiempo en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-103">Each execution of Setup creates log files are created with a new timestamped log folder at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span> <span data-ttu-id="34cde-104">El formato del nombre de la carpeta de registro con marca de tiempo es AAAAMMDD_hhmmss.</span><span class="sxs-lookup"><span data-stu-id="34cde-104">The time-stamped log folder name format is YYYYMMDD_hhmmss.</span></span> <span data-ttu-id="34cde-105">Cuando el programa de instalación se ejecuta en modo desatendido, los registros se crean en % temp%\sqlsetup\*.log.</span><span class="sxs-lookup"><span data-stu-id="34cde-105">When Setup is run in an unattended mode, the logs are created at % temp%\sqlsetup\*.log.</span></span> <span data-ttu-id="34cde-106">Todos los archivos de la carpeta de registro se almacenan en el archivo Log\*.cab en su carpeta respectiva.</span><span class="sxs-lookup"><span data-stu-id="34cde-106">All files in the logs folder are archived into the Log\*.cab file in their respective log folder.</span></span>  
  
 <span data-ttu-id="34cde-107">Una solicitud de instalación típica pasa por tres fases de ejecución:</span><span class="sxs-lookup"><span data-stu-id="34cde-107">A typical Setup request goes through three execution phases:</span></span>  
  
1.  <span data-ttu-id="34cde-108">Texto de reglas globales</span><span class="sxs-lookup"><span data-stu-id="34cde-108">Global rules text</span></span>  
  
2.  <span data-ttu-id="34cde-109">Actualización de componentes</span><span class="sxs-lookup"><span data-stu-id="34cde-109">Component update</span></span>  
  
3.  <span data-ttu-id="34cde-110">Acción solicitada por el usuario</span><span class="sxs-lookup"><span data-stu-id="34cde-110">User-requested action</span></span>  
  
 <span data-ttu-id="34cde-111">En cada fase, el programa de instalación genera registros de detalle y de resumen con registros adicionales creados según corresponda.</span><span class="sxs-lookup"><span data-stu-id="34cde-111">In each phase, Setup generates detail and summary logs with additional logs created as appropriate.</span></span> <span data-ttu-id="34cde-112">Se llama al programa de instalación al menos tres veces por acción de instalación solicitada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="34cde-112">Setup is called at least three times per user-requested Setup action.</span></span>  
  
 <span data-ttu-id="34cde-113">Los archivos de almacén de datos contienen una instantánea del estado de todos los objetos de configuración sometidos a seguimiento por el proceso de instalación y son útiles para solucionar errores de configuración.</span><span class="sxs-lookup"><span data-stu-id="34cde-113">Datastore files contain a snapshot of the state of all configuration objects being tracked by the Setup process, and are useful for troubleshooting configuration errors.</span></span> <span data-ttu-id="34cde-114">Se crean volcados de archivo XML para objetos de almacén de datos para cada fase de ejecución.</span><span class="sxs-lookup"><span data-stu-id="34cde-114">XML file dumps are created for datastore objects for each execution phase.</span></span> <span data-ttu-id="34cde-115">Se guardan en su propia subcarpeta de registro debajo de la carpeta de registro con marca de tiempo, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="34cde-115">They are saved in their own log subfolder under the time-stamped log folder, as follows:</span></span>  
  
-   <span data-ttu-id="34cde-116">Datastore_GlobalRules</span><span class="sxs-lookup"><span data-stu-id="34cde-116">Datastore_GlobalRules</span></span>  
  
-   <span data-ttu-id="34cde-117">Datastore_ComponentUpdate</span><span class="sxs-lookup"><span data-stu-id="34cde-117">Datastore_ComponentUpdated</span></span>  
  
-   <span data-ttu-id="34cde-118">Almacén de datos</span><span class="sxs-lookup"><span data-stu-id="34cde-118">Datastore</span></span>  
  
 <span data-ttu-id="34cde-119">En las secciones siguientes se describen los archivos de registro de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34cde-119">The following sections describe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup log files.</span></span>  
  
## <a name="summary-text"></a><span data-ttu-id="34cde-120">Texto de resumen</span><span class="sxs-lookup"><span data-stu-id="34cde-120">Summary Text</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-121">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-121">Overview</span></span>  
 <span data-ttu-id="34cde-122">Este archivo muestra los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se detectaron durante la instalación, el entorno del sistema operativo, los valores de parámetros de línea de comandos, si se especifican, y el estado general de cada MSI/MSP que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="34cde-122">This file shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components that were detected during Setup, the operating system environment, command-line parameter values if they are specified, and the overall status of each MSI/MSP that was executed.</span></span>  
  
 <span data-ttu-id="34cde-123">El registro se organiza en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="34cde-123">The log is organized into the following sections:</span></span>  
  
-   <span data-ttu-id="34cde-124">Un resumen general de la ejecución</span><span class="sxs-lookup"><span data-stu-id="34cde-124">An overall summary of the execution</span></span>  
  
-   <span data-ttu-id="34cde-125">Las propiedades y la configuración del equipo en el que se ejecutó el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34cde-125">Properties and the configuration of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup was run</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="34cde-126">instaladas anteriormente en el equipo</span><span class="sxs-lookup"><span data-stu-id="34cde-126">product features previously installed on the computer</span></span>  
  
-   <span data-ttu-id="34cde-127">Descripción de la versión de instalación y las propiedades del paquete de instalación</span><span class="sxs-lookup"><span data-stu-id="34cde-127">Description of the installation version and installation package properties</span></span>  
  
-   <span data-ttu-id="34cde-128">Configuración de entrada en tiempo de ejecución proporcionada durante la instalación</span><span class="sxs-lookup"><span data-stu-id="34cde-128">Runtime input settings that are provided during install</span></span>  
  
-   <span data-ttu-id="34cde-129">Ubicación del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="34cde-129">Location of the configuration file</span></span>  
  
-   <span data-ttu-id="34cde-130">Detalles de los resultados de la ejecución</span><span class="sxs-lookup"><span data-stu-id="34cde-130">Details of the execution results</span></span>  
  
-   <span data-ttu-id="34cde-131">Reglas globales</span><span class="sxs-lookup"><span data-stu-id="34cde-131">Global rules</span></span>  
  
-   <span data-ttu-id="34cde-132">Reglas específicas del escenario de instalación</span><span class="sxs-lookup"><span data-stu-id="34cde-132">Rules specific to the installation scenario</span></span>  
  
-   <span data-ttu-id="34cde-133">Reglas con errores</span><span class="sxs-lookup"><span data-stu-id="34cde-133">Failed rules</span></span>  
  
-   <span data-ttu-id="34cde-134">Ubicación del archivo de informe de reglas</span><span class="sxs-lookup"><span data-stu-id="34cde-134">Location of the rules report file</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-135">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-135">Location</span></span>  
 <span data-ttu-id="34cde-136">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-136">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span>  
  
 <span data-ttu-id="34cde-137">Para encontrar errores en el archivo de texto de resumen, busque en el archivo usando las palabras clave "error" o "failed".</span><span class="sxs-lookup"><span data-stu-id="34cde-137">To find errors in the summary text file, search the file by using the "error" or "failed" keywords.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmsstxt"></a><span data-ttu-id="34cde-138">Summary_engine-base_AAAAMMDD_HHMMss.txt</span><span class="sxs-lookup"><span data-stu-id="34cde-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-139">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-139">Overview</span></span>  
 <span data-ttu-id="34cde-140">El archivo base de registro de resumen es similar al archivo de resumen y se genera durante el flujo de trabajo principal.</span><span class="sxs-lookup"><span data-stu-id="34cde-140">The summary_engine base file is similar to the summary file and is generated during the main workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-141">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-141">Location</span></span>  
 <span data-ttu-id="34cde-142">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-142">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmss_componentupdatetxt"></a><span data-ttu-id="34cde-143">Summary_engine-base_AAAAMMDD_HHMMss_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="34cde-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-144">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-144">Overview</span></span>  
 <span data-ttu-id="34cde-145">El archivo de registro de resumen de actualización de componentes es similar al archivo de resumen y se genera durante el flujo de trabajo de actualización de componentes.</span><span class="sxs-lookup"><span data-stu-id="34cde-145">The component update summary log file is similar to the summary file and is generated during the component update workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-146">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-146">Location</span></span>  
 <span data-ttu-id="34cde-147">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-147">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_versionnumbermmdd_hhmmss_globalrulestxt"></a><span data-ttu-id="34cde-148">Summary_engine base_ \<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="34cde-148">Summary_engine-base_\<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-149">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-149">Overview</span></span>  
 <span data-ttu-id="34cde-150">El archivo de registro de resumen de reglas globales es similar al archivo de resumen y se genera durante el flujo de trabajo de reglas globales.</span><span class="sxs-lookup"><span data-stu-id="34cde-150">The global rules summary log file is similar to the summary file generated during the global rules workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-151">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-151">Location</span></span>  
 <span data-ttu-id="34cde-152">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-152">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detailtxt"></a><span data-ttu-id="34cde-153">Detail.txt</span><span class="sxs-lookup"><span data-stu-id="34cde-153">Detail.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-154">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-154">Overview</span></span>  
 <span data-ttu-id="34cde-155">El archivo Detail.txt se genera durante el flujo de trabajo principal, como la instalación o la actualización, y proporciona los detalles de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="34cde-155">Detail.txt is generated for the main workflow such as install or upgrade, and provides the details of the execution.</span></span> <span data-ttu-id="34cde-156">Los registros del archivo se generan en función del momento en que se invocó cada acción durante la instalación y muestran el orden que se ejecutaron las acciones, y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="34cde-156">The logs in the file are generated based on the time when each action for the installation was invoked, and show the order in which the actions were executed, and their dependencies.</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-157">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-157">Location</span></span>  
 <span data-ttu-id="34cde-158">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup</span><span class="sxs-lookup"><span data-stu-id="34cde-158">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup</span></span>  
  
 <span data-ttu-id="34cde-159">Bootstrap\Log\\<AAAAMMDD_HHMM>\Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="34cde-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span></span>  
  
 <span data-ttu-id="34cde-160">Si se produce un error durante el proceso de instalación, la excepción o el error se registran al final de este archivo.</span><span class="sxs-lookup"><span data-stu-id="34cde-160">If an error occurs during the Setup process, the exception or error are logged at the end of this file.</span></span> <span data-ttu-id="34cde-161">Para encontrar los errores en este archivo, examine primero el final del archivo y, a continuación, realice una búsqueda en el mismo utilizando las palabras clave "error" o "exception".</span><span class="sxs-lookup"><span data-stu-id="34cde-161">To find the errors in this file, first examine the end of the file followed by a search of the file for the "error" or "exception" keywords.</span></span>  
  
## <a name="detail_componentupdatetxt"></a><span data-ttu-id="34cde-162">Detail_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="34cde-162">Detail_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-163">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-163">Overview</span></span>  
 <span data-ttu-id="34cde-164">El archivo Detail_ComponentUpdate.txt se genera durante el flujo de trabajo de actualización de componentes y es similar al archivo Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="34cde-164">The Detail_ComponentUpdate.txt file is generated for the component update workflow and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-165">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-165">Location</span></span>  
 <span data-ttu-id="34cde-166">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-166">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detail_globalrulestxt"></a><span data-ttu-id="34cde-167">Detail_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="34cde-167">Detail_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-168">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-168">Overview</span></span>  
 <span data-ttu-id="34cde-169">El archivo Detail_GlobalRules.txt se genera durante la ejecución de las reglas globales y es similar al archivo Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="34cde-169">Detail_GlobalRules.txt is generated for the global rules execution and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-170">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-170">Location</span></span>  
 <span data-ttu-id="34cde-171">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-171">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="msi-log-files"></a><span data-ttu-id="34cde-172">Archivos de registro de MSI</span><span class="sxs-lookup"><span data-stu-id="34cde-172">MSI log files</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-173">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-173">Overview</span></span>  
 <span data-ttu-id="34cde-174">Los archivos de registro de MSI proporcionan detalles del proceso de paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="34cde-174">The MSI log files provide details of the installation package process.</span></span> <span data-ttu-id="34cde-175">Los genera el programa MSIEXEC durante la instalación del paquete especificado.</span><span class="sxs-lookup"><span data-stu-id="34cde-175">They are generated by the MSIEXEC during the installation of the specified package.</span></span>  
  
 <span data-ttu-id="34cde-176">Tipos de archivos de registro de MSI:</span><span class="sxs-lookup"><span data-stu-id="34cde-176">Types of MSI log files:</span></span>  
  
-   <span data-ttu-id="34cde-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="34cde-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="34cde-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="34cde-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="34cde-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span><span class="sxs-lookup"><span data-stu-id="34cde-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-180">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-180">Location</span></span>  
 <span data-ttu-id="34cde-181">Los archivos de registro de MSI se encuentran en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\<name \> . log.</span><span class="sxs-lookup"><span data-stu-id="34cde-181">The MSI log files are located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\<Name\>.log.</span></span>  
  
 <span data-ttu-id="34cde-182">Al final del archivo se encuentra un resumen de la ejecución que incluye el estado de corrección o error y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="34cde-182">At the end of the file is a summary of the execution which includes the success or failure status and properties.</span></span> <span data-ttu-id="34cde-183">Para encontrar el error en el archivo de MSI, busque "value 3" y, normalmente, los errores se mostrarán cerca de la cadena.</span><span class="sxs-lookup"><span data-stu-id="34cde-183">To find the error in the MSI file, search for "value 3" and usually the errors can be found close to the string.</span></span>  
  
## <a name="configurationfileini"></a><span data-ttu-id="34cde-184">ConfigurationFile.ini</span><span class="sxs-lookup"><span data-stu-id="34cde-184">ConfigurationFile.ini</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-185">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-185">Overview</span></span>  
 <span data-ttu-id="34cde-186">El archivo de configuración contiene la configuración de entrada que se proporciona durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="34cde-186">The configuration file contains the input settings that are provided during installation.</span></span> <span data-ttu-id="34cde-187">Se puede usar para reiniciar la instalación sin tener que especificar la configuración manualmente.</span><span class="sxs-lookup"><span data-stu-id="34cde-187">It can be used to restart the installation without having to enter the settings manually.</span></span> <span data-ttu-id="34cde-188">Sin embargo, las contraseñas de las cuentas, los PID y algunos parámetros no se guardan en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="34cde-188">However, passwords for the accounts, PID, and some parameters are not saved in the configuration file.</span></span> <span data-ttu-id="34cde-189">La configuración se puede agregar al archivo o se puede proporcionar usando la línea de comandos o la interfaz de usuario del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="34cde-189">The settings can be either added to the file or provided by using the command line or the Setup user interface.</span></span> <span data-ttu-id="34cde-190">Para obtener más información, consulte [instalación de SQL Server 2014 mediante un archivo de configuración](install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="34cde-190">For more information, see [Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md).</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-191">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-191">Location</span></span>  
 <span data-ttu-id="34cde-192">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-192">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="systemconfigurationcheck_reporthtm"></a><span data-ttu-id="34cde-193">SystemConfigurationCheck_Report.htm</span><span class="sxs-lookup"><span data-stu-id="34cde-193">SystemConfigurationCheck_Report.htm</span></span>  
  
### <a name="overview"></a><span data-ttu-id="34cde-194">Información general</span><span class="sxs-lookup"><span data-stu-id="34cde-194">Overview</span></span>  
 <span data-ttu-id="34cde-195">El informe de comprobación de la configuración del sistema contiene una descripción breve de cada regla ejecutada y el estado de ejecución.</span><span class="sxs-lookup"><span data-stu-id="34cde-195">The system configuration check report contains a short description for each executed rule, and the execution status.</span></span>  
  
### <a name="location"></a><span data-ttu-id="34cde-196">Location</span><span class="sxs-lookup"><span data-stu-id="34cde-196">Location</span></span>  
 <span data-ttu-id="34cde-197">Se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="34cde-197">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34cde-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34cde-198">See Also</span></span>  
 <span data-ttu-id="34cde-199">[Temas de procedimientos de instalación](../../sql-server/install/installation-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="34cde-199">[Installation How-to Topics](../../sql-server/install/installation-how-to-topics.md) </span></span>  
 [<span data-ttu-id="34cde-200">Instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="34cde-200">Install SQL Server 2014</span></span>](install-sql-server.md)  
  
  
