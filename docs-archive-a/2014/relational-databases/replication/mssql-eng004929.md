---
title: MSSQL_ENG004929 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG004929 error
ms.assetid: 1d9b1d88-1fbf-4089-b392-687d3b0220ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b202b28eabe1feb1ed180bda0d58d2e84c7d10d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662832"
---
# <a name="mssql_eng004929"></a><span data-ttu-id="516a8-102">MSSQL_ENG004929</span><span class="sxs-lookup"><span data-stu-id="516a8-102">MSSQL_ENG004929</span></span>
    
## <a name="message-details"></a><span data-ttu-id="516a8-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="516a8-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="516a8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="516a8-104">Product Name</span></span>|<span data-ttu-id="516a8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="516a8-105">SQL Server</span></span>|  
|<span data-ttu-id="516a8-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="516a8-106">Event ID</span></span>|<span data-ttu-id="516a8-107">4929</span><span class="sxs-lookup"><span data-stu-id="516a8-107">4929</span></span>|  
|<span data-ttu-id="516a8-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="516a8-108">Event Source</span></span>|<span data-ttu-id="516a8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="516a8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="516a8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="516a8-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="516a8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="516a8-111">Symbolic Name</span></span>||  
|<span data-ttu-id="516a8-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="516a8-112">Message Text</span></span>|<span data-ttu-id="516a8-113">No se puede modificar el %1! '%2!' porque se está publicando para replicación.</span><span class="sxs-lookup"><span data-stu-id="516a8-113">Cannot alter the %S_MSG '%.\*ls' because it is being published for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="516a8-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="516a8-114">Explanation</span></span>  
 <span data-ttu-id="516a8-115">Normalmente este error se produce si intenta quitar la restricción de clave principal en una tabla que está publicada para replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="516a8-115">This error typically occurs if you attempt to drop the primary key constraint on a table that is published for transactional replication.</span></span> <span data-ttu-id="516a8-116">La replicación transaccional requiere una clave principal para cada tabla publicada; por tanto, no se puede quitar la restricción.</span><span class="sxs-lookup"><span data-stu-id="516a8-116">Transactional replication requires a primary key for each published table; therefore the constraint cannot be dropped.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="516a8-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="516a8-117">User Action</span></span>  
 <span data-ttu-id="516a8-118">Para quitar la restricción, primero quite el artículo asociado con la tabla.</span><span class="sxs-lookup"><span data-stu-id="516a8-118">To drop the constraint, first drop the article associated with the table.</span></span> <span data-ttu-id="516a8-119">Para más información, vea [Agregar y quitar artículos de publicaciones existentes](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="516a8-119">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span> <span data-ttu-id="516a8-120">Si se produce este error en una base de datos que no está replicada, ejecute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para asegurarse de que los objetos de la base de datos no están marcados como replicados.</span><span class="sxs-lookup"><span data-stu-id="516a8-120">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="516a8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="516a8-121">See Also</span></span>  
 [<span data-ttu-id="516a8-122">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="516a8-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
