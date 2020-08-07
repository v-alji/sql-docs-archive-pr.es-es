---
title: Tipos de replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], types
ms.assetid: c1655e8d-d14c-455a-a7f9-9d2f43e88ab4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5576331004eca44bc32dbde8f430284f75e6eb70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746880"
---
# <a name="types-of-replication"></a><span data-ttu-id="54fa3-102">Tipos de replicación</span><span class="sxs-lookup"><span data-stu-id="54fa3-102">Types of Replication</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="54fa3-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona los siguientes tipos de replicación para usarlos en las aplicaciones distribuidas:</span><span class="sxs-lookup"><span data-stu-id="54fa3-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of replication for use in distributed applications:</span></span>  
  
-   <span data-ttu-id="54fa3-104">Replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="54fa3-104">Transactional replication.</span></span> <span data-ttu-id="54fa3-105">Para obtener más información, consulte [Replicación transaccional](transactional/transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="54fa3-105">For more information, see [Transactional Replication](transactional/transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="54fa3-106">Replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="54fa3-106">Merge replication.</span></span> <span data-ttu-id="54fa3-107">Para obtener más información, consulte [Replicación de mezcla](merge/merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="54fa3-107">For more information, see [Merge Replication](merge/merge-replication.md).</span></span>  
  
-   <span data-ttu-id="54fa3-108">Replicación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="54fa3-108">Snapshot replication.</span></span> <span data-ttu-id="54fa3-109">Para obtener más información, consulte [Replicación de instantáneas](snapshot-replication.md).</span><span class="sxs-lookup"><span data-stu-id="54fa3-109">For more information, see [Snapshot Replication](snapshot-replication.md).</span></span>  
  
 <span data-ttu-id="54fa3-110">El tipo de replicación que se elige para una aplicación depende de muchos factores, como el entorno físico de la replicación, el tipo y la cantidad de datos que se desean replicar y si los datos se actualizan en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="54fa3-110">The type of replication you choose for an application depends on many factors, including the physical replication environment, the type and quantity of data to be replicated, and whether the data is updated at the Subscriber.</span></span> <span data-ttu-id="54fa3-111">El entorno físico incluye el número y la ubicación de los equipos que participan en la replicación, y si estos equipos son clientes (estaciones de trabajo, equipos portátiles o dispositivos de mano) o servidores.</span><span class="sxs-lookup"><span data-stu-id="54fa3-111">The physical environment includes the number and location of computers involved in replication and whether these computers are clients (workstations, laptops, or handheld devices) or servers.</span></span>  
  
 <span data-ttu-id="54fa3-112">Por lo general, cada tipo de replicación comienza con una sincronización inicial de los objetos publicados entre el publicador y los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="54fa3-112">Each type of replication typically begins with an initial synchronization of the published objects between the Publisher and Subscribers.</span></span> <span data-ttu-id="54fa3-113">Esta sincronización inicial puede llevarse a cabo mediante la replicación con una *instantánea*, que es una copia de todos los objetos y datos especificados por una publicación.</span><span class="sxs-lookup"><span data-stu-id="54fa3-113">This initial synchronization can be performed by replication with a *snapshot*, which is a copy of all of the objects and data specified by a publication.</span></span> <span data-ttu-id="54fa3-114">Una vez creada la instantánea, se envía a los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="54fa3-114">After the snapshot is created, it is delivered to the Subscribers.</span></span> <span data-ttu-id="54fa3-115">Para algunas aplicaciones, la replicación de instantáneas es lo único que se necesita.</span><span class="sxs-lookup"><span data-stu-id="54fa3-115">For some applications, snapshot replication is all that is required.</span></span> <span data-ttu-id="54fa3-116">Para otros tipos de aplicaciones, es importante que los cambios de datos posteriores fluyan al suscriptor de forma incremental a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="54fa3-116">For other types of applications, it is important that subsequent data changes flow to the Subscriber incrementally over time.</span></span> <span data-ttu-id="54fa3-117">Algunas aplicaciones también requieren que los cambios vuelvan del suscriptor al publicador.</span><span class="sxs-lookup"><span data-stu-id="54fa3-117">Some applications also require that changes flow from the Subscriber back to the Publisher.</span></span> <span data-ttu-id="54fa3-118">La replicación transaccional y la replicación de mezcla proporcionan opciones para estos tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="54fa3-118">Transactional replication and merge replication provide options for these types of applications.</span></span>  
  
 <span data-ttu-id="54fa3-119">En la replicación de instantáneas, no se realiza un seguimiento de los cambios de datos; cada vez que se aplica una instantánea, ésta sobrescribe completamente los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="54fa3-119">Data changes are not tracked for snapshot replication; each time a snapshot is applied, it completely overwrites the existing data.</span></span> <span data-ttu-id="54fa3-120">La replicación transaccional realiza un seguimiento de los cambios a través del registro de transacciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y la replicación de mezcla realiza un seguimiento de los cambios a través de desencadenadores y tablas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="54fa3-120">Transactional replication tracks changes through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction log, and merge replication tracks changes through triggers and metadata tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fa3-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54fa3-121">See Also</span></span>  
 [<span data-ttu-id="54fa3-122">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="54fa3-122">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
