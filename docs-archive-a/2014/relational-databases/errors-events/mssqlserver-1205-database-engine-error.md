---
title: MSSQLSERVER_1205 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6afa81a05eea37bc67cd2e9ac2433b6c82f35b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662077"
---
# <a name="mssqlserver_1205"></a><span data-ttu-id="a6258-102">MSSQLSERVER_1205</span><span class="sxs-lookup"><span data-stu-id="a6258-102">MSSQLSERVER_1205</span></span>
    
## <a name="details"></a><span data-ttu-id="a6258-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a6258-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6258-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a6258-104">Product Name</span></span>|<span data-ttu-id="a6258-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6258-105">SQL Server</span></span>|  
|<span data-ttu-id="a6258-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a6258-106">Event ID</span></span>|<span data-ttu-id="a6258-107">1205</span><span class="sxs-lookup"><span data-stu-id="a6258-107">1205</span></span>|  
|<span data-ttu-id="a6258-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a6258-108">Event Source</span></span>|<span data-ttu-id="a6258-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a6258-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a6258-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a6258-110">Component</span></span>|<span data-ttu-id="a6258-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a6258-111">SQLEngine</span></span>|  
|<span data-ttu-id="a6258-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a6258-112">Symbolic Name</span></span>|<span data-ttu-id="a6258-113">LK_VICTIM</span><span class="sxs-lookup"><span data-stu-id="a6258-113">LK_VICTIM</span></span>|  
|<span data-ttu-id="a6258-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a6258-114">Message Text</span></span>|<span data-ttu-id="a6258-115">La transacción (Id. de proceso %d) quedó en interbloqueo en %.\*ls recursos con otro proceso y fue elegida como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="a6258-115">Transaction (Process ID %d) was deadlocked on %.\*ls resources with another process and has been chosen as the deadlock victim.</span></span> <span data-ttu-id="a6258-116">Vuelva a ejecutar la transacción.</span><span class="sxs-lookup"><span data-stu-id="a6258-116">Rerun the transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6258-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="a6258-117">Explanation</span></span>  
 <span data-ttu-id="a6258-118">El orden en el que se accede a los recursos en transacciones independientes es conflictivo y provoca un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="a6258-118">Resources are accessed in conflicting order on separate transactions, causing a deadlock.</span></span> <span data-ttu-id="a6258-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a6258-119">For example:</span></span>  
  
-   <span data-ttu-id="a6258-120">Transaction1 actualiza **Table1.Row1**, mientras que Transaction2 actualiza **Table2.Row2**.</span><span class="sxs-lookup"><span data-stu-id="a6258-120">Transaction1 updates **Table1.Row1**, while Transaction2 updates **Table2.Row2**.</span></span>  
  
-   <span data-ttu-id="a6258-121">Transaction1 intenta actualizar **Table2.Row2**, pero se bloquea porque todavía no se ha confirmado Transaction2.</span><span class="sxs-lookup"><span data-stu-id="a6258-121">Transaction1 tries to update **Table2.Row2** but is blocked because Transaction2 has not yet committed.</span></span>  
  
-   <span data-ttu-id="a6258-122">Transaction2 ahora intenta actualizar **Table1.Row1**, pero se bloquea porque no se ha confirmado Transaction1.</span><span class="sxs-lookup"><span data-stu-id="a6258-122">Transaction2 now tries to update **Table1.Row1** but is blocked because Transaction1 has not committed.</span></span>  
  
-   <span data-ttu-id="a6258-123">Se produce un interbloqueo porque Transacción1 está esperando a que Transacción2 finalice, pero Transacción2 está esperando a que finalice Transacción1.</span><span class="sxs-lookup"><span data-stu-id="a6258-123">A deadlock occurs because Transaction1 is waiting for Transaction2 to complete, but Transaction2 is waiting for Transaction1 to complete.</span></span>  
  
 <span data-ttu-id="a6258-124">El sistema detectará dicho interbloqueo, elegirá una de las transacciones implicadas como "víctima" y generará este mensaje, lo que deshará la transacción de la víctima.</span><span class="sxs-lookup"><span data-stu-id="a6258-124">The system will detect this deadlock and will choose one of the transactions involved as a 'victim' and will issue this message, rolling back the victim's transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6258-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a6258-125">User Action</span></span>  
 <span data-ttu-id="a6258-126">Ejecute de nuevo la transacción.</span><span class="sxs-lookup"><span data-stu-id="a6258-126">Execute the transaction again.</span></span> <span data-ttu-id="a6258-127">También puede revisar la aplicación para evitar los interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="a6258-127">You can also revise the application to avoid deadlocks.</span></span> <span data-ttu-id="a6258-128">La transacción elegida como víctima se puede volver a intentar y probablemente se realizará correctamente, en función de qué operaciones se estén ejecutando simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a6258-128">The transaction that was chosen as a victim can be retried and will likely succeed, depending on what operations are being executed simultaneously.</span></span>  
  
 <span data-ttu-id="a6258-129">Para evitar la aparición de interbloqueos, considere la posibilidad de hacer que todas las transacciones accedan a las filas en el mismo orden (**Table1**, seguida de **Table2**); de esta forma, aunque se puedan producir bloqueos, no se generarán interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="a6258-129">To prevent or avoid deadlocks from occurring, consider having all transactions access rows in the same order (**Table1**, then **Table2**); this way, although blocking might occur, a deadlock will not occur.</span></span>  
  
  
