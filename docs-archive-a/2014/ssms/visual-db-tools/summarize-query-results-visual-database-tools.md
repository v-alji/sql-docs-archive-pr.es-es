---
title: Resumir los resultados de una consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08713be2d4439e520df07ec5efd6cb761a78a994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747852"
---
# <a name="summarize-query-results-visual-database-tools"></a><span data-ttu-id="08fdb-102">Resumir los resultados de una consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="08fdb-102">Summarize Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="08fdb-103">Al crear consultas de funciones agregadas, se aplican determinados principios lógicos.</span><span class="sxs-lookup"><span data-stu-id="08fdb-103">When you create aggregate queries, certain logical principles apply.</span></span> <span data-ttu-id="08fdb-104">Por ejemplo, no puede mostrar el contenido de filas individuales en una consulta de resumen.</span><span class="sxs-lookup"><span data-stu-id="08fdb-104">For example, you cannot display the contents of individual rows in a summary query.</span></span> <span data-ttu-id="08fdb-105">El Diseñador de consultas y vistas le ayuda a cumplir estos principios ajustándose al comportamiento del [panel Diagrama](visual-database-tools.md) y el [panel Criterios](criteria-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="08fdb-105">The Query and View Designer helps you comply with these principles in the way the [Diagram pane](visual-database-tools.md) and [Criteria pane](criteria-pane-visual-database-tools.md) behave.</span></span>  
  
 <span data-ttu-id="08fdb-106">Si comprende los principios de las consultas de funciones agregadas y el comportamiento del Diseñador de consultas y vistas, podrá crear consultas de agregado correctas en cuanto a la lógica.</span><span class="sxs-lookup"><span data-stu-id="08fdb-106">By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries.</span></span> <span data-ttu-id="08fdb-107">El principio predominante es que las consultas de agregado solo pueden producir información de resumen.</span><span class="sxs-lookup"><span data-stu-id="08fdb-107">The overriding principle is that aggregate queries can result only in summary information.</span></span> <span data-ttu-id="08fdb-108">Por tanto, la mayoría de los principios que siguen describen las formas de hacer referencia a las columnas de datos individuales dentro de una consulta de agregado.</span><span class="sxs-lookup"><span data-stu-id="08fdb-108">Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08fdb-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="08fdb-109">In This Section</span></span>  
 [<span data-ttu-id="08fdb-110">Trabajar con columnas en consultas de funciones agregadas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="08fdb-110">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](work-with-columns-in-aggregate-queries-visual-database-tools.md)  
 <span data-ttu-id="08fdb-111">Describe los conceptos de la agrupación y el resumen de columnas con las cláusulas GROUP BY, WHERE y HAVING.</span><span class="sxs-lookup"><span data-stu-id="08fdb-111">Describes concepts about grouping and summarizing columns with the GROUP BY, WHERE, and HAVING clauses.</span></span>  
  
 [<span data-ttu-id="08fdb-112">Contar las filas de una tabla &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="08fdb-112">Count Rows in a Table &#40;Visual Database Tools&#41;</span></span>](count-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="08fdb-113">Proporciona los pasos para contar el número de filas de una tabla o el número de filas de una tabla que cumpla un conjunto de criterios.</span><span class="sxs-lookup"><span data-stu-id="08fdb-113">Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria.</span></span>  
  
 [<span data-ttu-id="08fdb-114">Resumir o agregar los valores de todas las filas de una tabla &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="08fdb-114">Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="08fdb-115">Proporciona los pasos para resumir todas las filas en lugar de un conjunto de filas agrupadas.</span><span class="sxs-lookup"><span data-stu-id="08fdb-115">Provides steps for summarizing all rows rather than for a set of grouped rows.</span></span>  
  
 [<span data-ttu-id="08fdb-116">Resumir o agregar valores mediante expresiones personalizadas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="08fdb-116">Summarize or Aggregate Values Using Custom Expressions &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
 <span data-ttu-id="08fdb-117">Proporciona los pasos para utilizar expresiones para resumir o agregar en lugar de utilizar las cláusulas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="08fdb-117">Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="08fdb-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="08fdb-118">Related Sections</span></span>  
 [<span data-ttu-id="08fdb-119">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="08fdb-119">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
 <span data-ttu-id="08fdb-120">Proporciona vínculos a temas en los que se explica cómo se utiliza el Diseñador de consultas y vistas.</span><span class="sxs-lookup"><span data-stu-id="08fdb-120">Provides links to topics covering how to use the Query and View Designer.</span></span>  
  
  
