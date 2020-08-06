---
title: Agregar columnas a las consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- queries [SQL Server], columns
- adding columns
ms.assetid: 82f3ba72-3d72-4fb1-8179-2a953a782787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 49c6e575eea2d4437be1f16b400ca22120471fcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670761"
---
# <a name="add-columns-to-queries-visual-database-tools"></a><span data-ttu-id="d5252-102">Agregar columnas a las consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d5252-102">Add Columns to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="d5252-103">Para utilizar una columna en una consulta, deberá agregarla a la consulta.</span><span class="sxs-lookup"><span data-stu-id="d5252-103">To use a column in a query, you must add it to the query.</span></span> <span data-ttu-id="d5252-104">Puede agregar una columna para mostrarla en los resultados de la consulta, para utilizarla al ordenar, para realizar búsquedas en el contenido de la columna o para resumir su contenido.</span><span class="sxs-lookup"><span data-stu-id="d5252-104">You might add a column to display it in query output, to use it for sorting, to search the contents of the column, or to summarize its contents.</span></span> <span data-ttu-id="d5252-105">Puede decidir cuáles de las columnas que utiliza en la consulta se van a incluir en el panel Resultados cuando la consulta se ejecute.</span><span class="sxs-lookup"><span data-stu-id="d5252-105">You can decide which of the columns you use in the query are included in the results pane when the query is run.</span></span> <span data-ttu-id="d5252-106">Para más información, consulte [Quitar columnas de los resultados de una consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d5252-106">For more information see [Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5252-107">Para ver el tipo de datos de una columna en el Diseñador de consultas y vistas, seleccione la tabla o el objeto con valores de tabla en el **panel Diagrama** y, en la ventana Propiedades, haga clic en Lista de columnas.</span><span class="sxs-lookup"><span data-stu-id="d5252-107">To view the data type of a column in Query and View Designer; select the table or table-valued object in the **Diagram Pane** and in the properties window click Column List.</span></span> <span data-ttu-id="d5252-108">Después, haga clic en los **puntos suspensivos (...)** para abrir el cuadro de diálogo **Lista de columnas**.</span><span class="sxs-lookup"><span data-stu-id="d5252-108">Then click the **ellipses (...)** to open the **Column List** dialog box.</span></span>  
  
 <span data-ttu-id="d5252-109">Siempre que utilice una columna en una consulta, también podrá utilizar una expresión formada por cualquier combinación de columnas, literales, operadores y funciones.</span><span class="sxs-lookup"><span data-stu-id="d5252-109">Wherever you use a column in a query, you can also use an expression that can consist of any combination of columns, literals, operators, and functions.</span></span>  
  
### <a name="to-add-an-individual-column"></a><span data-ttu-id="d5252-110">Para agregar una columna individual</span><span class="sxs-lookup"><span data-stu-id="d5252-110">To add an individual column</span></span>  
  
-   <span data-ttu-id="d5252-111">En el **panel Diagrama**, active la casilla situada junto a la columna que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="d5252-111">In the **Diagram Pane**, select the check box next to the column that you want to include.</span></span>  
  
     <span data-ttu-id="d5252-112">O bien</span><span class="sxs-lookup"><span data-stu-id="d5252-112">-or-</span></span>  
  
-   <span data-ttu-id="d5252-113">En el **panel Criterios**, vaya a la primera fila en blanco de la cuadrícula, haga clic en el campo de la columna **Columna** y seleccione un nombre de columna de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5252-113">In the **Criteria Pane**, move to the first blank grid row, click the field in the **Column** column, and select a column name from the drop-down list.</span></span>  
  
### <a name="to-add-all-columns-for-one-table-or-table-valued-object"></a><span data-ttu-id="d5252-114">Para agregar todas las columnas correspondientes a una tabla o a un objeto con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="d5252-114">To add all columns for one table or table-valued object</span></span>  
  
-   <span data-ttu-id="d5252-115">En el **panel Diagrama**, active la casilla situada junto a \*\* \* (todas las columnas)\*\*.</span><span class="sxs-lookup"><span data-stu-id="d5252-115">In the **Diagram Pane**, select the check box next to **\*(All Columns)**.</span></span>  
  
### <a name="to-add-all-columns-for-all-tables-and-table-structured-objects"></a><span data-ttu-id="d5252-116">Para agregar todas las columnas correspondientes a todas las tablas y todos los objetos con estructura de tabla</span><span class="sxs-lookup"><span data-stu-id="d5252-116">To add all columns for all tables and table-structured objects</span></span>  
  
1.  <span data-ttu-id="d5252-117">Compruebe que no hay ninguna línea de combinación seleccionada en el **panel de operaciones de tablas** .</span><span class="sxs-lookup"><span data-stu-id="d5252-117">Make sure no join lines in the **Table Operations Pane** are selected.</span></span>  
  
2.  <span data-ttu-id="d5252-118">Haga clic con el botón derecho en el espacio vacío de la ventana Diseño y elija **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="d5252-118">Right-click in the empty space of the Design window and choose **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="d5252-119">En la ventana Propiedades, haga clic en **Mostrar todas las columnas** y elija **Sí** o **No** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5252-119">In the Properties window click **Output all columns** and choose **Yes** or **No** from the dropdown list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5252-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5252-120">See Also</span></span>  
 <span data-ttu-id="d5252-121">[Quitar columnas de los resultados de una consulta &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5252-121">[Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="d5252-122">[Quitar columnas de las consultas &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5252-122">[Remove Columns from Queries &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d5252-123">[Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5252-123">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d5252-124">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5252-124">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d5252-125">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d5252-125">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
