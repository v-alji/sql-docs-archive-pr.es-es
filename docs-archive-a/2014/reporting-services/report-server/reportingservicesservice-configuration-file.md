---
title: Archivo de configuración ReportingServicesService | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- traces [Reporting Services]
- Report Server Windows service, ReportingServicesService configuration file
- ReportingServicesService configuration file
ms.assetid: 40f4a401-cb61-4c42-b1ec-01acdacdacd1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5124631db9635211827dd3b1abbff7116101a61d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673482"
---
# <a name="reportingservicesservice-configuration-file"></a><span data-ttu-id="092c4-102">archivo de configuración ReportingServicesService</span><span class="sxs-lookup"><span data-stu-id="092c4-102">ReportingServicesService Configuration File</span></span>
  <span data-ttu-id="092c4-103">El archivo ReportingServicesService.exe.config incluye valores que configuran la traza.</span><span class="sxs-lookup"><span data-stu-id="092c4-103">The ReportingServicesService.exe.config file includes settings that configure tracing.</span></span>  
  
## <a name="file-location"></a><span data-ttu-id="092c4-104">Ubicación del archivo</span><span class="sxs-lookup"><span data-stu-id="092c4-104">File Location</span></span>  
 <span data-ttu-id="092c4-105">Este archivo se encuentra en la carpeta \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="092c4-105">This file is located in the \Reporting Services\Report Server\Bin folder.</span></span>  
  
## <a name="editing-guidelines"></a><span data-ttu-id="092c4-106">Directrices para editar</span><span class="sxs-lookup"><span data-stu-id="092c4-106">Editing Guidelines</span></span>  
 <span data-ttu-id="092c4-107">Puede modificar este archivo para cambiar el nombre del archivo de registro, o bien para aumentar o disminuir los niveles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="092c4-107">You can modify this file to rename the log file or to increase or decrease trace levels.</span></span> <span data-ttu-id="092c4-108">No modifique ningún otro parámetro.</span><span class="sxs-lookup"><span data-stu-id="092c4-108">Do not modify any of the other settings.</span></span> <span data-ttu-id="092c4-109">Para obtener instrucciones, vea [Modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="092c4-109">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="092c4-110">Para más información sobre los registros de seguimiento, vea [Registro de seguimiento del servicio del servidor de informes](report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="092c4-110">For more information about trace logs, see [Report Server Service Trace Log](report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="092c4-111">Configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="092c4-111">Example Configuration</span></span>  
 <span data-ttu-id="092c4-112">El siguiente ejemplo muestra los parámetros de configuración y los valores predeterminados que se encuentran en el archivo ReportingServicesService.exe.config.</span><span class="sxs-lookup"><span data-stu-id="092c4-112">The following example shows the settings and default values found in the ReportingServicesService.exe.config file.</span></span>  
  
```  
<configSections>  
      <section name="RStrace" type="Microsoft.ReportingServices.Diagnostics.RSTraceSectionHandler,Microsoft.ReportingServices.Diagnostics" />  
</configSections>  
<system.diagnostics>  
      <switches>  
          <add name="DefaultTraceSwitch" value="3" />  
      </switches>  
</system.diagnostics>  
<RStrace>  
      <add name="FileName" value="ReportServerService_" />  
      <add name="FileSizeLimitMb" value="32" />  
      <add name="KeepFilesForDays" value="14" />  
      <add name="Prefix" value="tid, time" />  
      <add name="TraceListeners" value="debugwindow, file" />  
      <add name="TraceFileMode" value="unique" />  
      <add name="Components" value="all" />  
</RStrace>  
<runtime>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
             <dependentAssembly>  
                    <assemblyIdentity name="Microsoft.ReportingServices.Interfaces"  
                        publicKeyToken="89845dcd8080cc91"  
                        culture="neutral" />  
                    <bindingRedirect oldVersion="8.0.242.0"  
                                     newVersion="10.0.0.0"/>  
                    <bindingRedirect oldVersion="9.0.242.0"  
                                     newVersion="10.0.0.0"/>  
             </dependentAssembly>  
      </assemblyBinding>  
      <gcServer enabled="true" />  
</runtime>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="092c4-113">Valores de configuración</span><span class="sxs-lookup"><span data-stu-id="092c4-113">Configuration Settings</span></span>  
 <span data-ttu-id="092c4-114">La siguiente tabla proporciona información sobre parámetros específicos.</span><span class="sxs-lookup"><span data-stu-id="092c4-114">The following table provides information about specific settings.</span></span> <span data-ttu-id="092c4-115">Los parámetros se presentan en el orden en que aparecen en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="092c4-115">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="092c4-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="092c4-116">Setting</span></span>|<span data-ttu-id="092c4-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="092c4-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="092c4-118">**RStrace**</span><span class="sxs-lookup"><span data-stu-id="092c4-118">**RStrace**</span></span>|<span data-ttu-id="092c4-119">Especifica espacios de nombres utilizados para errores y traza.</span><span class="sxs-lookup"><span data-stu-id="092c4-119">Specifies namespaces used for errors and tracing.</span></span>|  
|<span data-ttu-id="092c4-120">**DefaultTraceSwitch**</span><span class="sxs-lookup"><span data-stu-id="092c4-120">**DefaultTraceSwitch**</span></span>|<span data-ttu-id="092c4-121">Especifica el nivel de información que se incluye en el registro de seguimiento de ReportServerService.</span><span class="sxs-lookup"><span data-stu-id="092c4-121">Specifies the level of information that is reported to the ReportServerService trace log.</span></span> <span data-ttu-id="092c4-122">Cada nivel incluye la información proporcionada para todos los niveles inferiores.</span><span class="sxs-lookup"><span data-stu-id="092c4-122">Each level includes the information reported by all lower-numbered levels.</span></span> <span data-ttu-id="092c4-123">No se recomienda deshabilitar la traza.</span><span class="sxs-lookup"><span data-stu-id="092c4-123">Disabling tracing is not recommended.</span></span> <span data-ttu-id="092c4-124">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="092c4-124">Valid values include:</span></span><br /><br /> <span data-ttu-id="092c4-125">0= Deshabilita la traza</span><span class="sxs-lookup"><span data-stu-id="092c4-125">0= Disables tracing</span></span><br /><br /> <span data-ttu-id="092c4-126">1= Excepciones y reinicios</span><span class="sxs-lookup"><span data-stu-id="092c4-126">1= Exceptions and restarts</span></span><br /><br /> <span data-ttu-id="092c4-127">2= Excepciones, reinicios y advertencias</span><span class="sxs-lookup"><span data-stu-id="092c4-127">2= Exceptions, restarts, warnings</span></span><br /><br /> <span data-ttu-id="092c4-128">3= Excepciones, reinicios, advertencias y mensajes de estado (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="092c4-128">3= Exceptions, restarts, warnings, status messages (default)</span></span><br /><br /> <span data-ttu-id="092c4-129">4= Modo detallado</span><span class="sxs-lookup"><span data-stu-id="092c4-129">4= Verbose mode</span></span>|  
|<span data-ttu-id="092c4-130">**FileName**</span><span class="sxs-lookup"><span data-stu-id="092c4-130">**FileName**</span></span>|<span data-ttu-id="092c4-131">Especifica la primera parte del nombre del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="092c4-131">Specifies the first portion of the log file name.</span></span> <span data-ttu-id="092c4-132">El valor especificado en `Prefix` completa el resto del nombre.</span><span class="sxs-lookup"><span data-stu-id="092c4-132">The value specified by `Prefix` completes the rest of the name.</span></span> <span data-ttu-id="092c4-133">El nombre predeterminado es ReportServerService_.</span><span class="sxs-lookup"><span data-stu-id="092c4-133">By default, the name is ReportServerService_.</span></span>|  
|<span data-ttu-id="092c4-134">**FileSizeLimitMb**</span><span class="sxs-lookup"><span data-stu-id="092c4-134">**FileSizeLimitMb**</span></span>|<span data-ttu-id="092c4-135">Especifica un límite superior para el tamaño del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="092c4-135">Specifies an upper limit on trace log size.</span></span> <span data-ttu-id="092c4-136">El tamaño del archivo se indica en megabytes.</span><span class="sxs-lookup"><span data-stu-id="092c4-136">The file is measured in megabytes.</span></span> <span data-ttu-id="092c4-137">Los valores válidos son de 0 a un número entero definido como máximo.</span><span class="sxs-lookup"><span data-stu-id="092c4-137">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="092c4-138">El valor predeterminado es 32.</span><span class="sxs-lookup"><span data-stu-id="092c4-138">The default value is 32.</span></span>|  
|<span data-ttu-id="092c4-139">**KeepFilesForDays**</span><span class="sxs-lookup"><span data-stu-id="092c4-139">**KeepFilesForDays**</span></span>|<span data-ttu-id="092c4-140">Especifica los días tras los que se elimina un archivo de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="092c4-140">Specifies the number of days after which a trace log file will be deleted.</span></span> <span data-ttu-id="092c4-141">Los valores válidos son de 0 a un número entero definido como máximo.</span><span class="sxs-lookup"><span data-stu-id="092c4-141">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="092c4-142">El valor predeterminado es 14.</span><span class="sxs-lookup"><span data-stu-id="092c4-142">The default value is 14.</span></span>|  
|`Prefix`|<span data-ttu-id="092c4-143">Especifica un valor generado que distingue una instancia de registro de otra.</span><span class="sxs-lookup"><span data-stu-id="092c4-143">Specifies a generated value that distinguishes one log instance from another.</span></span> <span data-ttu-id="092c4-144">De manera predeterminada, se anexan valores de marca de tiempo a los nombres de los archivos de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="092c4-144">By default, timestamp values are appended to trace log file names.</span></span> <span data-ttu-id="092c4-145">Este valor se establece en " tid, time ".</span><span class="sxs-lookup"><span data-stu-id="092c4-145">This value is set to " tid, time ".</span></span> <span data-ttu-id="092c4-146">No modifique este parámetro.</span><span class="sxs-lookup"><span data-stu-id="092c4-146">Do not modify this setting.</span></span>|  
|<span data-ttu-id="092c4-147">**TraceListeners**</span><span class="sxs-lookup"><span data-stu-id="092c4-147">**TraceListeners**</span></span>|<span data-ttu-id="092c4-148">Especifica un destino de salida para el contenido del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="092c4-148">Specifies a target for outputting trace log content.</span></span> <span data-ttu-id="092c4-149">Se pueden especificar varios destinos separados por comas.</span><span class="sxs-lookup"><span data-stu-id="092c4-149">You can specify multiple targets using a comma to separate each one.</span></span> <span data-ttu-id="092c4-150">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="092c4-150">Valid values include:</span></span><br /><br /> <span data-ttu-id="092c4-151">DebugWindow (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="092c4-151">DebugWindow (default)</span></span><br /><br /> <span data-ttu-id="092c4-152">File (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="092c4-152">File (default)</span></span><br /><br /> <span data-ttu-id="092c4-153">StdOut</span><span class="sxs-lookup"><span data-stu-id="092c4-153">StdOut</span></span>|  
|<span data-ttu-id="092c4-154">**TraceFileMode**</span><span class="sxs-lookup"><span data-stu-id="092c4-154">**TraceFileMode**</span></span>|<span data-ttu-id="092c4-155">Especifica si los registros de seguimiento incluyen datos de un período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="092c4-155">Specifies whether trace logs contain data for a 24-hour period.</span></span> <span data-ttu-id="092c4-156">Es recomendable tener un único registro de seguimiento para cada componente y día.</span><span class="sxs-lookup"><span data-stu-id="092c4-156">You should have one unique trace log for each component on each day.</span></span> <span data-ttu-id="092c4-157">Este valor se establece en "Unique (default)".</span><span class="sxs-lookup"><span data-stu-id="092c4-157">This value is set to "Unique (default)".</span></span> <span data-ttu-id="092c4-158">No modifique este valor.</span><span class="sxs-lookup"><span data-stu-id="092c4-158">Do not modify this value.</span></span>|  
|<span data-ttu-id="092c4-159">**Componentes**</span><span class="sxs-lookup"><span data-stu-id="092c4-159">**Components**</span></span>|<span data-ttu-id="092c4-160">Especifica los componentes para los que se crean registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="092c4-160">Specifies the components for which trace logs are created.</span></span> <span data-ttu-id="092c4-161">El valor predeterminado es `all`.</span><span class="sxs-lookup"><span data-stu-id="092c4-161">The default value is `all`.</span></span> <span data-ttu-id="092c4-162">Otros valores válidos para este parámetro son los nombres de los componentes internos.</span><span class="sxs-lookup"><span data-stu-id="092c4-162">Other valid values for this setting include the names of internal components.</span></span> <span data-ttu-id="092c4-163">No modifique este valor.</span><span class="sxs-lookup"><span data-stu-id="092c4-163">Do not modify this value.</span></span>|  
|<span data-ttu-id="092c4-164">**Runtime**</span><span class="sxs-lookup"><span data-stu-id="092c4-164">**Runtime**</span></span>|<span data-ttu-id="092c4-165">Especifica valores de configuración que ofrecen compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="092c4-165">Specifies configuration settings that support backward compatibility with the previous version.</span></span> <span data-ttu-id="092c4-166">Los valores de tiempo de ejecución se utilizan para redirigir a la nueva versión las solicitudes destinadas a versiones anteriores de Microsoft.ReportingServices.Interfaces.</span><span class="sxs-lookup"><span data-stu-id="092c4-166">Runtime settings are used to redirect requests that target the previous version of Microsoft.ReportingServices.Interfaces to the new version.</span></span><br /><br /> <span data-ttu-id="092c4-167">Todos los valores de configuración de esta sección están descritos en la documentación del producto [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="092c4-167">All of the configuration settings in this section are described in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] product documentation.</span></span> <span data-ttu-id="092c4-168">Para obtener más información, vea la sección sobre los valores de esquema de tiempo de ejecución en el sitio web de MSDN o en la documentación de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="092c4-168">For more information, search for "Runtime Schema Settings" on the MSDN Web site or in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="092c4-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="092c4-169">See Also</span></span>  
 <span data-ttu-id="092c4-170">[Archivos de configuración de Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="092c4-170">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="092c4-171">Registro de seguimiento del servicio del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="092c4-171">Report Server Service Trace Log</span></span>](report-server-service-trace-log.md)  
  
  
