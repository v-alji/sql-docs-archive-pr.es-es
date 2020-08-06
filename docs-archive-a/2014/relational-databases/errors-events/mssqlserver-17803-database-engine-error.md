---
title: MSSQLSERVER_17803 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17803 (Database Engine error)
ms.assetid: 28591a19-258d-4891-b78a-4686789bb2d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be63b3d05bff2ebf90122f66af4297d77376fce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675924"
---
# <a name="mssqlserver_17803"></a><span data-ttu-id="bbf32-102">MSSQLSERVER_17803</span><span class="sxs-lookup"><span data-stu-id="bbf32-102">MSSQLSERVER_17803</span></span>
    
## <a name="details"></a><span data-ttu-id="bbf32-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bbf32-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbf32-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="bbf32-104">Product Name</span></span>|<span data-ttu-id="bbf32-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbf32-105">SQL Server</span></span>|  
|<span data-ttu-id="bbf32-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="bbf32-106">Event ID</span></span>|<span data-ttu-id="bbf32-107">17803</span><span class="sxs-lookup"><span data-stu-id="bbf32-107">17803</span></span>|  
|<span data-ttu-id="bbf32-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="bbf32-108">Event Source</span></span>|<span data-ttu-id="bbf32-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bbf32-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bbf32-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bbf32-110">Component</span></span>|<span data-ttu-id="bbf32-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bbf32-111">SQLEngine</span></span>|  
|<span data-ttu-id="bbf32-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bbf32-112">Symbolic Name</span></span>|<span data-ttu-id="bbf32-113">SRV_NOMEMORY</span><span class="sxs-lookup"><span data-stu-id="bbf32-113">SRV_NOMEMORY</span></span>|  
|<span data-ttu-id="bbf32-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bbf32-114">Message Text</span></span>|<span data-ttu-id="bbf32-115">Error de asignación de memoria durante el establecimiento de la conexión.</span><span class="sxs-lookup"><span data-stu-id="bbf32-115">There was a memory allocation failure during connection establishment.</span></span> <span data-ttu-id="bbf32-116">Reduzca la carga de memoria no esencial o aumente la memoria del sistema.</span><span class="sxs-lookup"><span data-stu-id="bbf32-116">Reduce nonessential memory load, or increase system memory.</span></span> <span data-ttu-id="bbf32-117">Se cerró la conexión.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="bbf32-117">The connection has been closed.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bbf32-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="bbf32-118">Explanation</span></span>  
 <span data-ttu-id="bbf32-119">El servidor se está quedando sin memoria.</span><span class="sxs-lookup"><span data-stu-id="bbf32-119">Server is running out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bbf32-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bbf32-120">User Action</span></span>  
 <span data-ttu-id="bbf32-121">Determine la causa por la que el servidor se está quedando sin memoria.</span><span class="sxs-lookup"><span data-stu-id="bbf32-121">Determine the cause for server running out of memory.</span></span> <span data-ttu-id="bbf32-122">Puede ser útil seguir un procedimiento para solucionar problemas genéricos de memoria</span><span class="sxs-lookup"><span data-stu-id="bbf32-122">Generic memory troubleshooting steps may be useful</span></span>  
  
  
