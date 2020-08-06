---
title: Utilidad RS.exe (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- automatic report server tasks
- rs utility
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], automating tasks
- command prompt utilities [SQL Server], rs
- scripts [Reporting Services], command prompt
- deploying reports [Reporting Services]
ms.assetid: bd6f958f-cce6-4e79-8a0f-9475da2919ce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bcf21a1bf2453d2bd1f0644e31ca46f3f94e6884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747954"
---
# <a name="rsexe-utility-ssrs"></a><span data-ttu-id="be316-102">Utilidad RS.exe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="be316-102">RS.exe Utility (SSRS)</span></span>
  <span data-ttu-id="be316-103">La utilidad rs.exe procesa el script que proporcione en un archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="be316-103">The rs.exe utility processes script that you provide in an input file.</span></span> <span data-ttu-id="be316-104">Use esta utilidad para automatizar las tareas de implementación y administración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="be316-104">Use this utility to automate report server deployment and administration tasks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be316-105">A partir de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], la utilidad **rs** se admite con los servidores de informes configurados para el modo integrado de SharePoint, así como para los servidores configurados en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="be316-105">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], the **rs** utility is supported against report servers that are configured for SharePoint integrated mode as well as servers configured in native mode.</span></span> <span data-ttu-id="be316-106">Las versiones anteriores solo eran compatibles con las configuraciones del modo nativo.</span><span class="sxs-lookup"><span data-stu-id="be316-106">Previous versions only supported native mode configurations.</span></span>  
  
 <span data-ttu-id="be316-107">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="be316-107">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="be316-108">Ubicación del archivo</span><span class="sxs-lookup"><span data-stu-id="be316-108">File Location</span></span>](#bkmk_filelocation)  
  
-   [<span data-ttu-id="be316-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="be316-109">Arguments</span></span>](#bkmk_arguments)  
  
-   [<span data-ttu-id="be316-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="be316-110">Permissions</span></span>](#bkmk_permissions)  
  
-   [<span data-ttu-id="be316-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="be316-111">Examples</span></span>](#bkmk_examples)  
  
## <a name="syntax"></a><span data-ttu-id="be316-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be316-112">Syntax</span></span>  
  
```  
  
      rs {-?}  
{-i input_file=}  
{-s serverURL}  
{-u username}  
{-p password}  
{-e endpoint}  
{-l time_out}  
{-b batchmode}  
{-v globalvars=}  
{-t trace}  
```  
  
##  <a name="file-location"></a><a name="bkmk_filelocation"></a> <span data-ttu-id="be316-113">Ubicación del archivo</span><span class="sxs-lookup"><span data-stu-id="be316-113">File Location</span></span>  
 <span data-ttu-id="be316-114">**RS.exe** se encuentra en **\Archivos de programa\Microsoft SQL Server\110\Tools\Binn**.</span><span class="sxs-lookup"><span data-stu-id="be316-114">**RS.exe** is located at **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="be316-115">Puede ejecutar la utilidad desde cualquier carpeta del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="be316-115">You can run the utility from any folder on your file system.</span></span>  
  
##  <a name="arguments"></a><a name="bkmk_arguments"></a> <span data-ttu-id="be316-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="be316-116">Arguments</span></span>  
 <span data-ttu-id="be316-117">**-?**</span><span class="sxs-lookup"><span data-stu-id="be316-117">**-?**</span></span>  
 <span data-ttu-id="be316-118">(Opcional) Muestra la sintaxis de los argumentos de **rs** .</span><span class="sxs-lookup"><span data-stu-id="be316-118">(Optional) Displays the syntax of **rs** arguments.</span></span>  
  
 <span data-ttu-id="be316-119">`-i`*input_file*</span><span class="sxs-lookup"><span data-stu-id="be316-119">`-i` *input_file*</span></span>  
 <span data-ttu-id="be316-120">(Obligatorio) Especifica el archivo .rss que debe ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="be316-120">(Required) Specifies the .rss file to execute.</span></span> <span data-ttu-id="be316-121">Este valor puede ser una ruta de acceso relativa o una ruta de acceso completa al archivo .rss.</span><span class="sxs-lookup"><span data-stu-id="be316-121">This value can be a relative or fully qualified path to the .rss file.</span></span>  
  
 <span data-ttu-id="be316-122">`-s`*ServerURL*</span><span class="sxs-lookup"><span data-stu-id="be316-122">`-s` *serverURL*</span></span>  
 <span data-ttu-id="be316-123">(Obligatorio) Especifica el nombre del servidor web y el nombre del directorio virtual del servidor de informes donde debe ejecutarse el archivo.</span><span class="sxs-lookup"><span data-stu-id="be316-123">(Required) Specifies the Web server name and report server virtual directory name to execute the file against.</span></span> <span data-ttu-id="be316-124">Un ejemplo de una dirección URL de un servidor de informes es `http://examplewebserver/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="be316-124">An example of a report server URL is `http://examplewebserver/reportserver`.</span></span> <span data-ttu-id="be316-125">El prefijo http:// o https:// al principio del nombre del servidor es opcional.</span><span class="sxs-lookup"><span data-stu-id="be316-125">The prefix http:// or https:// at the beginning of the server name is optional.</span></span> <span data-ttu-id="be316-126">Si se omite el prefijo, el host de script del servidor de informes intentará usar primero https y, después, http si https no funciona.</span><span class="sxs-lookup"><span data-stu-id="be316-126">If you omit the prefix, the report server script host tries to use https first, and then uses http if https does not work.</span></span>  
  
 <span data-ttu-id="be316-127">`-u`[*dominio* \\ ] *nombre de usuario*</span><span class="sxs-lookup"><span data-stu-id="be316-127">`-u` [*domain*\\]*username*</span></span>  
 <span data-ttu-id="be316-128">(Opcional) Especifica una cuenta de usuario que se utiliza para conectarse al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="be316-128">(Optional) Specifies a user account used to connect to the report server.</span></span> <span data-ttu-id="be316-129">Si se omiten `-u` y `-p`, se usa la cuenta de usuario actual de Windows.</span><span class="sxs-lookup"><span data-stu-id="be316-129">If `-u` and `-p` are omitted, the current Windows user account is used.</span></span>  
  
 <span data-ttu-id="be316-130">`-p`*contraseña* de</span><span class="sxs-lookup"><span data-stu-id="be316-130">`-p` *password*</span></span>  
 <span data-ttu-id="be316-131">(Obligatorio si se especifica `-u`) Especifica la contraseña que debe utilizarse con el argumento `-u`.</span><span class="sxs-lookup"><span data-stu-id="be316-131">(Required if `-u` is specified) Specifies the password to use with the `-u` argument.</span></span> <span data-ttu-id="be316-132">Este valor distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="be316-132">This value is case-sensitive.</span></span>  
  
 `-e`  
 <span data-ttu-id="be316-133">(Opcional) Especifica el extremo SOAP en el que debe ejecutarse el script.</span><span class="sxs-lookup"><span data-stu-id="be316-133">(Optional) Specifies the SOAP endpoint against which the script should run.</span></span> <span data-ttu-id="be316-134">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="be316-134">Valid values are the following:</span></span>  
  
-   <span data-ttu-id="be316-135">Mgmt2010</span><span class="sxs-lookup"><span data-stu-id="be316-135">Mgmt2010</span></span>  
  
-   <span data-ttu-id="be316-136">Mgmt2006</span><span class="sxs-lookup"><span data-stu-id="be316-136">Mgmt2006</span></span>  
  
-   <span data-ttu-id="be316-137">Mgmt2005</span><span class="sxs-lookup"><span data-stu-id="be316-137">Mgmt2005</span></span>  
  
-   <span data-ttu-id="be316-138">Exec2005</span><span class="sxs-lookup"><span data-stu-id="be316-138">Exec2005</span></span>  
  
 <span data-ttu-id="be316-139">Si no se especifica ningún valor, se utilizará el extremo Mgmt2005.</span><span class="sxs-lookup"><span data-stu-id="be316-139">If a value is not specified, the Mgmt2005 endpoint is used.</span></span> <span data-ttu-id="be316-140">Para obtener más información acerca de los extremos SOAP, vea [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="be316-140">For more information about the SOAP endpoints, see [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span></span>  
  
 <span data-ttu-id="be316-141">`-l`*time_out*</span><span class="sxs-lookup"><span data-stu-id="be316-141">`-l` *time_out*</span></span>  
 <span data-ttu-id="be316-142">Opta Especifica el número de segundos que transcurren antes de que se agote el tiempo de espera de la conexión al servidor. El valor predeterminado es 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="be316-142">(Optional) Specifies the number of seconds that elapse before the connection to the server times out. The default is 60 seconds.</span></span> <span data-ttu-id="be316-143">Si no se especifica ningún valor de tiempo de espera, se utiliza el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="be316-143">If you do not specify a time-out value, the default is used.</span></span> <span data-ttu-id="be316-144">El valor `0` indica que nunca se agota el tiempo de espera de la conexión.</span><span class="sxs-lookup"><span data-stu-id="be316-144">A value of `0` specifies that the connection never times out.</span></span>  
  
 <span data-ttu-id="be316-145">**-b**</span><span class="sxs-lookup"><span data-stu-id="be316-145">**-b**</span></span>  
 <span data-ttu-id="be316-146">(Opcional) Especifica que los comandos del archivo de script se ejecutan en un lote.</span><span class="sxs-lookup"><span data-stu-id="be316-146">(Optional) Specifies that the commands in the script file run in a batch.</span></span> <span data-ttu-id="be316-147">Si se produce un error en alguno de los comandos, se revierte el lote.</span><span class="sxs-lookup"><span data-stu-id="be316-147">If any commands fail, the batch is rolled back.</span></span> <span data-ttu-id="be316-148">Algunos comandos no se pueden ejecutar por lotes y se ejecutan de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="be316-148">Some commands cannot be batched, and those run as usual.</span></span> <span data-ttu-id="be316-149">Solo si se producen excepciones que no se controlan dentro del script tiene lugar una operación de reversión.</span><span class="sxs-lookup"><span data-stu-id="be316-149">Only exceptions that are thrown and are not handled within the script result in a rollback.</span></span> <span data-ttu-id="be316-150">Si el script controla una excepción y vuelve con normalidad desde `Main`, se confirma el lote.</span><span class="sxs-lookup"><span data-stu-id="be316-150">If the script handles an exception and returns normally from `Main`, the batch is committed.</span></span> <span data-ttu-id="be316-151">Si omite este parámetro, los comandos se ejecutan sin crear un lote.</span><span class="sxs-lookup"><span data-stu-id="be316-151">If you omit this parameter, the commands run without creating a batch.</span></span> <span data-ttu-id="be316-152">Para obtener más información, consulte [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span><span class="sxs-lookup"><span data-stu-id="be316-152">For more information, see [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span></span>  
  
 <span data-ttu-id="be316-153">`-v` *globalvar*</span><span class="sxs-lookup"><span data-stu-id="be316-153">`-v` *globalvar*</span></span>  
 <span data-ttu-id="be316-154">(Opcional) Especifica las variables globales que se usan en el script.</span><span class="sxs-lookup"><span data-stu-id="be316-154">(Optional) Specifies global variables that are used in the script.</span></span> <span data-ttu-id="be316-155">Si el script utiliza variables globales, debe especificar este argumento.</span><span class="sxs-lookup"><span data-stu-id="be316-155">If the script uses global variables, you must specify this argument.</span></span> <span data-ttu-id="be316-156">El valor que especifique debe ser válido para la variable global definida en el archivo .rss.</span><span class="sxs-lookup"><span data-stu-id="be316-156">The value that you specify must be valid for global variable defined in the .rss file.</span></span> <span data-ttu-id="be316-157">Debe especificar una variable global para cada argumento **-v** .</span><span class="sxs-lookup"><span data-stu-id="be316-157">You must specify one global variable for each **-v** argument.</span></span>  
  
 <span data-ttu-id="be316-158">El argumento `-v` se especifica en la línea de comandos y se usa para establecer el valor de una variable global que se define en el script en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="be316-158">The `-v` argument is specified on the command line and is used to set the value for a global variable that is defined in your script at run time.</span></span> <span data-ttu-id="be316-159">Por ejemplo, si el script contiene una variable con nombre *parentFolder*, puede especificar un nombre para dicha carpeta en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="be316-159">For example, if your script contains a variable named *parentFolder*, you can specify a name for that folder on the command line:</span></span>  
  
 `rs.exe -i myScriptFile.rss -s http://myServer/reportserver -v parentFolder="Financial Reports"`  
  
 <span data-ttu-id="be316-160">Se crean variables globales con los nombres indicados y se establecen en los valores proporcionados.</span><span class="sxs-lookup"><span data-stu-id="be316-160">Global variables are created with the names given and set to the values supplied.</span></span> <span data-ttu-id="be316-161">Por ejemplo, **-v a =**" `1` " **-v b =**" `2` " da como resultado una variable denominada `a` con un valor de " `1` " y una variable **b** con un valor de " `2` ".</span><span class="sxs-lookup"><span data-stu-id="be316-161">For example, **-v a=**"`1`" **-v b=**"`2`" results in a variable named `a` with a value of"`1`" and a variable **b** with a value of "`2`".</span></span>  
  
 <span data-ttu-id="be316-162">Las variables globales están disponibles para todas las funciones del script.</span><span class="sxs-lookup"><span data-stu-id="be316-162">Global variables are available to any function in the script.</span></span> <span data-ttu-id="be316-163">Una barra diagonal inversa y Comillas (\*\* \\ "\*\*) se interpretan como comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="be316-163">A backslash and quotation mark (**\\"**) is interpreted as a double quotation mark.</span></span> <span data-ttu-id="be316-164">Las comillas solo son necesarias si la cadena contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="be316-164">The quotation marks are required only if the string contains a space.</span></span> <span data-ttu-id="be316-165">Los nombres de variable deben ser válidos para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ; deben comenzar por un carácter alfabético o de subrayado y contener caracteres alfabéticos, dígitos o caracteres de subrayado.</span><span class="sxs-lookup"><span data-stu-id="be316-165">Variable names must be valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]; they must start with alphabetical character or underscore and contain alphabetical characters, digits, or underscores.</span></span> <span data-ttu-id="be316-166">No se pueden utilizar palabras reservadas como nombres de variables.</span><span class="sxs-lookup"><span data-stu-id="be316-166">Reserved words cannot be used as variable names.</span></span> <span data-ttu-id="be316-167">Para más información sobre las variables globales, vea [Colecciones integradas en expresiones &#40;Generador de informes y SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="be316-167">For more information about using global variables, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
 <span data-ttu-id="be316-168">**-t**</span><span class="sxs-lookup"><span data-stu-id="be316-168">**-t**</span></span>  
 <span data-ttu-id="be316-169">(Opcional) Muestra mensajes de error en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="be316-169">(Optional) Outputs error messages to the trace log.</span></span> <span data-ttu-id="be316-170">Este argumento no toma ningún valor.</span><span class="sxs-lookup"><span data-stu-id="be316-170">This argument does not take a value.</span></span> <span data-ttu-id="be316-171">Para obtener más información, consulte [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="be316-171">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
##  <a name="permissions"></a><a name="bkmk_permissions"></a> <span data-ttu-id="be316-172">Permisos</span><span class="sxs-lookup"><span data-stu-id="be316-172">Permissions</span></span>  
 <span data-ttu-id="be316-173">Para ejecutar la herramienta, debe tener permiso para conectarse a la instancia del servidor de informes en la que se está ejecutando el script.</span><span class="sxs-lookup"><span data-stu-id="be316-173">To run the tool, you must have permission to connect to the report server instance you are running the script against.</span></span> <span data-ttu-id="be316-174">Puede ejecutar scripts para realizar cambios en el equipo local o en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="be316-174">You can run scripts to make changes to the local computer or a remote computer.</span></span> <span data-ttu-id="be316-175">Para realizar cambios en un servidor de informes instalado en un equipo remoto, especifique el equipo remoto en el argumento `-s`.</span><span class="sxs-lookup"><span data-stu-id="be316-175">To make changes to a report server installed on a remote computer, specify the remote computer in the `-s` argument.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="be316-176">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="be316-176">Examples</span></span>  
 <span data-ttu-id="be316-177">En el ejemplo siguiente se muestra cómo especificar el archivo de script que contiene el script de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET y los métodos del servicio Web que se desea ejecutar.</span><span class="sxs-lookup"><span data-stu-id="be316-177">The following example illustrates how to specify the script file that contains [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET script and Web service methods that you want to execute.</span></span>  
  
```  
rs -i c:\scriptfiles\script_copycontent.rss -s http://localhost/reportserver  
```  
  
 <span data-ttu-id="be316-178">Para obtener un ejemplo detallado, vea [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="be316-178">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="be316-179">Para ver otros ejemplos, vea [Ejecutar un archivo de script de Reporting Services](run-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="be316-179">For additional examples, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be316-180">Observaciones</span><span class="sxs-lookup"><span data-stu-id="be316-180">Remarks</span></span>  
 <span data-ttu-id="be316-181">Puede definir scripts para establecer propiedades del sistema, publicar informes, etc.</span><span class="sxs-lookup"><span data-stu-id="be316-181">You can define scripts to set system properties, publish reports, and so forth.</span></span> <span data-ttu-id="be316-182">Los scripts que crea pueden incluir cualquier método de la API [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be316-182">The scripts that you create can include any methods of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="be316-183">Para obtener más información sobre los métodos y las propiedades disponibles, vea [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="be316-183">For more information about the methods and properties available to you, see [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span></span>  
  
 <span data-ttu-id="be316-184">Es necesario escribir el script en código de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET y guardarlo en un archivo de texto Unicode o UTF-8 con la extensión de nombre de archivo .rss.</span><span class="sxs-lookup"><span data-stu-id="be316-184">The script must be written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET code, and stored in a Unicode or UTF-8 text file with an .rss file name extension.</span></span> <span data-ttu-id="be316-185">No se pueden depurar scripts mediante la utilidad **rs** .</span><span class="sxs-lookup"><span data-stu-id="be316-185">You cannot debug scripts with the **rs** utility.</span></span> <span data-ttu-id="be316-186">Para depurar un script, ejecute el código dentro de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be316-186">To debug a script, run the code within [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="be316-187">Para obtener un ejemplo detallado, vea [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="be316-187">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be316-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be316-188">See Also</span></span>  
 <span data-ttu-id="be316-189">[Ejecutar un archivo de script de Reporting Services](run-a-reporting-services-script-file.md) </span><span class="sxs-lookup"><span data-stu-id="be316-189">[Run a Reporting Services Script File](run-a-reporting-services-script-file.md) </span></span>  
 <span data-ttu-id="be316-190">[Crear script de tareas administrativas y de implementación](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="be316-190">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="be316-191">[Script con la utilidad rs.exe y el servicio Web](script-with-the-rs-exe-utility-and-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="be316-191">[Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md) </span></span>  
 [<span data-ttu-id="be316-192">Utilidades del símbolo del sistema del servidor de informes &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="be316-192">Report Server Command Prompt Utilities &#40;SSRS&#41;</span></span>](report-server-command-prompt-utilities-ssrs.md)  
  
  
