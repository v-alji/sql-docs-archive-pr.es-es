---
title: MSSQLSERVER_8621 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8621 (Database Engine error)
ms.assetid: 67f59865-becd-4999-8bb0-90aedd7effbf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48c36cf936475e3deea37a172c7dc59f88d0a31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674852"
---
# <a name="mssqlserver_8621"></a><span data-ttu-id="5b69e-102">MSSQLSERVER_8621</span><span class="sxs-lookup"><span data-stu-id="5b69e-102">MSSQLSERVER_8621</span></span>
    
## <a name="details"></a><span data-ttu-id="5b69e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b69e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b69e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5b69e-104">Product Name</span></span>|<span data-ttu-id="5b69e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b69e-105">SQL Server</span></span>|  
|<span data-ttu-id="5b69e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5b69e-106">Event ID</span></span>|<span data-ttu-id="5b69e-107">8621</span><span class="sxs-lookup"><span data-stu-id="5b69e-107">8621</span></span>|  
|<span data-ttu-id="5b69e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5b69e-108">Event Source</span></span>|<span data-ttu-id="5b69e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5b69e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5b69e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5b69e-110">Component</span></span>|<span data-ttu-id="5b69e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5b69e-111">SQLEngine</span></span>|  
|<span data-ttu-id="5b69e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5b69e-112">Symbolic Name</span></span>|<span data-ttu-id="5b69e-113">OPTIMIZER_STACK_OVERFLOW_ERR</span><span class="sxs-lookup"><span data-stu-id="5b69e-113">OPTIMIZER_STACK_OVERFLOW_ERR</span></span>|  
|<span data-ttu-id="5b69e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5b69e-114">Message Text</span></span>|<span data-ttu-id="5b69e-115">El procesador de consultas se quedó sin espacio de pila durante la optimización de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5b69e-115">The query processor ran out of stack space during query optimization.</span></span> <span data-ttu-id="5b69e-116">Simplifique la consulta.</span><span class="sxs-lookup"><span data-stu-id="5b69e-116">Please simplify the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b69e-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="5b69e-117">Explanation</span></span>  
 <span data-ttu-id="5b69e-118">La causa más probable del error es el tamaño de la consulta expandida.</span><span class="sxs-lookup"><span data-stu-id="5b69e-118">The size of the expanded query is the most likely cause of the error.</span></span> <span data-ttu-id="5b69e-119">La consulta expandida sustituye en la consulta original las definiciones de cada una de las vistas, columnas calculadas, funciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] y expresiones de tabla comunes a las que hace referencia, así como las acciones en cascada como actualizar los desencadenadores, vistas e índices secundarios.</span><span class="sxs-lookup"><span data-stu-id="5b69e-119">The expanded query substitutes into the original query the definitions of each of the views, computed columns, [!INCLUDE[tsql](../../includes/tsql-md.md)] functions, and common table expressions it references, as well as cascading actions like updating secondary indexes, views, and triggers.</span></span>  
  
 <span data-ttu-id="5b69e-120">Lo más probable es que la consulta sea grande en alguna dimensión; por ejemplo, el número de tablas al que se hace referencia en las definiciones de vista o una expresión escalar muy grande.</span><span class="sxs-lookup"><span data-stu-id="5b69e-120">Most likely the query is large in some dimension; for example, the number of tables referenced by view definitions, or a very large scalar expression.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b69e-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5b69e-121">User Action</span></span>  
 <span data-ttu-id="5b69e-122">Simplifique la consulta dividiéndola en varias a lo largo de la dimensión mayor.</span><span class="sxs-lookup"><span data-stu-id="5b69e-122">Simplify the query by breaking the query into multiple queries along the largest dimension.</span></span> <span data-ttu-id="5b69e-123">Primero quite cualquier elemento de la consulta que no sea realmente necesario y, a continuación, pruebe a agregar una tabla temporal y a dividir la consulta en dos.</span><span class="sxs-lookup"><span data-stu-id="5b69e-123">First remove any query elements that are not really necessary, then try adding a temp table and splitting the query in two.</span></span>  <span data-ttu-id="5b69e-124">No basta con mover simplemente una parte de la consulta a una subconsulta, función o expresión de tabla común porque el compilador de [!INCLUDE[tsql](../../includes/tsql-md.md)] las recombina.</span><span class="sxs-lookup"><span data-stu-id="5b69e-124">Merely moving a part of the query to a subquery, function, or common table expression is insufficient because they get recombined by the [!INCLUDE[tsql](../../includes/tsql-md.md)] compiler.</span></span>  
  
  
