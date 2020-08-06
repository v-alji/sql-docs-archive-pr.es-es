---
title: Función LocalDBStopInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 4bd73187-0aac-4f03-ac54-2b78e41917e5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 48b014e65e0a02a5f866e5301b12dae3cd255b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744085"
---
# <a name="localdbstopinstance-function"></a><span data-ttu-id="ea22d-102">Función LocalDBStopInstance</span><span class="sxs-lookup"><span data-stu-id="ea22d-102">LocalDBStopInstance Function</span></span>
  <span data-ttu-id="ea22d-103">Detiene la ejecución de la instancia de SQL Server Express LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="ea22d-103">Stops the specified SQL Server Express LocalDB instance from running.</span></span>  
  
 <span data-ttu-id="ea22d-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="ea22d-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea22d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea22d-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           ULONG ulTimeout   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea22d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea22d-106">Parameters</span></span>  
 <span data-ttu-id="ea22d-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="ea22d-107">*pInstanceName*</span></span>  
 <span data-ttu-id="ea22d-108">[Entrada] Nombre de la instancia de LocalDB que se va a detener.</span><span class="sxs-lookup"><span data-stu-id="ea22d-108">[Input] The name of the LocalDB instance to stop.</span></span>  
  
 <span data-ttu-id="ea22d-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="ea22d-109">*dwFlags*</span></span>  
 <span data-ttu-id="ea22d-110">[Entrada] Un valor de marcador o una combinación de ellos que especifican la forma en la que detener la instancia.</span><span class="sxs-lookup"><span data-stu-id="ea22d-110">[Input] One or a combination of the flag values specifying the way to stop the instance.</span></span>  
  
 <span data-ttu-id="ea22d-111">Marcadores disponibles:</span><span class="sxs-lookup"><span data-stu-id="ea22d-111">Available flags:</span></span>  
  
 <span data-ttu-id="ea22d-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="ea22d-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span></span>  
 <span data-ttu-id="ea22d-113">Cierre inmediato mediante el comando del sistema operativo de eliminar proceso.</span><span class="sxs-lookup"><span data-stu-id="ea22d-113">Shut down immediately using the kill process operating system command.</span></span>  
  
 <span data-ttu-id="ea22d-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span><span class="sxs-lookup"><span data-stu-id="ea22d-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span></span>  
 <span data-ttu-id="ea22d-115">Cierre mediante el comando de Transact-SQL de la opción WITH NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="ea22d-115">Shut down using the WITH NOWAIT option Transact-SQL command.</span></span>  
  
 <span data-ttu-id="ea22d-116">Si no se establece ningún marcador, la instancia de LocalDB se cerrará con el comando de Transact-SQL SHUTDOWN.</span><span class="sxs-lookup"><span data-stu-id="ea22d-116">If none of the flags is set, the LocalDB instance will be shut down using the SHUTDOWN Transact-SQL command.</span></span> <span data-ttu-id="ea22d-117">Si se han establecido ambos marcadores, tiene prioridad el marcador LOCALDB_SHUTDOWN_KILL_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="ea22d-117">If both flags are set, the LOCALDB_SHUTDOWN_KILL_PROCESS flag takes precedence.</span></span>  
  
 <span data-ttu-id="ea22d-118">*ulTimeout*</span><span class="sxs-lookup"><span data-stu-id="ea22d-118">*ulTimeout*</span></span>  
 <span data-ttu-id="ea22d-119">[Entrada] Tiempo en segundos que transcurrirá para que se complete esta operación.</span><span class="sxs-lookup"><span data-stu-id="ea22d-119">[Input] The time in seconds to wait for this operation to complete.</span></span> <span data-ttu-id="ea22d-120">Si este valor es 0, esta función devolverá resultados inmediatamente sin esperar a que se detenga la instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="ea22d-120">If this value is 0, this function will return immediately without waiting for the LocalDB instance to stop.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ea22d-121">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="ea22d-121">Returns</span></span>  
 <span data-ttu-id="ea22d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea22d-122">S_OK</span></span>  
 <span data-ttu-id="ea22d-123">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ea22d-123">The function succeeded.</span></span>  
  
 [<span data-ttu-id="ea22d-124">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="ea22d-124">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="ea22d-125">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ea22d-125">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="ea22d-126">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="ea22d-126">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="ea22d-127">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="ea22d-127">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="ea22d-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea22d-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="ea22d-129">El nombre de instancia de especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="ea22d-129">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="ea22d-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea22d-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="ea22d-131">La instancia no existe.</span><span class="sxs-lookup"><span data-stu-id="ea22d-131">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="ea22d-132">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea22d-132">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="ea22d-133">Se ha agotado el tiempo de espera mientras se intentaba adquirir bloqueos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="ea22d-133">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="ea22d-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span><span class="sxs-lookup"><span data-stu-id="ea22d-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-instance-stop-failed.md)  
 <span data-ttu-id="ea22d-135">La operación de detención no pudo completarse dentro del tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="ea22d-135">The stop operation failed to complete within the given time.</span></span>  
  
 [<span data-ttu-id="ea22d-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="ea22d-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="ea22d-137">La ruta de acceso donde la instancia debe almacenarse es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="ea22d-137">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="ea22d-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="ea22d-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="ea22d-139">No se puede recuperar una carpeta de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="ea22d-139">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="ea22d-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="ea22d-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="ea22d-141">No se puede tener acceso a una carpeta de la instancia.</span><span class="sxs-lookup"><span data-stu-id="ea22d-141">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="ea22d-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="ea22d-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="ea22d-143">No se puede tener acceso a un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="ea22d-143">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="ea22d-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="ea22d-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="ea22d-145">Una configuración de instancia está dañada.</span><span class="sxs-lookup"><span data-stu-id="ea22d-145">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="ea22d-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea22d-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="ea22d-147">El autor de llamada de la API no es propietario de la instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="ea22d-147">API caller is not LocalDB instance owner.</span></span>  
  
 [<span data-ttu-id="ea22d-148">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="ea22d-148">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="ea22d-149">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="ea22d-149">An unexpected error occurred.</span></span> <span data-ttu-id="ea22d-150">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="ea22d-150">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea22d-151">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ea22d-151">Remarks</span></span>  
 <span data-ttu-id="ea22d-152">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ea22d-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea22d-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea22d-153">See Also</span></span>  
 [<span data-ttu-id="ea22d-154">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="ea22d-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
