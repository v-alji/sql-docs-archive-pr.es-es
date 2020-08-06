---
title: MSSQLSERVER_3413 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3413 (Database Engine error)
ms.assetid: 3fa07637-ba93-4633-aaf2-ade7d18bc487
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a5d59ea61cff7051c3e1163a463c29443c553923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675897"
---
# <a name="mssqlserver_3413"></a><span data-ttu-id="60972-102">MSSQLSERVER_3413</span><span class="sxs-lookup"><span data-stu-id="60972-102">MSSQLSERVER_3413</span></span>
    
## <a name="details"></a><span data-ttu-id="60972-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="60972-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60972-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="60972-104">Product Name</span></span>|<span data-ttu-id="60972-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="60972-105">SQL Server</span></span>|  
|<span data-ttu-id="60972-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="60972-106">Event ID</span></span>|<span data-ttu-id="60972-107">3413</span><span class="sxs-lookup"><span data-stu-id="60972-107">3413</span></span>|  
|<span data-ttu-id="60972-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="60972-108">Event Source</span></span>|<span data-ttu-id="60972-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60972-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60972-110">Componente</span><span class="sxs-lookup"><span data-stu-id="60972-110">Component</span></span>|<span data-ttu-id="60972-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="60972-111">SQLEngine</span></span>|  
|<span data-ttu-id="60972-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="60972-112">Symbolic Name</span></span>|<span data-ttu-id="60972-113">MARKDB</span><span class="sxs-lookup"><span data-stu-id="60972-113">MARKDB</span></span>|  
|<span data-ttu-id="60972-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="60972-114">Message Text</span></span>|<span data-ttu-id="60972-115">Id. de base de datos %d.</span><span class="sxs-lookup"><span data-stu-id="60972-115">Database ID %d.</span></span> <span data-ttu-id="60972-116">No se pudo marcar la base de datos como sospechosa.</span><span class="sxs-lookup"><span data-stu-id="60972-116">Could not mark database as suspect.</span></span> <span data-ttu-id="60972-117">Error del recorrido con Getnext NC en sys.databases.database_id.</span><span class="sxs-lookup"><span data-stu-id="60972-117">Getnext NC scan on sys.databases.database_id failed.</span></span> <span data-ttu-id="60972-118">Consulte los errores anteriores del registro de errores para identificar la causa y corregir cualquier problema relacionado.</span><span class="sxs-lookup"><span data-stu-id="60972-118">Refer to previous errors in the error log to identify the cause and correct any associated problems.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60972-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="60972-119">Explanation</span></span>  
 <span data-ttu-id="60972-120">Se produjo un error inesperado al intentar marcar una base de datos de usuario como SUSPECT en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="60972-120">There was an unexpected failure while trying to mark a user database as SUSPECT in the catalog.</span></span> <span data-ttu-id="60972-121">El estado SUSPECT no será persistente.</span><span class="sxs-lookup"><span data-stu-id="60972-121">The SUSPECT state will not be persisted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60972-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="60972-122">User Action</span></span>  
 <span data-ttu-id="60972-123">Vea los errores anteriores y solucione el problema.</span><span class="sxs-lookup"><span data-stu-id="60972-123">See previous errors and correct the problem.</span></span>  
  
  
