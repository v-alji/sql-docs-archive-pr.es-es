---
title: Quitar tablas de las consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting tables
- removing tables
- dropping tables
- queries [SQL Server], tables
ms.assetid: 8fea0b4f-99b7-4050-8d6f-a97ffb839619
author: stevestein
ms.author: sstein
ms.openlocfilehash: fab5380e13742f3cd289ce17f26ad2e5fb9089ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672350"
---
# <a name="remove-tables-from-queries-visual-database-tools"></a><span data-ttu-id="a22ad-102">Quitar tablas de las consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a22ad-102">Remove Tables from Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="a22ad-103">Puede quitar una tabla, o cualquier objeto con valores de tabla, de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a22ad-103">You can remove a table - or any table-valued object - from the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a22ad-104">Si se quitan tablas u objetos con valores de tabla, no se eliminan de la base de datos; solo se quitan de la consulta actual.</span><span class="sxs-lookup"><span data-stu-id="a22ad-104">Removing a table or table-valued object does not delete anything from the database; it only removes it from the current query.</span></span> <span data-ttu-id="a22ad-105">Para obtener más información sobre cómo quitar una tabla de una base de datos, vea [Delete tables &#40;Motor de base de datos&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a22ad-105">For details about removing a table from a database, see [Delete Tables &#40;Database Engine&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span></span>  
  
### <a name="to-remove-a-table-or-table-structured-object"></a><span data-ttu-id="a22ad-106">Para quitar una tabla o un objeto con estructura de tabla</span><span class="sxs-lookup"><span data-stu-id="a22ad-106">To remove a table or table-structured object</span></span>  
  
-   <span data-ttu-id="a22ad-107">En el **panel Diagrama**, seleccione la tabla, vista, función definida por el usuario, sinónimo o consulta y, a continuación, presione la tecla Supr, o bien haga clic con el botón derecho en el objeto y elija **Quitar** en el cuadro de diálogo que aparecerá.</span><span class="sxs-lookup"><span data-stu-id="a22ad-107">In the **Diagram Pane**, select the table, view, user-defined function, synonym, or query, and then press DELETE, or right-click the object and then choose **Remove** in the resulting dialog box.</span></span> <span data-ttu-id="a22ad-108">Puede seleccionar y quitar varios objetos a la vez.</span><span class="sxs-lookup"><span data-stu-id="a22ad-108">You can select and remove multiple objects at one time.</span></span>  
  
     <span data-ttu-id="a22ad-109">O bien</span><span class="sxs-lookup"><span data-stu-id="a22ad-109">-or-</span></span>  
  
-   <span data-ttu-id="a22ad-110">Quite todas las referencias al objeto en el **panel SQL**.</span><span class="sxs-lookup"><span data-stu-id="a22ad-110">Remove all references to the object in the **SQL Pane.**</span></span>  
  
 <span data-ttu-id="a22ad-111">Cuando quite una tabla o un objeto con valores de tabla, el Diseñador de consultas y vistas quitará automáticamente las combinaciones que relacionen la tabla o el objeto con valores de tabla, así como las referencias a las columnas del objeto en el **panel SQL** y el **panel Criterios**.</span><span class="sxs-lookup"><span data-stu-id="a22ad-111">When you remove a table or table-valued object, the Query and View Designer automatically removes joins that involve that table or table-valued object and removes references to the object's columns in the **SQL Pane** and **Criteria Pane**.</span></span> <span data-ttu-id="a22ad-112">Sin embargo, si la consulta contiene expresiones complejas que hacen referencia al objeto, éste no se quitará automáticamente hasta que se hayan quitado todas las referencias al mismo.</span><span class="sxs-lookup"><span data-stu-id="a22ad-112">However, if the query contains complex expressions involving the object, the object is not automatically removed until all references to it are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a22ad-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a22ad-113">See Also</span></span>  
 <span data-ttu-id="a22ad-114">[Agregar tablas a las consultas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a22ad-114">[Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="a22ad-115">[Crear alias de tabla &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a22ad-115">[Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a22ad-116">[Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a22ad-116">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a22ad-117">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a22ad-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a22ad-118">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a22ad-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
