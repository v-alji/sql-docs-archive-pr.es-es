---
title: Crear alias de tabla (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table aliases [SQL Server]
- aliases [SQL Server], tables
ms.assetid: 49e61e85-8abf-4ca7-8c70-7e9f8f1078bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f9e6269fe6e24e8d98922094e799fbf4b5af584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673986"
---
# <a name="create-table-aliases-visual-database-tools"></a><span data-ttu-id="cda83-102">Crear alias de tabla (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="cda83-102">Create Table Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="cda83-103">Los alias facilitan el trabajo con nombres de tabla.</span><span class="sxs-lookup"><span data-stu-id="cda83-103">Aliases can make it easier to work with table names.</span></span> <span data-ttu-id="cda83-104">El uso de alias es útil cuando:</span><span class="sxs-lookup"><span data-stu-id="cda83-104">Using aliases is helpful when:</span></span>  
  
-   <span data-ttu-id="cda83-105">Desea acortar la instrucción del [panel SQL](visual-database-tools.md) y facilitar su lectura.</span><span class="sxs-lookup"><span data-stu-id="cda83-105">You want to make the statement in the [SQL Pane](visual-database-tools.md) shorter and easier to read.</span></span>  
  
-   <span data-ttu-id="cda83-106">La consulta hace referencia varias veces al nombre de tabla (como en el caso de los nombres completos de columnas) y quiere asegurarse de que la longitud de la consulta no superará un límite específico de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cda83-106">You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query.</span></span> <span data-ttu-id="cda83-107">(Algunas bases de datos imponen una longitud máxima a las consultas.)</span><span class="sxs-lookup"><span data-stu-id="cda83-107">(Some databases impose a maximum length for queries.)</span></span>  
  
-   <span data-ttu-id="cda83-108">Trabaja con varias instancias de la misma tabla (como en el caso de una autocombinación) y necesita una forma de hacer referencia a cada instancia.</span><span class="sxs-lookup"><span data-stu-id="cda83-108">You are working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.</span></span>  
  
 <span data-ttu-id="cda83-109">Por ejemplo, puede crear un alias `"e"` para el nombre de tabla `employee`_`information`y, a continuación, hacer referencia a la tabla como `"e"` en el resto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="cda83-109">For example, you can create an alias `"e"` for a table name `employee`_`information`, and then refer to the table as `"e"` throughout the rest of the query.</span></span>  
  
### <a name="to-create-an-alias-for-a-table-or-table-valued-object"></a><span data-ttu-id="cda83-110">Para crear un alias para una tabla o un objeto con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="cda83-110">To create an alias for a table or table-valued object</span></span>  
  
1.  <span data-ttu-id="cda83-111">Agregue la tabla o el objeto con valores de tabla a la consulta.</span><span class="sxs-lookup"><span data-stu-id="cda83-111">Add the table or table-valued object to your query.</span></span>  
  
2.  <span data-ttu-id="cda83-112">En el **panel Diagrama**, haga clic con el botón derecho en el objeto para el que desea crear un alias y después elija **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="cda83-112">In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="cda83-113">En la ventana **Propiedades** , escriba el alias en el campo **Alias** .</span><span class="sxs-lookup"><span data-stu-id="cda83-113">In the **Properties** window, enter the alias in the **Alias** field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda83-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cda83-114">See Also</span></span>  
 <span data-ttu-id="cda83-115">[Agregar tablas a las consultas &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="cda83-115">[Add Tables to Queries &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="cda83-116">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="cda83-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="cda83-117">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="cda83-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="cda83-118">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="cda83-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
