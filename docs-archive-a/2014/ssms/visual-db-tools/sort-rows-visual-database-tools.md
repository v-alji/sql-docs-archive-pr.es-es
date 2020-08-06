---
title: Ordenar filas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- sorting rows [SQL Server]
- sorting query results [SQL Server]
ms.assetid: 780ef467-f96e-4373-8235-6dacbedb05a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4939c08a4be8c6a7aa3a52d55928abe077f25d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748452"
---
# <a name="sort-rows-visual-database-tools"></a><span data-ttu-id="3eaa6-102">Ordenar filas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3eaa6-102">Sort Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="3eaa6-103">Puede ordenar las filas de un resultado de consulta.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-103">You can order the rows in a query result.</span></span> <span data-ttu-id="3eaa6-104">Es decir, puede indicar una columna o un conjunto de columnas determinado cuyos valores determinen el orden de las filas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-104">That is, you can name a particular column or set of columns whose values determine the order of rows in the result set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eaa6-105">La secuencia de intercalación de la columna determina en parte el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-105">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="3eaa6-106">La secuencia de intercalación se puede modificar en el [cuadro de diálogo Intercalación](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3eaa6-106">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="3eaa6-107">Los resultados de la consulta se pueden ordenar de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-107">There are several ways in which you can sort query results:</span></span>  
  
-   <span data-ttu-id="3eaa6-108">**Puede organizar filas en orden ascendente o descendente** De forma predeterminada, SQL utiliza el orden por columnas para organizar las filas en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-108">**You can arrange rows in ascending or descending order** By default, SQL uses order-by columns to arrange rows in ascending order.</span></span> <span data-ttu-id="3eaa6-109">Por ejemplo, para organizar los títulos de libros por precio ascendente, solo tiene que ordenar las filas por la columna price.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-109">For example, to arrange the book titles by ascending price, simply sort the rows by the price column.</span></span> <span data-ttu-id="3eaa6-110">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-110">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price  
  
    ```  
  
     <span data-ttu-id="3eaa6-111">Por otro lado, si desea organizar los títulos con los libros más caros primero, puede especificar explícitamente un orden en el que se indiquen primero los valores más altos.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-111">On the other hand, if you want to arrange the titles with the more expensive books first, you can explicitly specify a highest-first ordering.</span></span> <span data-ttu-id="3eaa6-112">Es decir, puede indicar que las filas del resultado se ordenen por valores descendentes de la columna price.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-112">That is, you indicate that the result rows should be arranged by descending values of the price column.</span></span> <span data-ttu-id="3eaa6-113">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-113">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="3eaa6-114">**Puede ordenar por varias columnas** Por ejemplo, puede crear un conjunto de resultados con una fila para cada autor, que se ordene primero por estado y, a continuación, por ciudad.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-114">**You can sort by multiple columns** For example, you can create a result set with one row for each author, ordering first by state and then by city.</span></span> <span data-ttu-id="3eaa6-115">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-115">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM authors   
    ORDER BY state, city  
  
    ```  
  
-   <span data-ttu-id="3eaa6-116">**Puede ordenar por columnas que no aparezcan en el conjunto de resultados** Por ejemplo, puede crear un conjunto de resultados con los títulos más caros primero, aunque no aparezcan los precios.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-116">**You can sort by columns not appearing in the result set** For example, you can create a result set with the most expensive titles first, even though the prices do not appear.</span></span> <span data-ttu-id="3eaa6-117">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-117">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title_id, title  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="3eaa6-118">**Puede ordenar por columnas derivadas** Por ejemplo, puede crear un conjunto de resultados en el que cada fila contenga un título de libro y en el que aparezcan primero los libros que pagan las regalías (royalties) más elevadas por copia.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-118">**You can sort by derived columns** For example, you can create a result set in which each row contains a book title - with the books that pay the highest royalty per copy appearing first.</span></span> <span data-ttu-id="3eaa6-119">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-119">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title, price * royalty / 100 as royalty_per_unit  
    FROM titles  
    ORDER BY royalty_per_unit DESC  
  
    ```  
  
     <span data-ttu-id="3eaa6-120">(La fórmula para calcular las regalías que cada libro genera por copia está resaltada).</span><span class="sxs-lookup"><span data-stu-id="3eaa6-120">(The formula for calculating the royalty that each book earns per copy is emphasized.)</span></span>  
  
     <span data-ttu-id="3eaa6-121">Para calcular una columna derivada, puede utilizar la sintaxis SQL, como en el ejemplo anterior, o puede utilizar una función definida por el usuario que devuelva un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-121">To calculate a derived column, you can use SQL syntax, as in the preceding example, or you can use a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="3eaa6-122">Para obtener más información sobre las funciones definidas por el usuario, vea la documentación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-122">For more information about user-defined functions, see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="3eaa6-123">**Puede ordenar filas agrupadas** Por ejemplo, puede crear un conjunto de resultados en el que cada fila describa una ciudad, además del número de autores de esa ciudad, y en el que aparezcan primero las ciudades que contienen muchos autores.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-123">**You can sort grouped rows** For example; you can create a result set in which each row describes a city, plus the number of authors in that city - with the cities containing many authors appearing first.</span></span> <span data-ttu-id="3eaa6-124">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-124">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ORDER BY COUNT(*) DESC, state  
  
    ```  
  
     <span data-ttu-id="3eaa6-125">Tenga en cuenta que la consulta utiliza `state` como columna de orden secundaria.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-125">Notice that the query uses `state` as a secondary sort column.</span></span> <span data-ttu-id="3eaa6-126">De este modo, si dos estados tienen el mismo número de autores, esos estados aparecerán en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-126">Thus, if two states have the same number of authors, those states will appear in alphabetical order.</span></span>  
  
-   <span data-ttu-id="3eaa6-127">**Puede ordenar mediante el uso de datos internacionales** Es decir, puede ordenar una columna mediante el uso de convenciones de intercalación diferentes de las convenciones predeterminadas para esa columna.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-127">**You can sort using international data** That is; you can sort a column using collating conventions that differ from the default conventions for that column.</span></span> <span data-ttu-id="3eaa6-128">Por ejemplo, puede escribir una consulta que recupere todos los títulos de libros por Jaime Pati?? aceptar.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-128">For example, you can write a query that retrieves all the book titles by Jaime Pati??o.</span></span> <span data-ttu-id="3eaa6-129">Para que los títulos aparezcan ordenados alfabéticamente, utilice una secuencia de intercalación de español en la columna de los títulos.</span><span class="sxs-lookup"><span data-stu-id="3eaa6-129">To display the titles in alphabetical order, you use a Spanish collating sequence for the title column.</span></span> <span data-ttu-id="3eaa6-130">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3eaa6-130">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title  
    FROM   
        authors   
        INNER JOIN   
            titleauthor   
            ON authors.au_id   
            =  titleauthor.au_id   
            INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
    WHERE   
         au_fname = 'Jaime' AND   
         au_lname = 'Pati??o'  
    ORDER BY   
         title COLLATE SQL_Spanish_Pref_CP1_CI_AS  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3eaa6-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3eaa6-131">See Also</span></span>  
 <span data-ttu-id="3eaa6-132">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa6-132">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3eaa6-133">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3eaa6-133">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
