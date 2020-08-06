---
title: MSSQLSERVER_12304 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12304 (Database Engine error)
ms.assetid: a2c252c2-e815-4ac8-a101-7af5b32e3233
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2347fc46fe5ab83ef2ff46b81500cd737ed02d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674154"
---
# <a name="mssqlserver_12304"></a><span data-ttu-id="0bf97-102">MSSQLSERVER_12304</span><span class="sxs-lookup"><span data-stu-id="0bf97-102">MSSQLSERVER_12304</span></span>
    
## <a name="details"></a><span data-ttu-id="0bf97-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0bf97-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bf97-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="0bf97-104">Product Name</span></span>|<span data-ttu-id="0bf97-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bf97-105">SQL Server</span></span>|  
|<span data-ttu-id="0bf97-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="0bf97-106">Event ID</span></span>|<span data-ttu-id="0bf97-107">12304</span><span class="sxs-lookup"><span data-stu-id="0bf97-107">12304</span></span>|  
|<span data-ttu-id="0bf97-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="0bf97-108">Event Source</span></span>|<span data-ttu-id="0bf97-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0bf97-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0bf97-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0bf97-110">Component</span></span>|<span data-ttu-id="0bf97-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0bf97-111">SQLEngine</span></span>|  
|<span data-ttu-id="0bf97-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0bf97-112">Symbolic Name</span></span>|<span data-ttu-id="0bf97-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span><span class="sxs-lookup"><span data-stu-id="0bf97-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span></span>|  
|<span data-ttu-id="0bf97-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0bf97-114">Message Text</span></span>|<span data-ttu-id="0bf97-115">No se admite el uso de una tabla optimizada de memoria que utiliza la propiedad IDENTITY con ninguna de sus columnas cuando se usa el tipo fuera del contexto de un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="0bf97-115">Using a memory optimized table type that uses the IDENTITY property with any of its columns is not supported when using the type outside the context of a natively compiled stored procedure.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="0bf97-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0bf97-116">User Action</span></span>  
 <span data-ttu-id="0bf97-117">No utilice un tipo de tabla optimizada de memoria que utilice la propiedad de identidad con ninguna de sus columnas.</span><span class="sxs-lookup"><span data-stu-id="0bf97-117">Do not use a memory-optimized table type that uses the identity property with any of its columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf97-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bf97-118">See Also</span></span>  
 [<span data-ttu-id="0bf97-119">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="0bf97-119">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
