---
title: LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c1595263-6264-4a43-9535-5eb76ece3a57
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0896f3e70e6c65a1fcd0de4169249fb622e6b5f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662940"
---
# <a name="localdb_error_too_many_shared_instances"></a><span data-ttu-id="5d42e-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span><span class="sxs-lookup"><span data-stu-id="5d42e-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span></span>
    
## <a name="details"></a><span data-ttu-id="5d42e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d42e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d42e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5d42e-104">Product Name</span></span>|<span data-ttu-id="5d42e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d42e-105">SQL Server</span></span>|  
|<span data-ttu-id="5d42e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5d42e-106">Event ID</span></span>|<span data-ttu-id="5d42e-107">287</span><span class="sxs-lookup"><span data-stu-id="5d42e-107">287</span></span>|  
|<span data-ttu-id="5d42e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5d42e-108">Event Source</span></span>|<span data-ttu-id="5d42e-109">SQL Server Local Database Runtime 12.0</span><span class="sxs-lookup"><span data-stu-id="5d42e-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="5d42e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5d42e-110">Component</span></span>|<span data-ttu-id="5d42e-111">API de Local Database Runtime</span><span class="sxs-lookup"><span data-stu-id="5d42e-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="5d42e-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5d42e-112">Message Text</span></span>|<span data-ttu-id="5d42e-113">Hay demasiadas instancias compartidas y no se puede generar un nombre de instancia único.</span><span class="sxs-lookup"><span data-stu-id="5d42e-113">There are too many shared instance and we cannot generate unique User Instance Name.</span></span> <span data-ttu-id="5d42e-114">Deje de compartir parte de las instancias compartidas existentes.</span><span class="sxs-lookup"><span data-stu-id="5d42e-114">Unshare some of the existing shared instances.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d42e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="5d42e-115">Explanation</span></span>  
 <span data-ttu-id="5d42e-116">Hay demasiadas instancias compartidas y no se puede generar un nombre de instancia único.</span><span class="sxs-lookup"><span data-stu-id="5d42e-116">There are too many shared instance and we cannot generate unique User Instance Name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d42e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5d42e-117">User Action</span></span>  
 <span data-ttu-id="5d42e-118">Deje de compartir una o varias instancias de Local Database Runtime compartidas e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d42e-118">Unshare one or more of the shared Local Database Runtime instances and try again.</span></span>  
  
  
