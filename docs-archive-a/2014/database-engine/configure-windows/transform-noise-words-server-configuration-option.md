---
title: transform noise words (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- full-text queries [SQL Server], performance
- transform noise words option
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 69bd388e-a86c-4de4-b5d5-d093424d9c57
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 49de4a381de3e998073a73c284e3e3e5960f4921
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748894"
---
# <a name="transform-noise-words-server-configuration-option"></a><span data-ttu-id="d9fa5-102">transform noise words (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="d9fa5-102">transform noise words Server Configuration Option</span></span>
  <span data-ttu-id="d9fa5-103">Use la `transform noise words` opción de configuración del servidor para suprimir un mensaje de error si las palabras irrelevantes, es decir, [palabras irrelevantes](../../relational-databases/search/full-text-search.md), provocan que una operación booleana en una consulta de texto completo devuelva cero filas.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-103">Use the `transform noise words` server configuration option to suppress an error message if noise words, that is [stopwords](../../relational-databases/search/full-text-search.md), cause a Boolean operation on a full-text query to return zero rows.</span></span> <span data-ttu-id="d9fa5-104">Esta opción es útil para las consultas de texto completo que utilizan el predicado CONTAINS en el que las operaciones booleanas o las operaciones NEAR incluyen palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-104">This option is useful for full-text queries that use the CONTAINS predicate in which Boolean operations or NEAR operations include noise words.</span></span> <span data-ttu-id="d9fa5-105">En la siguiente tabla se describen los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-105">The possible values are described in the following table.</span></span>  
  
|<span data-ttu-id="d9fa5-106">Value</span><span class="sxs-lookup"><span data-stu-id="d9fa5-106">Value</span></span>|<span data-ttu-id="d9fa5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9fa5-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d9fa5-108">0</span><span class="sxs-lookup"><span data-stu-id="d9fa5-108">0</span></span>|<span data-ttu-id="d9fa5-109">Las palabras irrelevantes no se transforman.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-109">Noise words (or stopwords) are not transformed.</span></span> <span data-ttu-id="d9fa5-110">Cuando una consulta de texto completo contiene palabras irrelevantes, la consulta devuelve cero filas y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] produce una advertencia.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-110">When a full-text query contains noise words, the query returns zero rows, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] raises a warning.</span></span> <span data-ttu-id="d9fa5-111">Este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-111">This is the default behavior.</span></span><br /><br /> <span data-ttu-id="d9fa5-112">Tenga en cuenta que la advertencia es una advertencia en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-112">Note that the warning is a run-time warning.</span></span> <span data-ttu-id="d9fa5-113">Por lo tanto, si no se ejecuta la cláusula de texto completo de la consulta, no se generará la advertencia.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-113">Therefore, if the full-text clause in the query is not executed, the warning is not raised.</span></span> <span data-ttu-id="d9fa5-114">En una consulta local solo se generará una advertencia, incluso si existen varias cláusulas de consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-114">For a local query, only one warning is raised, even when there are multiple full-text query clauses.</span></span> <span data-ttu-id="d9fa5-115">En una consulta remota, es posible que el servidor vinculado no retransmita el error; por tanto, puede que tampoco se genere la advertencia.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-115">For a remote query, the linked server might not relay the error; therefore, the warning might not be raised.</span></span>|  
|<span data-ttu-id="d9fa5-116">1</span><span class="sxs-lookup"><span data-stu-id="d9fa5-116">1</span></span>|<span data-ttu-id="d9fa5-117">Las palabras irrelevantes se transforman.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-117">Noise words (or stopwords) are transformed.</span></span> <span data-ttu-id="d9fa5-118">Se omiten y el resto de la consulta se evalúa.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-118">They are ignored, and the rest of the query is evaluated.</span></span><br /><br /> <span data-ttu-id="d9fa5-119">Si las palabras irrelevantes se especifican en un término de proximidad, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las quita.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-119">If noise words are specified in a proximity term, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] removes them.</span></span> <span data-ttu-id="d9fa5-120">Por ejemplo, la palabra irrelevante `is` se quita de `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transformando la consulta de búsqueda en `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-120">For example, the noise word `is` is removed from `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transforming the search query into `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span></span> <span data-ttu-id="d9fa5-121">Observe que `CONTAINS(<column_name>, 'NEAR(hello,is)')` se transformaría simplemente en `CONTAINS(<column_name>, hello)` porque solo hay un término de búsqueda válido.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-121">Notice that `CONTAINS(<column_name>, 'NEAR(hello,is)')` would be transformed into simply `CONTAINS(<column_name>, hello)` because there is only one valid search term.</span></span>|  
  
## <a name="effects-of-the-transform-noise-words-setting"></a><span data-ttu-id="d9fa5-122">Efectos de la opción Transformar palabras irrelevantes</span><span class="sxs-lookup"><span data-stu-id="d9fa5-122">Effects of the transform noise words Setting</span></span>  
 <span data-ttu-id="d9fa5-123">En esta sección se muestra el comportamiento de las consultas que contienen una palabra irrelevante, "`the`", en la configuración alternativa de `transform noise words`.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-123">This section illustrates the behavior of queries containing a noise word, "`the`", under the alternate settings of `transform noise words`.</span></span>  <span data-ttu-id="d9fa5-124">Se supone que las cadenas de consulta de texto completo de ejemplo se ejecutan en una fila de tabla que contiene los datos siguientes: `[1, "The black cat"]`.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-124">The sample full-text query strings are assumed to be run against a table row containing the following data: `[1, "The black cat"]`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9fa5-125">Todos esos escenarios pueden generar una advertencia por palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-125">All such scenarios can generate a noise word warning.</span></span>  
  
-   <span data-ttu-id="d9fa5-126">Con Transformar palabras irrelevantes establecido en 0:</span><span class="sxs-lookup"><span data-stu-id="d9fa5-126">With transform noise words set to 0:</span></span>  
  
    |<span data-ttu-id="d9fa5-127">Cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="d9fa5-127">Query string</span></span>|<span data-ttu-id="d9fa5-128">Resultado</span><span class="sxs-lookup"><span data-stu-id="d9fa5-128">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="d9fa5-129">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-129">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="d9fa5-130">Sin resultados (el comportamiento es el mismo para "`the`" AND "`cat`").</span><span class="sxs-lookup"><span data-stu-id="d9fa5-130">No results (The behavior is the same for "`the`" AND "`cat`".)</span></span>|  
    |<span data-ttu-id="d9fa5-131">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-131">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="d9fa5-132">Sin resultados (el comportamiento es el mismo para "`the`" NEAR "`cat`").</span><span class="sxs-lookup"><span data-stu-id="d9fa5-132">No results (The behavior is the same for "`the`" NEAR "`cat`".)</span></span>|  
    |<span data-ttu-id="d9fa5-133">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-133">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="d9fa5-134">No hay resultados</span><span class="sxs-lookup"><span data-stu-id="d9fa5-134">No results</span></span>|  
    |<span data-ttu-id="d9fa5-135">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-135">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="d9fa5-136">No hay resultados</span><span class="sxs-lookup"><span data-stu-id="d9fa5-136">No results</span></span>|  
  
-   <span data-ttu-id="d9fa5-137">Con Transformar palabras irrelevantes establecido en 1:</span><span class="sxs-lookup"><span data-stu-id="d9fa5-137">With transform noise words set to 1:</span></span>  
  
    |<span data-ttu-id="d9fa5-138">Cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="d9fa5-138">Query string</span></span>|<span data-ttu-id="d9fa5-139">Resultado</span><span class="sxs-lookup"><span data-stu-id="d9fa5-139">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="d9fa5-140">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-140">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="d9fa5-141">Acierto para la fila con identificador 1</span><span class="sxs-lookup"><span data-stu-id="d9fa5-141">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="d9fa5-142">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-142">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="d9fa5-143">Acierto para la fila con identificador 1</span><span class="sxs-lookup"><span data-stu-id="d9fa5-143">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="d9fa5-144">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-144">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="d9fa5-145">No hay resultados</span><span class="sxs-lookup"><span data-stu-id="d9fa5-145">No results</span></span>|  
    |<span data-ttu-id="d9fa5-146">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="d9fa5-146">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="d9fa5-147">Acierto para la fila con identificador 1</span><span class="sxs-lookup"><span data-stu-id="d9fa5-147">Hit for row with ID 1</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d9fa5-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9fa5-148">Example</span></span>  
 <span data-ttu-id="d9fa5-149">En el siguiente ejemplo se establece `transform noise words` en `1`.</span><span class="sxs-lookup"><span data-stu-id="d9fa5-149">The following example sets `transform noise words` to `1`.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
GO  
sp_configure 'transform noise words', 1;  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9fa5-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9fa5-150">See Also</span></span>  
 <span data-ttu-id="d9fa5-151">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d9fa5-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="d9fa5-152">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d9fa5-152">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
