---
title: Excluir filas duplicadas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- row duplicates [SQL Server]
- duplicate rows
- row excluded in search [SQL Server]
- result sets [SQL Server], duplicate values
- excluding rows
ms.assetid: ab35a363-421d-4665-946b-ae3f6397af50
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b396f2738f6895684d828884d4822ea9165e0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676793"
---
# <a name="exclude-duplicate-rows-visual-database-tools"></a><span data-ttu-id="b8ab7-102">Excluir filas duplicadas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b8ab7-102">Exclude Duplicate Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="b8ab7-103">Si solo desea ver los valores únicos de un conjunto de resultados, puede indicar que se excluyan los duplicados del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b8ab7-103">If you want to see only unique values in a result set, you can specify that you want to exclude duplicates from the result set.</span></span>  
  
### <a name="to-exclude-duplicate-rows-from-the-result-set"></a><span data-ttu-id="b8ab7-104">Para excluir filas duplicadas del conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="b8ab7-104">To exclude duplicate rows from the result set</span></span>  
  
1.  <span data-ttu-id="b8ab7-105">Haga clic con el botón derecho en el fondo del panel Diagrama y, luego, elija **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b8ab7-105">Right-click the background of the Diagram pane, then choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="b8ab7-106">En la ventana Propiedades, haga clic en **Valores DISTINCT** y establezca el valor en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b8ab7-106">In the Property window, click **Distinct values** and set the value to **Yes**.</span></span>  
  
     <span data-ttu-id="b8ab7-107">El Diseñador de consultas y vistas inserta la palabra clave DISTINCT delante de la lista de columnas mostradas en la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="b8ab7-107">The Query and View Designer inserts the keyword DISTINCT in front of the list of display columns in the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8ab7-108">Si utiliza la palabra clave DISTINCT , es posible que no pueda modificar el conjunto de resultados en el panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="b8ab7-108">If you use the DISTINCT keyword you may not be able to modify the result set in the results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ab7-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8ab7-109">See Also</span></span>  
 <span data-ttu-id="b8ab7-110">[Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b8ab7-110">[Specify Search Criteria &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b8ab7-111">Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b8ab7-111">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
