---
title: MSSQLSERVER_2518 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2518 (Database Engine error)
ms.assetid: 54a13abc-4c33-43f0-b55d-e2e74a1381c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5f5517458c1014d7830c4813b95e1120bef452e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671082"
---
# <a name="mssqlserver_2518"></a><span data-ttu-id="880d8-102">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="880d8-102">MSSQLSERVER_2518</span></span>
    
## <a name="details"></a><span data-ttu-id="880d8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="880d8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="880d8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="880d8-104">Product Name</span></span>|<span data-ttu-id="880d8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="880d8-105">SQL Server</span></span>|  
|<span data-ttu-id="880d8-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="880d8-106">Event ID</span></span>|<span data-ttu-id="880d8-107">2518</span><span class="sxs-lookup"><span data-stu-id="880d8-107">2518</span></span>|  
|<span data-ttu-id="880d8-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="880d8-108">Event Source</span></span>|<span data-ttu-id="880d8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="880d8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="880d8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="880d8-110">Component</span></span>|<span data-ttu-id="880d8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="880d8-111">SQLEngine</span></span>|  
|<span data-ttu-id="880d8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="880d8-112">Symbolic Name</span></span>|<span data-ttu-id="880d8-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span><span class="sxs-lookup"><span data-stu-id="880d8-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span></span>|  
|<span data-ttu-id="880d8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="880d8-114">Message Text</span></span>|<span data-ttu-id="880d8-115">Id. de objeto O_ID (objeto "O_NAME"): no es posible comprobar las columnas calculadas y los tipos definidos por el usuario para este objeto porque el entorno Common Language Runtime (CLR) está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="880d8-115">Object ID O_ID (object "O_NAME"): Computed columns and user-defined types cannot be checked for this object because the common language runtime (CLR) is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="880d8-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="880d8-116">Explanation</span></span>  
 <span data-ttu-id="880d8-117">Este mensaje informativo indica que el procesador de consultas no pudo proporcionar a DBCC un objeto interno para permitir la evaluación de las columnas calculadas y los tipos definidos por el usuario CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="880d8-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for computed columns and common language runtime (CLR) user-defined types to be evaluated.</span></span> <span data-ttu-id="880d8-118">Este problema se produjo porque una de las columnas utilizaba el CLR, pero éste no estaba habilitado.</span><span class="sxs-lookup"><span data-stu-id="880d8-118">This problem occurred because one of the columns involved the CLR, but the CLR is not enabled.</span></span> <span data-ttu-id="880d8-119">El objeto interno cubre todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="880d8-119">The internal object covers all columns.</span></span> <span data-ttu-id="880d8-120">Por tanto, la imposibilidad de evaluar una sola columna evita que se cree el objeto interno.</span><span class="sxs-lookup"><span data-stu-id="880d8-120">Therefore, the inability to evaluate a single column prevents creating the internal object.</span></span> <span data-ttu-id="880d8-121">Esto significa que no se comprobará si las columnas calculadas son correctas o que no se usarán cuando DBCC compruebe la coherencia entre índices y tablas base.</span><span class="sxs-lookup"><span data-stu-id="880d8-121">This means that computed columns will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="880d8-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="880d8-122">User Action</span></span>  
 <span data-ttu-id="880d8-123">Habilite el CLR y vuelva a ejecutar la instrucción DBCC.</span><span class="sxs-lookup"><span data-stu-id="880d8-123">Enable CLR and rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="880d8-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="880d8-124">See Also</span></span>  
 [<span data-ttu-id="880d8-125">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="880d8-125">Enabling CLR Integration</span></span>](../clr-integration/clr-integration-enabling.md)  
  
  
