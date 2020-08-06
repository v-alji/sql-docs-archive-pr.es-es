---
title: Rendimiento (categoría de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Performance event category
- Performance event category [SQL Server]
- event classes [SQL Server], Performance event category
ms.assetid: 708f3585-d8be-4980-bbff-672d7c59397e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b0c076a4132298797313ecbf0874d9d2d4e453cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674808"
---
# <a name="performance-event-category"></a><span data-ttu-id="20a39-102">Rendimiento (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-102">Performance Event Category</span></span>
  <span data-ttu-id="20a39-103">Use la categoría de eventos **Performance** para supervisar las clases de eventos **Showplan** y las clases de eventos que se producen al ejecutar operadores de lenguaje de manipulación de datos (DML) de SQL.</span><span class="sxs-lookup"><span data-stu-id="20a39-103">Use the **Performance** event category to monitor **Showplan** event classes and event classes that are produced from the execution of SQL data manipulation language (DML) operators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20a39-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20a39-104">In This Section</span></span>  
  
|<span data-ttu-id="20a39-105">Tema</span><span class="sxs-lookup"><span data-stu-id="20a39-105">Topic</span></span>|<span data-ttu-id="20a39-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="20a39-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="20a39-107">Auto Stats (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-107">Auto Stats Event Class</span></span>](auto-stats-event-class.md)|<span data-ttu-id="20a39-108">Indica que se ha producido una actualización automática de las estadísticas de índices y columnas.</span><span class="sxs-lookup"><span data-stu-id="20a39-108">Indicates that an automatic updating of index and column statistics has occurred.</span></span>|  
|[<span data-ttu-id="20a39-109">Degree of Parallelism &#40;7.0 Insert&#41; clase de eventos</span><span class="sxs-lookup"><span data-stu-id="20a39-109">Degree of Parallelism &#40;7.0 Insert&#41; Event Class</span></span>](degree-of-parallelism-7-0-insert-event-class.md)|<span data-ttu-id="20a39-110">Indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha ejecutado una instrucción SELECT, INSERT, UPDATE o DELETE utilizando un plan serie o paralelo.</span><span class="sxs-lookup"><span data-stu-id="20a39-110">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a SELECT, INSERT, UPDATE, or DELETE statement using either a serial or parallel plan.</span></span> <span data-ttu-id="20a39-111">Se informa también del número de CPUs utilizadas para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="20a39-111">The number of CPUs used to perform the operation is also reported.</span></span>|  
|[<span data-ttu-id="20a39-112">Performance Statistics (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-112">Performance Statistics Event Class</span></span>](performance-statistics-event-class.md)|<span data-ttu-id="20a39-113">Supervisa el rendimiento de las consultas que se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="20a39-113">Monitors performance of the queries that are being executed.</span></span>|  
|[<span data-ttu-id="20a39-114">Showplan All (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-114">Showplan All Event Class</span></span>](showplan-all-event-class.md)|<span data-ttu-id="20a39-115">Identifica los operadores de **Showplan** de una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="20a39-115">Identifies **Showplan** operators within a SQL statement.</span></span>|  
|[<span data-ttu-id="20a39-116">Showplan All for Query Compile (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-116">Showplan All for Query Compile Event Class</span></span>](showplan-all-for-query-compile-event-class.md)|<span data-ttu-id="20a39-117">Muestra los datos de tiempo de compilación de los operadores de **Showplan** .</span><span class="sxs-lookup"><span data-stu-id="20a39-117">Displays compile time data for **Showplan** operators.</span></span>|  
|[<span data-ttu-id="20a39-118">Showplan Statistics Profile (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-118">Showplan Statistics Profile Event Class</span></span>](showplan-statistics-profile-event-class.md)|<span data-ttu-id="20a39-119">Muestra el costo estimado de una consulta.</span><span class="sxs-lookup"><span data-stu-id="20a39-119">Displays the estimated cost of a query.</span></span>|  
|[<span data-ttu-id="20a39-120">Showplan XML (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-120">Showplan XML Event Class</span></span>](showplan-xml-event-class.md)|<span data-ttu-id="20a39-121">Identifica los operadores de **Showplan** en una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="20a39-121">Identifies the **Showplan** operators in a SQL statement.</span></span> <span data-ttu-id="20a39-122">La clase de eventos almacena cada evento como un documento XML bien definido.</span><span class="sxs-lookup"><span data-stu-id="20a39-122">The event class stores each event as a well defined XML document.</span></span>|  
|[<span data-ttu-id="20a39-123">Showplan XML For Query Compile (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-123">Showplan XML for Query Compile Event Class</span></span>](showplan-xml-for-query-compile-event-class.md)|<span data-ttu-id="20a39-124">Muestra los datos de tiempo de compilación de los operadores de **Showplan** en formato XML.</span><span class="sxs-lookup"><span data-stu-id="20a39-124">Displays compile time data for **Showplan** operators in XML format.</span></span>|  
|[<span data-ttu-id="20a39-125">Showplan XML Statistics Profile (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-125">Showplan XML Statistics Profile Event Class</span></span>](showplan-xml-statistics-profile-event-class.md)|<span data-ttu-id="20a39-126">Identifica los operadores de **Showplan** asociados a una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="20a39-126">Identifies the **Showplan** operators associated with a SQL statement.</span></span> <span data-ttu-id="20a39-127">La salida es un documento XML.</span><span class="sxs-lookup"><span data-stu-id="20a39-127">The output is an XML document.</span></span>|  
|[<span data-ttu-id="20a39-128">SQL:FullTextQuery Event Class</span><span class="sxs-lookup"><span data-stu-id="20a39-128">SQL:FullTextQuery Event Class</span></span>](sql-fulltextquery-event-class.md)|<span data-ttu-id="20a39-129">Indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha ejecutado una consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="20a39-129">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a full-text query.</span></span>|  
|[<span data-ttu-id="20a39-130">Plan Guide Successful (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-130">Plan Guide Successful Event Class</span></span>](plan-guide-successful-event-class.md)|<span data-ttu-id="20a39-131">Indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generó correctamente un plan de ejecución para una consulta o lote que contenía una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="20a39-131">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] successfully produced an execution plan for a query or batch that contained a plan guide.</span></span>|  
|[<span data-ttu-id="20a39-132">Plan Guide Unsuccessful (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="20a39-132">Plan Guide Unsuccessful Event Class</span></span>](plan-guide-unsuccessful-event-class.md)|<span data-ttu-id="20a39-133">Indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no pudo generar un plan de ejecución para una consulta o lote que contenía una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="20a39-133">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not produce an execution plan for a query or batch that contained a plan guide.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20a39-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20a39-134">See Also</span></span>  
 [<span data-ttu-id="20a39-135">Eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="20a39-135">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
