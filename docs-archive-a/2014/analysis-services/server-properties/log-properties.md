---
title: Propiedades del registro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- QueryLogFileSize property
- QueryLogTableName property
- TraceBackgroundDistributionPeriod property
- TraceMaxRowsetSize property
- NullKeyConvertedToUnknown property
- CrashReportsFolder property
- TraceDefinitionFile property
- SQLDumperFlagsOn property
- KeyErrorLimit property
- SnapshotDefinitionFile property
- MinidumpErrorList property
- ErrorLogFileName property
- KeyDuplicate property
- IgnoreDataTruncation property
- logs [Analysis Services]
- Enabled property
- FileSizeMB property
- TraceFileWriteTrailerPeriod property
- TraceQueryResponseTextChunkSize property
- File property
- FileBufferSize property
- TraceRowsetBackgroundFlushPeriod property
- ErrorLogFileSize property
- TraceRequestParameters property
- KeyErrorLimitAction property
- CreateQueryLogTable property
- LogDir property
- TraceBackgroundFlushPeriod property
- TraceFileBufferSize property
- SQLDumperFlagsOff property
- QueryLogConnectionString property
- KeyNotFound property
- KeyErrorLogFile property
- TraceReportFQDN property
- KeyErrorAction property
- QueryLogFileName property
- MessageLogs property
- MiniDumpFlagsOn property
- SnapshotFrequencySec property
- QueryLogSampling property
- CreateAndSendCrashReports property
- LogDurationSec property
ms.assetid: 33fd90ee-cead-48f0-8ff9-9b458994c766
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3761ce3dca232db8968a2a7cba083dcc5554d792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752385"
---
# <a name="log-properties"></a><span data-ttu-id="4277b-102">Propiedades de registro</span><span class="sxs-lookup"><span data-stu-id="4277b-102">Log Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="4277b-103">admite las propiedades de servidor de registro descritas en las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="4277b-103">supports the log server properties listed in the following tables.</span></span> <span data-ttu-id="4277b-104">Para obtener más información sobre las propiedades de servidor adicionales y cómo establecerlas, vea [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="4277b-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
## <a name="general"></a><span data-ttu-id="4277b-105">General</span><span class="sxs-lookup"><span data-stu-id="4277b-105">General</span></span>  
 `File`  
 <span data-ttu-id="4277b-106">Una propiedad de cadena que identifica el nombre del archivo de registro del servidor.</span><span class="sxs-lookup"><span data-stu-id="4277b-106">A string property that identifies the name of the server log file.</span></span> <span data-ttu-id="4277b-107">Esta propiedad solo se aplica cuando se utiliza un archivo de disco para realizar el registro, a diferencia de cuando se utiliza una tabla de base de datos (comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4277b-107">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="4277b-108">El valor predeterminado de esta propiedad es msmdsrv.log.</span><span class="sxs-lookup"><span data-stu-id="4277b-108">The default value for this property is msmdsrv.log.</span></span>  
  
 `FileBufferSize`  
 <span data-ttu-id="4277b-109">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MessageLogs`  
 <span data-ttu-id="4277b-110">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="error-log"></a><span data-ttu-id="4277b-111">Registro de errores</span><span class="sxs-lookup"><span data-stu-id="4277b-111">Error Log</span></span>  
 <span data-ttu-id="4277b-112">Puede establecer estas propiedades en la instancia de servidor level para modificar los valores predeterminados de Configuración de errores que aparecen en otras herramientas y diseñadores.</span><span class="sxs-lookup"><span data-stu-id="4277b-112">You can set these properties at the server instance level to modify the default values for Error Configuration that appear in other tools and designers.</span></span> <span data-ttu-id="4277b-113">Vea [configuración de errores para el procesamiento de cubos, particiones y dimensiones &#40;SSAS-multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) y <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4277b-113">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) and <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> for more information.</span></span>  
  
 <span data-ttu-id="4277b-114">**ErrorLog\ErrorLogFileName**</span><span class="sxs-lookup"><span data-stu-id="4277b-114">**ErrorLog\ErrorLogFileName**</span></span>  
 <span data-ttu-id="4277b-115">Una propiedad utilizada como valor predeterminado durante la operación de procesamiento realizada por el servidor.</span><span class="sxs-lookup"><span data-stu-id="4277b-115">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="4277b-116">**ErrorLog\ErrorLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="4277b-116">**ErrorLog\ErrorLogFileSize**</span></span>  
 <span data-ttu-id="4277b-117">Una propiedad utilizada como valor predeterminado durante la operación de procesamiento realizada por el servidor.</span><span class="sxs-lookup"><span data-stu-id="4277b-117">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="4277b-118">**ErrorLog\KeyErrorAction**</span><span class="sxs-lookup"><span data-stu-id="4277b-118">**ErrorLog\KeyErrorAction**</span></span>  
 <span data-ttu-id="4277b-119">Especifica la acción que realiza el servidor cuando se produce un error de `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="4277b-119">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="4277b-120">Entre las respuestas válidas a este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="4277b-120">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="4277b-121">`ConvertToUnknown` indica al servidor que asigne el valor de clave de error al miembro desconocido.</span><span class="sxs-lookup"><span data-stu-id="4277b-121">`ConvertToUnknown` tells the server to allocate the error key value to the unknown member.</span></span>  
  
-   <span data-ttu-id="4277b-122">`DiscardRecord` indica al servidor que excluya el registro.</span><span class="sxs-lookup"><span data-stu-id="4277b-122">`DiscardRecord` tells the server to exclude the record.</span></span>  
  
 <span data-ttu-id="4277b-123">**ErrorLog\KeyErrorLogFile**</span><span class="sxs-lookup"><span data-stu-id="4277b-123">**ErrorLog\KeyErrorLogFile**</span></span>  
 <span data-ttu-id="4277b-124">Es un nombre de archivo definido por el usuario que debe tener una extensión de archivo .log, situado en una carpeta para la que la cuenta de servicio tiene permisos de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="4277b-124">This is a user-defined filename that must have a .log file extension, located in a folder on which the service account has read-write permissions.</span></span> <span data-ttu-id="4277b-125">Este archivo de registro solo contendrá errores generados durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4277b-125">This log file will only contain errors generated during processing.</span></span> <span data-ttu-id="4277b-126">Use la Caja negra si necesita información más detallada.</span><span class="sxs-lookup"><span data-stu-id="4277b-126">Use the Flight Recorder if you require more detailed information.</span></span>  
  
 <span data-ttu-id="4277b-127">**ErrorLog\KeyErrorLimit**</span><span class="sxs-lookup"><span data-stu-id="4277b-127">**ErrorLog\KeyErrorLimit**</span></span>  
 <span data-ttu-id="4277b-128">Es el número máximo de errores de integridad de datos que el servidor permitirá antes de que se produzca un error de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4277b-128">This is the maximum number of data integrity errors that the server will allow before failing the processing.</span></span> <span data-ttu-id="4277b-129">Un valor de -1 indica que no hay ningún límite.</span><span class="sxs-lookup"><span data-stu-id="4277b-129">A value of -1 indicates that there is no limit.</span></span> <span data-ttu-id="4277b-130">El valor predeterminado es 0, lo que significa que el procesamiento se detiene después de producirse el primer error.</span><span class="sxs-lookup"><span data-stu-id="4277b-130">The default is 0, which means processing stops after the first error occurs.</span></span> <span data-ttu-id="4277b-131">También puede establecerlo en un número entero.</span><span class="sxs-lookup"><span data-stu-id="4277b-131">You can also set it to a whole number.</span></span>  
  
 <span data-ttu-id="4277b-132">**ErrorLog\KeyErrorLimitAction**</span><span class="sxs-lookup"><span data-stu-id="4277b-132">**ErrorLog\KeyErrorLimitAction**</span></span>  
 <span data-ttu-id="4277b-133">Especifica la acción que realiza el servidor cuando el número de errores de clave alcanza el límite superior.</span><span class="sxs-lookup"><span data-stu-id="4277b-133">Specifies the action taken by the server when the number of key errors has reached the upper limit.</span></span> <span data-ttu-id="4277b-134">Entre las respuestas válidas a esta acción se incluyen:</span><span class="sxs-lookup"><span data-stu-id="4277b-134">Valid responses to this action include:</span></span>  
  
-   <span data-ttu-id="4277b-135">`StopProcessing` indica al servidor que detenga el procesamiento cuando se alcance el límite de errores.</span><span class="sxs-lookup"><span data-stu-id="4277b-135">`StopProcessing` tells the server to stop processing when the error limit is reached.</span></span>  
  
-   <span data-ttu-id="4277b-136">`StopLogging` indica al servidor que detenga el registro de errores cuando se alcance el límite de errores, pero que permita que el procesamiento continúe.</span><span class="sxs-lookup"><span data-stu-id="4277b-136">`StopLogging` tells the server to stop logging errors when the error limit is reached, but allow processing to continue.</span></span>  
  
 <span data-ttu-id="4277b-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span><span class="sxs-lookup"><span data-stu-id="4277b-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span></span>  
 <span data-ttu-id="4277b-138">Especifica la acción que realiza el servidor cuando se produce un error de `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="4277b-138">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="4277b-139">Entre las respuestas válidas a este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="4277b-139">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="4277b-140">`IgnoreError` indica al servidor que continúe con el procesamiento sin registrar el error o contarlo de cara al límite de errores de clave.</span><span class="sxs-lookup"><span data-stu-id="4277b-140">`IgnoreError` tells the server to continue processing without logging the error or counting it towards the key error limit.</span></span> <span data-ttu-id="4277b-141">Si se omite el error, se permite que el procesamiento continúe sin agregarlo al recuento de errores o registrarlo en la pantalla o en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="4277b-141">By ignoring the error, you simply allow processing to continue without adding to the error count or logging it to the screen or log file.</span></span> <span data-ttu-id="4277b-142">El registro en cuestión tiene un problema de integridad de datos y no se puede agregar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4277b-142">The record in question has a data integrity problem and cannot be added to the database.</span></span> <span data-ttu-id="4277b-143">El registro se descartará o se agregará al Miembro desconocido, según determine la propiedad `KeyErrorAction`.</span><span class="sxs-lookup"><span data-stu-id="4277b-143">The record will either be discarded or aggregated to Unknown Member, as determined by the `KeyErrorAction` property.</span></span>  
  
-   <span data-ttu-id="4277b-144">`ReportAndContinue` indica al servidor que registre el error, lo cuente de cara al límite de errores de clave y continúe con el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4277b-144">`ReportAndContinue` tells the server to log the error, count it towards the key error limit, and continue processing.</span></span> <span data-ttu-id="4277b-145">El registro que desencadena el error se descarta o se convierte en Miembro desconocido.</span><span class="sxs-lookup"><span data-stu-id="4277b-145">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
-   <span data-ttu-id="4277b-146">`ReportAndStop` indica al servidor que registre el error y detenga el procesamiento inmediatamente, cualquiera que sea el límite de errores de clave.</span><span class="sxs-lookup"><span data-stu-id="4277b-146">`ReportAndStop` tells the server to log the error and stop processing immediately, regardless of the key error limit.</span></span> <span data-ttu-id="4277b-147">El registro que desencadena el error se descarta o se convierte en Miembro desconocido.</span><span class="sxs-lookup"><span data-stu-id="4277b-147">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
 <span data-ttu-id="4277b-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span><span class="sxs-lookup"><span data-stu-id="4277b-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span></span>  
 <span data-ttu-id="4277b-149">Especifica la acción que realiza el servidor cuando se encuentra una clave duplicada.</span><span class="sxs-lookup"><span data-stu-id="4277b-149">Specifies the action taken by the server when a duplicate key is found.</span></span> <span data-ttu-id="4277b-150">Entre los valores válidos se incluyen `IgnoreError` para continuar con el procesamiento como si el error no se hubiera producido, `ReportAndContinue` para registrar el error y continuar con el procesamiento, y `ReportAndStop` para registrar el error y detener el procesamiento inmediatamente, aunque el recuento de errores esté por debajo del límite de errores.</span><span class="sxs-lookup"><span data-stu-id="4277b-150">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="4277b-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span><span class="sxs-lookup"><span data-stu-id="4277b-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span></span>  
 <span data-ttu-id="4277b-152">Especifica la acción que realiza el servidor cuando una clave NULL se ha convertido en Miembro desconocido.</span><span class="sxs-lookup"><span data-stu-id="4277b-152">Specifies the action taken by the server when a null key has been converted to Unknown Member.</span></span> <span data-ttu-id="4277b-153">Entre los valores válidos se incluyen `IgnoreError` para continuar con el procesamiento como si el error no se hubiera producido, `ReportAndContinue` para registrar el error y continuar con el procesamiento, y `ReportAndStop` para registrar el error y detener el procesamiento inmediatamente, aunque el recuento de errores esté por debajo del límite de errores.</span><span class="sxs-lookup"><span data-stu-id="4277b-153">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="4277b-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span><span class="sxs-lookup"><span data-stu-id="4277b-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span></span>  
 <span data-ttu-id="4277b-155">Especifica la acción que realiza el servidor cuando `NullProcessing` se establece en `Error` para un atributo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="4277b-155">Specifies the action taken by the server when `NullProcessing` is set to `Error` for a dimension attribute.</span></span> <span data-ttu-id="4277b-156">Se genera un error cuando no se permite un valor NULL en un atributo determinado.</span><span class="sxs-lookup"><span data-stu-id="4277b-156">An error is generated when a null value is not allowed in a given attribute.</span></span> <span data-ttu-id="4277b-157">Esta propiedad de configuración de errores informa al paso siguiente, que es notificar el error y continuar con el procesamiento hasta que se alcance el límite de errores.</span><span class="sxs-lookup"><span data-stu-id="4277b-157">This error configuration property informs the next step, which is to report the error and continue processing until the error limit is reached.</span></span> <span data-ttu-id="4277b-158">Entre los valores válidos se incluyen `IgnoreError` para continuar con el procesamiento como si el error no se hubiera producido, `ReportAndContinue` para registrar el error y continuar con el procesamiento, y `ReportAndStop` para registrar el error y detener el procesamiento inmediatamente, aunque el recuento de errores esté por debajo del límite de errores.</span><span class="sxs-lookup"><span data-stu-id="4277b-158">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="4277b-159">**ErrorLog\ LogErrorTypes\CalculationError**</span><span class="sxs-lookup"><span data-stu-id="4277b-159">**ErrorLog\ LogErrorTypes\CalculationError**</span></span>  
 <span data-ttu-id="4277b-160">Una propiedad utilizada como valor predeterminado durante la operación de procesamiento realizada por el servidor.</span><span class="sxs-lookup"><span data-stu-id="4277b-160">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="4277b-161">**ErrorLog\IgnoreDataTruncation**</span><span class="sxs-lookup"><span data-stu-id="4277b-161">**ErrorLog\IgnoreDataTruncation**</span></span>  
 <span data-ttu-id="4277b-162">Una propiedad utilizada como valor predeterminado durante la operación de procesamiento realizada por el servidor.</span><span class="sxs-lookup"><span data-stu-id="4277b-162">A property used as a default during processing operation performed by the server.</span></span>  
  
## <a name="exception"></a><span data-ttu-id="4277b-163">Excepción</span><span class="sxs-lookup"><span data-stu-id="4277b-163">Exception</span></span>  
 <span data-ttu-id="4277b-164">**Exception\CreateAndSendCrashReports**</span><span class="sxs-lookup"><span data-stu-id="4277b-164">**Exception\CreateAndSendCrashReports**</span></span>  
 <span data-ttu-id="4277b-165">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-165">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-166">**Exception\CrashReportsFolder**</span><span class="sxs-lookup"><span data-stu-id="4277b-166">**Exception\CrashReportsFolder**</span></span>  
 <span data-ttu-id="4277b-167">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-167">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-168">**Exception\SQLDumperFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="4277b-168">**Exception\SQLDumperFlagsOn**</span></span>  
 <span data-ttu-id="4277b-169">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-170">**Exception\SQLDumperFlagsOff**</span><span class="sxs-lookup"><span data-stu-id="4277b-170">**Exception\SQLDumperFlagsOff**</span></span>  
 <span data-ttu-id="4277b-171">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-172">**Exception\MiniDumpFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="4277b-172">**Exception\MiniDumpFlagsOn**</span></span>  
 <span data-ttu-id="4277b-173">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-173">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-174">**Exception\MinidumpErrorList**</span><span class="sxs-lookup"><span data-stu-id="4277b-174">**Exception\MinidumpErrorList**</span></span>  
 <span data-ttu-id="4277b-175">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-175">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="flight-recorder"></a><span data-ttu-id="4277b-176">Caja negra SQL</span><span class="sxs-lookup"><span data-stu-id="4277b-176">Flight Recorder</span></span>  
 <span data-ttu-id="4277b-177">**FlightRecorder\Enabled**</span><span class="sxs-lookup"><span data-stu-id="4277b-177">**FlightRecorder\Enabled**</span></span>  
 <span data-ttu-id="4277b-178">Una propiedad booleana que indica si la característica Caja negra SQL está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4277b-178">A Boolean property that indicates whether the flight recorder feature is enabled.</span></span>  
  
 <span data-ttu-id="4277b-179">**FlightRecorder\FileSizeMB**</span><span class="sxs-lookup"><span data-stu-id="4277b-179">**FlightRecorder\FileSizeMB**</span></span>  
 <span data-ttu-id="4277b-180">Una propiedad de entero de 32 bits con signo que define el tamaño del archivo de disco de la caja negra SQL, en megabytes.</span><span class="sxs-lookup"><span data-stu-id="4277b-180">A signed 32-bit integer property that defines the size of the flight recorder disk file, in megabytes.</span></span>  
  
 <span data-ttu-id="4277b-181">**FlightRecorder\LogDurationSec**</span><span class="sxs-lookup"><span data-stu-id="4277b-181">**FlightRecorder\LogDurationSec**</span></span>  
 <span data-ttu-id="4277b-182">Una propiedad de entero de 32 bits con signo que define la frecuencia con la que se activa la caja negra SQL, en segundos.</span><span class="sxs-lookup"><span data-stu-id="4277b-182">A signed 32-bit integer property that defines the frequency that the flight recorder is rolled over, in seconds.</span></span>  
  
 <span data-ttu-id="4277b-183">**FlightRecorder\SnapshotDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="4277b-183">**FlightRecorder\SnapshotDefinitionFile**</span></span>  
 <span data-ttu-id="4277b-184">Una propiedad de cadena que define el nombre del archivo de definición de instantáneas, que contiene comandos de descubrimiento que se emiten al servidor cuando se toma una instantánea.</span><span class="sxs-lookup"><span data-stu-id="4277b-184">A string property that defines the name of the snapshot definition file, containing discover commands that are issued to the server when a snapshot is taken.</span></span>  
  
 <span data-ttu-id="4277b-185">El valor predeterminado para esta propiedad está en blanco, que a su vez establece el valor predeterminado en el nombre de archivo FlightRecorderSnapshotDef.xml.</span><span class="sxs-lookup"><span data-stu-id="4277b-185">The default value for this property is blank, which in turn defaults to file name FlightRecorderSnapshotDef.xml.</span></span>  
  
 <span data-ttu-id="4277b-186">**FlightRecorder\SnapshotFrequencySec**</span><span class="sxs-lookup"><span data-stu-id="4277b-186">**FlightRecorder\SnapshotFrequencySec**</span></span>  
 <span data-ttu-id="4277b-187">Una propiedad de entero de 32 bits con signo que define la frecuencia de instantáneas, en segundos.</span><span class="sxs-lookup"><span data-stu-id="4277b-187">A signed 32-bit integer property that defines the snapshot frequency, in seconds.</span></span>  
  
 <span data-ttu-id="4277b-188">**FlightRecorder\TraceDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="4277b-188">**FlightRecorder\TraceDefinitionFile**</span></span>  
 <span data-ttu-id="4277b-189">Una propiedad de cadena que especifica el nombre del archivo de definición de seguimiento de la Caja negra SQL.</span><span class="sxs-lookup"><span data-stu-id="4277b-189">A string property that specifies the name of the flight recorder trace definition file.</span></span>  
  
 <span data-ttu-id="4277b-190">El valor predeterminado para esta propiedad está en blanco, que a su vez establece el valor predeterminado en FlightRecorderTraceDef.xml.</span><span class="sxs-lookup"><span data-stu-id="4277b-190">The default value for this property is blank, which in turn defaults to FlightRecorderTraceDef.xml.</span></span>  
  
## <a name="query-log"></a><span data-ttu-id="4277b-191">Registro de consultas</span><span class="sxs-lookup"><span data-stu-id="4277b-191">Query Log</span></span>  
 <span data-ttu-id="4277b-192">**Se aplica a:** Modo de servidor multidimensional únicamente</span><span class="sxs-lookup"><span data-stu-id="4277b-192">**Applies to:** Multidimensional server mode only</span></span>  
  
 <span data-ttu-id="4277b-193">**QueryLog\QueryLogFileName**</span><span class="sxs-lookup"><span data-stu-id="4277b-193">**QueryLog\QueryLogFileName**</span></span>  
 <span data-ttu-id="4277b-194">Una propiedad de cadena que especifica el nombre del archivo de registro de consultas.</span><span class="sxs-lookup"><span data-stu-id="4277b-194">A string property that specifies the name of the query log file.</span></span> <span data-ttu-id="4277b-195">Esta propiedad solo se aplica cuando se utiliza un archivo de disco para realizar el registro, a diferencia de cuando se utiliza una tabla de base de datos (comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4277b-195">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="4277b-196">**QueryLog\QueryLogSampling**</span><span class="sxs-lookup"><span data-stu-id="4277b-196">**QueryLog\QueryLogSampling**</span></span>  
 <span data-ttu-id="4277b-197">Una propiedad de entero de 32 bits que especifica la velocidad de muestreo del registro de consultas.</span><span class="sxs-lookup"><span data-stu-id="4277b-197">A signed 32-bit integer property that specifies the query log sampling rate.</span></span>  
  
 <span data-ttu-id="4277b-198">El valor predeterminado para esta propiedad es 10, lo que significa que se ha registrado 1 de cada 10 consultas del servidor.</span><span class="sxs-lookup"><span data-stu-id="4277b-198">The default value for this property is 10, meaning that 1 out of every 10 server queries is logged.</span></span>  
  
 <span data-ttu-id="4277b-199">**QueryLog\QueryLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="4277b-199">**QueryLog\QueryLogFileSize**</span></span>  
 <span data-ttu-id="4277b-200">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-200">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-201">**QueryLog\QueryLogConnectionString**</span><span class="sxs-lookup"><span data-stu-id="4277b-201">**QueryLog\QueryLogConnectionString**</span></span>  
 <span data-ttu-id="4277b-202">Una propiedad de cadena que especifica la conexión con la base de datos del registro de consultas.</span><span class="sxs-lookup"><span data-stu-id="4277b-202">A string property that specifies the connection to the query log database.</span></span>  
  
 <span data-ttu-id="4277b-203">**QueryLog\QueryLogTableName**</span><span class="sxs-lookup"><span data-stu-id="4277b-203">**QueryLog\QueryLogTableName**</span></span>  
 <span data-ttu-id="4277b-204">Una propiedad de cadena que especifica el nombre de la tabla del registro de consultas.</span><span class="sxs-lookup"><span data-stu-id="4277b-204">A string property that specifies the name of the query log table.</span></span>  
  
 <span data-ttu-id="4277b-205">El valor predeterminado de esta propiedad es OlapQueryLog.</span><span class="sxs-lookup"><span data-stu-id="4277b-205">The default value for this property is OlapQueryLog.</span></span>  
  
 <span data-ttu-id="4277b-206">**QueryLog\CreateQueryLogTable**</span><span class="sxs-lookup"><span data-stu-id="4277b-206">**QueryLog\CreateQueryLogTable**</span></span>  
 <span data-ttu-id="4277b-207">Una propiedad booleana que especifica si se crea la tabla del registro de consultas.</span><span class="sxs-lookup"><span data-stu-id="4277b-207">A Boolean property that specifies whether to create the query log table.</span></span>  
  
 <span data-ttu-id="4277b-208">El valor predeterminado para esta propiedad es False, que indica que el servidor no creará automáticamente la tabla del registro y no registrará eventos de consulta.</span><span class="sxs-lookup"><span data-stu-id="4277b-208">The default value for this property is false, which indicates the server will not automatically create the log table and will not log query events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4277b-209">Para obtener más información acerca de cómo configurar el registro de consultas, consulte [operaciones de registro en Analysis Services](../instances/log-operations-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="4277b-209">For more information about configuring the query log, see [Log operations in Analysis Services](../instances/log-operations-in-analysis-services.md).</span></span>  
  
## <a name="trace"></a><span data-ttu-id="4277b-210">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="4277b-210">Trace</span></span>  
 <span data-ttu-id="4277b-211">**Trace\TraceBackgroundDistributionPeriod**</span><span class="sxs-lookup"><span data-stu-id="4277b-211">**Trace\TraceBackgroundDistributionPeriod**</span></span>  
 <span data-ttu-id="4277b-212">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-212">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-213">**Trace\TraceBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="4277b-213">**Trace\TraceBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="4277b-214">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-215">**Trace\TraceFileBufferSize**</span><span class="sxs-lookup"><span data-stu-id="4277b-215">**Trace\TraceFileBufferSize**</span></span>  
 <span data-ttu-id="4277b-216">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-216">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-217">**Trace\TraceFileWriteTrailerPeriod**</span><span class="sxs-lookup"><span data-stu-id="4277b-217">**Trace\TraceFileWriteTrailerPeriod**</span></span>  
 <span data-ttu-id="4277b-218">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-219">**Trace\TraceMaxRowsetSize**</span><span class="sxs-lookup"><span data-stu-id="4277b-219">**Trace\TraceMaxRowsetSize**</span></span>  
 <span data-ttu-id="4277b-220">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-221">**Trace\TraceProtocolTraffic**</span><span class="sxs-lookup"><span data-stu-id="4277b-221">**Trace\TraceProtocolTraffic**</span></span>  
 <span data-ttu-id="4277b-222">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-222">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-223">**Trace\TraceQueryResponseTextChunkSize**</span><span class="sxs-lookup"><span data-stu-id="4277b-223">**Trace\TraceQueryResponseTextChunkSize**</span></span>  
 <span data-ttu-id="4277b-224">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-225">**Trace\TraceReportFQDN**</span><span class="sxs-lookup"><span data-stu-id="4277b-225">**Trace\TraceReportFQDN**</span></span>  
 <span data-ttu-id="4277b-226">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-226">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-227">**Trace\TraceRequestParameters**</span><span class="sxs-lookup"><span data-stu-id="4277b-227">**Trace\TraceRequestParameters**</span></span>  
 <span data-ttu-id="4277b-228">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="4277b-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="4277b-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="4277b-230">Una propiedad avanzada que no debería cambiar, salvo a petición de expertos en soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4277b-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4277b-231">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4277b-231">See Also</span></span>  
 <span data-ttu-id="4277b-232">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4277b-232">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="4277b-233">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4277b-233">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
