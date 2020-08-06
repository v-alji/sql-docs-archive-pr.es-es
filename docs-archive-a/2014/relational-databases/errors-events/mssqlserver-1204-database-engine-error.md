---
title: MSSQLSERVER_1204 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1204 (Database Engine error)
ms.assetid: de6ece78-79de-484d-9224-ca0f7645815f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ca03c19552b88e391d2de053193a70531571ece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672075"
---
# <a name="mssqlserver_1204"></a><span data-ttu-id="e5c4c-102">MSSQLSERVER_1204</span><span class="sxs-lookup"><span data-stu-id="e5c4c-102">MSSQLSERVER_1204</span></span>
    
## <a name="details"></a><span data-ttu-id="e5c4c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e5c4c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5c4c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e5c4c-104">Product Name</span></span>|<span data-ttu-id="e5c4c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5c4c-105">SQL Server</span></span>|  
|<span data-ttu-id="e5c4c-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e5c4c-106">Event ID</span></span>|<span data-ttu-id="e5c4c-107">1204</span><span class="sxs-lookup"><span data-stu-id="e5c4c-107">1204</span></span>|  
|<span data-ttu-id="e5c4c-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e5c4c-108">Event Source</span></span>|<span data-ttu-id="e5c4c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e5c4c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e5c4c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e5c4c-110">Component</span></span>|<span data-ttu-id="e5c4c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e5c4c-111">SQLEngine</span></span>|  
|<span data-ttu-id="e5c4c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e5c4c-112">Symbolic Name</span></span>|<span data-ttu-id="e5c4c-113">LK_OUTOF</span><span class="sxs-lookup"><span data-stu-id="e5c4c-113">LK_OUTOF</span></span>|  
|<span data-ttu-id="e5c4c-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e5c4c-114">Message Text</span></span>|<span data-ttu-id="e5c4c-115">La instancia del motor de base de datos de SQL Server no puede obtener un recurso LOCK en este momento.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-115">The instance of the SQL Server Database Engine cannot obtain a LOCK resource at this time.</span></span> <span data-ttu-id="e5c4c-116">Vuelva a ejecutar la instrucción cuando haya menos usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-116">Rerun your statement when there are fewer active users.</span></span> <span data-ttu-id="e5c4c-117">Pida al administrador de la base de datos que compruebe la configuración de bloqueos y memoria de esta instancia o si hay transacciones que se ejecutan durante mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-117">Ask the database administrator to check the lock and memory configuration for this instance, or to check for long-running transactions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e5c4c-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e5c4c-118">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e5c4c-119">no puede obtener un recurso de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-119">cannot obtain a lock resource.</span></span> <span data-ttu-id="e5c4c-120">Esto puede suceder por una de las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="e5c4c-120">This can be caused by either of the following reasons:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e5c4c-121">no puede asignar más memoria del sistema operativo, ya sea porque la están usando otros procesos o porque el servidor está funcionando con la opción **max server memory** configurada.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-121">cannot allocate more memory from the operating system, either because other processes are using it, or because the server is operating with the **max server memory** option configured.</span></span>  
  
-   <span data-ttu-id="e5c4c-122">El administrador de bloqueos no utilizará más del 60 por ciento de la memoria disponible para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5c4c-122">The lock manager will not use more than 60 percent of the memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5c4c-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e5c4c-123">User Action</span></span>  
 <span data-ttu-id="e5c4c-124">Si sospecha que SQL Server no puede asignar suficiente memoria, intente lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5c4c-124">If you suspect that SQL Server cannot allocate sufficient memory, try the following:</span></span>  
  
-   <span data-ttu-id="e5c4c-125">Si hay otras aplicaciones que consumen recursos aparte de SQL Server, intente detener dichas aplicaciones o considere la posibilidad de ejecutarlas en un servidor independiente.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-125">If applications besides SQL Server are consuming resources, try stopping these applications or consider running them on a separate server.</span></span> <span data-ttu-id="e5c4c-126">De esta forma, se liberará memoria de otros procesos para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-126">This will remove release memory from other processes for SQL Server.</span></span>  
  
-   <span data-ttu-id="e5c4c-127">Si ha configurado la opción max server memory, aumente el valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-127">If you have configured max server memory, increase max server memory setting.</span></span>  
  
 <span data-ttu-id="e5c4c-128">Si sospecha que el administrador de bloqueos ha utilizado la cantidad máxima de memoria disponible, identifique la transacción que retiene más bloqueos y finalícela.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-128">If you suspect that the lock manager has used the maximum amount of available memory identify the transaction that is holding the most locks and terminate it.</span></span> <span data-ttu-id="e5c4c-129">Mediante el siguiente script se identifica la transacción que tiene más bloqueos:</span><span class="sxs-lookup"><span data-stu-id="e5c4c-129">The following script will identify the transaction with the most locks:</span></span>  
  
```  
SELECT request_session_id, COUNT (*) num_locks  
FROM sys.dm_tran_locks  
GROUP BY request_session_id   
ORDER BY count (*) DESC  
```  
  
 <span data-ttu-id="e5c4c-130">Finalice el identificador de sesión más alto mediante el comando KILL.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-130">Take the highest session id, and terminate it using the KILL command.</span></span>  
  
  
