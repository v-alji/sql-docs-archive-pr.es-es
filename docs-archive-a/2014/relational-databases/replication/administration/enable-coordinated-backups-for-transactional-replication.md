---
title: Habilitar copias de seguridad coordinadas para la replicación transaccional (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, backup and restore
- sp_replicationdboption
- sync with backup [SQL Server replication]
- coordinated backups [SQL Server replication]
- backups [SQL Server replication], transactional replication
ms.assetid: 73a914ba-8b2d-4f4d-ac1b-db9bac676a30
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77405cd968fa917c3ccc799eb7d168782443eee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750782"
---
# <a name="enable-coordinated-backups-for-transactional-replication-replication-transact-sql-programming"></a><span data-ttu-id="4cc9c-102">Habilitar copias de seguridad coordinadas para la replicación transaccional (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4cc9c-102">Enable Coordinated Backups for Transactional Replication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="4cc9c-103">Al habilitar una base de datos para la replicación transaccional, puede especificar que se tenga que realizar una copia de seguridad de todas las transacciones antes de ser entregadas a la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-103">When enabling a database for transactional replication, you can specify that all transactions must be backed up before being delivered to the distribution database.</span></span> <span data-ttu-id="4cc9c-104">También puede habilitar la copia de seguridad coordinada en la base de datos de distribución para que el registro de transacciones de la base de datos de publicación no se trunque hasta que se haya realizado una copia de seguridad de las transacciones que se han propagado al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-104">You can also enable coordinated backup on the distribution database so that the transaction log for the publication database is not truncated until transactions that have been propagated to the Distributor have been backed up.</span></span> <span data-ttu-id="4cc9c-105">Para más información, consulte [Estrategias para hacer copias de seguridad y restaurar replicación de instantáneas o replicación transaccional](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4cc9c-105">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-database-published-with-transactional-replication"></a><span data-ttu-id="4cc9c-106">Para habilitar las copias de seguridad coordinadas de una base de datos publicada con replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="4cc9c-106">To enable coordinated backups for a database published with transactional replication</span></span>  
  
1.  <span data-ttu-id="4cc9c-107">En el publicador, use la función [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) para devolver la propiedad **IsSyncWithBackup** de la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-107">At the Publisher, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the publication database.</span></span> <span data-ttu-id="4cc9c-108">Si la función devuelve **1**, las copias de seguridad coordinadas ya están habilitadas para la base de datos publicada.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-108">If the function returns **1**, coordinated backups are already enabled for the published database.</span></span>  
  
2.  <span data-ttu-id="4cc9c-109">Si la función del paso 1 devuelve **0**, ejecute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) en la base de datos de publicación del publicador.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-109">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="4cc9c-110">Especifique un valor de **sync with backup** para **\@optname** y **true** para **\@value**.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-110">Specify a value of **sync with backup** for **\@optname**, and **true** for **\@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4cc9c-111">Si cambia la opción **sync with backup** a **false**, el punto de la truncación de la base de datos de publicación estará actualizado después de que el Agente de registro del LOG se ejecute o después de un intervalo si el Agente de registro del LOG está ejecutando permanentemente.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-111">If you change the **sync with backup** option to **false**, the truncation point of the publication database will be updated after the Log Reader Agent runs, or after an interval if the Log Reader Agent is running continuously.</span></span> <span data-ttu-id="4cc9c-112">El parámetro del agente **-MessageInterval**, que tiene un valor predeterminado de 30 segundos, controla el intervalo máximo.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-112">The maximum interval is controlled by the **-MessageInterval** agent parameter (which has a default of 30 seconds).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-distribution-database"></a><span data-ttu-id="4cc9c-113">Para habilitar las copias de seguridad coordinadas para una base de datos de distribución</span><span class="sxs-lookup"><span data-stu-id="4cc9c-113">To enable coordinated backups for a distribution database</span></span>  
  
1.  <span data-ttu-id="4cc9c-114">En el distribuidor, use la función [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) para devolver la propiedad **IsSyncWithBackup** de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-114">At the Distributor, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the distribution database.</span></span> <span data-ttu-id="4cc9c-115">Si la función devuelve **1**, las copias de seguridad coordinadas ya están habilitadas para la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-115">If the function returns **1**, coordinated backups are already enabled for the distribution database.</span></span>  
  
2.  <span data-ttu-id="4cc9c-116">Si la función del paso 1 devuelve **0**, ejecute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) en la base de datos de distribución del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-116">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="4cc9c-117">Especifique un valor de **Sync with backup** para \*\* \@ optname\*\* y **true** para \*\* \@ Value\*\*.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-117">Specify a value of **sync with backup** for **\@optname** and **true** for **\@value**.</span></span>  
  
### <a name="to-disable-coordinated-backups"></a><span data-ttu-id="4cc9c-118">Para deshabilitar las copias de seguridad coordinadas</span><span class="sxs-lookup"><span data-stu-id="4cc9c-118">To disable coordinated backups</span></span>  
  
1.  <span data-ttu-id="4cc9c-119">En el publicador de la base de datos de publicación o en el distribuidor de la base de datos de distribución, ejecute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4cc9c-119">At either the Publisher on the publication database or at the Distributor on the distribution database, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span></span> <span data-ttu-id="4cc9c-120">Especifique un valor de **sync with backup** para **\@optname** y **false** para **\@value**.</span><span class="sxs-lookup"><span data-stu-id="4cc9c-120">Specify a value of **sync with backup** for **\@optname** and **false** for **\@value**.</span></span>  
  
  
