---
title: MSSQL_ENG020574 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e224e9a87d40fa826a05c669216649c45185037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677580"
---
# <a name="mssql_eng020574"></a><span data-ttu-id="bad0f-102">MSSQL_ENG020574</span><span class="sxs-lookup"><span data-stu-id="bad0f-102">MSSQL_ENG020574</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bad0f-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="bad0f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bad0f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="bad0f-104">Product Name</span></span>|<span data-ttu-id="bad0f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bad0f-105">SQL Server</span></span>|  
|<span data-ttu-id="bad0f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="bad0f-106">Event ID</span></span>|<span data-ttu-id="bad0f-107">20574</span><span class="sxs-lookup"><span data-stu-id="bad0f-107">20574</span></span>|  
|<span data-ttu-id="bad0f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="bad0f-108">Event Source</span></span>|<span data-ttu-id="bad0f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bad0f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bad0f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bad0f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bad0f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bad0f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bad0f-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bad0f-112">Message Text</span></span>|<span data-ttu-id="bad0f-113">La suscripción del suscriptor '%s' al artículo '%s' en la publicación '%s' no pasó la validación de datos.</span><span class="sxs-lookup"><span data-stu-id="bad0f-113">Subscriber '%s' subscription to article '%s' in publication '%s' failed data validation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bad0f-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="bad0f-114">Explanation</span></span>  
 <span data-ttu-id="bad0f-115">Los datos del suscriptor se validaron con los datos del publicador y no coinciden, por lo que se ha generado un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="bad0f-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="bad0f-116">Para obtener más información acerca de la validación, consulte [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="bad0f-116">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bad0f-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bad0f-117">User Action</span></span>  
 <span data-ttu-id="bad0f-118">Se recomienda hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bad0f-118">We recommend that you do the following:</span></span>  
  
-   <span data-ttu-id="bad0f-119">Determine el motivo por el que se ha producido un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="bad0f-119">Determine why validation failed.</span></span>  
  
-   <span data-ttu-id="bad0f-120">Corrija el problema subyacente que ha causado el error.</span><span class="sxs-lookup"><span data-stu-id="bad0f-120">Correct the underlying issue that caused the failure.</span></span>  
  
-   <span data-ttu-id="bad0f-121">Establezca la convergencia de los datos reinicializando la suscripción o mediante otro método.</span><span class="sxs-lookup"><span data-stu-id="bad0f-121">Bring the data into convergence by reinitializing the subscription or through another method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad0f-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bad0f-122">See Also</span></span>  
 [<span data-ttu-id="bad0f-123">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="bad0f-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
