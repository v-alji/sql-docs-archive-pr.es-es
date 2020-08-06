---
title: MSSQL_ENG021286 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592c788b563046e5949217c94006de2d4755f049
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745208"
---
# <a name="mssql_eng021286"></a><span data-ttu-id="68e2e-102">MSSQL_ENG021286</span><span class="sxs-lookup"><span data-stu-id="68e2e-102">MSSQL_ENG021286</span></span>
    
## <a name="message-details"></a><span data-ttu-id="68e2e-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="68e2e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68e2e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="68e2e-104">Product Name</span></span>|<span data-ttu-id="68e2e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="68e2e-105">SQL Server</span></span>|  
|<span data-ttu-id="68e2e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="68e2e-106">Event ID</span></span>|<span data-ttu-id="68e2e-107">21286</span><span class="sxs-lookup"><span data-stu-id="68e2e-107">21286</span></span>|  
|<span data-ttu-id="68e2e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="68e2e-108">Event Source</span></span>|<span data-ttu-id="68e2e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="68e2e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="68e2e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="68e2e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="68e2e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="68e2e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="68e2e-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="68e2e-112">Message Text</span></span>|<span data-ttu-id="68e2e-113">La tabla de conflictos '%1!' no existe.</span><span class="sxs-lookup"><span data-stu-id="68e2e-113">Conflict table '%s' does not exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68e2e-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="68e2e-114">Explanation</span></span>  
 <span data-ttu-id="68e2e-115">Este error se produce si la tabla de conflictos de un artículo mencionado en [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) no existe realmente.</span><span class="sxs-lookup"><span data-stu-id="68e2e-115">This error is raised if the conflict table for an article listed in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) does not actually exist.</span></span> <span data-ttu-id="68e2e-116">El error se puede producir al intentar agregar o quitar una columna de una tabla publicada para la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="68e2e-116">The error can occur when you attempt to add a column to or drop a column from a table published for merge replication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68e2e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="68e2e-117">User Action</span></span>  
 <span data-ttu-id="68e2e-118">Ejecute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) en la base de datos donde falta la tabla en conflicto para comprobar que no existen problemas de coherencia de datos.</span><span class="sxs-lookup"><span data-stu-id="68e2e-118">Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database with the missing conflict table to verify there are no data consistency issues.</span></span>  
  
 <span data-ttu-id="68e2e-119">Si la tabla de conflictos falta en un suscriptor, quite y vuelva a crear la suscripción.</span><span class="sxs-lookup"><span data-stu-id="68e2e-119">If the conflict table is missing on a Subscriber, drop the subscription and recreate it.</span></span> <span data-ttu-id="68e2e-120">Si la tabla de conflictos falta en un publicador, quite todas las suscripciones, quite la publicación y vuelva a crear la publicación y todas las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="68e2e-120">If the conflict table is missing on a Publisher, drop all subscriptions, drop the publication, and then recreate the publication and all subscriptions.</span></span> <span data-ttu-id="68e2e-121">Para obtener más información sobre la creación de publicación, vea [Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md) y [Suscribirse a publicaciones](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="68e2e-121">For more information, see [Publish Data and Database Objects](publish/publish-data-and-database-objects.md) and [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68e2e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68e2e-122">See Also</span></span>  
 [<span data-ttu-id="68e2e-123">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="68e2e-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
