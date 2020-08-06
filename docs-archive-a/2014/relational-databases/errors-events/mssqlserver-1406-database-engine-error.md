---
title: MSSQLSERVER_1406 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adaa0084b875f720c477189e0e8e085af124f4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747015"
---
# <a name="mssqlserver_1406"></a><span data-ttu-id="d79d3-102">MSSQLSERVER_1406</span><span class="sxs-lookup"><span data-stu-id="d79d3-102">MSSQLSERVER_1406</span></span>
    
## <a name="details"></a><span data-ttu-id="d79d3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d79d3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d79d3-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d79d3-104">Product Name</span></span>|<span data-ttu-id="d79d3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d79d3-105">SQL Server</span></span>|  
|<span data-ttu-id="d79d3-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d79d3-106">Event ID</span></span>|<span data-ttu-id="d79d3-107">1406</span><span class="sxs-lookup"><span data-stu-id="d79d3-107">1406</span></span>|  
|<span data-ttu-id="d79d3-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d79d3-108">Event Source</span></span>|<span data-ttu-id="d79d3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d79d3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d79d3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d79d3-110">Component</span></span>|<span data-ttu-id="d79d3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d79d3-111">SQLEngine</span></span>|  
|<span data-ttu-id="d79d3-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d79d3-112">Symbolic Name</span></span>|<span data-ttu-id="d79d3-113">DBM_BADSTATEFORFORCESERVICE</span><span class="sxs-lookup"><span data-stu-id="d79d3-113">DBM_BADSTATEFORFORCESERVICE</span></span>|  
|<span data-ttu-id="d79d3-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d79d3-114">Message Text</span></span>|<span data-ttu-id="d79d3-115">No se puede forzar el servicio de forma segura.</span><span class="sxs-lookup"><span data-stu-id="d79d3-115">Unable to force service safely.</span></span> <span data-ttu-id="d79d3-116">Quite el reflejo de la base de datos y recupere la base de datos "%.\*ls" para obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="d79d3-116">Remove database mirroring and recover database "%.\*ls" to gain access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d79d3-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="d79d3-117">Explanation</span></span>  
 <span data-ttu-id="d79d3-118">El [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] no puede forzar el servicio porque el estado de creación de reflejo no puede garantizar que el proceso de forzar el servicio funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="d79d3-118">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot force service because the mirroring state cannot guarantee that the force service process would work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d79d3-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d79d3-119">User Action</span></span>  
 <span data-ttu-id="d79d3-120">Quite el reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d79d3-120">Remove database mirroring.</span></span> <span data-ttu-id="d79d3-121">Después, puede recuperar la base de datos reflejada para obtener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="d79d3-121">You can then recover the mirror database to gain access to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79d3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d79d3-122">See Also</span></span>  
 <span data-ttu-id="d79d3-123">[Forzar el servicio en una sesión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="d79d3-123">[Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 [<span data-ttu-id="d79d3-124">Quitar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d79d3-124">Removing Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
