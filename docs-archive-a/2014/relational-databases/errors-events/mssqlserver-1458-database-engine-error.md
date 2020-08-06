---
title: MSSQLSERVER_1458 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1458 (Database Engine error)
ms.assetid: adc78c59-a6f2-432b-9a07-fdd1dc2b9026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efa45177a92402b25099be5bb3e3dcc91a5fa6d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675946"
---
# <a name="mssqlserver_1458"></a><span data-ttu-id="ef443-102">MSSQLSERVER_1458</span><span class="sxs-lookup"><span data-stu-id="ef443-102">MSSQLSERVER_1458</span></span>
    
## <a name="details"></a><span data-ttu-id="ef443-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ef443-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef443-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ef443-104">Product Name</span></span>|<span data-ttu-id="ef443-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef443-105">SQL Server</span></span>|  
|<span data-ttu-id="ef443-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ef443-106">Event ID</span></span>|<span data-ttu-id="ef443-107">1458</span><span class="sxs-lookup"><span data-stu-id="ef443-107">1458</span></span>|  
|<span data-ttu-id="ef443-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ef443-108">Event Source</span></span>|<span data-ttu-id="ef443-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ef443-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ef443-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ef443-110">Component</span></span>|<span data-ttu-id="ef443-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ef443-111">SQLEngine</span></span>|  
|<span data-ttu-id="ef443-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ef443-112">Symbolic Name</span></span>|<span data-ttu-id="ef443-113">DBM_FAILREDO_ON_PRIMARY</span><span class="sxs-lookup"><span data-stu-id="ef443-113">DBM_FAILREDO_ON_PRIMARY</span></span>|  
|<span data-ttu-id="ef443-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ef443-114">Message Text</span></span>|<span data-ttu-id="ef443-115">La copia principal de la base de datos '%.\*ls' encontró el error %d, el estado %d y la gravedad %d.</span><span class="sxs-lookup"><span data-stu-id="ef443-115">The principal copy of the '%.\*ls' database encountered error %d, status %d, severity %d.</span></span> <span data-ttu-id="ef443-116">Se suspendió la creación de reflejos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef443-116">Database mirroring has been suspended.</span></span> <span data-ttu-id="ef443-117">Intente resolver la condición de error y reanude la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="ef443-117">Try to resolve the error condition, and resume mirroring.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ef443-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="ef443-118">Explanation</span></span>  
 <span data-ttu-id="ef443-119">Este mensaje indica que la base de datos principal encontró un error que ocasionó la suspensión de la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef443-119">This messages indicates that the principal database encountered an error that caused database mirroring to be suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef443-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ef443-120">User Action</span></span>  
 <span data-ttu-id="ef443-121">En la mayoría de los casos, este error se corrige automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ef443-121">Most cases of this error are self correcting.</span></span> <span data-ttu-id="ef443-122">Si el problema continúa, el reinicio de la instancia de la base de datos o del servidor normalmente corrige el problema.</span><span class="sxs-lookup"><span data-stu-id="ef443-122">If the problem persists, restarting the database or server instance typically corrects the problem.</span></span> <span data-ttu-id="ef443-123">Para obtener más información, busque el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de cada asociado para el error asociado que precedía a este mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef443-123">For more information, look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on each partner for the associated error that preceded this message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef443-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef443-124">See Also</span></span>  
 [<span data-ttu-id="ef443-125">Supervisar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ef443-125">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
