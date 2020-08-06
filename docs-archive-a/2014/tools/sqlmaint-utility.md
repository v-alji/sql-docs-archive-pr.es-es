---
title: SQLMAINT (utilidad) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- database maintenance plans [SQL Server]
- sqlmaint utility
- maintaining databases [SQL Server]
- backups [SQL Server], sqlmaint utility
- command prompt utilities [SQL Server], sqlmaint
- maintenance plans [SQL Server], command prompt
- backing up [SQL Server], sqlmaint utility
ms.assetid: 937a9932-4aed-464b-b97a-a5acfe6a50de
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80e60b75305ee91e8b62a201d9c86af301326789
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743725"
---
# <a name="sqlmaint-utility"></a><span data-ttu-id="a391c-102">sqlmaint, utilidad</span><span class="sxs-lookup"><span data-stu-id="a391c-102">sqlmaint Utility</span></span>
  <span data-ttu-id="a391c-103">La utilidad**sqlmaint** realiza un conjunto especificado de operaciones de mantenimiento en una o varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-103">The**sqlmaint** utility performs a specified set of maintenance operations on one or more databases.</span></span> <span data-ttu-id="a391c-104">Use **sqlmaint** para ejecutar comprobaciones de DBCC, realizar una copia de seguridad de una base de datos y su registro de transacciones, actualizar estadísticas y volver a generar índices.</span><span class="sxs-lookup"><span data-stu-id="a391c-104">Use **sqlmaint** to run DBCC checks, back up a database and its transaction log, update statistics, and rebuild indexes.</span></span> <span data-ttu-id="a391c-105">Todas las actividades de mantenimiento de bases de datos generan un informe que se puede enviar a un archivo de texto designado, un archivo HTML o una cuenta de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a391c-105">All database maintenance activities generate a report that can be sent to a designated text file, HTML file, or e-mail account.</span></span> <span data-ttu-id="a391c-106">**sqlmaint** ejecuta los planes de mantenimiento de bases de datos creados con versiones anteriores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a391c-106">**sqlmaint** executes database maintenance plans created with previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a391c-107">Para ejecutar los planes de mantenimiento de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] desde el símbolo del sistema, emplee la [utilidad dtexec](../integration-services/packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="a391c-107">To run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plans from the command prompt, use the [dtexec Utility](../integration-services/packages/dtexec-utility.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="a391c-108">Use en su lugar la característica de plan de mantenimiento de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a391c-108">Use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plan feature instead.</span></span> <span data-ttu-id="a391c-109">Para obtener más información sobre los planes de mantenimiento, vea [Planes de mantenimiento](../relational-databases/maintenance-plans/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="a391c-109">For more information on maintenance plans, see [Maintenance Plans](../relational-databases/maintenance-plans/maintenance-plans.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a391c-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a391c-110">Syntax</span></span>  
  
```  
  
      sqlmaint   
[-?] |  
[  
     [-Sserver_name[\instance_name]]  
     [-Ulogin_ID [-Ppassword]]  
     {  
          [-Ddatabase_name | -PlanNamename | -PlanIDguid ]  
          [-Rpttext_file]  
          [-Tooperator_name]  
          [-HtmlRpthtml_file [-DelHtmlRpt <time_period>] ]  
          [-RmUnusedSpacethreshold_percentfree_percent]  
          [-CkDB | -CkDBNoIdx]  
          [-CkAl | -CkAlNoIdx]  
          [-CkCat]  
          [-UpdOptiStatssample_percent]  
          [-RebldIdxfree_space]  
          [-SupportComputedColumn]  
          [-WriteHistory]  
          [  
               {-BkUpDB [backup_path] | -BkUpLog [backup_path] }  
               {-BkUpMedia  
                    {DISK [  
                           [-DelBkUps<time_period>]   
                           [-CrBkSubDir ]   
                           [-UseDefDir ]   
                          ]  
                     | TAPE   
                    }  
               }  
               [-BkUpOnlyIfClean]  
               [-VrfyBackup]  
          ]  
     }  
]  
<time_period> ::=  
number[minutes | hours | days | weeks | months]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a391c-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a391c-111">Arguments</span></span>  
 <span data-ttu-id="a391c-112">Los parámetros y sus valores deben estar separados por un espacio.</span><span class="sxs-lookup"><span data-stu-id="a391c-112">The parameters and their values must be separated by a space.</span></span> <span data-ttu-id="a391c-113">Por ejemplo, debe haber un espacio en blanco entre **-S** y *server_name*.</span><span class="sxs-lookup"><span data-stu-id="a391c-113">For example, there must be a space between **-S** and *server_name*.</span></span>  
  
 <span data-ttu-id="a391c-114">**-?**</span><span class="sxs-lookup"><span data-stu-id="a391c-114">**-?**</span></span>  
 <span data-ttu-id="a391c-115">Especifica que debe devolverse el diagrama de sintaxis para **sqlmaint** .</span><span class="sxs-lookup"><span data-stu-id="a391c-115">Specifies that the syntax diagram for **sqlmaint** be returned.</span></span> <span data-ttu-id="a391c-116">Este parámetro debe utilizarse solo.</span><span class="sxs-lookup"><span data-stu-id="a391c-116">This parameter must be used alone.</span></span>  
  
 <span data-ttu-id="a391c-117">**-S** _SERVER_NAME_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="a391c-117">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="a391c-118">Especifica la instancia de destino de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a391c-118">Specifies the target instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a391c-119">Especifique *server_name* para conectar con la instancia predeterminada de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="a391c-119">Specify *server_name* to connect to the default instance of [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on that server.</span></span> <span data-ttu-id="a391c-120">Especifique *server_name **_\\_** instance_name* para conectarse a una instancia con nombre de [!INCLUDE[ssDE](../includes/ssde-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="a391c-120">Specify *server_name\*\*_\\_*\* instance_name\* to connect to a named instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="a391c-121">Si no se especifica ningún servidor, **sqlmaint** se conecta a la instancia predeterminada de [!INCLUDE[ssDE](../includes/ssde-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a391c-121">If no server is specified, **sqlmaint** connects to the default instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="a391c-122">**-U** _login_ID_</span><span class="sxs-lookup"><span data-stu-id="a391c-122">**-U** _login_ID_</span></span>  
 <span data-ttu-id="a391c-123">Especifica el Id. de inicio de sesión que va a utilizarse para conectar al servidor.</span><span class="sxs-lookup"><span data-stu-id="a391c-123">Specifies the login ID to use when connecting to the server.</span></span> <span data-ttu-id="a391c-124">Si no se especifica, **sqlmaint** intenta utilizar la autenticación de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="a391c-124">If not supplied, **sqlmaint** attempts to use [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="a391c-125">Si *login_ID* contiene caracteres especiales, debe incluirse entre comillas dobles ("); de lo contrario, las comillas dobles son opcionales.</span><span class="sxs-lookup"><span data-stu-id="a391c-125">If *login_ID* contains special characters, it must be enclosed in double quotation marks ("); otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a391c-126">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a391c-126">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a391c-127">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="a391c-127">**-P** _password_</span></span>  
 <span data-ttu-id="a391c-128">Especifica la contraseña para el identificador de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="a391c-128">Specifies the password for the login ID.</span></span> <span data-ttu-id="a391c-129">Solo tiene validez si también se especifica el parámetro **-U** .</span><span class="sxs-lookup"><span data-stu-id="a391c-129">Only valid if the **-U** parameter is also supplied.</span></span> <span data-ttu-id="a391c-130">Si *password* contiene caracteres especiales, debe incluirse entre comillas dobles; de lo contrario, las comillas dobles son opcionales.</span><span class="sxs-lookup"><span data-stu-id="a391c-130">If *password* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a391c-131">La contraseña no se enmascara.</span><span class="sxs-lookup"><span data-stu-id="a391c-131">The password is not masked.</span></span> <span data-ttu-id="a391c-132">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a391c-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a391c-133">**-D** _database_name_</span><span class="sxs-lookup"><span data-stu-id="a391c-133">**-D** _database_name_</span></span>  
 <span data-ttu-id="a391c-134">Especifica el nombre de la base de datos en que se va a realizar la operación de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a391c-134">Specifies the name of the database in which to perform the maintenance operation.</span></span> <span data-ttu-id="a391c-135">Si *database_name* contiene caracteres especiales, debe incluirse entre comillas dobles; de lo contrario, las comillas dobles son opcionales.</span><span class="sxs-lookup"><span data-stu-id="a391c-135">If *database_name* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
 <span data-ttu-id="a391c-136">**-PlanName** _name_</span><span class="sxs-lookup"><span data-stu-id="a391c-136">**-PlanName** _name_</span></span>  
 <span data-ttu-id="a391c-137">Especifica el nombre de un plan de mantenimiento de base de datos definido mediante el Asistente para planes de mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-137">Specifies the name of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="a391c-138">La única información del plan que **sqlmaint** usa es la lista de las bases de datos incluidas en él.</span><span class="sxs-lookup"><span data-stu-id="a391c-138">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="a391c-139">Todas las actividades de mantenimiento que se especifiquen en los demás parámetros de **sqlmaint** se aplicarán a esta lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-139">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span>  
  
 <span data-ttu-id="a391c-140">**-PlanID** _guid_</span><span class="sxs-lookup"><span data-stu-id="a391c-140">**-PlanID** _guid_</span></span>  
 <span data-ttu-id="a391c-141">Especifica el identificador exclusivo global (GUID) de un plan de mantenimiento de base de datos definido mediante el Asistente para planes de mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-141">Specifies the globally unique identifier (GUID) of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="a391c-142">La única información del plan que **sqlmaint** usa es la lista de las bases de datos incluidas en él.</span><span class="sxs-lookup"><span data-stu-id="a391c-142">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="a391c-143">Todas las actividades de mantenimiento que se especifiquen en los demás parámetros de **sqlmaint** se aplicarán a esta lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-143">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span> <span data-ttu-id="a391c-144">Debe coincidir con un valor de plan_id en msdb.dbo.sysdbmaintplans.</span><span class="sxs-lookup"><span data-stu-id="a391c-144">This must match a plan_id value in msdb.dbo.sysdbmaintplans.</span></span>  
  
 <span data-ttu-id="a391c-145">**-Rpt** _text_file_</span><span class="sxs-lookup"><span data-stu-id="a391c-145">**-Rpt** _text_file_</span></span>  
 <span data-ttu-id="a391c-146">Especifica la ruta de acceso completa y el nombre del archivo en que se va a generar el informe.</span><span class="sxs-lookup"><span data-stu-id="a391c-146">Specifies the full path and name of the file into which the report is to be generated.</span></span> <span data-ttu-id="a391c-147">También se genera el informe en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a391c-147">The report is also generated on the screen.</span></span> <span data-ttu-id="a391c-148">El informe mantiene información de las versiones al agregar una fecha al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="a391c-148">The report maintains version information by adding a date to the file name.</span></span> <span data-ttu-id="a391c-149">La fecha se genera de la siguiente manera: al final del nombre de archivo pero antes del punto, con el formato _*yyyyMMddhhmm*.</span><span class="sxs-lookup"><span data-stu-id="a391c-149">The date is generated as follows: at the end of the file name but before the period, in the form _*yyyyMMddhhmm*.</span></span> <span data-ttu-id="a391c-150">*yyyy* = año, *MM* = mes, *dd* = día, *hh* = hora, *mm* = minuto.</span><span class="sxs-lookup"><span data-stu-id="a391c-150">*yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, *mm* = minute.</span></span>  
  
 <span data-ttu-id="a391c-151">Si ejecuta la utilidad a las 10:23 a.m.</span><span class="sxs-lookup"><span data-stu-id="a391c-151">If you run the utility at 10:23 A.M.</span></span> <span data-ttu-id="a391c-152">el 1 de diciembre de 1996 y este es el valor de *text_file* :</span><span class="sxs-lookup"><span data-stu-id="a391c-152">on December 1, 1996, and this is the *text_file* value:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.rpt  
```  
  
 <span data-ttu-id="a391c-153">El nombre del archivo generado será:</span><span class="sxs-lookup"><span data-stu-id="a391c-153">The generated file name is:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint_199612011023.rpt  
```  
  
 <span data-ttu-id="a391c-154">Se requiere el nombre de archivo UNC (Convención de nomenclatura universal) para *text_file* cuando **sqlmaint** tiene acceso a un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="a391c-154">The full Universal Naming Convention (UNC) file name is required for *text_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="a391c-155">**-Para** _operator_name_</span><span class="sxs-lookup"><span data-stu-id="a391c-155">**-To** _operator_name_</span></span>  
 <span data-ttu-id="a391c-156">Especifica el operador al que se envía el informe generado a través de SQL Mail.</span><span class="sxs-lookup"><span data-stu-id="a391c-156">Specifies the operator to whom the generated report is sent through SQL Mail.</span></span>  
  
 <span data-ttu-id="a391c-157">**-HtmlRpt** _html_file_</span><span class="sxs-lookup"><span data-stu-id="a391c-157">**-HtmlRpt** _html_file_</span></span>  
 <span data-ttu-id="a391c-158">Especifica la ruta de acceso completa y el nombre del archivo en que se va a generar un informe HTML.</span><span class="sxs-lookup"><span data-stu-id="a391c-158">Specifies the full path and name of the file into which an HTML report is to be generated.</span></span> <span data-ttu-id="a391c-159">**sqlmaint** genera el nombre de archivo anexando una cadena con el formato _*yyyyMMddhhmm* al nombre de archivo, al igual que en el caso del parámetro **-Rpt** .</span><span class="sxs-lookup"><span data-stu-id="a391c-159">**sqlmaint** generates the file name by appending a string of the format _*yyyyMMddhhmm* to the file name, just as it does for the **-Rpt** parameter.</span></span>  
  
 <span data-ttu-id="a391c-160">Se requiere el nombre UNC completo del archivo para *html_file* cuando **sqlmaint** tiene acceso a un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="a391c-160">The full UNC file name is required for *html_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="a391c-161">**-DelHtmlRpt** \<*time_period*></span><span class="sxs-lookup"><span data-stu-id="a391c-161">**-DelHtmlRpt** \<*time_period*></span></span>  
 <span data-ttu-id="a391c-162">Especifica que debe eliminarse cualquier informe HTML del directorio de informes si el intervalo posterior a la creación del archivo de informe supera el valor de \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="a391c-162">Specifies that any HTML report in the report directory be deleted if the time interval after the creation of the report file exceeds \<*time_period*>.</span></span> <span data-ttu-id="a391c-163">**-DelHtmlRpt** busca archivos cuyo nombre se ajuste al patrón generado a partir del parámetro *html_file*.</span><span class="sxs-lookup"><span data-stu-id="a391c-163">**-DelHtmlRpt** looks for files whose name fits the pattern generated from the *html_file* parameter.</span></span> <span data-ttu-id="a391c-164">Si *html_file* es C:\Archivos de programa\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, **-DelHtmlRpt** hará que **sqlmaint** elimine todos los archivos cuyos nombres coincidan con el patrón C:\Archivos de programa\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm y que sean más antiguos que el valor de \<*time_period*> especificado.</span><span class="sxs-lookup"><span data-stu-id="a391c-164">If *html_file* is c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, then **-DelHtmlRpt** causes **sqlmaint** to delete any files whose names match the pattern C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm and that are older than the specified \<*time_period*>.</span></span>  
  
 <span data-ttu-id="a391c-165">**-RmUnusedSpace** _threshold_percent free_percent_</span><span class="sxs-lookup"><span data-stu-id="a391c-165">**-RmUnusedSpace** _threshold_percent free_percent_</span></span>  
 <span data-ttu-id="a391c-166">Especifica que se quite el espacio no usado de la base de datos especificada en **-D**.</span><span class="sxs-lookup"><span data-stu-id="a391c-166">Specifies that unused space be removed from the database specified in **-D**.</span></span> <span data-ttu-id="a391c-167">Esta opción solo resulta útil para aquellas bases de datos definidas para crecer automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a391c-167">This option is only useful for databases that are defined to grow automatically.</span></span> <span data-ttu-id="a391c-168">*Threshold_percent* especifica en megabytes el tamaño que debe alcanzar la base de datos antes de que **sqlmaint** intente quitar el espacio de datos no usado.</span><span class="sxs-lookup"><span data-stu-id="a391c-168">*Threshold_percent* specifies in megabytes the size that the database must reach before **sqlmaint** attempts to remove unused data space.</span></span> <span data-ttu-id="a391c-169">Si la base de datos es menor que el valor de *threshold_percent*, no se realiza ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="a391c-169">If the database is smaller than the *threshold_percent*, no action is taken.</span></span> <span data-ttu-id="a391c-170">*Free_percent* especifica la cantidad de espacio no usado que debe conservarse en la base de datos, especificado como porcentaje del tamaño final de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-170">*Free_percent* specifies how much unused space must remain in the database, specified as a percentage of the final size of the database.</span></span> <span data-ttu-id="a391c-171">Por ejemplo, si una base de datos de 200 MB contiene 100 MB de datos y se especifica el valor 10 para *free_percent* , el tamaño final de la base de datos será de 110 MB.</span><span class="sxs-lookup"><span data-stu-id="a391c-171">For example, if a 200-MB database contains 100 MB of data, specifying 10 for *free_percent* results in the final database size being 110 MB.</span></span> <span data-ttu-id="a391c-172">Tenga en cuenta que una base de datos no se ampliará si ocupa menos espacio que la suma de *free_percent* más el espacio ocupado por los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-172">Note that a database is not expanded if it is smaller than *free_percent* plus the amount of data in the database.</span></span> <span data-ttu-id="a391c-173">Por ejemplo, si una base de datos de 108 MB tiene 100 MB de datos y se especifica 10 para *free_percent* , la base de datos no se ampliará a 110 MB; se mantendrá con un espacio de 108 MB.</span><span class="sxs-lookup"><span data-stu-id="a391c-173">For example, if a 108-MB database has 100 MB of data, specifying 10 for *free_percent* does not expand the database to 110 MB; it remains at 108 MB.</span></span>  
  
 <span data-ttu-id="a391c-174">**-CkDB** |  **-CkDBNoIdx**</span><span class="sxs-lookup"><span data-stu-id="a391c-174">**-CkDB** | **-CkDBNoIdx**</span></span>  
 <span data-ttu-id="a391c-175">Especifica que se ejecute una instrucción DBCC CHECKDB o una instrucción DBCC CHECKDB con la opción NOINDEX en la base de datos especificada en **-D**.</span><span class="sxs-lookup"><span data-stu-id="a391c-175">Specifies that a DBCC CHECKDB statement or a DBCC CHECKDB statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="a391c-176">Para obtener más información, vea DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="a391c-176">For more information, see DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="a391c-177">Se escribe una advertencia en *text_file* si la base de datos está en uso cuando **sqlmaint** se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="a391c-177">A warning is written to *text_file* if the database is in use when **sqlmaint** runs.</span></span>  
  
 <span data-ttu-id="a391c-178">**-CkAl** |  **-CkAlNoIdx**</span><span class="sxs-lookup"><span data-stu-id="a391c-178">**-CkAl** | **-CkAlNoIdx**</span></span>  
 <span data-ttu-id="a391c-179">Especifica que se ejecute una instrucción DBCC CHECKALLOC con la opción NOINDEX en la base de datos especificada en **-D**.</span><span class="sxs-lookup"><span data-stu-id="a391c-179">Specifies that a DBCC CHECKALLOC statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="a391c-180">Para obtener más información, vea [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a391c-180">For more information, see [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span></span>  
  
 <span data-ttu-id="a391c-181">**-CkCat**</span><span class="sxs-lookup"><span data-stu-id="a391c-181">**-CkCat**</span></span>  
 <span data-ttu-id="a391c-182">Especifica que se ejecute una instrucción DBCC CHECKCATALOG (Transact-SQL) en la base de datos especificada en **-D**.</span><span class="sxs-lookup"><span data-stu-id="a391c-182">Specifies that a DBCC CHECKCATALOG (Transact-SQL) statement be run in the database specified in **-D**.</span></span> <span data-ttu-id="a391c-183">Para obtener más información, vea [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a391c-183">For more information, see [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span></span>  
  
 <span data-ttu-id="a391c-184">**-UpdOptiStats** _sample_percent_</span><span class="sxs-lookup"><span data-stu-id="a391c-184">**-UpdOptiStats** _sample_percent_</span></span>  
 <span data-ttu-id="a391c-185">Especifica que se ejecute la instrucción siguiente en cada una de las tablas de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="a391c-185">Specifies that the following statement be run on each table in the database:</span></span>  
  
```  
UPDATE STATISTICS table WITH SAMPLE sample_percent PERCENT;  
```  
  
 <span data-ttu-id="a391c-186">Si las tablas contienen columnas calculadas, también debe especificar el argumento **-SupportedComputedColumn** al usar **-UpdOptiStats**.</span><span class="sxs-lookup"><span data-stu-id="a391c-186">If the tables contain computed columns, you must also specify the **-SupportedComputedColumn** argument when you use **-UpdOptiStats**.</span></span>  
  
 <span data-ttu-id="a391c-187">Para obtener más información, vea [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a391c-187">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
 <span data-ttu-id="a391c-188">**-RebldIdx** _free_space_</span><span class="sxs-lookup"><span data-stu-id="a391c-188">**-RebldIdx** _free_space_</span></span>  
 <span data-ttu-id="a391c-189">Especifica que se deben volver a generar los índices de las tablas de la base de datos de destino mediante el valor porcentual de *free_space* en proporción inversa al factor de relleno.</span><span class="sxs-lookup"><span data-stu-id="a391c-189">Specifies that indexes on tables in the target database should be rebuilt by using the *free_space* percent value as the inverse of the fill factor.</span></span> <span data-ttu-id="a391c-190">Por ejemplo, si el porcentaje de *free_space* es 30, el factor de relleno empleado será 70.</span><span class="sxs-lookup"><span data-stu-id="a391c-190">For example, if *free_space* percentage is 30, then the fill factor used is 70.</span></span> <span data-ttu-id="a391c-191">Si se especifica un valor de 100 como porcentaje de *free_space* , se volverán a generar los índices con el valor de factor de relleno original.</span><span class="sxs-lookup"><span data-stu-id="a391c-191">If a *free_space* percentage value of 100 is specified, then the indexes are rebuilt with the original fill factor value.</span></span>  
  
 <span data-ttu-id="a391c-192">Si los índices están en columnas calculadas, también debe especificar el argumento **-SupportComputedColumn** al usar **-RebldIdx**.</span><span class="sxs-lookup"><span data-stu-id="a391c-192">If the indexes are on computed columns, you must also specify the **-SupportComputedColumn** argument when you use **-RebldIdx**.</span></span>  
  
 <span data-ttu-id="a391c-193">**-SupportComputedColumn**</span><span class="sxs-lookup"><span data-stu-id="a391c-193">**-SupportComputedColumn**</span></span>  
 <span data-ttu-id="a391c-194">Debe especificarse para ejecutar los comandos de mantenimiento de DBCC con **sqlmaint** en columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="a391c-194">Must be specified to run DBCC maintenance commands with **sqlmaint** on computed columns.</span></span>  
  
 <span data-ttu-id="a391c-195">**-WriteHistory**</span><span class="sxs-lookup"><span data-stu-id="a391c-195">**-WriteHistory**</span></span>  
 <span data-ttu-id="a391c-196">Especifica que se escriba una entrada en msdb.dbo.sysdbmaintplan_history para cada acción de mantenimiento que **sqlmaint**realice.</span><span class="sxs-lookup"><span data-stu-id="a391c-196">Specifies that an entry be made in msdb.dbo.sysdbmaintplan_history for each maintenance action performed by **sqlmaint**.</span></span> <span data-ttu-id="a391c-197">Si se especifica **-PlanName** o **-PlanID** , las entradas de sysdbmaintplan_history usarán el identificador del plan especificado.</span><span class="sxs-lookup"><span data-stu-id="a391c-197">If **-PlanName** or **-PlanID** is specified, the entries in sysdbmaintplan_history use the ID of the specified plan.</span></span> <span data-ttu-id="a391c-198">Si se especifica **-D** , las entradas de sysdbmaintplan_history para el identificador de plan estarán compuestas de ceros.</span><span class="sxs-lookup"><span data-stu-id="a391c-198">If **-D** is specified, the entries in sysdbmaintplan_history are made with zeroes for the plan ID.</span></span>  
  
 <span data-ttu-id="a391c-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span><span class="sxs-lookup"><span data-stu-id="a391c-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span></span>  
 <span data-ttu-id="a391c-200">Especifica una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a391c-200">Specifies a backup action.</span></span> <span data-ttu-id="a391c-201">**-BkUpDb** hace una copia de seguridad de toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-201">**-BkUpDb** backs up the entire database.</span></span> <span data-ttu-id="a391c-202">**-BkUpLog** hace una copia de seguridad solo del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a391c-202">**-BkUpLog** backs up only the transaction log.</span></span>  
  
 <span data-ttu-id="a391c-203">*backup_path* especifica el directorio de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a391c-203">*backup_path* specifies the directory for the backup.</span></span> <span data-ttu-id="a391c-204">*backup_path* no es necesario si también se especifica **-UseDefDir** . Si se especifican ambos, se reemplaza por **-UseDefDir** .</span><span class="sxs-lookup"><span data-stu-id="a391c-204">*backup_path* is not needed if **-UseDefDir** is also specified, and is overridden by **-UseDefDir** if both are specified.</span></span> <span data-ttu-id="a391c-205">La copia de seguridad se puede colocar en un directorio o en una dirección de dispositivo de cinta (por ejemplo, \\\\.\TAPE0).</span><span class="sxs-lookup"><span data-stu-id="a391c-205">The backup can be placed in a directory or a tape device address (for example, \\\\.\TAPE0).</span></span> <span data-ttu-id="a391c-206">El nombre de archivo de una copia de seguridad de base de datos se genera automáticamente del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a391c-206">The file name for a database backup is generated automatically as follows:</span></span>  
  
```  
dbname_db_yyyyMMddhhmm.BAK  
  
```  
  
 <span data-ttu-id="a391c-207">, donde</span><span class="sxs-lookup"><span data-stu-id="a391c-207">where</span></span>  
  
-   <span data-ttu-id="a391c-208">*dbname* es el nombre de la base de datos de la que se realiza una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a391c-208">*dbname* is the name of the database being backed up.</span></span>  
  
-   <span data-ttu-id="a391c-209">*aaaaMMddhhmm* es la hora de la operación de copia de seguridad, siendo *aaaa* = año, *MM* = mes, *dd* = día, *hh* = hora y *mm* = minuto.</span><span class="sxs-lookup"><span data-stu-id="a391c-209">*yyyyMMddhhmm* is the time of the backup operation with *yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, and *mm* = minute.</span></span>  
  
 <span data-ttu-id="a391c-210">El nombre del archivo para una copia de seguridad de transacciones se genera automáticamente con un formato similar:</span><span class="sxs-lookup"><span data-stu-id="a391c-210">The file name for a transaction backup is generated automatically with a similar format:</span></span>  
  
```  
dbname_log_yyyymmddhhmm.BAK  
  
```  
  
 <span data-ttu-id="a391c-211">Si se usa el parámetro **-BkUpDB** , también deberá especificar el medio por medio del parámetro **-BkUpMedia** .</span><span class="sxs-lookup"><span data-stu-id="a391c-211">If you use the **-BkUpDB** parameter, you must also specify the media by using the **-BkUpMedia** parameter.</span></span>  
  
 <span data-ttu-id="a391c-212">**-BkUpMedia**</span><span class="sxs-lookup"><span data-stu-id="a391c-212">**-BkUpMedia**</span></span>  
 <span data-ttu-id="a391c-213">Especifica el tipo de medio para la copia de seguridad (DISK o TAPE).</span><span class="sxs-lookup"><span data-stu-id="a391c-213">Specifies the media type of the backup, either DISK or TAPE.</span></span>  
  
 <span data-ttu-id="a391c-214">**DISK**</span><span class="sxs-lookup"><span data-stu-id="a391c-214">**DISK**</span></span>  
 <span data-ttu-id="a391c-215">Especifica que el medio de la copia de seguridad es un disco.</span><span class="sxs-lookup"><span data-stu-id="a391c-215">Specifies that the backup medium is disk.</span></span>  
  
 <span data-ttu-id="a391c-216">**-DelBkUps**\< *time_period* ></span><span class="sxs-lookup"><span data-stu-id="a391c-216">**-DelBkUps**\< *time_period* ></span></span>  
 <span data-ttu-id="a391c-217">Para copias de seguridad en disco, especifica que deben eliminarse todos los archivos de copia de seguridad del directorio de copia de seguridad si el intervalo posterior a la creación de la copia de seguridad supera el valor de \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="a391c-217">For disk backups, specifies that any backup file in the backup directory be deleted if the time interval after the creation of the backup exceeds the \<*time_period*>.</span></span>  
  
 <span data-ttu-id="a391c-218">**-CrBkSubDir**</span><span class="sxs-lookup"><span data-stu-id="a391c-218">**-CrBkSubDir**</span></span>  
 <span data-ttu-id="a391c-219">Para copias de seguridad en disco, especifica que se cree un subdirectorio en el directorio [*backup_path*] o en el directorio de copia de seguridad predeterminado, si también se especifica **-UseDefDir** .</span><span class="sxs-lookup"><span data-stu-id="a391c-219">For disk backups, specifies that a subdirectory be created in the [*backup_path*] directory or in the default backup directory if **-UseDefDir** is also specified.</span></span> <span data-ttu-id="a391c-220">El nombre del subdirectorio se genera a partir del nombre de la base de datos especificado en **-D**.</span><span class="sxs-lookup"><span data-stu-id="a391c-220">The name of the subdirectory is generated from the database name specified in **-D**.</span></span> <span data-ttu-id="a391c-221">**-CrBkSubDir** ofrece una sencilla forma de poner todas las copias de seguridad de diferentes bases de datos en subdirectorios separados sin tener que cambiar el parámetro *backup_path* .</span><span class="sxs-lookup"><span data-stu-id="a391c-221">**-CrBkSubDir** offers an easy way to put all the backups for different databases into separate subdirectories without having to change the *backup_path* parameter.</span></span>  
  
 <span data-ttu-id="a391c-222">**-UseDefDir**</span><span class="sxs-lookup"><span data-stu-id="a391c-222">**-UseDefDir**</span></span>  
 <span data-ttu-id="a391c-223">Para copias de seguridad en disco, especifica que se cree el archivo de copia de seguridad en el directorio de copia de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a391c-223">For disk backups, specifies that the backup file be created in the default backup directory.</span></span> <span data-ttu-id="a391c-224">**UseDefDir** invalida *backup_path* si se especifican ambos parámetros.</span><span class="sxs-lookup"><span data-stu-id="a391c-224">**UseDefDir** overrides *backup_path* if both are specified.</span></span> <span data-ttu-id="a391c-225">El directorio predeterminado de copia de seguridad en una instalación predeterminada de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] es C:\Archivos de programa\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span><span class="sxs-lookup"><span data-stu-id="a391c-225">With a default [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup, the default backup directory is C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span></span>  
  
 <span data-ttu-id="a391c-226">**TAPE**</span><span class="sxs-lookup"><span data-stu-id="a391c-226">**TAPE**</span></span>  
 <span data-ttu-id="a391c-227">Especifica que el medio de copia de seguridad es una cinta.</span><span class="sxs-lookup"><span data-stu-id="a391c-227">Specifies that the backup medium is tape.</span></span>  
  
 <span data-ttu-id="a391c-228">**-BkUpOnlyIfClean**</span><span class="sxs-lookup"><span data-stu-id="a391c-228">**-BkUpOnlyIfClean**</span></span>  
 <span data-ttu-id="a391c-229">Indica que solo se realice la copia de seguridad si las comprobaciones **-Ck** especificadas no han detectado problemas en los datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-229">Specifies that the backup occur only if any specified **-Ck** checks did not find problems with the data.</span></span> <span data-ttu-id="a391c-230">Las acciones de mantenimiento se ejecutan en la misma secuencia en que aparecen en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a391c-230">Maintenance actions run in the same sequence as they appear in the command prompt.</span></span> <span data-ttu-id="a391c-231">Especifique los parámetros **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**o **-CkCat** antes de los parámetros **-BkUpDB**/ **-BkUpLog** si también va a especificar **-BkUpOnlyIfClean**; de lo contrario, la copia de seguridad se llevará a cabo con independencia de que la comprobación indique la existencia de problemas o no.</span><span class="sxs-lookup"><span data-stu-id="a391c-231">Specify the parameters **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** before the **-BkUpDB**/**-BkUpLog** parameter(s) if you are also going to specify **-BkUpOnlyIfClean**, or the backup occurs whether or not the check reports problems.</span></span>  
  
 <span data-ttu-id="a391c-232">**-VrfyBackup**</span><span class="sxs-lookup"><span data-stu-id="a391c-232">**-VrfyBackup**</span></span>  
 <span data-ttu-id="a391c-233">Especifica que solo se ejecute RESTORE VERIFYONLY en la copia de seguridad cuando finalice.</span><span class="sxs-lookup"><span data-stu-id="a391c-233">Specifies that RESTORE VERIFYONLY be run on the backup when it completes.</span></span>  
  
 <span data-ttu-id="a391c-234">*número*[**minutos**| **horas**| **día**| **semanas**| **meses**]</span><span class="sxs-lookup"><span data-stu-id="a391c-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span></span>  
 <span data-ttu-id="a391c-235">Especifica el intervalo de tiempo que se utiliza para determinar si un informe o un archivo de copia de seguridad son suficientemente antiguos para poder eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="a391c-235">Specifies the time interval used to determine if a report or backup file is old enough to be deleted.</span></span> <span data-ttu-id="a391c-236">*number* es un número entero seguido (sin espacio) de una unidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a391c-236">*number* is an integer followed (without a space) by a unit of time.</span></span> <span data-ttu-id="a391c-237">Ejemplos válidos:</span><span class="sxs-lookup"><span data-stu-id="a391c-237">Valid examples:</span></span>  
  
-   <span data-ttu-id="a391c-238">**12weeks**</span><span class="sxs-lookup"><span data-stu-id="a391c-238">**12weeks**</span></span>  
  
-   <span data-ttu-id="a391c-239">**3months**</span><span class="sxs-lookup"><span data-stu-id="a391c-239">**3months**</span></span>  
  
-   <span data-ttu-id="a391c-240">**15days**</span><span class="sxs-lookup"><span data-stu-id="a391c-240">**15days**</span></span>  
  
 <span data-ttu-id="a391c-241">Si solo se especifica *number* , la parte de fecha predeterminada es **weeks**.</span><span class="sxs-lookup"><span data-stu-id="a391c-241">If only *number* is specified, the default date part is **weeks**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a391c-242">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a391c-242">Remarks</span></span>  
 <span data-ttu-id="a391c-243">La utilidad **sqlmaint** realiza operaciones de mantenimiento en una o varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-243">The **sqlmaint** utility performs maintenance operations on one or more databases.</span></span> <span data-ttu-id="a391c-244">Si se especifica **-D** , las operaciones especificadas en los modificadores restantes solo se realizan en la base de datos indicada.</span><span class="sxs-lookup"><span data-stu-id="a391c-244">If **-D** is specified, the operations specified in the remaining switches are performed only on the specified database.</span></span> <span data-ttu-id="a391c-245">Si se especifica **-PlanName** o **-PlanID** , la única información que **sqlmaint** recupera del plan de mantenimiento indicado es la lista de bases de datos del plan.</span><span class="sxs-lookup"><span data-stu-id="a391c-245">If **-PlanName** or **-PlanID** are specified, the only information **sqlmaint** retrieves from the specified maintenance plan is the list of databases in the plan.</span></span> <span data-ttu-id="a391c-246">Todas las operaciones especificadas en los parámetros **sqlmaint** restantes se aplican en cada base de datos de la lista obtenida del plan.</span><span class="sxs-lookup"><span data-stu-id="a391c-246">All operations specified in the remaining **sqlmaint** parameters are applied against each database in the list obtained from the plan.</span></span> <span data-ttu-id="a391c-247">La utilidad **sqlmaint** no aplica ninguna de las actividades de mantenimiento definidas en el propio plan.</span><span class="sxs-lookup"><span data-stu-id="a391c-247">The **sqlmaint** utility does not apply any of the maintenance activities defined in the plan itself.</span></span>  
  
 <span data-ttu-id="a391c-248">La utilidad **sqlmaint** devuelve 0 si se ejecuta correctamente o 1 si se produce algún error.</span><span class="sxs-lookup"><span data-stu-id="a391c-248">The **sqlmaint** utility returns 0 if it runs successfully or 1 if it fails.</span></span> <span data-ttu-id="a391c-249">Se informa del error:</span><span class="sxs-lookup"><span data-stu-id="a391c-249">Failure is reported:</span></span>  
  
-   <span data-ttu-id="a391c-250">Si no se produce alguna de las operaciones de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a391c-250">If any of the maintenance actions fail.</span></span>  
  
-   <span data-ttu-id="a391c-251">Si las comprobaciones **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**o **-CkCat** detectan algún problema en los datos.</span><span class="sxs-lookup"><span data-stu-id="a391c-251">If **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** checks find problems with the data.</span></span>  
  
-   <span data-ttu-id="a391c-252">Si se detecta un error general.</span><span class="sxs-lookup"><span data-stu-id="a391c-252">If a general failure is encountered.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="a391c-253">Permisos</span><span class="sxs-lookup"><span data-stu-id="a391c-253">Permissions</span></span>  
 <span data-ttu-id="a391c-254">La utilidad **sqlmaint** puede ejecutarla cualquier usuario de Windows con permiso de **lectura y ejecución** para `sqlmaint.exe`, que está almacenado de manera predeterminada en la carpeta `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` .</span><span class="sxs-lookup"><span data-stu-id="a391c-254">The **sqlmaint** utility can be executed by any Windows user with **Read and Execute** permission on `sqlmaint.exe`, which by default is stored in the `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` folder.</span></span> <span data-ttu-id="a391c-255">Además, el inicio de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] especificado con **-login_ID** debe tener los permisos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] necesarios para realizar la acción indicada.</span><span class="sxs-lookup"><span data-stu-id="a391c-255">Additionally, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login specified with **-login_ID** must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span> <span data-ttu-id="a391c-256">Si la conexión con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utiliza la autenticación de Windows, el inicio de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] asignado al usuario de Windows autenticado debe tener los permisos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] necesarios para realizar la acción especificada.</span><span class="sxs-lookup"><span data-stu-id="a391c-256">If the connection to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses Windows Authentication, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login mapped to the authenticated Windows user must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span>  
  
 <span data-ttu-id="a391c-257">Por ejemplo, para usar **-BkUpDB** , es necesario tener permiso para ejecutar la instrucción BACKUP.</span><span class="sxs-lookup"><span data-stu-id="a391c-257">For example, using the **-BkUpDB** requires permission to execute the BACKUP statement.</span></span> <span data-ttu-id="a391c-258">Para usar el argumento **-UpdOptiStats** , es necesario tener permiso para ejecutar la instrucción UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="a391c-258">And using the **-UpdOptiStats** argument requires permission to execute the UPDATE STATISTICS statement.</span></span> <span data-ttu-id="a391c-259">Para obtener más información, vea las secciones sobre permisos en los temas correspondientes de los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="a391c-259">For more information, see the "Permissions" sections of the corresponding topics in Books Online.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a391c-260">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a391c-260">Examples</span></span>  
  
### <a name="a-performing-dbcc-checks-on-a-database"></a><span data-ttu-id="a391c-261">A.</span><span class="sxs-lookup"><span data-stu-id="a391c-261">A.</span></span> <span data-ttu-id="a391c-262">Realizar comprobaciones DBCC en una base de datos</span><span class="sxs-lookup"><span data-stu-id="a391c-262">Performing DBCC checks on a database</span></span>  
  
```  
sqlmaint -S MyServer -D AdventureWorks2012 -CkDB -CkAl -CkCat -Rpt C:\MyReports\AdvWks_chk.rpt  
```  
  
### <a name="b-updating-statistics-using-a-15-sample-in-all-databases-in-a-plan-also-shrink-any-of-the-database-that-have-reached-110-mb-to-having-only-10-free-space"></a><span data-ttu-id="a391c-263">B.</span><span class="sxs-lookup"><span data-stu-id="a391c-263">B.</span></span> <span data-ttu-id="a391c-264">Actualizar estadísticas mediante una muestra del 15% en todas las bases de datos de un plan.</span><span class="sxs-lookup"><span data-stu-id="a391c-264">Updating statistics using a 15% sample in all databases in a plan.</span></span> <span data-ttu-id="a391c-265">Además, reducir todas las bases de datos que hayan alcanzado los 110 MB para que tengan solo el 10 % de espacio disponible</span><span class="sxs-lookup"><span data-stu-id="a391c-265">Also, shrink any of the database that have reached 110 MB to having only 10% free space</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -UpdOptiStats 15 -RmUnusedSpace 110 10  
```  
  
### <a name="c-backing-up-all-the-databases-in-a-plan-to-their-individual-subdirectories-in-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory-also-delete-any-backups-older-than-2-weeks"></a><span data-ttu-id="a391c-266">C.</span><span class="sxs-lookup"><span data-stu-id="a391c-266">C.</span></span> <span data-ttu-id="a391c-267">Realizar una copia de seguridad de todas las bases de datos de un plan en los subdirectorios individuales del directorio predeterminado x:\Archivos de programa\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup.</span><span class="sxs-lookup"><span data-stu-id="a391c-267">Backing up all the databases in a plan to their individual subdirectories in the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span> <span data-ttu-id="a391c-268">Además, eliminar las copias de seguridad con una antigüedad superior a 2 semanas</span><span class="sxs-lookup"><span data-stu-id="a391c-268">Also, delete any backups older than 2 weeks</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -BkUpDB -BkUpMedia DISK -UseDefDir -CrBkSubDir -DelBkUps 2weeks  
```  
  
### <a name="d-backing-up-a-database-to-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory"></a><span data-ttu-id="a391c-269">D.</span><span class="sxs-lookup"><span data-stu-id="a391c-269">D.</span></span> <span data-ttu-id="a391c-270">Copia de seguridad de una base de datos en el valor predeterminado X:\Archivos de Programa\microsoft SQL Server\MSSQL12. Directorio MSSQLSERVER\MSSQL\Backup. </span><span class="sxs-lookup"><span data-stu-id="a391c-270">Backing up a database to the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span>\  
  
```  
sqlmaint -S MyServer -BkUpDB -BkUpMedia DISK -UseDefDir  
```  
  
## <a name="see-also"></a><span data-ttu-id="a391c-271">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a391c-271">See Also</span></span>  
 <span data-ttu-id="a391c-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a391c-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="a391c-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a391c-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
