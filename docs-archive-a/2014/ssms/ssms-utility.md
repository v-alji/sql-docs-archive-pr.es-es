---
title: Ssms (Utilidad) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], opening
- command prompt utilities [SQL Server], sqlwb
- sqlwb utility
- Management Studio command line
- opening SQL Server Management Studio
ms.assetid: aafda520-9e2a-4e1e-b936-1b165f1684e8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0cfc9469e49e6ce3839d02a61477b8957fbc13e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676807"
---
# <a name="ssms-utility"></a><span data-ttu-id="61056-102">Ssms (Utilidad)</span><span class="sxs-lookup"><span data-stu-id="61056-102">Ssms Utility</span></span>
  <span data-ttu-id="61056-103">La utilidad **Ssms**abre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61056-103">The **Ssms**utility opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="61056-104">Si se especifica, **Ssms** también establece una conexión con un servidor y abre consultas, scripts, archivos, proyectos y soluciones.</span><span class="sxs-lookup"><span data-stu-id="61056-104">If specified, **Ssms** also establishes a connection to a server, and opens queries, scripts, files, projects, and solutions.</span></span>  
  
 <span data-ttu-id="61056-105">Puede especificar archivos que contienen consultas, proyectos o soluciones.</span><span class="sxs-lookup"><span data-stu-id="61056-105">You can specify files that contain queries, projects, or solutions.</span></span> <span data-ttu-id="61056-106">Los archivos que contienen consultas se conectan automáticamente con un servidor si se proporciona información de conexión y el tipo de archivo está asociado con ese tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="61056-106">Files that contain queries are automatically connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="61056-107">Por ejemplo, los archivos .sql abrirán una ventana del Editor de consultas de SQL en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], y los archivos .mdx abrirán una ventana del Editor de consultas MDX en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61056-107">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="61056-108">Las**Soluciones y proyectos de SQL Server** se abrirán en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61056-108">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61056-109">La utilidad **Ssms** no ejecuta consultas.</span><span class="sxs-lookup"><span data-stu-id="61056-109">The **Ssms** utility does not run queries.</span></span> <span data-ttu-id="61056-110">Para ejecutar consultas desde la línea de comandos, utilice la utilidad **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="61056-110">To run queries from the command line, use the **sqlcmd** utility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61056-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61056-111">Syntax</span></span>  
  
```  
  
      Ssms  
    [scriptfile] [projectfile] [solutionfile]  
    [-Sservername] [-ddatabasename] [-Uusername] [-Ppassword]   
    [-E] [-nosplash] [-log[filename]?] [-?]  
```  
  
## <a name="arguments"></a><span data-ttu-id="61056-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="61056-112">Arguments</span></span>  
 <span data-ttu-id="61056-113">*scriptfile*</span><span class="sxs-lookup"><span data-stu-id="61056-113">*scriptfile*</span></span>  
 <span data-ttu-id="61056-114">Especifica uno o más archivos de script para abrirlos.</span><span class="sxs-lookup"><span data-stu-id="61056-114">Specifies one or more script files to open.</span></span> <span data-ttu-id="61056-115">El parámetro debe contener la ruta completa a los archivos.</span><span class="sxs-lookup"><span data-stu-id="61056-115">The parameter must contain the full path to the files.</span></span>  
  
 <span data-ttu-id="61056-116">*projectfile*</span><span class="sxs-lookup"><span data-stu-id="61056-116">*projectfile*</span></span>  
 <span data-ttu-id="61056-117">Especifica un proyecto de script para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="61056-117">Specifies a script project to open.</span></span> <span data-ttu-id="61056-118">El parámetro debe contener la ruta completa al archivo del proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="61056-118">The parameter must contain the full path to the script project file.</span></span>  
  
 <span data-ttu-id="61056-119">*solutionfile*</span><span class="sxs-lookup"><span data-stu-id="61056-119">*solutionfile*</span></span>  
 <span data-ttu-id="61056-120">Especifica una solución para abrirla.</span><span class="sxs-lookup"><span data-stu-id="61056-120">Specifies a solution to open.</span></span> <span data-ttu-id="61056-121">El parámetro debe contener la ruta completa al archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="61056-121">The parameter must contain the full path to the solution file.</span></span>  
  
 <span data-ttu-id="61056-122">[**-S nombre de** _servidor_]</span><span class="sxs-lookup"><span data-stu-id="61056-122">[**-S** _servername_]</span></span>  
 <span data-ttu-id="61056-123">Nombre de servidor</span><span class="sxs-lookup"><span data-stu-id="61056-123">Server name</span></span>  
  
 <span data-ttu-id="61056-124">[**-d** _DatabaseName_]</span><span class="sxs-lookup"><span data-stu-id="61056-124">[**-d** _databasename_]</span></span>  
 <span data-ttu-id="61056-125">Nombre de la base de datos</span><span class="sxs-lookup"><span data-stu-id="61056-125">Database name</span></span>  
  
 <span data-ttu-id="61056-126">[**-U** _username_]</span><span class="sxs-lookup"><span data-stu-id="61056-126">[**-U** _username_]</span></span>  
 <span data-ttu-id="61056-127">Nombre de usuario cuando se conecta con la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61056-127">User name when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="61056-128">[**-P** _contraseña_]</span><span class="sxs-lookup"><span data-stu-id="61056-128">[**-P** _password_]</span></span>  
 <span data-ttu-id="61056-129">Contraseña cuando se conecta con la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61056-129">Password when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="61056-130">[**-E**]</span><span class="sxs-lookup"><span data-stu-id="61056-130">[**-E**]</span></span>  
 <span data-ttu-id="61056-131">Conectar con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="61056-131">Connect using Windows Authentication</span></span>  
  
 <span data-ttu-id="61056-132">[**-NoSplash**]</span><span class="sxs-lookup"><span data-stu-id="61056-132">[**-nosplash**]</span></span>  
 <span data-ttu-id="61056-133">Impide que [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] muestre el gráfico de la pantalla de presentación mientras se abre.</span><span class="sxs-lookup"><span data-stu-id="61056-133">Prevents [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from displaying the splash screen graphic while opening.</span></span> <span data-ttu-id="61056-134">Utilice esta opción cuando se conecte con un equipo que ejecute [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] mediante Terminal Services en una conexión con ancho de banda limitado.</span><span class="sxs-lookup"><span data-stu-id="61056-134">Use this option when connecting to the computer running [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by means of Terminal Services over a connection with a limited bandwidth.</span></span> <span data-ttu-id="61056-135">Este argumento no distingue entre mayúsculas y minúsculas y puede aparecer antes o después de otros argumentos.</span><span class="sxs-lookup"><span data-stu-id="61056-135">This argument is not case-sensitive and may appear before or after other arguments</span></span>  
  
 <span data-ttu-id="61056-136">[**-log**_[nombrearchivo]?_]</span><span class="sxs-lookup"><span data-stu-id="61056-136">[**-log**_[filename]?_]</span></span>  
 <span data-ttu-id="61056-137">Registra la actividad de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] en el archivo especificado para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="61056-137">Logs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] activity to the specified file for troubleshooting</span></span>  
  
 <span data-ttu-id="61056-138">[**-?**]</span><span class="sxs-lookup"><span data-stu-id="61056-138">[**-?**]</span></span>  
 <span data-ttu-id="61056-139">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="61056-139">Displays command line help</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61056-140">Observaciones</span><span class="sxs-lookup"><span data-stu-id="61056-140">Remarks</span></span>  
 <span data-ttu-id="61056-141">Todos los modificadores son opcionales y están separados por un espacio, excepto los archivos, que están separados por comas.</span><span class="sxs-lookup"><span data-stu-id="61056-141">All of the switches are optional and separated by a space except files which are separated by commas.</span></span> <span data-ttu-id="61056-142">Si no especifica modificadores, **Ssms** abre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] según se especifica en la configuración de **Opciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="61056-142">If you do not specify any switches, **Ssms** opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as specified in the **Options** settings on the **Tools** menu.</span></span> <span data-ttu-id="61056-143">Por ejemplo, si en la página **Entorno/General** , la opción **Al iniciar** especifica **Abrir nueva ventana de consulta**, **Ssms** se abrirá con un Editor de consultas en blanco.</span><span class="sxs-lookup"><span data-stu-id="61056-143">For example, if the **Environment/General** page **At startup** option specifies **Open new query window**, **Ssms** will open with a blank Query Editor.</span></span>  
  
 <span data-ttu-id="61056-144">El modificador **-log** debe aparecer al final de la línea de comandos, después de todos los demás modificadores.</span><span class="sxs-lookup"><span data-stu-id="61056-144">The **-log** switch must appear at the end of the command line, after all other switches.</span></span> <span data-ttu-id="61056-145">El argumento de nombre de archivo es opcional.</span><span class="sxs-lookup"><span data-stu-id="61056-145">The filename argument is optional.</span></span> <span data-ttu-id="61056-146">Si se especifica un nombre de archivo y el archivo no existe, este se crea.</span><span class="sxs-lookup"><span data-stu-id="61056-146">If a filename is specified, and the file does not exist, the file is created.</span></span> <span data-ttu-id="61056-147">Si no es posible crear el archivo, por ejemplo, debido a un acceso de escritura insuficiente, el registro se escribe en la ubicación APPDATA no localizada (ver más abajo).</span><span class="sxs-lookup"><span data-stu-id="61056-147">If the file cannot be created - for example, due to insufficient write access, the log is written to the nonlocalized APPDATA location instead (See below).</span></span> <span data-ttu-id="61056-148">Si no se especifica el argumento de nombre de archivo, se escriben dos archivos en la carpeta de datos de la aplicación no localizada del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="61056-148">If the filename argument is not specified, two files are written to the current user's nonlocalized application data folder.</span></span> <span data-ttu-id="61056-149">La carpeta de datos de la aplicación no localizada para SQL Server se puede obtener de la variable de entorno APPDATA.</span><span class="sxs-lookup"><span data-stu-id="61056-149">The nonlocalized application data folder for SQL Server can be found from the APPDATA environment variable.</span></span> <span data-ttu-id="61056-150">Por ejemplo, para SQL Server 2012, la carpeta es \<system drive> : \usuarios \\<nombredeusuario \> \AppData\Roaming\Microsoft\AppEnv\10.0 \\ .</span><span class="sxs-lookup"><span data-stu-id="61056-150">For example, for SQL Server 2012, the folder is \<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\\.</span></span> <span data-ttu-id="61056-151">De forma predeterminada, los dos archivos se denominan ActivityLog.xml y ActivityLog.xsl.</span><span class="sxs-lookup"><span data-stu-id="61056-151">The two files are, by default, named ActivityLog.xml and ActivityLog.xsl.</span></span> <span data-ttu-id="61056-152">El primero contiene los datos del registro de actividad y el segundo es una hoja de estilos XML que permite visualizar correctamente el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="61056-152">The former contains the activity log data and the latter is an XML style sheet which provides a more convenient way to view the XML file.</span></span> <span data-ttu-id="61056-153">Siga estos pasos para ver el archivo de registro en el visor XML predeterminado, como Internet Explorer: haga clic en Inicio, haga clic en ejecutar... "y, a continuación, escriba" \<system drive> : \usuarios \\<nombredeusuario \>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml "en el campo proporcionado y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="61056-153">Use the following steps to view the log file in your default XML viewer, like Internet Explorer:  Click Start, then click Run...", then type "\<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" into the field provided, and then press Enter.</span></span>  
  
 <span data-ttu-id="61056-154">Los archivos que contienen consultas solicitarán la conexión con un servidor si se proporciona información de conexión y el tipo de archivo está asociado con ese tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="61056-154">Files that contain queries will prompt to be connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="61056-155">Por ejemplo, los archivos .sql abrirán una ventana del Editor de consultas de SQL en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], y los archivos .mdx abrirán una ventana del Editor de consultas MDX en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61056-155">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="61056-156">Las**Soluciones y proyectos de SQL Server** se abrirán en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61056-156">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="61056-157">La siguiente tabla asigna tipos de servidores a extensiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="61056-157">The following table maps server types to file extensions.</span></span>  
  
|<span data-ttu-id="61056-158">Tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="61056-158">Server type</span></span>|<span data-ttu-id="61056-159">Extensión</span><span class="sxs-lookup"><span data-stu-id="61056-159">Extension</span></span>|  
|-----------------|---------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]|<span data-ttu-id="61056-160">.sql</span><span class="sxs-lookup"><span data-stu-id="61056-160">.sql</span></span>|  
|<span data-ttu-id="61056-161">SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="61056-161">SQL Server Analysis Services</span></span>|<span data-ttu-id="61056-162">.mdx</span><span class="sxs-lookup"><span data-stu-id="61056-162">.mdx</span></span><br /><br /> <span data-ttu-id="61056-163">.xmla</span><span class="sxs-lookup"><span data-stu-id="61056-163">.xmla</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="61056-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="61056-164">Examples</span></span>  
 <span data-ttu-id="61056-165">El siguiente script abre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] desde un símbolo del sistema con la configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="61056-165">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt with the default settings:</span></span>  
  
```  
Ssms  
  
```  
  
 <span data-ttu-id="61056-166">El siguiente script abre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] desde un símbolo del sistema, con autenticación de Windows, con el Editor de código establecido en el servidor `ACCTG and the database AdventureWorks2012,` sin mostrar la pantalla de presentación:</span><span class="sxs-lookup"><span data-stu-id="61056-166">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, with Windows Authentication, with the Code Editor set to the server `ACCTG and the database AdventureWorks2012,` without showing the splash screen:</span></span>  
  
```  
Ssms -E -S ACCTG -d AdventureWorks2012 -nosplash  
  
```  
  
 <span data-ttu-id="61056-167">El siguiente script abre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] desde un símbolo del sistema y abre el script de MonthEndQuery:</span><span class="sxs-lookup"><span data-stu-id="61056-167">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthEndQuery script.</span></span>  
  
```  
Ssms "C:\Documents and Settings\username\My Documents\SQL Server Management Studio Projects\FinanceScripts\FinanceScripts\MonthEndQuery.sql"  
  
```  
  
 <span data-ttu-id="61056-168">El siguiente script abre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] desde un símbolo del sistema y abre el proyecto NewReportsProject en el equipo denominado `developer`:</span><span class="sxs-lookup"><span data-stu-id="61056-168">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the NewReportsProject project on the computer named `developer`:</span></span>  
  
```  
Ssms "\\developer\fin\ReportProj\ReportProj\NewReportProj.ssmssqlproj"  
  
```  
  
 <span data-ttu-id="61056-169">El siguiente script abre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] desde un símbolo del sistema y abre la solución MonthlyReports:</span><span class="sxs-lookup"><span data-stu-id="61056-169">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthlyReports solution:</span></span>  
  
```  
Ssms "C:\solutionsfolder\ReportProj\MonthlyReports.ssmssln"  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="61056-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61056-170">See Also</span></span>  
 [<span data-ttu-id="61056-171">Usar SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61056-171">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
