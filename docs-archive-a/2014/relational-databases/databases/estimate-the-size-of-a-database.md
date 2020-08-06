---
title: Estimar el tamaño de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], database size
- calculating database size
- increasing database size
- database size [SQL Server], estimating
- predicting database size
- size [SQL Server], databases
- estimating database size
- designing databases [SQL Server], estimating size
ms.assetid: 5b240161-eba4-44b0-946c-61a8fc00fc8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3a390c4ade2c2dc08f67d2d1461955516e866c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672093"
---
# <a name="estimate-the-size-of-a-database"></a><span data-ttu-id="b486c-102">Estimar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="b486c-102">Estimate the Size of a Database</span></span>
  <span data-ttu-id="b486c-103">Cuando diseña una base de datos, puede que necesite realizar una estimación del tamaño que tendrá la base de datos cuando esté llena.</span><span class="sxs-lookup"><span data-stu-id="b486c-103">When you design a database, you may have to estimate how large the database will be when filled with data.</span></span> <span data-ttu-id="b486c-104">Esta estimación puede ayudarle a determinar la configuración de hardware que necesitará para realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b486c-104">Estimating the size of the database can help you determine the hardware configuration you will require to do the following:</span></span>  
  
-   <span data-ttu-id="b486c-105">Conseguir el rendimiento que necesitan las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b486c-105">Achieve the performance required by your applications.</span></span>  
  
-   <span data-ttu-id="b486c-106">Asegurar la cantidad física adecuada de espacio en disco necesario para almacenar los datos y los índices.</span><span class="sxs-lookup"><span data-stu-id="b486c-106">Guarantee the appropriate physical amount of disk space required to store the data and indexes.</span></span>  
  
 <span data-ttu-id="b486c-107">Asimismo, la estimación del tamaño de la base de datos puede ayudarle a determinar si el diseño de su base de datos necesita reajustes.</span><span class="sxs-lookup"><span data-stu-id="b486c-107">Estimating the size of a database can also help you determine whether the database design needs refining.</span></span> <span data-ttu-id="b486c-108">Por ejemplo, puede determinar que el tamaño estimado de la base de datos es demasiado grande para una implementación en su organización, y que se necesita un mayor grado de normalización.</span><span class="sxs-lookup"><span data-stu-id="b486c-108">For example, you may determine that the estimated size of the database is too large to implement in your organization and that more normalization is required.</span></span> <span data-ttu-id="b486c-109">Por el contrario, el tamaño estimado puede inferior al esperado,</span><span class="sxs-lookup"><span data-stu-id="b486c-109">Conversely, the estimated size may be smaller than expected.</span></span> <span data-ttu-id="b486c-110">con lo que podrá reducir la normalización de la base de datos para mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="b486c-110">This would allow you to denormalize the database to improve query performance.</span></span>  
  
 <span data-ttu-id="b486c-111">Para realizar una estimación del tamaño de una base de datos, efectúe una estimación del tamaño de cada tabla por separado y sume los valores obtenidos.</span><span class="sxs-lookup"><span data-stu-id="b486c-111">To estimate the size of a database, estimate the size of each table individually and then add the values obtained.</span></span> <span data-ttu-id="b486c-112">El tamaño de una tabla depende de si tiene índices y, si los tiene, del tipo de índices.</span><span class="sxs-lookup"><span data-stu-id="b486c-112">The size of a table depends on whether the table has indexes and, if they do, what type of indexes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b486c-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b486c-113">In This Section</span></span>  
  
|<span data-ttu-id="b486c-114">Tema</span><span class="sxs-lookup"><span data-stu-id="b486c-114">Topic</span></span>|<span data-ttu-id="b486c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b486c-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b486c-116">Calcular el tamaño de una tabla</span><span class="sxs-lookup"><span data-stu-id="b486c-116">Estimate the Size of a Table</span></span>](estimate-the-size-of-a-table.md)|<span data-ttu-id="b486c-117">Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en una tabla y en los índices asociados.</span><span class="sxs-lookup"><span data-stu-id="b486c-117">Defines the steps and calculations needed to estimate the amount of space required to store the data in a table and associated indexes.</span></span>|  
|[<span data-ttu-id="b486c-118">Estimar el tamaño de un montón</span><span class="sxs-lookup"><span data-stu-id="b486c-118">Estimate the Size of a Heap</span></span>](estimate-the-size-of-a-heap.md)|<span data-ttu-id="b486c-119">Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en un montón.</span><span class="sxs-lookup"><span data-stu-id="b486c-119">Defines the steps and calculations needed to estimate the amount of space required to store the data in a heap.</span></span> <span data-ttu-id="b486c-120">Un montón es una tabla que no contiene un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="b486c-120">A heap is a table that does not have a clustered index.</span></span>|  
|[<span data-ttu-id="b486c-121">Estimar el tamaño de un índice clúster</span><span class="sxs-lookup"><span data-stu-id="b486c-121">Estimate the Size of a Clustered Index</span></span>](estimate-the-size-of-a-clustered-index.md)|<span data-ttu-id="b486c-122">Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="b486c-122">Defines the steps and calculations needed to estimate the amount of space required to store the data in a clustered index.</span></span>|  
|[<span data-ttu-id="b486c-123">Estimar el tamaño de un índice no clúster</span><span class="sxs-lookup"><span data-stu-id="b486c-123">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)|<span data-ttu-id="b486c-124">Define los pasos y cálculos necesarios para realizar una estimación del espacio que se necesita para almacenar los datos en un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="b486c-124">Defines the steps and calculations needed to estimate the amount of space required to store the data in a nonclustered index.</span></span>|  
  
  
