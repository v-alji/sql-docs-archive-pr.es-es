---
title: Especificar la cláusula TOP en consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- TOP clause, queries
- percentage of rows returned [SQL Server]
- number of rows
- search conditions [SQL Server], TOP clause
- restricting rows returned
- search criteria [SQL Server], limiting rows returned
- inspecting portion of results
- limiting rows returned
- search criteria [SQL Server], TOP clause
ms.assetid: ba7d7c10-9bb3-4d9b-90b0-5fa94ecae59b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8228779703b1bbe3753f1e2728e83b4b5c3a3d17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749546"
---
# <a name="specify-the-top-clause-in-queries-visual-database-tools"></a><span data-ttu-id="e3ccc-102">Especificar la cláusula TOP en consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e3ccc-102">Specify the TOP Clause in Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="e3ccc-103">La cláusula TOP devuelve solo las primeras *n* o *n percent* filas de una consulta.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-103">The TOP clause returns only the first *n* or *n percent* rows from a query.</span></span> <span data-ttu-id="e3ccc-104">La cláusula TOP resulta muy útil si se desea inspeccionar una parte de los resultados para averiguar si el funcionamiento de la consulta es el esperado, sin tener que emplear los recursos necesarios para devolver todos los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-104">The TOP clause is useful when you want to inspect a portion of your results to find out if your query does what you expect it to do, without taking the resources necessary to return all of the query results.</span></span>  
  
### <a name="to-specify-the-top-clause-in-queries"></a><span data-ttu-id="e3ccc-105">Para especificar la cláusula TOP en las consultas</span><span class="sxs-lookup"><span data-stu-id="e3ccc-105">To specify the TOP clause in queries</span></span>  
  
1.  <span data-ttu-id="e3ccc-106">Abra una consulta del Explorador de soluciones o cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-106">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="e3ccc-107">En el menú **Ver** , haga clic en **Ventana Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-107">From the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="e3ccc-108">En la **Ventana Propiedades**, busque y expanda la propiedad **Especificación superior** .</span><span class="sxs-lookup"><span data-stu-id="e3ccc-108">In the **Properties Window**, locate and expand the **Top Specification** property.</span></span>  
  
4.  <span data-ttu-id="e3ccc-109">Haga clic en la propiedad secundaria **(Superior)** y establézcala en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-109">Click the **(Top)** child property and set it to **Yes**.</span></span>  
  
5.  <span data-ttu-id="e3ccc-110">En la propiedad secundaria **Expresión** , escriba una expresión que tenga un resultado numérico (por ejemplo, "10" o "2\*5").</span><span class="sxs-lookup"><span data-stu-id="e3ccc-110">In the **Expression** child property, type an expression that has a numeric result (for example, "10" or "2\*5").</span></span>  
  
6.  <span data-ttu-id="e3ccc-111">Haga clic en la propiedad secundaria **Porcentaje** e indique si la propiedad **Expresión** debe tratarse como un porcentaje de todas las filas devueltas (Sí) o como el número absoluto de filas devueltas (No).</span><span class="sxs-lookup"><span data-stu-id="e3ccc-111">Click the **Percent** child property and indicate whether or not to treat the **Expression** property as a percentage of all rows returned (Yes) or as the absolute number of rows returned (No).</span></span>  
  
7.  <span data-ttu-id="e3ccc-112">Si la consulta utiliza la cláusula ORDER BY, haga clic en la propiedad secundaria **Con valores equivalentes** y elija **Sí** para mostrar todas las filas de un grupo si solo parte del grupo está incluida o **No** para truncarlos.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-112">If your query uses the ORDER BY clause, click the **With Ties** child property and choose **Yes** to display all rows in a group if only part of the group is included or **No** to truncate them.</span></span>  
  
 <span data-ttu-id="e3ccc-113">Al realizar el procedimiento anterior, observe que la cláusula TOP que se muestra en el panel SQL cambia para reflejar la configuración actual de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-113">As you work through the preceding procedure, notice that the TOP clause, displayed in the SQL pane, changes to reflect the current settings of the properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3ccc-114">También puede cambiar los valores de las propiedades secundarias de **Especificación superior** editando el cláusula TOP en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="e3ccc-114">You can also change the values of the child properties of the **Top Specification** by editing the TOP clause in the SQL pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ccc-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3ccc-115">See Also</span></span>  
 <span data-ttu-id="e3ccc-116">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e3ccc-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e3ccc-117">Propiedades de la consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e3ccc-117">Query Properties &#40;Visual Database Tools&#41;</span></span>](query-properties-visual-database-tools.md)  
  
  
