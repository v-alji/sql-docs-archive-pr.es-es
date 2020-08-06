---
title: MSSQLSERVER_7911 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7911 (Database Engine error)
ms.assetid: dd8390f3-0f77-4fb2-ba94-631a56e42bc6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d37ce2dc11f231e8a6f8ae6cc8b95d8b2f87c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672993"
---
# <a name="mssqlserver_7911"></a><span data-ttu-id="7b7e4-102">MSSQLSERVER_7911</span><span class="sxs-lookup"><span data-stu-id="7b7e4-102">MSSQLSERVER_7911</span></span>
    
## <a name="details"></a><span data-ttu-id="7b7e4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b7e4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b7e4-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7b7e4-104">Product Name</span></span>|<span data-ttu-id="7b7e4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b7e4-105">SQL Server</span></span>|  
|<span data-ttu-id="7b7e4-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7b7e4-106">Event ID</span></span>|<span data-ttu-id="7b7e4-107">7911</span><span class="sxs-lookup"><span data-stu-id="7b7e4-107">7911</span></span>|  
|<span data-ttu-id="7b7e4-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7b7e4-108">Event Source</span></span>|<span data-ttu-id="7b7e4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7b7e4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7b7e4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7b7e4-110">Component</span></span>|<span data-ttu-id="7b7e4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7b7e4-111">SQLEngine</span></span>|  
|<span data-ttu-id="7b7e4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7b7e4-112">Symbolic Name</span></span>|<span data-ttu-id="7b7e4-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span><span class="sxs-lookup"><span data-stu-id="7b7e4-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span></span>|  
|<span data-ttu-id="7b7e4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7b7e4-114">Message Text</span></span>|<span data-ttu-id="7b7e4-115">Reparación: se ha cancelado la asignación de la página P_ID del id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="7b7e4-115">Repair: The page P_ID has been deallocated from object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b7e4-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7b7e4-116">Explanation</span></span>  
 <span data-ttu-id="7b7e4-117">Se trata de un mensaje informativo de REPAIR en el que se indica que se ha cancelado la asignación de una página de la matriz de espacios asignados en una página IAM (Mapa de asignación de índices).</span><span class="sxs-lookup"><span data-stu-id="7b7e4-117">This is an informational message from REPAIR that states that a page has been deallocated from the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b7e4-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7b7e4-118">User Action</span></span>  
 <span data-ttu-id="7b7e4-119">None</span><span class="sxs-lookup"><span data-stu-id="7b7e4-119">None</span></span>  
  
  
