---
title: MSSQLSERVER_802 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 802 (Database Engine error)
ms.assetid: 5892ed24-4dcb-4bf9-a8a4-a7ca898832d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9edcdda1410d7651f7c7531ef98c64c85741f15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678207"
---
# <a name="mssqlserver_802"></a><span data-ttu-id="182ba-102">MSSQLSERVER_802</span><span class="sxs-lookup"><span data-stu-id="182ba-102">MSSQLSERVER_802</span></span>
    
## <a name="details"></a><span data-ttu-id="182ba-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="182ba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="182ba-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="182ba-104">Product Name</span></span>|<span data-ttu-id="182ba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="182ba-105">SQL Server</span></span>|  
|<span data-ttu-id="182ba-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="182ba-106">Event ID</span></span>|<span data-ttu-id="182ba-107">802</span><span class="sxs-lookup"><span data-stu-id="182ba-107">802</span></span>|  
|<span data-ttu-id="182ba-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="182ba-108">Event Source</span></span>|<span data-ttu-id="182ba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="182ba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="182ba-110">Componente</span><span class="sxs-lookup"><span data-stu-id="182ba-110">Component</span></span>|<span data-ttu-id="182ba-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="182ba-111">SQLEngine</span></span>|  
|<span data-ttu-id="182ba-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="182ba-112">Symbolic Name</span></span>|<span data-ttu-id="182ba-113">NO_BUFS</span><span class="sxs-lookup"><span data-stu-id="182ba-113">NO_BUFS</span></span>|  
|<span data-ttu-id="182ba-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="182ba-114">Message Text</span></span>|<span data-ttu-id="182ba-115">No hay suficiente memoria disponible en el grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="182ba-115">There is insufficient memory available in the buffer pool.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="182ba-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="182ba-116">Explanation</span></span>  
 <span data-ttu-id="182ba-117">Esto se debe a que el grupo de búferes está lleno y no puede crecer más.</span><span class="sxs-lookup"><span data-stu-id="182ba-117">This is caused when the buffer pool is full and the buffer pool can not grow any larger.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="182ba-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="182ba-118">User Action</span></span>  
 <span data-ttu-id="182ba-119">En la siguiente lista se describen los pasos generales que ayudarán a resolver los errores de memoria:</span><span class="sxs-lookup"><span data-stu-id="182ba-119">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="182ba-120">Compruebe si otras aplicaciones o servicios están consumiendo memoria en este servidor.</span><span class="sxs-lookup"><span data-stu-id="182ba-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="182ba-121">Vuelva a configurar las aplicaciones o servicios menos críticos para que consuman menos memoria.</span><span class="sxs-lookup"><span data-stu-id="182ba-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="182ba-122">Empiece a recopilar los contadores del monitor de rendimiento para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Administrador de búfer**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Administrador de memoria**.</span><span class="sxs-lookup"><span data-stu-id="182ba-122">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="182ba-123">Compruebe los siguientes parámetros de configuración de memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="182ba-123">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="182ba-124">**memoria de servidor máxima**</span><span class="sxs-lookup"><span data-stu-id="182ba-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="182ba-125">**memoria de servidor mínima**</span><span class="sxs-lookup"><span data-stu-id="182ba-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="182ba-126">**memoria mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="182ba-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="182ba-127">Observe si hay algún valor fuera de lo normal y corríjalo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="182ba-127">Notice any unusual settings and correct them as necessary.</span></span> <span data-ttu-id="182ba-128">Investigue el porqué de los mayores requisitos de memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="182ba-128">Account for increased memory requirements for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="182ba-129">Se hace una lista de la configuración predeterminada en "Establecer las opciones de configuración del servidor" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="182ba-129">Default settings are listed in "Setting Server Configuration Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="182ba-130">Observe la salida de DBCC MEMORYSTATUS y la forma en que cambia cuando aparecen estos mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="182ba-130">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="182ba-131">Compruebe la carga de trabajo (el número de sesiones simultáneas y las consultas que se están ejecutando actualmente).</span><span class="sxs-lookup"><span data-stu-id="182ba-131">Check the workload (number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="182ba-132">Las siguientes acciones pueden hacer que haya más memoria disponible para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="182ba-132">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="182ba-133">Si otras aplicaciones además de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] están consumiendo recursos, intente detenerlas o ejecutarlas en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="182ba-133">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping these applications or running them on a separate server.</span></span>  
  
-   <span data-ttu-id="182ba-134">Si ha configurado **max server memory**, aumente su valor.</span><span class="sxs-lookup"><span data-stu-id="182ba-134">If you have configured **max server memory,** increase the setting.</span></span>  
  
 <span data-ttu-id="182ba-135">Ejecute los siguientes comandos DBCC para liberar varias cachés de la memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="182ba-135">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="182ba-136">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="182ba-136">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="182ba-137">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="182ba-137">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="182ba-138">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="182ba-138">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="182ba-139">Si el problema persiste, necesitará investigar más y, posiblemente, reducir la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="182ba-139">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
