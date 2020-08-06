---
title: Función LocalDBShareInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBShareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 21eb3b9a-7d32-455b-89bb-f624198cd202
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 238bff0b3512ceb03ead186dc001165274bd4e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671995"
---
# <a name="localdbshareinstance-function"></a><span data-ttu-id="c0957-102">Función LocalDBShareInstance</span><span class="sxs-lookup"><span data-stu-id="c0957-102">LocalDBShareInstance Function</span></span>
  <span data-ttu-id="c0957-103">Comparte la instancia de SQL Server Express LocalDB especificada con otros usuarios del equipo, mediante el nombre compartido indicado.</span><span class="sxs-lookup"><span data-stu-id="c0957-103">Shares the specified SQL Server Express LocalDB instance with other users of the computer, using the specified shared name.</span></span>  
  
 <span data-ttu-id="c0957-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="c0957-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0957-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0957-105">Syntax</span></span>  
  
```  
HRESULT LocalDBShareInstance(  
           PSID pOwnerSID,  
           PCWSTR pInstancePrivateName,  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0957-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0957-106">Parameters</span></span>  
 <span data-ttu-id="c0957-107">*pOwnerSID*</span><span class="sxs-lookup"><span data-stu-id="c0957-107">*pOwnerSID*</span></span>  
 <span data-ttu-id="c0957-108">[Entrada] SID del propietario de la instancia.</span><span class="sxs-lookup"><span data-stu-id="c0957-108">[Input] The SID of the instance owner.</span></span>  
  
 <span data-ttu-id="c0957-109">*pInstancePrivateName*</span><span class="sxs-lookup"><span data-stu-id="c0957-109">*pInstancePrivateName*</span></span>  
 <span data-ttu-id="c0957-110">[Entrada] Nombre privado de la instancia de LocalDB que se va a compartir.</span><span class="sxs-lookup"><span data-stu-id="c0957-110">[Input] The private name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="c0957-111">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="c0957-111">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="c0957-112">[Entrada] Nombre de la instancia compartida de LocalDB que se va a compartir.</span><span class="sxs-lookup"><span data-stu-id="c0957-112">[Input] The shared name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="c0957-113">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="c0957-113">*dwFlags*</span></span>  
 <span data-ttu-id="c0957-114">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="c0957-114">[Input] Reserved for future use.</span></span> <span data-ttu-id="c0957-115">En estos momentos, se debe establecer en 0.</span><span class="sxs-lookup"><span data-stu-id="c0957-115">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c0957-116">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="c0957-116">Returns</span></span>  
 <span data-ttu-id="c0957-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0957-117">S_OK</span></span>  
 <span data-ttu-id="c0957-118">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c0957-118">The function succeeded.</span></span>  
  
 [<span data-ttu-id="c0957-119">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="c0957-119">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="c0957-120">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c0957-120">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="c0957-121">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="c0957-121">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="c0957-122">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="c0957-122">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="c0957-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="c0957-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="c0957-124">El nombre de instancia de especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="c0957-124">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="c0957-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="c0957-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="c0957-126">La instancia especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="c0957-126">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="c0957-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="c0957-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="c0957-128">Se requieren privilegios de administrador para ejecutar esta operación.</span><span class="sxs-lookup"><span data-stu-id="c0957-128">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="c0957-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span><span class="sxs-lookup"><span data-stu-id="c0957-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span></span>](../express-localdb-error-messages/localdb-error-shared-name-taken.md)  
 <span data-ttu-id="c0957-130">El nombre compartido especificado ya existe.</span><span class="sxs-lookup"><span data-stu-id="c0957-130">The specified shared name is already taken.</span></span>  
  
 [<span data-ttu-id="c0957-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="c0957-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>](../express-localdb-error-messages/localdb-error-instance-already-shared.md)  
 <span data-ttu-id="c0957-132">Ya se está compartiendo la instancia especificada.</span><span class="sxs-lookup"><span data-stu-id="c0957-132">The specified instance is already shared.</span></span>  
  
 [<span data-ttu-id="c0957-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="c0957-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="c0957-134">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="c0957-134">An unexpected error occurred.</span></span> <span data-ttu-id="c0957-135">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="c0957-135">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0957-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c0957-136">Remarks</span></span>  
 <span data-ttu-id="c0957-137">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c0957-137">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0957-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0957-138">See Also</span></span>  
 [<span data-ttu-id="c0957-139">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="c0957-139">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
