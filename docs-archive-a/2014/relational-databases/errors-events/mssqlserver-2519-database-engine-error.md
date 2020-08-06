---
title: MSSQLSERVER_2519 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2519 (Database Engine error)
ms.assetid: 8dc6ad98-5db8-4c88-8dea-6d455e63b839
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8577b07586553f4b03714cd31451ac755faf824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662995"
---
# <a name="mssqlserver_2519"></a><span data-ttu-id="a4ed3-102">MSSQLSERVER_2519</span><span class="sxs-lookup"><span data-stu-id="a4ed3-102">MSSQLSERVER_2519</span></span>
    
## <a name="details"></a><span data-ttu-id="a4ed3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a4ed3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a4ed3-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a4ed3-104">Product Name</span></span>|<span data-ttu-id="a4ed3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4ed3-105">SQL Server</span></span>|  
|<span data-ttu-id="a4ed3-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a4ed3-106">Event ID</span></span>|<span data-ttu-id="a4ed3-107">2519</span><span class="sxs-lookup"><span data-stu-id="a4ed3-107">2519</span></span>|  
|<span data-ttu-id="a4ed3-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a4ed3-108">Event Source</span></span>|<span data-ttu-id="a4ed3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a4ed3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a4ed3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a4ed3-110">Component</span></span>|<span data-ttu-id="a4ed3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a4ed3-111">SQLEngine</span></span>|  
|<span data-ttu-id="a4ed3-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a4ed3-112">Symbolic Name</span></span>|<span data-ttu-id="a4ed3-113">DBCC_NO_EXPRESSION_EVALUATOR</span><span class="sxs-lookup"><span data-stu-id="a4ed3-113">DBCC_NO_EXPRESSION_EVALUATOR</span></span>|  
|<span data-ttu-id="a4ed3-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a4ed3-114">Message Text</span></span>|<span data-ttu-id="a4ed3-115">Las columnas calculadas y los tipos definidos por el usuario no se pueden comprobar para el Id. de objeto O_ID (objeto "O_NAME") porque el evaluador interno de expresiones no se pudo inicializar.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-115">Computed columns and user-defined types cannot be checked for object ID O_ID (object "O_NAME") because the internal expression evaluator could not be initialized.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a4ed3-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a4ed3-116">Explanation</span></span>  
 <span data-ttu-id="a4ed3-117">Este mensaje informativo indica que el procesador de consultas no pudo proporcionar a DBCC un objeto interno para permitir la evaluación de columnas calculadas y tipos definidos por el usuario CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="a4ed3-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for the evaluation of computed columns and common language runtime (CLR) user-defined types.</span></span> <span data-ttu-id="a4ed3-118">Como consecuencia, no se comprobará si las columnas calculadas y los tipos definidos por el usuario CLR son correctos ni se utilizarán cuando DBCC compruebe la coherencia entre los índices y las tablas base.</span><span class="sxs-lookup"><span data-stu-id="a4ed3-118">This means that computed columns and CLR user-defined types will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a4ed3-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a4ed3-119">User Action</span></span>  
 <span data-ttu-id="a4ed3-120">None</span><span class="sxs-lookup"><span data-stu-id="a4ed3-120">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ed3-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4ed3-121">See Also</span></span>  
 [<span data-ttu-id="a4ed3-122">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="a4ed3-122">MSSQLSERVER_2518</span></span>](mssqlserver-2518-database-engine-error.md)  
  
  
