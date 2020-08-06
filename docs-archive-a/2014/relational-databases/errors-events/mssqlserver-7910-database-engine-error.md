---
title: MSSQLSERVER_7910 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7910 (Database Engine error)
ms.assetid: 017a0113-2b17-40b3-a419-30bbc43d46b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e7cca3f6973374ae7aeaa959a0b31207a1258e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672995"
---
# <a name="mssqlserver_7910"></a><span data-ttu-id="612e7-102">MSSQLSERVER_7910</span><span class="sxs-lookup"><span data-stu-id="612e7-102">MSSQLSERVER_7910</span></span>
    
## <a name="details"></a><span data-ttu-id="612e7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="612e7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="612e7-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="612e7-104">Product Name</span></span>|<span data-ttu-id="612e7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="612e7-105">SQL Server</span></span>|  
|<span data-ttu-id="612e7-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="612e7-106">Event ID</span></span>|<span data-ttu-id="612e7-107">7910</span><span class="sxs-lookup"><span data-stu-id="612e7-107">7910</span></span>|  
|<span data-ttu-id="612e7-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="612e7-108">Event Source</span></span>|<span data-ttu-id="612e7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="612e7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="612e7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="612e7-110">Component</span></span>|<span data-ttu-id="612e7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="612e7-111">SQLEngine</span></span>|  
|<span data-ttu-id="612e7-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="612e7-112">Symbolic Name</span></span>|<span data-ttu-id="612e7-113">DBCC2_REPAIR_PAGE_ALLOCATED</span><span class="sxs-lookup"><span data-stu-id="612e7-113">DBCC2_REPAIR_PAGE_ALLOCATED</span></span>|  
|<span data-ttu-id="612e7-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="612e7-114">Message Text</span></span>|<span data-ttu-id="612e7-115">Reparación: se ha asignado la página P_ID al id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="612e7-115">Repair: The page P_ID has been allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="612e7-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="612e7-116">Explanation</span></span>  
 <span data-ttu-id="612e7-117">Se trata de un mensaje informativo de REPAIR que indica que se ha asignado una página a la matriz de espacios asignados en una página IAM (Mapa de asignación de índices).</span><span class="sxs-lookup"><span data-stu-id="612e7-117">This is an informational message from REPAIR that states that a page has been allocated to the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="612e7-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="612e7-118">User Action</span></span>  
 <span data-ttu-id="612e7-119">None</span><span class="sxs-lookup"><span data-stu-id="612e7-119">None</span></span>  
  
  
