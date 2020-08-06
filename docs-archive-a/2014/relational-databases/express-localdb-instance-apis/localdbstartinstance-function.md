---
title: Función LocalDBStartInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: cb325f5d-10ee-4a56-ba28-db0074ab3926
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 748bc373e8b0dbad0a91247e068d21b67f2dbc1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677119"
---
# <a name="localdbstartinstance-function"></a><span data-ttu-id="974d8-102">Función LocalDBStartInstance</span><span class="sxs-lookup"><span data-stu-id="974d8-102">LocalDBStartInstance Function</span></span>
  <span data-ttu-id="974d8-103">Inicia la instancia de SQL Server Express LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="974d8-103">Starts the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="974d8-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="974d8-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="974d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="974d8-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           LPWSTR wszSqlConnection,   
           LPDWORD lpcchSqlConnection   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="974d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="974d8-106">Parameters</span></span>  
 <span data-ttu-id="974d8-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="974d8-107">*pInstanceName*</span></span>  
 <span data-ttu-id="974d8-108">[Input] Nombre de la instancia de LocalDB que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="974d8-108">[Input] The name of the LocalDB instance to start.</span></span>  
  
 <span data-ttu-id="974d8-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="974d8-109">*dwFlags*</span></span>  
 <span data-ttu-id="974d8-110">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="974d8-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="974d8-111">En estos momentos, se debe establecer en 0.</span><span class="sxs-lookup"><span data-stu-id="974d8-111">Currently should be set to 0.</span></span>  
  
 <span data-ttu-id="974d8-112">*wszSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="974d8-112">*wszSqlConnection*</span></span>  
 <span data-ttu-id="974d8-113">[Salida] Búfer donde se almacena la cadena de conexión para la instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="974d8-113">[Output] The buffer to store the connection string to the LocalDB instance.</span></span>  
  
 <span data-ttu-id="974d8-114">*lpcchSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="974d8-114">*lpcchSqlConnection*</span></span>  
 <span data-ttu-id="974d8-115">[Entrada/Salida] En la entrada contiene el tamaño de búfer de *wszSqlConnection* en caracteres, incluidos los valores NULL finales.</span><span class="sxs-lookup"><span data-stu-id="974d8-115">[Input/Output] On input contains the size of the *wszSqlConnection* buffer in characters, including any trailing nulls.</span></span> <span data-ttu-id="974d8-116">En la salida, si el tamaño de búfer proporcionado es demasiado pequeño, contiene el tamaño de búfer necesario en caracteres, lo cual incluye los valores NULL finales.</span><span class="sxs-lookup"><span data-stu-id="974d8-116">On output, if the given buffer size is too small, contains the required buffer size in characters, including any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="974d8-117">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="974d8-117">Returns</span></span>  
 <span data-ttu-id="974d8-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="974d8-118">S_OK</span></span>  
 <span data-ttu-id="974d8-119">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="974d8-119">The function succeeded.</span></span>  
  
 [<span data-ttu-id="974d8-120">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="974d8-120">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="974d8-121">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="974d8-121">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="974d8-122">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="974d8-122">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="974d8-123">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="974d8-123">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="974d8-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="974d8-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="974d8-125">El nombre de instancia de especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="974d8-125">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="974d8-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="974d8-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="974d8-127">La instancia no existe.</span><span class="sxs-lookup"><span data-stu-id="974d8-127">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="974d8-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="974d8-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="974d8-129">El búfer *wszSqlConnection* especificado es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="974d8-129">The specified buffer *wszSqlConnection* is too small.</span></span>  
  
 [<span data-ttu-id="974d8-130">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="974d8-130">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="974d8-131">Se ha agotado el tiempo de espera mientras se intentaba adquirir bloqueos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="974d8-131">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="974d8-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="974d8-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="974d8-133">La ruta de acceso donde la instancia debe almacenarse es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="974d8-133">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="974d8-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="974d8-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="974d8-135">No se puede recuperar una carpeta de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="974d8-135">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="974d8-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="974d8-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="974d8-137">No se puede tener acceso a una carpeta de la instancia.</span><span class="sxs-lookup"><span data-stu-id="974d8-137">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="974d8-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="974d8-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="974d8-139">No se puede tener acceso a un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="974d8-139">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="974d8-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="974d8-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="974d8-141">No se puede modificar un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="974d8-141">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="974d8-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="974d8-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-sql-process.md)  
 <span data-ttu-id="974d8-143">No se puede crear un proceso para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="974d8-143">A process for SQL Server cannot be created.</span></span>  
  
 [<span data-ttu-id="974d8-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="974d8-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="974d8-145">Se ha iniciado un proceso de SQL Server, pero se ha producido un error al iniciar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="974d8-145">A SQL Server process was started, but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="974d8-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="974d8-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="974d8-147">Una configuración de instancia estaba dañada.</span><span class="sxs-lookup"><span data-stu-id="974d8-147">An instance configuration was corrupted.</span></span>  
  
 [<span data-ttu-id="974d8-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="974d8-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span></span>](../express-localdb-error-messages/localdb-error-auto-instance-create-failed.md)  
 <span data-ttu-id="974d8-149">No se puede crear una instancia automática.</span><span class="sxs-lookup"><span data-stu-id="974d8-149">Cannot create an automatic instance.</span></span> <span data-ttu-id="974d8-150">Vea el registro de eventos de aplicación de Windows para obtener los detalles del error.</span><span class="sxs-lookup"><span data-stu-id="974d8-150">See the Windows Application event log for error details.</span></span>  
  
 [<span data-ttu-id="974d8-151">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="974d8-151">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="974d8-152">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="974d8-152">An unexpected error occurred.</span></span> <span data-ttu-id="974d8-153">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="974d8-153">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="974d8-154">Detalles</span><span class="sxs-lookup"><span data-stu-id="974d8-154">Details</span></span>  
 <span data-ttu-id="974d8-155">Ell argumento del búfer de conexión (*wszSqlConnection*) y el argumento del tamaño de búfer de conexión (*lpcchSqlConnection*) son opcionales.</span><span class="sxs-lookup"><span data-stu-id="974d8-155">Both the connection buffer argument (*wszSqlConnection*) and the connection buffer size argument (*lpcchSqlConnection*) are optional.</span></span> <span data-ttu-id="974d8-156">La tabla siguiente muestra las opciones de uso de estos argumentos y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="974d8-156">The following table shows options for using these arguments and their results.</span></span>  
  
|<span data-ttu-id="974d8-157">Buffer</span><span class="sxs-lookup"><span data-stu-id="974d8-157">Buffer</span></span>|<span data-ttu-id="974d8-158">Tamaño de búfer</span><span class="sxs-lookup"><span data-stu-id="974d8-158">Buffer size</span></span>|<span data-ttu-id="974d8-159">Análisis razonado</span><span class="sxs-lookup"><span data-stu-id="974d8-159">Rationale</span></span>|<span data-ttu-id="974d8-160">Acción</span><span class="sxs-lookup"><span data-stu-id="974d8-160">Action</span></span>|  
|------------|-----------------|---------------|------------|  
|<span data-ttu-id="974d8-161">NULL</span><span class="sxs-lookup"><span data-stu-id="974d8-161">NULL</span></span>|<span data-ttu-id="974d8-162">NULL</span><span class="sxs-lookup"><span data-stu-id="974d8-162">NULL</span></span>|<span data-ttu-id="974d8-163">El usuario desea iniciar la instancia y no necesita un nombre de canalización.</span><span class="sxs-lookup"><span data-stu-id="974d8-163">User wants to start the instance and doesn't need a pipe name.</span></span>|<span data-ttu-id="974d8-164">Inicia una instancia (sin devolución de canalización y no se requiere la devolución de tamaño de búfer).</span><span class="sxs-lookup"><span data-stu-id="974d8-164">Starts an instance (no pipe return and no required buffer size return).</span></span>|  
|<span data-ttu-id="974d8-165">NULL</span><span class="sxs-lookup"><span data-stu-id="974d8-165">NULL</span></span>|<span data-ttu-id="974d8-166">Presente</span><span class="sxs-lookup"><span data-stu-id="974d8-166">Present</span></span>|<span data-ttu-id="974d8-167">El usuario solicita el tamaño de búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="974d8-167">User asks for the output buffer size.</span></span> <span data-ttu-id="974d8-168">(En la llamada siguiente el usuario probablemente solicitará un inicio real).</span><span class="sxs-lookup"><span data-stu-id="974d8-168">(In the next call the user will probably ask for an actual start.)</span></span>|<span data-ttu-id="974d8-169">Devuelve el tamaño de búfer necesario (sin inicio y sin devolución de canalización).</span><span class="sxs-lookup"><span data-stu-id="974d8-169">Returns a required buffer size (no start and no pipe return).</span></span> <span data-ttu-id="974d8-170">El resultado es S_OK.</span><span class="sxs-lookup"><span data-stu-id="974d8-170">Result is S_OK.</span></span>|  
|<span data-ttu-id="974d8-171">Presente</span><span class="sxs-lookup"><span data-stu-id="974d8-171">Present</span></span>|<span data-ttu-id="974d8-172">NULL</span><span class="sxs-lookup"><span data-stu-id="974d8-172">NULL</span></span>|<span data-ttu-id="974d8-173">No está permitido; entrada no correcta.</span><span class="sxs-lookup"><span data-stu-id="974d8-173">Not allowed; incorrect input.</span></span>|<span data-ttu-id="974d8-174">El resultado devuelto es LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="974d8-174">Returned result is LOCALDB_ERROR_INVALID_PARAMETER.</span></span>|  
|<span data-ttu-id="974d8-175">Presente</span><span class="sxs-lookup"><span data-stu-id="974d8-175">Present</span></span>|<span data-ttu-id="974d8-176">Presente</span><span class="sxs-lookup"><span data-stu-id="974d8-176">Present</span></span>|<span data-ttu-id="974d8-177">El usuario desea iniciar la instancia y necesita el nombre de la canalización para conectarse una vez se haya iniciado.</span><span class="sxs-lookup"><span data-stu-id="974d8-177">User wants to start the instance and needs the pipe name to connect to it after it is started.</span></span>|<span data-ttu-id="974d8-178">Comprueba el tamaño de búfer, inicia la instancia y devuelve el nombre de la canalización en el búfer.</span><span class="sxs-lookup"><span data-stu-id="974d8-178">Checks the buffer size, starts the instance, and returns the pipe name in the buffer.</span></span> <br /><span data-ttu-id="974d8-179">El argumento de tamaño de búfer devuelve la longitud de la cadena "Server =", sin incluir los valores NULL de terminación.</span><span class="sxs-lookup"><span data-stu-id="974d8-179">The buffer size argument returns the length of the "server=" string, not including terminating nulls.</span></span>|  
  
 <span data-ttu-id="974d8-180">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="974d8-180">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974d8-181">Consulte también</span><span class="sxs-lookup"><span data-stu-id="974d8-181">See Also</span></span>  
 [<span data-ttu-id="974d8-182">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="974d8-182">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
