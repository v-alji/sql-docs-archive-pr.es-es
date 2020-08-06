---
title: Función LocalDBStopTracing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 1d50e040-8602-4ffa-be8f-b8633fdfa7ff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bf6051fe8c86728c2ebf0a0b2bc34fabb98edb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663491"
---
# <a name="localdbstoptracing-function"></a><span data-ttu-id="4c9b2-102">Función LocalDBStopTracing</span><span class="sxs-lookup"><span data-stu-id="4c9b2-102">LocalDBStopTracing Function</span></span>
  <span data-ttu-id="4c9b2-103">Deshabilita el seguimiento de las llamadas a la API para todas las instancias de SQL Server Express LocalDB que son propiedad del usuario de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-103">Disables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="4c9b2-104">**Archivo de encabezado:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="4c9b2-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9b2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c9b2-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="4c9b2-106">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="4c9b2-106">Returns</span></span>  
 <span data-ttu-id="4c9b2-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c9b2-107">S_OK</span></span>  
 <span data-ttu-id="4c9b2-108">La función se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="4c9b2-109">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="4c9b2-109">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="4c9b2-110">Se ha producido un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-110">An unexpected error occurred.</span></span> <span data-ttu-id="4c9b2-111">Vea el registro de eventos para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-111">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c9b2-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c9b2-112">Remarks</span></span>  
 <span data-ttu-id="4c9b2-113">Para obtener un ejemplo de código que utilice LocalDB API, vea [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4c9b2-113">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9b2-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c9b2-114">See Also</span></span>  
 [<span data-ttu-id="4c9b2-115">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="4c9b2-115">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
