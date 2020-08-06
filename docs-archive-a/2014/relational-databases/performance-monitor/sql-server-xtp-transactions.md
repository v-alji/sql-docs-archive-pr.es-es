---
title: Transacciones XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 443d67e4-1c7f-41d7-b18d-2d657f58c22a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 75fa8bc9a673d9e0e018b8578a35af2e46b5044c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745239"
---
# <a name="xtp-transactions"></a><span data-ttu-id="02ad6-102">Transacciones XTP</span><span class="sxs-lookup"><span data-stu-id="02ad6-102">XTP Transactions</span></span>
  <span data-ttu-id="02ad6-103">El objeto de rendimiento Transacciones XTP contiene contadores relacionados con las transacciones del motor de XTP en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02ad6-103">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="02ad6-104">En esta tabla se describen los contadores de **Transacciones XTP** .</span><span class="sxs-lookup"><span data-stu-id="02ad6-104">This table describes the **XTP Transactions** counters.</span></span>  
  
|<span data-ttu-id="02ad6-105">Contador</span><span class="sxs-lookup"><span data-stu-id="02ad6-105">Counter</span></span>|<span data-ttu-id="02ad6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="02ad6-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02ad6-107">**Anulaciones en cascada/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-107">**Cascading aborts/sec**</span></span>|<span data-ttu-id="02ad6-108">Número de transacciones revertidas debido a una reversión de dependencia de confirmación (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-108">The number of transactions that rolled back to due a commit dependency rollback (on average), per second.</span></span>|  
|<span data-ttu-id="02ad6-109">**Dependencias de confirmación realizadas/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-109">**Commit dependencies taken/sec**</span></span>|<span data-ttu-id="02ad6-110">Número de dependencias de confirmación realizadas por transacciones (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-110">The number of commit dependencies taken by transactions (on average), per second.</span></span>|  
|<span data-ttu-id="02ad6-111">**Transacciones de solo lectura preparadas/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-111">**Read-only transactions prepared/sec**</span></span>|<span data-ttu-id="02ad6-112">Número de transacciones de solo lectura que se prepararon para el procesamiento de confirmaciones, por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-112">The number of read-only transactions that were prepared for commit processing, per second.</span></span>|  
|<span data-ttu-id="02ad6-113">**Actualizaciones de punto de retorno/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-113">**Save point refreshes/sec**</span></span>|<span data-ttu-id="02ad6-114">Número de veces que se "actualizó" un punto de retorno (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-114">The number of times a savepoint was "refreshed", (on average), per second.</span></span> <span data-ttu-id="02ad6-115">Una actualización de punto de retorno es cuando un punto de retorno existente se restablece al momento actual de la duración de la transacción.</span><span class="sxs-lookup"><span data-stu-id="02ad6-115">A savepoint refresh is when an existing savepoint is reset to the current point in the transaction's lifetime.</span></span>|  
|<span data-ttu-id="02ad6-116">**Reversiones de punto de retorno/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-116">**Save point rollbacks/sec**</span></span>|<span data-ttu-id="02ad6-117">Número de veces que se revertió una transacción a un punto de retorno (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-117">The number of times a transaction rolled back to a save point (on average), per second.</span></span>|  
|<span data-ttu-id="02ad6-118">**Puntos de retorno creados/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-118">**Save points created /sec**</span></span>|<span data-ttu-id="02ad6-119">Número de puntos de retorno creados (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-119">The number of save points created (on average), per second.</span></span>|  
|<span data-ttu-id="02ad6-120">**Errores de validación de transacciones/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-120">**Transaction validation failure/sec**</span></span>|<span data-ttu-id="02ad6-121">Número de transacciones que produjeron error en el procesamiento de validación (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-121">The number of transactions that failed validation processing (on average), per second.</span></span>|  
|<span data-ttu-id="02ad6-122">**Transacciones anuladas por el usuario/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-122">**Transactions aborted by user/sec**</span></span>|<span data-ttu-id="02ad6-123">Número de transacciones que el usuario anuló (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-123">The number of transactions that were aborted by the user (on average), per second.</span></span>|  
|<span data-ttu-id="02ad6-124">**Transacciones anuladas/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-124">**Transactions aborted/sec**</span></span>|<span data-ttu-id="02ad6-125">Número de transacciones anuladas (tanto por el usuario como por el sistema, en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-125">The number of transactions that aborted (both by the user and the system, on average), per second.</span></span>|  
|<span data-ttu-id="02ad6-126">**Transacciones creadas/s**</span><span class="sxs-lookup"><span data-stu-id="02ad6-126">**Transactions created/sec**</span></span>|<span data-ttu-id="02ad6-127">Número de transacciones creadas en el sistema (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="02ad6-127">The number of transactions created in the system (on average), per second.</span></span><br /><br /> <span data-ttu-id="02ad6-128">Las transacciones XTP se cuentan de manera distinta que las transacciones basadas en disco (según se refleja en Bases de datos: Transacciones/seg).</span><span class="sxs-lookup"><span data-stu-id="02ad6-128">XTP transactions are counted differently than disk-based transactions (as reflected in Databases:Transactions/sec).</span></span> <span data-ttu-id="02ad6-129">Por ejemplo, Transacciones creadas/seg cuenta las transacciones de solo lectura, mientras que Bases de datos: Transacciones/seg no.</span><span class="sxs-lookup"><span data-stu-id="02ad6-129">For example, Transactions created/sec counts read/only transactions, while Databases:Transactions/sec does not.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02ad6-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02ad6-130">See Also</span></span>  
 [<span data-ttu-id="02ad6-131">Contadores de rendimiento de OLTP &#40;en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="02ad6-131">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
