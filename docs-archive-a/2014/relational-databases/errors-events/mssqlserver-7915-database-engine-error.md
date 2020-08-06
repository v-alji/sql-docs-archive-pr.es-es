---
title: MSSQLSERVER_7915 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7915 (Database Engine error)
ms.assetid: 63338587-7dd3-40e6-b70e-d8ae18fff47b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1dc7a69023e49b48a10da9f0388cbd72fbe46be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673706"
---
# <a name="mssqlserver_7915"></a><span data-ttu-id="3c907-102">MSSQLSERVER_7915</span><span class="sxs-lookup"><span data-stu-id="3c907-102">MSSQLSERVER_7915</span></span>
    
## <a name="details"></a><span data-ttu-id="3c907-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3c907-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c907-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="3c907-104">Product Name</span></span>|<span data-ttu-id="3c907-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c907-105">SQL Server</span></span>|  
|<span data-ttu-id="3c907-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="3c907-106">Event ID</span></span>|<span data-ttu-id="3c907-107">7915</span><span class="sxs-lookup"><span data-stu-id="3c907-107">7915</span></span>|  
|<span data-ttu-id="3c907-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="3c907-108">Event Source</span></span>|<span data-ttu-id="3c907-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3c907-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3c907-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3c907-110">Component</span></span>|<span data-ttu-id="3c907-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3c907-111">SQLEngine</span></span>|  
|<span data-ttu-id="3c907-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3c907-112">Symbolic Name</span></span>|<span data-ttu-id="3c907-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span><span class="sxs-lookup"><span data-stu-id="3c907-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span></span>|  
|<span data-ttu-id="3c907-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3c907-114">Message Text</span></span>|<span data-ttu-id="3c907-115">Reparación: la cadena de IAM para el id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE), se ha truncado antes de la página P_ID y se volverá a generar.</span><span class="sxs-lookup"><span data-stu-id="3c907-115">Repair: IAM chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), has been truncated before page P_ID and will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c907-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3c907-116">Explanation</span></span>  
 <span data-ttu-id="3c907-117">Se trata de un mensaje informativo enviado por REPAIR que indica que la cadena IAM (Mapa de asignación de índices) especificada se revisó para que pudiera volver a generarse.</span><span class="sxs-lookup"><span data-stu-id="3c907-117">This is an information message sent by REPAIR that indicates that the specified Index Allocation Map (IAM) chain was patched so that it could be rebuilt.</span></span> <span data-ttu-id="3c907-118">Esta revisión puede haber necesitado de la asignación de un nuevo encabezado de la cadena IAM o de la eliminación de las páginas erróneas de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3c907-118">This patching may have required the allocation of a new head of the IAM chain or the removal of bad pages from the chain.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c907-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3c907-119">User Action</span></span>  
 <span data-ttu-id="3c907-120">None</span><span class="sxs-lookup"><span data-stu-id="3c907-120">None</span></span>  
  
  
