---
title: Crear consultas con algo distinto de una tabla (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], queries
- queries [SQL Server], creating
ms.assetid: 8e4a1f0a-8a42-4733-be8d-e21d6dbddb33
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0444c20fe10080949930f23623d5699f7fd3712c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662466"
---
# <a name="create-queries-using-something-besides-a-table-visual-database-tools"></a><span data-ttu-id="64f2c-102">Crear consultas a partir de otro objeto distinto de una tabla (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="64f2c-102">Create Queries using Something Besides a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="64f2c-103">Al escribir una consulta de recuperación, puede enunciar qué columnas y qué filas desea obtener y dónde tiene que buscar el procesador de consultas los datos originales.</span><span class="sxs-lookup"><span data-stu-id="64f2c-103">Whenever you write a retrieval query, you articulate what columns you want, what rows you want, and where the query processor should find the original data.</span></span> <span data-ttu-id="64f2c-104">Normalmente, estos datos originales están formados por una o varias tablas combinadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="64f2c-104">Typically, this original data consists of a table or several tables joined together.</span></span> <span data-ttu-id="64f2c-105">Pero los datos originales pueden proceder de orígenes que no sean tablas.</span><span class="sxs-lookup"><span data-stu-id="64f2c-105">But the original data can come from sources other than tables.</span></span> <span data-ttu-id="64f2c-106">De hecho, pueden provenir de vistas, consultas, sinónimos o funciones definidas por el usuario que devuelven una tabla.</span><span class="sxs-lookup"><span data-stu-id="64f2c-106">In fact, it can come from views, queries, synonyms, or user-defined functions that return a table.</span></span>  
  
## <a name="using-a-view-in-place-of-a-table"></a><span data-ttu-id="64f2c-107">Utilizar una vista en lugar de una tabla</span><span class="sxs-lookup"><span data-stu-id="64f2c-107">Using a View in Place of a Table</span></span>  
 <span data-ttu-id="64f2c-108">Puede seleccionar filas en una vista.</span><span class="sxs-lookup"><span data-stu-id="64f2c-108">You can select rows from a view.</span></span> <span data-ttu-id="64f2c-109">Por ejemplo, supongamos que la base de datos incluye una vista denominada "ExpensiveBooks", en la que cada fila describe un título cuyo precio supera 19,99.</span><span class="sxs-lookup"><span data-stu-id="64f2c-109">For example, suppose the database includes a view called "ExpensiveBooks," in which each row describes a title whose price exceeds 19.99.</span></span> <span data-ttu-id="64f2c-110">La definición de vista puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="64f2c-110">The view definition might look like this:</span></span>  
  
```  
SELECT *  
FROM titles  
WHERE price > 19.99  
  
```  
  
 <span data-ttu-id="64f2c-111">Si desea seleccionar los libros de psicología caros, solo tiene que seleccionar los libros de psicología de la vista ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="64f2c-111">You can select the expensive psychology books merely by selecting the psychology books from the ExpensiveBooks view.</span></span> <span data-ttu-id="64f2c-112">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="64f2c-112">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM ExpensiveBooks  
WHERE type = 'psychology'  
  
```  
  
 <span data-ttu-id="64f2c-113">De igual manera, una vista puede participar en una operación JOIN.</span><span class="sxs-lookup"><span data-stu-id="64f2c-113">Similarly, a view can participate in a JOIN operation.</span></span> <span data-ttu-id="64f2c-114">Por ejemplo, puede buscar las ventas de libros caros combinando simplemente la tabla de ventas (sales) con la vista ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="64f2c-114">For example, you can find the sales of expensive books merely by joining the sales table to the ExpensiveBooks view.</span></span> <span data-ttu-id="64f2c-115">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="64f2c-115">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM sales   
         INNER JOIN   
         ExpensiveBooks   
         ON sales.title_id   
         =  ExpensiveBooks.title_id  
  
```  
  
 <span data-ttu-id="64f2c-116">Para obtener más información sobre cómo agregar una vista a una consulta, consulte [Agregar tablas a las consultas (Visual Database Tools)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64f2c-116">For more information about adding a view to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-query-in-place-of-a-table"></a><span data-ttu-id="64f2c-117">Utilizar una consulta en lugar de una tabla</span><span class="sxs-lookup"><span data-stu-id="64f2c-117">Using a Query in Place of a Table</span></span>  
 <span data-ttu-id="64f2c-118">Puede seleccionar filas de una consulta.</span><span class="sxs-lookup"><span data-stu-id="64f2c-118">You can select rows from a query.</span></span> <span data-ttu-id="64f2c-119">Por ejemplo, supongamos que ya ha escrito una consulta que recupera títulos e identificadores de los libros escritos por varios autores.</span><span class="sxs-lookup"><span data-stu-id="64f2c-119">For example, suppose you have already written a query retrieving titles and identifiers of the coauthored books - the books with more than one author.</span></span> <span data-ttu-id="64f2c-120">El aspecto de SQL puede ser el siguiente:</span><span class="sxs-lookup"><span data-stu-id="64f2c-120">The SQL might look like this:</span></span>  
  
```  
SELECT   
     titles.title_id, title, type  
FROM   
     titleauthor   
         INNER JOIN  
         titles   
         ON titleauthor.title_id   
         =  titles.title_id   
GROUP BY   
     titles.title_id, title, type  
HAVING COUNT(*) > 1  
  
```  
  
 <span data-ttu-id="64f2c-121">Seguidamente, puede escribir otra consulta que se base en este resultado.</span><span class="sxs-lookup"><span data-stu-id="64f2c-121">You can then write another query that builds on this result.</span></span> <span data-ttu-id="64f2c-122">Por ejemplo, puede escribir una consulta que recupere los libros de psicología escritos por varios autores.</span><span class="sxs-lookup"><span data-stu-id="64f2c-122">For example, you can write a query that retrieves the coauthored psychology books.</span></span> <span data-ttu-id="64f2c-123">Para escribir esta consulta nueva, puede utilizar la consulta existente como origen de datos de la nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="64f2c-123">To write this new query, you can use the existing query as the source of the new query's data.</span></span> <span data-ttu-id="64f2c-124">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="64f2c-124">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    title  
FROM   
    (  
    SELECT   
        titles.title_id,   
        title,   
        type  
    FROM   
        titleauthor   
            INNER JOIN  
            titles   
            ON titleauthor.title_id   
            =  titles.title_id   
    GROUP BY   
        titles.title_id,   
        title,   
        type  
    HAVING COUNT(*) > 1  
    )   
    co_authored_books  
WHERE     type = 'psychology'  
  
```  
  
 <span data-ttu-id="64f2c-125">El texto resaltado muestra la consulta existente utilizada como origen de los datos de la nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="64f2c-125">The emphasized text shows the existing query used as the source of the new query's data.</span></span> <span data-ttu-id="64f2c-126">Tenga en cuenta que la consulta nueva utiliza un alias ("co_authored_books") para la consulta existente.</span><span class="sxs-lookup"><span data-stu-id="64f2c-126">Note that the new query uses an alias ("co_authored_books") for the existing query.</span></span> <span data-ttu-id="64f2c-127">Para obtener más información sobre los alias, consulte [Crear alias de tabla (Visual Database Tools)](create-table-aliases-visual-database-tools.md) y [Crear alias de columna (Visual Database Tools)](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64f2c-127">For more information about aliases, see [Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) and [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="64f2c-128">De igual manera, una consulta puede participar en una operación JOIN.</span><span class="sxs-lookup"><span data-stu-id="64f2c-128">Similarly, a query can participate in a JOIN operation.</span></span> <span data-ttu-id="64f2c-129">Por ejemplo, puede buscar las ventas de libros caros escritos por varios autores simplemente mediante la combinación de la vista ExpensiveBooks con la consulta que recupera los libros escritos por varios autores.</span><span class="sxs-lookup"><span data-stu-id="64f2c-129">For example, you can find the sales of expensive coauthored books merely by joining the ExpensiveBooks view to the query retrieving the coauthored books.</span></span> <span data-ttu-id="64f2c-130">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="64f2c-130">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    ExpensiveBooks.title  
FROM   
    ExpensiveBooks   
        INNER JOIN  
        (  
        SELECT   
            titles.title_id,   
            title,   
            type  
        FROM   
            titleauthor   
                INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
        GROUP BY   
            titles.title_id,   
            title,   
            type  
        HAVING COUNT(*) > 1  
        )  
```  
  
 <span data-ttu-id="64f2c-131">Para obtener más información sobre cómo agregar una consulta a otra consulta, consulte [Agregar tablas a las consultas (Visual Database Tools)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64f2c-131">For more information about adding a query to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-user-defined-function-in-place-of-a-table"></a><span data-ttu-id="64f2c-132">Usar una función definida por el usuario en lugar de una tabla</span><span class="sxs-lookup"><span data-stu-id="64f2c-132">Using a User-Defined Function in Place of a Table</span></span>  
 <span data-ttu-id="64f2c-133">En SQL Server 2000 o superior, puede crear una función definida por el usuario que devuelva una tabla.</span><span class="sxs-lookup"><span data-stu-id="64f2c-133">In SQL Server 2000 or higher, you can create a user-defined function that returns a table.</span></span> <span data-ttu-id="64f2c-134">Estas funciones son útiles para la realización de lógica compleja o de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="64f2c-134">Such functions are useful for performing complex or procedural logic.</span></span>  
  
 <span data-ttu-id="64f2c-135">Por ejemplo, suponga que la tabla employee (empleados) contiene una columna adicional, employee.manager_emp_id, y que existe una clave externa de manager_emp_id a employee.emp_id.</span><span class="sxs-lookup"><span data-stu-id="64f2c-135">For example, suppose the employee table contains an additional column, employee.manager_emp_id, and that a foreign key exists from manager_emp_id to employee.emp_id.</span></span> <span data-ttu-id="64f2c-136">Dentro de cada fila de la tabla employee, la columna manager_emp_id se refiere al jefe del empleado.</span><span class="sxs-lookup"><span data-stu-id="64f2c-136">Within each row of the employee table, the manager_emp_id column indicates the employee's boss.</span></span> <span data-ttu-id="64f2c-137">Para ser más exactos, se referirá al emp_id del jefe del empleado.</span><span class="sxs-lookup"><span data-stu-id="64f2c-137">More precisely, it indicates the employee's boss's emp_id.</span></span> <span data-ttu-id="64f2c-138">Puede crear una función definida por el usuario que devuelva una tabla que contenga una fila para cada empleado que trabaje en una determinada jerarquía organizativa de un director de alto nivel.</span><span class="sxs-lookup"><span data-stu-id="64f2c-138">You can create a user-defined function that returns a table containing one row for each employee working within a particular high-level manager's organizational hierarchy.</span></span> <span data-ttu-id="64f2c-139">Puede llamar a la función fn_GetWholeTeam y diseñarla para que acepte una variable de entrada: el valor emp_id del director cuyo equipo quiere recuperar.</span><span class="sxs-lookup"><span data-stu-id="64f2c-139">You might call the function fn_GetWholeTeam, and design it to take an input variable - the emp_id of the manager whose team you want to retrieve.</span></span>  
  
 <span data-ttu-id="64f2c-140">Puede escribir una consulta que utilice la función fn_GetWholeTeam como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="64f2c-140">You can write a query that uses the fn_GetWholeTeam function as a source of data.</span></span> <span data-ttu-id="64f2c-141">El código SQL resultante puede presentar el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="64f2c-141">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *   
FROM   
     fn_GetWholeTeam ('VPA30890F')  
  
```  
  
 <span data-ttu-id="64f2c-142">"VPA30890F" es el emp_id del director cuya organización desea recuperar.</span><span class="sxs-lookup"><span data-stu-id="64f2c-142">"VPA30890F" is the emp_id of the manager whose organization you want to retrieve.</span></span> <span data-ttu-id="64f2c-143">Para obtener más información sobre cómo agregar una función definida por el usuario a una consulta, consulte [Agregar tablas a las consultas (Visual Database Tools)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64f2c-143">For more information about adding a user-defined function to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="64f2c-144">Para obtener una descripción completa de las funciones definidas por el usuario, consulte [Funciones definidas por el usuario](../../relational-databases/user-defined-functions/user-defined-functions.md).</span><span class="sxs-lookup"><span data-stu-id="64f2c-144">For a complete description of user-defined functions, see [User-Defined Functions](../../relational-databases/user-defined-functions/user-defined-functions.md).</span></span>  
  
  
