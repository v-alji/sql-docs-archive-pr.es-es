---
title: MSSQLSERVER_4846 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4846 (Database Engine error)
ms.assetid: a455e809-1883-4c7d-b3e3-835ee5bfe258
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 923137645aae72476fb4b2ae33f0cbbf3e81c2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745309"
---
# <a name="mssqlserver_4846"></a><span data-ttu-id="3fd3f-102">MSSQLSERVER_4846</span><span class="sxs-lookup"><span data-stu-id="3fd3f-102">MSSQLSERVER_4846</span></span>
    
## <a name="details"></a><span data-ttu-id="3fd3f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3fd3f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3fd3f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="3fd3f-104">Product Name</span></span>|<span data-ttu-id="3fd3f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3fd3f-105">SQL Server</span></span>|  
|<span data-ttu-id="3fd3f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="3fd3f-106">Event ID</span></span>|<span data-ttu-id="3fd3f-107">4846</span><span class="sxs-lookup"><span data-stu-id="3fd3f-107">4846</span></span>|  
|<span data-ttu-id="3fd3f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="3fd3f-108">Event Source</span></span>|<span data-ttu-id="3fd3f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3fd3f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3fd3f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3fd3f-110">Component</span></span>|<span data-ttu-id="3fd3f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3fd3f-111">SQLEngine</span></span>|  
|<span data-ttu-id="3fd3f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3fd3f-112">Symbolic Name</span></span>|<span data-ttu-id="3fd3f-113">BULKPROV_MEMORY</span><span class="sxs-lookup"><span data-stu-id="3fd3f-113">BULKPROV_MEMORY</span></span>|  
|<span data-ttu-id="3fd3f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3fd3f-114">Message Text</span></span>|<span data-ttu-id="3fd3f-115">El proveedor de conjuntos masivos de datos no pudo asignar memoria.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-115">The bulk data provider failed to allocate memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3fd3f-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3fd3f-116">Explanation</span></span>  
 <span data-ttu-id="3fd3f-117">Se produjo un error de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-117">Memory allocation failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3fd3f-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3fd3f-118">User Action</span></span>  
 <span data-ttu-id="3fd3f-119">Para solucionar errores de memoria, siga estos pasos generales:</span><span class="sxs-lookup"><span data-stu-id="3fd3f-119">Follow these general steps to troubleshoot memory errors:</span></span>  
  
1.  <span data-ttu-id="3fd3f-120">Compruebe si otras aplicaciones o servicios están consumiendo memoria en este servidor.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="3fd3f-121">Vuelva a configurar las aplicaciones o servicios menos críticos para que consuman menos memoria.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="3fd3f-122">Empiece a recopilar los contadores del monitor de rendimiento para **SQL Server: Administrador de búfer**, **SQL Server: Administrador de memoria**.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-122">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="3fd3f-123">Compruebe los siguientes parámetros de configuración de memoria de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="3fd3f-123">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="3fd3f-124">**memoria de servidor máxima**</span><span class="sxs-lookup"><span data-stu-id="3fd3f-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="3fd3f-125">**memoria de servidor mínima**</span><span class="sxs-lookup"><span data-stu-id="3fd3f-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="3fd3f-126">**memoria mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="3fd3f-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="3fd3f-127">Observe si hay algún valor fuera de lo normal.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-127">Notice any unusual settings.</span></span> <span data-ttu-id="3fd3f-128">Corríjalos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-128">Correct them as necessary.</span></span> <span data-ttu-id="3fd3f-129">Investigue los requisitos de memoria para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fd3f-129">Account for memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3fd3f-130">La configuración predeterminada se enumera en "Establecer las opciones de configuración del servidor" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-130">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="3fd3f-131">Observe la salida de DBCC MEMORYSTATUS y la forma en que cambia cuando aparecen estos mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-131">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="3fd3f-132">Compruebe la carga de trabajo (por ejemplo, el número de sesiones simultáneas y las consultas que se están ejecutando actualmente).</span><span class="sxs-lookup"><span data-stu-id="3fd3f-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="3fd3f-133">Las siguientes acciones pueden hacer que haya más memoria disponible para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3fd3f-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="3fd3f-134">Si otras aplicaciones están consumiendo recursos, intente detener su ejecución o plantéese ejecutarlas en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-134">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="3fd3f-135">Esto quitará presión externa de la memoria.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="3fd3f-136">Si ha configurado **max server memory**, aumente su valor.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="3fd3f-137">Ejecute los siguientes comandos DBCC para liberar varias cachés de la memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fd3f-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="3fd3f-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="3fd3f-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="3fd3f-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="3fd3f-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="3fd3f-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="3fd3f-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="3fd3f-141">Si el problema persiste, necesitará investigar más y, posiblemente, reducir la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3fd3f-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
