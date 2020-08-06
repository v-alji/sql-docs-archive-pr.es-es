---
title: Función LocalDBStartTracing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: c7b83833-6d2a-4a06-9cb7-42767bed52c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1b10482e9839d43e29da72dbe2c194a01d8248eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752165"
---
# <a name="localdbstarttracing-function"></a><span data-ttu-id="238c2-102">Función LocalDBStartTracing</span><span class="sxs-lookup"><span data-stu-id="238c2-102">LocalDBStartTracing Function</span></span>
  <span data-ttu-id="238c2-103">Habilita el seguimiento de las llamadas a la API para todas las instancias de SQL Server Express LocalDB que son propiedad del usuario de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="238c2-103">Enables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="238c2-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="238c2-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238c2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="238c2-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="238c2-106">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="238c2-106">Returns</span></span>  
 <span data-ttu-id="238c2-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="238c2-107">S_OK</span></span>  
 <span data-ttu-id="238c2-108">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="238c2-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="238c2-109">LOCALDB_ERROR_XEVENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="238c2-109">LOCALDB_ERROR_XEVENT_FAILED</span></span>](../express-localdb-error-messages/localdb-error-xevent-failed.md)  
 <span data-ttu-id="238c2-110">No se pudo iniciar el motor XEvent en la API de instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="238c2-110">Failed to start XEvent engine within the LocalDB Instance API.</span></span>  
  
 [<span data-ttu-id="238c2-111">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="238c2-111">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="238c2-112">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="238c2-112">An unexpected error occurred.</span></span> <span data-ttu-id="238c2-113">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="238c2-113">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="238c2-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="238c2-114">Remarks</span></span>  
 <span data-ttu-id="238c2-115">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="238c2-115">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238c2-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="238c2-116">See Also</span></span>  
 [<span data-ttu-id="238c2-117">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="238c2-117">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
