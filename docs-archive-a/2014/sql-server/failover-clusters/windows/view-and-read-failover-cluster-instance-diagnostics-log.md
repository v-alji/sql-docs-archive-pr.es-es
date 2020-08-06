---
title: Ver y leer el registro de diagnósticos de la instancia de clúster de conmutación por error | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 68074bd5-be9d-4487-a320-5b51ef8e2b2d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 774dc4ec4a02c72420d004909cb7e6ee1b31f3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672552"
---
# <a name="view-and-read-failover-cluster-instance-diagnostics-log"></a><span data-ttu-id="71ab0-102">Ver y leer el registro de diagnósticos de la instancia de clúster de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="71ab0-102">View and Read Failover Cluster Instance Diagnostics Log</span></span>
  <span data-ttu-id="71ab0-103">Todos los errores críticos y eventos de advertencia de la DLL de recursos de SQL Server se escriben en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="71ab0-103">All critical errors and warning events for the SQL Server Resource DLL are written to the Windows event log.</span></span> <span data-ttu-id="71ab0-104">El procedimiento almacenado del sistema [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) captura un registro en ejecución de la información de diagnóstico específica de SQL Server y lo escribe en los archivos de registro de diagnósticos de clústeres de conmutación por error de SQL Server (también conocidos como registros *SQLDIAG*).</span><span class="sxs-lookup"><span data-stu-id="71ab0-104">A running log of the diagnostic information specific to SQL Server is captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) system stored procedure and is written to the SQL Server failover cluster diagnostics (also known as the *SQLDIAG* logs) log files.</span></span>  
  
-   <span data-ttu-id="71ab0-105">**Antes de empezar:**  [Recomendaciones](#Recommendations), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="71ab0-105">**Before you begin:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="71ab0-106">**Para ver el registro de diagnóstico, mediante:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="71ab0-106">**To View the Diagnostic Log, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="71ab0-107">**Para configurar los valores del registro de diagnóstico, mediante:** [Transact-SQL](#TsqlConfigure)</span><span class="sxs-lookup"><span data-stu-id="71ab0-107">**To Configure Diagnostic Log settings, using:** [Transact-SQL](#TsqlConfigure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="71ab0-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="71ab0-108">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="71ab0-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="71ab0-109">Recommendations</span></span>  
 <span data-ttu-id="71ab0-110">De forma predeterminada, el SQLDIAG se almacena en una carpeta de registro local del directorio de la instancia de SQL Server, por ejemplo, ' C\archivos de Programa\microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\LOG. ' del nodo propietario de la instancia de clúster de conmutación por error (FCI) AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="71ab0-110">By default, the SQLDIAG are stored under a local LOG folder of the SQL Server instance directory, for example, 'C\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\LOG' of the owning node of the AlwaysOn Failover Cluster Instance (FCI).</span></span> <span data-ttu-id="71ab0-111">El tamaño de cada archivo de registro de SQLDIAG se fija en 100 MB.</span><span class="sxs-lookup"><span data-stu-id="71ab0-111">The size of each SQLDIAG log file is fixed at 100 MB.</span></span> <span data-ttu-id="71ab0-112">Diez archivos de registro se almacenan en el equipo antes de que se reciclen para los nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="71ab0-112">Ten such log files are stored on the computer before they are recycled for new logs.</span></span>  
  
 <span data-ttu-id="71ab0-113">Los registros usan el formato de archivo extendido de eventos.</span><span class="sxs-lookup"><span data-stu-id="71ab0-113">The logs use the extended events file format.</span></span> <span data-ttu-id="71ab0-114">La función del sistema **sys.fn_xe_file_target_read_file** se puede usar para leer los archivos creados por eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="71ab0-114">The **sys.fn_xe_file_target_read_file** system function can be used to read the files that are created by Extended Events.</span></span> <span data-ttu-id="71ab0-115">Se devuelve un evento, en formato XML, por cada fila.</span><span class="sxs-lookup"><span data-stu-id="71ab0-115">One event, in XML format, is returned per row.</span></span> <span data-ttu-id="71ab0-116">Consulte la vista del sistema para analizar los datos XML como conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="71ab0-116">Query the system view to parse the XML data as a result-set.</span></span> <span data-ttu-id="71ab0-117">Para obtener más información, vea [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="71ab0-117">For more information, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="71ab0-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="71ab0-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="71ab0-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="71ab0-119">Permissions</span></span>  
 <span data-ttu-id="71ab0-120">El permiso VIEW SERVER STATE es necesario para ejecutar **fn_xe_file_target_read_file**.</span><span class="sxs-lookup"><span data-stu-id="71ab0-120">VIEW SERVER STATE permission is needed to run **fn_xe_file_target_read_file**.</span></span>  
  
 <span data-ttu-id="71ab0-121">Abra SQL Server Management Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="71ab0-121">Open SQL Server Management Studio as Administrator</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71ab0-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71ab0-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="71ab0-123">**Para ver los archivos de registro de diagnóstico:**</span><span class="sxs-lookup"><span data-stu-id="71ab0-123">**To view the Diagnostic log files:**</span></span>  
  
1.  <span data-ttu-id="71ab0-124">En el menú **Archivo** , seleccione **Abrir**, **Archivo**y elija el archivo de registro de diagnóstico que desea ver.</span><span class="sxs-lookup"><span data-stu-id="71ab0-124">From the **File** menu, select **Open**, **File**, and choose the diagnostic log file you want to view.</span></span>  
  
2.  <span data-ttu-id="71ab0-125">Los eventos aparecen como filas en el panel derecho y, de forma predeterminada, las dos únicas columnas mostradas son **name**y **timestamp** .</span><span class="sxs-lookup"><span data-stu-id="71ab0-125">The events are displayed as rows in the right pane, and by default **name**, and **timestamp** are the only two columns displayed.</span></span>  
  
     <span data-ttu-id="71ab0-126">De este modo también se activa el menú **ExtendedEvents** .</span><span class="sxs-lookup"><span data-stu-id="71ab0-126">This also activates the **ExtendedEvents** menu.</span></span>  
  
3.  <span data-ttu-id="71ab0-127">Para ver más columnas, vaya el menú **ExtendedEvents** y seleccione **Elegir columnas**.</span><span class="sxs-lookup"><span data-stu-id="71ab0-127">To see more columns, go the **ExtendedEvents** menu, and select **Choose Columns**.</span></span>  
  
     <span data-ttu-id="71ab0-128">Se abre un cuadro de diálogo con columnas disponibles que permiten seleccionar las columnas de la presentación.</span><span class="sxs-lookup"><span data-stu-id="71ab0-128">A dialog box opens with the available columns allowing you to select the columns for display.</span></span>  
  
4.  <span data-ttu-id="71ab0-129">Puede filtrar y ordenar los datos de evento mediante el menú **ExtendedEvents** y la selección de la opción **Filtrar** .</span><span class="sxs-lookup"><span data-stu-id="71ab0-129">You can filter, and sort the event data using the **ExtendedEvents** menu and selecting the **Filter** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="71ab0-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71ab0-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="71ab0-131">**Para ver los archivos de registro de diagnóstico:**</span><span class="sxs-lookup"><span data-stu-id="71ab0-131">**To view the Diagnostic log files:**</span></span>  
  
 <span data-ttu-id="71ab0-132">Para ver todos los elementos en el archivo de registro SQLDIAG, use la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="71ab0-132">To view all the log items in the SQLDIAG log file, use the following query:</span></span>  
  
```  
SELECT  
xml_data.value('(event/@name)[1]','varchar(max)') AS 'Name'  
,xml_data.value('(event/@package)[1]','varchar(max)') AS 'Package'  
,xml_data.value('(event/@timestamp)[1]','datetime') AS 'Time'  
,xml_data.value('(event/data[@name=''state'']/value)[1]','int') AS 'State'  
,xml_data.value('(event/data[@name=''state_desc'']/text)[1]','varchar(max)') AS 'State Description'  
,xml_data.value('(event/data[@name=''failure_condition_level'']/value)[1]','int') AS 'Failure Conditions'  
,xml_data.value('(event/data[@name=''node_name'']/value)[1]','varchar(max)') AS 'Node_Name'  
,xml_data.value('(event/data[@name=''instancename'']/value)[1]','varchar(max)') AS 'Instance Name'  
,xml_data.value('(event/data[@name=''creation time'']/value)[1]','datetime') AS 'Creation Time'  
,xml_data.value('(event/data[@name=''component'']/value)[1]','varchar(max)') AS 'Component'  
,xml_data.value('(event/data[@name=''data'']/value)[1]','varchar(max)') AS 'Data'  
,xml_data.value('(event/data[@name=''info'']/value)[1]','varchar(max)') AS 'Info'  
FROM  
 ( SELECT object_name AS 'event'  
  ,CONVERT(xml,event_data) AS 'xml_data'  
  FROM sys.fn_xe_file_target_read_file('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log\SQLNODE1_MSSQLSERVER_SQLDIAG_0_129936003752530000.xel',NULL,NULL,NULL)   
)   
AS XEventData  
ORDER BY Time;  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="71ab0-133">Puede filtrar los resultados para los componentes específicos o con estado la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="71ab0-133">You can filter the results for specific components or state using the WHERE clause.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlConfigure"></a> <span data-ttu-id="71ab0-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71ab0-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="71ab0-135">**Para configurar las propiedades de registro de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="71ab0-135">**To configure the Diagnostic Log Properties**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71ab0-136">Para ver un ejemplo de este procedimiento, vea [Ejemplo (Transact-SQL)](#TsqlExample)más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="71ab0-136">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
 <span data-ttu-id="71ab0-137">Con la instrucción de lenguaje de definición de datos (DDL), `ALTER SERVER CONFIGURATION` puede iniciar o detener el registro de datos de diagnóstico capturados por la [sp_server_diagnostics &#40;procedimiento de&#41;de TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) y establecer parámetros de configuración del registro sqldiag como el recuento de sustitución de archivos de registro, el tamaño del archivo de registro y la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="71ab0-137">Using the Data Definition Language (DDL) statement, `ALTER SERVER CONFIGURATION`, you can start or stop logging diagnostic data captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) procedure, and set SQLDIAG log configuration parameters such as the log file rollover count, log file size, and file location.</span></span> <span data-ttu-id="71ab0-138">Para obtener información detallada sobre la sintaxis, vea [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span><span class="sxs-lookup"><span data-stu-id="71ab0-138">For syntax details, see [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="ConfigTsqlExample"></a> <span data-ttu-id="71ab0-139">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="71ab0-139">Examples (Transact-SQL)</span></span>  
  
####  <a name="setting-diagnostic-log-options"></a><a name="TsqlExample"></a> <span data-ttu-id="71ab0-140">Setting diagnostic log options</span><span class="sxs-lookup"><span data-stu-id="71ab0-140">Setting diagnostic log options</span></span>  
 <span data-ttu-id="71ab0-141">En los ejemplos de esta sección se muestra cómo establecer los valores para la opción de registro de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="71ab0-141">The examples in this section show how to set the values for the diagnostic log option.</span></span>  
  
##### <a name="a-starting-diagnostic-logging"></a><span data-ttu-id="71ab0-142">A.</span><span class="sxs-lookup"><span data-stu-id="71ab0-142">A.</span></span> <span data-ttu-id="71ab0-143">Iniciar el registro de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="71ab0-143">Starting diagnostic logging</span></span>  
 <span data-ttu-id="71ab0-144">En el ejemplo siguiente se inicia el registro de los datos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="71ab0-144">The following example starts the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG ON;  
```  
  
##### <a name="b-stopping-diagnostic-logging"></a><span data-ttu-id="71ab0-145">B.</span><span class="sxs-lookup"><span data-stu-id="71ab0-145">B.</span></span> <span data-ttu-id="71ab0-146">Detener el registro de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="71ab0-146">Stopping diagnostic logging</span></span>  
 <span data-ttu-id="71ab0-147">En el ejemplo siguiente se detiene el registro de los datos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="71ab0-147">The following example stops the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG OFF;  
```  
  
##### <a name="c-specifying-the-location-of-the-diagnostic-logs"></a><span data-ttu-id="71ab0-148">C.</span><span class="sxs-lookup"><span data-stu-id="71ab0-148">C.</span></span> <span data-ttu-id="71ab0-149">Especificar la ubicación de los registros de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="71ab0-149">Specifying the location of the diagnostic logs</span></span>  
 <span data-ttu-id="71ab0-150">En el ejemplo siguiente se establece la ubicación de los registros de diagnóstico en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="71ab0-150">The following example sets the location of the diagnostic logs to the specified file path.</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET DIAGNOSTICS LOG PATH = 'C:\logs';  
```  
  
##### <a name="d-specifying-the-maximum-size-of-each-diagnostic-log"></a><span data-ttu-id="71ab0-151">D.</span><span class="sxs-lookup"><span data-stu-id="71ab0-151">D.</span></span> <span data-ttu-id="71ab0-152">Especificar el tamaño máximo de cada registro de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="71ab0-152">Specifying the maximum size of each diagnostic log</span></span>  
 <span data-ttu-id="71ab0-153">En el ejemplo siguiente se establece el tamaño máximo de cada registro de diagnóstico en 10 megabytes.</span><span class="sxs-lookup"><span data-stu-id="71ab0-153">The following example set the maximum size of each diagnostic log to 10 megabytes.</span></span>  
  
```  
ALTER SERVER CONFIGURATION   
SET DIAGNOSTICS LOG MAX_SIZE = 10 MB;  
```  
  
## <a name="see-also"></a><span data-ttu-id="71ab0-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71ab0-154">See Also</span></span>  
 [<span data-ttu-id="71ab0-155">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="71ab0-155">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
  
  
