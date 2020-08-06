---
title: Función LocalDBGetVersions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersions
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 033a9c6b-0d7f-4f8a-ab60-33cd6fee0d33
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 37d2a927346252f1b126f5e3a4ec78ea03cde0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749954"
---
# <a name="localdbgetversions-function"></a><span data-ttu-id="89759-102">Función LocalDBGetVersions</span><span class="sxs-lookup"><span data-stu-id="89759-102">LocalDBGetVersions Function</span></span>
  <span data-ttu-id="89759-103">Devuelve todas las versiones de SQL Server Express LocalDB disponibles en el equipo.</span><span class="sxs-lookup"><span data-stu-id="89759-103">Returns all SQL Server Express LocalDB versions available on the computer.</span></span>  
  
 <span data-ttu-id="89759-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="89759-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89759-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89759-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_VERSION_LENGTH 43typedef WCHAR TLocalDBVersion[MAX_LOCALDB_VERSION_LENGTH + 1];typedef TLocalDBVersion* PTLocalDBVersion;HRESULT LocalDBGetVersions(           PTLocalDBVersion pVersion,           LPDWORD lpdwNumberOfVersions);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89759-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89759-106">Parameters</span></span>  
 <span data-ttu-id="89759-107">*pVersionNames*</span><span class="sxs-lookup"><span data-stu-id="89759-107">*pVersionNames*</span></span>  
 <span data-ttu-id="89759-108">Genere Contiene los nombres de las versiones de LocalDB que están disponibles en la estación de trabajo del usuario.</span><span class="sxs-lookup"><span data-stu-id="89759-108">[Output] Contains names of the LocalDB versions that are available on the user's workstation.</span></span>  
  
 <span data-ttu-id="89759-109">*lpdwNumberOfVersions*</span><span class="sxs-lookup"><span data-stu-id="89759-109">*lpdwNumberOfVersions*</span></span>  
 <span data-ttu-id="89759-110">[Input/Output] En la entrada, contiene el número de zonas para las versiones en el búfer de *pVersionNames* .</span><span class="sxs-lookup"><span data-stu-id="89759-110">[Input/Output] On input holds the number of slots for versions in the *pVersionNames* buffer.</span></span>   
<span data-ttu-id="89759-111">En salida, contiene el número de versiones de LocalDB existentes.</span><span class="sxs-lookup"><span data-stu-id="89759-111">On output, holds the number of existing LocalDB versions.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="89759-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="89759-112">Returns</span></span>  
 <span data-ttu-id="89759-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="89759-113">S_OK</span></span>  
 <span data-ttu-id="89759-114">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="89759-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="89759-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="89759-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="89759-116">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="89759-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="89759-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="89759-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="89759-118">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="89759-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="89759-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="89759-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="89759-120">El búfer de entrada es demasiado corto y no se ha solicitado truncamiento.</span><span class="sxs-lookup"><span data-stu-id="89759-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="89759-121">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="89759-121">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="89759-122">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="89759-122">An unexpected error occurred.</span></span> <span data-ttu-id="89759-123">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="89759-123">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89759-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="89759-124">Remarks</span></span>  
 <span data-ttu-id="89759-125">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="89759-125">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89759-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89759-126">See Also</span></span>  
 [<span data-ttu-id="89759-127">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="89759-127">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
