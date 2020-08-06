---
title: Seleccionar filas que no coinciden con un valor (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 412ec93cbfedc87e92da9e86c7e4c7455919722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747385"
---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a><span data-ttu-id="bebc2-102">Seleccionar filas que no coinciden con un valor (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bebc2-102">Select Rows That Do Not Match a Value (Visual Database Tools)</span></span>
  <span data-ttu-id="bebc2-103">Para buscar filas que no coinciden con un valor, utilice el operador NOT.</span><span class="sxs-lookup"><span data-stu-id="bebc2-103">To find rows that do not match a value, use the NOT operator.</span></span>  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a><span data-ttu-id="bebc2-104">Para buscar filas que no coincidan con un valor</span><span class="sxs-lookup"><span data-stu-id="bebc2-104">To find rows that do not match a value</span></span>  
  
1.  <span data-ttu-id="bebc2-105">Si aún no lo ha hecho, agregue al [panel Criterios](visual-database-tools.md)las columnas o expresiones que desee utilizar en la condición de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bebc2-105">If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="bebc2-106">Busque la fila que contiene la columna de datos o la expresión que desea buscar y, a continuación, en la columna de cuadrícula **Filtro** , escriba el operador NOT seguido de un valor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bebc2-106">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.</span></span>  
  
 <span data-ttu-id="bebc2-107">Por ejemplo, para buscar todas las filas de una tabla `products` cuyos valores de la columna de código de producto empiecen por un carácter distinto de "A", escriba una condición de búsqueda como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="bebc2-107">For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:</span></span>  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a><span data-ttu-id="bebc2-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bebc2-108">See Also</span></span>  
 <span data-ttu-id="bebc2-109">[Reglas para especificar valores de búsqueda &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bebc2-109">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="bebc2-110">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bebc2-110">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
