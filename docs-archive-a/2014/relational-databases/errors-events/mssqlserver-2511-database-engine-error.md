---
title: MSSQLSERVER_2511 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2511 (Database Engine error)
ms.assetid: 9a00c0ed-eb4b-4fae-8016-192396006c37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23e91b0d64140329639cf57f3a336cd2eab8e4e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745774"
---
# <a name="mssqlserver_2511"></a><span data-ttu-id="e98e6-102">MSSQLSERVER_2511</span><span class="sxs-lookup"><span data-stu-id="e98e6-102">MSSQLSERVER_2511</span></span>
    
## <a name="details"></a><span data-ttu-id="e98e6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e98e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e98e6-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e98e6-104">Product Name</span></span>|<span data-ttu-id="e98e6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e98e6-105">SQL Server</span></span>|  
|<span data-ttu-id="e98e6-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e98e6-106">Event ID</span></span>|<span data-ttu-id="e98e6-107">2511</span><span class="sxs-lookup"><span data-stu-id="e98e6-107">2511</span></span>|  
|<span data-ttu-id="e98e6-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e98e6-108">Event Source</span></span>|<span data-ttu-id="e98e6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e98e6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e98e6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e98e6-110">Component</span></span>|<span data-ttu-id="e98e6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e98e6-111">SQLEngine</span></span>|  
|<span data-ttu-id="e98e6-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e98e6-112">Symbolic Name</span></span>|<span data-ttu-id="e98e6-113">DBCC_KEYS_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="e98e6-113">DBCC_KEYS_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="e98e6-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e98e6-114">Message Text</span></span>|<span data-ttu-id="e98e6-115">Error de tabla: id. de objeto%d, id. de índice %d, id. de partición %I64d, id. de unidad de asignación %I64d (tipo %.\*ls).</span><span class="sxs-lookup"><span data-stu-id="e98e6-115">Table error: Object ID %d, index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls).</span></span> <span data-ttu-id="e98e6-116">Las claves no están ordenadas en la página %S_PGID, zonas %d y %d.</span><span class="sxs-lookup"><span data-stu-id="e98e6-116">Keys out of order on page %S_PGID, slots %d and %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e98e6-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e98e6-117">Explanation</span></span>  
 <span data-ttu-id="e98e6-118">Se detectaron claves desordenadas en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="e98e6-118">Out-of-order keys were detected in the specified index.</span></span> <span data-ttu-id="e98e6-119">La página en la que están las claves puede estar dañada.</span><span class="sxs-lookup"><span data-stu-id="e98e6-119">The page in which the keys are contained may be corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e98e6-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e98e6-120">User Action</span></span>  
 <span data-ttu-id="e98e6-121">Vuelva a generar el índice especificado usando la instrucción ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="e98e6-121">Rebuild the specified index by using the ALTER INDEX REBUILD statement.</span></span>  
  
  
