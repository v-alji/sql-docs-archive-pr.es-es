---
title: MSSQLSERVER_5231 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5231 (Database Engine error)
ms.assetid: 6954ae84-ed0b-4f4c-9d0a-e73f3d71476c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 68f40ac3a566280526757bd8b83c784954ba3dde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744709"
---
# <a name="mssqlserver_5231"></a><span data-ttu-id="0ff18-102">MSSQLSERVER_5231</span><span class="sxs-lookup"><span data-stu-id="0ff18-102">MSSQLSERVER_5231</span></span>
    
## <a name="details"></a><span data-ttu-id="0ff18-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0ff18-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ff18-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="0ff18-104">Product Name</span></span>|<span data-ttu-id="0ff18-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ff18-105">SQL Server</span></span>|  
|<span data-ttu-id="0ff18-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="0ff18-106">Event ID</span></span>|<span data-ttu-id="0ff18-107">5231</span><span class="sxs-lookup"><span data-stu-id="0ff18-107">5231</span></span>|  
|<span data-ttu-id="0ff18-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="0ff18-108">Event Source</span></span>|<span data-ttu-id="0ff18-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0ff18-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0ff18-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0ff18-110">Component</span></span>|<span data-ttu-id="0ff18-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0ff18-111">SQLEngine</span></span>|  
|<span data-ttu-id="0ff18-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0ff18-112">Symbolic Name</span></span>|<span data-ttu-id="0ff18-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span><span class="sxs-lookup"><span data-stu-id="0ff18-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span></span>|  
|<span data-ttu-id="0ff18-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0ff18-114">Message Text</span></span>|<span data-ttu-id="0ff18-115">Id. de objeto O_ID (objeto "NAME"): Se ha producido un interbloqueo al intentar bloquear este objeto para la comprobación.</span><span class="sxs-lookup"><span data-stu-id="0ff18-115">Object ID O_ID (object 'NAME'): A deadlock occurred while trying to lock this object for checking.</span></span> <span data-ttu-id="0ff18-116">Este objeto ha sido omitido y no se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="0ff18-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ff18-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="0ff18-117">Explanation</span></span>  
 <span data-ttu-id="0ff18-118">Se ha producido un interbloqueo cuando DBCC intentaba bloquear el objeto; DBCC ha sido elegido como víctima del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="0ff18-118">A deadlock occurred when DBCC was trying to lock the object, and DBCC was chosen as the deadlock victim.</span></span> <span data-ttu-id="0ff18-119">El objeto no se procesará.</span><span class="sxs-lookup"><span data-stu-id="0ff18-119">The object will not be processed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ff18-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0ff18-120">User Action</span></span>  
 <span data-ttu-id="0ff18-121">None</span><span class="sxs-lookup"><span data-stu-id="0ff18-121">None</span></span>  
  
  
