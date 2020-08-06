---
title: Crear consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], creating
ms.assetid: 696a080d-848f-44d3-a918-e29bafaab85a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52392adff03b27e1c4c19f354bc62c350cccf17a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662465"
---
# <a name="create-queries-visual-database-tools"></a><span data-ttu-id="9c76f-102">Crear consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9c76f-102">Create Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="9c76f-103">Las consultas le permiten recuperar datos de las tablas y las vistas de su base de datos.</span><span class="sxs-lookup"><span data-stu-id="9c76f-103">Queries allow you to retrieve data from the tables and views in your database.</span></span> <span data-ttu-id="9c76f-104">El **Diseñador de consultas y vistas**, que permite crear y trabajar con consultas, se compone de cuatro paneles: el [panel Diagrama](visual-database-tools.md), el [panel SQL](sql-pane-visual-database-tools.md), el [panel Criterios](criteria-pane-visual-database-tools.md)y el [panel Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9c76f-104">You create and work with queries in **Query and View Designer**, which is composed of four panes: the [Diagram Pane](visual-database-tools.md), the [SQL Pane](sql-pane-visual-database-tools.md), the [Criteria Pane](criteria-pane-visual-database-tools.md), and the [Results Pane](results-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-a-new-query"></a><span data-ttu-id="9c76f-105">Para crear una nueva consulta</span><span class="sxs-lookup"><span data-stu-id="9c76f-105">To create a new query</span></span>  
  
1.  <span data-ttu-id="9c76f-106">En el **Explorador de objetos**, expanda el nodo **Tablas** de la base de datos que desee consultar.</span><span class="sxs-lookup"><span data-stu-id="9c76f-106">In **Object Explorer**, expand the **Tables** node for the database you want to query.</span></span> <span data-ttu-id="9c76f-107">Haga clic con el botón derecho en la tabla que desee consultar y haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-107">Right-click the table you want to query and click **Open Table**.</span></span>  
  
2.  <span data-ttu-id="9c76f-108">Para agregar más tablas a la consulta, en el menú Diseñador de consultas, seleccione **Agregar tabla**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-108">To add more tables to the query, on the Query Designer menu, select **Add Table**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c76f-109">Si no aparecen los paneles **Diagrama**, **SQL**, **Criterios**o **Resultados** , en el menú del Diseñador de consultas, seleccione **Panel** y haga clic en el panel que desea abrir.</span><span class="sxs-lookup"><span data-stu-id="9c76f-109">If you do not see the **Diagram**, **SQL**, **Criteria**, or **Results** panes, from the Query Designer menu, point to **Pane** and click the pane you want to open.</span></span>  
  
3.  <span data-ttu-id="9c76f-110">En el cuadro de diálogo **Agregar tabla** , seleccione las tablas que desea consultar y haga clic en **Agregar** para cada una.</span><span class="sxs-lookup"><span data-stu-id="9c76f-110">In the **Add Table** dialog box, select the tables you want to query and click **Add** for each one.</span></span>  
  
4.  <span data-ttu-id="9c76f-111">Cuando haya agregado todas las tablas que desea consultar, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-111">Once you have added all the tables you want to query, click **Close**.</span></span>  
  
     <span data-ttu-id="9c76f-112">Para agregar más tablas posteriormente, haga clic con el botón derecho en el espacio abierto en el panel **Diagrama** y, en el menú contextual, haga clic en **Agregar tabla**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-112">To add more tables later, right-click the open space in the **Diagram** pane and from the shortcut menu click **Add Table**.</span></span>  
  
5.  <span data-ttu-id="9c76f-113">En el panel **Diagrama**, active las casillas de los objetos con valores de tabla de cada columna que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="9c76f-113">In the **Diagram Pane**, check the boxes in the table-valued objects for each column you want to query.</span></span>  
  
6.  <span data-ttu-id="9c76f-114">En el menú del Diseñador de consultas, elija **Ejecutar SQL** para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="9c76f-114">From the Query Designer menu, choose **Execute SQL** to run your query.</span></span>  
  
 <span data-ttu-id="9c76f-115">Para restringir más la consulta, puede cambiar el código SQL en el **panel SQL** o elegir opciones como el criterio de ordenación y los alias de las columnas en el panel **Criterios**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-115">To further refine your query, you can change the SQL code in the **SQL Pane** or choose options such as sort order and column aliases in the **Criteria Pane.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c76f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c76f-116">See Also</span></span>  
 <span data-ttu-id="9c76f-117">[Guardar consultas &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9c76f-117">[Save Queries &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9c76f-118">[Tipos de consultas &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9c76f-118">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9c76f-119">[Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9c76f-119">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9c76f-120">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9c76f-120">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9c76f-121">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9c76f-121">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
