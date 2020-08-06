---
title: 'Lección 3: Sincronización de la suscripción con la publicación de combinación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 49008384-2c55-4080-a890-9bceb40e4d6d
author: rothja
ms.author: jroth
ms.openlocfilehash: bf0256c69d69d1236869fa83285bf4dbf5c462da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749229"
---
# <a name="lesson-3-synchronizing-the-subscription-to-the-merge-publication"></a><span data-ttu-id="75fd9-102">Lección 3: Sincronizar la suscripción con la publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="75fd9-102">Lesson 3: Synchronizing the Subscription to the Merge Publication</span></span>
  <span data-ttu-id="75fd9-103">En esta lección iniciará el Agente de mezcla para inicializar la suscripción con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75fd9-103">In this lesson, you will start the Merge Agent to initialize the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="75fd9-104">También utilizará este procedimiento para sincronizar con el publicador.</span><span class="sxs-lookup"><span data-stu-id="75fd9-104">You also use this procedure to synchronize with the Publisher.</span></span> <span data-ttu-id="75fd9-105">Esta lección requiere que haya completado la lección anterior, [Lección 2: Crear una suscripción a la publicación de mezcla](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="75fd9-105">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
### <a name="to-start-synchronization-and-initialize-the-subscription"></a><span data-ttu-id="75fd9-106">Para iniciar la sincronización e inicializar la suscripción</span><span class="sxs-lookup"><span data-stu-id="75fd9-106">To start synchronization and initialize the subscription</span></span>  
  
1.  <span data-ttu-id="75fd9-107">Conéctese al suscriptor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="75fd9-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="75fd9-108">En la carpeta **Suscripciones locales** , haga clic con el botón derecho en la suscripción de la base de datos **SalesOrdersReplica** y, después, haga clic en **Ver estado de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="75fd9-108">In the **Local Subscriptions** folder, right-click the subscription in the **SalesOrdersReplica** database, and then click **View Synchronization Status**.</span></span>  
  
3.  <span data-ttu-id="75fd9-109">Haga clic en **Inicio** para inicializar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="75fd9-109">Click **Start** to initialize the subscription.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="75fd9-110">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="75fd9-110">Next Steps</span></span>  
 <span data-ttu-id="75fd9-111">Ha ejecutado correctamente el Agente de mezcla para iniciar la sincronización e inicializar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="75fd9-111">You have successfully run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="75fd9-112">También puede insertar, actualizar o eliminar datos en las tablas **SalesOrderHeader** o **SalesOrderDetail** en el publicador o en el suscriptor, repetir este procedimiento cuando exista conectividad de red para sincronizar datos entre el publicador y el suscriptor y, después, consultar las tablas **SalesOrderHeader** o **SalesOrderDetail** en el otro servidor para ver los cambios replicados.</span><span class="sxs-lookup"><span data-stu-id="75fd9-112">You can also insert, update, or delete data in the **SalesOrderHeader** or **SalesOrderDetail** tables at the Publisher or Subscriber, repeat this procedure when network connectivity is available to synchronize data between the Publisher and the Subscriber, and then query the **SalesOrderHeader** or **SalesOrderDetail** tables at the other server to view the replicated changes.</span></span>  
  
 <span data-ttu-id="75fd9-113">Con esto finaliza el tutorial Replicar datos con clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="75fd9-113">This completes the Replicating Data with Mobile Clients tutorial.</span></span> <span data-ttu-id="75fd9-114">Para obtener un tutorial similar que usa la replicación transaccional, consulte [Tutorial: Replicar datos entre servidores conectados de forma continua](tutorial-replicating-data-between-continuously-connected-servers.md).</span><span class="sxs-lookup"><span data-stu-id="75fd9-114">For a similar tutorial that uses transactional replication, see [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75fd9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75fd9-115">See Also</span></span>  
 <span data-ttu-id="75fd9-116">[Inicializar una suscripción con una instantánea](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="75fd9-116">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="75fd9-117">[Sincronizar datos](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="75fd9-117">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="75fd9-118">Sincronizar una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="75fd9-118">Synchronize a Pull Subscription</span></span>](synchronize-a-pull-subscription.md)  
  
  
