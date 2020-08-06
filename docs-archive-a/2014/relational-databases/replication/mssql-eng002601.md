---
title: MSSQL_ENG002601 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002601 error
ms.assetid: 657c3ae6-9e4b-4c60-becc-4caf7435c1dc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2e8340fef83749fd6d041af42566b10ed3542c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749730"
---
# <a name="mssql_eng002601"></a><span data-ttu-id="dae56-102">MSSQL_ENG002601</span><span class="sxs-lookup"><span data-stu-id="dae56-102">MSSQL_ENG002601</span></span>
    
## <a name="message-details"></a><span data-ttu-id="dae56-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="dae56-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dae56-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="dae56-104">Product Name</span></span>|<span data-ttu-id="dae56-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dae56-105">SQL Server</span></span>|  
|<span data-ttu-id="dae56-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="dae56-106">Event ID</span></span>|<span data-ttu-id="dae56-107">2601</span><span class="sxs-lookup"><span data-stu-id="dae56-107">2601</span></span>|  
|<span data-ttu-id="dae56-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="dae56-108">Event Source</span></span>|<span data-ttu-id="dae56-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dae56-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dae56-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dae56-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="dae56-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dae56-111">Symbolic Name</span></span>|<span data-ttu-id="dae56-112">N/D</span><span class="sxs-lookup"><span data-stu-id="dae56-112">N/A</span></span>|  
|<span data-ttu-id="dae56-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dae56-113">Message Text</span></span>|<span data-ttu-id="dae56-114">No se puede insertar una fila de clave duplicada en el objeto '%.\*ls' con índice único '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="dae56-114">Cannot insert duplicate key row in object '%.\*ls' with unique index '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dae56-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="dae56-115">Explanation</span></span>  
 <span data-ttu-id="dae56-116">Se trata de un error general que puede producirse independientemente de que la base de datos esté replicada o no.</span><span class="sxs-lookup"><span data-stu-id="dae56-116">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="dae56-117">En las bases de datos replicadas, el error suele producirse cuando las claves principales no se han administrado adecuadamente en la topología.</span><span class="sxs-lookup"><span data-stu-id="dae56-117">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="dae56-118">En un entorno distribuido es fundamental asegurarse de que no se inserta el mismo valor en una columna de clave principal o en otra columna única en más de un nodo.</span><span class="sxs-lookup"><span data-stu-id="dae56-118">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="dae56-119">Entre las posibles causas figuran:</span><span class="sxs-lookup"><span data-stu-id="dae56-119">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="dae56-120">Se están llevando a cabo inserciones y actualizaciones en una fila en más de un nodo.</span><span class="sxs-lookup"><span data-stu-id="dae56-120">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="dae56-121">Tanto la replicación de mezcla como las suscripciones actualizables de la replicación transaccional ofrecen detección y resolución de conflictos, aunque es preferible insertar o actualizar una fila concreta solo en un nodo.</span><span class="sxs-lookup"><span data-stu-id="dae56-121">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="dae56-122">La replicación transaccional del mismo nivel no ofrece detección y resolución de conflictos; exige que las inserciones y las actualizaciones estén divididas en particiones.</span><span class="sxs-lookup"><span data-stu-id="dae56-122">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="dae56-123">Se ha insertado una fila en un suscriptor que debería ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="dae56-123">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="dae56-124">Los suscriptores de publicaciones de instantáneas deben tratarse como de solo lectura, al igual que los suscriptores de publicaciones transaccionales, a menos que se utilicen suscripciones actualizables o replicación transaccional del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="dae56-124">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="dae56-125">Se está utilizando una tabla con una columna de identidad, pero la columna no está correctamente administrada.</span><span class="sxs-lookup"><span data-stu-id="dae56-125">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
-   <span data-ttu-id="dae56-126">En la replicación de mezcla, este error puede producirse también durante una inserción en la tabla del sistema **MSmerge_contents**; el error que se produce es similar al siguiente: No se puede insertar una fila de clave duplicada en el objeto 'MSmerge_contents' con índice único 'ucl1SycContents'.</span><span class="sxs-lookup"><span data-stu-id="dae56-126">In merge replication, this error can also occur during an insert into the system table **MSmerge_contents**; the error raised is similar to: Cannot insert duplicate key row in object 'MSmerge_contents' with unique index 'ucl1SycContents.'</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dae56-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dae56-127">User Action</span></span>  
 <span data-ttu-id="dae56-128">La acción que debe llevarse a cabo depende del motivo por el que se produjo el error:</span><span class="sxs-lookup"><span data-stu-id="dae56-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="dae56-129">Se están llevando a cabo inserciones y actualizaciones en una fila en más de un nodo.</span><span class="sxs-lookup"><span data-stu-id="dae56-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="dae56-130">Independientemente del tipo de replicación utilizada, se recomienda que, siempre que sea posible, las inserciones y las actualizaciones se dividan en particiones, ya que esto reduce el procesamiento necesario para la detección y resolución de conflictos.</span><span class="sxs-lookup"><span data-stu-id="dae56-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="dae56-131">En la replicación transaccional del mismo nivel, se exige dividir en particiones las inserciones y las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="dae56-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="dae56-132">Para obtener más información, consulte [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="dae56-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="dae56-133">Se ha insertado una fila en un suscriptor que debería ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="dae56-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="dae56-134">No inserte ni actualice filas en el suscriptor a menos que esté utilizando replicación de mezcla, replicación transaccional con suscripciones actualizables o replicación transaccional del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="dae56-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="dae56-135">Se está utilizando una tabla con una columna de identidad, pero la columna no está correctamente administrada.</span><span class="sxs-lookup"><span data-stu-id="dae56-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="dae56-136">En la replicación de mezcla y la replicación transaccional con suscripciones actualizables, las columnas de identidad deben ser administradas automáticamente por la replicación.</span><span class="sxs-lookup"><span data-stu-id="dae56-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="dae56-137">En la replicación transaccional de punto a punto, es necesario administrarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="dae56-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="dae56-138">Para más información, vea [Replicar columnas de identidad](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="dae56-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
-   <span data-ttu-id="dae56-139">El error se produce durante una inserción en la tabla del sistema **MSmerge_contents**.</span><span class="sxs-lookup"><span data-stu-id="dae56-139">The error occurs during an insert into the system table **MSmerge_contents**.</span></span>  
  
     <span data-ttu-id="dae56-140">Este error se puede producir debido a un valor incorrecto de la propiedad del filtro de combinación **join_unique_key**.</span><span class="sxs-lookup"><span data-stu-id="dae56-140">This error can occur because of an incorrect value for the join filter property **join_unique_key**.</span></span> <span data-ttu-id="dae56-141">Esta propiedad debe definirse como TRUE solo si la columna combinada de la tabla primaria es única.</span><span class="sxs-lookup"><span data-stu-id="dae56-141">This property should be set to TRUE only if the joined column in the parent table is unique.</span></span> <span data-ttu-id="dae56-142">El error se produce si la propiedad se define como TRUE pero la columna no es única.</span><span class="sxs-lookup"><span data-stu-id="dae56-142">If the property is set to TRUE, but the column is not unique, this error is raised.</span></span> <span data-ttu-id="dae56-143">Para obtener más información acerca de cómo configurar esta propiedad, vea [Definir y modificar un filtro de combinación entre artículos de mezcla](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="dae56-143">For more information on setting this property, see [Define and Modify a Join Filter Between Merge Articles](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae56-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dae56-144">See Also</span></span>  
 [<span data-ttu-id="dae56-145">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="dae56-145">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
