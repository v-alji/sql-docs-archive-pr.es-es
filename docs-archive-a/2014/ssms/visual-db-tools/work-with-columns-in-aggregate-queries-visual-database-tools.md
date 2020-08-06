---
title: Trabajar con columnas en consultas de funciones agregadas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query summary results
- GROUP BY clause, query summary results
- aggregate queries [SQL Server]
- WHERE clause, query summary results
ms.assetid: 1b82681f-3d4f-4b9a-bb1d-2060e44f2577
author: stevestein
ms.author: sstein
ms.openlocfilehash: 880f7529cebd7f51951e62952e3b5f13190f99b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743815"
---
# <a name="work-with-columns-in-aggregate-queries-visual-database-tools"></a><span data-ttu-id="4a594-102">Trabajar con columnas en consultas de funciones agregadas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4a594-102">Work with Columns in Aggregate Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="4a594-103">Al crear consultas agregadas, el [Diseñador de consultas y vistas](visual-database-tools.md) asume determinados criterios para poder crear una consulta válida.</span><span class="sxs-lookup"><span data-stu-id="4a594-103">When you create aggregate queries the [Query and View Designer](visual-database-tools.md) makes certain assumptions so that it can construct a valid query.</span></span> <span data-ttu-id="4a594-104">Por ejemplo, si está creando una consulta de funciones de agregado y marca una columna de datos para los resultados, el Diseñador de consultas y vistas incluye automáticamente la columna en la cláusula GROUP BY para que no intente mostrar sin darse cuenta el contenido de una fila individual en un resumen.</span><span class="sxs-lookup"><span data-stu-id="4a594-104">For example, if you are creating an aggregate query and mark a data column for output, the Query and View Designer automatically makes the column part of the GROUP BY clause so that you do not inadvertently attempt to display the contents of an individual row in a summary.</span></span>  
  
## <a name="using-group-by"></a><span data-ttu-id="4a594-105">Utilizar Agrupar por</span><span class="sxs-lookup"><span data-stu-id="4a594-105">Using Group By</span></span>  
 <span data-ttu-id="4a594-106">El Diseñador de consultas y vistas utiliza las siguientes instrucciones para trabajar con columnas:</span><span class="sxs-lookup"><span data-stu-id="4a594-106">The Query and View Designer uses the following guidelines for working with columns:</span></span>  
  
-   <span data-ttu-id="4a594-107">Al elegir la opción Agrupar por o al agregar una función agregada a una consulta, se agregan automáticamente a la cláusula GROUP BY todas las columnas marcadas para los resultados o utilizadas para ordenar.</span><span class="sxs-lookup"><span data-stu-id="4a594-107">When you choose the Group By option or add an aggregate function to a query, all columns marked for output or used for sorting are automatically added to the GROUP BY clause.</span></span> <span data-ttu-id="4a594-108">Las columnas no se agregan automáticamente a la cláusula GROUP BY si ya forman parte de una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="4a594-108">Columns are not automatically added to the GROUP BY clause if they are already part of an aggregate function.</span></span>  
  
     <span data-ttu-id="4a594-109">Si no desea que una columna en particular forme parte de la cláusula GROUP BY, debe cambiarla manualmente mediante la selección de una opción distinta en la columna Agrupar por del panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="4a594-109">If you do not want a particular column to be part of the GROUP BY clause, you must manually change it by selecting a different option in the Group By column of the Criteria pane.</span></span> <span data-ttu-id="4a594-110">Sin embargo, el Diseñador de consultas y vistas no impedirá que elija una opción que pueda dar como resultado una consulta que no acabe ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="4a594-110">However, the Query and View Designer will not prevent you from choosing an option that can result in a query that will not run.</span></span>  
  
-   <span data-ttu-id="4a594-111">Si agrega manualmente una columna de resultados de consulta a una función de agregado ya sea en el panel Criterios o en el panel SQL, el Diseñador de consultas y vistas no quita automáticamente las demás columnas de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="4a594-111">If you manually add a query output column to an aggregate function in either the Criteria or SQL pane, the Query and View Designer does not automatically remove other output columns from the query.</span></span> <span data-ttu-id="4a594-112">Por lo tanto, debe quitar las columnas restantes de los resultados de la consulta o incluirlas en la cláusula GROUP BY o en una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="4a594-112">Therefore, you must remove the remaining columns from the query output or make them part of the GROUP BY clause or of an aggregate function.</span></span>  
  
 <span data-ttu-id="4a594-113">Al especificar una condición de búsqueda en la columna Filtro del panel Criterios, el Diseñador de consultas y vistas sigue estas reglas:</span><span class="sxs-lookup"><span data-stu-id="4a594-113">When you enter a search condition into the Filter column of the Criteria pane, the Query and View Designer follows these rules:</span></span>  
  
-   <span data-ttu-id="4a594-114">Si no se muestra la columna **Agrupar por** de la cuadrícula (porque todavía no ha especificado una consulta de funciones agregadas), la condición de búsqueda se coloca en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="4a594-114">If the **Group By** column of the grid is not displayed (because you have not yet specified an aggregate query), the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="4a594-115">Si ya se encuentra en una consulta de funciones agregadas y ha seleccionado la opción **Ubicación** en la columna **Agrupar por** , la condición de búsqueda se coloca en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="4a594-115">If you are already in an aggregate query and have selected the option **Where** in the **Group By** column, the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="4a594-116">Si la columna **Agrupar por** contiene cualquier valor que no sea **Ubicación**, la condición de búsqueda se coloca en la cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="4a594-116">If the **Group By** column contains any value other than **Where**, the search condition is placed in the HAVING clause.</span></span>  
  
## <a name="using-the-having-and-where-clauses"></a><span data-ttu-id="4a594-117">Uso de las cláusulas HAVING y WHERE</span><span class="sxs-lookup"><span data-stu-id="4a594-117">Using the HAVING and WHERE Clauses</span></span>  
 <span data-ttu-id="4a594-118">Los principios siguientes describen cómo puede hacer referencia a columnas de una consulta de funciones agregadas en condiciones de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="4a594-118">The following principles describe how you can reference columns in an aggregate query in search conditions.</span></span> <span data-ttu-id="4a594-119">en general, puede utilizar una columna en una condición de búsqueda para filtrar las filas que deben resumirse (una cláusula WHERE) o determinar qué resultados agrupados aparecen en los resultados finales (una cláusula HAVING).</span><span class="sxs-lookup"><span data-stu-id="4a594-119">In general, you can use a column in a search condition to filter the rows that should be summarized (a WHERE clause) or to determine which grouped results appear in the final output (a HAVING clause).</span></span>  
  
-   <span data-ttu-id="4a594-120">Las columnas de datos individuales pueden aparecer en la cláusula WHERE o HAVING, en función de cómo se utilicen en cualquier otra parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="4a594-120">Individual data columns can appear in either the WHERE or HAVING clause, depending on how they are used elsewhere in the query.</span></span>  
  
-   <span data-ttu-id="4a594-121">Las cláusulas WHERE se utilizan para seleccionar subconjuntos de filas para resumir y agrupar y, así, se aplican antes de que se realice un agrupamiento.</span><span class="sxs-lookup"><span data-stu-id="4a594-121">WHERE clauses are used to select a subset of rows for summarizing and grouping and are thus applied before any grouping is done.</span></span> <span data-ttu-id="4a594-122">De ahí que pueda utilizar una columna de datos en una cláusula WHERE aunque no forme parte de la cláusula GROUP BY o no esté contenida en una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="4a594-122">Therefore, you can use a data column in a WHERE clause even if it is not part of the GROUP BY clause or contained in an aggregate function.</span></span> <span data-ttu-id="4a594-123">Por ejemplo, la siguiente instrucción selecciona todos los títulos que cuestan más de 10,00 USD y obtiene un promedio del precio:</span><span class="sxs-lookup"><span data-stu-id="4a594-123">For example, the following statement selects all titles that cost more than $10.00 and averages the price:</span></span>  
  
    ```  
    SELECT AVG(price)  
    FROM titles  
    WHERE price > 10  
    ```  
  
-   <span data-ttu-id="4a594-124">Si crea una condición de búsqueda que incluya una columna que también se usa en una cláusula GROUP BY o en una función de agregado, la condición de búsqueda puede aparecer como una cláusula WHERE o como una cláusula HAVING: puede decidir cuál al crear la condición.</span><span class="sxs-lookup"><span data-stu-id="4a594-124">If you create a search condition that involves a column also used in a GROUP BY clause or aggregate function, the search condition can appear as either a WHERE clause or a HAVING clause - you can decide which when you create the condition.</span></span> <span data-ttu-id="4a594-125">Por ejemplo, la siguiente instrucción crea un precio medio de los títulos de cada editorial y, a continuación, muestra la media de las editoriales cuyo precio medio supera los 10,00 USD:</span><span class="sxs-lookup"><span data-stu-id="4a594-125">For example, the following statement creates an average price for the titles for each publisher, then displays the average for the publishers in which the average price is greater than $10.00:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
    ```  
  
-   <span data-ttu-id="4a594-126">Si utiliza una función de agregado en una condición de búsqueda, la condición requiere un resumen y, por lo tanto, debe formar parte de la cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="4a594-126">If you use an aggregate function in a search condition, the condition involves a summary and must therefore be part of the HAVING clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a594-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a594-127">See Also</span></span>  
 <span data-ttu-id="4a594-128">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4a594-128">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4a594-129">Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4a594-129">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
