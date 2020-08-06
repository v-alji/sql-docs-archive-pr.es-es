---
title: Tratamiento de errores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ff79e19d-afca-42a4-81b0-62d759380d11
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 083af496c60fb11afaf85068ba980e54986134d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744277"
---
# <a name="error-handling"></a><span data-ttu-id="336f6-102">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="336f6-102">Error Handling</span></span>
  <span data-ttu-id="336f6-103">Una instancia CDC de Oracle realiza minería de datos en los cambios de una sola base de datos de origen de Oracle (un clúster de Oracle RAC se considera una sola base de datos) y escribe los cambios confirmados en las tablas de cambios en una base de datos CDC en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="336f6-103">An Oracle CDC Instance mines changes from a single Oracle source database (an Oracle RAC cluster is considered a single database) and writes the committed changes to change tables in a CDC database in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="336f6-104">Una instancia CDC mantiene su estado en una tabla del sistema denominada **cdc.xdbcdc_state**.</span><span class="sxs-lookup"><span data-stu-id="336f6-104">A CDC Instance maintains its state in a system table called **cdc.xdbcdc_state**.</span></span> <span data-ttu-id="336f6-105">Esta tabla se puede consultar en cualquier momento para conocer el estado de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="336f6-105">This table can be queried any time to find the state of the CDC Instance.</span></span> <span data-ttu-id="336f6-106">Para obtener más información sobre la tabla cdc.xdbcdc_state, vea [cdc.xdbcdc_state](the-oracle-cdc-databases.md#bkmk_cdcxdbcdc_state).</span><span class="sxs-lookup"><span data-stu-id="336f6-106">For more information about the cdc.xdbcdc_state table, see [cdc.xdbcdc_state](the-oracle-cdc-databases.md#bkmk_cdcxdbcdc_state).</span></span>  
  
 <span data-ttu-id="336f6-107">En la tabla siguiente se describen los estados de la instancia CDC en la tabla xdbcdc_state.</span><span class="sxs-lookup"><span data-stu-id="336f6-107">The table below describes the CDC Instance states in the xdbcdc_state table.</span></span>  
  
 <span data-ttu-id="336f6-108">Para cada estado, se muestran las dos indicaciones siguientes para las columnas correspondientes de la tabla cdc.xdbcdc_state:</span><span class="sxs-lookup"><span data-stu-id="336f6-108">For each state, the following two indications are shown for the corresponding columns in the cdc.xdbcdc_state table:</span></span>  
  
-   <span data-ttu-id="336f6-109">La instancia no está activa (no hay ningún proceso de Windows que la administra actualmente).</span><span class="sxs-lookup"><span data-stu-id="336f6-109">Instance is not active (there is no Windows process currently handling it).</span></span> <span data-ttu-id="336f6-110">Si el valor de la columna **active** es 1, se está ejecutando un subproceso del servicio CDC de Oracle que administra esta instancia CDC de Oracle específica.</span><span class="sxs-lookup"><span data-stu-id="336f6-110">If the **active** column value is 1, a subprocess of the Oracle CDC Service handling this specific Oracle CDC Instance is running.</span></span>  
  
-   <span data-ttu-id="336f6-111">Si el valor de la columna **error** es 0, la instancia CDC de Oracle no está en una condición de error.</span><span class="sxs-lookup"><span data-stu-id="336f6-111">If the **error** column value is 0, the Oracle CDC Instance is not in an error condition.</span></span> <span data-ttu-id="336f6-112">Si el valor de la columna **error** es 1, hay un error que impide que la instancia CDC de Oracle procese cambios.</span><span class="sxs-lookup"><span data-stu-id="336f6-112">If the **error** column value is 1, there is an error that prevents the Oracle CDC Instance from processing changes.</span></span>  
  
     <span data-ttu-id="336f6-113">Si la columna **error** tiene el valor 1 y el valor de la columna **active** es también 1, se está produciendo un error recuperable para la instancia CDC de Oracle, que se puede resolver automáticamente.</span><span class="sxs-lookup"><span data-stu-id="336f6-113">If the **error** column has a value of 1 and the **active** column value is also 1, then a recoverable error is occurring for the Oracle CDC Instance, which can be resolved automatically.</span></span> <span data-ttu-id="336f6-114">Si la columna error tiene un valor de 1 y la columna active tiene el valor 0, en la mayoría de los casos puede ser necesaria una solución manual para resolver el problema antes de que el procesamiento se puede reanudar.</span><span class="sxs-lookup"><span data-stu-id="336f6-114">If the error column has a value of 1 and the active column has a value of 0, then in most cases a manual workaround may be needed to resolve the problem before processing can be resumed.</span></span>  
  
 <span data-ttu-id="336f6-115">En la tabla siguiente se describen los distintos códigos de estado que la instancia CDC de Oracle puede notificar en su tabla de estado.</span><span class="sxs-lookup"><span data-stu-id="336f6-115">The following table describes the various status codes that the Oracle CDC Instance may report in its state table.</span></span>  
  
|<span data-ttu-id="336f6-116">Estado</span><span class="sxs-lookup"><span data-stu-id="336f6-116">Status</span></span>|<span data-ttu-id="336f6-117">Código de estado de active</span><span class="sxs-lookup"><span data-stu-id="336f6-117">Active Status Code</span></span>|<span data-ttu-id="336f6-118">Código de estado de error</span><span class="sxs-lookup"><span data-stu-id="336f6-118">Error Status Code</span></span>|<span data-ttu-id="336f6-119">Descripciones</span><span class="sxs-lookup"><span data-stu-id="336f6-119">Descriptions</span></span>|  
|------------|------------------------|-----------------------|------------------|  
|<span data-ttu-id="336f6-120">ABORTED</span><span class="sxs-lookup"><span data-stu-id="336f6-120">ABORTED</span></span>|<span data-ttu-id="336f6-121">0</span><span class="sxs-lookup"><span data-stu-id="336f6-121">0</span></span>|<span data-ttu-id="336f6-122">1</span><span class="sxs-lookup"><span data-stu-id="336f6-122">1</span></span>|<span data-ttu-id="336f6-123">La instancia CDC de Oracle no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="336f6-123">The Oracle CDC Instance is not running.</span></span> <span data-ttu-id="336f6-124">El subestado ABORTED indica que la instancia CDC de Oracle estaba ACTIVE y se ha detenido inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="336f6-124">The ABORTED substatus indicates that the Oracle CDC Instance was ACTIVE and then has stopped unexpectedly.</span></span><br /><br /> <span data-ttu-id="336f6-125">La instancia principal del servicio CDC de Oracle establece el subestado ABORTED cuando detecta que la instancia CDC de Oracle no se está ejecutando mientras su estado es ACTIVE.</span><span class="sxs-lookup"><span data-stu-id="336f6-125">The ABORTED substatus is established by the Oracle CDC Service main instance when it detects that the Oracle CDC Instance is not running while its status is ACTIVE.</span></span>|  
|<span data-ttu-id="336f6-126">ERROR</span><span class="sxs-lookup"><span data-stu-id="336f6-126">ERROR</span></span>|<span data-ttu-id="336f6-127">0</span><span class="sxs-lookup"><span data-stu-id="336f6-127">0</span></span>|<span data-ttu-id="336f6-128">1</span><span class="sxs-lookup"><span data-stu-id="336f6-128">1</span></span>|<span data-ttu-id="336f6-129">La instancia CDC de Oracle no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="336f6-129">The Oracle CDC Instance is not running.</span></span> <span data-ttu-id="336f6-130">El estado ERROR indica que la instancia CDC estaba ACTIVE pero encontró un error no recuperable y se deshabilitó a sí misma.</span><span class="sxs-lookup"><span data-stu-id="336f6-130">The ERROR status indicates that the CDC instance was ACTIVE but then encountered an error that is not recoverable and disabled itself.</span></span> <span data-ttu-id="336f6-131">El estado ERROR contiene los códigos de subestado siguientes:</span><span class="sxs-lookup"><span data-stu-id="336f6-131">The ERROR status contains the following substatus codes:</span></span><br /><br /> <span data-ttu-id="336f6-132">MISCONFIGURED: se detectó un error de configuración irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="336f6-132">MISCONFIGURED: An unrecoverable configuration error was detected.</span></span><br /><br /> <span data-ttu-id="336f6-133">PASSWORD-REQUIRED: no hay ninguna contraseña establecida en Change Data Capture Designer para Oracle de Attunity o la contraseña configurada no es válida.</span><span class="sxs-lookup"><span data-stu-id="336f6-133">PASSWORD-REQUIRED: There is no password set for the Change Data Capture Designer for Oracle by Attunity or the configured password is not valid.</span></span> <span data-ttu-id="336f6-134">Esto puede deberse a un cambio en la contraseña de clave asimétrica del servicio.</span><span class="sxs-lookup"><span data-stu-id="336f6-134">This can be because of a change to the service asymmetric key password.</span></span>|  
|<span data-ttu-id="336f6-135">RUNNING</span><span class="sxs-lookup"><span data-stu-id="336f6-135">RUNNING</span></span>|<span data-ttu-id="336f6-136">1</span><span class="sxs-lookup"><span data-stu-id="336f6-136">1</span></span>|<span data-ttu-id="336f6-137">0</span><span class="sxs-lookup"><span data-stu-id="336f6-137">0</span></span>|<span data-ttu-id="336f6-138">La instancia CDC se está ejecutando y está procesando registros de cambios.</span><span class="sxs-lookup"><span data-stu-id="336f6-138">The CDC instance is running and is processing change records.</span></span> <span data-ttu-id="336f6-139">El estado RUNNING contiene los códigos de subestado siguientes:</span><span class="sxs-lookup"><span data-stu-id="336f6-139">The RUNNING status contains the following substatus codes:</span></span><br /><br /> <span data-ttu-id="336f6-140">IDLE: todos los registros de cambios se han procesado y almacenado en las tablas de control de destino ( **_CT**).</span><span class="sxs-lookup"><span data-stu-id="336f6-140">IDLE: All change records were processed and stored into the target control (**_CT**) tables.</span></span> <span data-ttu-id="336f6-141">No hay ninguna transacción activa con las tablas de control.</span><span class="sxs-lookup"><span data-stu-id="336f6-141">There is no active transaction with the control tables.</span></span><br /><br /> <span data-ttu-id="336f6-142">PROCESSING: hay registros de cambios que se están procesando y que no se han escrito todavía en las tablas de control ( **_CT**).</span><span class="sxs-lookup"><span data-stu-id="336f6-142">PROCESSING: There are change records being processed that are not yet written to the control (**_CT**) tables.</span></span>|  
|<span data-ttu-id="336f6-143">STOPPED</span><span class="sxs-lookup"><span data-stu-id="336f6-143">STOPPED</span></span>|<span data-ttu-id="336f6-144">0</span><span class="sxs-lookup"><span data-stu-id="336f6-144">0</span></span>|<span data-ttu-id="336f6-145">0</span><span class="sxs-lookup"><span data-stu-id="336f6-145">0</span></span>|<span data-ttu-id="336f6-146">La instancia CDC no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="336f6-146">The CDC instance is not running.</span></span> <span data-ttu-id="336f6-147">El subestado STOP indica que la instancia CDC estaba ACTIVE y se detuvo correctamente.</span><span class="sxs-lookup"><span data-stu-id="336f6-147">The STOP substatus indicates that the CDC instance was ACTIVE and then was stopped correctly.</span></span>|  
|<span data-ttu-id="336f6-148">SUSPENDED</span><span class="sxs-lookup"><span data-stu-id="336f6-148">SUSPENDED</span></span>|<span data-ttu-id="336f6-149">1</span><span class="sxs-lookup"><span data-stu-id="336f6-149">1</span></span>|<span data-ttu-id="336f6-150">1</span><span class="sxs-lookup"><span data-stu-id="336f6-150">1</span></span>|<span data-ttu-id="336f6-151">La instancia CDC se está ejecutando pero el procesamiento está suspendido debido a un error recuperable.</span><span class="sxs-lookup"><span data-stu-id="336f6-151">The CDC instance is running but processing is suspended due to a recoverable error.</span></span> <span data-ttu-id="336f6-152">El estado SUSPENDED contiene los códigos de subestado siguientes:</span><span class="sxs-lookup"><span data-stu-id="336f6-152">The SUSPENDED status contains the following substatus codes:</span></span><br /><br /> <span data-ttu-id="336f6-153">DISCONNECTED: no se puede establecer la conexión con la base de datos Oracle de origen.</span><span class="sxs-lookup"><span data-stu-id="336f6-153">DISCONNECTED: The connection with the source Oracle database cannot be established.</span></span> <span data-ttu-id="336f6-154">El procesamiento se reanudará una vez que se restaure la conexión.</span><span class="sxs-lookup"><span data-stu-id="336f6-154">Processing will resume once connection is restored.</span></span><br /><br /> <span data-ttu-id="336f6-155">STORAGE: el almacenamiento está lleno.</span><span class="sxs-lookup"><span data-stu-id="336f6-155">STORAGE: The storage is full.</span></span> <span data-ttu-id="336f6-156">El procesamiento se reanudará cuando haya disponible más almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="336f6-156">Processing will resume when storage becomes available.</span></span> <span data-ttu-id="336f6-157">En algunos casos, este estado puede no aparecer porque la tabla de estado no se puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="336f6-157">In some cases, this status may not appear because the status table cannot be updated.</span></span><br /><br /> <span data-ttu-id="336f6-158">LOGGER: el registrador está conectado a Oracle pero no puede leer los registros de transacciones de Oracle debido a un problema temporal.</span><span class="sxs-lookup"><span data-stu-id="336f6-158">LOGGER: The logger is connected to Oracle but it cannot read the Oracle transaction logs because of a temporary problem.</span></span>|  
|<span data-ttu-id="336f6-159">DATAERROR</span><span class="sxs-lookup"><span data-stu-id="336f6-159">DATAERROR</span></span>|<span data-ttu-id="336f6-160">x</span><span class="sxs-lookup"><span data-stu-id="336f6-160">x</span></span>|<span data-ttu-id="336f6-161">x</span><span class="sxs-lookup"><span data-stu-id="336f6-161">x</span></span>|<span data-ttu-id="336f6-162">Este código de estado solo se usa para la tabla **xdbcdc_trace** .</span><span class="sxs-lookup"><span data-stu-id="336f6-162">This status code is only used for the **xdbcdc_trace** table.</span></span> <span data-ttu-id="336f6-163">No aparece en la tabla **xdbcdc_state** .</span><span class="sxs-lookup"><span data-stu-id="336f6-163">It does not appear in the **xdbcdc_state** table.</span></span> <span data-ttu-id="336f6-164">Los registros de seguimiento que tienen este estado indican un problema con una entrada de registro de Oracle.</span><span class="sxs-lookup"><span data-stu-id="336f6-164">Trace records with this status indicate a problem with an Oracle log record.</span></span> <span data-ttu-id="336f6-165">La entrada de registro no válida se almacena en la columna **data** como un BLOB.</span><span class="sxs-lookup"><span data-stu-id="336f6-165">The bad log record is stored in the **data** column as a BLOB.</span></span> <span data-ttu-id="336f6-166">El estado DATAERROR contiene los códigos de subestado siguientes:</span><span class="sxs-lookup"><span data-stu-id="336f6-166">The DATAERROR status contains the following substatus codes:</span></span><br /><br /> <span data-ttu-id="336f6-167">BADRECORD: la entrada de registro adjunta no se pudo analizar.</span><span class="sxs-lookup"><span data-stu-id="336f6-167">BADRECORD: The attached log record could not be parsed.</span></span><br /><br /> <span data-ttu-id="336f6-168">CONVERT-ERROR: los datos de algunas columnas no se pudieron convertir a las columnas de destino de la tabla de captura.</span><span class="sxs-lookup"><span data-stu-id="336f6-168">CONVERT-ERROR: The data in some columns could not be converted to the target columns in the capture table.</span></span> <span data-ttu-id="336f6-169">Este estado puede aparecer solo si la configuración especifica que los errores de conversión deben producir registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="336f6-169">This status may appear only if the configuration specifies that conversion errors should produce trace records.</span></span>|  
  
 <span data-ttu-id="336f6-170">Puesto que el estado del servicio CDC de Oracle se almacena en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede haber casos en los que el valor de estado de la base de datos no refleje el estado actual del servicio.</span><span class="sxs-lookup"><span data-stu-id="336f6-170">Because the Oracle CDC Service state is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], there may be cases where the state value in the database might not reflect the actual state of the service.</span></span> <span data-ttu-id="336f6-171">El escenario más común es cuando el servicio pierde su conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no se puede reanudar (por cualquier motivo).</span><span class="sxs-lookup"><span data-stu-id="336f6-171">The most common scenario is when the service loses its connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and cannot resume it (for any reason).</span></span> <span data-ttu-id="336f6-172">En ese caso, el estado almacenado en **cdc.xdbcdc_state** se queda obsoleto.</span><span class="sxs-lookup"><span data-stu-id="336f6-172">In that case, the state stored in **cdc.xdbcdc_state** becomes stale.</span></span> <span data-ttu-id="336f6-173">Si la marca de tiempo (UTC) de la última actualización tiene más de un minuto de antigüedad, probablemente el estado esté obsoleto.</span><span class="sxs-lookup"><span data-stu-id="336f6-173">If the last update timestamp (UTC) is more than a minute old, the state is probably stale.</span></span> <span data-ttu-id="336f6-174">En este caso, use el Visor de eventos de Windows para buscar información adicional sobre el estado del servicio.</span><span class="sxs-lookup"><span data-stu-id="336f6-174">In this case, use the Windows Event Viewer to find additional information about the status of the service.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="336f6-175">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="336f6-175">Error Handling</span></span>  
 <span data-ttu-id="336f6-176">En esta sección se describe cómo trata los errores el servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="336f6-176">This section describes how the Oracle CDC Service handles errors.</span></span>  
  
### <a name="logging"></a><span data-ttu-id="336f6-177">Registro</span><span class="sxs-lookup"><span data-stu-id="336f6-177">Logging</span></span>  
 <span data-ttu-id="336f6-178">El servicio CDC de Oracle crea información de error en uno de los lugares siguientes.</span><span class="sxs-lookup"><span data-stu-id="336f6-178">The Oracle CDC Service creates error information in one of the following places.</span></span>  
  
-   <span data-ttu-id="336f6-179">El registro de eventos de Windows, que se emplea con los errores de registro y para indicar eventos del ciclo de vida del servicio CDC de Oracle (iniciar, detener, conectar o volver a conectar con la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino).</span><span class="sxs-lookup"><span data-stu-id="336f6-179">The Windows event log, which is used with logging errors and to indicate Oracle CDC Service life cycle events (starting, stopping, (re)connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance).</span></span>  
  
-   <span data-ttu-id="336f6-180">La tabla MSXDBCDC.dbo.xdbcdc_trace, que el proceso principal del servicio CDC de Oracle emplea para el registro y el seguimiento generales.</span><span class="sxs-lookup"><span data-stu-id="336f6-180">The MSXDBCDC.dbo.xdbcdc_trace table, which is used for general logging and tracing by the Oracle CDC Service main process.</span></span>  
  
-   <span data-ttu-id="336f6-181">La tabla \<cdc-database>.cdc.xdbcdc_trace, que las instancias de CDC de Oracle usan para el registro y el seguimiento generales.</span><span class="sxs-lookup"><span data-stu-id="336f6-181">The \<cdc-database>.cdc.xdbcdc_trace table, which is used for general logging and tracing by Oracle CDC Instances.</span></span> <span data-ttu-id="336f6-182">Esto significa que los errores relacionados con una instancia CDC de Oracle específica se registran en la tabla de seguimiento de esa instancia.</span><span class="sxs-lookup"><span data-stu-id="336f6-182">This means that errors related to a specific Oracle CDC Instance are logged to that instance's trace table.</span></span>  
  
 <span data-ttu-id="336f6-183">El servicio CDC de Oracle registra información cuando el servicio:</span><span class="sxs-lookup"><span data-stu-id="336f6-183">Information is logged by the Oracle CDC service when the service:</span></span>  
  
-   <span data-ttu-id="336f6-184">Es iniciado o detenido por el administrador de control de servicios.</span><span class="sxs-lookup"><span data-stu-id="336f6-184">Is started or stopped by the service control manager.</span></span>  
  
-   <span data-ttu-id="336f6-185">No se puede conectar con la instancia asociada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y cuando establece correctamente una conexión después de un error.</span><span class="sxs-lookup"><span data-stu-id="336f6-185">Cannot connect to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and when it successfully establishes a connection following a failure.</span></span>  
  
-   <span data-ttu-id="336f6-186">Detecta un error al iniciar instancias de servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="336f6-186">Encounters an error starting Oracle CDC Service instances.</span></span>  
  
-   <span data-ttu-id="336f6-187">Detecta que una instancia CDC de Oracle se ha anulado.</span><span class="sxs-lookup"><span data-stu-id="336f6-187">Detects that an Oracle CDC Instance has aborted.</span></span>  
  
-   <span data-ttu-id="336f6-188">Detecta un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="336f6-188">Encounters an unexpected error.</span></span>  
  
 <span data-ttu-id="336f6-189">La instancia CDC registra información cuando la instancia:</span><span class="sxs-lookup"><span data-stu-id="336f6-189">Information is logged by the CDC instance when the instance:</span></span>  
  
-   <span data-ttu-id="336f6-190">Se habilita o deshabilita.</span><span class="sxs-lookup"><span data-stu-id="336f6-190">Is enabled or disabled.</span></span>  
  
-   <span data-ttu-id="336f6-191">Detecta un error.</span><span class="sxs-lookup"><span data-stu-id="336f6-191">Encounters an error.</span></span>  
  
-   <span data-ttu-id="336f6-192">Se recupera de un error recuperable.</span><span class="sxs-lookup"><span data-stu-id="336f6-192">Recovers from a recoverable error.</span></span>  
  
 <span data-ttu-id="336f6-193">La tabla de seguimiento también se usa para registrar información de seguimiento detallada para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="336f6-193">The trace table is also used for recording detailed trace information for troubleshooting.</span></span>  
  
### <a name="handling-source-oracle-connection-errors"></a><span data-ttu-id="336f6-194">Controlar los errores de conexión de Oracle de origen</span><span class="sxs-lookup"><span data-stu-id="336f6-194">Handling Source Oracle Connection Errors</span></span>  
 <span data-ttu-id="336f6-195">El servicio CDC de Oracle necesita una conexión persistente con la base de datos de Oracle de origen.</span><span class="sxs-lookup"><span data-stu-id="336f6-195">The Oracle CDC Service needs a persistent connection with the source Oracle database.</span></span> <span data-ttu-id="336f6-196">Muchos errores de conexión que no están relacionadas con la configuración del servicio (como errores de red) se consideran transitorios.</span><span class="sxs-lookup"><span data-stu-id="336f6-196">Many connection errors that are unrelated to the service configuration (such as networking errors) are considered transient.</span></span> <span data-ttu-id="336f6-197">Por tanto, si el servicio CDC de Oracle no puede establecer conexión con la base de datos de Oracle (en el inicio o durante el trabajo que sigue a una desconexión), el servicio cambia su estado a SUSPENDED/DISCONNECTED y entra en un bucle de reintentos en el que la conexión se vuelve a intentar periódicamente.</span><span class="sxs-lookup"><span data-stu-id="336f6-197">Therefore, if the Oracle CDC Service cannot establish connection with the Oracle database (either on start or during work following a disconnection), the service changes its state to SUSPENDED/DISCONNECTED and enters a retry loop where the connection is retried at regular intervals.</span></span> <span data-ttu-id="336f6-198">Cuando se restablece la conexión, el procesamiento continúa.</span><span class="sxs-lookup"><span data-stu-id="336f6-198">When the connection is re-established, processing continues.</span></span>  
  
 <span data-ttu-id="336f6-199">Otros tipos de errores de conexión no son transitorios (por ejemplo, credenciales no válidas, privilegios insuficientes y una dirección de base de datos no válida).</span><span class="sxs-lookup"><span data-stu-id="336f6-199">Other types of connection errors are not transient (for example, bad credentials, insufficient privileges, and bad database address).</span></span> <span data-ttu-id="336f6-200">Cuando se producen estos errores, el estado del servicio CDC de Oracle se establece en ERROR/MISCONFIGURED o en ERROR/PASSWORD-REQUIRED y el servicio se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="336f6-200">When these errors occur, the Oracle CDC Service state is set to ERROR/MISCONFIGURED or to ERROR/PASSWORD-REQUIRED and the service is disabled.</span></span> <span data-ttu-id="336f6-201">Cuando el usuario corrige el error subyacente, la instancia CDC de Oracle debe volver a habilitarse manualmente para que el procesamiento se reanude.</span><span class="sxs-lookup"><span data-stu-id="336f6-201">When the user fixes the underlying error, the Oracle CDC Instance should be manually re-enabled for processing to resume.</span></span>  
  
 <span data-ttu-id="336f6-202">Cuando no está claro si el error es transitorio, lo mejor es suponer que es transitorio.</span><span class="sxs-lookup"><span data-stu-id="336f6-202">When it is not clear whether the error is transient, it is best to assume it is transient.</span></span>  
  
### <a name="handling-target-sql-server-connection-errors"></a><span data-ttu-id="336f6-203">Controlar errores de conexión con SQL Server de destino</span><span class="sxs-lookup"><span data-stu-id="336f6-203">Handling Target SQL Server Connection Errors</span></span>  
 <span data-ttu-id="336f6-204">El servicio CDC de Oracle necesita una conexión persistente con la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="336f6-204">The Oracle CDC Service needs a persistent connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="336f6-205">Esta conexión se emplea para:</span><span class="sxs-lookup"><span data-stu-id="336f6-205">This connection is used to:</span></span>  
  
-   <span data-ttu-id="336f6-206">Asegurarse de que no haya otros servicios con el mismo nombre que usen actualmente esta instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="336f6-206">Ensure that there are no other services by the same name currently working with this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="336f6-207">Comprobar que la instancia CDC de Oracle está habilitada o deshabilita e iniciar (o detener) su subproceso.</span><span class="sxs-lookup"><span data-stu-id="336f6-207">Check which Oracle CDC Instance is enabled or disabled and start (or stop) its subprocess.</span></span>  
  
 <span data-ttu-id="336f6-208">Cuando el servicio establece una conexión con la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino y comprueba que es el único servicio CDC de Oracle con este nombre que está funcionando, puede comprobar qué instancias CDC de Oracle están habilitadas e iniciar sus procesos de control (después el servicio detiene estos procesos cuando se deshabilitan).</span><span class="sxs-lookup"><span data-stu-id="336f6-208">When the service establishes a connection with the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and verifies that it is the only Oracle CDC service by this name that is working, it can check which Oracle CDC instances are enabled and start their handling processes (afterward the service stops these processes when they are disabled).</span></span> <span data-ttu-id="336f6-209">Las instancias CDC de Oracle usan sus conexiones con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para trabajar con la base de datos CDC de la instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="336f6-209">The Oracle CDC instances use their [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections to work with the CDC database of the Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="336f6-210">La forma en que se controlan los errores en la conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino depende de si los errores son transitorios o no.</span><span class="sxs-lookup"><span data-stu-id="336f6-210">How errors are handled when the connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fails depends on whether the errors are transient.</span></span>  
  
 <span data-ttu-id="336f6-211">En el caso de los errores no transitorios conocidos (como credenciales no válidas, privilegios insuficientes, información de conexión incorrecta), el servicio registra un error en el registro de eventos de Windows y se detiene (no puede escribir en la tabla de seguimiento porque no puede conectar con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="336f6-211">For known non-transient errors (such as bad credentials, insufficient privileges, bad connection information), the service logs an error to the Windows event log and stops (it cannot write to the trace table because it cannot connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="336f6-212">En este caso, el usuario debe resolver el error y reiniciar el servicio de Windows CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="336f6-212">In this case, the user must resolve the error and restart the Oracle CDC Windows service.</span></span>  
  
 <span data-ttu-id="336f6-213">Si se trata de errores transitorios y errores inesperados, la operación se reintenta varias veces y si el error persiste durante un período de tiempo significativo, el servicio CDC detiene sus subprocesos de instancia CDC y vuelve al intento de conexión inicial (para entonces, un servicio CDC de Oracle de otro equipo puede haber tomado ya el control de ese servicio CDC).</span><span class="sxs-lookup"><span data-stu-id="336f6-213">For transient errors and unexpected errors, the operation is retried several times and if the failure persists for a significant time period, the CDC Service stops its CDC Instance subprocesses and goes back to its initial connection attempt (by this time, an Oracle CDC Service on another machine may have already taken control of the named CDC service).</span></span>  
  
### <a name="handling-target-sql-server-storage-full-errors"></a><span data-ttu-id="336f6-214">Controlar errores de almacenamiento lleno de SQL Server de destino</span><span class="sxs-lookup"><span data-stu-id="336f6-214">Handling Target SQL Server Storage Full Errors</span></span>  
 <span data-ttu-id="336f6-215">Cuando el servicio CDC de Oracle detecta que no puede insertar nuevos datos modificados en la base de datos CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino, escribe una advertencia en el registro de eventos e intenta insertar un registro de seguimiento (aunque se puede producir un error por el mismo motivo).</span><span class="sxs-lookup"><span data-stu-id="336f6-215">When the Oracle CDC Service detects that it cannot insert new change data into the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database, it writes a warning to the event log and tries to insert a trace record (although that may fail for the same reason).</span></span> <span data-ttu-id="336f6-216">A continuación, vuelve a intentar la operación en un intervalo determinado hasta que lo consigue.</span><span class="sxs-lookup"><span data-stu-id="336f6-216">It then retries the operation in a specific interval until it is successful.</span></span>  
  
### <a name="handling-oracle-cdc-errors"></a><span data-ttu-id="336f6-217">Controlar errores CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="336f6-217">Handling Oracle CDC Errors</span></span>  
 <span data-ttu-id="336f6-218">La instancia CDC de Oracle lee el registro de transacciones de Oracle y lo procesa.</span><span class="sxs-lookup"><span data-stu-id="336f6-218">The Oracle CDC Instance reads the Oracle transaction log and processes it.</span></span> <span data-ttu-id="336f6-219">Si el procesamiento de CDC detecta un error, se notifica en la tabla **cdc.xdbcdc_state** y el usuario debe intervenir manualmente según el error notificado.</span><span class="sxs-lookup"><span data-stu-id="336f6-219">If the CDC processing encounters an error, it is reported in the **cdc.xdbcdc_state** table and the user needs to manually intervene based on the reported error.</span></span>  
  
 <span data-ttu-id="336f6-220">Por ejemplo, puede que la instancia CDC de Oracle no esté activa durante un tiempo prolongado y los archivos de registro de transacciones de Oracle necesarios ya no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="336f6-220">For example, the Oracle CDC Instance may not be active for an extended duration and the required Oracle transaction log files are no longer available.</span></span> <span data-ttu-id="336f6-221">En este caso, el DBA de Oracle debe restaurar los registros necesarios para que la instancia CDC de Oracle reanude el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="336f6-221">In this case, the Oracle DBA must restore the required logs for the Oracle CDC Instance to resume processing.</span></span>  
  
### <a name="handling-unexpected-oracle-cdc-instance-failures"></a><span data-ttu-id="336f6-222">Controlar errores inesperados de la instancia CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="336f6-222">Handling Unexpected Oracle CDC Instance Failures</span></span>  
 <span data-ttu-id="336f6-223">El servicio CDC de Oracle supervisa los subprocesos de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="336f6-223">The Oracle CDC Service monitors its CDC Instance subprocesses.</span></span> <span data-ttu-id="336f6-224">Cuando se anula un subproceso de instancia CDC, el servicio CDC lo deshabilita en la tabla MSXDBCDC.dbo.xdbcdc_databases y actualiza su estado de cdc.xdbcdc_state a ABORTED.</span><span class="sxs-lookup"><span data-stu-id="336f6-224">When a CDC Instance subprocess aborts, the CDC Service disables it in the MSXDBCDC.dbo.xdbcdc_databases table and updates its cdc.xdbcdc_state status to ABORTED.</span></span> <span data-ttu-id="336f6-225">En este caso, se emplea el cuadro de diálogo estándar de informe de errores de Windows para informar del error para su análisis.</span><span class="sxs-lookup"><span data-stu-id="336f6-225">In this case, the standard Windows Error Reporting dialog box is used to report this error for further analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="336f6-226">Consulte también</span><span class="sxs-lookup"><span data-stu-id="336f6-226">See Also</span></span>  
 <span data-ttu-id="336f6-227">[Diseñador de captura de datos modificados para Oracle de Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="336f6-227">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="336f6-228">La instancia CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="336f6-228">The Oracle CDC Instance</span></span>](the-oracle-cdc-instance.md)  