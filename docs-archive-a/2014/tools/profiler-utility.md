---
title: Utilidad Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server], profiler90 utility
- profiler90 utility
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: e91c30a9-0d29-4f84-bcb8-e8fb62afadda
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8df3e8557bb52839d17291bae0c5ba507d0a671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743763"
---
# <a name="profiler-utility"></a><span data-ttu-id="9198c-102">Analizador (utilidad)</span><span class="sxs-lookup"><span data-stu-id="9198c-102">Profiler Utility</span></span>
  <span data-ttu-id="9198c-103">La utilidad **profiler** inicia la herramienta [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9198c-103">The **profiler** utility launches the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] tool.</span></span> <span data-ttu-id="9198c-104">Los argumentos opcionales que se enumeran más adelante en este tema permiten controlar cómo se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9198c-104">The optional arguments listed later in this topic allow you to control how the application starts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9198c-105">La utilidad **profiler** no está pensada para la creación de scripts en seguimientos.</span><span class="sxs-lookup"><span data-stu-id="9198c-105">The **profiler** utility is not intended for scripting traces.</span></span> <span data-ttu-id="9198c-106">Para más información, consulte [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="9198c-106">For more information, see [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9198c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9198c-107">Syntax</span></span>  
  
```  
  
      profiler  
          [ /? ] |  
[  
{  
{ /U login_id [ /P password ] }  
| /E  
}  
{[ /S sql_server_name ] | [ /A analysis_services_server_name ] }  
[ /D database ]  
[ /T "template_name" ]  
[ /B { "trace_table_name" } ]  
{ [/F "filename" ] | [ /O "filename" ] }  
[ /L locale_ID ]  
[ /M "MM-DD-YY hh:mm:ss" ]  
[ /R ]  
[ /Z file_size ]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9198c-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9198c-108">Arguments</span></span>  
 <span data-ttu-id="9198c-109">**/?**</span><span class="sxs-lookup"><span data-stu-id="9198c-109">**/?**</span></span>  
 <span data-ttu-id="9198c-110">Muestra el resumen de sintaxis de los argumentos de **profiler** .</span><span class="sxs-lookup"><span data-stu-id="9198c-110">Displays the syntax summary of **profiler** arguments.</span></span>  
  
 <span data-ttu-id="9198c-111">**/U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="9198c-111">**/U** *login_id*</span></span>  
 <span data-ttu-id="9198c-112">Es el Id. de inicio de sesión para la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9198c-112">Is the user login ID for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="9198c-113">Los Id. de inicio de sesión distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9198c-113">Login IDs are case sensitive.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]<span data-ttu-id="9198c-114">.</span><span class="sxs-lookup"><span data-stu-id="9198c-114">.</span></span>  
  
 <span data-ttu-id="9198c-115">**/P** *password*</span><span class="sxs-lookup"><span data-stu-id="9198c-115">**/P** *password*</span></span>  
 <span data-ttu-id="9198c-116">Especifica una contraseña especificada por el usuario para la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9198c-116">Specifies a user-specified password for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="9198c-117">**/E**</span><span class="sxs-lookup"><span data-stu-id="9198c-117">**/E**</span></span>  
 <span data-ttu-id="9198c-118">Especifica la conexión con la autenticación de Windows con las credenciales actuales del usuario.</span><span class="sxs-lookup"><span data-stu-id="9198c-118">Specifies connecting with Windows Authentication with the current user's credentials.</span></span>  
  
 <span data-ttu-id="9198c-119">**/S**  *sql_server_name*</span><span class="sxs-lookup"><span data-stu-id="9198c-119">**/S**  *sql_server_name*</span></span>  
 <span data-ttu-id="9198c-120">Especifica una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9198c-120">Specifies an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9198c-121">Profiler se conectará automáticamente con el servidor especificado usando la información de autenticación que se especifica en los modificadores **/U** y **/P** o en el modificador **/E** .</span><span class="sxs-lookup"><span data-stu-id="9198c-121">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="9198c-122">Para conectar una instancia con nombre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *sql_server_name*\\*instance_name*.</span><span class="sxs-lookup"><span data-stu-id="9198c-122">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *sql_server_name*\\*instance_name*.</span></span>  
  
 <span data-ttu-id="9198c-123">**/A**  *analysis_services_server_name*</span><span class="sxs-lookup"><span data-stu-id="9198c-123">**/A**  *analysis_services_server_name*</span></span>  
 <span data-ttu-id="9198c-124">Especifica una instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9198c-124">Specifies an instance of Analysis Services.</span></span> <span data-ttu-id="9198c-125">Profiler se conectará automáticamente con el servidor especificado usando la información de autenticación que se especifica en los modificadores **/U** y **/P** o en el modificador **/E** .</span><span class="sxs-lookup"><span data-stu-id="9198c-125">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="9198c-126">Para conectar con una instancia con nombre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/A** *analysis_services_server_name\instance_name*.</span><span class="sxs-lookup"><span data-stu-id="9198c-126">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] use **/A** *analysis_services_server_name\instance_name*.</span></span>  
  
 <span data-ttu-id="9198c-127">**/D** *database*</span><span class="sxs-lookup"><span data-stu-id="9198c-127">**/D** *database*</span></span>  
 <span data-ttu-id="9198c-128">Especifica el nombre de la base de datos que se utilizará con la conexión.</span><span class="sxs-lookup"><span data-stu-id="9198c-128">Specifies the name of the database to be used with the connection.</span></span> <span data-ttu-id="9198c-129">Esta opción seleccionará la base de datos predeterminada para el usuario especificado si no se especifica ninguna base de datos.</span><span class="sxs-lookup"><span data-stu-id="9198c-129">This option will select the default database for the specified user if no database is specified.</span></span>  
  
 <span data-ttu-id="9198c-130">**/B "** *trace_table_name* **"**</span><span class="sxs-lookup"><span data-stu-id="9198c-130">**/B "** *trace_table_name* **"**</span></span>  
 <span data-ttu-id="9198c-131">Especifica una tabla de seguimiento que se cargará cuando se inicie Profiler.</span><span class="sxs-lookup"><span data-stu-id="9198c-131">Specifies a trace table to load when the profiler is launched.</span></span> <span data-ttu-id="9198c-132">Debe especificar la base de datos, el usuario o esquema, y la tabla.</span><span class="sxs-lookup"><span data-stu-id="9198c-132">You must specify the database, the user or schema, and the table.</span></span>  
  
 <span data-ttu-id="9198c-133">**/T"** *template_name* **"**</span><span class="sxs-lookup"><span data-stu-id="9198c-133">**/T"** *template_name* **"**</span></span>  
 <span data-ttu-id="9198c-134">Especifica la plantilla que se cargará para configurar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9198c-134">Specifies the template that will be loaded to configure the trace.</span></span> <span data-ttu-id="9198c-135">El nombre de la plantilla debe estar entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9198c-135">The template name must be in quotes.</span></span> <span data-ttu-id="9198c-136">El nombre de la plantilla debe estar en el directorio de plantillas del sistema o en el directorio de plantillas del usuario.</span><span class="sxs-lookup"><span data-stu-id="9198c-136">The template name must be in either the system template directory or the user template directory.</span></span> <span data-ttu-id="9198c-137">Si existen dos plantillas con el mismo nombre en ambos directorios, la plantilla del directorio del sistema se cargará.</span><span class="sxs-lookup"><span data-stu-id="9198c-137">If two templates with the same name exist in both directories, the template from the system directory will be loaded.</span></span> <span data-ttu-id="9198c-138">Si no existe ninguna plantilla con el nombre especificado se cargará la plantilla estándar.</span><span class="sxs-lookup"><span data-stu-id="9198c-138">If no template with the specified name exists, the standard template will be loaded.</span></span> <span data-ttu-id="9198c-139">Tenga en cuenta que la extensión de archivo para la plantilla (.tdf) no debe especificarse como parte de *template_name*.</span><span class="sxs-lookup"><span data-stu-id="9198c-139">Note that the file extension for the template (.tdf) should not be specified as part of the *template_name*.</span></span> <span data-ttu-id="9198c-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9198c-140">For example:</span></span>  
  
```  
/T "standard"  
```  
  
 <span data-ttu-id="9198c-141">**/F"** *filename* **"**</span><span class="sxs-lookup"><span data-stu-id="9198c-141">**/F"** *filename* **"**</span></span>  
 <span data-ttu-id="9198c-142">Especifica la ruta y el nombre de un archivo de seguimiento que se cargará cuando se inicie Profiler.</span><span class="sxs-lookup"><span data-stu-id="9198c-142">Specifies the path and filename of a trace file to load when profiler is launched.</span></span> <span data-ttu-id="9198c-143">Toda la ruta y el nombre de archivo debe estar entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9198c-143">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="9198c-144">Esta opción no se puede usar con **/O**.</span><span class="sxs-lookup"><span data-stu-id="9198c-144">This option cannot be used with **/O**.</span></span>  
  
 <span data-ttu-id="9198c-145">**/O "** *filename*  **"**</span><span class="sxs-lookup"><span data-stu-id="9198c-145">**/O "** *filename*  **"**</span></span>  
 <span data-ttu-id="9198c-146">Especifica la ruta y el nombre de un archivo en el que deben escribirse los resultados del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9198c-146">Specifies the path and filename of a file to which trace results should be written.</span></span> <span data-ttu-id="9198c-147">Toda la ruta y el nombre de archivo debe estar entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9198c-147">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="9198c-148">Esta opción no se puede usar con **/F.**</span><span class="sxs-lookup"><span data-stu-id="9198c-148">This option cannot be used with **/F.**</span></span>  
  
 <span data-ttu-id="9198c-149">**/L** *locale_ID*</span><span class="sxs-lookup"><span data-stu-id="9198c-149">**/L** *locale_ID*</span></span>  
 <span data-ttu-id="9198c-150">No disponible.</span><span class="sxs-lookup"><span data-stu-id="9198c-150">Not available.</span></span>  
  
 <span data-ttu-id="9198c-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span><span class="sxs-lookup"><span data-stu-id="9198c-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span></span>  
 <span data-ttu-id="9198c-152">Especifica la fecha y la hora de detención del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9198c-152">Specifies the date and time for the trace to stop.</span></span> <span data-ttu-id="9198c-153">La hora de detención debe estar entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9198c-153">The stop time must be in quotes.</span></span> <span data-ttu-id="9198c-154">Especifique la hora de detención de acuerdo con los parámetros de la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="9198c-154">Specify the stop time according to the parameters in the table below:</span></span>  
  
|<span data-ttu-id="9198c-155">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9198c-155">Parameter</span></span>|<span data-ttu-id="9198c-156">Definición</span><span class="sxs-lookup"><span data-stu-id="9198c-156">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="9198c-157">MM</span><span class="sxs-lookup"><span data-stu-id="9198c-157">MM</span></span>|<span data-ttu-id="9198c-158">Mes de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="9198c-158">Two-digit month</span></span>|  
|<span data-ttu-id="9198c-159">DD</span><span class="sxs-lookup"><span data-stu-id="9198c-159">DD</span></span>|<span data-ttu-id="9198c-160">Día de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="9198c-160">Two-digit day</span></span>|  
|<span data-ttu-id="9198c-161">YY</span><span class="sxs-lookup"><span data-stu-id="9198c-161">YY</span></span>|<span data-ttu-id="9198c-162">Año de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="9198c-162">Two-digit year</span></span>|  
|<span data-ttu-id="9198c-163">hh</span><span class="sxs-lookup"><span data-stu-id="9198c-163">hh</span></span>|<span data-ttu-id="9198c-164">Hora de dos dígitos en un reloj de 24 horas</span><span class="sxs-lookup"><span data-stu-id="9198c-164">Two-digit hour on a 24-hour clock</span></span>|  
|<span data-ttu-id="9198c-165">MM</span><span class="sxs-lookup"><span data-stu-id="9198c-165">mm</span></span>|<span data-ttu-id="9198c-166">Minuto de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="9198c-166">Two-digit minute</span></span>|  
|<span data-ttu-id="9198c-167">ss</span><span class="sxs-lookup"><span data-stu-id="9198c-167">ss</span></span>|<span data-ttu-id="9198c-168">Segundo de dos dígitos</span><span class="sxs-lookup"><span data-stu-id="9198c-168">Two-digit second</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="9198c-169">El formato "MM-DD-YY hh:mm:ss" solo se puede usar si la opción **Usar la configuración regional para mostrar valores de fecha y hora** está habilitada en [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9198c-169">The "MM-DD-YY hh:mm:ss" format can only be used if the **Use regional settings to display date and time values** option is enabled in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="9198c-170">Si esta opción no está habilitada, debe utilizar  el formato de fecha y hora "YYYY-MM-DD hh:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="9198c-170">If this option is not enabled, you must use the "YYYY-MM-DD hh:mm:ss" date and time format.</span></span>  
  
 <span data-ttu-id="9198c-171">**/R**</span><span class="sxs-lookup"><span data-stu-id="9198c-171">**/R**</span></span>  
 <span data-ttu-id="9198c-172">Habilita la sustitución incremental de los archivos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9198c-172">Enables trace file rollover.</span></span>  
  
 <span data-ttu-id="9198c-173">**/Z**  *file_size*</span><span class="sxs-lookup"><span data-stu-id="9198c-173">**/Z**  *file_size*</span></span>  
 <span data-ttu-id="9198c-174">Especifica el tamaño del archivo de seguimiento en megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="9198c-174">Specifies the size of the trace file in megabytes (MB).</span></span> <span data-ttu-id="9198c-175">El tamaño predeterminado es 5 MB.</span><span class="sxs-lookup"><span data-stu-id="9198c-175">The default size is 5 MB.</span></span> <span data-ttu-id="9198c-176">Si está habilitada la sustitución incremental de archivos, todos los archivos de sustitución incremental estarán limitados al valor especificado en el argumento.</span><span class="sxs-lookup"><span data-stu-id="9198c-176">If rollover is enabled, all rollover files will be limited to the value specified in this argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9198c-177">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9198c-177">Remarks</span></span>  
 <span data-ttu-id="9198c-178">Para iniciar un seguimiento con una plantilla específica, use las opciones **/S** y **/T** juntas.</span><span class="sxs-lookup"><span data-stu-id="9198c-178">To start a trace with a specific template, use the **/S** and **/T** options together.</span></span> <span data-ttu-id="9198c-179">Por ejemplo, para iniciar un seguimiento mediante la plantilla Standard en MyServer\MyInstance, escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="9198c-179">For example, to start a trace using the Standard template on MyServer\MyInstance, enter the following at the command prompt:</span></span>  
  
```  
profiler /S MyServer\MyInstance /T "Standard"  
```  
  
## <a name="see-also"></a><span data-ttu-id="9198c-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9198c-180">See Also</span></span>  
 [<span data-ttu-id="9198c-181">Referencia de la utilidad del símbolo del sistema &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="9198c-181">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](command-prompt-utility-reference-database-engine.md)  
  
  
