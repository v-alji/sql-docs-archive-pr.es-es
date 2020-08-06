---
title: MSSQLSERVER_9003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6f67e4184ea54be6bcd5c2a74d3c0e0711b702f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674843"
---
# <a name="mssqlserver_9003"></a><span data-ttu-id="cd124-102">MSSQLSERVER_9003</span><span class="sxs-lookup"><span data-stu-id="cd124-102">MSSQLSERVER_9003</span></span>
    
## <a name="details"></a><span data-ttu-id="cd124-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cd124-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd124-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="cd124-104">Product Name</span></span>|<span data-ttu-id="cd124-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd124-105">SQL Server</span></span>|  
|<span data-ttu-id="cd124-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cd124-106">Event ID</span></span>|<span data-ttu-id="cd124-107">9003</span><span class="sxs-lookup"><span data-stu-id="cd124-107">9003</span></span>|  
|<span data-ttu-id="cd124-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="cd124-108">Event Source</span></span>|<span data-ttu-id="cd124-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cd124-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cd124-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cd124-110">Component</span></span>|<span data-ttu-id="cd124-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cd124-111">SQLEngine</span></span>|  
|<span data-ttu-id="cd124-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cd124-112">Symbolic Name</span></span>|<span data-ttu-id="cd124-113">LOG_INVALID_LSN</span><span class="sxs-lookup"><span data-stu-id="cd124-113">LOG_INVALID_LSN</span></span>|  
|<span data-ttu-id="cd124-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cd124-114">Message Text</span></span>|<span data-ttu-id="cd124-115">El número de examen del registro %S_LSN pasado al examen del registro de la base de datos '%.\*ls' no es válido.</span><span class="sxs-lookup"><span data-stu-id="cd124-115">The log scan number %S_LSN passed to log scan in database '%.\*ls' is not valid.</span></span> <span data-ttu-id="cd124-116">This error may indicate data corruption or that the log file (.ldf) does not match the data file (.mdf).</span><span class="sxs-lookup"><span data-stu-id="cd124-116">This error may indicate data corruption or that the log file (.ldf) does not match the data file (.mdf).</span></span> <span data-ttu-id="cd124-117">If this error occurred during replication, re-create the publication.</span><span class="sxs-lookup"><span data-stu-id="cd124-117">If this error occurred during replication, re-create the publication.</span></span> <span data-ttu-id="cd124-118">De lo contrario, restaure la base de datos a partir de una copia de seguridad si el problema da lugar a un error durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="cd124-118">Otherwise, restore from backup if the problem results in a failure during startup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cd124-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="cd124-119">Explanation</span></span>  
 <span data-ttu-id="cd124-120">Un componente pasó un número de flujo de registro no válido al administrador de registros para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd124-120">A component passed an invalid log sequence number to the log manager for the database.</span></span> <span data-ttu-id="cd124-121">Podría corresponder a la replicación, a daños o a una incoherencia entre el archivo de datos principal y el registro.</span><span class="sxs-lookup"><span data-stu-id="cd124-121">This could be replication, corruption, or an inconsistency between the primary data file and the log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd124-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cd124-122">User Action</span></span>  
 <span data-ttu-id="cd124-123">Si esto ocurrió durante la replicación, vuelva a crear la publicación.</span><span class="sxs-lookup"><span data-stu-id="cd124-123">If this occurred during replication, recreate the publication.</span></span> <span data-ttu-id="cd124-124">De lo contrario, restaure una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cd124-124">Otherwise, restore from backup.</span></span>  
  
  
