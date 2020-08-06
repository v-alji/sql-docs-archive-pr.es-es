---
title: Inicialización de nuevos nodos del mismo nivel (replicación punto a punto) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.p2pwizard.init.f1
ms.assetid: 050c00e1-78bd-4d9c-affe-40e22feb4d94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26658fdfbcf0d3d3a88bedbace4102cda6cee9c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675279"
---
# <a name="new-peer-initialization-peer-to-peer-replication"></a><span data-ttu-id="2fde3-102">Inicialización de nuevos nodos del mismo nivel (replicación punto a punto)</span><span class="sxs-lookup"><span data-stu-id="2fde3-102">New Peer Initialization (Peer-to-Peer Replication)</span></span>
  <span data-ttu-id="2fde3-103"> Use la página **Inicialización de nuevos nodos del mismo nivel** para especificar cómo se han inicializado las bases de datos del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="2fde3-103">Use the **New Peer Initialization** page to specify how peer databases were initialized.</span></span> <span data-ttu-id="2fde3-104">(Los elementos del mismo nivel se deben inicializar antes de completar este asistente). Los elementos del mismo nivel se inicializan manualmente o mediante la funcionalidad **Initialize with backup** que proporciona la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="2fde3-104">(Peers must be initialized before you complete this wizard.) Peers are initialized manually or by using the **initialize with backup** functionality that is provided by transactional replication.</span></span> <span data-ttu-id="2fde3-105">(La replicación transaccional punto a punto no admite la inicialización de elementos del mismo nivel mediante una instantánea). Si se deben inicializar diferentes pares con métodos diferentes, debe agregar los elementos del mismo nivel por separado mediante la ejecución del asistente varias veces.</span><span class="sxs-lookup"><span data-stu-id="2fde3-105">(Peer-to-peer transactional replication does not support initializing peers by using a snapshot.) If different peers have to be initialized using different methods, you must add the peers separately by running the wizard multiple times.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2fde3-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="2fde3-106">Options</span></span>  
 <span data-ttu-id="2fde3-107">**Especificar cómo se inicializaron las nuevas bases de datos del mismo nivel.**</span><span class="sxs-lookup"><span data-stu-id="2fde3-107">**Specify how the new peer database(s) was initialized**</span></span>  
 <span data-ttu-id="2fde3-108">El esquema y los datos correspondientes a todos los objetos publicados deben estar presentes en cada nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="2fde3-108">The schema and data for all published objects must be present at each peer.</span></span> <span data-ttu-id="2fde3-109">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2fde3-109">Select one of the following options:</span></span>  
  
-   <span data-ttu-id="2fde3-110">Seleccione la primera opción si ha creado manualmente el esquema de los objetos publicados o si ha restaurado una copia de seguridad pero no se han efectuado cambios en la primera base de datos de publicación desde la creación de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2fde3-110">Select the first option if you have manually created the schema for published objects or you have restored a backup, and no data changes have been made at the first publication database since the backup was taken.</span></span> <span data-ttu-id="2fde3-111">Si ha creado el esquema manualmente, debe asegurarse de que todos los datos requeridos estén presentes en cada nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="2fde3-111">If you created the schema manually, you must ensure that all required data is present at each peer.</span></span> <span data-ttu-id="2fde3-112">Esta opción corresponde a un valor de **replication support only** para la propiedad de suscripción **sync_type**.</span><span class="sxs-lookup"><span data-stu-id="2fde3-112">This option corresponds to a value of **replication support only** for the subscription property **sync_type**.</span></span>  
  
-   <span data-ttu-id="2fde3-113">Seleccione la segunda opción si ha restaurado una copia de seguridad, y si se han efectuado cambios en la primera base de datos de publicaciones desde la obtención de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2fde3-113">Select the second option if you have restored a backup, and data changes have been made at the first publication database since the backup was taken.</span></span> <span data-ttu-id="2fde3-114">La replicación debe entregar los cambios desde la primera base de datos de publicaciones que no se incluyeron en la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2fde3-114">Replication must now deliver changes from the first publication database that were not included in the backup.</span></span> <span data-ttu-id="2fde3-115">Esta opción corresponde a un valor de **initialize with backup** para la propiedad de suscripción **sync_type**.</span><span class="sxs-lookup"><span data-stu-id="2fde3-115">This option corresponds to a value of **initialize with backup** for the subscription property **sync_type**.</span></span>  
  
     <span data-ttu-id="2fde3-116">Cuando se habilita una publicación para una replicación punto a punto, se establece la propiedad de publicación **ayos_initialize_from_backup** .</span><span class="sxs-lookup"><span data-stu-id="2fde3-116">When a publication is enabled for peer-to-peer replication, the **allow_initialize_from_backup** publication property is set.</span></span> <span data-ttu-id="2fde3-117">La replicación empieza inmediatamente a realizar el seguimiento de los cambios en la primera base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="2fde3-117">Replication immediately starts to track changes in the first publication database.</span></span> <span data-ttu-id="2fde3-118">Por tanto, estos cambios se pueden entregar a una base de datos restaurada en uno o más pares si la opción **initialize with backup** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2fde3-118">Therefore, these changes can be delivered to a restored database at one or more peers if the **initialize with backup** option is selected.</span></span> <span data-ttu-id="2fde3-119">Haga clic en el botón **Examinar** para localizar la copia de seguridad utilizada; la replicación leerá el número de secuencia de registro (LSN) de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2fde3-119">Click the **Browse** button to locate the backup used, and replication will read the log sequence number (LSN) from the backup.</span></span> <span data-ttu-id="2fde3-120">Todos los cambios efectuados en la primera base de datos de publicación que tengan un LSN más alto se entregarán a cada nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="2fde3-120">All changes in the first publication database that have a higher LSN will be delivered to each peer.</span></span>  
  
     <span data-ttu-id="2fde3-121">Es posible que esta opción no esté disponible si la creación o la agregación se realizan en una topología que incluye [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2fde3-121">This option might not be available if you are creating or adding to a topology that includes [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="2fde3-122">La tabla siguiente muestra si la opción está disponible al agregar un nodo a una topología existente.</span><span class="sxs-lookup"><span data-stu-id="2fde3-122">The following table shows whether the option is available when you are adding a node to an existing topology.</span></span>  
  
    |<span data-ttu-id="2fde3-123">Nuevo nodo</span><span class="sxs-lookup"><span data-stu-id="2fde3-123">New node</span></span>|<span data-ttu-id="2fde3-124">Primer nodo</span><span class="sxs-lookup"><span data-stu-id="2fde3-124">First node</span></span>|<span data-ttu-id="2fde3-125">Nodos adicionales</span><span class="sxs-lookup"><span data-stu-id="2fde3-125">Additional nodes</span></span>|<span data-ttu-id="2fde3-126">Opción</span><span class="sxs-lookup"><span data-stu-id="2fde3-126">Option</span></span>|  
    |--------------|----------------|----------------------|------------|  
    |[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="2fde3-127">Disabled</span><span class="sxs-lookup"><span data-stu-id="2fde3-127">Disabled</span></span>|  
    |[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="2fde3-128">None</span><span class="sxs-lookup"><span data-stu-id="2fde3-128">None</span></span>|<span data-ttu-id="2fde3-129">Disabled</span><span class="sxs-lookup"><span data-stu-id="2fde3-129">Disabled</span></span>|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="2fde3-130">Disabled</span><span class="sxs-lookup"><span data-stu-id="2fde3-130">Disabled</span></span>|  
    |[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="2fde3-131">None</span><span class="sxs-lookup"><span data-stu-id="2fde3-131">None</span></span>|<span data-ttu-id="2fde3-132">habilitado</span><span class="sxs-lookup"><span data-stu-id="2fde3-132">Enabled</span></span>|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="2fde3-133">None</span><span class="sxs-lookup"><span data-stu-id="2fde3-133">None</span></span>|<span data-ttu-id="2fde3-134">habilitado</span><span class="sxs-lookup"><span data-stu-id="2fde3-134">Enabled</span></span>|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="2fde3-135">habilitado</span><span class="sxs-lookup"><span data-stu-id="2fde3-135">Enabled</span></span>|  
    |[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="2fde3-136">None</span><span class="sxs-lookup"><span data-stu-id="2fde3-136">None</span></span>|<span data-ttu-id="2fde3-137">habilitado</span><span class="sxs-lookup"><span data-stu-id="2fde3-137">Enabled</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fde3-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fde3-138">See Also</span></span>  
 <span data-ttu-id="2fde3-139">[Administrar una topología punto a punto &#40;programación de la replicación con Transact-SQL&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="2fde3-139">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="2fde3-140">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="2fde3-140">Peer-to-Peer Transactional Replication</span></span>](transactional/peer-to-peer-transactional-replication.md)  
  
  