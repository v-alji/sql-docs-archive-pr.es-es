---
title: Sincronizar datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], about synchronization
- merge replication synchronization [SQL Server replication]
- scripts [SQL Server replication], synchronization and
- synchronization [SQL Server replication]
- snapshot replication [SQL Server], synchronization
- transactional replication, synchronization
- subscriptions [SQL Server replication], synchronizing
- on demand script execution
- replication [SQL Server], synchronization
- scripts [SQL Server replication]
ms.assetid: 724802f7-7d69-46d3-a330-bd8aa7f53114
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c92cc4d1ae8e836f169a731ecf3c37c81f3dbf10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746233"
---
# <a name="synchronize-data"></a><span data-ttu-id="e06cd-102">Sincronizar datos</span><span class="sxs-lookup"><span data-stu-id="e06cd-102">Synchronize Data</span></span>
  <span data-ttu-id="e06cd-103">La sincronización de los datos se refiere al proceso de propagación de los cambios en los datos y el esquema entre el publicador y los suscriptores después de haber aplicado la instantánea inicial en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e06cd-103">Synchronizing data refers to the process of data and schema changes being propagated between the Publisher and Subscribers after the initial snapshot has been applied at the Subscriber.</span></span> <span data-ttu-id="e06cd-104">La sincronización puede producirse:</span><span class="sxs-lookup"><span data-stu-id="e06cd-104">Synchronization can occur:</span></span>  
  
-   <span data-ttu-id="e06cd-105">De forma continua, lo que es típico de la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="e06cd-105">Continuously, which is typical for transactional replication.</span></span>  
  
-   <span data-ttu-id="e06cd-106">A petición, lo que es típico de la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="e06cd-106">On demand, which is typical for merge replication.</span></span>  
  
-   <span data-ttu-id="e06cd-107">Según una programación, lo que es típico de la replicación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="e06cd-107">On a schedule, which is typical for snapshot replication.</span></span>  
  
 <span data-ttu-id="e06cd-108">Cuando se sincroniza una suscripción, se producen diferentes procesos según el tipo de replicación que se utilice:</span><span class="sxs-lookup"><span data-stu-id="e06cd-108">When a subscription is synchronized, different processes occur based on the type of replication you are using:</span></span>  
  
-   <span data-ttu-id="e06cd-109">Replicación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="e06cd-109">Snapshot replication.</span></span> <span data-ttu-id="e06cd-110">La sincronización significa que el Agente de distribución vuelve a aplicar la instantánea en el suscriptor, de modo que los datos y el esquema de la base de datos de suscripciones sean coherentes con la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="e06cd-110">Synchronization means that the Distribution Agent reapplies the snapshot at the Subscriber so that schema and data at the subscription database is consistent with the publication database.</span></span>  
  
     <span data-ttu-id="e06cd-111">Si se han realizado modificaciones de los datos o del esquema en el publicador, es necesario generar una nueva instantánea para poder propagarlas al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e06cd-111">If modifications to data or schema have been made at the Publisher, a new snapshot must be generated in order to propagate modifications to the Subscriber.</span></span>  
  
-   <span data-ttu-id="e06cd-112">Replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="e06cd-112">Transactional replication.</span></span> <span data-ttu-id="e06cd-113">La sincronización significa que el Agente de distribución transfiere las actualizaciones, las inserciones, las eliminaciones y otros cambios de la base de datos de distribución al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e06cd-113">Synchronization means that the Distribution Agent transfers updates, inserts, deletes, and any other changes from the distribution database to the Subscriber.</span></span>  
  
-   <span data-ttu-id="e06cd-114">Replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="e06cd-114">Merge replication.</span></span> <span data-ttu-id="e06cd-115">La sincronización significa que el Agente de mezcla carga los cambios del suscriptor en el publicador y, después, descarga los cambios del publicador en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e06cd-115">Synchronization means that the Merge Agent uploads changes from the Subscriber to the Publisher and then downloads changes from the Publisher to the Subscriber.</span></span> <span data-ttu-id="e06cd-116">Si hubiera conflictos, se detectan y se resuelven.</span><span class="sxs-lookup"><span data-stu-id="e06cd-116">Conflicts, if any, are detected and resolved.</span></span> <span data-ttu-id="e06cd-117">Los datos convergen y, al final, el publicador y todos los suscriptores acaban por tener los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="e06cd-117">Data is converged, and the Publisher and all Subscribers eventually end up with the same data values.</span></span> <span data-ttu-id="e06cd-118">Si se detectan conflictos y se resuelven, el trabajo confirmado por algunos usuarios se modifica para solucionar el conflicto según las directrices definidas.</span><span class="sxs-lookup"><span data-stu-id="e06cd-118">If conflicts were detected and resolved, work that was committed by some of the users is changed to resolve the conflict according to policies you define.</span></span>  
  
 <span data-ttu-id="e06cd-119">Las publicaciones de instantáneas actualizan completamente el esquema en el suscriptor cada vez que se produce una sincronización, así que todos los cambios de esquema se aplican en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e06cd-119">Snapshot publications completely refresh the schema at the Subscriber every time synchronization occurs, so all schema changes are applied to the Subscriber.</span></span> <span data-ttu-id="e06cd-120">La replicación transaccional y la replicación de mezcla también admiten los cambios de esquema más comunes.</span><span class="sxs-lookup"><span data-stu-id="e06cd-120">Transactional replication and merge replication also support the most common schema changes.</span></span> <span data-ttu-id="e06cd-121">Para más información, vea [Realizar cambios de esquema en bases de datos de publicaciones](publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e06cd-121">For more information, see [Make Schema Changes on Publication Databases](publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
 <span data-ttu-id="e06cd-122">Para sincronizar una suscripción de inserción, vea [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="e06cd-122">To synchronize a push subscription, see [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="e06cd-123">Para sincronizar una suscripción de extracción, vea [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="e06cd-123">To synchronize a pull subscription, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="e06cd-124">Para establecer programaciones de sincronización, vea [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="e06cd-124">To set synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="e06cd-125">**Para ver y solucionar los conflictos de sincronización**</span><span class="sxs-lookup"><span data-stu-id="e06cd-125">**To view and resolve synchronization conflicts**</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="e06cd-126">: [Ver y resolver conflictos de datos para publicaciones de mezcla &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span><span class="sxs-lookup"><span data-stu-id="e06cd-126">: [View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="e06cd-127">: [Ver conflictos de datos para publicaciones transaccionales &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="e06cd-127">: [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span></span>  
  
## <a name="executing-code-during-synchronization"></a><span data-ttu-id="e06cd-128">Ejecutar código durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="e06cd-128">Executing Code During Synchronization</span></span>  
 <span data-ttu-id="e06cd-129">La replicación admite dos métodos de ejecución de código durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="e06cd-129">Replication supports two methods of executing code during synchronization</span></span>  
  
-   <span data-ttu-id="e06cd-130">La ejecución de script a petición se admite en la replicación transaccional y la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="e06cd-130">On demand script execution is supported for transactional replication and merge replication.</span></span> <span data-ttu-id="e06cd-131">Con la ejecución de script a petición es posible especificar un script SQL para ejecutarlo durante la sincronización.</span><span class="sxs-lookup"><span data-stu-id="e06cd-131">Using on demand script execution you can specify a SQL script to run during synchronization.</span></span> <span data-ttu-id="e06cd-132">Este script se copia en el suscriptor y se ejecuta mediante **sqlcmd** al inicio del proceso de sincronización.</span><span class="sxs-lookup"><span data-stu-id="e06cd-132">The script is copied to the Subscriber and executed using **sqlcmd** at the beginning of the synchronization process.</span></span> <span data-ttu-id="e06cd-133">El script no tiene acceso a los cambios replicados cuando se aplican al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e06cd-133">The script does not have access to the replicated changes as they are applied to the Subscriber.</span></span> <span data-ttu-id="e06cd-134">Para más información, vea [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md) (Ejecutar scripts durante la sincronización (programación de la replicación con Transact-SQL)).</span><span class="sxs-lookup"><span data-stu-id="e06cd-134">For more information, see [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span></span>  
  
-   <span data-ttu-id="e06cd-135">La replicación de mezcla admite controladores de lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="e06cd-135">Business logic handlers are supported for merge replication.</span></span> <span data-ttu-id="e06cd-136">El uso de un marco de trabajo de controladores de lógica de negocios le permite escribir un ensamblado de código administrado al que se llama durante el proceso de sincronización de mezcla.</span><span class="sxs-lookup"><span data-stu-id="e06cd-136">Using the business logic handler framework you can write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="e06cd-137">El ensamblado incluye lógica de negocios que puede responder a varias condiciones durante la sincronización: cambios de datos, conflictos y errores.</span><span class="sxs-lookup"><span data-stu-id="e06cd-137">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="e06cd-138">Para obtener más información, consulte [Ejecutar lógica de negocios durante la sincronización de mezcla](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="e06cd-138">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e06cd-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e06cd-139">See Also</span></span>  
 [<span data-ttu-id="e06cd-140">Detectar y solucionar conflictos de replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="e06cd-140">Detect and Resolve Merge Replication Conflicts</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
