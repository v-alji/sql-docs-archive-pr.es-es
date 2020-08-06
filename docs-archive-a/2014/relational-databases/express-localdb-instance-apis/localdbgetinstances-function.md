---
title: Función LocalDBGetInstances | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstances
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: f95a9980-8bc0-426c-8aa1-e2660b6784cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a6f758bd647fd69a14f72a0651bb3e2e33a7c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744086"
---
# <a name="localdbgetinstances-function"></a><span data-ttu-id="0eb00-102">Función LocalDBGetInstances</span><span class="sxs-lookup"><span data-stu-id="0eb00-102">LocalDBGetInstances Function</span></span>
  <span data-ttu-id="0eb00-103">Devuelve todas las instancias de SQL Server Express LocalDB con la versión indicada.</span><span class="sxs-lookup"><span data-stu-id="0eb00-103">Returns all SQL Server Express LocalDB instances with the given version.</span></span>  
  
 <span data-ttu-id="0eb00-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="0eb00-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb00-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eb00-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_INSTANCE_NAME_LENGTH 128typedef WCHAR TLocalDBInstanceName[MAX_LOCALDB_INSTANCE_NAME_LENGTH + 1];typedef TLocalDBInstanceName* PTLocalDBInstanceName;  
HRESULT LocalDBGetInstances(  
           PTLocalDBInstanceName pInstanceNames,  
           LPDWORD lpdwNumberOfInstances  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eb00-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0eb00-106">Parameters</span></span>  
 <span data-ttu-id="0eb00-107">*pInstanceNames*</span><span class="sxs-lookup"><span data-stu-id="0eb00-107">*pInstanceNames*</span></span>  
 <span data-ttu-id="0eb00-108">Genere Cuando esta función devuelve un valor, contiene los nombres de las instancias de LocalDB con nombre y predeterminadas en la estación de trabajo del usuario.</span><span class="sxs-lookup"><span data-stu-id="0eb00-108">[Output] When this function returns, contains the names of both named and default LocalDB instances on the user's workstation.</span></span>  
  
 <span data-ttu-id="0eb00-109">*lpdwNumberOfInstances*</span><span class="sxs-lookup"><span data-stu-id="0eb00-109">*lpdwNumberOfInstances*</span></span>  
 <span data-ttu-id="0eb00-110">[Entrada/Salida] En la entrada, contiene el número de zonas para los nombres de instancia en el búfer de *pInstanceNames* .</span><span class="sxs-lookup"><span data-stu-id="0eb00-110">[Input/Output] On input, contains the number of slots for instance names in the *pInstanceNames* buffer.</span></span> <span data-ttu-id="0eb00-111">En la salida, contiene el número de instancias de LocalDB que se encuentran en la estación de trabajo del usuario.</span><span class="sxs-lookup"><span data-stu-id="0eb00-111">On output, contains the number of LocalDB instances found on the user's workstation.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0eb00-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="0eb00-112">Returns</span></span>  
 <span data-ttu-id="0eb00-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0eb00-113">S_OK</span></span>  
 <span data-ttu-id="0eb00-114">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0eb00-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="0eb00-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="0eb00-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="0eb00-116">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0eb00-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="0eb00-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="0eb00-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="0eb00-118">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="0eb00-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="0eb00-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0eb00-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="0eb00-120">El búfer de entrada es demasiado corto y no se ha solicitado truncamiento.</span><span class="sxs-lookup"><span data-stu-id="0eb00-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="0eb00-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="0eb00-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="0eb00-122">La ruta de acceso donde la instancia debe almacenarse es mayor que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="0eb00-122">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="0eb00-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="0eb00-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="0eb00-124">No se puede tener acceso a un registro de la instancia.</span><span class="sxs-lookup"><span data-stu-id="0eb00-124">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="0eb00-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="0eb00-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="0eb00-126">Una configuración de instancia está dañada.</span><span class="sxs-lookup"><span data-stu-id="0eb00-126">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="0eb00-127">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="0eb00-127">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="0eb00-128">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="0eb00-128">An unexpected error occurred.</span></span> <span data-ttu-id="0eb00-129">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="0eb00-129">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0eb00-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0eb00-130">Remarks</span></span>  
 <span data-ttu-id="0eb00-131">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0eb00-131">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb00-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0eb00-132">See Also</span></span>  
 [<span data-ttu-id="0eb00-133">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="0eb00-133">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
