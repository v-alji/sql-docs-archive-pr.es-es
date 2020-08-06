---
title: MSSQLSERVER_8710 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65fb6b3efb42c282347f560353a2b21edc337859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678202"
---
# <a name="mssqlserver_8710"></a><span data-ttu-id="73e56-102">MSSQLSERVER_8710</span><span class="sxs-lookup"><span data-stu-id="73e56-102">MSSQLSERVER_8710</span></span>
    
## <a name="details"></a><span data-ttu-id="73e56-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="73e56-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73e56-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="73e56-104">Product Name</span></span>|<span data-ttu-id="73e56-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="73e56-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="73e56-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="73e56-106">Event ID</span></span>|<span data-ttu-id="73e56-107">8710</span><span class="sxs-lookup"><span data-stu-id="73e56-107">8710</span></span>|  
|<span data-ttu-id="73e56-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="73e56-108">Event Source</span></span>|<span data-ttu-id="73e56-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="73e56-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="73e56-110">Componente</span><span class="sxs-lookup"><span data-stu-id="73e56-110">Component</span></span>|<span data-ttu-id="73e56-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="73e56-111">SQLEngine</span></span>|  
|<span data-ttu-id="73e56-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="73e56-112">Symbolic Name</span></span>|<span data-ttu-id="73e56-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span><span class="sxs-lookup"><span data-stu-id="73e56-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span></span>|  
|<span data-ttu-id="73e56-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="73e56-114">Message Text</span></span>|<span data-ttu-id="73e56-115">Las funciones de agregado que se utilizan con consultas CUBE, ROLLUP o GROUPING SET se deben proporcionar para la combinación de subagregados.</span><span class="sxs-lookup"><span data-stu-id="73e56-115">Aggregate functions that are used with CUBE, ROLLUP, or GROUPING SET queries must provide for the merging of subaggregates.</span></span> <span data-ttu-id="73e56-116">Para solucionar este problema, quite la función de agregado o escriba la consulta utilizando UNION ALL en cláusulas GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="73e56-116">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="73e56-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="73e56-117">Explanation</span></span>  
 <span data-ttu-id="73e56-118">Se ha usado una función de agregado con CUBE, ROLLUP o GROUPING SETS que no proporciona un método para combinar subagregados.</span><span class="sxs-lookup"><span data-stu-id="73e56-118">An aggregate function has been used with CUBE, ROLLUP, or GROUPING SETS that does not provide a method for merging subaggregates.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73e56-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="73e56-119">User Action</span></span>  
 <span data-ttu-id="73e56-120">Para solucionar este problema, quite la función de agregado o escriba la consulta utilizando UNION ALL en cláusulas GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="73e56-120">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>  
  
  
