---
title: Combinar tablas automáticamente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- joins [SQL Server], creating
- joins [SQL Server], automatic
ms.assetid: f152af82-bcb6-49ca-af19-48cdb7fc9ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: d05100f801d972759c1b5c105814f5cdbdccf84f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743838"
---
# <a name="join-tables-automatically-visual-database-tools"></a><span data-ttu-id="4744a-102">Combinar tablas automáticamente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4744a-102">Join Tables Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="4744a-103">Al agregar dos o más tablas a una consulta, el [Diseñador de consultas y vistas](visual-database-tools.md) intenta determinar si están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4744a-103">When you add two or more tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to determine if they are related.</span></span> <span data-ttu-id="4744a-104">Si lo están, el Diseñador de consultas y vistas coloca automáticamente líneas de combinación entre los rectángulos que representan las tablas o los objetos con estructura de tabla.</span><span class="sxs-lookup"><span data-stu-id="4744a-104">If they are, the Query and View Designer automatically puts join lines between the rectangles representing the tables or table-structured objects.</span></span>  
  
 <span data-ttu-id="4744a-105">El Diseñador de consultas y vistas determinará que las tablas están combinadas si:</span><span class="sxs-lookup"><span data-stu-id="4744a-105">The Query and View Designer will recognize tables as joined if:</span></span>  
  
-   <span data-ttu-id="4744a-106">La base de datos contiene información que especifica que las tablas están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4744a-106">The database contains information that specifies that the tables are related.</span></span>  
  
-   <span data-ttu-id="4744a-107">Dos columnas, una en cada tabla, tienen el mismo nombre y tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="4744a-107">If two columns, one in each table, have the same name and data type.</span></span> <span data-ttu-id="4744a-108">La columna debe ser una clave principal en al menos una de las tablas.</span><span class="sxs-lookup"><span data-stu-id="4744a-108">The column must be a primary key in at least one of the tables.</span></span> <span data-ttu-id="4744a-109">Por ejemplo, al agregar las tablas `employee` y `jobs` , si la columna `job_id` es la clave principal de la tabla `jobs` y cada tabla tiene una columna llamada `job_id` con el mismo tipo de datos, el Diseñador de consultas y vistas combinará automáticamente las tablas.</span><span class="sxs-lookup"><span data-stu-id="4744a-109">For example, if you add `employee` and `jobs` tables, if the `job_id` column is the primary key in the `jobs` table, and if each table has a column called `job_id` with the same data type, the Query and View Designer will automatically join the tables.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4744a-110">El Diseñador de consultas y vistas creará solo una combinación basada en columnas con el mismo nombre y tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="4744a-110">The Query and View Designer will create only one join based on columns with the same name and data type.</span></span> <span data-ttu-id="4744a-111">Si son posibles varias combinaciones, el Diseñador de consultas y vistas se detendrá después de crear una combinación basada en el primer conjunto de columnas coincidentes que encuentre.</span><span class="sxs-lookup"><span data-stu-id="4744a-111">If more than one join is possible, the Query and View Designer stops after creating a join based on the first set of matching columns that it finds.</span></span>  
  
-   <span data-ttu-id="4744a-112">El Diseñador de consultas y vistas detecta que una condición de búsqueda (una cláusula WHERE) es realmente una condición de combinación.</span><span class="sxs-lookup"><span data-stu-id="4744a-112">The Query and View Designer detects that a search condition (a WHERE clause) is actually a join condition.</span></span> <span data-ttu-id="4744a-113">Por ejemplo, puede agregar las tablas `employee` y `jobs`y crear, a continuación, una condición de búsqueda que busque el mismo valor en la columna `job_id` de ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="4744a-113">For example, you might add the tables `employee` and `jobs`, then create a search condition that searches for the same value in the `job_id` column of both tables.</span></span> <span data-ttu-id="4744a-114">En este caso, el Diseñador de consultas y vistas detecta que la condición de búsqueda genera una combinación y, a continuación, crea una condición de combinación a partir de la condición de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4744a-114">When you do, the Query and View Designer detects that the search condition results in a join, and then creates a join condition based on the search condition.</span></span>  
  
 <span data-ttu-id="4744a-115">Si el Diseñador de consultas y vistas ha creado una combinación que no es adecuada para la consulta, puede modificarla o quitarla.</span><span class="sxs-lookup"><span data-stu-id="4744a-115">If the Query and View Designer has created a join that is not suitable to your query, you can modify the join or remove it.</span></span> <span data-ttu-id="4744a-116">Para detalles, consulte [Modificar operadores de combinación &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) y [Quitar combinaciones &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4744a-116">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) and [Remove Joins &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="4744a-117">Si el Diseñador de consultas y vistas no combina automáticamente las tablas de la consulta, puede crear una combinación de forma manual.</span><span class="sxs-lookup"><span data-stu-id="4744a-117">If the Query and View Designer does not automatically join the tables in your query, you can create a join yourself.</span></span> <span data-ttu-id="4744a-118">Para detalles, consulte [Combinar tablas manualmente &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4744a-118">For details, see [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4744a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4744a-119">See Also</span></span>  
 <span data-ttu-id="4744a-120">[Cómo representa combinaciones el diseñador de consultas y vistas &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4744a-120">[How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4744a-121">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4744a-121">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4744a-122">Realizar consultas con combinaciones &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4744a-122">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
