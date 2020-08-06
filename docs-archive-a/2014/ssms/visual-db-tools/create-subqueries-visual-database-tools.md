---
title: Crear subconsultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], subqueries
- nested queries
- subqueries [SQL Server], SQL pane
ms.assetid: 34f6b9b4-ca3a-4a4f-9594-36e513f1c547
author: stevestein
ms.author: sstein
ms.openlocfilehash: 540228839b9734992be008b5d4fb7d717176832e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673987"
---
# <a name="create-subqueries-visual-database-tools"></a><span data-ttu-id="9bd70-102">Crear subconsultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9bd70-102">Create Subqueries (Visual Database Tools)</span></span>
  <span data-ttu-id="9bd70-103">Puede utilizar los resultados de una consulta como entrada para otra consulta.</span><span class="sxs-lookup"><span data-stu-id="9bd70-103">You can use the results of one query as the input for another.</span></span> <span data-ttu-id="9bd70-104">Puede usar los resultados de una subconsulta como una instrucción que utiliza la función IN( ), el operador EXISTS o la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="9bd70-104">You can use the results of a subquery as a statement that uses the IN( ) function, the EXISTS operator, or the FROM clause.</span></span>  
  
 <span data-ttu-id="9bd70-105">Puede crear una subconsulta escribiéndola directamente en el panel SQL o copiando una consulta y pegándola en otra.</span><span class="sxs-lookup"><span data-stu-id="9bd70-105">You can create a subquery by entering it directly into the SQL pane or by copying a query and pasting it into another.</span></span>  
  
### <a name="to-define-a-subquery-in-the-sql-pane"></a><span data-ttu-id="9bd70-106">Para definir una subconsulta en el panel SQL</span><span class="sxs-lookup"><span data-stu-id="9bd70-106">To define a subquery in the SQL pane</span></span>  
  
1.  <span data-ttu-id="9bd70-107">Cree la consulta principal.</span><span class="sxs-lookup"><span data-stu-id="9bd70-107">Create the primary query.</span></span>  
  
2.  <span data-ttu-id="9bd70-108">En el panel SQL, seleccione la instrucción SQL y use **Copiar** para mover la consulta al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="9bd70-108">In the SQL pane, select the SQL statement, and then use **Copy** to move the query to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="9bd70-109">Inicie la nueva consulta y después utilice **Pegar** para mover la primera consulta a la cláusula WHERE o FROM de la nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="9bd70-109">Start the new query, and then use **Paste** to move the first query into the new query's WHERE or FROM clause.</span></span>  
  
     <span data-ttu-id="9bd70-110">Imagine, por ejemplo, que tiene dos tablas, `products` y `suppliers`y desea crear una consulta en la que se muestren todos los productos de todos los proveedores suecos.</span><span class="sxs-lookup"><span data-stu-id="9bd70-110">For example, imagine you have two tables, `products` and `suppliers`, and you want to create a query showing all products for suppliers in Sweden.</span></span> <span data-ttu-id="9bd70-111">Cree la primera consulta en la tabla `suppliers` para buscar todos los proveedores suecos:</span><span class="sxs-lookup"><span data-stu-id="9bd70-111">Create the first query on the `suppliers` table to find all Swedish suppliers:</span></span>  
  
    ```  
    SELECT supplier_id  
    FROM supplier  
    WHERE (country = 'Sweden')  
    ```  
  
     <span data-ttu-id="9bd70-112">Utilice el comando Copiar para mover esta consulta al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="9bd70-112">Use the Copy command to move this query to the Clipboard.</span></span> <span data-ttu-id="9bd70-113">Cree la segunda consulta utilizando la tabla `products` , con la información necesaria sobre los productos:</span><span class="sxs-lookup"><span data-stu-id="9bd70-113">Create the second query using the `products` table, listing the information you need about products:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    ```  
  
     <span data-ttu-id="9bd70-114">En el panel SQL, agregue una cláusula WHERE a la segunda consulta y, a continuación, pegue la primera consulta del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="9bd70-114">In the SQL pane, add a WHERE clause to the second query, then paste the first query from the Clipboard.</span></span> <span data-ttu-id="9bd70-115">Escriba la primera consulta entre paréntesis, de forma que el resultado final tenga un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9bd70-115">Place parentheses around the first query, so that the end result looks like this:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    WHERE supplier_id IN  
       (SELECT supplier_id  
      FROM supplier  
      WHERE (country = 'Sweden'))  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9bd70-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bd70-116">See Also</span></span>  
 <span data-ttu-id="9bd70-117">[Tipos de consultas admitidos &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9bd70-117">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9bd70-118">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9bd70-118">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
