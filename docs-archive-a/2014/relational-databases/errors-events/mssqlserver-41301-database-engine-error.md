---
title: MSSQLSERVER_41301 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41301 (Database Engine error)
ms.assetid: c6127e1e-2846-4ee9-bc42-2d896ea9730e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d4fa78b334f32033f96df002aeaf039994b396cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674142"
---
# <a name="mssqlserver_41301"></a><span data-ttu-id="77e00-102">MSSQLSERVER_41301</span><span class="sxs-lookup"><span data-stu-id="77e00-102">MSSQLSERVER_41301</span></span>
    
## <a name="details"></a><span data-ttu-id="77e00-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="77e00-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77e00-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="77e00-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="77e00-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="77e00-105">Event ID</span></span>|<span data-ttu-id="77e00-106">41301</span><span class="sxs-lookup"><span data-stu-id="77e00-106">41301</span></span>|  
|<span data-ttu-id="77e00-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="77e00-107">Event Source</span></span>|<span data-ttu-id="77e00-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="77e00-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="77e00-109">Componente</span><span class="sxs-lookup"><span data-stu-id="77e00-109">Component</span></span>|<span data-ttu-id="77e00-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="77e00-110">SQLEngine</span></span>|  
|<span data-ttu-id="77e00-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="77e00-111">Symbolic Name</span></span>|<span data-ttu-id="77e00-112">COMMIT_DEPENDENCY_FAILURE</span><span class="sxs-lookup"><span data-stu-id="77e00-112">COMMIT_DEPENDENCY_FAILURE</span></span>|  
|<span data-ttu-id="77e00-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="77e00-113">Message Text</span></span>|<span data-ttu-id="77e00-114">Una transacción anterior a la transacción actual realizada en una dependencia se ha anulado y la transacción actual ya no puede confirmarse.</span><span class="sxs-lookup"><span data-stu-id="77e00-114">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77e00-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="77e00-115">Explanation</span></span>  
 <span data-ttu-id="77e00-116">La transacción encontró un error de dependencia y ahora está condenada.</span><span class="sxs-lookup"><span data-stu-id="77e00-116">The transaction encountered a dependency failure, and is now doomed.</span></span>  
  
 <span data-ttu-id="77e00-117">Este error también puede producirse si hay demasiadas transacciones dependientes.</span><span class="sxs-lookup"><span data-stu-id="77e00-117">This error can also be caused by too many dependent transactions.</span></span> <span data-ttu-id="77e00-118">Las transacciones de escritura pueden tener un número limitado de transacciones dependientes.</span><span class="sxs-lookup"><span data-stu-id="77e00-118">Any write transaction can have a limited number of dependent transactions.</span></span> <span data-ttu-id="77e00-119">Por ejemplo, este error puede producirse si muchas transacciones de lectura intentan depender de la transacción de actualización.</span><span class="sxs-lookup"><span data-stu-id="77e00-119">For example, this error can occur if too many read transactions try to take a dependency on the update transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77e00-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="77e00-120">User Action</span></span>  
 <span data-ttu-id="77e00-121">No haga ningún trabajo en la transacción.</span><span class="sxs-lookup"><span data-stu-id="77e00-121">Don't do any work on the transaction.</span></span> <span data-ttu-id="77e00-122">Llame a ROLLBACK TRAN para revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="77e00-122">Call ROLLBACK TRAN to roll back the transaction.</span></span> <span data-ttu-id="77e00-123">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="77e00-123">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e00-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77e00-124">See Also</span></span>  
 [<span data-ttu-id="77e00-125">Habilitar y deshabilitar grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77e00-125">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md)  
  
  
