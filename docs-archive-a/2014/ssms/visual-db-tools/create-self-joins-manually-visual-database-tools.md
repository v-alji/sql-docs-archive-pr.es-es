---
title: Crear autocombinaciones manualmente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- self-joins
- manual joins [SQL Server]
- joins [SQL Server], self
ms.assetid: 910ed516-cb84-481b-95d0-cba3e89afdba
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31e125fdfe0f7f285ea679cfe85356d1aa10353a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673989"
---
# <a name="create-self-joins-manually-visual-database-tools"></a><span data-ttu-id="cf525-102">Crear autocombinaciones manualmente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="cf525-102">Create Self-Joins Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="cf525-103">Puede combinar una tabla consigo misma aunque no tenga una relación reflexiva en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cf525-103">You can join a table to itself even if the table does not have a reflexive relationship in the database.</span></span> <span data-ttu-id="cf525-104">Por ejemplo, puede utilizar una autocombinación para buscar pares de autores que residan en la misma ciudad.</span><span class="sxs-lookup"><span data-stu-id="cf525-104">For example, you can use a self-join to find pairs of authors living in the same city.</span></span>  
  
 <span data-ttu-id="cf525-105">Al igual que el resto de las combinaciones, una autocombinación requiere al menos dos tablas.</span><span class="sxs-lookup"><span data-stu-id="cf525-105">As with any join, a self-join requires at least two tables.</span></span> <span data-ttu-id="cf525-106">La diferencia reside en que, en lugar de agregar una segunda tabla a la consulta, se agrega una segunda instancia de la misma tabla.</span><span class="sxs-lookup"><span data-stu-id="cf525-106">The difference is that, instead of adding a second table to the query, you add a second instance of the same table.</span></span> <span data-ttu-id="cf525-107">De ese modo, puede comparar una columna de la primera instancia de la tabla con la misma columna de la segunda instancia y, por tanto, comparar los valores de una columna entre sí.</span><span class="sxs-lookup"><span data-stu-id="cf525-107">That way, you can compare a column in the first instance of the table to the same column in the second instance, which allows you to compare the values in a column to each other.</span></span> <span data-ttu-id="cf525-108">El [Diseñador de consultas y vistas](visual-database-tools.md) asigna un alias a la segunda instancia de la tabla.</span><span class="sxs-lookup"><span data-stu-id="cf525-108">The [Query and View Designer](visual-database-tools.md) assigns an alias to the second instance of the table.</span></span>  
  
 <span data-ttu-id="cf525-109">Por ejemplo, si se crea una autocombinación para buscar todos los pares de autores de Berkeley, se compara la columna `city` de la primera instancia de la tabla con la columna `city` de la segunda instancia.</span><span class="sxs-lookup"><span data-stu-id="cf525-109">For example, if you are creating a self-join to find all pairs of authors within Berkeley, you compare the `city` column in the first instance of the table against the `city` column in the second instance.</span></span> <span data-ttu-id="cf525-110">La consulta resultante podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf525-110">The resulting query might look like the following:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="cf525-111">La creación de una autocombinación requiere a menudo varias condiciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="cf525-111">Creating a self-join often requires multiple join conditions.</span></span> <span data-ttu-id="cf525-112">Para comprender el motivo de este requisito, considere el resultado de la consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="cf525-112">To understand why, consider the result of the preceding query:</span></span>  
  
```  
Cheryl Carson       Cheryl Carson  
Abraham Bennet      Abraham Bennet  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="cf525-113">La primera fila es inservible; indica que Cheryl Carson vive en la misma ciudad que Cheryl Carson.</span><span class="sxs-lookup"><span data-stu-id="cf525-113">The first row is useless; it indicates that Cheryl Carson lives in the same city as Cheryl Carson.</span></span> <span data-ttu-id="cf525-114">La segunda fila también es inservible.</span><span class="sxs-lookup"><span data-stu-id="cf525-114">The second row is equally useless.</span></span> <span data-ttu-id="cf525-115">Para eliminar estos datos inútiles, agregue otra condición que conserve solo las filas de resultados en las que los dos nombres de autores correspondan a autores diferentes.</span><span class="sxs-lookup"><span data-stu-id="cf525-115">To eliminate this useless data, you add another condition retaining only those result rows in which the two author names describe different authors.</span></span> <span data-ttu-id="cf525-116">La consulta resultante podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf525-116">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             <> authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="cf525-117">El conjunto de resultados mejora:</span><span class="sxs-lookup"><span data-stu-id="cf525-117">The result set is improved:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="cf525-118">Pero las dos filas de resultados son redundantes.</span><span class="sxs-lookup"><span data-stu-id="cf525-118">But the two result rows are redundant.</span></span> <span data-ttu-id="cf525-119">En la primera se indica que Carson vive en la misma ciudad que Bennet y en la segunda, que Bennet vive en la misma ciudad que Carson.</span><span class="sxs-lookup"><span data-stu-id="cf525-119">The first says Carson lives in the same city as Bennet, and the second says the Bennet lives in the same city as Carson.</span></span> <span data-ttu-id="cf525-120">Para eliminar esta redundancia, puede cambiar la segunda condición de combinación de "no es igual a" a "menor que".</span><span class="sxs-lookup"><span data-stu-id="cf525-120">To eliminate this redundancy, you can alter the second join condition from "not equals" to "less than."</span></span> <span data-ttu-id="cf525-121">La consulta resultante podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf525-121">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             < authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="cf525-122">Y el conjunto de resultados tendría el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf525-122">And the result set looks like this:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
```  
  
### <a name="to-create-a-self-join-manually"></a><span data-ttu-id="cf525-123">Para crear una autocombinación manualmente</span><span class="sxs-lookup"><span data-stu-id="cf525-123">To create a self-join manually</span></span>  
  
1.  <span data-ttu-id="cf525-124">Agregue al [panel Diagrama](diagram-pane-visual-database-tools.md) la tabla o el objeto con valores de tabla con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="cf525-124">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the table or table-valued object you want to work with.</span></span>  
  
2.  <span data-ttu-id="cf525-125">Vuelva a agregar la misma tabla, de forma que en el panel Diagrama muestre la misma tabla u objeto con valores de tabla dos veces.</span><span class="sxs-lookup"><span data-stu-id="cf525-125">Add the same table again, so that the Diagram pane shows the same table or table-valued object twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="cf525-126">El Diseñador de consultas y vistas asigna un alias a la segunda instancia mediante la adición de un número consecutivo al nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="cf525-126">The Query and View Designer assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="cf525-127">Asimismo, el Diseñador de consultas y vistas crea una línea de combinación entre las dos repeticiones de la tabla u objeto con valores de tabla en el panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="cf525-127">In addition, the Query and View Designer creates a join line between the two occurrences of the table or table-valued object within the Diagram pane.</span></span>  
  
3.  <span data-ttu-id="cf525-128">Haga clic con el botón derecho y elija **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="cf525-128">Right-click the join line and choose **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="cf525-129">En la ventana Propiedades, haga clic en **Condición y tipo de combinación** y después en los **puntos suspensivos (...)** situados a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cf525-129">In the Properties window click **Join Condition and Type** and click the **ellipses (...)** to the right of the property.</span></span>  
  
5.  <span data-ttu-id="cf525-130">En el [cuadro de diálogo Combinar](join-dialog-box-visual-database-tools.md) , cambie el operador de comparación entre las claves principales según corresponda.</span><span class="sxs-lookup"><span data-stu-id="cf525-130">In the [Join Dialog Box](join-dialog-box-visual-database-tools.md) change the comparison operator between the primary keys as required.</span></span> <span data-ttu-id="cf525-131">Por ejemplo, puede cambiar el operador a menor que (<).</span><span class="sxs-lookup"><span data-stu-id="cf525-131">For example, you might change the operator to less than (<).</span></span>  
  
6.  <span data-ttu-id="cf525-132">Cree la otra condición de combinación (por ejemplo, authors.zip = authors1.zip) arrastrando el nombre de la columna de combinación principal de la primera aparición de la tabla u objeto con valores de tabla y colocándolo en la columna correspondiente de la segunda aparición.</span><span class="sxs-lookup"><span data-stu-id="cf525-132">Create the additional join condition (for example, authors.zip = authors1.zip) by dragging the name of the primary join column in the first occurrence of the table or table-valued object and dropping it on the corresponding column in the second occurrence.</span></span>  
  
7.  <span data-ttu-id="cf525-133">Especifique otras opciones para la consulta, como las columnas de resultados, las condiciones de búsqueda y el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="cf525-133">Specify other options for the query such as output columns, search conditions, and sort order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf525-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf525-134">See Also</span></span>  
 <span data-ttu-id="cf525-135">[Crear autocombinaciones automáticamente &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="cf525-135">[Create Self-Joins Automatically &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="cf525-136">Realizar consultas con combinaciones &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="cf525-136">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
