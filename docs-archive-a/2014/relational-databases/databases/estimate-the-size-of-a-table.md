---
title: Calcular el tamaño de una tabla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- pages [SQL Server], space
- space [SQL Server], tables
- row size [SQL Server]
- size [SQL Server], tables
- column size [SQL Server]
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- disk space [SQL Server], tables
- space allocation [SQL Server], table size
- designing databases [SQL Server], estimating size
- reserved free rows per page [SQL Server]
- calculating table size
ms.assetid: 15c17c92-616f-402e-894b-907a296efe5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a16d439d3b2bc59479866b7bb36295ec4fc8950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748121"
---
# <a name="estimate-the-size-of-a-table"></a><span data-ttu-id="3a780-102">Calcular el tamaño de una tabla</span><span class="sxs-lookup"><span data-stu-id="3a780-102">Estimate the Size of a Table</span></span>
  <span data-ttu-id="3a780-103">Los siguientes pasos pueden utilizarse para calcular el espacio necesario para almacenar datos en una tabla:</span><span class="sxs-lookup"><span data-stu-id="3a780-103">You can use the following steps to estimate the amount of space required to store data in a table:</span></span>  
  
1.  <span data-ttu-id="3a780-104">Calcular el espacio necesario para el montón o para el índice agrupado siguiendo las instrucciones indicadas en [Estimar el tamaño de un montón](estimate-the-size-of-a-heap.md) o en [Estimar el tamaño de un índice agrupado](estimate-the-size-of-a-clustered-index.md).</span><span class="sxs-lookup"><span data-stu-id="3a780-104">Calculate the space required for the heap or clustered index following the instructions in [Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) or [Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md).</span></span>  
  
2.  <span data-ttu-id="3a780-105">Calcular el espacio necesario para cada índice no agrupado mediante las instrucciones que se detallan en [Estimar el tamaño de un índice no agrupado](estimate-the-size-of-a-nonclustered-index.md).</span><span class="sxs-lookup"><span data-stu-id="3a780-105">For each nonclustered index, calculate the space required for it by following the instructions in [Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md).</span></span>  
  
3.  <span data-ttu-id="3a780-106">Sumar los valores calculados en los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="3a780-106">Add the values calculated in steps 1 and 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a780-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a780-107">See Also</span></span>  
 <span data-ttu-id="3a780-108">[Estimar el tamaño de una base de datos](estimate-the-size-of-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="3a780-108">[Estimate the Size of a Database](estimate-the-size-of-a-database.md) </span></span>  
 <span data-ttu-id="3a780-109">[Estimar el tamaño de un montón](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="3a780-109">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 <span data-ttu-id="3a780-110">[Estimar el tamaño de un índice agrupado](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="3a780-110">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 [<span data-ttu-id="3a780-111">Estimar el tamaño de un índice no clúster</span><span class="sxs-lookup"><span data-stu-id="3a780-111">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)  
  
  
