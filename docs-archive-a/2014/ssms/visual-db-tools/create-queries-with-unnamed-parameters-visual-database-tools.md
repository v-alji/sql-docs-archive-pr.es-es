---
title: Crear consultas con parámetros sin nombre (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0ea53afd1fa4d44390f5805d6b28494428608b90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662464"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a><span data-ttu-id="01348-102">Crear consultas con parámetros sin nombre (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="01348-102">Create Queries with Unnamed Parameters (Visual Database Tools)</span></span>
  <span data-ttu-id="01348-103">Puede crear una consulta con un parámetro sin nombre incluyendo un signo de interrogación (?) como marcador de posición para un valor literal.</span><span class="sxs-lookup"><span data-stu-id="01348-103">You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value.</span></span> <span data-ttu-id="01348-104">El Diseñador de consultas y vistas le asignará un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="01348-104">Query and View Designer will give it a temporary name.</span></span> <span data-ttu-id="01348-105">Puede especificar tantos parámetros sin nombre como necesite en la consulta.</span><span class="sxs-lookup"><span data-stu-id="01348-105">You can specify as many unnamed parameters in the query as you need.</span></span>  
  
 <span data-ttu-id="01348-106">Cuando se ejecute la consulta en el Diseñador de consultas y vistas, se mostrará el cuadro de diálogo Parámetros de la consulta con el nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="01348-106">When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.</span></span>  
  
### <a name="to-specify-an-unnamed-parameter"></a><span data-ttu-id="01348-107">Para especificar un parámetro sin nombre</span><span class="sxs-lookup"><span data-stu-id="01348-107">To specify an unnamed parameter</span></span>  
  
1.  <span data-ttu-id="01348-108">Agregue las columnas o expresiones que desea buscar al [panel Criterios](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01348-108">Add the columns or expressions that you want to search to the [Criteria pane](visual-database-tools.md).</span></span> <span data-ttu-id="01348-109">Si no desea que las columnas o expresiones de búsqueda aparezcan en los resultados de la consulta, quítelas como columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="01348-109">If you do not want the search columns or expressions to appear in the query output, remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="01348-110">Busque la fila que contiene la columna de datos o expresión que va a buscar y, luego, en la columna de cuadrícula **Filtro** , escriba un signo de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="01348-110">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).</span></span>  
  
     <span data-ttu-id="01348-111">De forma predeterminada, el Diseñador de consultas y vistas agrega el operador "=".</span><span class="sxs-lookup"><span data-stu-id="01348-111">By default, the Query and View Designer adds the "=" operator.</span></span> <span data-ttu-id="01348-112">No obstante, puede editar la celda para sustituir el operador por ">", "<" o cualquier otro operador de comparación SQL.</span><span class="sxs-lookup"><span data-stu-id="01348-112">However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01348-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01348-113">See Also</span></span>  
 [<span data-ttu-id="01348-114">Realizar consultas con parámetros &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="01348-114">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
