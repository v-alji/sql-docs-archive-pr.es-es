---
title: Especificar condiciones de búsqueda (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- choosing search criteria
- search conditions [SQL Server], specifying
- search criteria [SQL Server], specifying conditions
ms.assetid: 18e2c759-68ec-4efe-b208-2f73418cd9bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa5dab8326de079c385a3a508bc1b01b1ee1247d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672346"
---
# <a name="specify-search-conditions-visual-database-tools"></a><span data-ttu-id="434c2-102">Especificar condiciones de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="434c2-102">Specify Search Conditions (Visual Database Tools)</span></span>
  <span data-ttu-id="434c2-103">Puede especificar las filas de datos que aparecen en la consulta mediante condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="434c2-103">You can specify the data rows that appear in your query by specifying search conditions.</span></span> <span data-ttu-id="434c2-104">Por ejemplo, si realiza una consulta en una tabla `employee` , puede especificar que se busquen solo los empleados que trabajan en una determinada región.</span><span class="sxs-lookup"><span data-stu-id="434c2-104">For example, if you are querying an `employee` table, you can specify that you want to find only the employees who work in a particular region.</span></span>  
  
 <span data-ttu-id="434c2-105">Las condiciones de búsqueda se especifican mediante una expresión.</span><span class="sxs-lookup"><span data-stu-id="434c2-105">You specify search conditions using an expression.</span></span> <span data-ttu-id="434c2-106">Normalmente, las expresiones constan de un operador y un valor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="434c2-106">Most commonly the expression consists of an operator and a search value.</span></span> <span data-ttu-id="434c2-107">Por ejemplo, para buscar los empleados de una región de ventas determinada, podría especificar el siguiente criterio de búsqueda para la columna `region` :</span><span class="sxs-lookup"><span data-stu-id="434c2-107">For example, to find employees in a particular sales region, you might specify the following search criterion for the `region` column:</span></span>  
  
```  
='UK'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="434c2-108">Si trabaja con varias tablas, el Diseñador de consultas y vistas examina cada condición de búsqueda para determinar si la comparación realizada da lugar a una combinación.</span><span class="sxs-lookup"><span data-stu-id="434c2-108">If you are working with multiple tables, the Query and View Designer examines each search condition to determine whether the comparison you are making results in a join.</span></span> <span data-ttu-id="434c2-109">Si es así, el Diseñador de consultas y vistas convierte automáticamente la condición de búsqueda en una combinación.</span><span class="sxs-lookup"><span data-stu-id="434c2-109">If so, the Query and View Designer automatically converts the search condition into a join.</span></span> <span data-ttu-id="434c2-110">Para más información, consulte [Combinar tablas automáticamente &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="434c2-110">For more information, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-specify-search-conditions"></a><span data-ttu-id="434c2-111">Para especificar condiciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="434c2-111">To specify search conditions</span></span>  
  
1.  <span data-ttu-id="434c2-112">Si aún no lo ha hecho, agregue al panel Criterios las columnas o expresiones que desee utilizar en la condición de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="434c2-112">If you have not done so already, add the columns or expressions that you want to use within your search condition to the Criteria pane.</span></span>  
  
     <span data-ttu-id="434c2-113">Si va a crear una consulta SELECT y no desea que las columnas o expresiones de búsqueda aparezcan en el resultado de la consulta, borre la columna **Resultados** de cada columna o expresión de búsqueda para que no aparezcan como columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="434c2-113">If you are creating a Select query and do not want the search columns or expressions to appear in the query output, clear the **Output** column for each search column or expression to remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="434c2-114">Busque la fila que contiene la columna de datos o la expresión que desea buscar y, a continuación, en la columna **Filtro** , escriba una condición de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="434c2-114">Locate the row containing the data column or expression to search, and then in the **Filter** column, enter a search condition.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="434c2-115">Si no especifica ningún operador, el Diseñador de consultas y vistas inserta automáticamente el operador de igualdad "=".</span><span class="sxs-lookup"><span data-stu-id="434c2-115">If you do not enter an operator, the Query and View Designer automatically inserts the equality operator "=".</span></span>  
  
 <span data-ttu-id="434c2-116">El Diseñador de consultas y vistas actualiza la instrucción SQL en el [panel SQL](sql-pane-visual-database-tools.md) agregando o modificando la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="434c2-116">The Query and View Designer updates the SQL statement in the [SQL Pane](sql-pane-visual-database-tools.md) by adding or modifying the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434c2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="434c2-117">See Also</span></span>  
 <span data-ttu-id="434c2-118">[Reglas para especificar valores de búsqueda &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="434c2-118">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="434c2-119">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="434c2-119">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
