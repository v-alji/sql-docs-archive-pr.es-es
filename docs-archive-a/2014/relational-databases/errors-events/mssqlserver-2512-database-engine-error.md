---
title: MSSQLSERVER_2512 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2512 (Database Engine error)
ms.assetid: 989b527f-5b02-403c-9b7f-51580f4e7688
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da121c8b49ab8290c494d33f0f2a0ba6fded9e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745314"
---
# <a name="mssqlserver_2512"></a><span data-ttu-id="cb636-102">MSSQLSERVER_2512</span><span class="sxs-lookup"><span data-stu-id="cb636-102">MSSQLSERVER_2512</span></span>
    
## <a name="details"></a><span data-ttu-id="cb636-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cb636-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb636-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="cb636-104">Product Name</span></span>|<span data-ttu-id="cb636-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb636-105">SQL Server</span></span>|  
|<span data-ttu-id="cb636-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cb636-106">Event ID</span></span>|<span data-ttu-id="cb636-107">2512</span><span class="sxs-lookup"><span data-stu-id="cb636-107">2512</span></span>|  
|<span data-ttu-id="cb636-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="cb636-108">Event Source</span></span>|<span data-ttu-id="cb636-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cb636-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cb636-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cb636-110">Component</span></span>|<span data-ttu-id="cb636-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cb636-111">SQLEngine</span></span>|  
|<span data-ttu-id="cb636-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cb636-112">Symbolic Name</span></span>|<span data-ttu-id="cb636-113">DBCC_DUPLICATE_KEYS</span><span class="sxs-lookup"><span data-stu-id="cb636-113">DBCC_DUPLICATE_KEYS</span></span>|  
|<span data-ttu-id="cb636-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cb636-114">Message Text</span></span>|<span data-ttu-id="cb636-115">Error de tabla: id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="cb636-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="cb636-116">Hay claves duplicadas en la página P_ID1, zona SLOT1 y en la página P_ID2, zona SLOT2.</span><span class="sxs-lookup"><span data-stu-id="cb636-116">Duplicate keys on page P_ID1 slot SLOT1 and page P_ID2 slot SLOT2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cb636-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="cb636-117">Explanation</span></span>  
 <span data-ttu-id="cb636-118">Las dos zonas especificadas tienen claves idénticas, incluidos los `uniqueifiers`.</span><span class="sxs-lookup"><span data-stu-id="cb636-118">The two specified slots have identical keys, including any `uniqueifiers`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb636-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cb636-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="cb636-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="cb636-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="cb636-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="cb636-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="cb636-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="cb636-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="cb636-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="cb636-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="cb636-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="cb636-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="cb636-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="cb636-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="cb636-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="cb636-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="cb636-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="cb636-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="cb636-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cb636-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="cb636-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="cb636-129">Restore from Backup</span></span>  
 <span data-ttu-id="cb636-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cb636-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="cb636-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="cb636-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="cb636-132">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="cb636-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="cb636-133">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="cb636-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="cb636-134">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="cb636-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="cb636-135">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="cb636-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="cb636-136">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="cb636-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="cb636-137">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="cb636-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="cb636-138">Si uno de los registros es un fantasma o el índice no es único, DBCC puede reparar este problema volviendo a generar el índice.</span><span class="sxs-lookup"><span data-stu-id="cb636-138">If either record is a ghost or the index is nonunique, DBCC can repair this problem by rebuilding the index.</span></span> <span data-ttu-id="cb636-139">De lo contrario, si es necesario, REPAIR eliminará el intervalo *SLOT2* de la página *P_ID2* o marcará la zona como fantasma.</span><span class="sxs-lookup"><span data-stu-id="cb636-139">Otherwise, if necessary, REPAIR will delete slot *SLOT2* on page *P_ID2* or mark the slot as a ghost.</span></span>  
  
  
