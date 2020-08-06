---
title: MSSQLSERVER_8645 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8645 (Database Engine error)
ms.assetid: 63d6d6d7-3850-4061-8e96-b1fa665e3180
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7be9774452e2008c34ecb52d228a0123992c5368
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674849"
---
# <a name="mssqlserver_8645"></a><span data-ttu-id="dbae8-102">MSSQLSERVER_8645</span><span class="sxs-lookup"><span data-stu-id="dbae8-102">MSSQLSERVER_8645</span></span>
    
## <a name="details"></a><span data-ttu-id="dbae8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dbae8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dbae8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="dbae8-104">Product Name</span></span>|<span data-ttu-id="dbae8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dbae8-105">SQL Server</span></span>|  
|<span data-ttu-id="dbae8-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="dbae8-106">Event ID</span></span>|<span data-ttu-id="dbae8-107">8645</span><span class="sxs-lookup"><span data-stu-id="dbae8-107">8645</span></span>|  
|<span data-ttu-id="dbae8-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="dbae8-108">Event Source</span></span>|<span data-ttu-id="dbae8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dbae8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dbae8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dbae8-110">Component</span></span>|<span data-ttu-id="dbae8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dbae8-111">SQLEngine</span></span>|  
|<span data-ttu-id="dbae8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dbae8-112">Symbolic Name</span></span>|<span data-ttu-id="dbae8-113">MEMTIMEDOUT_ERR</span><span class="sxs-lookup"><span data-stu-id="dbae8-113">MEMTIMEDOUT_ERR</span></span>|  
|<span data-ttu-id="dbae8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dbae8-114">Message Text</span></span>|<span data-ttu-id="dbae8-115">Se agotó el tiempo de espera para que los recursos de memoria ejecutaran la consulta.</span><span class="sxs-lookup"><span data-stu-id="dbae8-115">A time out occurred while waiting for memory resources to execute the query.</span></span> <span data-ttu-id="dbae8-116">Vuelva a ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="dbae8-116">Rerun the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dbae8-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="dbae8-117">Explanation</span></span>  
 <span data-ttu-id="dbae8-118">Se agotó el tiempo de espera mientras los recursos de memoria ejecutaban la consulta en el grupo de recursos 'predeterminado'.</span><span class="sxs-lookup"><span data-stu-id="dbae8-118">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dbae8-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dbae8-119">User Action</span></span>  
 <span data-ttu-id="dbae8-120">Si no utiliza el regulador de recursos, le recomendamos que compruebe el estado y la carga generales del servidor, o la configuración del grupo de recursos o del grupo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dbae8-120">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="dbae8-121">En la siguiente lista se describen los pasos generales que ayudarán a resolver los errores de memoria:</span><span class="sxs-lookup"><span data-stu-id="dbae8-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="dbae8-122">Compruebe si otras aplicaciones o servicios están consumiendo memoria en este servidor.</span><span class="sxs-lookup"><span data-stu-id="dbae8-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="dbae8-123">Vuelva a configurar las aplicaciones o servicios menos críticos para que consuman menos memoria.</span><span class="sxs-lookup"><span data-stu-id="dbae8-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="dbae8-124">Empiece a recopilar los contadores del monitor de rendimiento para **SQL Server: Administrador de búfer**, **SQL Server: Administrador de memoria**.</span><span class="sxs-lookup"><span data-stu-id="dbae8-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="dbae8-125">Compruebe los siguientes parámetros de configuración de memoria de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="dbae8-125">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="dbae8-126">**memoria de servidor máxima**</span><span class="sxs-lookup"><span data-stu-id="dbae8-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="dbae8-127">**memoria de servidor mínima**</span><span class="sxs-lookup"><span data-stu-id="dbae8-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="dbae8-128">**memoria mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="dbae8-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="dbae8-129">Observe si hay algún valor fuera de lo normal.</span><span class="sxs-lookup"><span data-stu-id="dbae8-129">Notice unusual settings.</span></span> <span data-ttu-id="dbae8-130">Corríjalos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="dbae8-130">Correct them as necessary.</span></span> <span data-ttu-id="dbae8-131">Investigue el porqué de los mayores requisitos de memoria de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbae8-131">Account for increased memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="dbae8-132">La configuración predeterminada se enumera en "Establecer las opciones de configuración del servidor" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dbae8-132">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="dbae8-133">Observe la salida de DBCC MEMORYSTATUS y la forma en que cambia cuando aparecen estos mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="dbae8-133">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="dbae8-134">Compruebe la carga de trabajo (por ejemplo, el número de sesiones simultáneas y las consultas que se están ejecutando actualmente).</span><span class="sxs-lookup"><span data-stu-id="dbae8-134">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="dbae8-135">Las siguientes acciones pueden hacer que haya más memoria disponible para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dbae8-135">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="dbae8-136">Si otras aplicaciones están consumiendo recursos, intente detener su ejecución o plantéese ejecutarlas en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="dbae8-136">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="dbae8-137">Esto quitará presión externa de la memoria.</span><span class="sxs-lookup"><span data-stu-id="dbae8-137">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="dbae8-138">Si ha configurado **max server memory**, aumente su valor.</span><span class="sxs-lookup"><span data-stu-id="dbae8-138">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="dbae8-139">Ejecute los siguientes comandos DBCC para liberar varias cachés de la memoria de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dbae8-139">Run the following DBCC commands to free several SQL Server memory caches.</span></span>  
  
-   <span data-ttu-id="dbae8-140">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="dbae8-140">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="dbae8-141">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="dbae8-141">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="dbae8-142">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="dbae8-142">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="dbae8-143">Si el problema persiste, necesitará investigar más y, posiblemente, reducir la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dbae8-143">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
