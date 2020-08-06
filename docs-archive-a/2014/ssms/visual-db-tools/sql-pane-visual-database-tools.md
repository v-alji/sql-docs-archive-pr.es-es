---
title: Panel SQL (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], SQL pane
- View Designer, SQL pane
- SQL pane [Visual Database Tools]
ms.assetid: dbabab18-0614-415b-a2ef-9bcd0d320d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a87ec1d5517852fefb152e0ec7b3165fa32988b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743817"
---
# <a name="sql-pane-visual-database-tools"></a><span data-ttu-id="2c256-102">Panel SQL (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2c256-102">SQL Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="2c256-103">Puede utilizar el panel SQL para crear su propia instrucción SQL o puede hacerlo en los paneles Criterios y Diagrama (en ese caso, las instrucciones SQL se crearán en el panel SQL).</span><span class="sxs-lookup"><span data-stu-id="2c256-103">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="2c256-104">A medida que crea la consulta, el panel SQL actualiza la instrucción y le vuelve a dar formato automáticamente para facilitar su lectura.</span><span class="sxs-lookup"><span data-stu-id="2c256-104">As you build your query, the SQL pane automatically updates and reformats for easy readability.</span></span>  
  
 <span data-ttu-id="2c256-105">Para abrir el panel SQL, primero abra el Diseñador de consultas y vistas (con un objeto de base de datos seleccionado en Explorador de servidores, en el menú **Base de datos** haga clic en **Nueva consulta**).</span><span class="sxs-lookup"><span data-stu-id="2c256-105">To open the SQL pane, first open Query and View Designer (with a database object selected in Server Explorer, from the **Database** menu, click **New Query**).</span></span> <span data-ttu-id="2c256-106">A continuación, en el menú **Diseñador de consultas** , seleccione **Panel** y haga clic en **SQL**.</span><span class="sxs-lookup"><span data-stu-id="2c256-106">Then from the **Query Designer** menu point to **Pane** and click **SQL**.</span></span>  
  
 <span data-ttu-id="2c256-107">En el panel SQL, puede:</span><span class="sxs-lookup"><span data-stu-id="2c256-107">In the SQL pane you can:</span></span>  
  
-   <span data-ttu-id="2c256-108">Crear consultas nuevas mediante la especificación de instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="2c256-108">Create new queries by entering SQL statements.</span></span>  
  
-   <span data-ttu-id="2c256-109">Modificar la instrucción SQL creada por el Diseñador de consultas y vistas a partir de la configuración establecida en los paneles Diagrama y Criterios.</span><span class="sxs-lookup"><span data-stu-id="2c256-109">Modify the SQL statement created by the Query and View Designer based on settings you make in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="2c256-110">Especificar instrucciones que aprovechan las ventajas de las características específicas de la base de datos que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="2c256-110">Enter statements that take advantage of features specific to the database you are using.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c256-111">Asegúrese de que conoce las reglas para identificar objetos de base de datos en la base de datos que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="2c256-111">Be sure you know the rules for identifying database objects in the database you are using.</span></span> <span data-ttu-id="2c256-112">Para obtener información detallada, vea la documentación del sistema de administración de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2c256-112">For details, see the documentation for your database management system.</span></span>  
  
## <a name="statements-in-the-sql-pane"></a><span data-ttu-id="2c256-113">Instrucciones en el panel SQL</span><span class="sxs-lookup"><span data-stu-id="2c256-113">Statements in the SQL Pane</span></span>  
 <span data-ttu-id="2c256-114">Puede modificar la consulta actual directamente en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="2c256-114">You can edit the current query directly in the SQL pane.</span></span> <span data-ttu-id="2c256-115">Al desplazarse a otro panel, el Diseñador de consultas y vistas da formato a la instrucción de forma automática y, a continuación, cambia los paneles Diagrama y Criterios para que coincidan con la instrucción.</span><span class="sxs-lookup"><span data-stu-id="2c256-115">When you move to another pane, the Query and View Designer automatically formats your statement, and then changes the Diagram and Criteria panes to match your statement.</span></span>  
  
 <span data-ttu-id="2c256-116">Si la instrucción no puede representarse en los paneles Diagrama y Criterios y éstos están visibles, el Diseñador de consultas y vistas mostrará un error y, a continuación, ofrecerá dos alternativas:</span><span class="sxs-lookup"><span data-stu-id="2c256-116">If your statement cannot be represented in the Diagram and Criteria panes, and if those panes are visible, Query and View Designer displays an error and then offers you two choices:</span></span>  
  
-   <span data-ttu-id="2c256-117">Omitir el hecho que la instrucción no puede representarse en los paneles Diagrama y Criterios.</span><span class="sxs-lookup"><span data-stu-id="2c256-117">Ignore that the statement can not be represented in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="2c256-118">Deshacer el cambio que no puede representarse y revertir la instrucción SQL a su versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="2c256-118">Undo the change that can not be represented and revert to the most recent version of the SQL statement.</span></span>  
  
 <span data-ttu-id="2c256-119">Si decide omitir el hecho de que la instrucción no puede representarse en los paneles Diagrama y Criterios, el Diseñador de consultas y vistas atenuará los otros paneles para indicar que ya no reflejan el contenido del panel SQL.</span><span class="sxs-lookup"><span data-stu-id="2c256-119">If you choose to ignore that the statement can not be represented in the Diagram and Criteria panes, the Query and View Designer dims the other panes to indicate that they no longer reflect the contents of the SQL pane.</span></span>  
  
 <span data-ttu-id="2c256-120">Puede continuar con la modificación de la instrucción y ejecutarla como lo haría con cualquier otra instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="2c256-120">You can continue to edit the statement and execute it as you would any SQL statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c256-121">Si especifica una instrucción SQL, pero, a continuación, realiza cambios adicionales en la consulta mediante la modificación de los paneles Diagrama y Criterios, el Diseñador de consultas y vistas vuelve a generar y a mostrar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="2c256-121">If you enter an SQL statement, but then make further changes to the query by changing the Diagram and Criteria panes, the Query and View Designer rebuilds and redisplays the SQL statement.</span></span> <span data-ttu-id="2c256-122">En algunos casos, esta acción da como resultado una instrucción SQL construida de forma diferente a la que especificó originalmente (aunque siempre dará los mismos resultados).</span><span class="sxs-lookup"><span data-stu-id="2c256-122">In some cases, this action results in an SQL statement that is constructed differently from the one you originally entered (though it will always yield the same results).</span></span> <span data-ttu-id="2c256-123">Es especialmente probable que se produzca esta diferencia cuando está trabajando con condiciones de búsqueda que incluyen varias cláusulas vinculadas con AND y OR.</span><span class="sxs-lookup"><span data-stu-id="2c256-123">This difference is particularly likely when you are working with search conditions that involve several clauses linked with AND and OR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c256-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c256-124">See Also</span></span>  
 <span data-ttu-id="2c256-125">[Crear consultas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2c256-125">[Create Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="2c256-126">[Ejecutar consultas &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2c256-126">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2c256-127">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2c256-127">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2c256-128">[Panel Diagrama &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2c256-128">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2c256-129">[Panel criterios &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2c256-129">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2c256-130">Panel Resultados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2c256-130">Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
