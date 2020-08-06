---
title: Administrar memoria para OLTP en memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d82f21fa-6be1-4723-a72e-f2526fafd1b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90f9b638697d59a0a573a9a31c0a5faade23e870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748892"
---
# <a name="managing-memory-for-in-memory-oltp"></a><span data-ttu-id="56b05-102">Administrar memoria para OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="56b05-102">Managing Memory for In-Memory OLTP</span></span>
  <span data-ttu-id="56b05-103">Las tablas con optimización para memoria requieren que exista memoria suficiente para mantener todas las filas e índices en memoria.</span><span class="sxs-lookup"><span data-stu-id="56b05-103">Memory-optimized tables require that sufficient memory exist to keep all of the rows and indexes in memory.</span></span> <span data-ttu-id="56b05-104">Dado que la memoria es un recurso finito, es importante que conozca y administre el uso que hace de la memoria en su sistema.</span><span class="sxs-lookup"><span data-stu-id="56b05-104">Because memory is a finite resource, it is important that you understand and manage memory usage on your system.</span></span> <span data-ttu-id="56b05-105">Los temas de esta sección se ocupan de situaciones de uso y administración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="56b05-105">The topics in this section cover common memory use and management scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56b05-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="56b05-106">In this section</span></span>  
  
|<span data-ttu-id="56b05-107">Sección</span><span class="sxs-lookup"><span data-stu-id="56b05-107">Section</span></span>|<span data-ttu-id="56b05-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="56b05-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56b05-109">Estimar los requisitos de memoria para las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="56b05-109">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)|<span data-ttu-id="56b05-110">Calcular las necesidades de memoria de una tabla.</span><span class="sxs-lookup"><span data-stu-id="56b05-110">Estimate a table's memory needs.</span></span>|  
|[<span data-ttu-id="56b05-111">Enlazar una base de datos con tablas con optimización para memoria a un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="56b05-111">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)|<span data-ttu-id="56b05-112">Tutorial paso a paso para enlazar una base de datos con un grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="56b05-112">Step by step walkthrough to bind a database with a resource pool.</span></span>|  
|[<span data-ttu-id="56b05-113">Supervisar y solucionar problemas de uso de memoria</span><span class="sxs-lookup"><span data-stu-id="56b05-113">Monitor and Troubleshoot Memory Usage</span></span>](../relational-databases/in-memory-oltp/monitor-and-troubleshoot-memory-usage.md)|<span data-ttu-id="56b05-114">Herramientas que puede usar para supervisar el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="56b05-114">Tools you can use to monitor your memory usage.</span></span> <span data-ttu-id="56b05-115">También cubre la solución de problemas si el uso de memoria se dispara.</span><span class="sxs-lookup"><span data-stu-id="56b05-115">Also covers troubleshooting if memory usage gets too high.</span></span>|  
|[<span data-ttu-id="56b05-116">Resolver problemas de memoria insuficiente</span><span class="sxs-lookup"><span data-stu-id="56b05-116">Resolve Out Of Memory Issues</span></span>](../relational-databases/in-memory-oltp/resolve-out-of-memory-issues.md)|<span data-ttu-id="56b05-117">Pasos para recuperarse de una situación de OOM (quedarse sin memoria).</span><span class="sxs-lookup"><span data-stu-id="56b05-117">Steps to recover from an OOM (Out of Memory) situation.</span></span>|  
|[<span data-ttu-id="56b05-118">Restaurar una base de datos y enlazarla a un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="56b05-118">Restore a Database and Bind it to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md)|<span data-ttu-id="56b05-119">Pasos para restaurar una base de datos de [!INCLUDE[hek_2](../includes/hek-2-md.md)] y para enlazarla a un grupo de recursos de servidor con nombre.</span><span class="sxs-lookup"><span data-stu-id="56b05-119">Steps to restore an [!INCLUDE[hek_2](../includes/hek-2-md.md)] database and bind it to a named resource pool.</span></span>|  
|[<span data-ttu-id="56b05-120">Recolección de elementos no utilizados de OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="56b05-120">In-Memory OLTP Garbage Collection</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-garbage-collection.md)|<span data-ttu-id="56b05-121">Descripción de cómo funciona la recolección de elementos no utilizados en filas eliminadas.</span><span class="sxs-lookup"><span data-stu-id="56b05-121">Understand how garbage collection operates on deleted rows.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56b05-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56b05-122">See Also</span></span>  
 [<span data-ttu-id="56b05-123">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="56b05-123">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
