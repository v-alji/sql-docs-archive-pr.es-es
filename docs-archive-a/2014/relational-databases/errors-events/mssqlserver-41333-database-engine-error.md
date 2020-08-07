---
title: MSSQLSERVER_41333 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41333 (Database Engine error)
ms.assetid: c3c3ae9a-1e4c-4de6-ba72-2f393375b053
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ba3cfc9627b4b44c3c9eccc620fb16bb94b861b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746305"
---
# <a name="mssqlserver_41333"></a><span data-ttu-id="45d10-102">MSSQLSERVER_41333</span><span class="sxs-lookup"><span data-stu-id="45d10-102">MSSQLSERVER_41333</span></span>
    
## <a name="details"></a><span data-ttu-id="45d10-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="45d10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45d10-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="45d10-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="45d10-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="45d10-105">Event ID</span></span>|<span data-ttu-id="45d10-106">41333</span><span class="sxs-lookup"><span data-stu-id="45d10-106">41333</span></span>|  
|<span data-ttu-id="45d10-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="45d10-107">Event Source</span></span>|<span data-ttu-id="45d10-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="45d10-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="45d10-109">Componente</span><span class="sxs-lookup"><span data-stu-id="45d10-109">Component</span></span>|<span data-ttu-id="45d10-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="45d10-110">SQLEngine</span></span>|  
|<span data-ttu-id="45d10-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="45d10-111">Symbolic Name</span></span>|<span data-ttu-id="45d10-112">CROSS_CONTAINER_ISOLATION_FAILURE</span><span class="sxs-lookup"><span data-stu-id="45d10-112">CROSS_CONTAINER_ISOLATION_FAILURE</span></span>|  
|<span data-ttu-id="45d10-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="45d10-113">Message Text</span></span>|<span data-ttu-id="45d10-114">Las siguientes transacciones deben acceder a tablas optimizadas para memoria y a procedimientos almacenados compilados de forma nativa en el aislamiento de instantáneas: transacciones RepeatableRead, transacciones Serializable y transacciones que accedan a las tablas que no estén optimizadas para memoria en aislamiento RepeatableRead o Serializable.</span><span class="sxs-lookup"><span data-stu-id="45d10-114">The following transactions must access memory optimized tables and natively compiled stored procedures under snapshot isolation: RepeatableRead transactions, Serializable transactions, and transactions that access tables that are not memory optimized in RepeatableRead or Serializable isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="45d10-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="45d10-115">Explanation</span></span>  
 <span data-ttu-id="45d10-116">Hay restricciones respecto al usuario de los niveles de aislamiento mayores entre las transacciones basadas en disco y las transacciones XTP.</span><span class="sxs-lookup"><span data-stu-id="45d10-116">There are restrictions against the user of the higher isolation levels between disk based transactions and XTP transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45d10-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="45d10-117">User Action</span></span>  
 <span data-ttu-id="45d10-118">No intente operaciones de aislamiento alto nivel de las tablas optimizadas en memoria (y procedimientos compilados de forma nativa) y las tablas basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="45d10-118">Don't attempt high level isolation operations on memory-optimized tables (and natively compiled procedures) and disk based tables.</span></span>  
  
 <span data-ttu-id="45d10-119">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="45d10-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d10-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45d10-120">See Also</span></span>  
 [<span data-ttu-id="45d10-121">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="45d10-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
