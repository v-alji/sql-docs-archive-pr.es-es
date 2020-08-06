---
title: Usar cláusulas HAVING y WHERE en la misma consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- search conditions [SQL Server], HAVING clause
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- HAVING clause, search criteria
- search conditions [SQL Server], WHERE clause
- WHERE clause, search criteria
- excluding rows
ms.assetid: 1e07cf56-b4b7-4c49-8ddd-c276812a7148
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f6b471a60bf225ee61bdbbf0ecec30f21a92cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744461"
---
# <a name="use-having-and-where-clauses-in-the-same-query-visual-database-tools"></a><span data-ttu-id="f88f9-102">Utilizar cláusulas HAVING y WHERE en la misma consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f88f9-102">Use HAVING and WHERE Clauses in the Same Query (Visual Database Tools)</span></span>
  <span data-ttu-id="f88f9-103">En algunas ocasiones, será conveniente excluir algunas filas de los grupos (utilizando una cláusula WHERE) antes de aplicar una condición a los grupos como un todo (utilizando una cláusula HAVING).</span><span class="sxs-lookup"><span data-stu-id="f88f9-103">In some instances, you might want to exclude individual rows from groups (using a WHERE clause) before applying a condition to groups as a whole (using a HAVING clause).</span></span>  
  
 <span data-ttu-id="f88f9-104">Una cláusula HAVING es como una cláusula WHERE, pero que solo se aplica a los grupos en su totalidad (es decir, a las filas del conjunto de resultados que representa los grupos), a diferencia de la cláusula WHERE, que se aplica a filas individuales.</span><span class="sxs-lookup"><span data-stu-id="f88f9-104">A HAVING clause is like a WHERE clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the WHERE clause applies to individual rows.</span></span> <span data-ttu-id="f88f9-105">Una consulta puede contener tanto una cláusula WHERE como una cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="f88f9-105">A query can contain both a WHERE clause and a HAVING clause.</span></span> <span data-ttu-id="f88f9-106">En tal caso:</span><span class="sxs-lookup"><span data-stu-id="f88f9-106">In that case:</span></span>  
  
-   <span data-ttu-id="f88f9-107">La cláusula WHERE se aplica primero a las filas individuales de las tablas u objetos con valores de tabla del panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="f88f9-107">The WHERE clause is applied first to the individual rows in the tables or table-valued objects in the Diagram pane.</span></span> <span data-ttu-id="f88f9-108">Solo se agrupan las filas que cumplen las condiciones de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="f88f9-108">Only the rows that meet the conditions in the WHERE clause are grouped.</span></span>  
  
-   <span data-ttu-id="f88f9-109">La cláusula HAVING se aplica a continuación a las filas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f88f9-109">The HAVING clause is then applied to the rows in the result set.</span></span> <span data-ttu-id="f88f9-110">Solo aparecen en el resultado de la consulta los grupos que cumplen las condiciones HAVING.</span><span class="sxs-lookup"><span data-stu-id="f88f9-110">Only the groups that meet the HAVING conditions appear in the query output.</span></span> <span data-ttu-id="f88f9-111">Solo puede aplicar una cláusula HAVING a las columnas que también aparecen en la cláusula GROUP BY o en una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f88f9-111">You can apply a HAVING clause only to columns that also appear in the GROUP BY clause or in an aggregate function.</span></span>  
  
 <span data-ttu-id="f88f9-112">Imagine, por ejemplo, que va a combinar las tablas `titles` y `publishers` para crear una consulta que muestre el precio medio de los libros de un conjunto de editoriales.</span><span class="sxs-lookup"><span data-stu-id="f88f9-112">For example, imagine that you are joining the `titles` and `publishers` tables to create a query showing the average book price for a set of publishers.</span></span> <span data-ttu-id="f88f9-113">Solo quiere ver el precio medio de un conjunto específico de editores: los del estado de California, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f88f9-113">You want to see the average price for only a specific set of publishers - perhaps only the publishers in the state of California.</span></span> <span data-ttu-id="f88f9-114">Y además, solo quiere ver el precio medio si éste es superior a 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="f88f9-114">And even then, you want to see the average price only if it is over $10.00.</span></span>  
  
 <span data-ttu-id="f88f9-115">Puede establecer la primera condición incluyendo una cláusula WHERE, que descarta todas las editoriales que no están en California, antes de calcular los precios medios.</span><span class="sxs-lookup"><span data-stu-id="f88f9-115">You can establish the first condition by including a WHERE clause, which discards any publishers that are not in California, before calculating average prices.</span></span> <span data-ttu-id="f88f9-116">La segunda condición requiere una cláusula HAVING, ya que se basa en los resultados de la agrupación y del resumen de los datos.</span><span class="sxs-lookup"><span data-stu-id="f88f9-116">The second condition requires a HAVING clause, because the condition is based on the results of grouping and summarizing the data.</span></span> <span data-ttu-id="f88f9-117">La instrucción SQL resultante podría tener la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="f88f9-117">The resulting SQL statement might look like this:</span></span>  
  
```  
SELECT titles.pub_id, AVG(titles.price)  
FROM titles INNER JOIN publishers  
   ON titles.pub_id = publishers.pub_id  
WHERE publishers.state = 'CA'  
GROUP BY titles.pub_id  
HAVING AVG(price) > 10  
```  
  
 <span data-ttu-id="f88f9-118">Puede crear tanto cláusulas HAVING como WHERE en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="f88f9-118">You can create both HAVING and WHERE clauses in the Criteria pane.</span></span> <span data-ttu-id="f88f9-119">De forma predeterminada, si especifica una condición de búsqueda para una columna, la condición entra a formar parte de la cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="f88f9-119">By default, if you specify a search condition for a column, the condition becomes part of the HAVING clause.</span></span> <span data-ttu-id="f88f9-120">No obstante, puede cambiar la condición para que sea una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="f88f9-120">However, you can change the condition to be a WHERE clause.</span></span>  
  
 <span data-ttu-id="f88f9-121">Puede crear una cláusula WHERE y una cláusula HAVING en las que intervenga la misma columna.</span><span class="sxs-lookup"><span data-stu-id="f88f9-121">You can create a WHERE clause and HAVING clause involving the same column.</span></span> <span data-ttu-id="f88f9-122">Para ello, debe agregar la columna dos veces al panel Criterios y especificar, a continuación, una instancia como parte de la cláusula HAVING y la otra como parte de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="f88f9-122">To do so, you must add the column twice to the Criteria pane, then specify one instance as part of the HAVING clause and the other instance as part of the WHERE clause.</span></span>  
  
### <a name="to-specify-a-where-condition-in-an-aggregate-query"></a><span data-ttu-id="f88f9-123">Para especificar una condición WHERE en una consulta de funciones agregadas</span><span class="sxs-lookup"><span data-stu-id="f88f9-123">To specify a WHERE condition in an aggregate query</span></span>  
  
1.  <span data-ttu-id="f88f9-124">Especifique los grupos de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f88f9-124">Specify the groups for your query.</span></span> <span data-ttu-id="f88f9-125">Para detalles, consulte [Agrupar filas en los resultados de la consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f88f9-125">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="f88f9-126">Si aún no está en el panel Criterios, agregue la columna en la que desea que se base la condición WHERE.</span><span class="sxs-lookup"><span data-stu-id="f88f9-126">If it is not already in the Criteria pane, add the column on which you want to base the WHERE condition.</span></span>  
  
3.  <span data-ttu-id="f88f9-127">Borre la columna **Resultados** , a menos que la columna de datos forme parte de la cláusula GROUP BY o esté incluida en una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f88f9-127">Clear the **Output** column unless the data column is part of the GROUP BY clause or included in an aggregate function.</span></span>  
  
4.  <span data-ttu-id="f88f9-128">En la columna **Filtro** , especifique la condición WHERE.</span><span class="sxs-lookup"><span data-stu-id="f88f9-128">In the **Filter** column, specify the WHERE condition.</span></span> <span data-ttu-id="f88f9-129">El Diseñador de consultas y vistas agrega la condición a la cláusula HAVING de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="f88f9-129">The Query and View Designer adds the condition to the HAVING clause of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f88f9-130">En la consulta mostrada en el ejemplo de este procedimiento se combinan dos tablas: `titles` y `publishers`.</span><span class="sxs-lookup"><span data-stu-id="f88f9-130">The query shown in the example for this procedure joins two tables, `titles` and `publishers`.</span></span>  
  
     <span data-ttu-id="f88f9-131">En este punto de la consulta, la instrucción SQL contiene una cláusula HAVING:</span><span class="sxs-lookup"><span data-stu-id="f88f9-131">At this point in the query, the SQL statement contains a HAVING clause:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    GROUP BY titles.pub_id  
    HAVING publishers.state = 'CA'  
    ```  
  
5.  <span data-ttu-id="f88f9-132">En la columna **Agrupar por** , seleccione **Where** de la lista de opciones de agrupación y resumen.</span><span class="sxs-lookup"><span data-stu-id="f88f9-132">In the **Group By** column, select **Where** from the list of group and summary options.</span></span> <span data-ttu-id="f88f9-133">El Diseñador de consultas y vistas quita la condición de la cláusula HAVING en la instrucción SQL y la agrega a la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="f88f9-133">The Query and View Designer removes the condition from the HAVING clause in the SQL statement and adds it to the WHERE clause.</span></span>  
  
     <span data-ttu-id="f88f9-134">La instrucción SQL cambia para incluir en su lugar una cláusula WHERE:</span><span class="sxs-lookup"><span data-stu-id="f88f9-134">The SQL statement changes to include a WHERE clause instead:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    WHERE publishers.state = 'CA'  
    GROUP BY titles.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f88f9-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f88f9-135">See Also</span></span>  
 <span data-ttu-id="f88f9-136">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f88f9-136">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="f88f9-137">Resumir los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="f88f9-137">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
