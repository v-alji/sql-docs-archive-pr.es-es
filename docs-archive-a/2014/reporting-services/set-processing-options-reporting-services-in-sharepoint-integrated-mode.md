---
title: Establecer opciones de procesamiento (Reporting Services en el modo integrado de SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], content management
- snapshots [Reporting Services], creating
ms.assetid: 453b19a1-739a-4b67-aeea-2069b52204e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c33b205a702d4ab77abf74154232990da9840b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746151"
---
# <a name="set-processing-options-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="80fb3-102">Establecer opciones de procesamiento (Reporting Services en el modo integrado de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="80fb3-102">Set Processing Options (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="80fb3-103">Puede establecer opciones de procesamiento en un informe [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para determinar cuándo debe tener lugar el procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="80fb3-103">You can set processing options on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report to determine when data processing occurs.</span></span> <span data-ttu-id="80fb3-104">También puede establecer un valor de tiempo de espera para el procesamiento de informes, así como opciones que determinen si debe habilitarse el historial de informes para el informe actual.</span><span class="sxs-lookup"><span data-stu-id="80fb3-104">You can also set a time-out value for report processing, and options that determine whether report history is enabled for the current report.</span></span>  
  
-   <span data-ttu-id="80fb3-105">Los informes pueden ejecutarse como una instantánea de informe si se desea evitar que el informe se ejecute de forma arbitraria (durante una copia de seguridad programada, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="80fb3-105">You can run a report as a report snapshot to prevent the report from being run at arbitrary times (for example, during a scheduled backup).</span></span> <span data-ttu-id="80fb3-106">Una instantánea de informe suele crearse y actualizarse posteriormente según una programación, lo que permite controlar con exactitud el momento en que se producirá el procesamiento del informe y los datos.</span><span class="sxs-lookup"><span data-stu-id="80fb3-106">A report snapshot is usually created and subsequently refreshed on a schedule, allowing you to time exactly when report and data processing will occur.</span></span> <span data-ttu-id="80fb3-107">Si un informe se basa en consultas que tardan demasiado en ejecutarse o en consultas que usan datos desde un origen de datos al que prefiere que nadie tenga acceso durante determinadas horas, debe ejecutar el informe como instantánea.</span><span class="sxs-lookup"><span data-stu-id="80fb3-107">If a report is based on queries that take a long time to run, or on queries that use data from a data source that you prefer no one access during certain hours, you should run the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="80fb3-108">Un servidor de informes puede almacenar en memoria caché una copia de un informe procesado y devolverla cuando el usuario abra el informe.</span><span class="sxs-lookup"><span data-stu-id="80fb3-108">A report server can cache a copy of a processed report and return that copy when a user opens the report.</span></span> <span data-ttu-id="80fb3-109">El almacenamiento en caché es una técnica de mejora del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="80fb3-109">Caching is a performance-enhancement technique.</span></span> <span data-ttu-id="80fb3-110">El almacenamiento en caché puede reducir el tiempo necesario para recuperar un informe cuando éste es demasiado grande o se utiliza con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="80fb3-110">Caching can shorten the time required to retrieve a report if the report is large or accessed frequently.</span></span>  
  
-   <span data-ttu-id="80fb3-111">El historial del informe es un conjunto de copias de un informe ejecutadas con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="80fb3-111">Report history is a collection of previously run copies of a report.</span></span> <span data-ttu-id="80fb3-112">Puede usar el historial de informe para conservar un registro de un informe a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="80fb3-112">You can use report history to maintain a record of a report over time.</span></span> <span data-ttu-id="80fb3-113">El historial del informe no se ha diseñado para informes que contienen datos confidenciales o personales.</span><span class="sxs-lookup"><span data-stu-id="80fb3-113">Report history is not intended for reports that contain confidential or personal data.</span></span> <span data-ttu-id="80fb3-114">Por este motivo, el historial solamente puede incluir aquellos informes que realizan una consulta a un origen de datos mediante un único conjunto de credenciales (sean credenciales almacenadas o credenciales usadas para la ejecución de informes desatendida) disponible para todos los usuarios que ejecutan un informe.</span><span class="sxs-lookup"><span data-stu-id="80fb3-114">For this reason, report history can include only those reports that query a data source using a single set of credentials (either stored credentials or credentials used for unattended report execution) that are available to all users who run a report.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="80fb3-115">con SharePoint usa las características de mantenimiento de entrada y salida de SharePoint para guardar las actualizaciones en los tipos de contenido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80fb3-115">integration with SharePoint uses the check out and check in content management features of SharePoint to save updates to [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="80fb3-116">Esto incluye la creación de instantáneas de informe.</span><span class="sxs-lookup"><span data-stu-id="80fb3-116">This includes the creation of report snapshots.</span></span> <span data-ttu-id="80fb3-117">Por consiguiente si ha habilitado la versión en una biblioteca de documentos, verá la versión del informe actualizada cuando se crea una nueva instantánea del historial de informes.</span><span class="sxs-lookup"><span data-stu-id="80fb3-117">Therefore if you have enabled versioning on a document library, you will see the report version updated when a new report history snapshot is created.</span></span> <span data-ttu-id="80fb3-118">Este es un efecto secundario de actualizar las instantáneas.</span><span class="sxs-lookup"><span data-stu-id="80fb3-118">This is a side-effect of updating snapshots.</span></span> <span data-ttu-id="80fb3-119">Cuando una instantánea está actualizada hace que la propiedad LastExecution del informe cambie y eso producirá un cambio en la versión del informe.</span><span class="sxs-lookup"><span data-stu-id="80fb3-119">When a snapshot is updated it causes the LastExecution property of the report to change and that will cause a change in the version of the report.</span></span>  
  
-   <span data-ttu-id="80fb3-120">La especificación de valores de tiempo de espera permite establecer límites relativos al empleo de los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="80fb3-120">You can specify time-out values to set limits on how system resources are used.</span></span>  
  
||  
|-|  
|<span data-ttu-id="80fb3-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="80fb3-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|  
  
 <span data-ttu-id="80fb3-122">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="80fb3-122">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="80fb3-123">Para establecer opciones de actualización de datos</span><span class="sxs-lookup"><span data-stu-id="80fb3-123">To set data refresh options</span></span>](#bkmk_set_data_refresh)  
  
-   [<span data-ttu-id="80fb3-124">Para establecer opciones de almacenamiento en caché de informes</span><span class="sxs-lookup"><span data-stu-id="80fb3-124">To set report caching options</span></span>](#bkmk_set_report_caching)  
  
-   [<span data-ttu-id="80fb3-125">Para establecer valores de tiempo de espera de procesamiento</span><span class="sxs-lookup"><span data-stu-id="80fb3-125">To set processing time-out values</span></span>](#bkmk_set_processing)  
  
-   [<span data-ttu-id="80fb3-126">Para establecer opciones y límites del historial de informes</span><span class="sxs-lookup"><span data-stu-id="80fb3-126">To set report history options and limits</span></span>](#bkmk_set_report_history)  
  
-   [<span data-ttu-id="80fb3-127">Establecer tiempo de espera de base de datos</span><span class="sxs-lookup"><span data-stu-id="80fb3-127">Set database timeout</span></span>](#bkmk_set_database_timeout)  
  
##  <a name="to-set-data-refresh-options"></a><a name="bkmk_set_data_refresh"></a><span data-ttu-id="80fb3-128">Para establecer las opciones de actualización de datos</span><span class="sxs-lookup"><span data-stu-id="80fb3-128">To set data refresh options</span></span>  
  
1.  <span data-ttu-id="80fb3-129">Seleccione un informe en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="80fb3-129">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="80fb3-130">Haga clic en la flecha abajo y, a continuación, seleccione **Administrar opciones de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-130">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="80fb3-131">En **Opciones de actualización de datos**, haga clic en **Usar datos de instantánea**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-131">In **Data Refresh Options**, click **Use snapshot data**.</span></span> <span data-ttu-id="80fb3-132">Si se muestra el mensaje "Este informe no se puede ejecutar desde una instantánea porque una o varias de las credenciales de los orígenes de datos no están almacenadas", significa que el informe no está configurado para ejecutarse en modo desatendido y que debe modificar los orígenes de datos para usar credenciales almacenadas antes de establecer esta opción.</span><span class="sxs-lookup"><span data-stu-id="80fb3-132">If you see "This report can not run from a snapshot because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="80fb3-133">En **Opciones de instantánea de datos**, seleccione **Programar procesamiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-133">In **Data Snapshot Options**, select **Schedule data processing**.</span></span>  
  
5.  <span data-ttu-id="80fb3-134">Seleccione **En una programación compartida** si dispone de una programación compartida que desee usar; de lo contrario, haga clic en **En una programación personalizada**y, a continuación, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-134">Select **On a shared schedule** if you have an existing shared schedule that you want to use, otherwise click **On a custom schedule**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="80fb3-135">Seleccione la frecuencia, la programación y las fechas de inicio y finalización y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-135">Select frequency, schedule, and start and end dates, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="80fb3-136">En **Opciones de instantáneas de datos**, seleccione **Crear o actualizar la instantánea cuando se guarde la página** si desea crear datos de instantáneas inmediatamente para utilizarlos con el informe, sin esperar a que tenga lugar el procesamiento de datos programados.</span><span class="sxs-lookup"><span data-stu-id="80fb3-136">In **Data Snapshot Options**, select **Create or update the snapshot when this page is saved** if you want to immediately create snapshot data to use with the report, without waiting for the scheduled data processing to occur.</span></span>  
  
##  <a name="to-set-report-caching-options"></a><a name="bkmk_set_report_caching"></a><span data-ttu-id="80fb3-137">Para establecer las opciones de almacenamiento en caché de informes</span><span class="sxs-lookup"><span data-stu-id="80fb3-137">To set report caching options</span></span>  
  
1.  <span data-ttu-id="80fb3-138">Seleccione un informe en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="80fb3-138">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="80fb3-139">Haga clic en la flecha abajo y, a continuación, seleccione **Administrar opciones de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-139">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="80fb3-140">En **Opciones de actualización de datos**, haga clic en **Usar datos en caché**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-140">In **Data Refresh Options**, click **Use cached data**.</span></span> <span data-ttu-id="80fb3-141">Si se muestra el mensaje "No se pudo almacenar en caché el informe porque una o varias de las credenciales de orígenes de datos no están almacenadas", significa que el informe no está configurado para ejecutarse en modo desatendido y que debe modificar los orígenes de datos para usar credenciales almacenadas antes de establecer esta opción.</span><span class="sxs-lookup"><span data-stu-id="80fb3-141">If you see "This report can not be cached because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="80fb3-142">En **Opciones de caché**, especifique la forma en que expirará la caché:</span><span class="sxs-lookup"><span data-stu-id="80fb3-142">In **Cache Options**, specify how the cache will expire:</span></span>  
  
    -   <span data-ttu-id="80fb3-143">Escriba un número de minutos tras los que expirará la caché.</span><span class="sxs-lookup"><span data-stu-id="80fb3-143">Enter a number of minutes after which the cache will expire.</span></span>  
  
    -   <span data-ttu-id="80fb3-144">Use una programación compartida para borrar la caché a las horas especificadas en la programación.</span><span class="sxs-lookup"><span data-stu-id="80fb3-144">Use a shared schedule to clear the cache at times specified in the schedule.</span></span>  
  
    -   <span data-ttu-id="80fb3-145">Cree una programación personalizada para borrar la caché a la hora especificada.</span><span class="sxs-lookup"><span data-stu-id="80fb3-145">Create a custom schedule to clear the cache at a time that you specify.</span></span>  
  
##  <a name="to-set-processing-time-out-values"></a><a name="bkmk_set_processing"></a><span data-ttu-id="80fb3-146">Para establecer valores de tiempo de espera de procesamiento</span><span class="sxs-lookup"><span data-stu-id="80fb3-146">To set processing time-out values</span></span>  
  
1.  <span data-ttu-id="80fb3-147">Seleccione un informe en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="80fb3-147">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="80fb3-148">Haga clic en la flecha abajo y, a continuación, seleccione **Administrar opciones de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-148">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="80fb3-149">En **Tiempo de espera de procesamiento**, seleccione **Usar configuración predeterminada del sitio** si quiere usar el valor especificado en el nivel del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="80fb3-149">In **Processing Time-out**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="80fb3-150">De lo contrario, seleccione **No agotar tiempo de espera de procesamiento de informes** o **Limitar procesamiento de informe a (en segundos)** si quiere reemplazar dicho valor por valores de tiempo de espera distintos o por ningún valor de tiempo de espera en absoluto.</span><span class="sxs-lookup"><span data-stu-id="80fb3-150">Otherwise, select **Do not time out report processing** or **Limit report processing in seconds** if you want to override that value with no time-out or different time-out values.</span></span>  
  
##  <a name="to-set-report-history-options-and-limits"></a><a name="bkmk_set_report_history"></a><span data-ttu-id="80fb3-151">Para establecer opciones y límites del historial de informes</span><span class="sxs-lookup"><span data-stu-id="80fb3-151">To set report history options and limits</span></span>  
  
1.  <span data-ttu-id="80fb3-152">Seleccione un informe en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="80fb3-152">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="80fb3-153">Haga clic en la flecha abajo y, a continuación, seleccione **Administrar opciones de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="80fb3-153">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="80fb3-154">En **Opciones de instantáneas del historial**, especifique cuándo y cómo debe producirse el procesamiento y almacenamiento de los datos.</span><span class="sxs-lookup"><span data-stu-id="80fb3-154">In **History Snapshot Options**, specify how and when data processing occurs and is saved.</span></span>  
  
4.  <span data-ttu-id="80fb3-155">En **Límites de instantáneas del historial**, seleccione **Usar configuración predeterminada del sitio** si desea utilizar el valor especificado en el nivel del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="80fb3-155">In **History Snapshot Limits**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="80fb3-156">De lo contrario, seleccione **No limitar el número de instantáneas** o **Limitar número de instantáneas a** para especificar un valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="80fb3-156">Otherwise, select **Do not limit the number of snapshots** or **Limit number of snapshots** to specify a custom value.</span></span>  
  
##  <a name="set-database-timeout"></a><a name="bkmk_set_database_timeout"></a><span data-ttu-id="80fb3-157">Establecer tiempo de espera de base de datos</span><span class="sxs-lookup"><span data-stu-id="80fb3-157">Set database timeout</span></span>  
  
1.  <span data-ttu-id="80fb3-158">Usar Windows PowerShell para establecer el tiempo de espera de la base de datos de un servidor de informes de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="80fb3-158">Use Windows PowerShell to set the database timeout of a SharePoint report server.</span></span> <span data-ttu-id="80fb3-159">Para obtener más información, vea la sección "Obtener y establecer las propiedades de la base de datos de aplicación de Reporting Services" de [Cmdlets de PowerShell para el modo de SharePoint de Reporting Services](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="80fb3-159">For more information, see the "Get and set Properties of the Reporting Service Application Database" section of [PowerShell cmdlets for Reporting Services SharePoint Mode](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fb3-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80fb3-160">See Also</span></span>  
 <span data-ttu-id="80fb3-161">[Establecer propiedades de procesamiento de informes](report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="80fb3-161">[Set Report Processing Properties](report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="80fb3-162">[Informes almacenados en caché &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80fb3-162">[Caching Reports &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span></span>  
 [<span data-ttu-id="80fb3-163">Establecer valores de tiempo de espera para el procesamiento de informes y conjuntos de datos compartidos &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="80fb3-163">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
  
  
