---
title: Función LocalDBCreateInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBCreateInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 3eebb485-8a53-4a79-82a9-57b8de9f8e84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ff822c552176ad8c083a1c8ea6c0f2430f72972f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675404"
---
# <a name="localdbcreateinstance-function"></a><span data-ttu-id="acae2-102">Función LocalDBCreateInstance</span><span class="sxs-lookup"><span data-stu-id="acae2-102">LocalDBCreateInstance Function</span></span>
  <span data-ttu-id="acae2-103">Crea una nueva instancia de SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="acae2-103">Creates a new SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="acae2-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="acae2-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acae2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acae2-105">Syntax</span></span>  
  
```  
HRESULT LocalDBCreateInstance(  
           PCWSTR wszVersion,  
           PCWSTR pInstanceName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acae2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acae2-106">Parameters</span></span>  
 <span data-ttu-id="acae2-107">*wszVersion*</span><span class="sxs-lookup"><span data-stu-id="acae2-107">*wszVersion*</span></span>  
 <span data-ttu-id="acae2-108">[Entrada] Versión de LocalDB, por ejemplo 11.0 o 11.0.1094.2.</span><span class="sxs-lookup"><span data-stu-id="acae2-108">[Input] The LocalDB version, for example 11.0 or 11.0.1094.2.</span></span>  
  
 <span data-ttu-id="acae2-109">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="acae2-109">*pInstanceName*</span></span>  
 <span data-ttu-id="acae2-110">[Entrada] Nombre de la instancia de LocalDB que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="acae2-110">[Input] The name for the LocalDB instance to create.</span></span>  
  
 <span data-ttu-id="acae2-111">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="acae2-111">*dwFlags*</span></span>  
 <span data-ttu-id="acae2-112">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="acae2-112">[Input] Reserved for future use.</span></span> <span data-ttu-id="acae2-113">En estos momentos, se debe establecer en 0.</span><span class="sxs-lookup"><span data-stu-id="acae2-113">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="acae2-114">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="acae2-114">Returns</span></span>  
 <span data-ttu-id="acae2-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="acae2-115">S_OK</span></span>  
 <span data-ttu-id="acae2-116">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="acae2-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="acae2-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="acae2-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="acae2-118">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="acae2-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="acae2-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="acae2-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="acae2-120">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="acae2-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="acae2-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="acae2-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="acae2-122">El nombre de instancia de especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="acae2-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="acae2-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="acae2-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="acae2-124">La ruta de acceso donde la instancia debe almacenarse es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="acae2-124">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="acae2-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="acae2-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>](../express-localdb-error-messages/localdb-error-instance-exists-with-lower-version.md)  
 <span data-ttu-id="acae2-126">La instancia especificada ya existe pero la versión es anterior a la solicitada.</span><span class="sxs-lookup"><span data-stu-id="acae2-126">The specified instance already exists but its version is lower than requested.</span></span>  
  
 [<span data-ttu-id="acae2-127">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="acae2-127">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="acae2-128">La versión especificada no está disponible.</span><span class="sxs-lookup"><span data-stu-id="acae2-128">The specified version is not available.</span></span>  
  
 [<span data-ttu-id="acae2-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="acae2-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-version-requested-not-installed.md)  
 <span data-ttu-id="acae2-130">El nivel especificado de la revisión no está instalado.</span><span class="sxs-lookup"><span data-stu-id="acae2-130">The specified patch level is not installed.</span></span>  
  
 [<span data-ttu-id="acae2-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="acae2-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-instance-folder.md)  
 <span data-ttu-id="acae2-132">No se puede crear una carpeta en %userprofile%.</span><span class="sxs-lookup"><span data-stu-id="acae2-132">A folder cannot be created under %userprofile%.</span></span>  
  
 [<span data-ttu-id="acae2-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="acae2-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="acae2-134">No se puede recuperar una carpeta de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="acae2-134">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="acae2-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="acae2-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="acae2-136">No se puede tener acceso a una carpeta de la instancia.</span><span class="sxs-lookup"><span data-stu-id="acae2-136">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="acae2-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="acae2-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="acae2-138">No se puede tener acceso a un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="acae2-138">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="acae2-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="acae2-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="acae2-140">No se puede modificar un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="acae2-140">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="acae2-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="acae2-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="acae2-142">Se ha iniciado un proceso de SQL Server, pero se ha producido un error al iniciar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="acae2-142">A SQL Server process is started but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="acae2-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="acae2-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="acae2-144">Una configuración de instancia está dañada.</span><span class="sxs-lookup"><span data-stu-id="acae2-144">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="acae2-145">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="acae2-145">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="acae2-146">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="acae2-146">An unexpected error occurred.</span></span> <span data-ttu-id="acae2-147">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="acae2-147">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acae2-148">Observaciones</span><span class="sxs-lookup"><span data-stu-id="acae2-148">Remarks</span></span>  
 <span data-ttu-id="acae2-149">Si ya existe una instancia de LocalDB completamente operativa con el nombre especificado y su versión es la misma o superior a la solicitada, el resultado es S_OK.</span><span class="sxs-lookup"><span data-stu-id="acae2-149">If a fully functional LocalDB instance with the specified name already exists and its version is equal to or higher than requested, the result is S_OK.</span></span>  
  
 <span data-ttu-id="acae2-150">En los casos en los que se daña una instancia existente, las llamadas ulteriores al método de la API `LocalDBCreateInstance` producirán un error.</span><span class="sxs-lookup"><span data-stu-id="acae2-150">In cases when an existing instance becomes corrupted, subsequent calls to the `LocalDBCreateInstance` API method will fail.</span></span> <span data-ttu-id="acae2-151">Las instancias dañadas deben corregirse manualmente o eliminarse explícitamente antes de que se puedan volver a usar.</span><span class="sxs-lookup"><span data-stu-id="acae2-151">Corrupted instances must be fixed manually or explicitly deleted before they can be used again.</span></span>  
  
 <span data-ttu-id="acae2-152">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="acae2-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acae2-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acae2-153">See Also</span></span>  
 [<span data-ttu-id="acae2-154">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="acae2-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
