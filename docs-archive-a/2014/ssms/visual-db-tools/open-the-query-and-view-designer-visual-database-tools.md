---
title: Abrir el Diseñador de consultas y vistas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a36a0a9f014759269517a5774167f84c19b0b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673415"
---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a><span data-ttu-id="c515e-102">Abrir el Diseñador de consultas y vistas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c515e-102">Open the Query and View Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="c515e-103">El Diseñador de consultas y vistas se ejecuta cuando se abre la definición de una vista, cuando se muestran los resultados de una consulta o una vista, o cuando se crea o se abre una consulta.</span><span class="sxs-lookup"><span data-stu-id="c515e-103">The Query and View Designer opens when you open the definition of a view, show the results for a query or view, or create or open a query.</span></span> <span data-ttu-id="c515e-104">Se compone de cuatro paneles diferentes:</span><span class="sxs-lookup"><span data-stu-id="c515e-104">It consists of four separate panes:</span></span>  
  
-   <span data-ttu-id="c515e-105">El panel Diagrama muestra una presentación gráfica de las tablas o de los objetos con valores de tabla que ha seleccionado en la conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="c515e-105">The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection.</span></span> <span data-ttu-id="c515e-106">También muestra todas las relaciones de combinación entre ellos.</span><span class="sxs-lookup"><span data-stu-id="c515e-106">It also shows any join relationships among them.</span></span>  
  
-   <span data-ttu-id="c515e-107">El panel Criterios permite definir las opciones de consulta (como qué columnas de datos se van a mostrar, cómo se van a ordenar los resultados y qué filas se van a seleccionar); para ello, las opciones se deben escribir en una cuadrícula con forma de hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="c515e-107">The Criteria pane allows you to specify query options - such as which data columns to display, how to order the results, and what rows to select - by entering your choices into a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="c515e-108">Puede utilizar el panel SQL para crear su propia instrucción SQL o puede hacerlo en los paneles Criterios y Diagrama (en ese caso, las instrucciones SQL se crearán en el panel SQL).</span><span class="sxs-lookup"><span data-stu-id="c515e-108">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="c515e-109">A medida que crea la consulta, el panel SQL actualiza la instrucción y le vuelve a dar formato automáticamente para facilitar su lectura.</span><span class="sxs-lookup"><span data-stu-id="c515e-109">As you build your query, the SQL pane automatically updates and reformats to be easily read.</span></span>  
  
-   <span data-ttu-id="c515e-110">El panel Resultados muestra los resultados de la consulta Select que se ha ejecutado más recientemente</span><span class="sxs-lookup"><span data-stu-id="c515e-110">The Results pane shows the results of the most recently executed Select query.</span></span> <span data-ttu-id="c515e-111">(Los resultados de otros tipos de consultas se muestran en cuadros de mensaje).</span><span class="sxs-lookup"><span data-stu-id="c515e-111">(The results of other query types are displayed in message boxes.)</span></span>  
  
-   <span data-ttu-id="c515e-112">Estos paneles resultan útiles al trabajar con consultas y vistas.</span><span class="sxs-lookup"><span data-stu-id="c515e-112">These panes are useful for working with both queries and views.</span></span>  
  
-   <span data-ttu-id="c515e-113">Cuando abra una vista o una consulta, se abrirán algunos o todos los paneles.</span><span class="sxs-lookup"><span data-stu-id="c515e-113">When you open a view or query some or all of the panes open with it.</span></span> <span data-ttu-id="c515e-114">Los paneles se abrirán en función de los valores establecidos en el cuadro de diálogo **Opciones** y del sistema de administración de base de datos a la que está conectado.</span><span class="sxs-lookup"><span data-stu-id="c515e-114">Which ones open depend on the settings in the **Options** dialog box and what database management system you're connected to.</span></span> <span data-ttu-id="c515e-115">De forma predeterminada, se abren los cuatro.</span><span class="sxs-lookup"><span data-stu-id="c515e-115">The default is that all four open.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a><span data-ttu-id="c515e-116">Para abrir el Diseñador de consultas y vistas para una vista</span><span class="sxs-lookup"><span data-stu-id="c515e-116">To open the Query and View Designer for a view</span></span>  
  
1.  <span data-ttu-id="c515e-117">En el Explorador de objetos, haga clic con el botón derecho en la vista que desea abrir y, a continuación, haga clic en **Diseño** o en **Abrir vista**.</span><span class="sxs-lookup"><span data-stu-id="c515e-117">In Object Explorer, right-click the view you want to open and click **Design** or **Open View**.</span></span>  
  
     <span data-ttu-id="c515e-118">Si elige **Diseño**, se abrirán los paneles del Diseñador de consultas y vistas en función de las opciones seleccionadas en el cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="c515e-118">If you chose **Design**, the Query and View Designer panes open as dictated by the options selected in the **Options** dialog box.</span></span> <span data-ttu-id="c515e-119">Si elige **Abrir vista**, se abre solo el panel Resultados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c515e-119">If you chose **Open View**, only the Results pane opens by default.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a><span data-ttu-id="c515e-120">Para abrir el Diseñador de consultas y vistas para una consulta existente</span><span class="sxs-lookup"><span data-stu-id="c515e-120">To open the Query and View Designer for an existing query</span></span>  
  
1.  <span data-ttu-id="c515e-121">En el Explorador de soluciones, expanda la carpeta **Consultas** .</span><span class="sxs-lookup"><span data-stu-id="c515e-121">In Solution Explorer, expand the **Queries** folder.</span></span>  
  
2.  <span data-ttu-id="c515e-122">Haga doble clic en la consulta que desee abrir.</span><span class="sxs-lookup"><span data-stu-id="c515e-122">Double-click the query you want to open.</span></span>  
  
3.  <span data-ttu-id="c515e-123">Resalte las instrucciones de la consulta, haga clic con el botón derecho en el área resaltada y, a continuación, haga clic en **Diseñar consulta en el editor**.</span><span class="sxs-lookup"><span data-stu-id="c515e-123">Highlight the query statement(s), right-click the highlighted area and click **Design Query in Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c515e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c515e-124">See Also</span></span>  
 <span data-ttu-id="c515e-125">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c515e-125">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c515e-126">Herramientas Diseñador de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c515e-126">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](query-and-view-designer-tools-visual-database-tools.md)  
  
  
