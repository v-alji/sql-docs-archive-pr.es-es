---
title: Administrar archivos de registro de DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- logging
- log files
- dqs log files
ms.assetid: 4fccfd24-aede-4882-be69-ec1e82682e16
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ca85772b8cc8aca41b75ad05d028bc444f280378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676677"
---
# <a name="manage-dqs-log-files"></a><span data-ttu-id="d7284-102">Administrar archivos de registro de DQS</span><span class="sxs-lookup"><span data-stu-id="d7284-102">Manage DQS Log Files</span></span>
  <span data-ttu-id="d7284-103">Los archivos de registro de[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) le ayudan a diagnosticar y solucionar los problemas relacionados con [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]y [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7284-103">[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) log files help you in diagnosing and troubleshooting issue with [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="d7284-104">Se generan archivos de registro independientes para [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]y el [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7284-104">Separate log files are generated for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
 <span data-ttu-id="d7284-105">Puede utilizar [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] para configurar el valor de gravedad del registro para los módulos y las características de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7284-105">You can use [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] to configure the log severity setting for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] features and modules.</span></span> <span data-ttu-id="d7284-106">Además, también es posible configurar varios valores (avanzados) para los archivos de registro de DQS cambiando manualmente la configuración del registro de DQS en la base de datos DQS_MAIN y un archivo XML en el equipo de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7284-106">Additionally, you can also configure some other (advanced) settings for the DQS log files by manually changing the DQS log configuration settings in the DQS_MAIN database and an XML file on the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] computer.</span></span>  
  
##  <a name="data-quality-server-log-file"></a><a name="DQSServer"></a><span data-ttu-id="d7284-107">Archivo de registro de Data Quality Server</span><span class="sxs-lookup"><span data-stu-id="d7284-107">Data Quality Server Log File</span></span>  
 <span data-ttu-id="d7284-108">El archivo de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , DQServerLog.DQS_MAIN.log, incluye registros de las actividades que se ejecutan en [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7284-108">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, DQServerLog.DQS_MAIN.log, includes logs of activities that are run on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="d7284-109">Si instaló la instancia predeterminada de SQL Server, el archivo DQServerLog.DQS_MAIN.log se encontrará en C:\Archivos de programa\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span><span class="sxs-lookup"><span data-stu-id="d7284-109">If you installed the default instance of SQL Server, the DQServerLog.DQS_MAIN.log file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span></span> <span data-ttu-id="d7284-110">El archivo de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] contiene los elementos de información siguientes, cada uno de ellos delimitado por un carácter de barra vertical (|):</span><span class="sxs-lookup"><span data-stu-id="d7284-110">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file contains the following pieces of information, each delimited by a pipe (|):</span></span>  
  
-   <span data-ttu-id="d7284-111">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="d7284-111">Date and time</span></span>  
  
-   <span data-ttu-id="d7284-112">Nombre del subproceso</span><span class="sxs-lookup"><span data-stu-id="d7284-112">Thread name</span></span>  
  
-   <span data-ttu-id="d7284-113">Id. de subproceso</span><span class="sxs-lookup"><span data-stu-id="d7284-113">Thread ID</span></span>  
  
-   <span data-ttu-id="d7284-114">Gravedad del registro (FATAL, ERROR, WARN, INFO y DEBUG)</span><span class="sxs-lookup"><span data-stu-id="d7284-114">Log severity (FATAL, ERROR, WARN, INFO, and DEBUG)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7284-115">La gravedad del registro DEBUG es la misma que Detallado.</span><span class="sxs-lookup"><span data-stu-id="d7284-115">The DEBUG logging severity is same as Verbose.</span></span>  
  
-   <span data-ttu-id="d7284-116">UID (identificador de infraestructura de DQS interno)</span><span class="sxs-lookup"><span data-stu-id="d7284-116">UID (internal DQS infrastructure ID)</span></span>  
  
-   <span data-ttu-id="d7284-117">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d7284-117">Namespace</span></span>  
  
-   <span data-ttu-id="d7284-118">Clase y método</span><span class="sxs-lookup"><span data-stu-id="d7284-118">Class and method</span></span>  
  
-   <span data-ttu-id="d7284-119">Message</span><span class="sxs-lookup"><span data-stu-id="d7284-119">Message</span></span>  
  
 <span data-ttu-id="d7284-120">Junto con estos elementos, el archivo de registro también muestra información sobre la versión de la aplicación, el nombre del equipo, el nombre del usuario y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d7284-120">Along with these, the log file also displays information about the application version, computer name, user name, and operating system.</span></span>  
  
 <span data-ttu-id="d7284-121">Una entrada de ejemplo del archivo de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] tiene el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="d7284-121">A sample entry in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file looks like the following:</span></span>  
  
```  
23-08-2013 01:45:29|[]|4|INFO|PUID|InfInfoModuleStarting|Microsoft.Ssdqs.Core.Startup.ServerInit|Starting DQS ServerInit: version [12.0.0.0], machine name [DQS-TEST], user name [NT Service\MSSQLSERVER], operating system [Microsoft Windows NT 6.1.7600.0]...  
```  
  
 <span data-ttu-id="d7284-122">El archivo DQServerLog.DQS_MAIN.log es un archivo gradual, y se crea un nuevo archivo de registro cuando el existente supera el límite de tamaño del archivo gradual especificado en la configuración del registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7284-122">The DQServerLog.DQS_MAIN.log file is a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="d7284-123">Para obtener más información, vea [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="d7284-123">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="data-quality-client-log-file"></a><a name="DQSClient"></a><span data-ttu-id="d7284-124">Archivo de registro de Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="d7284-124">Data Quality Client Log File</span></span>  
 <span data-ttu-id="d7284-125">El archivo de registro de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , DQClientLog.log, incluye los registros del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="d7284-125">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file, DQClientLog.log, includes the client side logs.</span></span> <span data-ttu-id="d7284-126">El archivo de registro de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] está disponible en %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="d7284-126">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="d7284-127">El archivo de registro de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] contiene un conjunto de información similar al del archivo de registro del servidor, pero para el lado cliente.</span><span class="sxs-lookup"><span data-stu-id="d7284-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file contains similar set of information as in the server log file, but for the client side.</span></span>  
  
 <span data-ttu-id="d7284-128">Al igual que el archivo de registro de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , el archivo de registro de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] es un archivo gradual, y se crea un nuevo archivo de registro cuando el existente supera el límite de tamaño del archivo gradual especificado en la configuración del registro de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7284-128">As with the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is also a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log configuration settings.</span></span> <span data-ttu-id="d7284-129">Para obtener más información, vea [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="d7284-129">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="dqs-cleansing-component-log-file"></a><a name="DQSCleansing"></a><span data-ttu-id="d7284-130">Archivo de registro del componente de limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="d7284-130">DQS Cleansing Component Log File</span></span>  
 <span data-ttu-id="d7284-131">El archivo de registro de [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] , DQSSSISLog.log, incluye registros de las actividades realizadas mediante [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7284-131">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file, DQSSSISLog.log, includes logs of activities performed using the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="d7284-132">El archivo de registro del componente [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] está disponible en %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="d7284-132">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] component log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="d7284-133">El archivo de registro de [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] contiene un conjunto de información similar al del archivo de registro del servidor, pero para [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7284-133">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file contains similar set of information as in the server log file, but for the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
##  <a name="related-tasks"></a><a name="RT"></a> <span data-ttu-id="d7284-134">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d7284-134">Related Tasks</span></span>  
  
|<span data-ttu-id="d7284-135">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="d7284-135">Task Description</span></span>|<span data-ttu-id="d7284-136">Tema</span><span class="sxs-lookup"><span data-stu-id="d7284-136">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="d7284-137">Describe cómo configurar los valores de gravedad del registro para los archivos de registro de DQS mediante [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7284-137">Describes how to configure log severity settings for DQS log files using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>|[<span data-ttu-id="d7284-138">Configurar los niveles de gravedad de los archivos de registro de DQS</span><span class="sxs-lookup"><span data-stu-id="d7284-138">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|<span data-ttu-id="d7284-139">Describe cómo realizar manualmente la configuración avanzada para los archivos de registro de DQS.</span><span class="sxs-lookup"><span data-stu-id="d7284-139">Describes how to manually configure advanced settings for DQS log files.</span></span>|[<span data-ttu-id="d7284-140">Configurar las opciones avanzadas de los archivos de registro de DQS</span><span class="sxs-lookup"><span data-stu-id="d7284-140">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d7284-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7284-141">See Also</span></span>  
 [<span data-ttu-id="d7284-142">dqs, administración</span><span class="sxs-lookup"><span data-stu-id="d7284-142">DQS Administration</span></span>](../../2014/data-quality-services/dqs-administration.md)  
  
  
