---
title: MSSQL_ENG020572 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020572 error
ms.assetid: 636566db-ffcf-4109-8c11-15b8c7cb9cd9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5762f160e119012f4fdc0ca1a205ba0ecf690378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677581"
---
# <a name="mssql_eng020572"></a><span data-ttu-id="04a9b-102">MSSQL_ENG020572</span><span class="sxs-lookup"><span data-stu-id="04a9b-102">MSSQL_ENG020572</span></span>
    
## <a name="message-details"></a><span data-ttu-id="04a9b-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="04a9b-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04a9b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="04a9b-104">Product Name</span></span>|<span data-ttu-id="04a9b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="04a9b-105">SQL Server</span></span>|  
|<span data-ttu-id="04a9b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="04a9b-106">Event ID</span></span>|<span data-ttu-id="04a9b-107">20572</span><span class="sxs-lookup"><span data-stu-id="04a9b-107">20572</span></span>|  
|<span data-ttu-id="04a9b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="04a9b-108">Event Source</span></span>|<span data-ttu-id="04a9b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="04a9b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="04a9b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="04a9b-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="04a9b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="04a9b-111">Symbolic Name</span></span>||  
|<span data-ttu-id="04a9b-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="04a9b-112">Message Text</span></span>|<span data-ttu-id="04a9b-113">Se ha reinicializado la suscripción del suscriptor '%s' al artículo '%s' en la publicación '%s' porque no pasó la validación.</span><span class="sxs-lookup"><span data-stu-id="04a9b-113">Subscriber '%s' subscription to article '%s' in publication '%s' has been reinitialized after a validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="04a9b-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="04a9b-114">Explanation</span></span>  
 <span data-ttu-id="04a9b-115">Los datos del suscriptor se validaron con los datos del publicador y no coinciden, por lo que se ha generado un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="04a9b-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="04a9b-116">Cuando especificó que la validación se debería realizar, seleccionó la opción de que se debería reinicializar una suscripción si se generaba un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="04a9b-116">When you specified that validation should be performed, you selected the option that a subscription should be reinitialized if validation failed.</span></span> <span data-ttu-id="04a9b-117">La reinicialización de una suscripción implica la aplicación de una instantánea nueva en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="04a9b-117">Reinitializing a subscription involves applying a new snapshot at the Subscriber.</span></span> <span data-ttu-id="04a9b-118">Para obtener más información acerca de la validación, consulte [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="04a9b-118">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04a9b-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="04a9b-119">User Action</span></span>  
 <span data-ttu-id="04a9b-120">Los datos del publicador y el suscriptor coincidirán después de aplicar una nueva instantánea en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="04a9b-120">Data at the Publisher and Subscriber will match after the new snapshot is applied at the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a9b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04a9b-121">See Also</span></span>  
 [<span data-ttu-id="04a9b-122">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="04a9b-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
