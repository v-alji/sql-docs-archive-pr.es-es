---
title: Contadores de rendimiento de XTP (OLTP en memoria) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: fe3cbaf4-65f4-44c5-acc6-7b735cda0c5d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4363a526ada3694e92d18cac0d7abe8a26f6a92f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745243"
---
# <a name="xtp-in-memory-oltp-performance-counters"></a><span data-ttu-id="beb1a-102">Contadores de rendimiento de XTP (OLTP en memoria)</span><span class="sxs-lookup"><span data-stu-id="beb1a-102">XTP (In-Memory OLTP) Performance Counters</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="beb1a-103">ofrece objetos y contadores que el Monitor de rendimiento puede usar para supervisar la actividad de OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="beb1a-103">provides objects and counters that can be used by Performance Monitor to monitor In-Memory OLTP activity.</span></span>  
  
##  <a name="xtp-in-memory-oltp-performance-objects"></a><a name="SQLServerPOs"></a><span data-ttu-id="beb1a-104">Objetos de rendimiento de XTP (OLTP en memoria)</span><span class="sxs-lookup"><span data-stu-id="beb1a-104">XTP (In-Memory OLTP) Performance Objects</span></span>  
 <span data-ttu-id="beb1a-105">En la tabla siguiente se describen los objetos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="beb1a-105">The following table describes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span>  
  
|<span data-ttu-id="beb1a-106">Objeto de rendimiento</span><span class="sxs-lookup"><span data-stu-id="beb1a-106">Performance object</span></span>|<span data-ttu-id="beb1a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="beb1a-107">Description</span></span>|  
|------------------------|-----------------|  
|[<span data-ttu-id="beb1a-108">Cursores XTP</span><span class="sxs-lookup"><span data-stu-id="beb1a-108">XTP Cursors</span></span>](../cursors.md)|<span data-ttu-id="beb1a-109">El objeto de rendimiento Cursores XTP contiene contadores relacionados con los cursores internos del motor de XTP.</span><span class="sxs-lookup"><span data-stu-id="beb1a-109">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="beb1a-110">Los cursores son los bloques de creación de bajo nivel que el motor de XTP utiliza para procesar consultas de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="beb1a-110">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="beb1a-111">Por tanto, el usuario no tiene normalmente control directo sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="beb1a-111">As such, you do not typically have direct control over them.</span></span>|  
|[<span data-ttu-id="beb1a-112">Recolección de elementos no utilizados de XTP</span><span class="sxs-lookup"><span data-stu-id="beb1a-112">XTP Garbage Collection</span></span>](sql-server-xtp-garbage-collection.md)|<span data-ttu-id="beb1a-113">El objeto de rendimiento Recolección de elementos no utilizados de XTP contiene contadores relacionados con el recolector de elementos no utilizados del motor de XTP.</span><span class="sxs-lookup"><span data-stu-id="beb1a-113">The XTP Garbage Collection performance object contains counters related to the XTP engine's garbage collector.</span></span>|  
|[<span data-ttu-id="beb1a-114">Procesador fantasma de XTP</span><span class="sxs-lookup"><span data-stu-id="beb1a-114">XTP Phantom Processor</span></span>](sql-server-xtp-phantom-processor.md)|<span data-ttu-id="beb1a-115">El objeto de rendimiento Procesador fantasma de XTP contiene contadores relacionados con el subsistema de procesamiento fantasma del motor de XTP.</span><span class="sxs-lookup"><span data-stu-id="beb1a-115">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="beb1a-116">Este componente es responsable de detectar filas fantasma en transacciones que se ejecutan en el nivel de aislamiento SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="beb1a-116">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>|  
|[<span data-ttu-id="beb1a-117">XTP Storage</span><span class="sxs-lookup"><span data-stu-id="beb1a-117">XTP Storage</span></span>](sql-server-xtp-storage.md)|<span data-ttu-id="beb1a-118">El objeto de rendimiento XTP Storage contiene contadores relacionados con el almacenamiento de XTP en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beb1a-118">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="beb1a-119">Registro de transacciones XTP</span><span class="sxs-lookup"><span data-stu-id="beb1a-119">XTP Transaction Log</span></span>](sql-server-xtp-transaction-log.md)|<span data-ttu-id="beb1a-120">El objeto de rendimiento Registro de transacciones XTP contiene contadores relacionados con el registro de transacciones XTP en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beb1a-120">The XTP Transaction Log performance object contains counters related to XTP transaction logging in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="beb1a-121">Transacciones XTP</span><span class="sxs-lookup"><span data-stu-id="beb1a-121">XTP Transactions</span></span>](sql-server-xtp-transactions.md)|<span data-ttu-id="beb1a-122">El objeto de rendimiento Transacciones XTP contiene contadores relacionados con las transacciones del motor de XTP en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beb1a-122">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
  
