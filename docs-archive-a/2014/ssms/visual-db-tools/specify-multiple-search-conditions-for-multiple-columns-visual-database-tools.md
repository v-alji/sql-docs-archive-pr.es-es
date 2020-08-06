---
title: Especificar varias condiciones de búsqueda para varias columnas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 06617729-0d0b-4da2-9890-b7e2f5cdbc7b
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccf08a98d39d4ab808b7c2df794164b341be363a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670733"
---
# <a name="specify-multiple-search-conditions-for-multiple-columns-visual-database-tools"></a><span data-ttu-id="432f9-102">Especificar varias condiciones de búsqueda para varias columnas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="432f9-102">Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="432f9-103">Puede ampliar o reducir el alcance de la consulta incluyendo varias columnas de datos como parte de la condición de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="432f9-103">You can expand or narrow the scope of your query by including several data columns as part of your search condition.</span></span> <span data-ttu-id="432f9-104">Por ejemplo, podría:</span><span class="sxs-lookup"><span data-stu-id="432f9-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="432f9-105">Buscar los empleados que han trabajado más de cinco años en la compañía o que tienen determinados puestos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="432f9-105">Search for employees who either have worked more than five years at the company or who hold certain jobs.</span></span>  
  
-   <span data-ttu-id="432f9-106">Buscar un libro publicado por una editorial específica y relativo a la cocina.</span><span class="sxs-lookup"><span data-stu-id="432f9-106">Search for a book that is both published by a specific publisher and pertains to cooking.</span></span>  
  
 <span data-ttu-id="432f9-107">Para crear una consulta que busque valores en dos o más columnas, debe especificar una condición OR.</span><span class="sxs-lookup"><span data-stu-id="432f9-107">To create a query that searches for values in either of two (or more) columns, you specify an OR condition.</span></span> <span data-ttu-id="432f9-108">Para crear una consulta que cumpla todas las condiciones de dos o más columnas, debe especificar una condición AND.</span><span class="sxs-lookup"><span data-stu-id="432f9-108">To create a query that must meet all conditions in two (or more) columns, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="432f9-109">Especificar una condición OR</span><span class="sxs-lookup"><span data-stu-id="432f9-109">Specifying an OR Condition</span></span>  
 <span data-ttu-id="432f9-110">Para crear varias condiciones vinculadas con OR, debe incluir cada condición en una columna diferente del panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="432f9-110">To create multiple conditions linked with OR, you put each separate condition in a different column of the Criteria pane.</span></span>  
  
#### <a name="to-specify-an-or-condition-for-two-different-columns"></a><span data-ttu-id="432f9-111">Para especificar una condición OR para dos columnas diferentes</span><span class="sxs-lookup"><span data-stu-id="432f9-111">To specify an OR condition for two different columns</span></span>  
  
1.  <span data-ttu-id="432f9-112">En el [panel Criterios](visual-database-tools.md), agregue las columnas en las que desee realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="432f9-112">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="432f9-113">En la columna **Filtro** de la primera columna en la que se va a realizar la búsqueda, especifique la primera condición.</span><span class="sxs-lookup"><span data-stu-id="432f9-113">In the **Filter** column for the first column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="432f9-114">En la columna **O...** de la segunda columna de datos en la que se va a realizar la búsqueda, especifique la segunda condición, dejando en blanco la columna **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="432f9-114">In the **Or...** column for the second data column to search, specify the second condition, leaving the **Filter** column blank.</span></span>  
  
     <span data-ttu-id="432f9-115">El Diseñador de consultas y vistas crea una cláusula WHERE que contiene una condición OR similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="432f9-115">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
    ```  
    SELECT job_lvl, hire_date  
    FROM employee  
    WHERE (job_lvl >= 200) OR   
      (hire_date < '01/01/1998')  
    ```  
  
4.  <span data-ttu-id="432f9-116">Repita los pasos 2 y 3 para las demás condiciones que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="432f9-116">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span> <span data-ttu-id="432f9-117">Use una columna **O...** distinta para cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="432f9-117">Use a different **Or...** column for each new condition.</span></span>  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="432f9-118">Especificar una condición AND</span><span class="sxs-lookup"><span data-stu-id="432f9-118">Specifying an AND Condition</span></span>  
 <span data-ttu-id="432f9-119">Para buscar en columnas de datos diferentes utilizando condiciones vinculadas con AND, debe incluir todas las condiciones en la columna **Filtro** de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="432f9-119">To search different data columns using conditions linked with AND, you put all the conditions in the **Filter** column of the grid.</span></span>  
  
#### <a name="to-specify-an-and-condition-for-two-different-columns"></a><span data-ttu-id="432f9-120">Para especificar una condición AND para dos columnas diferentes</span><span class="sxs-lookup"><span data-stu-id="432f9-120">To specify an AND condition for two different columns</span></span>  
  
1.  <span data-ttu-id="432f9-121">En el [panel Criterios](visual-database-tools.md), agregue las columnas en las que desee realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="432f9-121">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="432f9-122">En la columna **Filtro** de la primera columna de datos en la que se va a realizar la búsqueda, especifique la primera condición.</span><span class="sxs-lookup"><span data-stu-id="432f9-122">In the **Filter** column for the first data column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="432f9-123">En la columna **Filtro** de la segunda columna de datos, especifique la segunda condición.</span><span class="sxs-lookup"><span data-stu-id="432f9-123">In the **Filter** column for the second data column, specify the second condition.</span></span>  
  
     <span data-ttu-id="432f9-124">El Diseñador de consultas y vistas crea una cláusula WHERE que contiene una condición AND similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="432f9-124">The Query and View Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
    ```  
    SELECT pub_id, title  
    FROM titles  
    WHERE (pub_id = '0877') AND (title LIKE '%Cook%')  
    ```  
  
4.  <span data-ttu-id="432f9-125">Repita los pasos 2 y 3 para las demás condiciones que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="432f9-125">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="432f9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="432f9-126">See Also</span></span>  
 <span data-ttu-id="432f9-127">[Combinar condiciones cuando AND tiene prioridad &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="432f9-127">[Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="432f9-128">[Combinar condiciones cuando OR tiene prioridad &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="432f9-128">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="432f9-129">[Convenciones para combinar condiciones de búsqueda en el panel criterios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="432f9-129">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="432f9-130">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="432f9-130">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
