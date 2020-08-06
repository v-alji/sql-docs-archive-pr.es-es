---
title: Transacciones (categoría de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Transactions event category
- event classes [SQL Server], Transactions event category
- Transactions event category [SQL Server]
ms.assetid: bfc75c5b-7115-49d8-9148-a0c84ee66a9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b68a91fb166797c220cb0c4f5cf2607ca267538
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675405"
---
# <a name="transactions-event-category"></a><span data-ttu-id="e4389-102">Transacciones (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-102">Transactions Event Category</span></span>
  <span data-ttu-id="e4389-103">Las clases de eventos **Transactions** se pueden utilizar para supervisar el estado de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="e4389-103">The **Transactions** event classes can be used to monitor the status of transactions.</span></span> <span data-ttu-id="e4389-104">Los nombres de las clases de eventos prefijados con **TM:** se usan para realizar un seguimiento de las operaciones relacionadas con las transacciones enviadas desde la interfaz de administración de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e4389-104">The event class names that are prefixed with **TM:** are used to track the transaction-related operations that are sent through the transaction management interface.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4389-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e4389-105">In This Section</span></span>  
  
|<span data-ttu-id="e4389-106">Tema</span><span class="sxs-lookup"><span data-stu-id="e4389-106">Topic</span></span>|<span data-ttu-id="e4389-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4389-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e4389-108">DTCTransaction (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-108">DTCTransaction Event Class</span></span>](dtctransaction-event-class.md)|<span data-ttu-id="e4389-109">Realiza un seguimiento de las transacciones coordinadas por el Coordinador de transacciones distribuidas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="e4389-109">Tracks transactions coordinated by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="e4389-110">Se trata de transacciones distribuidas entre dos o más bases de datos o instancias del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4389-110">These are transactions distributed between two or more databases or instances of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>|  
|[<span data-ttu-id="e4389-111">SQLTransaction (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-111">SQLTransaction Event Class</span></span>](sqltransaction-event-class.md)|<span data-ttu-id="e4389-112">Realiza un seguimiento de las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN y ROLLBACK TRAN.</span><span class="sxs-lookup"><span data-stu-id="e4389-112">Tracks [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN, and ROLLBACK TRAN statements.</span></span>|  
|[<span data-ttu-id="e4389-113">TM: Begin Tran Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-113">TM: Begin Tran Completed Event Class</span></span>](tm-begin-tran-completed-event-class.md)|<span data-ttu-id="e4389-114">Indica que se ha completado la solicitud BEGIN TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-114">Indicates that a BEGIN TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="e4389-115">TM: Begin Tran Starting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-115">TM: Begin Tran Starting Event Class</span></span>](tm-begin-tran-starting-event-class.md)|<span data-ttu-id="e4389-116">Indica que se está iniciando la solicitud BEGIN TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-116">Indicates that a BEGIN TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="e4389-117">TM: Commit Tran Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-117">TM: Commit Tran Completed Event Class</span></span>](tm-commit-tran-completed-event-class.md)|<span data-ttu-id="e4389-118">Indica que se ha completado la solicitud COMMIT TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-118">Indicates that a COMMIT TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="e4389-119">TM: Commit Tran Starting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-119">TM: Commit Tran Starting Event Class</span></span>](tm-commit-tran-starting-event-class.md)|<span data-ttu-id="e4389-120">Indica que se está iniciando la solicitud COMMIT TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-120">Indicates that a COMMIT TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="e4389-121">TM: Promote Tran Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-121">TM: Promote Tran Completed Event Class</span></span>](tm-promote-tran-completed-event-class.md)|<span data-ttu-id="e4389-122">Indica que se ha completado la solicitud PROMOTE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-122">Indicates that a PROMOTE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="e4389-123">TM: Promote Tran Starting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-123">TM: Promote Tran Starting Event Class</span></span>](tm-promote-tran-starting-event-class.md)|<span data-ttu-id="e4389-124">Indica que se está iniciando la solicitud PROMOTE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-124">Indicates that a PROMOTE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="e4389-125">TM: Rollback Tran Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-125">TM: Rollback Tran Completed Event Class</span></span>](tm-rollback-tran-completed-event-class.md)|<span data-ttu-id="e4389-126">Indica que se ha completado la solicitud ROLLBACK TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-126">Indicates that a ROLLBACK TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="e4389-127">TM: Rollback Tran Starting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-127">TM: Rollback Tran Starting Event Class</span></span>](tm-rollback-tran-starting-event-class.md)|<span data-ttu-id="e4389-128">Indica que se está iniciando la solicitud ROLLBACK TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-128">Indicates that a ROLLBACK TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="e4389-129">TM: Save Tran Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-129">TM: Save Tran Completed Event Class</span></span>](tm-save-tran-completed-event-class.md)|<span data-ttu-id="e4389-130">Indica que se ha completado la solicitud SAVE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-130">Indicates that a SAVE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="e4389-131">TM: Save Tran Starting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-131">TM: Save Tran Starting Event Class</span></span>](tm-save-tran-starting-event-class.md)|<span data-ttu-id="e4389-132">Indica que se está iniciando la solicitud SAVE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e4389-132">Indicates that a SAVE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="e4389-133">TransactionLog (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="e4389-133">TransactionLog Event Class</span></span>](transactionlog-event-class.md)|<span data-ttu-id="e4389-134">Realiza un seguimiento cuando se escriben transacciones en el registro de transacciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e4389-134">Tracks when transactions are written to a database transaction log.</span></span>|  
  
  
