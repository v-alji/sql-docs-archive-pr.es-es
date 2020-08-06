---
title: Configurar las opciones avanzadas de los archivos de registro de DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- log files,advanced settings
- dqs log files,advanced settings
ms.assetid: 1d565748-9759-425c-ae38-4d2032a86868
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ad41b0cac95f9bfe5565ccbac16b0fda3e28ddf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744326"
---
# <a name="configure-advanced-settings-for-dqs-log-files"></a><span data-ttu-id="d8400-102">Configurar las opciones avanzadas de los archivos de registro de DQS</span><span class="sxs-lookup"><span data-stu-id="d8400-102">Configure Advanced Settings for DQS Log Files</span></span>
  <span data-ttu-id="d8400-103">En este tema se describe cómo realizar la configuración avanzada para los archivos de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] y [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , como configurar el límite de tamaño del archivo gradual de los archivos de registro, establecer el patrón de marca de tiempo de los eventos, etc.</span><span class="sxs-lookup"><span data-stu-id="d8400-103">This topic describes how to configure advanced settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log files, such as set the rolling file size limit of the log files, set the time stamp pattern of the events, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8400-104">Estas actividades no se pueden realizar mediante [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], y están dirigidas exclusivamente a los usuarios expertos.</span><span class="sxs-lookup"><span data-stu-id="d8400-104">These activities cannot be performed using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and is intended for advanced users only.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8400-105">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d8400-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8400-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d8400-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8400-107">Permisos</span><span class="sxs-lookup"><span data-stu-id="d8400-107">Permissions</span></span>  
  
-   <span data-ttu-id="d8400-108">La cuenta de usuario de Windows debe ser miembro del rol fijo de servidor sysadmin en la instancia de SQL Server para modificar la configuración de la tabla A_CONFIGURATION de la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="d8400-108">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to modify configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
-   <span data-ttu-id="d8400-109">Debe haber iniciado sesión como miembro del grupo Administradores en el equipo donde está modificando el archivo DQLog.Client.xml para configurar los valores de registro de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8400-109">You must be logged on as a member of the Administrators group on the computer where you are modifying the DQLog.Client.xml file to configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] logging settings.</span></span>  
  
##  <a name="configure-data-quality-server-log-settings"></a><a name="DQSServer"></a><span data-ttu-id="d8400-110">Configurar los valores de registro de Data Quality Server</span><span class="sxs-lookup"><span data-stu-id="d8400-110">Configure Data Quality Server Log Settings</span></span>  
 <span data-ttu-id="d8400-111">Los valores de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] se encuentran en formato XML en la columna **VALUE** de la fila **ServerLogging** de la tabla A_CONFIGURATION de la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="d8400-111">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings are present in an XML format in the **VALUE** column of the **ServerLogging** row in the A_CONFIGURATION table in the DQS_MAIN database.</span></span> <span data-ttu-id="d8400-112">Puede ejecutar la consulta SQL siguiente para ver la información de configuración:</span><span class="sxs-lookup"><span data-stu-id="d8400-112">You can run the following SQL query to view the configuration information:</span></span>  
  
```sql  
select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'; 
```  
  
 <span data-ttu-id="d8400-113">Debe actualizar la información correspondiente en la columna **VALUE** de la fila **ServerLogging** para cambiar la configuración del registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8400-113">You must update the appropriate information in the **VALUE** column of the **ServerLogging** row to change the configuration settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging.</span></span> <span data-ttu-id="d8400-114">En este ejemplo, actualizaremos los valores de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] para establecer el límite de tamaño del archivo gradual en 25000 kB (el valor predeterminado es 20000 kB).</span><span class="sxs-lookup"><span data-stu-id="d8400-114">In this example, we will update the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings to set the rolling file size limit to 25000 KB (the default is 20000 KB).</span></span>  
  
1.  <span data-ttu-id="d8400-115">Inicie Microsoft SQL Server Management Studio y conéctese a la instancia adecuada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d8400-115">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="d8400-116">En el Explorador de objetos, haga clic con el botón secundario en el servidor y, a continuación, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d8400-116">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8400-117">En la ventana del editor de consultas, copie las instrucciones SQL siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8400-117">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    -- Begin the transaction.  
    BEGIN TRAN  
    GO  
    -- set the XML value field for the row with name=ServerLogging  
    update DQS_MAIN.dbo.A_CONFIGURATION   
    set VALUE='<configuration>  
      <configSections>  
        <section name="loggingConfiguration" type="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.LoggingSettings, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" />  
      </configSections>  
      <loggingConfiguration name="Logging Application Block" tracingEnabled="true" defaultCategory="" logWarningsWhenNoCategoriesMatch="true">  
        <listeners>  
          <add fileName="###REPLACE_THIS_WITH_SQL_SERVER_INSTANCE_LOG_FOLDER_NAME###DQServerLog.###REPLACE_THIS_WITH_SQL_CATALOG_NAME###.log" footer="" formatter="Custom Text Formatter" header="" rollFileExistsBehavior="Increment" rollInterval="None" rollSizeKB="25000" timeStampPattern="yyyy-MM-dd" listenerDataType="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.RollingFlatFileTraceListenerData, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" traceOutputOptions="None" filter="All" type="Microsoft.Practices.EnterpriseLibrary.Logging.TraceListeners.RollingFlatFileTraceListener, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Rolling Flat File Trace Listener" />  
        </listeners>  
        <formatters>  
          <add template="{timestamp(local)}|[{threadName}]|{dictionary({value}|)}{message}" type="Microsoft.Practices.EnterpriseLibrary.Logging.Formatters.TextFormatter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Custom Text Formatter" />  
        </formatters>  
        <logFilters>  
          <add enabled="true" type="Microsoft.Practices.EnterpriseLibrary.Logging.Filters.LogEnabledFilter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="LogEnabled Filter" />  
        </logFilters>  
        <categorySources />  
        <specialSources>  
          <allEvents switchValue="All" name="All Events" />  
          <notProcessed switchValue="All" name="Unprocessed Category" />  
          <errors switchValue="All" name="Logging Errors & Warnings">  
            <listeners>  
              <add name="Rolling Flat File Trace Listener" />  
            </listeners>  
          </errors>  
        </specialSources>  
      </loggingConfiguration>  
    </configuration>'  
    WHERE NAME='ServerLogging'  
    GO  
    -- check the result  
    select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'  
  
    -- Commit the transaction.  
    COMMIT TRAN  
  
    ```  
  
4.  <span data-ttu-id="d8400-118">Presione F5 para ejecutar las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d8400-118">Press F5 to execute the statements.</span></span> <span data-ttu-id="d8400-119">Vea el panel **Resultados** para comprobar que las instrucciones se han ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8400-119">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
5.  <span data-ttu-id="d8400-120">Para aplicar los cambios realizados en la configuración de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , debe ejecutar las instrucciones Transact-SQL siguientes.</span><span class="sxs-lookup"><span data-stu-id="d8400-120">To apply changes done to the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging configuration, you must run the following Transact-SQL statements.</span></span> <span data-ttu-id="d8400-121">Abra una nueva ventana del editor de consultas y pegue las instrucciones Transact-SQL siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8400-121">Open a new Query Editor window, and paste the following Transact-SQL statements:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    DECLARE @return_value int  
    EXEC @return_value = [internal_core].[RefreshLogSettings]  
    SELECT 'Return Value' = @return_value  
    GO  
    ```  
  
6.  <span data-ttu-id="d8400-122">Presione F5 para ejecutar las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d8400-122">Press F5 to execute the statements.</span></span> <span data-ttu-id="d8400-123">Vea el panel **Resultados** para comprobar que las instrucciones se han ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8400-123">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8400-124">La configuración de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] se genera y se almacena dinámicamente en el archivo DQS_MAIN.Log, que normalmente se encuentra en C:\Archivos de programa\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log si ha instalado la instancia predeterminada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d8400-124">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging settings configuration is dynamically generated and stored in the DQS_MAIN.Log file, which is typically available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log if you installed the default instance of SQL Server.</span></span> <span data-ttu-id="d8400-125">Sin embargo, los cambios realizados directamente en este archivo no se conservan, y serán reemplazados por la configuración de la tabla A_CONFIGURATION de la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="d8400-125">However, changes done directly in this file do not hold, and are overwritten by the configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
##  <a name="configure-data-quality-client-log-settings"></a><a name="DQSClient"></a><span data-ttu-id="d8400-126">Configuración del registro de Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="d8400-126">Configure Data Quality Client Log Settings</span></span>  
 <span data-ttu-id="d8400-127">El [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] archivo de configuración de configuración de registro, DQLog.Client.xml, suele estar disponible en c:\Archivos de programa\Microsoft SQL Server\120\Tools\Binn\DQ\config. El contenido del archivo XML es similar al del archivo XML que modificó anteriormente para los [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] valores de configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="d8400-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log setting configuration file, DQLog.Client.xml, is typically available at C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. The contents of the XML file is similar to the XML file that you modified earlier for the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="d8400-128">Para configurar los valores de registro de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d8400-128">To configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log settings:</span></span>  
  
1.  <span data-ttu-id="d8400-129">Ejecute cualquier herramienta de edición de XML o el Bloc de notas como administrador.</span><span class="sxs-lookup"><span data-stu-id="d8400-129">Run any XML editing tool or notepad as an administrator.</span></span>  
  
2.  <span data-ttu-id="d8400-130">Abra el archivo DQLog.Client.xml en la herramienta o en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="d8400-130">Open the DQLog.Client.xml file in the tool or notepad.</span></span>  
  
3.  <span data-ttu-id="d8400-131">Realice los cambios necesarios y guarde el archivo para aplicarlos.</span><span class="sxs-lookup"><span data-stu-id="d8400-131">Make the required changes, and save the file to apply the new logging changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8400-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8400-132">See Also</span></span>  
 [<span data-ttu-id="d8400-133">Configurar los niveles de gravedad de los archivos de registro de DQS</span><span class="sxs-lookup"><span data-stu-id="d8400-133">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)  
  
  
