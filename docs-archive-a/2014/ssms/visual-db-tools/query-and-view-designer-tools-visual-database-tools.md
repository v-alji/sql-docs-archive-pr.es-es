---
title: Herramientas Diseñador de consultas y vistas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.querydesigner
- vdt.pane.diagram
- vdt.pane.grid
- vdt.dlgbox.querybuilder
- vdt.pane.sql
- vdt.pane.results
helpviewer_keywords:
- Query Designer [SQL Server], panes
- View Designer, panes
- Query Designer [SQL Server], components
- View Designer, components
ms.assetid: 12e4b5a5-b793-4b6c-a0e5-c450c49bf26f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 29bd3fa9e171551197927aae0d1bc00446df6e7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747873"
---
# <a name="query-and-view-designer-tools-visual-database-tools"></a><span data-ttu-id="83956-102">Herramientas Diseñador de consultas y vistas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="83956-102">Query and View Designer Tools (Visual Database Tools)</span></span>
  <span data-ttu-id="83956-103">Al diseñar una consulta, una vista, una función insertada o un procedimiento almacenado de una sola instrucción, el diseñador que utiliza está formado por cuatro paneles: el panel Diagrama, el panel Criterios, el panel de SQL y el panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="83956-103">When you design a query, view, in-line function, or single-statement stored procedure, the designer you use consists of four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span>  
  
 <span data-ttu-id="83956-104">![Diseñador de consultas](../../database-engine/media//vs-queryviewdsgpanes.gif "Diseñador de consultas")</span><span class="sxs-lookup"><span data-stu-id="83956-104">![Query Designer](../../database-engine/media//vs-queryviewdsgpanes.gif "Query Designer")</span></span>  
  
-   <span data-ttu-id="83956-105">En el panel Diagrama se muestran las tablas y otros objetos con valores de tabla que se están consultando.</span><span class="sxs-lookup"><span data-stu-id="83956-105">The Diagram pane displays the tables and other table-valued objects that you are querying.</span></span> <span data-ttu-id="83956-106">Cada rectángulo representa una tabla o un objeto con valores de tabla y muestra las columnas de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="83956-106">Each rectangle represents a table or table-valued object and shows the available data columns.</span></span> <span data-ttu-id="83956-107">Las combinaciones se indican mediante líneas entre los rectángulos.</span><span class="sxs-lookup"><span data-stu-id="83956-107">Joins are indicated by lines between the rectangles.</span></span> <span data-ttu-id="83956-108">Para más información, consulte [Panel Diagrama &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="83956-108">For more information, see [Diagram Pane &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="83956-109">El panel Criterios contiene una cuadrícula con forma de hoja de cálculo en la que se especifican opciones, como qué columnas de datos mostrar, qué filas seleccionar, cómo agrupar filas, etc.</span><span class="sxs-lookup"><span data-stu-id="83956-109">The Criteria pane contains a spreadsheet-like grid in which you specify options, such as which data columns to display, what rows to select, how to group rows, and so on.</span></span> <span data-ttu-id="83956-110">Para más información, consulte [Panel Criterios &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="83956-110">For more information, see [Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="83956-111">En el panel SQL se muestra la instrucción SQL para la consulta o vista.</span><span class="sxs-lookup"><span data-stu-id="83956-111">The SQL pane displays the SQL statement for the query or view.</span></span> <span data-ttu-id="83956-112">Puede editar la instrucción SQL creada por el Diseñador o puede especificar una instrucción SQL propia.</span><span class="sxs-lookup"><span data-stu-id="83956-112">You can edit the SQL statement created by the Designer or you can enter your own SQL statement.</span></span> <span data-ttu-id="83956-113">Resulta especialmente útil para escribir instrucciones SQL que no se pueden crear mediante los paneles Diagrama y Cuadrícula, como las consultas de unión.</span><span class="sxs-lookup"><span data-stu-id="83956-113">It is particularly useful for entering SQL statements that cannot be created using the Diagram and Criteria panes, such as union queries.</span></span> <span data-ttu-id="83956-114">Para más información, consulte [Panel SQL &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="83956-114">For more information, see [SQL Pane &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="83956-115">En el panel Resultados se muestra una cuadrícula con datos recuperados por la consulta o vista.</span><span class="sxs-lookup"><span data-stu-id="83956-115">The Results pane shows a grid with data retrieved by the query or view.</span></span> <span data-ttu-id="83956-116">En el panel del Diseñador de consultas y vistas, se muestran los resultados de la consulta SELECT ejecutada más recientemente.</span><span class="sxs-lookup"><span data-stu-id="83956-116">In the Query and View Designer, the pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="83956-117">Puede modificar la base de datos mediante la edición de los valores de las celdas de la cuadrícula y puede agregar filas o eliminarlas.</span><span class="sxs-lookup"><span data-stu-id="83956-117">You can modify the database by editing values in the cells of the grid, and you can add or delete rows.</span></span> <span data-ttu-id="83956-118">Para más información, consulte [Panel Resultados &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="83956-118">For more information, see [Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="83956-119">Puede crear una consulta o una vista en cualquiera de los paneles; para hacer aparecer una columna, puede elegirla en el panel Diagrama, puede introducirla en el panel Criterios o puede incluirla en la instrucción SQL del panel de SQL.</span><span class="sxs-lookup"><span data-stu-id="83956-119">You can create a query or view by working in any of the panes: you can specify a column to display by choosing it in the Diagram pane, entering it into the Criteria pane, or making it part of the SQL statement in the SQL pane.</span></span>  
  
## <a name="displaying-and-hiding-panes"></a><span data-ttu-id="83956-120">Mostrar y ocultar paneles</span><span class="sxs-lookup"><span data-stu-id="83956-120">Displaying and Hiding Panes</span></span>  
 <span data-ttu-id="83956-121">Para ocultar un panel o mostrar un panel que no esté visible, haga clic con el botón derecho en la superficie de diseño, seleccione **Panel**y, a continuación, haga clic en el nombre del panel.</span><span class="sxs-lookup"><span data-stu-id="83956-121">To hide a pane or display a pane that is not visible, right-click the design surface, point to **Pane**, and then click the name of the pane.</span></span> <span data-ttu-id="83956-122">Si el Diseñador de consultas y vistas se abre en el modo de Diseñador de consultas, el panel **Resultados** no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="83956-122">If the Query and View Designer is opened in Query Designer mode, the **Results** pane is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83956-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83956-123">See Also</span></span>  
 <span data-ttu-id="83956-124">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="83956-124">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="83956-125">[Abra el diseñador de consultas y vistas &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="83956-125">[Open the Query and View Designer &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="83956-126">Editor SQL &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="83956-126">SQL Editor &#40;Visual Database Tools&#41;</span></span>](sql-editor-visual-database-tools.md)  
  
  
