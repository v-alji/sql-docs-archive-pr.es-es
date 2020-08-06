---
title: MSSQL_ENG002627 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002627 error
ms.assetid: 7f4136ac-3784-4a41-a98c-8a02308e4883
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cf481635d6a24570792c9da04fe71ebea885ce5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750701"
---
# <a name="mssql_eng002627"></a><span data-ttu-id="706d6-102">MSSQL_ENG002627</span><span class="sxs-lookup"><span data-stu-id="706d6-102">MSSQL_ENG002627</span></span>
    
## <a name="message-details"></a><span data-ttu-id="706d6-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="706d6-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="706d6-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="706d6-104">Product Name</span></span>|<span data-ttu-id="706d6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="706d6-105">SQL Server</span></span>|  
|<span data-ttu-id="706d6-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="706d6-106">Event ID</span></span>|<span data-ttu-id="706d6-107">2627</span><span class="sxs-lookup"><span data-stu-id="706d6-107">2627</span></span>|  
|<span data-ttu-id="706d6-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="706d6-108">Event Source</span></span>|<span data-ttu-id="706d6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="706d6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="706d6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="706d6-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="706d6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="706d6-111">Symbolic Name</span></span>|<span data-ttu-id="706d6-112">N/D</span><span class="sxs-lookup"><span data-stu-id="706d6-112">N/A</span></span>|  
|<span data-ttu-id="706d6-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="706d6-113">Message Text</span></span>|<span data-ttu-id="706d6-114">Infracción de la restricción '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="706d6-114">Violation of %ls constraint '%.\*ls'.</span></span> <span data-ttu-id="706d6-115">No se puede insertar una fila de clave duplicada en el objeto '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="706d6-115">Cannot insert duplicate key in object '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="706d6-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="706d6-116">Explanation</span></span>  
 <span data-ttu-id="706d6-117">Se trata de un error general que puede producirse independientemente de que la base de datos esté replicada o no.</span><span class="sxs-lookup"><span data-stu-id="706d6-117">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="706d6-118">En las bases de datos replicadas, el error suele producirse cuando las claves principales no se han administrado adecuadamente en la topología.</span><span class="sxs-lookup"><span data-stu-id="706d6-118">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="706d6-119">En un entorno distribuido es fundamental asegurarse de que no se inserta el mismo valor en una columna de clave principal o en otra columna única en más de un nodo.</span><span class="sxs-lookup"><span data-stu-id="706d6-119">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="706d6-120">Entre las posibles causas figuran:</span><span class="sxs-lookup"><span data-stu-id="706d6-120">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="706d6-121">Se están llevando a cabo inserciones y actualizaciones en una fila en más de un nodo.</span><span class="sxs-lookup"><span data-stu-id="706d6-121">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="706d6-122">Tanto la replicación de mezcla como las suscripciones actualizables de la replicación transaccional ofrecen detección y resolución de conflictos, aunque es preferible insertar o actualizar una fila concreta solo en un nodo.</span><span class="sxs-lookup"><span data-stu-id="706d6-122">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="706d6-123">La replicación transaccional del mismo nivel no ofrece detección y resolución de conflictos; exige que las inserciones y las actualizaciones estén divididas en particiones.</span><span class="sxs-lookup"><span data-stu-id="706d6-123">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="706d6-124">Se ha insertado una fila en un suscriptor que debería ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="706d6-124">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="706d6-125">Los suscriptores de publicaciones de instantáneas deben tratarse como de solo lectura, al igual que los suscriptores de publicaciones transaccionales, a menos que se utilicen suscripciones actualizables o replicación transaccional del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="706d6-125">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="706d6-126">Se está utilizando una tabla con una columna de identidad, pero la columna no está correctamente administrada.</span><span class="sxs-lookup"><span data-stu-id="706d6-126">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="706d6-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="706d6-127">User Action</span></span>  
 <span data-ttu-id="706d6-128">La acción que debe llevarse a cabo depende del motivo por el que se produjo el error:</span><span class="sxs-lookup"><span data-stu-id="706d6-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="706d6-129">Se están llevando a cabo inserciones y actualizaciones en una fila en más de un nodo.</span><span class="sxs-lookup"><span data-stu-id="706d6-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="706d6-130">Independientemente del tipo de replicación utilizada, se recomienda que, siempre que sea posible, las inserciones y las actualizaciones se dividan en particiones, ya que esto reduce el procesamiento necesario para la detección y resolución de conflictos.</span><span class="sxs-lookup"><span data-stu-id="706d6-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="706d6-131">En la replicación transaccional del mismo nivel, se exige dividir en particiones las inserciones y las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="706d6-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="706d6-132">Para obtener más información, consulte [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="706d6-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="706d6-133">Se ha insertado una fila en un suscriptor que debería ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="706d6-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="706d6-134">No inserte ni actualice filas en el suscriptor a menos que esté utilizando replicación de mezcla, replicación transaccional con suscripciones actualizables o replicación transaccional del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="706d6-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="706d6-135">Se está utilizando una tabla con una columna de identidad, pero la columna no está correctamente administrada.</span><span class="sxs-lookup"><span data-stu-id="706d6-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="706d6-136">En la replicación de mezcla y la replicación transaccional con suscripciones actualizables, las columnas de identidad deben ser administradas automáticamente por la replicación.</span><span class="sxs-lookup"><span data-stu-id="706d6-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="706d6-137">En la replicación transaccional de punto a punto, es necesario administrarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="706d6-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="706d6-138">Para más información, vea [Replicar columnas de identidad](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="706d6-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="706d6-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="706d6-139">See Also</span></span>  
 <span data-ttu-id="706d6-140">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="706d6-140">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="706d6-141">[Replicación de mezcla](merge/merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="706d6-141">[Merge Replication](merge/merge-replication.md) </span></span>  
 <span data-ttu-id="706d6-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="706d6-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="706d6-143">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="706d6-143">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
