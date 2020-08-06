---
title: Limpieza de metadatos de mezcla (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- metadata [SQL Server replication]
- sp_mergemetadataretentioncleanup
ms.assetid: 9b88baea-b7c6-4e5d-88f9-93d6a0ff0368
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5a2306db72fd3f0098e18ff058796a5498eafcac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748083"
---
# <a name="clean-up-merge-metadata-replication-transact-sql-programming"></a><span data-ttu-id="0caa4-102">Limpiar metadatos de mezcla (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0caa4-102">Clean Up Merge Metadata (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="0caa4-103">El Agente de mezcla limpia periódicamente los metadatos de replicación de mezcla según la configuración de retención de la publicación.</span><span class="sxs-lookup"><span data-stu-id="0caa4-103">Merge replication metadata is cleaned up periodically by the Merge Agent based on the retention setting for the publication.</span></span> <span data-ttu-id="0caa4-104">Esto tiene lugar en el publicador y en el suscriptor de las tablas del sistema [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql)y [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) .</span><span class="sxs-lookup"><span data-stu-id="0caa4-104">This occurs at the Publisher and Subscriber in the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql), and [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) system tables.</span></span> <span data-ttu-id="0caa4-105">También puede limpiar mediante programación los datos de estas tablas utilizando procedimientos almacenados de la replicación.</span><span class="sxs-lookup"><span data-stu-id="0caa4-105">You can also programmatically clean up the data in these tables using replication stored procedures.</span></span>  
  
### <a name="to-manually-clean-up-merge-metadata"></a><span data-ttu-id="0caa4-106">Para limpiar manualmente los metadatos de mezcla</span><span class="sxs-lookup"><span data-stu-id="0caa4-106">To manually clean up merge metadata</span></span>  
  
1.  <span data-ttu-id="0caa4-107">En el publicador de la base de datos de publicación, ejecute [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0caa4-107">At the Publisher on the publication database, execute [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span></span>  
  
2.  <span data-ttu-id="0caa4-108">Opta Tenga en cuenta el número de filas que se han quitado en el paso 1 de las tablas del sistema [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql)y [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) , devueltas respectivamente en los **@num_genhistory_rows** parámetros de **@num_contents_rows** salida, y **@num_tombstone_rows** .</span><span class="sxs-lookup"><span data-stu-id="0caa4-108">(Optional) Note the number of rows removed in step 1 from the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), and [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) system tables, returned respectively in the **@num_genhistory_rows**, **@num_contents_rows**, and **@num_tombstone_rows** output parameters.</span></span>  
  
3.  <span data-ttu-id="0caa4-109">Repita los pasos 1 y 2 en el suscriptor para limpiar los metadatos en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="0caa4-109">Repeat steps 1 and 2 at the Subscriber to clean up metadata on the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0caa4-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0caa4-110">See Also</span></span>  
 [<span data-ttu-id="0caa4-111">Desactivación y expiración de la suscripción</span><span class="sxs-lookup"><span data-stu-id="0caa4-111">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
