---
title: Agregar tablas a las consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
- queries [SQL Server], tables
ms.assetid: 6551aa7e-31a1-4636-852a-819bc53d658b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 572002bc913cc9916a75ce2b16c12064452d250f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673428"
---
# <a name="add-tables-to-queries-visual-database-tools"></a><span data-ttu-id="0319e-102">Agregar tablas a las consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0319e-102">Add Tables to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="0319e-103">Cuando crea una consulta, recupera datos de una tabla u otros objetos con estructura de tabla (vistas y determinadas funciones definidas por el usuario).</span><span class="sxs-lookup"><span data-stu-id="0319e-103">When you create a query, you are retrieving data from a table or other objects structured like tables - views and certain user-defined functions.</span></span> <span data-ttu-id="0319e-104">Para trabajar con cualquiera de estos objetos en la consulta, deberá agregarlos al **panel Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="0319e-104">To work with any of these objects in your query, you add them to the **Diagram Pane**.</span></span>  
  
### <a name="to-add-a-table-or-table-valued-object-to-a-query"></a><span data-ttu-id="0319e-105">Para agregar una tabla u objeto con valor de tabla a una consulta</span><span class="sxs-lookup"><span data-stu-id="0319e-105">To add a table or table-valued object to a query</span></span>  
  
1.  <span data-ttu-id="0319e-106">Haga clic con el botón derecho en el fondo del **panel Diagrama** del Diseñador de consultas y vistas y, a continuación, elija **Agregar tabla** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="0319e-106">In the **Diagram pane** of the Query and View Designer, right-click the background and choose **Add Table** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="0319e-107">En el cuadro de diálogo **Agregar tabla** , seleccione la pestaña correspondiente al tipo de objeto que desea agregar a la consulta.</span><span class="sxs-lookup"><span data-stu-id="0319e-107">In the **Add Table** dialog box, select the tab for the type of object you want to add to the query.</span></span>  
  
3.  <span data-ttu-id="0319e-108">En la lista de elementos, haga doble clic en cada elemento que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="0319e-108">In the list of items, double-click each item you want to add.</span></span>  
  
4.  <span data-ttu-id="0319e-109">Cuando acabe de agregar elementos, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0319e-109">When you finish adding items, click **Close**.</span></span>  
  
     <span data-ttu-id="0319e-110">El Diseñador de consultas y vistas actualizará el **panel Diagrama**, el **panel Criterios**y el **panel SQL** en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="0319e-110">The Query and View Designer updates the **Diagram Pane**, **Criteria Pane**, and **SQL Pane** accordingly.</span></span>  
  
 <span data-ttu-id="0319e-111">Cuando haga referencia a tablas o vistas en la instrucción del panel SQL, se agregarán automáticamente a la consulta.</span><span class="sxs-lookup"><span data-stu-id="0319e-111">Tables and views are automatically added to the query when you reference them in the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="0319e-112">El Diseñador de consultas y vistas no mostrará las columnas de datos de una tabla o de un objeto con estructura de tabla si no tiene suficientes derechos de acceso o si el proveedor no puede devolver información acerca de la tabla o del objeto.</span><span class="sxs-lookup"><span data-stu-id="0319e-112">The Query and View Designer will not display data columns for a table or table-structured object if you do not have sufficient access rights to it or if the provider cannot return information about it.</span></span> <span data-ttu-id="0319e-113">En este caso, solo se muestra una barra de título y la casilla \* (Todas las columnas) en la tabla o el objeto con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0319e-113">In such cases, only a title bar and the \* (All Columns) check box are displayed for the table or table-valued object.</span></span>  
  
### <a name="to-add-an-existing-query-to-a-new-query"></a><span data-ttu-id="0319e-114">Para agregar una consulta existente a una consulta nueva</span><span class="sxs-lookup"><span data-stu-id="0319e-114">To add an existing query to a new query</span></span>  
  
1.  <span data-ttu-id="0319e-115">Compruebe que el **panel SQL** está visible en la nueva consulta que va a crear.</span><span class="sxs-lookup"><span data-stu-id="0319e-115">Make sure the **SQL Pane** is displayed in the new query you are creating.</span></span>  
  
2.  <span data-ttu-id="0319e-116">En el **panel SQL**, escriba un paréntesis de apertura y otro de cierre () después de la palabra FROM.</span><span class="sxs-lookup"><span data-stu-id="0319e-116">In the **SQL Pane**, type a right and left parentheses () after the word FROM.</span></span>  
  
3.  <span data-ttu-id="0319e-117">Abra el Diseñador de consultas para la consulta existente.</span><span class="sxs-lookup"><span data-stu-id="0319e-117">Open the Query Designer for the existing query.</span></span> <span data-ttu-id="0319e-118">(Ahora tiene dos Diseñadores de consultas abiertos.)</span><span class="sxs-lookup"><span data-stu-id="0319e-118">(You now have two Query Designers open.)</span></span>  
  
4.  <span data-ttu-id="0319e-119">Muestre el **panel SQL** para la consulta interna (la consulta existente que se va a incluir en la nueva consulta externa).</span><span class="sxs-lookup"><span data-stu-id="0319e-119">Display the **SQL Pane** for the inner query - the existing query you are including in the new, outer query.</span></span>  
  
5.  <span data-ttu-id="0319e-120">Seleccione todo el texto del **panel SQL**y cópielo en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0319e-120">Select all the text in the **SQL Pane**, and copy it to the Clipboard.</span></span>  
  
6.  <span data-ttu-id="0319e-121">Haga clic en el **panel SQL** de la nueva consulta, coloque el cursor entre los paréntesis agregados y pegue el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0319e-121">Click in the **SQL Pane** of the new query, situate the cursor between the parentheses you added, and paste the contents of the Clipboard.</span></span>  
  
7.  <span data-ttu-id="0319e-122">En el **panel SQL**, agregue un alias después del paréntesis de cierre.</span><span class="sxs-lookup"><span data-stu-id="0319e-122">Still in the **SQL Pane**, add an alias after the right parenthesis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0319e-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0319e-123">See Also</span></span>  
 <span data-ttu-id="0319e-124">[Crear alias de tabla &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0319e-124">[Create Table Aliases &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="0319e-125">[Quitar tablas de las consultas &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0319e-125">[Remove Tables from Queries &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0319e-126">[Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0319e-126">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0319e-127">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0319e-127">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0319e-128">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0319e-128">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
