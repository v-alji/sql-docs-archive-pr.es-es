---
title: MSSQLSERVER_7711 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e29b2ea993e8e5332ef03b05f628dc791e20aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673012"
---
# <a name="mssqlserver_7711"></a><span data-ttu-id="1606c-102">MSSQLSERVER_7711</span><span class="sxs-lookup"><span data-stu-id="1606c-102">MSSQLSERVER_7711</span></span>
    
## <a name="details"></a><span data-ttu-id="1606c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1606c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1606c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1606c-104">Product Name</span></span>|<span data-ttu-id="1606c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1606c-105">SQL Server</span></span>|  
|<span data-ttu-id="1606c-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1606c-106">Event ID</span></span>|<span data-ttu-id="1606c-107">7711</span><span class="sxs-lookup"><span data-stu-id="1606c-107">7711</span></span>|  
|<span data-ttu-id="1606c-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1606c-108">Event Source</span></span>|<span data-ttu-id="1606c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1606c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1606c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1606c-110">Component</span></span>|<span data-ttu-id="1606c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1606c-111">SQLEngine</span></span>|  
|<span data-ttu-id="1606c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1606c-112">Symbolic Name</span></span>|<span data-ttu-id="1606c-113">PRT_RANGE_OVERLAP</span><span class="sxs-lookup"><span data-stu-id="1606c-113">PRT_RANGE_OVERLAP</span></span>|  
|<span data-ttu-id="1606c-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1606c-114">Message Text</span></span>|<span data-ttu-id="1606c-115">La opción DATA_COMPRESSION se especificó más de una vez para la tabla o índice, o una de sus particiones.</span><span class="sxs-lookup"><span data-stu-id="1606c-115">The DATA_COMPRESSION option was specified more than once for the table or index or one of its partitions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1606c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1606c-116">Explanation</span></span>  
 <span data-ttu-id="1606c-117">Error en la opción DATA_COMPRESSION en una de las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1606c-117">An error occurred in the DATA_COMPRESSION option in one of the following statements:</span></span>  
  
-   <span data-ttu-id="1606c-118">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="1606c-118">CREATE TABLE</span></span>  
  
-   <span data-ttu-id="1606c-119">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="1606c-119">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="1606c-120">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="1606c-120">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="1606c-121">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="1606c-121">ALTER INDEX</span></span>  
  
 <span data-ttu-id="1606c-122">Si la tabla o índice mencionado tiene particiones, la opción DATA_COMPRESSION se enumeró más de una vez para al menos una de las particiones.</span><span class="sxs-lookup"><span data-stu-id="1606c-122">If the table or index cited is partitioned, the DATA_COMPRESSION option was listed more than one time for at least one of the partitions.</span></span> <span data-ttu-id="1606c-123">Si la tabla o índice no tiene particiones, la opción DATA_COMPRESSION se mencionó más de una vez.</span><span class="sxs-lookup"><span data-stu-id="1606c-123">If the table or index is not partitioned, the DATA_COMPRESSION option was cited more than one time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1606c-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1606c-124">User Action</span></span>  
 <span data-ttu-id="1606c-125">Para una tabla o índice con particiones, asegúrese de que la opción DATA_COMPRESSION se especifica solo una vez para cada partición.</span><span class="sxs-lookup"><span data-stu-id="1606c-125">For a partitioned table or index, make sure that the DATA_COMPRESSION option is specified only one time for each partition.</span></span> <span data-ttu-id="1606c-126">Para una tabla o índice sin particiones, utilice la opción DATA_COMPRESSION solo una vez en la instrucción.</span><span class="sxs-lookup"><span data-stu-id="1606c-126">For a table or index that is not partitioned, use the DATA_COMPRESSION option only one time in the statement.</span></span>  
  
  
