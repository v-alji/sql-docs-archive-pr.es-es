---
title: MSSQLSERVER_847 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 847 (Database Engine error)
ms.assetid: 67208b7c-bd8d-48a1-9f70-a6488e0f5f9b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b2d5c0a35533700606a44867d2a51cf9087e399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674857"
---
# <a name="mssqlserver_847"></a><span data-ttu-id="81b8b-102">MSSQLSERVER_847</span><span class="sxs-lookup"><span data-stu-id="81b8b-102">MSSQLSERVER_847</span></span>
    
## <a name="details"></a><span data-ttu-id="81b8b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="81b8b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81b8b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="81b8b-104">Product Name</span></span>|<span data-ttu-id="81b8b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="81b8b-105">SQL Server</span></span>|  
|<span data-ttu-id="81b8b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="81b8b-106">Event ID</span></span>|<span data-ttu-id="81b8b-107">847</span><span class="sxs-lookup"><span data-stu-id="81b8b-107">847</span></span>|  
|<span data-ttu-id="81b8b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="81b8b-108">Event Source</span></span>|<span data-ttu-id="81b8b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="81b8b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="81b8b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="81b8b-110">Component</span></span>|<span data-ttu-id="81b8b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="81b8b-111">SQLEngine</span></span>|  
|<span data-ttu-id="81b8b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="81b8b-112">Symbolic Name</span></span>|<span data-ttu-id="81b8b-113">N/D</span><span class="sxs-lookup"><span data-stu-id="81b8b-113">N/A</span></span>|  
|<span data-ttu-id="81b8b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="81b8b-114">Message Text</span></span>|<span data-ttu-id="81b8b-115">Se agotó el tiempo de espera mientras se esperaba el bloqueo temporal: clase '%ls', id. %p, tipo %d, Tarea 0x%p : %d, tiempo de espera %d, marcas 0x%I64x, tarea propietaria 0x%p.</span><span class="sxs-lookup"><span data-stu-id="81b8b-115">Time-out occurred while waiting for latch: class '%ls', id %p, type %d, Task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span> <span data-ttu-id="81b8b-116">Esperando.</span><span class="sxs-lookup"><span data-stu-id="81b8b-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81b8b-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="81b8b-117">Explanation</span></span>  
 <span data-ttu-id="81b8b-118">Es posible que un equipo deje de responder, que se agote el tiempo de espera o que se produzca alguna otra interrupción de las operaciones normales al mismo tiempo que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escribe errores de bloqueos temporales de búfer en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81b8b-118">A computer might stop responding, or a time-out or some other disruption of regular operations might occur at the same time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] writes buffer latch errors to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="81b8b-119">Si el campo de estado del mensaje tiene activado el valor 0x04, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estará esperando una operación de E/S.</span><span class="sxs-lookup"><span data-stu-id="81b8b-119">If the stat field in the message has the value of 0x04 on, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for an I/O operation.</span></span> <span data-ttu-id="81b8b-120">También puede recibir el mensaje [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81b8b-120">You may also receive message [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="81b8b-121">Si el campo de estado del mensaje tiene desactivado el valor 0x04, habrá una contención intensa en una página.</span><span class="sxs-lookup"><span data-stu-id="81b8b-121">If the stat field in the message has the value 0x04 off, there is heavy contention for a page.</span></span> <span data-ttu-id="81b8b-122">Si el objeto es una página de datos, esto puede deberse a un diseño de código ineficaz.</span><span class="sxs-lookup"><span data-stu-id="81b8b-122">If the object is a data page, this can be caused by inefficient code design.</span></span> <span data-ttu-id="81b8b-123">Si la página no es de datos, el error puede producirse por cuellos de botella del servidor, como recursos de hardware insuficientes.</span><span class="sxs-lookup"><span data-stu-id="81b8b-123">If the page is nondata, the error might be caused by server bottlenecks, such as insufficient hardware resources.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81b8b-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="81b8b-124">User Action</span></span>  
 <span data-ttu-id="81b8b-125">Para solucionar este problema, según el entorno, puede seguir uno o varios de estos pasos para reducir o eliminar los mensajes de error:</span><span class="sxs-lookup"><span data-stu-id="81b8b-125">To work around this problem, depending on your environment, one or more of the following steps might reduce or eliminate the error messages:</span></span>  
  
-   <span data-ttu-id="81b8b-126">Determine si tiene algún cuello de botella de hardware.</span><span class="sxs-lookup"><span data-stu-id="81b8b-126">Determine whether you have any hardware bottlenecks.</span></span> <span data-ttu-id="81b8b-127">Si es necesario, actualice el hardware para que sea compatible con los requisitos de configuración, consulta y carga del entorno.</span><span class="sxs-lookup"><span data-stu-id="81b8b-127">If it is necessary, upgrade your hardware so that it can support the configuration, query, and load requirements of your environment.</span></span> <span data-ttu-id="81b8b-128">Para obtener más información sobre los cuellos de botella, vea [Identificar los cuellos de botella](../performance/identify-bottlenecks.md).</span><span class="sxs-lookup"><span data-stu-id="81b8b-128">For more information about bottlenecks, see [Identify Bottlenecks](../performance/identify-bottlenecks.md).</span></span>  
  
-   <span data-ttu-id="81b8b-129">Compruebe si hay algún error registrado y ejecute los diagnósticos suministrados por el proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="81b8b-129">Check for any logged errors and run any diagnostics provided by your hardware vendor.</span></span>  
  
-   <span data-ttu-id="81b8b-130">Asegúrese de que las unidades de disco no estén comprimidas.</span><span class="sxs-lookup"><span data-stu-id="81b8b-130">Make sure that your disk drives are not compressed.</span></span> <span data-ttu-id="81b8b-131">No se admite el almacenamiento de datos ni archivos de registro en unidades comprimidas.</span><span class="sxs-lookup"><span data-stu-id="81b8b-131">Storing data or log files on compressed drives is not supported.</span></span> <span data-ttu-id="81b8b-132">Para obtener más información sobre los archivos físicos, vea [Archivos y grupos de archivos de base de datos](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="81b8b-132">For more information about physical files, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
-   <span data-ttu-id="81b8b-133">Observe si los mensajes de error desaparecen al desactivar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="81b8b-133">See whether the error messages disappear when you set the following options to off:</span></span>  
  
    -   <span data-ttu-id="81b8b-134">Opción de configuración de aumento de prioridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="81b8b-134">SQL Server priority boost configuration option</span></span>  
  
    -   <span data-ttu-id="81b8b-135">Opción de agrupación ligera (modo de fibra)</span><span class="sxs-lookup"><span data-stu-id="81b8b-135">Lightweight pooling (fiber mode) option</span></span>  
  
    -   <span data-ttu-id="81b8b-136">Opción "set working set size"</span><span class="sxs-lookup"><span data-stu-id="81b8b-136">Set working set size option</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="81b8b-137">A menudo, las opciones de configuración anteriores pueden ser contraproducentes si modifica su valor predeterminado desactivado.</span><span class="sxs-lookup"><span data-stu-id="81b8b-137">The previous settings can frequently be counter-productive if you change them from their default setting of OFF.</span></span> <span data-ttu-id="81b8b-138">Para obtener más información, vea [Opciones de configuración del servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="81b8b-138">For more information about the settings, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
-   <span data-ttu-id="81b8b-139">Optimice las consultas para reducir los recursos utilizados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="81b8b-139">Tune queries to reduce resources used on the system.</span></span> <span data-ttu-id="81b8b-140">La optimización del rendimiento ayudará a reducir la demanda en un sistema y a mejorar el tiempo de respuesta de las consultas individuales.</span><span class="sxs-lookup"><span data-stu-id="81b8b-140">Performance tuning will help reduce the stress on a system and improve response time for individual queries.</span></span>  
  
-   <span data-ttu-id="81b8b-141">Establezca la opción AUTO_SHRINK en OFF para reducir la sobrecarga de los cambios de tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="81b8b-141">Set the AUTO_SHRINK option to OFF to reduce the overhead of changes to the database size.</span></span>  
  
-   <span data-ttu-id="81b8b-142">Asegúrese de establecer la opción FILEGROWTH en incrementos lo suficientemente grandes como para ser infrecuentes.</span><span class="sxs-lookup"><span data-stu-id="81b8b-142">Make sure that you set the FILEGROWTH option to increments that are large enough to be infrequent.</span></span> <span data-ttu-id="81b8b-143">Programe un trabajo para comprobar el espacio disponible en las bases de datos y, a continuación, aumente el tamaño de la base de datos durante las horas de menor actividad.</span><span class="sxs-lookup"><span data-stu-id="81b8b-143">Schedule a job to check the available space in the databases, and then increase the database size during nonpeak hours.</span></span>  
  
  
