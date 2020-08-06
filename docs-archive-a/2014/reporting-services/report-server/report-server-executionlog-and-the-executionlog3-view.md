---
title: Registro de ejecución del servidor de informes y vista ExecutionLog3 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- logs [Reporting Services], execution
- execution logs [Reporting Services]
ms.assetid: a7ead67d-1404-4e67-97e7-4c7b0d942070
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 868f8497e61c17662cb621850cdb8aee74c82706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670297"
---
# <a name="report-server-execution-log-and-the-executionlog3-view"></a><span data-ttu-id="cfbdc-102">Registro de ejecución del servidor de informes y la vista ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="cfbdc-102">Report Server Execution Log and the ExecutionLog3 View</span></span>
  <span data-ttu-id="cfbdc-103">El registro de la ejecución del servidor de informes contiene información sobre los informes que se ejecutan en el servidor o en varios servidores de una implementación escalada en modo nativo o de una granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-103">The report server execution log contains information about the reports that execute on the server or on multiple servers in a native mode scale-out deployment or a SharePoint farm.</span></span> <span data-ttu-id="cfbdc-104">Puede usar el registro de la ejecución de informes para averiguar con qué frecuencia se solicita el informe, qué formatos de salida se usan más y cuántos milisegundos del tiempo de procesamiento se dedica a cada fase del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-104">You can use the report execution log to find out how often a report is requested, what output formats are used the most, and how many milliseconds of processing time is spent on each processing phase.</span></span> <span data-ttu-id="cfbdc-105">El registro contiene información sobre el tiempo de ejecución de la consulta de conjunto de datos de un informe y el tiempo empleado en el procesamiento de los datos.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-105">The log contains information on the length of time spent executing a report's dataset query and the time spent processing the data.</span></span> <span data-ttu-id="cfbdc-106">Si es administrador del servidor de informes, puede revisar la información del registro e identificar las tareas de ejecución prolongada, y realizar sugerencias a los autores de informes en las áreas del informe (conjunto de datos o procesamiento) que se puedan mejorar.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-106">If you are a report server administrator, you can review the log information and identify long running tasks and make suggestions to the report authors on the areas of the report (dataset or processing) they may be able to improve.</span></span>  
  
 <span data-ttu-id="cfbdc-107">Los servidores de informes configurados para el modo de SharePoint, también pueden usar los registros de ULS de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-107">Report servers configured for SharePoint mode, can also utilize the SharePoint ULS logs.</span></span> <span data-ttu-id="cfbdc-108">Para obtener más información, vea [Activar eventos de Reporting Services para el registro de seguimiento de SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-108">For more information, see [Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span></span>  
  
##  <a name="viewing-log-information"></a><a name="bkmk_top"></a> <span data-ttu-id="cfbdc-109">Ver la información del registro</span><span class="sxs-lookup"><span data-stu-id="cfbdc-109">Viewing Log Information</span></span>  
 <span data-ttu-id="cfbdc-110">La ejecución del servidor de informes registra datos sobre la ejecución de informes en una tabla interna de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-110">The report server execution logs data about report execution into an internal database table.</span></span> <span data-ttu-id="cfbdc-111">La información de la tabla está disponible en las vistas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-111">The information from the table is available from SQL Server views.</span></span>  
  
 <span data-ttu-id="cfbdc-112">El registro de la ejecución de informes se almacena en la base de datos del servidor de informes que se denomina **ReportServer**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-112">The report execution log is stored in the report server database that by default is named **ReportServer**.</span></span> <span data-ttu-id="cfbdc-113">Las vistas de SQL proporcionan la información del registro de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-113">The SQL views provide the execution log information.</span></span> <span data-ttu-id="cfbdc-114">Las vistas "2" y "3" se agregaron en versiones más recientes y contienen campos nuevos o campos con nombres más descriptivos que las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-114">The "2" and "3" views were added in more recent releases and contain new fields or they contain fields with friendlier names than the previous releases.</span></span> <span data-ttu-id="cfbdc-115">Permanece en el producto las vistas antiguas para que no se vean afectadas las aplicaciones personalizadas que dependen de ellas.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-115">The older views remain in the product so custom applications that depend on them are not impacted.</span></span> <span data-ttu-id="cfbdc-116">Si no tiene una dependencia en una vista anterior, por ejemplo ExecutionLog, se recomienda utilizar la vista más reciente, ExecutionLog**3**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-116">If you do not have a dependence on an older view, for example ExecutionLog, it is recommended you use the most recent view, ExecutionLog**3**.</span></span>  
  
 <span data-ttu-id="cfbdc-117">En este tema:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-117">In this topic:</span></span>  
  
-   [<span data-ttu-id="cfbdc-118">Configuración para un servidor de informes en modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfbdc-118">Configuration Settings for a SharePoint mode Report Server</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="cfbdc-119">Configuración de un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="cfbdc-119">Configuration Settings for a Native Mode Report Server</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="cfbdc-120">Campos de registro (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-120">Log Fields (ExecutionLog3)</span></span>](#bkmk_executionlog3)  
  
-   [<span data-ttu-id="cfbdc-121">El campo AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="cfbdc-121">The AdditionalInfo Field</span></span>](#bkmk_additionalinfo)  
  
-   [<span data-ttu-id="cfbdc-122">Campos de registro (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-122">Log Fields (ExecutionLog2)</span></span>](#bkmk_executionlog2)  
  
-   [<span data-ttu-id="cfbdc-123">Campos de registro (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-123">Log Fields (ExecutionLog)</span></span>](#bkmk_executionlog)  
  
##  <a name="configuration-settings-for-a-sharepoint-mode-report-server"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="cfbdc-124">Configuración para un servidor de informes en modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfbdc-124">Configuration Settings for a SharePoint mode Report Server</span></span>  
 <span data-ttu-id="cfbdc-125">Puede activar o desactivar la ejecución de informes en la configuración del sistema de una aplicación de servicios de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-125">You can turn report execution logging on or off from the system settings of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
 <span data-ttu-id="cfbdc-126">De forma predeterminada, las entradas de registro se mantienen 60 días.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-126">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="cfbdc-127">Las entradas que superan esta fecha se quitan a las 2:00 a. m.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-127">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="cfbdc-128">todos los días.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-128">every day.</span></span> <span data-ttu-id="cfbdc-129">En instalaciones antiguas, solo habrá 60 días de información disponibles en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-129">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="cfbdc-130">No puede establecer límites en el número de filas o en el tipo de entradas que se registran.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-130">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="cfbdc-131">**Para habilitar el registro de la ejecución:**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-131">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="cfbdc-132">En Administración central de SharePoint, haga clic en **Administrar aplicaciones de servicio** en el grupo **Administración de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-132">From SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="cfbdc-133">Haga clic en el nombre de la aplicación de servicio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que desee configurar.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-133">Click the name of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application you want to configure.</span></span>  
  
3.  <span data-ttu-id="cfbdc-134">Haga clic en **Configuración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-134">Click **System Settings**.</span></span>  
  
4.  <span data-ttu-id="cfbdc-135">Seleccione **Habilitar el registro de la ejecución** en la sección **Registro** .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-135">Select **Enable Execution Logging** in the **Logging** section.</span></span>  
  
5.  <span data-ttu-id="cfbdc-136">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-136">Click **OK**.</span></span>  
  
 <span data-ttu-id="cfbdc-137">**Para habilitar el registro detallado:**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-137">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="cfbdc-138">Debe habilitar el registro como se describe en los pasos anteriores y, a continuación, realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-138">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="cfbdc-139">En la página **Configuración del sistema** de la aplicación de servicios de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , busque la sección **Definido por el usuario** .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-139">From the **System Settings** page of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] services application, find the **User-defined** section.</span></span>  
  
2.  <span data-ttu-id="cfbdc-140">Cambie **ExecutionLogLevel** a **detallado**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-140">Change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="cfbdc-141">Este campo es un campo de entrada de texto y los dos valores posibles son **detallado** y **normal**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-141">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="configuration-settings-for-a-native-mode-report-server"></a><a name="bkmk_native"></a> <span data-ttu-id="cfbdc-142">Configuración de un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="cfbdc-142">Configuration Settings for a Native Mode Report Server</span></span>  
 <span data-ttu-id="cfbdc-143">Puede activar o desactivar la ejecución de informes en la página propiedades del servidor en SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-143">You can turn report execution logging on or off from the Server Properties page in SQL Server Management Studio.</span></span> <span data-ttu-id="cfbdc-144">**EnableExecutionLogging** es una propiedad avanzada.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-144">The **EnableExecutionLogging** is and Advanced property.</span></span>  
  
 <span data-ttu-id="cfbdc-145">De forma predeterminada, las entradas de registro se mantienen 60 días.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-145">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="cfbdc-146">Las entradas que superan esta fecha se quitan a las 2:00 a. m.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-146">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="cfbdc-147">todos los días.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-147">every day.</span></span> <span data-ttu-id="cfbdc-148">En instalaciones antiguas, solo habrá 60 días de información disponibles en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-148">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="cfbdc-149">No puede establecer límites en el número de filas o en el tipo de entradas que se registran.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-149">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="cfbdc-150">**Para habilitar el registro de la ejecución:**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-150">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="cfbdc-151">Inicie SQL Server Management Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-151">Start SQL Server Management Studio with administrative privileges.</span></span> <span data-ttu-id="cfbdc-152">Por ejemplo, haga clic con el botón derecho en el icono de Management Studio y seleccione "Ejecutar como administrador".</span><span class="sxs-lookup"><span data-stu-id="cfbdc-152">For example right-click the Management Studio icon and click 'Run as administrator'.</span></span>  
  
2.  <span data-ttu-id="cfbdc-153">Conéctese al servidor de informes que desee.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-153">Connect to the desired report server.</span></span>  
  
3.  <span data-ttu-id="cfbdc-154">Haga clic con el botón derecho en el nombre del servidor y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-154">Right-click the server name and click **Properties**.</span></span> <span data-ttu-id="cfbdc-155">Si la opción Propiedades está deshabilitada, compruebe que ha ejecutado SQL Server Management Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-155">If the Properties option is disabled, verify you ran SQL Server Management Studio with administrative privileges.</span></span>  
  
4.  <span data-ttu-id="cfbdc-156">Haga clic en la página **Registro** .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-156">Click the **Logging** page.</span></span>  
  
5.  <span data-ttu-id="cfbdc-157">Seleccione **Habilitar el registro de la ejecución de informes**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-157">Select **Enable report execution Logging**.</span></span>  
  
 <span data-ttu-id="cfbdc-158">**Para habilitar el registro detallado:**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-158">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="cfbdc-159">Debe habilitar el registro como se describe en los pasos anteriores y, a continuación, realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-159">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="cfbdc-160">En el cuadro de diálogo **Propiedades de servidor** , haga clic en la página **Avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-160">From the **Server Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="cfbdc-161">En la sección **Definido por el usuario** , cambie **ExecutionLogLevel** a **detallado**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-161">In the **User-defined** section, change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="cfbdc-162">Este campo es un campo de entrada de texto y los dos valores posibles son **detallado** y **normal**.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-162">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="log-fields-executionlog3"></a><a name="bkmk_executionlog3"></a> <span data-ttu-id="cfbdc-163">Campos de registro (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-163">Log Fields (ExecutionLog3)</span></span>  
 <span data-ttu-id="cfbdc-164">En esta vista, se agregaron nodos de diagnóstico adicionales en la columna **AdditionalInfo** basada en XML.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-164">This view added additional performance diagnostics node inside the XML based **AdditionalInfo** column.</span></span> <span data-ttu-id="cfbdc-165">La columna AdditionalInfo contiene una estructura XML de 1 a muchos campos adicionales de información.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-165">The AdditionalInfo column contains an XML structure of 1 to many additional fields of information.</span></span> <span data-ttu-id="cfbdc-166">La siguiente es una instrucción Transact-SQL de ejemplo para recuperar filas de la vista ExecutionLog3.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-166">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog3.</span></span> <span data-ttu-id="cfbdc-167">En el ejemplo se supone que la base de datos del servidor de informes se denomina **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-167">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog3 order by TimeStart DESC  
```  
  
 <span data-ttu-id="cfbdc-168">La siguiente tabla describe los datos que se capturan en el registro de ejecución de informes</span><span class="sxs-lookup"><span data-stu-id="cfbdc-168">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="cfbdc-169">Columna</span><span class="sxs-lookup"><span data-stu-id="cfbdc-169">Column</span></span>|<span data-ttu-id="cfbdc-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfbdc-170">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cfbdc-171">InstanceName</span><span class="sxs-lookup"><span data-stu-id="cfbdc-171">InstanceName</span></span>|<span data-ttu-id="cfbdc-172">Nombre de la instancia de servidor de informes que procesó la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-172">Name of the report server instance that handled the request.</span></span> <span data-ttu-id="cfbdc-173">Si el entorno tiene más de un servidor de informes, puede analizar la distribución de InstanceName para supervisar y determinar si el equilibrador de carga de red distribuye las solicitudes entre los servidores de informes como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-173">If your environment has more than one report server, you can analyze the InstanceName distribution to monitor and determine if your network-load balancer distributes requests across report servers as expected.</span></span>|  
|<span data-ttu-id="cfbdc-174">ItemPath</span><span class="sxs-lookup"><span data-stu-id="cfbdc-174">ItemPath</span></span>|<span data-ttu-id="cfbdc-175">Ruta de acceso donde se almacena un informe o un elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-175">Path of where a report or report item is stored.</span></span>|  
|<span data-ttu-id="cfbdc-176">UserName</span><span class="sxs-lookup"><span data-stu-id="cfbdc-176">UserName</span></span>|<span data-ttu-id="cfbdc-177">Identificador del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-177">User identifier.</span></span>|  
|<span data-ttu-id="cfbdc-178">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="cfbdc-178">ExecutionID</span></span>|<span data-ttu-id="cfbdc-179">Identificador interno asociado a una solicitud.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-179">The internal identifier associated with a request.</span></span> <span data-ttu-id="cfbdc-180">Las solicitudes en las mismas sesiones de usuario comparten el mismo identificador de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-180">Requests on the same user sessions share the same execution id.</span></span>|  
|<span data-ttu-id="cfbdc-181">RequestType</span><span class="sxs-lookup"><span data-stu-id="cfbdc-181">RequestType</span></span>|<span data-ttu-id="cfbdc-182">Valores posibles:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-182">Possible Values:</span></span><br /><span data-ttu-id="cfbdc-183">**Interactivo**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-183">**Interactive**</span></span><br /><span data-ttu-id="cfbdc-184">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-184">**Subscription**</span></span><br /><br /> <br /><br /> <span data-ttu-id="cfbdc-185">El análisis de los datos de registro filtrados por RequestType=Subscription y ordenados por TimeStart pueden revelar los periodos de mucho uso de suscripciones y puede indicar la conveniencia de modificar algunas de las suscripciones de informe a un momento diferente.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-185">Analyzing log data filtered by RequestType=Subscription and sorted by TimeStart may reveal periods of heavy subscription usage and you may want to modify some of the report subscriptions to a different time.</span></span>|  
|<span data-ttu-id="cfbdc-186">Formato</span><span class="sxs-lookup"><span data-stu-id="cfbdc-186">Format</span></span>|<span data-ttu-id="cfbdc-187">Formato de representación.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-187">Rendering format.</span></span>|  
|<span data-ttu-id="cfbdc-188">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfbdc-188">Parameters</span></span>|<span data-ttu-id="cfbdc-189">Valores de parámetros utilizados para la ejecución de un informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-189">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="cfbdc-190">ItemAction</span><span class="sxs-lookup"><span data-stu-id="cfbdc-190">ItemAction</span></span>|<span data-ttu-id="cfbdc-191">Valores posibles:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-191">Possible values:</span></span><br /><br /> <span data-ttu-id="cfbdc-192">**Representar**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-192">**Render**</span></span><br /><br /> <span data-ttu-id="cfbdc-193">**Sort**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-193">**Sort**</span></span><br /><br /> <span data-ttu-id="cfbdc-194">**BookMarkNavigation**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-194">**BookMarkNavigation**</span></span><br /><br /> <span data-ttu-id="cfbdc-195">**DocumentNavigation**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-195">**DocumentNavigation**</span></span><br /><br /> <span data-ttu-id="cfbdc-196">**GetDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-196">**GetDocumentMap**</span></span><br /><br /> <span data-ttu-id="cfbdc-197">**FindString**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-197">**Findstring**</span></span><br /><br /> <span data-ttu-id="cfbdc-198">**Ejecut**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-198">**Execute**</span></span><br /><br /> <span data-ttu-id="cfbdc-199">**RenderEdit**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-199">**RenderEdit**</span></span>|  
|<span data-ttu-id="cfbdc-200">TimeStart</span><span class="sxs-lookup"><span data-stu-id="cfbdc-200">TimeStart</span></span>|<span data-ttu-id="cfbdc-201">Horas de inicio y detención que indican la duración del procesamiento de un informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-201">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="cfbdc-202">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="cfbdc-202">TimeEnd</span></span>||  
|<span data-ttu-id="cfbdc-203">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="cfbdc-203">TimeDataRetrieval</span></span>|<span data-ttu-id="cfbdc-204">Número de milisegundos empleados en recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-204">Number of milliseconds spent retrieving the data.</span></span>|  
|<span data-ttu-id="cfbdc-205">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="cfbdc-205">TimeProcessing</span></span>|<span data-ttu-id="cfbdc-206">Número de milisegundos empleados en procesar el informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-206">Number of milliseconds spent processing the report.</span></span>|  
|<span data-ttu-id="cfbdc-207">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="cfbdc-207">TimeRendering</span></span>|<span data-ttu-id="cfbdc-208">Número de milisegundos empleados en representar el informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-208">Number of milliseconds spent rendering the report.</span></span>|  
|<span data-ttu-id="cfbdc-209">Source</span><span class="sxs-lookup"><span data-stu-id="cfbdc-209">Source</span></span>|<span data-ttu-id="cfbdc-210">Origen de la ejecución del informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-210">Source of the report execution.</span></span> <span data-ttu-id="cfbdc-211">Valores posibles:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-211">Possible values:</span></span><br /><br /> <span data-ttu-id="cfbdc-212">**Directo**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-212">**Live**</span></span><br /><br /> <span data-ttu-id="cfbdc-213">**Cache**: indica una ejecución almacenada en caché; por ejemplo, no se ejecutan consultas de conjunto de los conjuntos de los mismos.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-213">**Cache**: Indicates a cached execution, for example, dataset queries are not executed live.</span></span><br /><br /> <span data-ttu-id="cfbdc-214">**Instantánea**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-214">**Snapshot**</span></span><br /><br /> <span data-ttu-id="cfbdc-215">**Historial**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-215">**History**</span></span><br /><br /> <span data-ttu-id="cfbdc-216">**Adhoc** : indica un informe detallado basado en un modelo de informe generado dinámicamente, o un informe generador de informes que se muestra como vista previa en un cliente mediante el servidor de informes para su procesamiento y representación.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-216">**AdHoc** : Indicates either a dynamically generated report model based drill through report, or a Report Builder report that is previewed on a client utilizing the report server for processing and rendering.</span></span><br /><br /> <span data-ttu-id="cfbdc-217">**Sesión**: indica una solicitud de seguimiento en una sesión ya establecida.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-217">**Session**: Indicates a follow up request within an already established session.</span></span>  <span data-ttu-id="cfbdc-218">Por ejemplo, la solicitud inicial es ver la página 1 y la solicitud de seguimiento es exportar a Excel con el estado actual de la sesión.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-218">For example the initial request is to view page 1, and the follow up request is to export to Excel with the current session state.</span></span><br /><br /> <span data-ttu-id="cfbdc-219">**Rdce**: indica una extensión de personalización de definición de informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-219">**Rdce**:  Indicates a Report Definition Customization Extension.</span></span> <span data-ttu-id="cfbdc-220">Las extensiones personalizadas de RDCE pueden personalizar dinámicamente una definición de informe antes de que se pase al motor de procesamiento en el momento de la ejecución de informes.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-220">An RDCE custom extension can dynamically customize a report definition before it is passed to the processing engine upon report execution.</span></span>|  
|<span data-ttu-id="cfbdc-221">Status</span><span class="sxs-lookup"><span data-stu-id="cfbdc-221">Status</span></span>|<span data-ttu-id="cfbdc-222">Estado (rsSuccess o un código de error; si se producen varios errores, solo se registra el primero).</span><span class="sxs-lookup"><span data-stu-id="cfbdc-222">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="cfbdc-223">ByteCount</span><span class="sxs-lookup"><span data-stu-id="cfbdc-223">ByteCount</span></span>|<span data-ttu-id="cfbdc-224">Tamaño de los informes representados en bytes</span><span class="sxs-lookup"><span data-stu-id="cfbdc-224">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="cfbdc-225">RowCount</span><span class="sxs-lookup"><span data-stu-id="cfbdc-225">RowCount</span></span>|<span data-ttu-id="cfbdc-226">Número de filas devueltas de consultas.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-226">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="cfbdc-227">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="cfbdc-227">AdditionalInfo</span></span>|<span data-ttu-id="cfbdc-228">Un contenedor de propiedades XML que incluye información adicional sobre la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-228">An XML property bag containing additional information about the execution.</span></span> <span data-ttu-id="cfbdc-229">El contenido puede ser diferente para cada fila.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-229">The contents can be different for each row.</span></span>|  
  
##  <a name="the-additionalinfo-field"></a><a name="bkmk_additionalinfo"></a> <span data-ttu-id="cfbdc-230">El campo AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="cfbdc-230">The AdditionalInfo Field</span></span>  
 <span data-ttu-id="cfbdc-231">El campo AdditionalInfo es un contenedor de propiedades o estructura XML que incluye información adicional sobre la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-231">The AdditionalInfo field is an XML property bag or structure containing additional information about the execution.</span></span> <span data-ttu-id="cfbdc-232">El contenido puede ser diferente para cada fila del registro.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-232">The contents can be different for each row in the log.</span></span>  
  
 <span data-ttu-id="cfbdc-233">Las tablas siguientes son ejemplos de los contenidos del campo AddtionalInfo para el registro estándar y el registro detallado:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-233">The following tables are examples  of the contents of the AddtionalInfo field for both standard and verbose logging:</span></span>  
  
 <span data-ttu-id="cfbdc-234">**Ejemplo de registro estándar de AddtionalInfo**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-234">**Standard logging example of AddtionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>147</ConnectionOpenTime>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>642</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>63</ExecuteReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>157</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>60</ExecuteReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="cfbdc-235">**Ejemplo de registro detallado de AdditionalInfo**</span><span class="sxs-lookup"><span data-stu-id="cfbdc-235">**Verbose logging example of AdditionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>127</ConnectionOpenTime>  
      <DataSource>  
        <Name>DataSource1</Name>  
        <DataExtension>SQL</DataExtension>  
      </DataSource>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>33</ExecuteReaderTime>  
          <DataReaderMappingTime>30</DataReaderMappingTime>  
          <DisposeDataReaderTime>1</DisposeDataReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>1</ExecuteReaderTime>  
          <DataReaderMappingTime>0</DataReaderMappingTime>  
          <DisposeDataReaderTime>0</DisposeDataReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="cfbdc-236">A continuación se describen algunas de las propiedades que verá en el campo AdditionalInfo:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-236">The following describes some of the properties you will see in the AdditionalInfo field:</span></span>  
  
-   <span data-ttu-id="cfbdc-237">**ProcessingEngine**: 1 = SQL Server 2005, 2 = el nuevo motor de procesamiento a petición.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-237">**ProcessingEngine**: 1=SQL Server 2005, 2=The new On-demand Processing Engine.</span></span> <span data-ttu-id="cfbdc-238">Si una mayoría de los informes sigue mostrando el valor 1, puede investigar cómo reajustarlos para que usen el motor de procesamiento a petición más reciente y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-238">If a majority of your reports are still showing the value of 1, you may investigate how to redesign them so they utilize the newer and more efficient on-demand processing engine.</span></span>  
  
     `<ProcessingEngine>2</ProcessingEngine>`  
  
-   <span data-ttu-id="cfbdc-239">**ScalabilityTime**: el número de milisegundos empleados en realizar operaciones relacionadas con la escala en el motor de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-239">**ScalabilityTime**: The number of milliseconds spent performing scale related operations in the processing engine.</span></span> <span data-ttu-id="cfbdc-240">Un valor de 0 indica que no se empleó ningún tiempo adicional en las operaciones de escala y 0 también indica que la solicitud no estaba bajo presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-240">A value of 0 indicates that no additional time was spent on scale operations and a 0 also indicates the request was not under memory pressure.</span></span>  
  
    ```  
    <ScalabilityTime>  
        <Processing>0</Processing>  
    </ScalabilityTime>  
    ```  
  
-   <span data-ttu-id="cfbdc-241">**EstimatedMemoryUsageKB**: una estimación de la cantidad máxima de memoria, en kilobytes, consumida por cada componente durante una solicitud determinada.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-241">**EstimatedMemoryUsageKB**: An estimate of the peak amount of memory, in kilobytes, consumed by each component during a particular request.</span></span>  
  
    ```  
    <EstimatedMemoryUsageKB>  
        <Processing>38</Processing>  
    </EstimatedMemoryUsageKB>  
    ```  
  
-   <span data-ttu-id="cfbdc-242">**Extension**: los tipos de extensiones de datos u orígenes de datos usados en el informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-242">**DataExtension**: The types of data extensions or data sources used in the report.</span></span> <span data-ttu-id="cfbdc-243">El número es un recuento del número de repeticiones del origen de datos concreto.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-243">The number is a count of the number of occurrences of the particular data source.</span></span>  
  
    ```  
    <DataExtension>  
       <DAX>2</DAX>  
    </DataExtension>  
    ```  
  
-   <span data-ttu-id="cfbdc-244">**ExternalImages** El valor está en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-244">**ExternalImages**The value is in miliseconds.</span></span> <span data-ttu-id="cfbdc-245">Estos datos se pueden utilizar para diagnosticar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-245">This data can be used to diagnose performance issues.</span></span> <span data-ttu-id="cfbdc-246">El tiempo necesario para recuperar imágenes desde un servidor web externo puede ralentizar la ejecución de informes global.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-246">The time needed to retrieve images from an external webserver may slow the overall report execution.</span></span> <span data-ttu-id="cfbdc-247">Agregado en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-247">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <ExternalImages>  
        <Count>3</Count>  
        <ByteCount>9268</ByteCount>  
        <ResourceFetchTime>9</ResourceFetchTime>  
    </ExternalImages>  
    ```  
  
-   <span data-ttu-id="cfbdc-248">**Conexiones**: una estructura de varios niveles.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-248">**Connections**: A multi-leveled structure.</span></span> <span data-ttu-id="cfbdc-249">Agregado en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfbdc-249">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <Connections>  
        <Connection>  
          <ConnectionOpenTime>127</ConnectionOpenTime>  
          <DataSource>  
            <Name>DataSource1</Name>  
            <DataExtension>SQL</DataExtension>  
          </DataSource>  
          <DataSets>  
            <DataSet>  
              <Name>DataSet1</Name>  
              <RowsRead>16</RowsRead>  
              <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>33</ExecuteReaderTime>  
              <DataReaderMappingTime>30</DataReaderMappingTime>  
              <DisposeDataReaderTime>1</DisposeDataReaderTime>  
            </DataSet>  
            <DataSet>  
              <Name>DataSet2</Name>  
              <RowsRead>3</RowsRead>  
              <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>1</ExecuteReaderTime>  
              <DataReaderMappingTime>0</DataReaderMappingTime>  
              <DisposeDataReaderTime>0</DisposeDataReaderTime>  
            </DataSet>  
          </DataSets>  
        </Connection>  
    </Connections>  
  
    ```  
  
##  <a name="log-fields-executionlog2"></a><a name="bkmk_executionlog2"></a><span data-ttu-id="cfbdc-250">Campos de registro (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-250">Log Fields (ExecutionLog2)</span></span>  
 <span data-ttu-id="cfbdc-251">Esta vista ha agregado algunos campos nuevos y ha cambiado el nombre de otros.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-251">This view added a few new fields and renamed a few others.</span></span> <span data-ttu-id="cfbdc-252">La siguiente es una instrucción Transact-SQL de ejemplo para recuperar filas de la vista ExecutionLog2.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-252">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog2.</span></span> <span data-ttu-id="cfbdc-253">En el ejemplo se supone que la base de datos del servidor de informes se denomina **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-253">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog2 order by TimeStart DESC  
```  
  
 <span data-ttu-id="cfbdc-254">La siguiente tabla describe los datos que se capturan en el registro de ejecución de informes</span><span class="sxs-lookup"><span data-stu-id="cfbdc-254">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="cfbdc-255">Columna</span><span class="sxs-lookup"><span data-stu-id="cfbdc-255">Column</span></span>|<span data-ttu-id="cfbdc-256">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfbdc-256">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cfbdc-257">InstanceName</span><span class="sxs-lookup"><span data-stu-id="cfbdc-257">InstanceName</span></span>|<span data-ttu-id="cfbdc-258">Nombre de la instancia de servidor de informes que procesó la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-258">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="cfbdc-259">ReportPath</span><span class="sxs-lookup"><span data-stu-id="cfbdc-259">ReportPath</span></span>|<span data-ttu-id="cfbdc-260">La estructura de ruta de acceso al informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-260">The path structure to the report.</span></span>  <span data-ttu-id="cfbdc-261">Por ejemplo, un informe denominado "test" que está en la carpeta raíz en el Administrador de informes, tendría un ReportPath de "/test".</span><span class="sxs-lookup"><span data-stu-id="cfbdc-261">For example a report named "test" which is the in root folder in Report Manager, would have a ReportPath of "/test".</span></span><br /><br /> <span data-ttu-id="cfbdc-262">Un informe denominado "test" guardado en la carpeta "samples" en el Administrador de informes, tendrá un ReportPath de "/Samples/test/".</span><span class="sxs-lookup"><span data-stu-id="cfbdc-262">A report named "test" that is saved in the folder "samples" on Report Manager , will have a ReportPath of "/Samples/test/"</span></span>|  
|<span data-ttu-id="cfbdc-263">UserName</span><span class="sxs-lookup"><span data-stu-id="cfbdc-263">UserName</span></span>|<span data-ttu-id="cfbdc-264">Identificador del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-264">User identifier.</span></span>|  
|<span data-ttu-id="cfbdc-265">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="cfbdc-265">ExecutionID</span></span>||  
|<span data-ttu-id="cfbdc-266">RequestType</span><span class="sxs-lookup"><span data-stu-id="cfbdc-266">RequestType</span></span>|<span data-ttu-id="cfbdc-267">Tipo de solicitud (de usuario o del sistema).</span><span class="sxs-lookup"><span data-stu-id="cfbdc-267">Request type (either user or system).</span></span>|  
|<span data-ttu-id="cfbdc-268">Formato</span><span class="sxs-lookup"><span data-stu-id="cfbdc-268">Format</span></span>|<span data-ttu-id="cfbdc-269">Formato de representación.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-269">Rendering format.</span></span>|  
|<span data-ttu-id="cfbdc-270">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfbdc-270">Parameters</span></span>|<span data-ttu-id="cfbdc-271">Valores de parámetros utilizados para la ejecución de un informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-271">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="cfbdc-272">ReportAction</span><span class="sxs-lookup"><span data-stu-id="cfbdc-272">ReportAction</span></span>|<span data-ttu-id="cfbdc-273">Valores posibles: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span><span class="sxs-lookup"><span data-stu-id="cfbdc-273">Possible values: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span></span>|  
|<span data-ttu-id="cfbdc-274">TimeStart</span><span class="sxs-lookup"><span data-stu-id="cfbdc-274">TimeStart</span></span>|<span data-ttu-id="cfbdc-275">Horas de inicio y detención que indican la duración del procesamiento de un informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-275">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="cfbdc-276">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="cfbdc-276">TimeEnd</span></span>||  
|<span data-ttu-id="cfbdc-277">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="cfbdc-277">TimeDataRetrieval</span></span>|<span data-ttu-id="cfbdc-278">Número de milisegundos dedicados a recuperar los datos, procesar el informe y representarlo.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-278">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="cfbdc-279">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="cfbdc-279">TimeProcessing</span></span>||  
|<span data-ttu-id="cfbdc-280">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="cfbdc-280">TimeRendering</span></span>||  
|<span data-ttu-id="cfbdc-281">Source</span><span class="sxs-lookup"><span data-stu-id="cfbdc-281">Source</span></span>|<span data-ttu-id="cfbdc-282">Origen de la ejecución del informe (1=Activo, 2=Caché, 3=Instantánea, 4=Historial).</span><span class="sxs-lookup"><span data-stu-id="cfbdc-282">Source of the report execution (1=Live, 2=Cache, 3=Snapshot, 4=History).</span></span>|  
|<span data-ttu-id="cfbdc-283">Estado</span><span class="sxs-lookup"><span data-stu-id="cfbdc-283">Status</span></span>|<span data-ttu-id="cfbdc-284">Estado (rsSuccess o un código de error; si se producen varios errores, solo se registra el primero).</span><span class="sxs-lookup"><span data-stu-id="cfbdc-284">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="cfbdc-285">ByteCount</span><span class="sxs-lookup"><span data-stu-id="cfbdc-285">ByteCount</span></span>|<span data-ttu-id="cfbdc-286">Tamaño de los informes representados en bytes</span><span class="sxs-lookup"><span data-stu-id="cfbdc-286">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="cfbdc-287">RowCount</span><span class="sxs-lookup"><span data-stu-id="cfbdc-287">RowCount</span></span>|<span data-ttu-id="cfbdc-288">Número de filas devueltas de consultas.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-288">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="cfbdc-289">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="cfbdc-289">AdditionalInfo</span></span>|<span data-ttu-id="cfbdc-290">Un contenedor de propiedades XML que incluye información adicional sobre la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-290">An XML property bag containing additional information about the execution.</span></span>|  
  
##  <a name="log-fields-executionlog"></a><a name="bkmk_executionlog"></a><span data-ttu-id="cfbdc-291">Campos de registro (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-291">Log Fields (ExecutionLog)</span></span>  
 <span data-ttu-id="cfbdc-292">La siguiente es una instrucción Transact-SQL de ejemplo para recuperar filas de la vista ExecutionLog.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-292">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog.</span></span> <span data-ttu-id="cfbdc-293">En el ejemplo se supone que la base de datos del servidor de informes se denomina **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-293">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog order by TimeStart DESC  
  
```  
  
 <span data-ttu-id="cfbdc-294">La siguiente tabla describe los datos que se capturan en el registro de ejecución de informes</span><span class="sxs-lookup"><span data-stu-id="cfbdc-294">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="cfbdc-295">Columna</span><span class="sxs-lookup"><span data-stu-id="cfbdc-295">Column</span></span>|<span data-ttu-id="cfbdc-296">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfbdc-296">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cfbdc-297">InstanceName</span><span class="sxs-lookup"><span data-stu-id="cfbdc-297">InstanceName</span></span>|<span data-ttu-id="cfbdc-298">Nombre de la instancia de servidor de informes que procesó la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-298">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="cfbdc-299">ReportID</span><span class="sxs-lookup"><span data-stu-id="cfbdc-299">ReportID</span></span>|<span data-ttu-id="cfbdc-300">Identificador del informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-300">Report identifier.</span></span>|  
|<span data-ttu-id="cfbdc-301">UserName</span><span class="sxs-lookup"><span data-stu-id="cfbdc-301">UserName</span></span>|<span data-ttu-id="cfbdc-302">Identificador del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-302">User identifier.</span></span>|  
|<span data-ttu-id="cfbdc-303">RequestType</span><span class="sxs-lookup"><span data-stu-id="cfbdc-303">RequestType</span></span>|<span data-ttu-id="cfbdc-304">Valores posibles:</span><span class="sxs-lookup"><span data-stu-id="cfbdc-304">Possible values:</span></span><br /><br /> <span data-ttu-id="cfbdc-305">True = una solicitud de suscripción</span><span class="sxs-lookup"><span data-stu-id="cfbdc-305">True = A Subscription request</span></span><br /><br /> <span data-ttu-id="cfbdc-306">False= una solicitud interactiva</span><span class="sxs-lookup"><span data-stu-id="cfbdc-306">False= An Interactive request</span></span>|  
|<span data-ttu-id="cfbdc-307">Formato</span><span class="sxs-lookup"><span data-stu-id="cfbdc-307">Format</span></span>|<span data-ttu-id="cfbdc-308">Formato de representación.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-308">Rendering format.</span></span>|  
|<span data-ttu-id="cfbdc-309">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfbdc-309">Parameters</span></span>|<span data-ttu-id="cfbdc-310">Valores de parámetros utilizados para la ejecución de un informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-310">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="cfbdc-311">TimeStart</span><span class="sxs-lookup"><span data-stu-id="cfbdc-311">TimeStart</span></span>|<span data-ttu-id="cfbdc-312">Horas de inicio y detención que indican la duración del procesamiento de un informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-312">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="cfbdc-313">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="cfbdc-313">TimeEnd</span></span>||  
|<span data-ttu-id="cfbdc-314">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="cfbdc-314">TimeDataRetrieval</span></span>|<span data-ttu-id="cfbdc-315">Número de milisegundos dedicados a recuperar los datos, procesar el informe y representarlo.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-315">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="cfbdc-316">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="cfbdc-316">TimeProcessing</span></span>||  
|<span data-ttu-id="cfbdc-317">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="cfbdc-317">TimeRendering</span></span>||  
|<span data-ttu-id="cfbdc-318">Source</span><span class="sxs-lookup"><span data-stu-id="cfbdc-318">Source</span></span>|<span data-ttu-id="cfbdc-319">Origen de la ejecución del informe.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-319">Source of the report execution.</span></span> <span data-ttu-id="cfbdc-320">Valores posibles: (1=Activo, 2=Caché, 3=Instantánea, 4=Historial, 5=Adhoc, 6=Sesión, 7=RDCE).</span><span class="sxs-lookup"><span data-stu-id="cfbdc-320">Possible values: (1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE).</span></span>|  
|<span data-ttu-id="cfbdc-321">Estado</span><span class="sxs-lookup"><span data-stu-id="cfbdc-321">Status</span></span>|<span data-ttu-id="cfbdc-322">Valores posibles: rsSuccess, rsProcessingAborted o un código de error.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-322">Possible values: rsSuccess, rsProcessingAborted, or an error code.</span></span> <span data-ttu-id="cfbdc-323">Si aparecen varios errores, solo se registra el primero.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-323">If multiple errors occur, only the first error is recorded.</span></span>|  
|<span data-ttu-id="cfbdc-324">ByteCount</span><span class="sxs-lookup"><span data-stu-id="cfbdc-324">ByteCount</span></span>|<span data-ttu-id="cfbdc-325">Tamaño de los informes representados en bytes</span><span class="sxs-lookup"><span data-stu-id="cfbdc-325">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="cfbdc-326">RowCount</span><span class="sxs-lookup"><span data-stu-id="cfbdc-326">RowCount</span></span>|<span data-ttu-id="cfbdc-327">Número de filas devueltas de consultas.</span><span class="sxs-lookup"><span data-stu-id="cfbdc-327">Number of rows returned from queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfbdc-328">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfbdc-328">See Also</span></span>  
 <span data-ttu-id="cfbdc-329">[Activar Reporting Services eventos para el registro de seguimiento de SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span><span class="sxs-lookup"><span data-stu-id="cfbdc-329">[Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span></span>  
 <span data-ttu-id="cfbdc-330">[Archivos de registro y orígenes de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="cfbdc-330">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="cfbdc-331">Referencia de errores y eventos &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cfbdc-331">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](../troubleshooting/errors-and-events-reference-reporting-services.md)  
  
  
