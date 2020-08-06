---
title: MSSQLSERVER_5233 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5233 (Database Engine error)
ms.assetid: 7a855afa-2d3b-49b7-adef-197b99fc98b1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a5e2c603652534a6d3093a01da0a926a7195954
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675883"
---
# <a name="mssqlserver_5233"></a><span data-ttu-id="4aa8e-102">MSSQLSERVER_5233</span><span class="sxs-lookup"><span data-stu-id="4aa8e-102">MSSQLSERVER_5233</span></span>
    
## <a name="details"></a><span data-ttu-id="4aa8e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4aa8e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4aa8e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4aa8e-104">Product Name</span></span>|<span data-ttu-id="4aa8e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4aa8e-105">SQL Server</span></span>|  
|<span data-ttu-id="4aa8e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4aa8e-106">Event ID</span></span>|<span data-ttu-id="4aa8e-107">5233</span><span class="sxs-lookup"><span data-stu-id="4aa8e-107">5233</span></span>|  
|<span data-ttu-id="4aa8e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4aa8e-108">Event Source</span></span>|<span data-ttu-id="4aa8e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4aa8e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4aa8e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4aa8e-110">Component</span></span>|<span data-ttu-id="4aa8e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4aa8e-111">SQLEngine</span></span>|  
|<span data-ttu-id="4aa8e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4aa8e-112">Symbolic Name</span></span>|<span data-ttu-id="4aa8e-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="4aa8e-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="4aa8e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4aa8e-114">Message Text</span></span>|<span data-ttu-id="4aa8e-115">Error de tabla: id. de unidad de asignación A_ID, página P_ID.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-115">Table error: alloc unit ID A_ID, page P_ID.</span></span> <span data-ttu-id="4aa8e-116">Error de la prueba (TEST).</span><span class="sxs-lookup"><span data-stu-id="4aa8e-116">The test (TEST) failed.</span></span> <span data-ttu-id="4aa8e-117">Los valores son VAL1 y VAL2.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-117">The values are VAL1 and VAL2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4aa8e-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="4aa8e-118">Explanation</span></span>  
 <span data-ttu-id="4aa8e-119">La página *P_ID* ha experimentado un error de auditoría debido a que su encabezado de página está dañado.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-119">Page *P_ID* has failed auditing due to a corruption in its page header.</span></span> <span data-ttu-id="4aa8e-120">La cadena de TEST proporciona la prueba real en la que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-120">The string in TEST gives the actual test that failed.</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4aa8e-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="4aa8e-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4aa8e-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4aa8e-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4aa8e-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4aa8e-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4aa8e-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4aa8e-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4aa8e-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4aa8e-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4aa8e-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="4aa8e-130">Restore from Backup</span></span>  
 <span data-ttu-id="4aa8e-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4aa8e-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4aa8e-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4aa8e-133">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-133">Not applicable.</span></span> <span data-ttu-id="4aa8e-134">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-134">This error cannot be repaired.</span></span> <span data-ttu-id="4aa8e-135">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4aa8e-135">If you cannot restore the database from a backup, contact Microsoft Customer Service and Support (CSS).</span></span>  
  
  
