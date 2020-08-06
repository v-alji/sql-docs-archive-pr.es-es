---
title: MSSQLSERVER_617 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88e9feb7c3ac5d8cf646d2243319b2b160b7757e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746997"
---
# <a name="mssqlserver_617"></a><span data-ttu-id="46ce8-102">MSSQLSERVER_617</span><span class="sxs-lookup"><span data-stu-id="46ce8-102">MSSQLSERVER_617</span></span>
    
## <a name="details"></a><span data-ttu-id="46ce8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="46ce8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46ce8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="46ce8-104">Product Name</span></span>|<span data-ttu-id="46ce8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46ce8-105">SQL Server</span></span>|  
|<span data-ttu-id="46ce8-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="46ce8-106">Event ID</span></span>|<span data-ttu-id="46ce8-107">617</span><span class="sxs-lookup"><span data-stu-id="46ce8-107">617</span></span>|  
|<span data-ttu-id="46ce8-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="46ce8-108">Event Source</span></span>|<span data-ttu-id="46ce8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46ce8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46ce8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="46ce8-110">Component</span></span>|<span data-ttu-id="46ce8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46ce8-111">SQLEngine</span></span>|  
|<span data-ttu-id="46ce8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="46ce8-112">Symbolic Name</span></span>|<span data-ttu-id="46ce8-113">NODESHASH</span><span class="sxs-lookup"><span data-stu-id="46ce8-113">NODESHASH</span></span>|  
|<span data-ttu-id="46ce8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="46ce8-114">Message Text</span></span>|<span data-ttu-id="46ce8-115">No se encontró el descriptor del id. de objeto %ld del id. de base de datos %d en la tabla hash al intentar deshacer el hash.</span><span class="sxs-lookup"><span data-stu-id="46ce8-115">Descriptor for object ID %ld in database ID %d not found in the hash table during attempt to unhash it.</span></span> <span data-ttu-id="46ce8-116">Falta una entrada en una tabla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="46ce8-116">A work table is missing an entry.</span></span> <span data-ttu-id="46ce8-117">Vuelva a ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="46ce8-117">Rerun the query.</span></span> <span data-ttu-id="46ce8-118">Si hay un cursor en el proceso, ciérrelo y vuelva a abrirlo.</span><span class="sxs-lookup"><span data-stu-id="46ce8-118">If a cursor is involved, close and reopen the cursor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46ce8-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="46ce8-119">Explanation</span></span>  
 <span data-ttu-id="46ce8-120">SQL Server no puede encontrar la tabla de trabajo para una entrada concreta.</span><span class="sxs-lookup"><span data-stu-id="46ce8-120">SQL Server cannot locate the work table for a specific entry.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46ce8-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="46ce8-121">User Action</span></span>  
  
1.  <span data-ttu-id="46ce8-122">Si hay un cursor en el proceso, ciérrelo y vuelve a abrirlo.</span><span class="sxs-lookup"><span data-stu-id="46ce8-122">If a cursor is involved, close the cursor and re-open the cursor.</span></span>  
  
2.  <span data-ttu-id="46ce8-123">Ejecute de nuevo la consulta.</span><span class="sxs-lookup"><span data-stu-id="46ce8-123">Run the query again.</span></span>  
  
  
