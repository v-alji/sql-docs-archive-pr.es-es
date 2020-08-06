---
title: Exportar una aplicación de capa de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportdac.settings.f1
- sql12.swb. exportdac.settings.f1
- sql12.swb.exportdac.welcome.f1
- sql12.swb. exportdac.summary.f1
- sql12.swb.exportdac.progress.f1
- sql12.swb.exportdac.summary.f1
- sql12.swb.exportdac.results.f1
- sql12.swb. exportdac.results.f1
helpviewer_keywords:
- How to [DAC], export
- wizard [DAC], export
- export DAC
- data-tier application [SQL Server], export
ms.assetid: 61915bc5-0f5f-45ac-8cfe-3452bc185558
author: stevestein
ms.author: sstein
ms.openlocfilehash: d5e1bbfc5c38dee5e7f29598086d87b680880641
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675982"
---
# <a name="export-a-data-tier-application"></a><span data-ttu-id="7ecc5-102">Exportar una aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="7ecc5-102">Export a Data-tier Application</span></span>
  <span data-ttu-id="7ecc5-103">Al exportar una aplicación de capa de datos (DAC) o base de datos implementada se crea un archivo de exportación que incluye las definiciones de los objetos de la base de datos y todos los datos contenidos en las tablas.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-103">Exporting a deployed data-tier application (DAC) or database creates an export file that includes both the definitions of the objects in the database and all of the data contained in the tables.</span></span> <span data-ttu-id="7ecc5-104">El archivo de exportación se podrá importar a otra instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)]o a [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ecc5-104">The export file can then be imported to another instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="7ecc5-105">Las operaciones de exportación-importación se pueden combinar para migrar una DAC de una instancia a otra, crear una copia de seguridad lógica o crear una copia local de una base de datos implementada en [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ecc5-105">The export-import operations can be combined to migrate a DAC between instances, to create a logical backup, or to create an on-premise copy of a database deployed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="7ecc5-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="7ecc5-106">Before You Begin</span></span>  
 <span data-ttu-id="7ecc5-107">El proceso de exportación compila un archivo de exportación DAC en dos fases.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-107">The export process builds a DAC export file in two stages.</span></span>  
  
1.  <span data-ttu-id="7ecc5-108">La exportación genera una definición de DAC en el archivo de exportación (archivo BACPAC) de la misma forma que una extracción de DAC genera una definición de DAC en un archivo de paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-108">The export builds a DAC definition in the export file - BACPAC file - in the same way a DAC extract builds a DAC definition in a DAC package file.</span></span> <span data-ttu-id="7ecc5-109">La definición de DAC exportada incluye todos los objetos de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-109">The exported DAC definition includes all of the objects in the current database.</span></span> <span data-ttu-id="7ecc5-110">Si el proceso de exportación se ejecuta en una base de datos que se implementó originalmente a partir de una DAC y se realizaron cambios directamente en la base de datos tras la implementación, la definición exportada coincide con el objeto establecido en la base de datos, no con lo definido en la DAC original.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-110">If the export process is run against a database that was originally deployed from a DAC, and changes were made directly to the database after deployment, the exported definition matches the object set in the database, not what was defined in the original DAC.</span></span>  
  
2.  <span data-ttu-id="7ecc5-111">La exportación masiva copia los datos de todas las tablas de la base de datos y los incorpora en el archivo de exportación.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-111">The export bulk copies out the data from all of the tables in the database and incorporates the data into the export file.</span></span>  
  
 <span data-ttu-id="7ecc5-112">El proceso de exportación establece la versión de DAC en 1.0.0.0 y la descripción de DAC en el archivo de exportación en una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-112">The export process sets the DAC version to 1.0.0.0 and the DAC description in the export file to an empty string.</span></span> <span data-ttu-id="7ecc5-113">Si la base de datos se implementó a partir de una DAC, la definición de DAC del archivo de exportación contiene el nombre asignado a DAC original; de lo contrario, el nombre de la DAC se establece el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-113">If the database was deployed from a DAC, the DAC definition in the export file contains the name given to the original DAC, otherwise the DAC name is set to the database name.</span></span>  
  

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="7ecc5-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7ecc5-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7ecc5-115">Una DAC o base de datos solo se puede extraer de una base de datos de [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o posterior.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-115">A DAC or database can only be exported from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
 <span data-ttu-id="7ecc5-116">No puede exportar una base de datos que tenga objetos que no se admiten en una DAC, o usuarios contenidos.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-116">You cannot export a database that has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="7ecc5-117">Para obtener más información acerca de los objetos admitidos por una DAC, vea [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="7ecc5-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7ecc5-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="7ecc5-118">Permissions</span></span>  
 <span data-ttu-id="7ecc5-119">La exportación de una DAC requiere al menos permisos ALTER ANY LOGIN y VIEW DEFINITION en el ámbito de la base de datos, así como permisos SELECT en **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-119">Exporting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="7ecc5-120">La exportación de una DAC la pueden realizar los miembros del rol fijo de servidor securityadmin que sean también miembros del rol fijo de base de datos database_owner en la base de datos de la que se exporta la DAC.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-120">Exporting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is exported.</span></span> <span data-ttu-id="7ecc5-121">Los miembros del rol fijo de servidor sysadmin o de la cuenta de administrador del sistema de SQL Server integrada denominada **sa** también pueden exportar una DAC.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also export a DAC.</span></span>  
  
##  <a name="using-the-export-data-tier-application-wizard"></a><a name="UsingDeployDACWizard"></a><span data-ttu-id="7ecc5-122">Usar el asistente exportar aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="7ecc5-122">Using the Export Data-tier Application Wizard</span></span>  
 <span data-ttu-id="7ecc5-123">**Para exportar una DAC mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="7ecc5-123">**To Export a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="7ecc5-124">Conéctese con la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ya sea local o en [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ecc5-124">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], whether on-premise or in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
2.  <span data-ttu-id="7ecc5-125">En el **Explorador de objetos**, expanda el nodo para la instancia de la que dese exportar la DAC.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-125">In **Object Explorer**, expand the node for the instance from which you want to export the DAC.</span></span>  
  
3.  <span data-ttu-id="7ecc5-126">Haga clic con el botón secundario en el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-126">Right-click the database name.</span></span>  
  
4.  <span data-ttu-id="7ecc5-127">Haga clic en **Tareas** y después seleccione **Exportar aplicación de capa de datos...**.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-127">Click **Tasks** and then select **Export Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="7ecc5-128">Complete los cuadros de diálogo del asistente:</span><span class="sxs-lookup"><span data-stu-id="7ecc5-128">Complete the wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="7ecc5-129">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="7ecc5-129">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="7ecc5-130">Página Exportar configuraciones</span><span class="sxs-lookup"><span data-stu-id="7ecc5-130">Export Settings Page</span></span>](#Export_settings)  
  
    -   [<span data-ttu-id="7ecc5-131">Página Validación</span><span class="sxs-lookup"><span data-stu-id="7ecc5-131">Validation Page</span></span>](#Validation)  
  
    -   [<span data-ttu-id="7ecc5-132">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="7ecc5-132">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="7ecc5-133">Página progreso</span><span class="sxs-lookup"><span data-stu-id="7ecc5-133">Progress Page</span></span>](#Progress)  
  
    -   [<span data-ttu-id="7ecc5-134">Página Resultados</span><span class="sxs-lookup"><span data-stu-id="7ecc5-134">Results Page</span></span>](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="7ecc5-135">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="7ecc5-135">Introduction Page</span></span>  
 <span data-ttu-id="7ecc5-136">Esta página describe los pasos para el Asistente Exportar aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-136">This page describes the steps for the Export Data-tier Application Wizard.</span></span>  
  
 <span data-ttu-id="7ecc5-137">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="7ecc5-137">**Options**</span></span>  
  
 <span data-ttu-id="7ecc5-138">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="7ecc5-138">**Do not show this page again.**</span></span> <span data-ttu-id="7ecc5-139">- Active la casilla para que la página Introducción deje de mostrarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-139">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="7ecc5-140">**Siguiente** : avanza a la página **Seleccionar paquete DAC** .</span><span class="sxs-lookup"><span data-stu-id="7ecc5-140">**Next** - Proceeds to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="7ecc5-141">**Cancelar** : cancela la operación y cierra el asistente.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-141">**Cancel** - Cancels the operation and closes the Wizard.</span></span>  
  
##  <a name="export-settings-page"></a><a name="Export_settings"></a><span data-ttu-id="7ecc5-142">Página exportar configuración</span><span class="sxs-lookup"><span data-stu-id="7ecc5-142">Export Settings Page</span></span>  
 <span data-ttu-id="7ecc5-143">En esta página se puede especificar la ubicación donde se desea crear el archivo BACPAC.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-143">Use this page to specify the location where you want the BACPAC file to be created.</span></span>  
  
-   <span data-ttu-id="7ecc5-144">**Guardar en disco local** : crea un archivo BACPAC en un directorio del equipo local.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-144">**Save to local disk** - Creates a BACPAC file in a directory on the local computer.</span></span> <span data-ttu-id="7ecc5-145">Haga clic en **Examinar...** para navegar por el equipo local, o bien especifique la ruta de acceso en el espacio proporcionado.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-145">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span> <span data-ttu-id="7ecc5-146">El nombre de ruta de acceso debe incluir un nombre de archivo y la extensión .bacpac.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-146">The path name must include a file name and the .bacpac extension.</span></span>  
  
-   <span data-ttu-id="7ecc5-147">**Guardar en Azure**: crea un archivo BACPAC en un contenedor de Azure.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-147">**Save to Azure** - Creates a BACPAC file in an Azure container.</span></span> <span data-ttu-id="7ecc5-148">Debe conectarse a un contenedor de Azure para validar esta opción.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-148">You must connect to an Azure container in order to validate this option.</span></span> <span data-ttu-id="7ecc5-149">Observe que esta opción también requiere que se especifique un directorio local para el archivo temporal.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-149">Note that this option also requires that you specify a local directory for the temporary file.</span></span> <span data-ttu-id="7ecc5-150">Tenga en cuenta que el archivo temporal se creará en la ubicación especificada y permanecerá en ella una vez completada la operación.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-150">Note that the temporary file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
 <span data-ttu-id="7ecc5-151">Para especificar un subconjunto de tablas para exportar, utilice la opción **Avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="7ecc5-151">To specify a subset of tables to export, use the **Advanced** option.</span></span>  
  
##  <a name="validation-page"></a><a name="Validation"></a><span data-ttu-id="7ecc5-152">Página validación</span><span class="sxs-lookup"><span data-stu-id="7ecc5-152">Validation Page</span></span>  
 <span data-ttu-id="7ecc5-153">La página de validación se utiliza para revisar los problemas que bloquean la operación.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-153">Use the validation page to review any issues that block the operation.</span></span> <span data-ttu-id="7ecc5-154">Para continuar, resuelva los problemas de bloqueo y, después, haga clic en **Volver a ejecutar la validación** para asegurarse de que la validación es correcta.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-154">To continue, resolve blocking issues and then click **Re-run Validation** to ensure that validation is successful.</span></span>  
  
 <span data-ttu-id="7ecc5-155">Para continuar, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-155">To continue, click **Next**.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="7ecc5-156">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="7ecc5-156">Summary Page</span></span>  
 <span data-ttu-id="7ecc5-157">Esta página se utiliza para revisar los valores de origen y de destino especificados de la operación.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-157">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="7ecc5-158">Para completar la operación de exportación mediante los valores especificados, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-158">To complete the export operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="7ecc5-159">Para cancelar la operación de exportación y salir del asistente, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-159">To cancel the export operation and exit the Wizard, click **Cancel**.</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="7ecc5-160">Página Progreso</span><span class="sxs-lookup"><span data-stu-id="7ecc5-160">Progress Page</span></span>  
 <span data-ttu-id="7ecc5-161">En esta página se muestra una barra de progreso que indica el estado de la operación.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-161">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="7ecc5-162">Para ver el estado detallado, haga clic en la opción **Ver detalles** .</span><span class="sxs-lookup"><span data-stu-id="7ecc5-162">To view detailed status, click the **View details** option.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="7ecc5-163">Página resultados</span><span class="sxs-lookup"><span data-stu-id="7ecc5-163">Results Page</span></span>  
 <span data-ttu-id="7ecc5-164">En esta página se notifica la corrección o el error de la operación de exportación, mostrando los resultados de cada acción.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-164">This page reports the success or failure of the export operation, showing the results of each action.</span></span> <span data-ttu-id="7ecc5-165">Cualquier acción que encontrara un error tendrá un vínculo en la columna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="7ecc5-165">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="7ecc5-166">Haga clic en el vínculo para ver un informe del error para esa acción.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-166">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="7ecc5-167">Haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-167">Click **Finish** to close the Wizard.</span></span>  
  
##  <a name="using-a-net-framework-application"></a><a name="NetApp"></a><span data-ttu-id="7ecc5-168">Usar una aplicación de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7ecc5-168">Using a .Net Framework Application</span></span>  
 <span data-ttu-id="7ecc5-169">**Para exportar una DAC mediante el método Export() en una aplicación .Net Framework**</span><span class="sxs-lookup"><span data-stu-id="7ecc5-169">**To export a DAC using the Export() method in a .Net Framework application.**</span></span>  
  
 <span data-ttu-id="7ecc5-170">Para obtener un ejemplo de código, descargue la aplicación de ejemplo de DAC en [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575).</span><span class="sxs-lookup"><span data-stu-id="7ecc5-170">To view a code example, download the DAC sample application on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span></span>  
  
1.  <span data-ttu-id="7ecc5-171">Cree un objeto SMO Server y establézcalo en la instancia que contiene la DAC que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-171">Create a SMO Server object and set it to the instance that contains the DAC to be exported.</span></span>  
  
2.  <span data-ttu-id="7ecc5-172">Abra un objeto `ServerConnection` y conéctese a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-172">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="7ecc5-173">Use el método de `Export` de tipo `Microsoft.SqlServer.Management.Dac.DacStore` para exportar la DAC.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-173">Use the `Export` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to export the DAC.</span></span> <span data-ttu-id="7ecc5-174">Especifique el nombre de la DAC que se exportará y la ruta de acceso a la carpeta donde se va a guardar el archivo de exportación.</span><span class="sxs-lookup"><span data-stu-id="7ecc5-174">Specify the name of the DAC to be exported, and the path to the folder where the export file is to be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ecc5-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ecc5-175">See Also</span></span>  
 <span data-ttu-id="7ecc5-176">[Aplicaciones de capa de datos](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="7ecc5-176">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="7ecc5-177">Extraer una DAC de una base de datos</span><span class="sxs-lookup"><span data-stu-id="7ecc5-177">Extract a DAC From a Database</span></span>](extract-a-dac-from-a-database.md)  
  
  
