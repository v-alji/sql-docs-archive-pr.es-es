---
title: Función LocalDBUnshareInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBUnshareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 54012ccb-eded-43f7-8ea5-da5ce79224c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 77ebf8cad9d410b047fccede4360ca0041637986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663492"
---
# <a name="localdbunshareinstance-function"></a><span data-ttu-id="0b862-102">Función LocalDBUnshareInstance</span><span class="sxs-lookup"><span data-stu-id="0b862-102">LocalDBUnshareInstance Function</span></span>
  <span data-ttu-id="0b862-103">Detiene el uso compartido de la instancia de SQL Server Express LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="0b862-103">Stops the sharing of the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="0b862-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="0b862-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b862-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b862-105">Syntax</span></span>  
  
```  
HRESULT LocalDBUnShareInstance(  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b862-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b862-106">Parameters</span></span>  
 <span data-ttu-id="0b862-107">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="0b862-107">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="0b862-108">[Entrada] Nombre de la instancia compartida de LocalDB que se va a dejar de compartir.</span><span class="sxs-lookup"><span data-stu-id="0b862-108">[Input] The shared name for the LocalDB instance to unshare.</span></span>  
  
 <span data-ttu-id="0b862-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="0b862-109">*dwFlags*</span></span>  
 <span data-ttu-id="0b862-110">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="0b862-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="0b862-111">En estos momentos, se debe establecer en 0.</span><span class="sxs-lookup"><span data-stu-id="0b862-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0b862-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="0b862-112">Returns</span></span>  
 <span data-ttu-id="0b862-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b862-113">S_OK</span></span>  
 <span data-ttu-id="0b862-114">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b862-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="0b862-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="0b862-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="0b862-116">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0b862-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="0b862-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="0b862-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="0b862-118">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="0b862-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="0b862-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b862-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="0b862-120">El nombre de instancia de especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="0b862-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="0b862-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="0b862-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="0b862-122">La instancia especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="0b862-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="0b862-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="0b862-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="0b862-124">Se requieren privilegios de administrador para ejecutar esta operación.</span><span class="sxs-lookup"><span data-stu-id="0b862-124">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="0b862-125">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="0b862-125">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="0b862-126">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="0b862-126">An unexpected error occurred.</span></span> <span data-ttu-id="0b862-127">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="0b862-127">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b862-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0b862-128">Remarks</span></span>  
 <span data-ttu-id="0b862-129">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0b862-129">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b862-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b862-130">See Also</span></span>  
 [<span data-ttu-id="0b862-131">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="0b862-131">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
