---
title: MSSQLSERVER_41307 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41307 (Database Engine error)
ms.assetid: 56f56410-b07d-4379-b01c-702c95761070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 98407a65d5529fd73bccc638df11167131bd9f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747008"
---
# <a name="mssqlserver_41307"></a><span data-ttu-id="ded04-102">MSSQLSERVER_41307</span><span class="sxs-lookup"><span data-stu-id="ded04-102">MSSQLSERVER_41307</span></span>
    
## <a name="details"></a><span data-ttu-id="ded04-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ded04-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ded04-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ded04-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="ded04-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ded04-105">Event ID</span></span>|<span data-ttu-id="ded04-106">41307</span><span class="sxs-lookup"><span data-stu-id="ded04-106">41307</span></span>|  
|<span data-ttu-id="ded04-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ded04-107">Event Source</span></span>|<span data-ttu-id="ded04-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ded04-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ded04-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ded04-109">Component</span></span>|<span data-ttu-id="ded04-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ded04-110">SQLEngine</span></span>|  
|<span data-ttu-id="ded04-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ded04-111">Symbolic Name</span></span>|<span data-ttu-id="ded04-112">HK_HEKATON_ROW_LIMIT</span><span class="sxs-lookup"><span data-stu-id="ded04-112">HK_HEKATON_ROW_LIMIT</span></span>|  
|<span data-ttu-id="ded04-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ded04-113">Message Text</span></span>|<span data-ttu-id="ded04-114">Se ha superado el límite de tamaño de fila de *number* bytes para las tablas optimizadas en memoria.</span><span class="sxs-lookup"><span data-stu-id="ded04-114">The row size limit of *number* bytes for memory optimized tables has been exceeded.</span></span> <span data-ttu-id="ded04-115">Simplifique la definición de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ded04-115">Please simplify the table definition.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ded04-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ded04-116">Explanation</span></span>  
 <span data-ttu-id="ded04-117">El límite de tamaño de fila para las tablas optimizadas en memoria es de 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="ded04-117">The row size limit for memory optimized tables is 8,060 bytes.</span></span> <span data-ttu-id="ded04-118">Para obtener más información, vea [Tamaño de tabla y fila de las tablas con optimización para memoria](../in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ded04-118">For more information, see [Table and Row Size in Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md).</span></span> <span data-ttu-id="ded04-119">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="ded04-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded04-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ded04-120">See Also</span></span>  
 [<span data-ttu-id="ded04-121">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="ded04-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
