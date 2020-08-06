---
title: Reglas para actualizar resultados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- updating query results
- Query Designer [SQL Server], Results pane
- Results pane
ms.assetid: de131ef0-ccbd-446f-9400-b93c7b8fa537
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc6befc6571f29be95b176f8de6d7dcfaed9108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747392"
---
# <a name="rules-for-updating-results-visual-database-tools"></a><span data-ttu-id="ca795-102">Reglas para actualizar resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ca795-102">Rules for Updating Results (Visual Database Tools)</span></span>
  <span data-ttu-id="ca795-103">En muchos casos, puede actualizar el conjunto de resultados mostrado en el [panel Resultados](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca795-103">In many cases, you can update the result set displayed in the [Results Pane](visual-database-tools.md).</span></span> <span data-ttu-id="ca795-104">Sin embargo, en algunos casos no es posible realizar esta actualización.</span><span class="sxs-lookup"><span data-stu-id="ca795-104">However, in some cases you cannot.</span></span>  
  
 <span data-ttu-id="ca795-105">En general, para actualizar resultados, el [Diseñador de consultas y vistas](query-and-view-designer-tools-visual-database-tools.md) debe tener información suficiente para identificar de forma exclusiva la fila en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ca795-105">In general, in order to update results, the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) must have sufficient information to uniquely identify the row in the table.</span></span> <span data-ttu-id="ca795-106">Por ejemplo, si la consulta incluye una clave principal en la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="ca795-106">An example is if the query includes a primary key in the output list.</span></span> <span data-ttu-id="ca795-107">Además, debe tener permisos suficientes para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ca795-107">In addition, you must have sufficient permission to update the database.</span></span>  
  
 <span data-ttu-id="ca795-108">Si la consulta se basa en una vista, se podrá actualizar.</span><span class="sxs-lookup"><span data-stu-id="ca795-108">If your query is based on a view, you might be able to update it.</span></span> <span data-ttu-id="ca795-109">Se aplican las mismas directrices, con la salvedad de que se aplican a las tablas subyacentes en la vista, no solamente a la propia vista.</span><span class="sxs-lookup"><span data-stu-id="ca795-109">The same guidelines apply, except that they apply to the underlying tables in the view, not just to the view itself.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca795-110">El Diseñador de consultas y vistas no puede determinar con antelación si se puede actualizar un conjunto de resultados basado en una vista.</span><span class="sxs-lookup"><span data-stu-id="ca795-110">The Query and View Designer cannot determine in advance whether you can update a result set based on a view.</span></span> <span data-ttu-id="ca795-111">Por lo tanto, muestra todas las vistas, aunque es posible que no se puedan actualizar.</span><span class="sxs-lookup"><span data-stu-id="ca795-111">Therefore, it displays all views, even though you might not be able to update them.</span></span>  
  
 <span data-ttu-id="ca795-112">La siguiente tabla resume casos específicos en los que sería posible o no actualizar los resultados de la consulta en el panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="ca795-112">The following table summarizes specific instances in which you might and might not be able to update query results in the Results pane.</span></span> <span data-ttu-id="ca795-113">En muchos casos, la base de datos que se utiliza establece si se pueden actualizar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="ca795-113">In many cases, the database you are using dictates whether you can update query results.</span></span>  
  
|<span data-ttu-id="ca795-114">Consultar</span><span class="sxs-lookup"><span data-stu-id="ca795-114">Query</span></span>|<span data-ttu-id="ca795-115">¿Pueden actualizarse los resultados?</span><span class="sxs-lookup"><span data-stu-id="ca795-115">Can results be updated?</span></span>|  
|-----------|-----------------------------|  
|<span data-ttu-id="ca795-116">Consulta basada en una tabla con clave principal en la lista de resultados</span><span class="sxs-lookup"><span data-stu-id="ca795-116">Query based on one table with primary key in the output list</span></span>|<span data-ttu-id="ca795-117">Sí (con la excepción de lo mostrado a continuación).</span><span class="sxs-lookup"><span data-stu-id="ca795-117">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="ca795-118">Consulta basada en una tabla sin índice único y sin clave principal</span><span class="sxs-lookup"><span data-stu-id="ca795-118">Query based on a table with no unique index and without a primary key</span></span>|<span data-ttu-id="ca795-119">Depende de la consulta y de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ca795-119">Depends on query and database.</span></span> <span data-ttu-id="ca795-120">Algunas bases de datos permiten actualizaciones si hay suficiente información disponible para identificar registros de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="ca795-120">Some databases allow updates if sufficient information is available to uniquely identify records.</span></span>|  
|<span data-ttu-id="ca795-121">Consulta basada en varias tablas que no están combinadas</span><span class="sxs-lookup"><span data-stu-id="ca795-121">Query based on multiple tables which are not joined</span></span>|<span data-ttu-id="ca795-122">No.</span><span class="sxs-lookup"><span data-stu-id="ca795-122">No.</span></span>|  
|<span data-ttu-id="ca795-123">Consulta basada en datos marcados como de solo lectura en la base de datos</span><span class="sxs-lookup"><span data-stu-id="ca795-123">Query based on data marked as read-only in the database</span></span>|<span data-ttu-id="ca795-124">No.</span><span class="sxs-lookup"><span data-stu-id="ca795-124">No.</span></span>|  
|<span data-ttu-id="ca795-125">Consulta basada en una vista que incluye una tabla sin restricciones</span><span class="sxs-lookup"><span data-stu-id="ca795-125">Query based on a view that involves one table with no constraints</span></span>|<span data-ttu-id="ca795-126">Sí (con la excepción de lo mostrado a continuación).</span><span class="sxs-lookup"><span data-stu-id="ca795-126">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="ca795-127">Consulta basada en tablas combinadas con una relación uno a uno</span><span class="sxs-lookup"><span data-stu-id="ca795-127">Query based on tables joined with a one-to-one relationship</span></span>|<span data-ttu-id="ca795-128">Sí (con la excepción de lo mostrado a continuación).</span><span class="sxs-lookup"><span data-stu-id="ca795-128">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="ca795-129">Consulta basada en tablas combinadas con una relación uno a varios</span><span class="sxs-lookup"><span data-stu-id="ca795-129">Query based on tables joined with a one-to-many relationship</span></span>|<span data-ttu-id="ca795-130">Normalmente.</span><span class="sxs-lookup"><span data-stu-id="ca795-130">Usually.</span></span>|  
|<span data-ttu-id="ca795-131">Consulta basada en tres o más tablas en las que existe una relación varios a varios</span><span class="sxs-lookup"><span data-stu-id="ca795-131">Query based on three or more tables in which there is a many-to-many relationship</span></span>|<span data-ttu-id="ca795-132">No.</span><span class="sxs-lookup"><span data-stu-id="ca795-132">No.</span></span>|  
|<span data-ttu-id="ca795-133">Consulta basada en una tabla para la que no se dispone de permiso de actualización</span><span class="sxs-lookup"><span data-stu-id="ca795-133">Query based on a table for which update permission is not granted</span></span>|<span data-ttu-id="ca795-134">Pueden eliminarse pero no actualizarse.</span><span class="sxs-lookup"><span data-stu-id="ca795-134">Can delete but not update.</span></span>|  
|<span data-ttu-id="ca795-135">Consulta basada en una tabla para la que no se dispone de permiso de eliminación</span><span class="sxs-lookup"><span data-stu-id="ca795-135">Query based on a table for which delete permission is not granted</span></span>|<span data-ttu-id="ca795-136">Pueden actualizarse pero no eliminarse.</span><span class="sxs-lookup"><span data-stu-id="ca795-136">Can update but not delete.</span></span>|  
|<span data-ttu-id="ca795-137">Consulta de funciones agregadas</span><span class="sxs-lookup"><span data-stu-id="ca795-137">Aggregate query</span></span>|<span data-ttu-id="ca795-138">No.</span><span class="sxs-lookup"><span data-stu-id="ca795-138">No.</span></span>|  
|<span data-ttu-id="ca795-139">Consulta basada en una subconsulta que contiene totales o funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="ca795-139">Query based on a subquery that contains totals or aggregate functions</span></span>|<span data-ttu-id="ca795-140">No.</span><span class="sxs-lookup"><span data-stu-id="ca795-140">No.</span></span>|  
|<span data-ttu-id="ca795-141">Consulta que incluye la palabra clave DISTINCT para excluir filas duplicadas</span><span class="sxs-lookup"><span data-stu-id="ca795-141">Query that includes the DISTINCT keyword to exclude duplicate rows</span></span>|<span data-ttu-id="ca795-142">No.</span><span class="sxs-lookup"><span data-stu-id="ca795-142">No.</span></span>|  
|<span data-ttu-id="ca795-143">Consulta cuya cláusula FROM incluye una función definida por el usuario que devuelve una tabla y la función definida por el usuario contiene varias instrucciones SELECT</span><span class="sxs-lookup"><span data-stu-id="ca795-143">Query whose FROM clause includes a user-defined function that returns a table and the user-defined function contains multiple select statements</span></span>|<span data-ttu-id="ca795-144">No.</span><span class="sxs-lookup"><span data-stu-id="ca795-144">No.</span></span>|  
|<span data-ttu-id="ca795-145">Consulta cuya cláusula FROM incluya una función inline definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="ca795-145">Query whose FROM clause includes an inline user-defined function</span></span>|<span data-ttu-id="ca795-146">Sí.</span><span class="sxs-lookup"><span data-stu-id="ca795-146">Yes.</span></span>|  
  
 <span data-ttu-id="ca795-147">Además, es posible que no pueda actualizar columnas específicas de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="ca795-147">In addition, you might not be able to update specific columns in the query results.</span></span> <span data-ttu-id="ca795-148">La siguiente lista resume tipos específicos de columnas que no se pueden actualizar en el panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="ca795-148">The following list summarizes specific types of columns that you cannot update in the Results pane.</span></span>  
  
-   <span data-ttu-id="ca795-149">Columnas basadas en expresiones</span><span class="sxs-lookup"><span data-stu-id="ca795-149">Columns based on expressions</span></span>  
  
-   <span data-ttu-id="ca795-150">Columnas basadas en funciones escalares definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="ca795-150">Columns based on scalar user-defined functions</span></span>  
  
-   <span data-ttu-id="ca795-151">Filas o columnas eliminadas por otro usuario</span><span class="sxs-lookup"><span data-stu-id="ca795-151">Rows or columns deleted by another user</span></span>  
  
-   <span data-ttu-id="ca795-152">Filas o columnas bloqueadas por otro usuario (normalmente, las filas bloqueadas se pueden actualizar en cuanto se desbloquean)</span><span class="sxs-lookup"><span data-stu-id="ca795-152">Rows or columns locked by another user (locked rows can usually be updated as soon as they are unlocked)</span></span>  
  
-   <span data-ttu-id="ca795-153">Columnas de marca de tiempo o BLOB</span><span class="sxs-lookup"><span data-stu-id="ca795-153">Timestamp or BLOB columns</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca795-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca795-154">See Also</span></span>  
 [<span data-ttu-id="ca795-155">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca795-155">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
