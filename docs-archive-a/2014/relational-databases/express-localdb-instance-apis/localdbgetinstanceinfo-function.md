---
title: Función LocalDBGetInstanceInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstanceInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 231706f5-26c6-42eb-ab47-315df6b8f824
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dc7cbe2c59a7502a1fd0c8b4f92fb14e5defd50b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670393"
---
# <a name="localdbgetinstanceinfo-function"></a><span data-ttu-id="f4876-102">Función LocalDBGetInstanceInfo</span><span class="sxs-lookup"><span data-stu-id="f4876-102">LocalDBGetInstanceInfo Function</span></span>
  <span data-ttu-id="f4876-103">Devuelve información para la instancia de SQL Server Express LocalDB especificada, por ejemplo si existe, la versión de LocalDB que usa, si se está ejecutando, etc.</span><span class="sxs-lookup"><span data-stu-id="f4876-103">Returns information for the specified SQL Server Express LocalDB instance, such as whether it exists, the LocalDB version it uses, whether it is running, and so on.</span></span>  
  
 <span data-ttu-id="f4876-104">La información se devuelve en un `struct` **LocalDBInstanceInfo**con nombre, que tiene la siguiente definición.</span><span class="sxs-lookup"><span data-stu-id="f4876-104">The information is returned in a `struct` named **LocalDBInstanceInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBInstanceInfo  
{  
      // Contains the size of the LocalDBInstanceInfo struct  
      DWORD  cbLocalDBInstanceInfoSize;  
  
      // Holds the instance name  
      TLocalDBInstanceNamewszInstanceName;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // TRUE if the instance configuration registry is corrupted, FALSE otherwise  
      BOOLbConfigurationCorrupted;  
  
      // TRUE if the instance is running at the moment, FALSE otherwise  
      BOOL   bIsRunning;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
  
      // Holds the date and time when the instance was started for the last time  
      FILETIME ftLastStartUTC;  
  
      // Holds the name of the TDS named pipe to connect to the instance  
      WCHARwszConnection;  
  
      // TRUE if the instance is shared, FALSE otherwise  
      BOOLbIsShared;  
  
      // Holds the shared name for the instance (if the instance is shared)  
      TLocalDBInstanceNamewszSharedInstanceName;  
  
      // Holds the SID of the instance owner (if the instance is shared)  
      WCHARwszOwnerSID;   
  
      // TRUE if the instance is Automatic, FALSE otherwise  
      BOOLbIsAutomatic;  
} LocalDBInstanceInfo;  
  
```  
  
 <span data-ttu-id="f4876-105">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="f4876-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4876-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4876-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetInstanceInfo(  
           PCWSTR wszInstanceName,  
           PLocalDBInstanceInfo pInstanceInfo,  
           DWORD dwInstanceInfoSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4876-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4876-107">Parameters</span></span>  
 <span data-ttu-id="f4876-108">*wszInstanceName*</span><span class="sxs-lookup"><span data-stu-id="f4876-108">*wszInstanceName*</span></span>  
 <span data-ttu-id="f4876-109">[Input] Nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="f4876-109">[Input] The instance name.</span></span>  
  
 <span data-ttu-id="f4876-110">*pInstanceInfo*</span><span class="sxs-lookup"><span data-stu-id="f4876-110">*pInstanceInfo*</span></span>  
 <span data-ttu-id="f4876-111">[Output] Búfer para almacenar información sobre la instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f4876-111">[Output] The buffer to store the information about the LocalDB instance.</span></span>  
  
 <span data-ttu-id="f4876-112">*dwInstanceInfoSize*</span><span class="sxs-lookup"><span data-stu-id="f4876-112">*dwInstanceInfoSize*</span></span>  
 <span data-ttu-id="f4876-113">Entradas Contiene el tamaño del búfer de *InstanceInfo* .</span><span class="sxs-lookup"><span data-stu-id="f4876-113">[Input] Holds the size of the *InstanceInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f4876-114">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="f4876-114">Returns</span></span>  
 <span data-ttu-id="f4876-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4876-115">S_OK</span></span>  
 <span data-ttu-id="f4876-116">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4876-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="f4876-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="f4876-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="f4876-118">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f4876-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="f4876-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="f4876-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="f4876-120">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="f4876-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="f4876-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="f4876-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="f4876-122">El nombre de instancia de especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="f4876-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="f4876-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="f4876-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="f4876-124">La instancia no existe.</span><span class="sxs-lookup"><span data-stu-id="f4876-124">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="f4876-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="f4876-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="f4876-126">La ruta de acceso donde la instancia debe almacenarse es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="f4876-126">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="f4876-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f4876-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="f4876-128">No se puede tener acceso a una carpeta de la instancia.</span><span class="sxs-lookup"><span data-stu-id="f4876-128">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="f4876-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="f4876-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="f4876-130">No se puede tener acceso a un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="f4876-130">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="f4876-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="f4876-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="f4876-132">Una configuración de instancia está dañada.</span><span class="sxs-lookup"><span data-stu-id="f4876-132">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="f4876-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="f4876-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="f4876-134">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="f4876-134">An unexpected error occurred.</span></span> <span data-ttu-id="f4876-135">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="f4876-135">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4876-136">Detalles</span><span class="sxs-lookup"><span data-stu-id="f4876-136">Details</span></span>  
 <span data-ttu-id="f4876-137">La lógica que subyace a la introducción del `struct` argumento de tamaño (*lpInstanceInfoSize*) es permitir que la API devuelva distintas versiones de **LocalDBInstanceInfostruct**, con lo que se habilita la compatibilidad con versiones anteriores y posteriores.</span><span class="sxs-lookup"><span data-stu-id="f4876-137">The rationale behind the introduction of the `struct` size argument (*lpInstanceInfoSize*) is to enable the API to return different versions of the **LocalDBInstanceInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="f4876-138">Si el `struct` argumento de tamaño (*lpInstanceInfoSize*) coincide con el tamaño de una versión conocida de **LocalDBInstanceInfostruct**, se devuelve esa versión de `struct` .</span><span class="sxs-lookup"><span data-stu-id="f4876-138">If the `struct` size argument (*lpInstanceInfoSize*) matches the size of a known version of the **LocalDBInstanceInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="f4876-139">De lo contrario, se devuelve LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="f4876-139">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="f4876-140">Un ejemplo típico de uso de la API de **LocalDBGetInstanceInfo** tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="f4876-140">A typical example of **LocalDBGetInstanceInfo** API usage looks like this:</span></span>  
  
```  
LocalDBInstanceInfo ii;  
LocalDBInstanceInfo(L"Test", &ii, sizeof(LocalDBInstanceInfo));  
  
```  
  
 <span data-ttu-id="f4876-141">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f4876-141">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4876-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4876-142">See Also</span></span>  
 [<span data-ttu-id="f4876-143">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="f4876-143">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
