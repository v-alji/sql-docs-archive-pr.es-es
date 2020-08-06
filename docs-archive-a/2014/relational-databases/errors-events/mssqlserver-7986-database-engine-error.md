---
title: MSSQLSERVER_7986 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7986 (Database Engine error)
ms.assetid: ae64276c-4e1e-4ef3-9ee9-ebeb2f61e565
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4f7d312987a2692c95f2cf6dbe0c86a4b2acbe6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746996"
---
# <a name="mssqlserver_7986"></a><span data-ttu-id="86de5-102">MSSQLSERVER_7986</span><span class="sxs-lookup"><span data-stu-id="86de5-102">MSSQLSERVER_7986</span></span>
    
## <a name="details"></a><span data-ttu-id="86de5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="86de5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86de5-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="86de5-104">Product Name</span></span>|<span data-ttu-id="86de5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="86de5-105">SQL Server</span></span>|  
|<span data-ttu-id="86de5-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="86de5-106">Event ID</span></span>|<span data-ttu-id="86de5-107">7986</span><span class="sxs-lookup"><span data-stu-id="86de5-107">7986</span></span>|  
|<span data-ttu-id="86de5-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="86de5-108">Event Source</span></span>|<span data-ttu-id="86de5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="86de5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="86de5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="86de5-110">Component</span></span>|<span data-ttu-id="86de5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="86de5-111">SQLEngine</span></span>|  
|<span data-ttu-id="86de5-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="86de5-112">Symbolic Name</span></span>|<span data-ttu-id="86de5-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span><span class="sxs-lookup"><span data-stu-id="86de5-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span></span>|  
|<span data-ttu-id="86de5-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="86de5-114">Message Text</span></span>|<span data-ttu-id="86de5-115">Comprobaciones previas de tabla del sistema: el id. de objeto O_ID tiene encadenamiento entre objetos.</span><span class="sxs-lookup"><span data-stu-id="86de5-115">System table pre-checks: Object ID O_ID has cross-object chain linkage.</span></span> <span data-ttu-id="86de5-116">La página P_ID1 apunta a P_ID2 en el Id. de unidad de asignación A_ID1 (debería ser A_ID2).</span><span class="sxs-lookup"><span data-stu-id="86de5-116">Page P_ID1 points to P_ID2 in alloc unit ID A_ID1 (should be A_ID2).</span></span> <span data-ttu-id="86de5-117">Instrucción de comprobación terminada debido a un error irreparable.</span><span class="sxs-lookup"><span data-stu-id="86de5-117">Check statement terminated due to unrepairable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="86de5-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="86de5-118">Explanation</span></span>  
 <span data-ttu-id="86de5-119">La primera fase de DBCC CHECKDB es hacer comprobaciones básicas en las páginas de datos de las tablas críticas del sistema.</span><span class="sxs-lookup"><span data-stu-id="86de5-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="86de5-120">Si se encuentra algún error, no puede repararse; por tanto, DBCC CHECKDB termina inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="86de5-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="86de5-121">El puntero de página siguiente de la página *P_ID1* en el nivel de datos del objeto especificado apunta a una página, *P_ID2*, de un objeto diferente.</span><span class="sxs-lookup"><span data-stu-id="86de5-121">The next page pointer of page *P_ID1* in the data level of the specified object points to a page, *P_ID2*, in a different object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86de5-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="86de5-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="86de5-123">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="86de5-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="86de5-124">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="86de5-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="86de5-125">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="86de5-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="86de5-126">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="86de5-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="86de5-127">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="86de5-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="86de5-128">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="86de5-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="86de5-129">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="86de5-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="86de5-130">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="86de5-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="86de5-131">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="86de5-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="86de5-132">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="86de5-132">Restore from Backup</span></span>  
 <span data-ttu-id="86de5-133">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86de5-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="86de5-134">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="86de5-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="86de5-135">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="86de5-135">Not applicable.</span></span> <span data-ttu-id="86de5-136">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="86de5-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="86de5-137">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86de5-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
