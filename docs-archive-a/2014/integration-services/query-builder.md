---
title: Generador de consultas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.querybuilder.f1
helpviewer_keywords:
- Query Builder dialog box
ms.assetid: 780752c9-6e3c-4f44-aaff-4f4d5e5a45c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81be066d92ef1e19a141414dad4359b60efca2f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744759"
---
# <a name="query-builder"></a><span data-ttu-id="f0799-102">Generador de consultas</span><span class="sxs-lookup"><span data-stu-id="f0799-102">Query Builder</span></span>
  <span data-ttu-id="f0799-103">Utilice el cuadro de diálogo **Generador de consultas** para crear una consulta para su uso en la tarea Ejecutar SQL, el origen de OLE DB y el destino de OLE DB, y la transformación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f0799-103">Use the **Query Builder** dialog box to create a query for use in the Execute SQL task, the OLE DB source and the OLE DB destination, and the Lookup transformation.</span></span>  
  
 <span data-ttu-id="f0799-104">Puede utilizar el Generador de consultas para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f0799-104">You can use Query Builder to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="f0799-105">**Trabajar con una representación gráfica de una consulta o con comandos SQL** El Generador de comandos tiene un panel en el que se muestra gráficamente la consulta y otro en el que se muestra el texto SQL de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0799-105">**Working with a graphical representation of a query or with SQL commands** Query Builder includes a pane that displays your query graphically and a pane that displays the SQL text of your query.</span></span> <span data-ttu-id="f0799-106">Puede trabajar en el panel gráfico o en el panel de texto.</span><span class="sxs-lookup"><span data-stu-id="f0799-106">You can work in either the graphical pane or the text pane.</span></span> <span data-ttu-id="f0799-107">El Generador de consultas sincroniza las vistas para que siempre estén actualizadas.</span><span class="sxs-lookup"><span data-stu-id="f0799-107">Query Builder synchronizes the views so that they are always current.</span></span>  
  
-   <span data-ttu-id="f0799-108">**Combinar tablas relacionadas** Si agrega más de una tabla a la consulta, el Generador de consultas determinará automáticamente cómo están relacionadas las tablas y generará el comando de combinación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f0799-108">**Joining related tables** If you add more than one table to your query, Query Builder automatically determines how the tables are related and constructs the appropriate join command.</span></span>  
  
-   <span data-ttu-id="f0799-109">**Consultar o actualizar bases de datos** Puede usar el Generador de consultas para devolver datos mediante instrucciones SELECT de Transact-SQL y para crear consultas que actualicen, agreguen o eliminen registros en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="f0799-109">**Querying or updating databases** You can use Query Builder to return data by using Transact-SQL SELECT statements and to create queries that update, add, or delete records in a database.</span></span>  
  
-   <span data-ttu-id="f0799-110">**Ver y editar resultados inmediatamente** Puede ejecutar la consulta y trabajar con un conjunto de registros en una cuadrícula que le permite desplazarse por los registros de la base de datos y editarlos.</span><span class="sxs-lookup"><span data-stu-id="f0799-110">**Viewing and editing results immediately** You can run your query and work with a recordset in a grid that allows you to scroll through and edit records in the database.</span></span>  
  
 <span data-ttu-id="f0799-111">Las herramientas gráficas del cuadro de diálogo **Generador de consultas** le permiten crear consultas mediante operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f0799-111">The graphical tools in the **Query Builder** dialog box let you construct queries using drag-and-drop operations.</span></span> <span data-ttu-id="f0799-112">De forma predeterminada, el cuadro de diálogo Generador de consultas construye consultas SELECT, aunque también se pueden crear consultas INSERT, UPDATE o DELETE.</span><span class="sxs-lookup"><span data-stu-id="f0799-112">By default, the Query Builder dialog box constructs SELECT queries, but you can also build INSERT, UPDATE, or DELETE queries.</span></span> <span data-ttu-id="f0799-113">Todos los tipos de instrucciones SQL se pueden analizar y ejecutar en el cuadro de diálogo **Generador de consultas** .</span><span class="sxs-lookup"><span data-stu-id="f0799-113">All types of SQL statements can be parsed and run in the **Query Builder** dialog box.</span></span> <span data-ttu-id="f0799-114">Para obtener más información sobre la presencia de instrucciones SQL en paquetes, vea [Consultas de Integration Services &#40;SSIS&#41;](integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f0799-114">For more information about SQL statements in packages, see [Integration Services &#40;SSIS&#41; Queries](integration-services-ssis-queries.md).</span></span>  
  
 <span data-ttu-id="f0799-115">Para obtener más información sobre el lenguaje Transact-SQL y su sintaxis, vea [Referencia de Transact-SQL &#40;motor de base de datos&#41;](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="f0799-115">To learn more about the Transact-SQL language and its syntax, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span>  
  
 <span data-ttu-id="f0799-116">Asimismo, puede utilizar variables en una consulta para proporcionar valores a un parámetro de entrada, capturar valores de parámetros de salida y almacenar códigos de retorno.</span><span class="sxs-lookup"><span data-stu-id="f0799-116">You can also use variables in a query to provide values to an input parameter, to capture values of output parameters, and to store return codes.</span></span> <span data-ttu-id="f0799-117">Para obtener más información sobre cómo usar variables en las consultas que usan los paquetes, vea [Tarea Ejecutar SQL](control-flow/execute-sql-task.md), [Origen de OLE DB](data-flow/ole-db-source.md)y [Integration Services &#40;SSIS&#41; Queries](integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f0799-117">To learn more about using variables in the queries that packages use, see [Execute SQL Task](control-flow/execute-sql-task.md), [OLE DB Source](data-flow/ole-db-source.md), and [Integration Services &#40;SSIS&#41; Queries](integration-services-ssis-queries.md).</span></span> <span data-ttu-id="f0799-118">Para obtener más información sobre cómo usar variables en la tarea Ejecutar SQL, vea [Parámetros y códigos de retorno en la tarea Ejecutar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) y [Conjuntos de resultados en la tarea Ejecutar SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="f0799-118">To learn more about using variables in the Execute SQL Task, see [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) and [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span></span>  
  
 <span data-ttu-id="f0799-119">Las transformaciones de búsqueda Aproximada y Búsqueda también pueden utilizar variables con parámetros y códigos de retorno.</span><span class="sxs-lookup"><span data-stu-id="f0799-119">The Lookup and Fuzzy lookup transformations can also use variables with parameters and return codes.</span></span> <span data-ttu-id="f0799-120">Además, la información relativa al origen OLE DB se puede aplicar a estas dos transformaciones.</span><span class="sxs-lookup"><span data-stu-id="f0799-120">The information about the OLE DB source applies to these two transformations also.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0799-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="f0799-121">Options</span></span>  
 <span data-ttu-id="f0799-122">**Barra de herramientas**</span><span class="sxs-lookup"><span data-stu-id="f0799-122">**Toolbar**</span></span>  
 <span data-ttu-id="f0799-123">Use la barra de herramientas para administrar conjuntos de datos, seleccionar los paneles que desea mostrar y controlar funciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="f0799-123">Use the toolbar to manage datasets, select panes to display, and control query functions.</span></span>  
  
|<span data-ttu-id="f0799-124">Value</span><span class="sxs-lookup"><span data-stu-id="f0799-124">Value</span></span>|<span data-ttu-id="f0799-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0799-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f0799-126">**Mostrar u ocultar panel de diagrama**</span><span class="sxs-lookup"><span data-stu-id="f0799-126">**Show/Hide Diagram Pane**</span></span>|<span data-ttu-id="f0799-127">Muestra u oculta el panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="f0799-127">Shows or hides the **Diagram** pane.</span></span>|  
|<span data-ttu-id="f0799-128">**Mostrar u ocultar panel de cuadrícula**</span><span class="sxs-lookup"><span data-stu-id="f0799-128">**Show/Hide Grid Pane**</span></span>|<span data-ttu-id="f0799-129">Muestra u oculta el panel **Cuadrícula** .</span><span class="sxs-lookup"><span data-stu-id="f0799-129">Shows or hides the **Grid** pane.</span></span>|  
|<span data-ttu-id="f0799-130">**Mostrar u ocultar panel de SQL**</span><span class="sxs-lookup"><span data-stu-id="f0799-130">**Show/Hide SQL Pane**</span></span>|<span data-ttu-id="f0799-131">Muestra u oculta el panel **SQL** .</span><span class="sxs-lookup"><span data-stu-id="f0799-131">Shows or hides the **SQL** pane.</span></span>|  
|<span data-ttu-id="f0799-132">**Mostrar u ocultar panel de resultados**</span><span class="sxs-lookup"><span data-stu-id="f0799-132">**Show/Hide Results Pane**</span></span>|<span data-ttu-id="f0799-133">Muestra u oculta el panel **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="f0799-133">Shows or hides the **Results** pane.</span></span>|  
|<span data-ttu-id="f0799-134">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="f0799-134">**Run**</span></span>|<span data-ttu-id="f0799-135">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0799-135">Runs the query.</span></span> <span data-ttu-id="f0799-136">Los resultados se mostrarán en el panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="f0799-136">Results are displayed in the result pane.</span></span>|  
|<span data-ttu-id="f0799-137">**Comprobar SQL**</span><span class="sxs-lookup"><span data-stu-id="f0799-137">**Verify SQL**</span></span>|<span data-ttu-id="f0799-138">Comprueba que la instrucción SQL sea válida.</span><span class="sxs-lookup"><span data-stu-id="f0799-138">Verifies that the SQL statement is valid.</span></span>|  
|<span data-ttu-id="f0799-139">**Orden ascendente**</span><span class="sxs-lookup"><span data-stu-id="f0799-139">**Sort Ascending**</span></span>|<span data-ttu-id="f0799-140">Ordena las filas de salida de la columna seleccionada en el panel de cuadrícula en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="f0799-140">Sorts output rows on the selected column in the grid pane, in ascending order.</span></span>|  
|<span data-ttu-id="f0799-141">**Orden descendente**</span><span class="sxs-lookup"><span data-stu-id="f0799-141">**Sort Descending**</span></span>|<span data-ttu-id="f0799-142">Ordena las filas de salida de la columna seleccionada en el panel de cuadrícula en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="f0799-142">Sorts output rows on the selected column in the grid pane, in descending order.</span></span>|  
|<span data-ttu-id="f0799-143">**Quitar filtro**</span><span class="sxs-lookup"><span data-stu-id="f0799-143">**Remove Filter**</span></span>|<span data-ttu-id="f0799-144">Seleccione un nombre de columna en el panel de cuadrícula y, a continuación, haga clic en **Quitar filtro** para quitar los criterios de ordenación de dicha columna.</span><span class="sxs-lookup"><span data-stu-id="f0799-144">Select a column name in the grid pane, and then click **Remove Filter** to remove sort criteria for the column.</span></span>|  
|<span data-ttu-id="f0799-145">**Usar GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="f0799-145">**Use Group By**</span></span>|<span data-ttu-id="f0799-146">Agrega la funcionalidad GROUP BY a la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0799-146">Adds GROUP BY functionality to the query.</span></span>|  
|<span data-ttu-id="f0799-147">**Agregar tabla**</span><span class="sxs-lookup"><span data-stu-id="f0799-147">**Add Table**</span></span>|<span data-ttu-id="f0799-148">Agrega una nueva tabla a la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0799-148">Adds a new table to the query.</span></span>|  
  
 <span data-ttu-id="f0799-149">**Definición de la consulta**</span><span class="sxs-lookup"><span data-stu-id="f0799-149">**Query Definition**</span></span>  
 <span data-ttu-id="f0799-150">La definición de la consulta proporciona una barra de herramientas y paneles en los que se define y prueba la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0799-150">The query definition provides a toolbar and panes in which to define and test the query.</span></span>  
  
|<span data-ttu-id="f0799-151">Panel</span><span class="sxs-lookup"><span data-stu-id="f0799-151">Pane</span></span>|<span data-ttu-id="f0799-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0799-152">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f0799-153">Panel **Diagrama**</span><span class="sxs-lookup"><span data-stu-id="f0799-153">**Diagram** pane</span></span>|<span data-ttu-id="f0799-154">Muestra la consulta en un diagrama.</span><span class="sxs-lookup"><span data-stu-id="f0799-154">Displays the query in a diagram.</span></span> <span data-ttu-id="f0799-155">El diagrama muestra las tablas incluidas en la consulta y cómo se combinan.</span><span class="sxs-lookup"><span data-stu-id="f0799-155">The diagram shows the tables included in the query, and how they are joined.</span></span> <span data-ttu-id="f0799-156">Active o desactive la casilla situada junto a una columna de la tabla para agregarla a (o quitarla de) la salida de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0799-156">Select or clear the check box next to a column in a table to add or remove it from the query output.</span></span><br /><br /> <span data-ttu-id="f0799-157">Cuando agrega tablas a la consulta, el Generador de consultas crea combinaciones entre las tablas basadas en tablas, según las claves de la tabla.</span><span class="sxs-lookup"><span data-stu-id="f0799-157">When you add tables to the query, Query Builder creates joins between tables based on tables, depending on the keys in the table.</span></span> <span data-ttu-id="f0799-158">Para agregar una combinación, arrastre un campo de una de las tablas a un campo de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="f0799-158">To add a join, drag a field from one table onto a field in another table.</span></span> <span data-ttu-id="f0799-159">Para administrar una combinación, haga clic con el botón secundario en la combinación y, a continuación, seleccione una opción de menú.</span><span class="sxs-lookup"><span data-stu-id="f0799-159">To manage a join, right-click the join, and then select a menu option.</span></span><br /><br /> <span data-ttu-id="f0799-160">Haga clic con el botón secundario en el panel **Diagrama** para agregar o quitar tablas, seleccionar todas las tablas y mostrar u ocultar paneles.</span><span class="sxs-lookup"><span data-stu-id="f0799-160">Right-click the **Diagram** pane to add or remove tables, select all the tables, and show or hide panes.</span></span>|  
|<span data-ttu-id="f0799-161">Panel **cuadrícula**</span><span class="sxs-lookup"><span data-stu-id="f0799-161">**Grid** pane</span></span>|<span data-ttu-id="f0799-162">Muestra la consulta en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f0799-162">Displays the query in a grid.</span></span> <span data-ttu-id="f0799-163">Puede utilizar este panel para agregar y quitar columnas de una consulta y cambiar la configuración de cada columna.</span><span class="sxs-lookup"><span data-stu-id="f0799-163">You can use this pane to add to and remove columns from the query and change the settings for each column.</span></span>|  
|<span data-ttu-id="f0799-164">Panel **SQL**</span><span class="sxs-lookup"><span data-stu-id="f0799-164">**SQL** pane</span></span>|<span data-ttu-id="f0799-165">Muestra la consulta como texto SQL.</span><span class="sxs-lookup"><span data-stu-id="f0799-165">Displays the query as SQL text.</span></span> <span data-ttu-id="f0799-166">Los cambios que se realicen en el panel **Diagrama** y en el panel **Cuadrícula** aparecerán aquí, y los cambios que se realicen aquí aparecerán en el panel **Diagrama** y en el panel **Cuadrícula** .</span><span class="sxs-lookup"><span data-stu-id="f0799-166">Changes made in the **Diagram** pane and the **Grid** pane will appear here, and changes made here will appear in the **Diagram** pane and the **Grid** pane.</span></span>|  
|<span data-ttu-id="f0799-167">Panel**Resultados**</span><span class="sxs-lookup"><span data-stu-id="f0799-167">**Results** pane</span></span>|<span data-ttu-id="f0799-168">Muestra los resultados de la consulta al hacer clic en **Ejecutar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="f0799-168">Displays the results of the query when you click **Run** on the toolbar.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0799-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0799-169">See Also</span></span>  
 <span data-ttu-id="f0799-170">[Tarea ejecutar SQL](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="f0799-170">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="f0799-171">[Origen de OLE DB](data-flow/ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="f0799-171">[OLE DB Source](data-flow/ole-db-source.md) </span></span>  
 <span data-ttu-id="f0799-172">[Destino de OLE DB](data-flow/ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="f0799-172">[OLE DB Destination](data-flow/ole-db-destination.md) </span></span>  
 <span data-ttu-id="f0799-173">[Transformación búsqueda](data-flow/transformations/lookup-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="f0799-173">[Lookup Transformation](data-flow/transformations/lookup-transformation.md) </span></span>  
 <span data-ttu-id="f0799-174">[Integration Services &#40;consultas&#41; SSIS](integration-services-ssis-queries.md) </span><span class="sxs-lookup"><span data-stu-id="f0799-174">[Integration Services &#40;SSIS&#41; Queries](integration-services-ssis-queries.md) </span></span>  
 [<span data-ttu-id="f0799-175">MERGE en paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="f0799-175">MERGE in Integration Services Packages</span></span>](control-flow/merge-in-integration-services-packages.md)  
  
  