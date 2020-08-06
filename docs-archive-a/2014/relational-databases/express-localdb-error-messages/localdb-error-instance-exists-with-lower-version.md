---
title: LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa6db2af138bb2aeefb1a922e55db56c4ea821f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752186"
---
# <a name="localdb_error_instance_exists_with_lower_version"></a><span data-ttu-id="e0163-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="e0163-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>
    
## <a name="details"></a><span data-ttu-id="e0163-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e0163-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0163-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e0163-104">Product Name</span></span>|<span data-ttu-id="e0163-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e0163-105">SQL Server</span></span>|  
|<span data-ttu-id="e0163-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e0163-106">Event ID</span></span>|<span data-ttu-id="e0163-107">258</span><span class="sxs-lookup"><span data-stu-id="e0163-107">258</span></span>|  
|<span data-ttu-id="e0163-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e0163-108">Event Source</span></span>|<span data-ttu-id="e0163-109">SQL Server Local Database Runtime 12.0</span><span class="sxs-lookup"><span data-stu-id="e0163-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="e0163-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e0163-110">Component</span></span>|<span data-ttu-id="e0163-111">API de Local Database Runtime</span><span class="sxs-lookup"><span data-stu-id="e0163-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="e0163-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e0163-112">Message Text</span></span>|<span data-ttu-id="e0163-113">No se puede crear la instancia de Local Database con la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="e0163-113">Unable to create the Local Database instance with specified version.</span></span> <span data-ttu-id="e0163-114">Ya existe una instancia con el mismo nombre, pero tiene una versión anterior a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="e0163-114">An instance with the same name already exists, but it has lower version than the specified version.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e0163-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e0163-115">Explanation</span></span>  
 <span data-ttu-id="e0163-116">La instancia especificada ya existe pero la versión es anterior a la solicitada.</span><span class="sxs-lookup"><span data-stu-id="e0163-116">The specified instance already exists but its version is lower than requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0163-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e0163-117">User Action</span></span>  
 <span data-ttu-id="e0163-118">Elimine la instancia existente e intente de nuevo la operación.</span><span class="sxs-lookup"><span data-stu-id="e0163-118">Delete the existing instance and retry the operation.</span></span>  
  
  
