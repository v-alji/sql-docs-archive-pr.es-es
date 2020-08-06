---
title: Generar archivos de volcado para la ejecución de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 61ef1731-cb3a-4afb-b4a4-059b04aeade0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61e511aaff6c3c77338211537a685f8a1dc82981
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662149"
---
# <a name="generating-dump-files-for-package-execution"></a><span data-ttu-id="bbb61-102">Generar archivos de volcado para la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="bbb61-102">Generating Dump Files for Package Execution</span></span>
  <span data-ttu-id="bbb61-103">En [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], puede crear archivos de volcado de depuración que proporcionen información sobre la ejecución de un paquete.</span><span class="sxs-lookup"><span data-stu-id="bbb61-103">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you can create debug dump files that provide information about the execution of a package.</span></span> <span data-ttu-id="bbb61-104">La información de estos archivos puede ayudarle a solucionar los problemas de ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="bbb61-104">The information in these files can help you in troubleshooting package execution issues.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbb61-105">Los archivos de volcado de depuración podrían contener información confidencial.</span><span class="sxs-lookup"><span data-stu-id="bbb61-105">Debug dump files might contain sensitive information.</span></span> <span data-ttu-id="bbb61-106">Para proteger la información confidencial, puede utilizar una lista de control de acceso (ACL) con objeto de restringir el acceso a los archivos o copiarlos en una carpeta con acceso restringido.</span><span class="sxs-lookup"><span data-stu-id="bbb61-106">To help protect sensitive information, you can use an access control list (ACL) to restrict access to the files, or copy the files to a folder that has restricted access.</span></span> <span data-ttu-id="bbb61-107">Por ejemplo, antes de enviar los archivos de depuración a los servicios de soporte al cliente de [!INCLUDE[msCoName](../../includes/msconame-md.md)] , se recomienda que quite cualquier información sensible o confidencial.</span><span class="sxs-lookup"><span data-stu-id="bbb61-107">For example, before you send your debug files to [!INCLUDE[msCoName](../../includes/msconame-md.md)] support services, we recommend that you remove any sensitive or confidential information.</span></span>  
  
 <span data-ttu-id="bbb61-108">Al implementar un proyecto en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , puede crear archivos de volcado que proporcionen información sobre la ejecución de paquetes incluidos en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bbb61-108">When you deploy a project to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you can create dump files that provide information about the execution of the packages contained in the project.</span></span> <span data-ttu-id="bbb61-109">Cuando finaliza el proceso de ISServerExec.exe, se crean los archivos de volcado.</span><span class="sxs-lookup"><span data-stu-id="bbb61-109">When the ISServerExec.exe process ends, the dump files are created.</span></span> <span data-ttu-id="bbb61-110">Puede especificar que un archivo de volcado se cree cuando aparezcan errores durante la ejecución del paquete; para ello, seleccione la opción **Volcado de errores** en el cuadro de diálogo **Ejecutar paquete** .</span><span class="sxs-lookup"><span data-stu-id="bbb61-110">You can specify that a dump file is created when errors occur during the package execution, by selecting the **Dump on errors** option in the **Execute Package** Dialog box.</span></span> <span data-ttu-id="bbb61-111">También puede utilizar los siguientes procedimientos almacenados:</span><span class="sxs-lookup"><span data-stu-id="bbb61-111">You can also use the following stored procedures:</span></span>  
  
-   <span data-ttu-id="bbb61-112">[catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) (catalog.set_execution_parameter_value [base de datos de SSISDB];)</span><span class="sxs-lookup"><span data-stu-id="bbb61-112">[catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database)</span></span>  
  
     <span data-ttu-id="bbb61-113">Llame a este procedimiento almacenado para configurar un archivo de volcado que se creará cuando se produzca algún error o evento y cuando se produzcan eventos específicos durante la ejecución de un paquete.</span><span class="sxs-lookup"><span data-stu-id="bbb61-113">Call this stored procedure to configure a dump file to be created when any error or event occurs, and when specific events occur, during a package execution.</span></span>  
  
-   [<span data-ttu-id="bbb61-114">catalog.create_execution_dump</span><span class="sxs-lookup"><span data-stu-id="bbb61-114">catalog.create_execution_dump</span></span>](/sql/integration-services/system-stored-procedures/catalog-create-execution-dump)  
  
     <span data-ttu-id="bbb61-115">Llame a este procedimiento almacenado para hacer que se detenga un paquete en ejecución y crear un archivo de volcado.</span><span class="sxs-lookup"><span data-stu-id="bbb61-115">Call this stored procedure to cause a running package to pause and create a dump file.</span></span>  
  
 <span data-ttu-id="bbb61-116">Si está implementando paquetes con el modelo de implementación de paquetes, puede crear archivos de volcado de depuración mediante la utilidad **dtexec** o la utilidad **dtutil** para especificar una opción de volcado de depuración en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bbb61-116">If you are deploying packages using the package deployment model, you create the debug dump files by using either the **dtexec** utility or the **dtutil** utility to specify a debug dump option in the command line.</span></span> <span data-ttu-id="bbb61-117">Para obtener más información, consulte [dtexec Utility](../packages/dtexec-utility.md) y [dtutil Utility](../dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="bbb61-117">For more information, see [dtexec Utility](../packages/dtexec-utility.md) and [dtutil Utility](../dtutil-utility.md).</span></span> <span data-ttu-id="bbb61-118">Para obtener más información sobre el modelo de implementación de paquetes, vea [implementación de proyectos y paquetes](../packages/deploy-integration-services-ssis-projects-and-packages.md) e implementación de paquetes [&#40;SSIS&#41;](../packages/legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="bbb61-118">For more information about the package deployment model, see [Deployment of Projects and Packages](../packages/deploy-integration-services-ssis-projects-and-packages.md) and [Package Deployment &#40;SSIS&#41;](../packages/legacy-package-deployment-ssis.md).</span></span>  
  
## <a name="debug-dump-file-format"></a><span data-ttu-id="bbb61-119">Formato de los archivos de volcado de depuración</span><span class="sxs-lookup"><span data-stu-id="bbb61-119">Debug Dump File Format</span></span>  
 <span data-ttu-id="bbb61-120">Cuando se especifica una opción de volcado de depuración, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea los archivos de volcado de depuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbb61-120">When you specify a debug dump option, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates the following debug dump files:</span></span>  
  
-   <span data-ttu-id="bbb61-121">Un archivo de volcado de depuración .mdmp.</span><span class="sxs-lookup"><span data-stu-id="bbb61-121">A .mdmp debug dump file.</span></span> <span data-ttu-id="bbb61-122">Es un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="bbb61-122">This is a binary file.</span></span>  
  
-   <span data-ttu-id="bbb61-123">El archivo de volcado de depuración .tmp.</span><span class="sxs-lookup"><span data-stu-id="bbb61-123">The .tmp debug dump file.</span></span> <span data-ttu-id="bbb61-124">Es un archivo de texto con formato.</span><span class="sxs-lookup"><span data-stu-id="bbb61-124">This is a text formatted file.</span></span>  
  
 <span data-ttu-id="bbb61-125">De forma predeterminada, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] almacena estos archivos en la carpeta *\<drive>:* \Archivos de programa\Microsoft SQL Server\110\Shared\ErrorDumps.</span><span class="sxs-lookup"><span data-stu-id="bbb61-125">By default, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stores these files in the folder, *\<drive>:* \Program Files\Microsoft SQL Server\110\Shared\ErrorDumps.</span></span>  
  
 <span data-ttu-id="bbb61-126">En la tabla siguiente solo se describen determinadas secciones del archivo .tmp.</span><span class="sxs-lookup"><span data-stu-id="bbb61-126">The following table describes only certain sections in the .tmp file.</span></span> <span data-ttu-id="bbb61-127">El archivo .tmp incluye datos adicionales que no se incluyen en la tabla.</span><span class="sxs-lookup"><span data-stu-id="bbb61-127">The .tmp file includes additional data that is not listed in the table.</span></span>  
  
|<span data-ttu-id="bbb61-128">Tipo de información</span><span class="sxs-lookup"><span data-stu-id="bbb61-128">Type of information</span></span>|<span data-ttu-id="bbb61-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbb61-129">Description</span></span>|<span data-ttu-id="bbb61-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbb61-130">Example</span></span>|  
|-------------------------|-----------------|-------------|  
|<span data-ttu-id="bbb61-131">Entorno</span><span class="sxs-lookup"><span data-stu-id="bbb61-131">Environment</span></span>|<span data-ttu-id="bbb61-132">Versión del sistema operativo, datos de uso de la memoria, identificador de proceso y nombre de imagen de proceso.</span><span class="sxs-lookup"><span data-stu-id="bbb61-132">Operating system version, memory usage data, process ID, and process image name.</span></span> <span data-ttu-id="bbb61-133">La información del entorno se encuentra al principio del archivo .tmp.</span><span class="sxs-lookup"><span data-stu-id="bbb61-133">The environment information is at the beginning of the .tmp file.</span></span>|<span data-ttu-id="bbb61-134"># SSIS Textual Dump taken at 9/13/2007 1:50:34 PM</span><span class="sxs-lookup"><span data-stu-id="bbb61-134"># SSIS Textual Dump taken at 9/13/2007 1:50:34 PM</span></span><br /><br /> <span data-ttu-id="bbb61-135">#PID 4120</span><span class="sxs-lookup"><span data-stu-id="bbb61-135">#PID 4120</span></span><br /><br /> <span data-ttu-id="bbb61-136">#Image Name [C:\Program Files\Microsoft SQL Server\110\DTS\Binn\DTExec.exe]</span><span class="sxs-lookup"><span data-stu-id="bbb61-136">#Image Name [C:\Program Files\Microsoft SQL Server\110\DTS\Binn\DTExec.exe]</span></span><br /><br /> <span data-ttu-id="bbb61-137"># OS major=6 minor=0 build=6000</span><span class="sxs-lookup"><span data-stu-id="bbb61-137"># OS major=6 minor=0 build=6000</span></span><br /><br /> <span data-ttu-id="bbb61-138"># Running on 2 amd64 processors under WOW64</span><span class="sxs-lookup"><span data-stu-id="bbb61-138"># Running on 2 amd64 processors under WOW64</span></span><br /><br /> <span data-ttu-id="bbb61-139"># Memory: 58% in use.</span><span class="sxs-lookup"><span data-stu-id="bbb61-139"># Memory: 58% in use.</span></span> <span data-ttu-id="bbb61-140">Physical: 845M/2044M  Paging: 2404M/4095M (avail/total)</span><span class="sxs-lookup"><span data-stu-id="bbb61-140">Physical: 845M/2044M  Paging: 2404M/4095M (avail/total)</span></span>|  
|<span data-ttu-id="bbb61-141">Ruta de acceso y versión de la biblioteca de vínculos dinámicos (DLL)</span><span class="sxs-lookup"><span data-stu-id="bbb61-141">Dynamic-link library (DLL) path and version</span></span>|<span data-ttu-id="bbb61-142">Ruta de acceso y número de versión de cada DLL que el sistema carga durante el procesamiento de un paquete.</span><span class="sxs-lookup"><span data-stu-id="bbb61-142">Path and version number of each DLL that the system loads during the processing of a package.</span></span>|<span data-ttu-id="bbb61-143"># Loaded Module: c:\bb\Sql\DTS\src\bin\debug\i386\DTExec.exe (10.0.1069.5)</span><span class="sxs-lookup"><span data-stu-id="bbb61-143"># Loaded Module: c:\bb\Sql\DTS\src\bin\debug\i386\DTExec.exe (10.0.1069.5)</span></span><br /><br /> <span data-ttu-id="bbb61-144"># Loaded Module: C:\Windows\SysWOW64\ntdll.dll (6.0.6000.16386)</span><span class="sxs-lookup"><span data-stu-id="bbb61-144"># Loaded Module: C:\Windows\SysWOW64\ntdll.dll (6.0.6000.16386)</span></span><br /><br /> <span data-ttu-id="bbb61-145"># Loaded Module: C:\Windows\syswow64\kernel32.dll (6.0.6000.16386)</span><span class="sxs-lookup"><span data-stu-id="bbb61-145"># Loaded Module: C:\Windows\syswow64\kernel32.dll (6.0.6000.16386)</span></span>|  
|<span data-ttu-id="bbb61-146">Mensajes recientes</span><span class="sxs-lookup"><span data-stu-id="bbb61-146">Recent messages</span></span>|<span data-ttu-id="bbb61-147">Mensajes recientes emitidos por el sistema.</span><span class="sxs-lookup"><span data-stu-id="bbb61-147">Recent messages issued by the system.</span></span> <span data-ttu-id="bbb61-148">Incluye la fecha y hora, el tipo, la descripción y el identificador de subproceso de cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="bbb61-148">Includes the time, type, description, and thread ID of each message.</span></span>|<span data-ttu-id="bbb61-149">[M:1]   Ring buffer entry:              (\*pRecord)</span><span class="sxs-lookup"><span data-stu-id="bbb61-149">[M:1]   Ring buffer entry:              (\*pRecord)</span></span><br /><br /> <span data-ttu-id="bbb61-150">[D:2]      <<\<CRingBufferLogging::RingBufferLoggingRecord>>> ( \@ 0282F1A8 )</span><span class="sxs-lookup"><span data-stu-id="bbb61-150">[D:2]      <<\<CRingBufferLogging::RingBufferLoggingRecord>>> ( \@ 0282F1A8 )</span></span><br /><br /> <span data-ttu-id="bbb61-151">[E:3]         Time Stamp: 2007-09-13 13:50:32.786      (szTimeStamp)</span><span class="sxs-lookup"><span data-stu-id="bbb61-151">[E:3]         Time Stamp: 2007-09-13 13:50:32.786      (szTimeStamp)</span></span><br /><br /> <span data-ttu-id="bbb61-152">[E:3]         Thread ID: 2368           (ThreadID)</span><span class="sxs-lookup"><span data-stu-id="bbb61-152">[E:3]         Thread ID: 2368           (ThreadID)</span></span><br /><br /> <span data-ttu-id="bbb61-153">[E:3]         Event Name: OnError                        (EventName)</span><span class="sxs-lookup"><span data-stu-id="bbb61-153">[E:3]         Event Name: OnError                        (EventName)</span></span><br /><br /> <span data-ttu-id="bbb61-154">[E:3]         Source Name:                (SourceName)</span><span class="sxs-lookup"><span data-stu-id="bbb61-154">[E:3]         Source Name:                (SourceName)</span></span><br /><br /> <span data-ttu-id="bbb61-155">[E:3]         Source ID:                        (SourceID)</span><span class="sxs-lookup"><span data-stu-id="bbb61-155">[E:3]         Source ID:                        (SourceID)</span></span><br /><br /> <span data-ttu-id="bbb61-156">[E:3]         Execution ID:                 (ExecutionGUID)</span><span class="sxs-lookup"><span data-stu-id="bbb61-156">[E:3]         Execution ID:                 (ExecutionGUID)</span></span><br /><br /> <span data-ttu-id="bbb61-157">[E:3]         Data Code: -1073446879              (DataCode)</span><span class="sxs-lookup"><span data-stu-id="bbb61-157">[E:3]         Data Code: -1073446879              (DataCode)</span></span><br /><br /> <span data-ttu-id="bbb61-158">[E:3]         Description: Falta el componente, no está registrado, no puede actualizarse o faltan interfaces necesarias.</span><span class="sxs-lookup"><span data-stu-id="bbb61-158">[E:3]         Description: The component is missing, not registered, not upgradeable, or missing required interfaces.</span></span> <span data-ttu-id="bbb61-159">La información de contacto para este componente es "".</span><span class="sxs-lookup"><span data-stu-id="bbb61-159">The contact information for this component is "".</span></span>|  
  
## <a name="related-content"></a><span data-ttu-id="bbb61-160">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="bbb61-160">Related Content</span></span>  
 [<span data-ttu-id="bbb61-161">Ejecutar paquete (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="bbb61-161">Execute Package Dialog Box</span></span>](../execute-package-dialog-box.md)  
  
  