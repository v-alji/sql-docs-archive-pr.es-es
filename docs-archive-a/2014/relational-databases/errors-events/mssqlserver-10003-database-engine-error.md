---
title: MSSQLSERVER_10003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10003 (Database Engine error)
ms.assetid: 9e2cb199-f077-4d88-8117-1b7550afc696
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ea44fc9591602bfc8279924e10a1803d0d5a87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663010"
---
# <a name="mssqlserver_10003"></a><span data-ttu-id="9c4dc-102">MSSQLSERVER_10003</span><span class="sxs-lookup"><span data-stu-id="9c4dc-102">MSSQLSERVER_10003</span></span>
    
## <a name="details"></a><span data-ttu-id="9c4dc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9c4dc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c4dc-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="9c4dc-104">Product Name</span></span>|<span data-ttu-id="9c4dc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c4dc-105">SQL Server</span></span>|  
|<span data-ttu-id="9c4dc-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="9c4dc-106">Event ID</span></span>|<span data-ttu-id="9c4dc-107">10003</span><span class="sxs-lookup"><span data-stu-id="9c4dc-107">10003</span></span>|  
|<span data-ttu-id="9c4dc-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="9c4dc-108">Event Source</span></span>|<span data-ttu-id="9c4dc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9c4dc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9c4dc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9c4dc-110">Component</span></span>|<span data-ttu-id="9c4dc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9c4dc-111">SQLEngine</span></span>|  
|<span data-ttu-id="9c4dc-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9c4dc-112">Symbolic Name</span></span>|<span data-ttu-id="9c4dc-113">HR_E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9c4dc-113">HR_E_OUTOFMEMORY</span></span>|  
|<span data-ttu-id="9c4dc-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9c4dc-114">Message Text</span></span>|<span data-ttu-id="9c4dc-115">Memoria insuficiente para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-115">The provider ran out of memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9c4dc-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="9c4dc-116">Explanation</span></span>  
 <span data-ttu-id="9c4dc-117">La escasa memoria del sistema ha hecho que el proveedor OLE DB se ejecute con memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-117">Low system memory has caused the OLE DB provider to run out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c4dc-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9c4dc-118">User Action</span></span>  
 <span data-ttu-id="9c4dc-119">Reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c4dc-119">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9c4dc-120">Si esto apenas sirve, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-120">If that does not help, restart the computer.</span></span> <span data-ttu-id="9c4dc-121">Si el problema persiste, recopile eventos de seguimiento de OLE DB mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] y proporcione estos datos al soporte técnico del producto para el proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-121">If the problem persists, collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4dc-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c4dc-122">See Also</span></span>  
 <span data-ttu-id="9c4dc-123">[Plantillas y permisos de SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="9c4dc-123">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="9c4dc-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="9c4dc-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
