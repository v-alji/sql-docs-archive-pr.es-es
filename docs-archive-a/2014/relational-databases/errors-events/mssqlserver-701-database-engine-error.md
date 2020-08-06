---
title: MSSQLSERVER_701 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 701 (Database Engine error)
ms.assetid: 3b975000-63a1-43c2-a40f-89d0a8a36bef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 542535223d3e394c72079092411add143de61545
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671077"
---
# <a name="mssqlserver_701"></a><span data-ttu-id="ddea5-102">MSSQLSERVER_701</span><span class="sxs-lookup"><span data-stu-id="ddea5-102">MSSQLSERVER_701</span></span>
    
## <a name="details"></a><span data-ttu-id="ddea5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ddea5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddea5-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ddea5-104">Product Name</span></span>|<span data-ttu-id="ddea5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddea5-105">SQL Server</span></span>|  
|<span data-ttu-id="ddea5-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ddea5-106">Event ID</span></span>|<span data-ttu-id="ddea5-107">701</span><span class="sxs-lookup"><span data-stu-id="ddea5-107">701</span></span>|  
|<span data-ttu-id="ddea5-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ddea5-108">Event Source</span></span>|<span data-ttu-id="ddea5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ddea5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ddea5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ddea5-110">Component</span></span>|<span data-ttu-id="ddea5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ddea5-111">SQLEngine</span></span>|  
|<span data-ttu-id="ddea5-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ddea5-112">Symbolic Name</span></span>|<span data-ttu-id="ddea5-113">NOSYSMEM</span><span class="sxs-lookup"><span data-stu-id="ddea5-113">NOSYSMEM</span></span>|  
|<span data-ttu-id="ddea5-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ddea5-114">Message Text</span></span>|<span data-ttu-id="ddea5-115">Memoria de sistema insuficiente para ejecutar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="ddea5-115">There is insufficient system memory to run this query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ddea5-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ddea5-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ddea5-117">no ha podido asignar suficiente memoria para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="ddea5-117">has failed to allocate sufficient memory to run the query.</span></span> <span data-ttu-id="ddea5-118">Esto puede deberse a varios motivos, entre los que se incluye la configuración del sistema operativo, la disponibilidad de la memoria física o los límites de la memoria en la carga de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="ddea5-118">This can be caused by a variety of reasons including operating system settings, physical memory availability, or memory limits on the current workload.</span></span> <span data-ttu-id="ddea5-119">En la mayoría de los casos, la transacción que no se ha realizado no es la causa de este error.</span><span class="sxs-lookup"><span data-stu-id="ddea5-119">In most cases, the transaction that failed is not the cause of this error.</span></span>  
  
 <span data-ttu-id="ddea5-120">Las consultas de diagnóstico, como las instrucciones DBCC, pueden generar un error porque el servidor no tiene suficiente memoria.</span><span class="sxs-lookup"><span data-stu-id="ddea5-120">Diagnostic queries, such as DBCC statements, may fail because server the does not have sufficient memory.</span></span>  
  
 <span data-ttu-id="ddea5-121">Se agotó el tiempo de espera mientras los recursos de memoria ejecutaban la consulta en el grupo de recursos 'predeterminado'.</span><span class="sxs-lookup"><span data-stu-id="ddea5-121">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddea5-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ddea5-122">User Action</span></span>  
 <span data-ttu-id="ddea5-123">Si no utiliza el regulador de recursos, le recomendamos que compruebe el estado y la carga generales del servidor, o la configuración del grupo de recursos o del grupo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ddea5-123">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="ddea5-124">En la siguiente lista se describen los pasos generales que ayudarán a resolver los errores de memoria:</span><span class="sxs-lookup"><span data-stu-id="ddea5-124">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="ddea5-125">Compruebe si otras aplicaciones o servicios están consumiendo memoria en este servidor.</span><span class="sxs-lookup"><span data-stu-id="ddea5-125">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="ddea5-126">Vuelva a configurar las aplicaciones o servicios menos críticos para que consuman menos memoria.</span><span class="sxs-lookup"><span data-stu-id="ddea5-126">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="ddea5-127">Empiece a recopilar los contadores del monitor de rendimiento para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Administrador de búfer**, **SQL Server: Administrador de memoria**.</span><span class="sxs-lookup"><span data-stu-id="ddea5-127">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="ddea5-128">Compruebe los siguientes parámetros de configuración de memoria de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ddea5-128">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="ddea5-129">**memoria de servidor máxima**</span><span class="sxs-lookup"><span data-stu-id="ddea5-129">**max server memory**</span></span>  
  
    -   <span data-ttu-id="ddea5-130">**memoria de servidor mínima**</span><span class="sxs-lookup"><span data-stu-id="ddea5-130">**min server memory**</span></span>  
  
    -   <span data-ttu-id="ddea5-131">**memoria mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="ddea5-131">**min memory per query**</span></span>  
  
     <span data-ttu-id="ddea5-132">Observe si hay algún valor fuera de lo normal.</span><span class="sxs-lookup"><span data-stu-id="ddea5-132">Notice unusual settings.</span></span> <span data-ttu-id="ddea5-133">Corríjalos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ddea5-133">Correct them as necessary.</span></span> <span data-ttu-id="ddea5-134">Investigue el porqué de los mayores requisitos de memoria.</span><span class="sxs-lookup"><span data-stu-id="ddea5-134">Account for increased memory requirements.</span></span> <span data-ttu-id="ddea5-135">La configuración predeterminada se enumera en "Establecer las opciones de configuración del servidor" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ddea5-135">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="ddea5-136">Observe la salida de DBCC MEMORYSTATUS y la forma en que cambia cuando aparecen estos mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="ddea5-136">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="ddea5-137">Compruebe la carga de trabajo (por ejemplo, el número de sesiones simultáneas y las consultas que se están ejecutando actualmente).</span><span class="sxs-lookup"><span data-stu-id="ddea5-137">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="ddea5-138">Las siguientes acciones pueden hacer que haya más memoria disponible para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ddea5-138">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="ddea5-139">Si otras aplicaciones además de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] están consumiendo recursos, intente detener su ejecución o plantéese ejecutarlas en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="ddea5-139">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="ddea5-140">Esto quitará presión externa de la memoria.</span><span class="sxs-lookup"><span data-stu-id="ddea5-140">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="ddea5-141">Si ha configurado **max server memory**, aumente su valor.</span><span class="sxs-lookup"><span data-stu-id="ddea5-141">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="ddea5-142">Ejecute los siguientes comandos DBCC para liberar varias cachés de la memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddea5-142">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="ddea5-143">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="ddea5-143">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="ddea5-144">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="ddea5-144">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="ddea5-145">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="ddea5-145">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="ddea5-146">Si el problema persiste, necesitará investigar más y, posiblemente, reducir la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ddea5-146">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
