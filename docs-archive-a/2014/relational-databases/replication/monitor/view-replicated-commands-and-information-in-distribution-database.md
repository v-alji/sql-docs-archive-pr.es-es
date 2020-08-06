---
title: Ver comandos replicados y otra información en la base de datos de distribución (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_browsereplcmds
- transactional replication, monitoring
- distribution databases [SQL Server replication], viewing replicated commands
- viewing replicated commands
ms.assetid: 9c20acec-8fab-4483-b9c1-dfe3768f85dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fb5850277d685f2ecf6471fa4bf9814579b2843e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750705"
---
# <a name="view-replicated-commands-and-other-information-in-the-distribution-database-replication-transact-sql-programming"></a><span data-ttu-id="211f3-102">Ver comandos replicados y otra información en la base de datos de distribución (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="211f3-102">View Replicated Commands and Other Information in the Distribution Database (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="211f3-103">Al utilizar la replicación transaccional, los comandos de transacción están almacenados en la base de datos de distribución hasta que el Agente de distribución los propaga a todos los suscriptores o un Agente de distribución del suscriptor extrae los cambios.</span><span class="sxs-lookup"><span data-stu-id="211f3-103">When using transactional replication, transaction commands are stored in the distribution database until the Distribution Agent propagates them to all Subscribers or a Distribution Agent at the Subscriber pulls the changes.</span></span> <span data-ttu-id="211f3-104">Estos comandos pendientes en la base de datos de distribución se pueden ver utilizando mediante programación los procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="211f3-104">These pending commands in the distribution database can be viewed programmatically using replication stored procedures.</span></span> <span data-ttu-id="211f3-105">Para obtener más información, consulte [Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) (Procedimientos almacenados de replicación [Transact-SQL]).</span><span class="sxs-lookup"><span data-stu-id="211f3-105">For more information, see [Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-from-all-transactional-publications-in-the-distribution-database"></a><span data-ttu-id="211f3-106">Para ver los comandos replicados de todas las publicaciones transaccionales en la base de datos de distribución</span><span class="sxs-lookup"><span data-stu-id="211f3-106">To view replicated commands from all transactional publications in the distribution database</span></span>  
  
1.  <span data-ttu-id="211f3-107">En cualquier base de datos de distribución, ejecute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="211f3-107">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-in-the-distribution-database-from-a-specific-article-or-from-a-specific-database-published-using-transactional-replication"></a><span data-ttu-id="211f3-108">Para ver los comandos replicados en la base de datos de distribución de un artículo concreto o de una base de datos concreta publicada utilizando replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="211f3-108">To view replicated commands in the distribution database from a specific article or from a specific database published using transactional replication</span></span>  
  
1.  <span data-ttu-id="211f3-109">(Opcional) En la base de datos de publicación del publicador, ejecute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="211f3-109">(Optional) At the Publisher on the publication database, execute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span></span> <span data-ttu-id="211f3-110">Especifique la \*\* \@ publicación\*\* y el \*\* \@ artículo\*\*.</span><span class="sxs-lookup"><span data-stu-id="211f3-110">Specify **\@publication** and **\@article**.</span></span> <span data-ttu-id="211f3-111">Anote el valor de **article** del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="211f3-111">Note the value of **article id** in the result set.</span></span>  
  
2.  <span data-ttu-id="211f3-112">En cualquier base de datos de distribución, ejecute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="211f3-112">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span> <span data-ttu-id="211f3-113">Opta Especifique el ID. del artículo del paso 2 para \*\* \@ article_id\*\*.</span><span class="sxs-lookup"><span data-stu-id="211f3-113">(Optional) Specify the article ID from step 2 for **\@article_id**.</span></span> <span data-ttu-id="211f3-114">Opta Especifique el identificador de la base de datos de publicación para \*\* \@ publisher_database_id\*\*, que se puede obtener de la columna **database_id** de la vista de catálogo [Sys. Databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="211f3-114">(Optional) Specify the ID of the publication database for **\@publisher_database_id**, which can be obtained from the **database_id** column in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211f3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="211f3-115">See Also</span></span>  
 [<span data-ttu-id="211f3-116">Supervisar la replicación mediante programación</span><span class="sxs-lookup"><span data-stu-id="211f3-116">Programmatically Monitor Replication</span></span>](../monitoring-replication.md)  
  
  
