---
title: Función LocalDBGetVersionInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersionInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: d4aaea30-1d0d-4436-bcdc-5c101d27b1c1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e30bb4dcd4c258db899883f650dbfe7100171ef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751046"
---
# <a name="localdbgetversioninfo-function"></a><span data-ttu-id="5614c-102">Función LocalDBGetVersionInfo</span><span class="sxs-lookup"><span data-stu-id="5614c-102">LocalDBGetVersionInfo Function</span></span>
  <span data-ttu-id="5614c-103">Devuelve información de la versión de SQL Server Express LocalDB especificada, por ejemplo si existe y el número de versión completo de LocalDB (incluida la compilación y los números de versión).</span><span class="sxs-lookup"><span data-stu-id="5614c-103">Returns information for the specified SQL Server Express LocalDB version, such as whether it exists and the full LocalDB version number (including build and release numbers).</span></span>  
  
 <span data-ttu-id="5614c-104">La información se devuelve en el formato de un `struct` **LocalDBVersionInfo**con nombre, que tiene la siguiente definición.</span><span class="sxs-lookup"><span data-stu-id="5614c-104">The information is returned in the form of a `struct` named **LocalDBVersionInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBVersionInfo  
{  
      // Contains the size of the LocalDBVersionInfo struct  
      DWORD  cbLocalDBVersionInfoSize;  
  
      // Holds the version name  
      TLocalDBVersionwszVersion;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
} LocalDBVersionInfo;  
  
```  
  
 <span data-ttu-id="5614c-105">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="5614c-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5614c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5614c-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetVersionInfo(  
           PCWSTR wszVersionName,           PLocalDBVersionInfo pVersionInfo,           DWORD dwVersionInfoSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5614c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5614c-107">Parameters</span></span>  
 <span data-ttu-id="5614c-108">*wszVersionName*</span><span class="sxs-lookup"><span data-stu-id="5614c-108">*wszVersionName*</span></span>  
 <span data-ttu-id="5614c-109">[Entrada] El nombre de versión de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="5614c-109">[Input] The LocalDB version name.</span></span>  
  
 <span data-ttu-id="5614c-110">*pVersionInfo*</span><span class="sxs-lookup"><span data-stu-id="5614c-110">*pVersionInfo*</span></span>  
 <span data-ttu-id="5614c-111">[Output] El búfer en el que se almacena información sobre la versión de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="5614c-111">[Output] The buffer to store the information about the LocalDB version.</span></span>  
  
 <span data-ttu-id="5614c-112">*dwVersionInfoSize*</span><span class="sxs-lookup"><span data-stu-id="5614c-112">*dwVersionInfoSize*</span></span>  
 <span data-ttu-id="5614c-113">Entradas Contiene el tamaño del búfer *versionInfo* .</span><span class="sxs-lookup"><span data-stu-id="5614c-113">[Input] Holds the size of the *VersionInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="5614c-114">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="5614c-114">Returns</span></span>  
 <span data-ttu-id="5614c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5614c-115">S_OK</span></span>  
 <span data-ttu-id="5614c-116">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="5614c-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="5614c-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="5614c-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="5614c-118">SQL Server Express LocalDB no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5614c-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="5614c-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="5614c-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="5614c-120">Uno o más parámetros de entrada especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="5614c-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="5614c-121">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="5614c-121">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="5614c-122">La versión de LocalDB especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="5614c-122">The specified LocalDB version does not exist.</span></span>  
  
 [<span data-ttu-id="5614c-123">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="5614c-123">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="5614c-124">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="5614c-124">An unexpected error occurred.</span></span> <span data-ttu-id="5614c-125">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="5614c-125">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5614c-126">Detalles</span><span class="sxs-lookup"><span data-stu-id="5614c-126">Details</span></span>  
 <span data-ttu-id="5614c-127">La lógica que subyace a la introducción del `struct` argumento de tamaño (*lpVersionInfoSize*) es permitir que la API devuelva distintas versiones de **LocalDBVersionInfostruct**, con lo que se habilita la compatibilidad con versiones anteriores y posteriores.</span><span class="sxs-lookup"><span data-stu-id="5614c-127">The rationale behind the introduction of the `struct` size argument (*lpVersionInfoSize*) is to enable the API to return different versions of the **LocalDBVersionInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="5614c-128">Si el `struct` argumento de tamaño (*lpVersionInfoSize*) coincide con el tamaño de una versión conocida de **LocalDBVersionInfostruct**, se devuelve esa versión de `struct` .</span><span class="sxs-lookup"><span data-stu-id="5614c-128">If the `struct` size argument (*lpVersionInfoSize*) matches the size of a known version of the **LocalDBVersionInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="5614c-129">De lo contrario, se devuelve LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="5614c-129">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="5614c-130">Un ejemplo típico de uso de la API de **LocalDBGetVersionInfo** tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="5614c-130">A typical example of **LocalDBGetVersionInfo** API usage looks like this:</span></span>  
  
```  
LocalDBVersionInfo vi;  
LocalDBVersionInfo(L"11.0", &vi, sizeof(LocalDBVersionInfo));  
  
```  
  
## <a name="remarks"></a><span data-ttu-id="5614c-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5614c-131">Remarks</span></span>  
 <span data-ttu-id="5614c-132">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5614c-132">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5614c-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5614c-133">See Also</span></span>  
 [<span data-ttu-id="5614c-134">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="5614c-134">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
