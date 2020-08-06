---
title: MSSQLSERVER_825 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 825 (Database Engine error)
ms.assetid: f69f8214-5af1-4769-878b-117ad6eaff52
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3b17dfac371ad3c805fdbb0b5d3269fc451dd9d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672048"
---
# <a name="mssqlserver_825"></a><span data-ttu-id="7eea0-102">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="7eea0-102">MSSQLSERVER_825</span></span>
    
## <a name="details"></a><span data-ttu-id="7eea0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7eea0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7eea0-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7eea0-104">Product Name</span></span>|<span data-ttu-id="7eea0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7eea0-105">SQL Server</span></span>|  
|<span data-ttu-id="7eea0-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7eea0-106">Event ID</span></span>|<span data-ttu-id="7eea0-107">825</span><span class="sxs-lookup"><span data-stu-id="7eea0-107">825</span></span>|  
|<span data-ttu-id="7eea0-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7eea0-108">Event Source</span></span>|<span data-ttu-id="7eea0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7eea0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7eea0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7eea0-110">Component</span></span>|<span data-ttu-id="7eea0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7eea0-111">SQLEngine</span></span>|  
|<span data-ttu-id="7eea0-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7eea0-112">Symbolic Name</span></span>|<span data-ttu-id="7eea0-113">B_RETRYWORKED</span><span class="sxs-lookup"><span data-stu-id="7eea0-113">B_RETRYWORKED</span></span>|  
|<span data-ttu-id="7eea0-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7eea0-114">Message Text</span></span>|<span data-ttu-id="7eea0-115">Se realizó correctamente una operación de lectura del archivo '%ls' en el desplazamiento %#016I64x después de %d intentos sin éxito: %ls.</span><span class="sxs-lookup"><span data-stu-id="7eea0-115">A read of the file '%ls' at offset %#016I64x succeeded after failing %d time(s) with error: %ls.</span></span> <span data-ttu-id="7eea0-116">Encontrará más detalles en los mensajes adicionales del registro de errores de SQL Server y el registro de eventos del sistema.</span><span class="sxs-lookup"><span data-stu-id="7eea0-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="7eea0-117">Este estado de error amenaza la integridad de la base de datos y debe ser rectificado.</span><span class="sxs-lookup"><span data-stu-id="7eea0-117">This error condition threatens database integrity and must be corrected.</span></span> <span data-ttu-id="7eea0-118">Ejecute una comprobación de coherencia completa de la base de datos (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="7eea0-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="7eea0-119">Este error puede deberse a muchos factores. Para obtener más información vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7eea0-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7eea0-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="7eea0-120">Explanation</span></span>  
 <span data-ttu-id="7eea0-121">Este mensaje indica que la operación de lectura tenía que volver a emitirse al menos una vez e indica un problema más importante con el hardware del disco.</span><span class="sxs-lookup"><span data-stu-id="7eea0-121">This message indicates that the read operation had to be reissued at least one time, and indicates a major problem with the disk hardware.</span></span> <span data-ttu-id="7eea0-122">Este mensaje no indica actualmente un problema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sino que el problema del disco podría provocar la pérdida de datos o daños en la base de datos si no se resuelve.</span><span class="sxs-lookup"><span data-stu-id="7eea0-122">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem, but the disk problem could cause data loss or database corruption if it is not resolved.</span></span> <span data-ttu-id="7eea0-123">El registro de eventos del sistema puede contener eventos relacionados que ayuden a diagnosticar el problema.</span><span class="sxs-lookup"><span data-stu-id="7eea0-123">The system event log may contain related events that help to diagnose the problem.</span></span> <span data-ttu-id="7eea0-124">Para obtener más información sobre los errores de E/S, vea el [capítulo 2 del documento sobre conceptos básicos de E/S de Microsoft SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="7eea0-124">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7eea0-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7eea0-125">User Action</span></span>  
 <span data-ttu-id="7eea0-126">Las siguientes acciones pueden ayudarle a identificar y resolver el problema subyacente:</span><span class="sxs-lookup"><span data-stu-id="7eea0-126">The following actions may help you identify and resolve the underlying problem:</span></span>  
  
-   <span data-ttu-id="7eea0-127">Revise el registro de errores y el texto variable de este mensaje para obtener pistas que expliquen el problema.</span><span class="sxs-lookup"><span data-stu-id="7eea0-127">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="7eea0-128">Compruebe su sistema de disco.</span><span class="sxs-lookup"><span data-stu-id="7eea0-128">Check your disk system.</span></span> <span data-ttu-id="7eea0-129">El problema podría estar relacionado con discos, controladores de discos, tarjetas de matriz o unidades de disco.</span><span class="sxs-lookup"><span data-stu-id="7eea0-129">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="7eea0-130">Póngase en contacto con el fabricante del disco para obtener las utilidades más recientes a fin de comprobar el estado del sistema de disco.</span><span class="sxs-lookup"><span data-stu-id="7eea0-130">Contact the disk manufacturer for the latest utilities for checking the status of your disk system.</span></span>  
  
-   <span data-ttu-id="7eea0-131">Póngase en contacto con el fabricante del disco para obtener las últimas actualizaciones del controlador.</span><span class="sxs-lookup"><span data-stu-id="7eea0-131">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
  
