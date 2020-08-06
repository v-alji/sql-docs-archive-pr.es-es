---
title: MSSQLSERVER_1222 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ac3fe9314386836633a11f17d6775c75019de93a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662076"
---
# <a name="mssqlserver_1222"></a><span data-ttu-id="a9c3c-102">MSSQLSERVER_1222</span><span class="sxs-lookup"><span data-stu-id="a9c3c-102">MSSQLSERVER_1222</span></span>
    
## <a name="details"></a><span data-ttu-id="a9c3c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a9c3c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9c3c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a9c3c-104">Product Name</span></span>|<span data-ttu-id="a9c3c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9c3c-105">SQL Server</span></span>|  
|<span data-ttu-id="a9c3c-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a9c3c-106">Event ID</span></span>|<span data-ttu-id="a9c3c-107">1222</span><span class="sxs-lookup"><span data-stu-id="a9c3c-107">1222</span></span>|  
|<span data-ttu-id="a9c3c-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a9c3c-108">Event Source</span></span>|<span data-ttu-id="a9c3c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a9c3c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a9c3c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a9c3c-110">Component</span></span>|<span data-ttu-id="a9c3c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a9c3c-111">SQLEngine</span></span>|  
|<span data-ttu-id="a9c3c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a9c3c-112">Symbolic Name</span></span>|<span data-ttu-id="a9c3c-113">LK_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9c3c-113">LK_TIMEOUT</span></span>|  
|<span data-ttu-id="a9c3c-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a9c3c-114">Message Text</span></span>|<span data-ttu-id="a9c3c-115">Superado el tiempo de espera de solicitud de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a9c3c-115">Lock request time out period exceeded.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a9c3c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a9c3c-116">Explanation</span></span>  
 <span data-ttu-id="a9c3c-117">Otra transacción retuvo un bloqueo en un recurso necesario durante más tiempo del que esta consulta podía esperar.</span><span class="sxs-lookup"><span data-stu-id="a9c3c-117">Another transaction held a lock on a required resource longer than this query could wait for it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9c3c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a9c3c-118">User Action</span></span>  
 <span data-ttu-id="a9c3c-119">Realice las siguientes tareas para solucionar el problema:</span><span class="sxs-lookup"><span data-stu-id="a9c3c-119">Perform the following tasks to alleviate the problem:</span></span>  
  
1.  <span data-ttu-id="a9c3c-120">Busque la transacción que está reteniendo el bloqueo en el recurso necesario, si es posible.</span><span class="sxs-lookup"><span data-stu-id="a9c3c-120">Locate the transaction that is holding the lock on the required resource, if possible.</span></span> <span data-ttu-id="a9c3c-121">Use las vistas de administración dinámica **sys.dm_os_waiting_tasks** y **sys.dm_tran_locks**.</span><span class="sxs-lookup"><span data-stu-id="a9c3c-121">Use **sys.dm_os_waiting_tasks** and **sys.dm_tran_locks** dynamic management views.</span></span>  
  
2.  <span data-ttu-id="a9c3c-122">Si la transacción sigue reteniendo el bloqueo, finalice la transacción si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a9c3c-122">If the transaction is still holding the lock, terminate that transaction if appropriate.</span></span>  
  
3.  <span data-ttu-id="a9c3c-123">Vuelva a ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="a9c3c-123">Execute the query again.</span></span>  
  
 <span data-ttu-id="a9c3c-124">Si este error se produce con frecuencia, cambie el período de tiempo de espera de bloqueo o modifique las transacciones problemáticas para que mantengan el bloqueo durante menos tiempo.</span><span class="sxs-lookup"><span data-stu-id="a9c3c-124">If this error occurs frequently change the lock time-out period or modify the offending transactions so that they hold the lock for less time.</span></span>  
  
  
