---
title: Función LocalDBDeleteInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBDeleteInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 37cb2a7e-672a-4223-b6f3-a94d7b8d58cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8d4c873e045c5effed476ca9d147270d159ec3b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675399"
---
# <a name="localdbdeleteinstance-function"></a><span data-ttu-id="83238-102">Función LocalDBDeleteInstance</span><span class="sxs-lookup"><span data-stu-id="83238-102">LocalDBDeleteInstance Function</span></span>
  <span data-ttu-id="83238-103">Quita la instancia de SQL Server Express LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="83238-103">Removes the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="83238-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="83238-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83238-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83238-105">Syntax</span></span>  
  
```  
HRESULT LocalDBDeleteInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83238-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83238-106">Parameters</span></span>  
 <span data-ttu-id="83238-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="83238-107">*pInstanceName*</span></span>  
 <span data-ttu-id="83238-108">[Entrada] Nombre de la instancia de LocalDB que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="83238-108">[Input] The name of the LocalDB instance to remove.</span></span>  
  
 <span data-ttu-id="83238-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="83238-109">*dwFlags*</span></span>  
 <span data-ttu-id="83238-110">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="83238-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="83238-111">En estos momentos, se debe establecer en 0.</span><span class="sxs-lookup"><span data-stu-id="83238-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="83238-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="83238-112">Returns</span></span>  
 <span data-ttu-id="83238-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="83238-113">S_OK</span></span>  
 <span data-ttu-id="83238-114">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="83238-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="83238-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="83238-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="83238-116">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="83238-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="83238-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="83238-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="83238-118">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="83238-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="83238-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="83238-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="83238-120">El nombre de instancia de especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="83238-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="83238-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="83238-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="83238-122">La instancia especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="83238-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="83238-123">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="83238-123">LOCALDB_ERROR_INSTANCE_BUSY</span></span>](../express-localdb-error-messages/localdb-error-instance-busy.md)  
 <span data-ttu-id="83238-124">La instancia especificada se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="83238-124">The specified instance is running.</span></span>  
  
 [<span data-ttu-id="83238-125">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83238-125">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="83238-126">Se ha agotado el tiempo de espera mientras se intentaban adquirir bloqueos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="83238-126">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
 [<span data-ttu-id="83238-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="83238-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="83238-128">La ruta de acceso donde la instancia debe almacenarse es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="83238-128">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="83238-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="83238-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="83238-130">No se puede recuperar una carpeta de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="83238-130">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="83238-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="83238-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="83238-132">No se puede tener acceso a una carpeta de la instancia.</span><span class="sxs-lookup"><span data-stu-id="83238-132">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="83238-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="83238-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="83238-134">No se puede tener acceso a un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="83238-134">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="83238-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="83238-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="83238-136">No se puede modificar un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="83238-136">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="83238-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="83238-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="83238-138">Una configuración de instancia está dañada.</span><span class="sxs-lookup"><span data-stu-id="83238-138">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="83238-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83238-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="83238-140">El autor de llamada de API no es el propietario de la instancia de Local Database.</span><span class="sxs-lookup"><span data-stu-id="83238-140">API caller is not Local Database instance owner.</span></span>  
  
 [<span data-ttu-id="83238-141">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="83238-141">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="83238-142">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="83238-142">An unexpected error occurred.</span></span> <span data-ttu-id="83238-143">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="83238-143">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83238-144">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83238-144">Remarks</span></span>  
 <span data-ttu-id="83238-145">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="83238-145">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83238-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83238-146">See Also</span></span>  
 [<span data-ttu-id="83238-147">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="83238-147">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
