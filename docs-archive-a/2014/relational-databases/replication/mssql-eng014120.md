---
title: MSSQL_ENG014120 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014120 error
ms.assetid: 6b169a3b-30da-4981-b998-b52d61811572
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7f3484d9344a203ca8c44fee6b79605163ea069
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661938"
---
# <a name="mssql_eng014120"></a><span data-ttu-id="e6010-102">MSSQL_ENG014120</span><span class="sxs-lookup"><span data-stu-id="e6010-102">MSSQL_ENG014120</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e6010-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="e6010-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6010-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e6010-104">Product Name</span></span>|<span data-ttu-id="e6010-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6010-105">SQL Server</span></span>|  
|<span data-ttu-id="e6010-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e6010-106">Event ID</span></span>|<span data-ttu-id="e6010-107">14120</span><span class="sxs-lookup"><span data-stu-id="e6010-107">14120</span></span>|  
|<span data-ttu-id="e6010-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e6010-108">Event Source</span></span>|<span data-ttu-id="e6010-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e6010-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e6010-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e6010-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e6010-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e6010-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e6010-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e6010-112">Message Text</span></span>|<span data-ttu-id="e6010-113">No se pudo quitar la base de datos de distribución '%s'.</span><span class="sxs-lookup"><span data-stu-id="e6010-113">Could not drop the distribution database '%s'.</span></span> <span data-ttu-id="e6010-114">Esta base de datos está asociada a un publicador.</span><span class="sxs-lookup"><span data-stu-id="e6010-114">This distributor database is associated with a Publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6010-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e6010-115">Explanation</span></span>  
 <span data-ttu-id="e6010-116">La base de datos de distribución almacena metadatos y datos del historial de todos los tipos de replicación y transacciones para la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="e6010-116">The distribution database stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="e6010-117">Este error se produce si intenta quitar una base de datos de distribución que está asociada a uno o más publicadores.</span><span class="sxs-lookup"><span data-stu-id="e6010-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6010-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e6010-118">User Action</span></span>  
 <span data-ttu-id="e6010-119">Para quitar una base de datos de distribución, primero debe quitar la asociación entre el distribuidor y el publicador.</span><span class="sxs-lookup"><span data-stu-id="e6010-119">To drop a distribution database you must first drop the association between the Distributor and the Publisher.</span></span> <span data-ttu-id="e6010-120">Para obtener más información, vea [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6010-120">For more information, see [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6010-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6010-121">See Also</span></span>  
 <span data-ttu-id="e6010-122">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="e6010-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="e6010-123">Configurar distribución</span><span class="sxs-lookup"><span data-stu-id="e6010-123">Configure Distribution</span></span>](configure-distribution.md)  
  
  
