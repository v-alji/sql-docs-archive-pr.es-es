---
title: Crear alias de columna (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: febe7ed27ed10a283cab549bc65299577d69761c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670745"
---
# <a name="create-column-aliases-visual-database-tools"></a><span data-ttu-id="87674-102">Crear alias de columna (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="87674-102">Create Column Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="87674-103">Puede crear alias para nombres de columnas con el fin de facilitar el trabajo con nombres de columnas, cálculos y valores de resumen.</span><span class="sxs-lookup"><span data-stu-id="87674-103">You can create aliases for column names to make it easier to work with column names, calculations, and summary values.</span></span> <span data-ttu-id="87674-104">Por ejemplo, puede crear un alias de columna para:</span><span class="sxs-lookup"><span data-stu-id="87674-104">For example, you can create a column alias to:</span></span>  
  
-   <span data-ttu-id="87674-105">Crear un nombre de columna, como "Importe total", para una expresión como `(quantity * unit_price)` o para una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="87674-105">Create a column name, such as "Total Amount," for an expression such as `(quantity * unit_price)` or for an aggregate function.</span></span>  
  
-   <span data-ttu-id="87674-106">Crear un nombre abreviado de un nombre de columna, como `"d_id"` para `"discounts.stor_id."`</span><span class="sxs-lookup"><span data-stu-id="87674-106">Create a shortened form of a column name, such as `"d_id"` for `"discounts.stor_id."`</span></span>  
  
 <span data-ttu-id="87674-107">Cuando haya definido un alias de columna, podrá utilizarlo en una consulta Select para especificar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="87674-107">After you have defined a column alias, you can use the alias in a Select query to specify query output.</span></span>  
  
### <a name="to-create-a-column-alias"></a><span data-ttu-id="87674-108">Para crear un alias de columna</span><span class="sxs-lookup"><span data-stu-id="87674-108">To create a column alias</span></span>  
  
1.  <span data-ttu-id="87674-109">En el panel **Criterios**, busque la fila que contiene la columna de datos para la que desea crear un alias y, si es necesario, márquela como columna de resultados.</span><span class="sxs-lookup"><span data-stu-id="87674-109">In the **Criteria Pane**, locate the row containing the data column for which you want to create an alias, and if necessary, mark it for output.</span></span> <span data-ttu-id="87674-110">Si la columna de datos no está en la cuadrícula, agréguela.</span><span class="sxs-lookup"><span data-stu-id="87674-110">If the data column is not already in the grid, add it.</span></span>  
  
2.  <span data-ttu-id="87674-111">Escriba el alias en la columna **Alias** de la fila.</span><span class="sxs-lookup"><span data-stu-id="87674-111">In the **Alias** column for that row, enter the alias.</span></span> <span data-ttu-id="87674-112">El alias debe cumplir todas las convenciones de nomenclatura de SQL.</span><span class="sxs-lookup"><span data-stu-id="87674-112">The alias must follow all naming conventions for SQL.</span></span> <span data-ttu-id="87674-113">Si el nombre de alias escrito contiene espacios, el Diseñador de consultas y vistas colocará automáticamente delimitadores en torno al mismo.</span><span class="sxs-lookup"><span data-stu-id="87674-113">If the alias name you enter contains spaces, the Query and View Designer automatically puts delimiters around it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87674-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87674-114">See Also</span></span>  
 <span data-ttu-id="87674-115">[Agregar columnas a las consultas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="87674-115">[Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="87674-116">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="87674-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="87674-117">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="87674-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="87674-118">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="87674-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
