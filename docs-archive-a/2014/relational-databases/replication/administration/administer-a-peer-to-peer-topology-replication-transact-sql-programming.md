---
title: Administrar una topología punto a punto (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, peer-to-peer replication
ms.assetid: 4d0fa941-f9ea-4a14-aed9-34df593fc6f2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a73af1c1f3a7196d87f77681ee9d62a3ef248a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670961"
---
# <a name="administer-a-peer-to-peer-topology-replication-transact-sql-programming"></a><span data-ttu-id="5df42-102">Administrar una topología punto a punto (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5df42-102">Administer a Peer-to-Peer Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="5df42-103">Administrar una topología punto a punto es parecido a administrar una topología de replicación transaccional típica, pero hay varios aspectos que requieren una consideración especial.</span><span class="sxs-lookup"><span data-stu-id="5df42-103">Administering a peer-to-peer topology is similar to administering a typical transactional replication topology, but there are a number of areas with special considerations.</span></span> <span data-ttu-id="5df42-104">La diferencia principal cuando se administra una topología punto a punto es que algunos cambios requieren que el sistema esté *detenido*.</span><span class="sxs-lookup"><span data-stu-id="5df42-104">The principal difference in administering a peer-to-peer topology is that some changes require the system to be *quiesced*.</span></span> <span data-ttu-id="5df42-105">Para poner el sistema en modo inactivo, hay que detener la actividad de las tablas publicadas en todos los nodos y asegurarse de que cada nodo haya recibido todos los cambios de los demás nodos.</span><span class="sxs-lookup"><span data-stu-id="5df42-105">Quiescing a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="5df42-106">Para más información, vea [Poner en modo inactivo una topología de replicación &#40;programación de la replicación con Transact-SQL&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="5df42-106">For more information, see [Quiesce a Replication Topology &#40;Replication Transact-SQL Programming&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5df42-107">En una topología punto a punto, el distribuidor no puede utilizar una versión anterior de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que la de un suscriptor de extracción.</span><span class="sxs-lookup"><span data-stu-id="5df42-107">In a peer-to-peer topology, the distributor cannot be using an earlier version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] than a pull subscriber.</span></span>  
  
### <a name="to-add-an-article-to-an-existing-configuration"></a><span data-ttu-id="5df42-108">Agregar un artículo a una configuración existente</span><span class="sxs-lookup"><span data-stu-id="5df42-108">To add an article to an existing configuration</span></span>  
  
1.  <span data-ttu-id="5df42-109">Detenga el sistema.</span><span class="sxs-lookup"><span data-stu-id="5df42-109">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="5df42-110">Detenga el Agente de distribución en cada nodo de la topología.</span><span class="sxs-lookup"><span data-stu-id="5df42-110">Stop the Distribution Agent at each node in the topology.</span></span> <span data-ttu-id="5df42-111">Para más información, vea [Conceptos de los ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md) o [Iniciar y detener un Agente de replicación &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="5df42-111">For more information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="5df42-112">Ejecute la instrucción CREATE TABLE para agregar la nueva tabla en cada nodo de la topología.</span><span class="sxs-lookup"><span data-stu-id="5df42-112">Execute the CREATE TABLE statement to add the new table at each node in the topology.</span></span>  
  
4.  <span data-ttu-id="5df42-113">Realice una copia masiva de los datos de la nueva tabla manualmente en todos los nodos mediante la utilidad [bcp](../../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5df42-113">Bulk copy the data for the new table manually at all nodes by using the [bcp utility](../../../tools/bcp-utility.md).</span></span>  
  
5.  <span data-ttu-id="5df42-114">Ejecute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) para crear el nuevo artículo en cada nodo en la topología.</span><span class="sxs-lookup"><span data-stu-id="5df42-114">Execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) to create the new article at each node in the topology.</span></span> <span data-ttu-id="5df42-115">Para más información, consulte [Define an Article](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="5df42-115">For more information, see [Define an Article](../publish/define-an-article.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5df42-116">Una vez ejecutado [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) , la replicación agrega automáticamente el artículo a las suscripciones de la topología.</span><span class="sxs-lookup"><span data-stu-id="5df42-116">After [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) is executed, replication automatically adds the article to the subscriptions in the topology.</span></span>  
  
6.  <span data-ttu-id="5df42-117">Reinicie los agentes de distribución en cada nodo de la topología.</span><span class="sxs-lookup"><span data-stu-id="5df42-117">Restart the Distribution Agents at each node in the topology.</span></span>  
  
### <a name="to-make-schema-changes-to-a-publication-database"></a><span data-ttu-id="5df42-118">Para realizar cambios del esquema en una base de datos de publicación</span><span class="sxs-lookup"><span data-stu-id="5df42-118">To make schema changes to a publication database</span></span>  
  
1.  <span data-ttu-id="5df42-119">Detenga el sistema.</span><span class="sxs-lookup"><span data-stu-id="5df42-119">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="5df42-120">Ejecute las instrucciones de lenguaje de definición de datos (DDL) para modificar el esquema de tablas publicadas.</span><span class="sxs-lookup"><span data-stu-id="5df42-120">Execute the data definition language (DDL) statements to modify the schema of published tables.</span></span> <span data-ttu-id="5df42-121">Para más información sobre los cambios de esquema admitidos, vea [Realizar cambios de esquema en bases de datos de publicaciones](../publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5df42-121">For more information about supported schema changes, see [Make Schema Changes on Publication Databases](../publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
3.  <span data-ttu-id="5df42-122">Antes de reanudar la actividad en tablas publicadas, detenga el sistema de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5df42-122">Before you resume activity on published tables, quiesce the system again.</span></span> <span data-ttu-id="5df42-123">De esta manera se garantiza que los cambios del esquema se han recibido en todos los nodos antes de que se haya replicado cualquier nuevo cambio de los datos.</span><span class="sxs-lookup"><span data-stu-id="5df42-123">This ensures that schema changes have been received by all nodes before any new data changes are replicated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5df42-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5df42-124">Example</span></span>  
 <span data-ttu-id="5df42-125">En el siguiente ejemplo se muestra cómo agregar un nuevo artículo de tabla a una topología de replicación punto a punto existente con dos nodos.</span><span class="sxs-lookup"><span data-stu-id="5df42-125">The following example demonstrates how to add a new table article to an existing peer-to-peer replication topology that has two nodes.</span></span>  
  
 [!code-sql[HowTo#sp_addp2particle_createtables](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createtables)]  
  
 [!code-sql[HowTo#sp_addp2particle_cmdline](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_cmdline)]  
  
 [!code-sql[HowTo#sp_addp2particle_createarticle](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createarticle)]  
  
## <a name="see-also"></a><span data-ttu-id="5df42-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5df42-126">See Also</span></span>  
 <span data-ttu-id="5df42-127">[Preguntas más frecuentes para administradores de replicación](frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="5df42-127">[Replication Administration FAQ](frequently-asked-questions-for-replication-administrators.md) </span></span>  
 <span data-ttu-id="5df42-128">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="5df42-128">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="5df42-129">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="5df42-129">Peer-to-Peer Transactional Replication</span></span>](../transactional/peer-to-peer-transactional-replication.md)  
  
  
