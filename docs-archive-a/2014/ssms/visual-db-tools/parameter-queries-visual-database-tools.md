---
title: Consultas con parámetros (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- parameter queries [SQL Server]
ms.assetid: 4897c41a-324a-47b8-a30b-cbc9e9e19a8b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f6fd94ef180a34ae91d52c213092898612dc77d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674489"
---
# <a name="parameter-queries-visual-database-tools"></a><span data-ttu-id="42863-102">Consultas con parámetros (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="42863-102">Parameter Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="42863-103">En algunos casos, tal vez necesite crear una consulta que pueda utilizar en muchas ocasiones, pero con un valor diferente cada vez.</span><span class="sxs-lookup"><span data-stu-id="42863-103">In some cases you want to create a query that you can use many times, but with a different value each time.</span></span> <span data-ttu-id="42863-104">Por ejemplo, puede ejecutar habitualmente una consulta para buscar todos los `title_ids` escritos por un autor.</span><span class="sxs-lookup"><span data-stu-id="42863-104">For example, you might frequently run a query to find all the `title_ids` written by one author.</span></span> <span data-ttu-id="42863-105">Puede ejecutar la misma consulta para cada solicitud, con la salvedad de que el nombre o el Id. del autor serán diferentes cada vez.</span><span class="sxs-lookup"><span data-stu-id="42863-105">You could run the same query for each request, except that the author's ID or name would be different each time.</span></span>  
  
 <span data-ttu-id="42863-106">Para crear una consulta que pueda tener valores diferentes en distintas ocasiones, puede utilizar parámetros en la consulta.</span><span class="sxs-lookup"><span data-stu-id="42863-106">To create a query that can have different values at different times, you use parameters in the query.</span></span> <span data-ttu-id="42863-107">Un parámetro es un marcador de posición para un valor que se proporciona al ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="42863-107">A parameter is a placeholder for a value that is supplied when the query runs.</span></span> <span data-ttu-id="42863-108">Una instrucción SQL con un parámetro puede presentar el siguiente aspecto ("?" representaría el parámetro del Id. del autor):</span><span class="sxs-lookup"><span data-stu-id="42863-108">An SQL statement with a parameter might look like the following, where "?" represents the parameter for the author's ID:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
## <a name="where-you-can-use-parameters"></a><span data-ttu-id="42863-109">Cuándo se pueden utilizar parámetros</span><span class="sxs-lookup"><span data-stu-id="42863-109">Where You Can Use Parameters</span></span>  
 <span data-ttu-id="42863-110">Puede usar parámetros como marcadores de posición para valores literales, tanto para valores de texto como para valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="42863-110">You can use parameters as placeholders for literal values - for either text or numeric values.</span></span> <span data-ttu-id="42863-111">Generalmente, los parámetros se utilizan como marcadores de posición en condiciones de búsqueda para filas individuales o para grupos (es decir, en las cláusulas WHERE o HAVING de una instrucción SQL).</span><span class="sxs-lookup"><span data-stu-id="42863-111">Most commonly, parameters are used as placeholders in search conditions for individual rows or for groups (that is, in the WHERE or HAVING clauses of an SQL statement).</span></span>  
  
 <span data-ttu-id="42863-112">Se pueden utilizar parámetros como marcadores de posición en expresiones.</span><span class="sxs-lookup"><span data-stu-id="42863-112">You can use parameters as placeholders in expressions.</span></span> <span data-ttu-id="42863-113">Por ejemplo, si desea calcular precios con descuento, proporcione un valor de descuento distinto cada vez que ejecute una consulta.</span><span class="sxs-lookup"><span data-stu-id="42863-113">For example, you might want to calculate discounted prices by supplying a different discount value each time you run a query.</span></span> <span data-ttu-id="42863-114">Para hacerlo, puede especificar la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="42863-114">To do so, you could specify the following expression:</span></span>  
  
```  
(price * ?)  
```  
  
## <a name="specifying-unnamed-and-named-parameters"></a><span data-ttu-id="42863-115">Especificar parámetros con nombre y sin nombre</span><span class="sxs-lookup"><span data-stu-id="42863-115">Specifying Unnamed and Named Parameters</span></span>  
 <span data-ttu-id="42863-116">Puede especificar dos tipos de parámetros: con nombre y sin nombre.</span><span class="sxs-lookup"><span data-stu-id="42863-116">You can specify two types of parameters: unnamed and named.</span></span> <span data-ttu-id="42863-117">Un parámetro sin nombre es un signo de interrogación de cierre (?) que se coloca en cualquier parte de la consulta en que se desea solicitar o sustituir un valor literal.</span><span class="sxs-lookup"><span data-stu-id="42863-117">An unnamed parameter is a question mark (?) that you put anywhere in the query that you want to prompt for or substitute a literal value.</span></span> <span data-ttu-id="42863-118">Por ejemplo, si utiliza un parámetro sin nombre para buscar el Id. de un autor en la tabla `titleauthor` , la instrucción resultante en el [panel SQL](visual-database-tools.md) podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="42863-118">For example, if you use an unnamed parameter to search for an author's id in the `titleauthor` table, the resulting statement in the [SQL Pane](visual-database-tools.md) might look like this:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
 <span data-ttu-id="42863-119">Cuando ejecute la consulta en el [Diseñador de consultas y vistas](query-and-view-designer-tools-visual-database-tools.md), el [cuadro de diálogo Parámetros de la consulta](query-parameters-dialog-box-visual-database-tools.md) mostrará "?" como nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="42863-119">When you run the query in the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md), the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with "?" as the name of the parameter.</span></span>  
  
 <span data-ttu-id="42863-120">Como alternativa, puede asignar un nombre a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="42863-120">Alternatively, you can assign a name to a parameter.</span></span> <span data-ttu-id="42863-121">Los parámetros con nombre son especialmente útiles si dispone de varios parámetros en una consulta.</span><span class="sxs-lookup"><span data-stu-id="42863-121">Named parameters are particularly useful if you have multiple parameters in a query.</span></span> <span data-ttu-id="42863-122">Por ejemplo, si utiliza parámetros con nombre para buscar el nombre y los apellidos de un autor en la tabla `authors` , la instrucción resultante en el panel SQL podría presentar este aspecto:</span><span class="sxs-lookup"><span data-stu-id="42863-122">For example, if you use named parameters to search for an author's first and last names in the `authors` table, the resulting statement in the SQL pane might look like this:</span></span>  
  
```  
SELECT au_id  
FROM authors  
WHERE au_fname = %first name% AND  
      au_lname = %last name%  
```  
  
> [!TIP]  
>  <span data-ttu-id="42863-123">Debe definir caracteres de prefijo y de sufijo antes de crear una consulta de parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="42863-123">You must define prefix and suffix characters before creating a named parameter query.</span></span>  
  
 <span data-ttu-id="42863-124">Cuando ejecute la consulta en el Diseñador de consultas y vistas, el [cuadro de diálogo Parámetros de la consulta](query-parameters-dialog-box-visual-database-tools.md) mostrará una lista de parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="42863-124">When you run the query in the Query and View Designer, the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with a list of named parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42863-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42863-125">See Also</span></span>  
 <span data-ttu-id="42863-126">[Consultar con parámetros &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="42863-126">[Query with Parameters &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span></span>  
 <span data-ttu-id="42863-127">[Tipos de consultas admitidos &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="42863-127">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="42863-128">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="42863-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
