---
title: MSSQL_REPL020011 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL020011 error
ms.assetid: f72072d7-bbb6-48ad-ac88-afa74aeb4d58
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646f25740ebb007f8d04a89690d3b712781efcc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748062"
---
# <a name="mssql_repl020011"></a><span data-ttu-id="89966-102">MSSQL_REPL020011</span><span class="sxs-lookup"><span data-stu-id="89966-102">MSSQL_REPL020011</span></span>
    
## <a name="message-details"></a><span data-ttu-id="89966-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="89966-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89966-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="89966-104">Product Name</span></span>|<span data-ttu-id="89966-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="89966-105">SQL Server</span></span>|  
|<span data-ttu-id="89966-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="89966-106">Event ID</span></span>|<span data-ttu-id="89966-107">20011</span><span class="sxs-lookup"><span data-stu-id="89966-107">20011</span></span>|  
|<span data-ttu-id="89966-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="89966-108">Event Source</span></span>|<span data-ttu-id="89966-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="89966-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="89966-110">Componente</span><span class="sxs-lookup"><span data-stu-id="89966-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="89966-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="89966-111">Symbolic Name</span></span>||  
|<span data-ttu-id="89966-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="89966-112">Message Text</span></span>|<span data-ttu-id="89966-113">El proceso no pudo ejecutar '%1' en '%2'.</span><span class="sxs-lookup"><span data-stu-id="89966-113">The process could not execute '%1' on '%2'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="89966-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="89966-114">Explanation</span></span>  
 <span data-ttu-id="89966-115">Este error se puede generar en una serie de circunstancias durante el procesamiento de la replicación transaccional, por ejemplo, cuando el Agente de registro del LOG ejecuta **sp_replcmds** (el proceso no pudo ejecutar "sp_replcmds" en \<ServerName>) o **sp_repldone** (el proceso no pudo ejecutar "sp_repldone" en \<ServerName>).</span><span class="sxs-lookup"><span data-stu-id="89966-115">This error can be raised in a number of circumstances during transactional replication processing, such as when the Log Reader Agent executes **sp_replcmds** (The process could not execute 'sp_replcmds' on \<ServerName>) or **sp_repldone** (The process could not execute 'sp_repldone' on \<ServerName>).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89966-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="89966-116">User Action</span></span>  
 <span data-ttu-id="89966-117">Si este error se genera en una base de datos que acaba de restaurar de una copia de seguridad, asegúrese de que ha seguido los pasos descritos en la documentación referente a copias de seguridad y restauración, incluida la ejecución de **sp_replrestart** si fuese necesario.</span><span class="sxs-lookup"><span data-stu-id="89966-117">If this error is raised in a database that you have just restored from a backup, ensure you have followed the steps outlined in the backup and restore documentation, including executing **sp_replrestart** if appropriate.</span></span> <span data-ttu-id="89966-118">Para más información, consulte [Estrategias para hacer copias de seguridad y restaurar replicación de instantáneas o replicación transaccional](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="89966-118">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="89966-119">Se trata de un error de procesamiento interno y si se genera en circunstancias diferentes a una restauración, normalmente indica que la replicación se debe quitar y volver a configurar.</span><span class="sxs-lookup"><span data-stu-id="89966-119">This error is an internal processing error and if it is raised in circumstances other than a restore, it typically indicates that replication must be removed and reconfigured.</span></span> <span data-ttu-id="89966-120">Si no puede quitar la replicación, póngase en contacto con el soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="89966-120">If you cannot remove replication, contact customer support for assistance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89966-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89966-121">See Also</span></span>  
 <span data-ttu-id="89966-122">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="89966-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="89966-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89966-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span></span>  
 [<span data-ttu-id="89966-124">sp_repldone &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89966-124">sp_repldone &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql)  
  
  
