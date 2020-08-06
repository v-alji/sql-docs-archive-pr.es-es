---
title: Propiedades de la consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69636
- vdt.ppg.querydesigner.query
ms.assetid: 07495669-6ed5-4004-904e-aae1230be5e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3c8adfb50e15113228afe8b48218f341f19084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744958"
---
# <a name="query-properties-visual-database-tools"></a><span data-ttu-id="659d1-102">Propiedades de la consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="659d1-102">Query Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="659d1-103">Estas propiedades aparecen en la ventana Propiedades cuando hay una consulta abierta en el Diseñador de consultas y vistas.</span><span class="sxs-lookup"><span data-stu-id="659d1-103">These properties appear in the Properties window when you have a query open in Query and View Designer.</span></span> <span data-ttu-id="659d1-104">A menos que se especifique lo contrario, podrá modificar estas propiedades en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="659d1-104">Unless otherwise noted, you can edit these properties in the Properties window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="659d1-105">Las propiedades de este tema están ordenadas por categoría en lugar de alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="659d1-105">The properties in this topic are ordered by category, rather than alphabetically.</span></span>  
  
## <a name="options"></a><span data-ttu-id="659d1-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="659d1-106">Options</span></span>  
 <span data-ttu-id="659d1-107">**Categoría Identidad**</span><span class="sxs-lookup"><span data-stu-id="659d1-107">**Identity Category**</span></span>  
 <span data-ttu-id="659d1-108">Se expande para mostrar la propiedad **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="659d1-108">Expand to show the **Name** property.</span></span>  
  
 <span data-ttu-id="659d1-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="659d1-109">**Name**</span></span>  
 <span data-ttu-id="659d1-110">Muestra el nombre de la consulta actual.</span><span class="sxs-lookup"><span data-stu-id="659d1-110">Shows the name of the current query.</span></span> <span data-ttu-id="659d1-111">No se puede cambiar en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="659d1-111">Cannot be changed in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="659d1-112">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="659d1-112">**Database Name**</span></span>  
 <span data-ttu-id="659d1-113">Muestra el nombre del origen de datos de la tabla seleccionada</span><span class="sxs-lookup"><span data-stu-id="659d1-113">Shows the name of the data source for the selected table.</span></span>  
  
 <span data-ttu-id="659d1-114">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="659d1-114">**Server Name**</span></span>  
 <span data-ttu-id="659d1-115">Muestra el nombre del servidor del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="659d1-115">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="659d1-116">**Diseñador de consultas (Categoría)**</span><span class="sxs-lookup"><span data-stu-id="659d1-116">**Query Designer Category**</span></span>  
 <span data-ttu-id="659d1-117">Se expande para mostrar las propiedades restantes.</span><span class="sxs-lookup"><span data-stu-id="659d1-117">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="659d1-118">**Tabla de destino**</span><span class="sxs-lookup"><span data-stu-id="659d1-118">**Destination table**</span></span>  
 <span data-ttu-id="659d1-119">Especifica el nombre de la tabla en la que se van a insertar los datos.</span><span class="sxs-lookup"><span data-stu-id="659d1-119">Specify the name of the table into which you are inserting data.</span></span> <span data-ttu-id="659d1-120">Esta lista se mostrará cuando cree una consulta INSERT o MAKE TABLE.</span><span class="sxs-lookup"><span data-stu-id="659d1-120">This list appears if you are creating an INSERT query or MAKE TABLE query.</span></span> <span data-ttu-id="659d1-121">Para las consultas INSERT, seleccione un nombre de tabla de la lista.</span><span class="sxs-lookup"><span data-stu-id="659d1-121">For an INSERT query, select a table name from the list.</span></span>  
  
 <span data-ttu-id="659d1-122">En las consultas MAKE TABLE, escriba el nombre de la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="659d1-122">For a MAKE TABLE query, type the name of the new table.</span></span> <span data-ttu-id="659d1-123">Para crear una tabla de destino en otro origen de datos, especifique un nombre de tabla completo, incluido el nombre del origen de datos de destino, el propietario (si fuera necesario) y el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="659d1-123">To create a destination table in another data source, specify a fully qualified table name, including the name of the target data source, the owner (if required), and the name of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="659d1-124">El Diseñador de consultas no comprueba si el nombre ya está en uso o si tiene permisos para crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="659d1-124">Query Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
 <span data-ttu-id="659d1-125">**Valores distintos**</span><span class="sxs-lookup"><span data-stu-id="659d1-125">**Distinct values**</span></span>  
 <span data-ttu-id="659d1-126">Especifica que la consulta filtrará los duplicados del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="659d1-126">Specify that the query will filter out duplicates in the result set.</span></span> <span data-ttu-id="659d1-127">Esta opción es útil cuando solo se utilizan algunas columnas de la tabla o tablas y dichas columnas podrían contener valores duplicados, o cuando el proceso de combinar dos o más tablas genera filas duplicadas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="659d1-127">This option is useful when you are using only some of the columns from the table or tables and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="659d1-128">Elegir esta opción equivale a insertar la palabra DISTINCT en la instrucción en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="659d1-128">Choosing this option is equivalent to inserting the word DISTINCT into the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="659d1-129">**Extensión GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="659d1-129">**GROUP BY Extension**</span></span>  
 <span data-ttu-id="659d1-130">Especifica que las opciones adicionales para consultas basadas en consultas de agregado están disponibles.</span><span class="sxs-lookup"><span data-stu-id="659d1-130">Specify that additional options for queries based on aggregate queries are available.</span></span> <span data-ttu-id="659d1-131">(Solo se aplica a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="659d1-131">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="659d1-132">**Todas las columnas**</span><span class="sxs-lookup"><span data-stu-id="659d1-132">**Output All Columns**</span></span>  
 <span data-ttu-id="659d1-133">Especifica que se incluirán todas las columnas de todas las tablas de la consulta actual en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="659d1-133">Specify that all columns from all tables in the current query will be in the result set.</span></span> <span data-ttu-id="659d1-134">La elección de esta opción equivale a especificar en la instrucción SQL un asterisco (\*) en lugar de los nombres de columnas individuales a continuación de la palabra clave SELECT.</span><span class="sxs-lookup"><span data-stu-id="659d1-134">Choosing this option is equivalent to specifying an asterisk (\*) in place of individual column names after the SELECT keyword in the SQL statement.</span></span>  
  
 <span data-ttu-id="659d1-135">**Lista de parámetros de la consulta**</span><span class="sxs-lookup"><span data-stu-id="659d1-135">**Query Parameter List**</span></span>  
 <span data-ttu-id="659d1-136">Muestra los parámetros de la consulta.</span><span class="sxs-lookup"><span data-stu-id="659d1-136">Shows query parameters.</span></span> <span data-ttu-id="659d1-137">Para editar los parámetros, haga clic en la propiedad y, después, en el botón de puntos suspensivos **(...)** situado a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="659d1-137">To edit the parameters click the property and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="659d1-138">(Solo se aplica a OLE DB genérico.)</span><span class="sxs-lookup"><span data-stu-id="659d1-138">(Applies only to generic OLE DB.)</span></span>  
  
 <span data-ttu-id="659d1-139">**Comentario de SQL**</span><span class="sxs-lookup"><span data-stu-id="659d1-139">**SQL Comment**</span></span>  
 <span data-ttu-id="659d1-140">Muestra una descripción de las instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="659d1-140">Shows a description of the SQL statements.</span></span> <span data-ttu-id="659d1-141">Para ver o editar la descripción completa, haga clic en la descripción y después en el botón de puntos suspensivos **(...)** situado a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="659d1-141">To see the entire description or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="659d1-142">Los comentarios pueden incluir información, como quién utiliza la consulta y cuándo.</span><span class="sxs-lookup"><span data-stu-id="659d1-142">Your comments can include information such as who uses the query and when they use it.</span></span> <span data-ttu-id="659d1-143">(Solo se aplica a las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o versiones posteriores.)</span><span class="sxs-lookup"><span data-stu-id="659d1-143">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 databases or later.)</span></span>  
  
 <span data-ttu-id="659d1-144">**Especificación superior (Categoría)**</span><span class="sxs-lookup"><span data-stu-id="659d1-144">**Top Specification Category**</span></span>  
 <span data-ttu-id="659d1-145">Se expande para mostrar las propiedades **Superior**, **Porcentaje**, **Expresión**y **Con valores equivalentes** .</span><span class="sxs-lookup"><span data-stu-id="659d1-145">Expand to show properties for the **Top**, **Percent**, **Expression**, and **With Ties** properties.</span></span>  
  
 <span data-ttu-id="659d1-146">**(Superior)**</span><span class="sxs-lookup"><span data-stu-id="659d1-146">**(Top)**</span></span>  
 <span data-ttu-id="659d1-147">Permite especificar que la consulta incluirá una cláusula TOP, que solo devuelve las primeras *n* o el primer *n* por ciento de filas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="659d1-147">Specify hat the query will include a TOP clause, which returns only the first *n* rows or first *n* percentage of rows in the result set.</span></span> <span data-ttu-id="659d1-148">De forma predeterminada, la consulta devolverá las diez primeras filas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="659d1-148">The default is that the query returns the first 10 rows in the result set.</span></span>  
  
 <span data-ttu-id="659d1-149">Utilice este cuadro para cambiar el número de filas que se van a devolver o para especificar un porcentaje diferente.</span><span class="sxs-lookup"><span data-stu-id="659d1-149">Use this box to change the number of rows to return or to specify a different percentage.</span></span> <span data-ttu-id="659d1-150">(Solo se aplica a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o posterior.)</span><span class="sxs-lookup"><span data-stu-id="659d1-150">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later.)</span></span>  
  
 <span data-ttu-id="659d1-151">**Expression**</span><span class="sxs-lookup"><span data-stu-id="659d1-151">**Expression**</span></span>  
 <span data-ttu-id="659d1-152">Especifica el número o el porcentaje de filas que la consulta va a devolver.</span><span class="sxs-lookup"><span data-stu-id="659d1-152">Specify the number or percentage of rows that the query will return.</span></span> <span data-ttu-id="659d1-153">Si establece **Porcentaje** en Sí, este número indicará el porcentaje de filas que devolverá la consulta, mientras que si establece **Porcentaje** en No, representará el número de filas que se devolverá.</span><span class="sxs-lookup"><span data-stu-id="659d1-153">If you set **Percent** to Yes, this number is the percentage of rows the query will return; if you set **Percent** to No, it represents the number of rows to return.</span></span> <span data-ttu-id="659d1-154">(Solo se aplica a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o posterior.)</span><span class="sxs-lookup"><span data-stu-id="659d1-154">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="659d1-155">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="659d1-155">**Percent**</span></span>  
 <span data-ttu-id="659d1-156">Permite especificar que la consulta devolverá solo el primer *n* por ciento de filas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="659d1-156">Specify that the query will return only the first *n* percent of rows in the result set.</span></span> <span data-ttu-id="659d1-157">(Solo se aplica a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o posterior.)</span><span class="sxs-lookup"><span data-stu-id="659d1-157">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="659d1-158">**Con valores equivalentes**</span><span class="sxs-lookup"><span data-stu-id="659d1-158">**With Ties**</span></span>  
 <span data-ttu-id="659d1-159">Especifica que la vista incluirá una cláusula WITH TIES.</span><span class="sxs-lookup"><span data-stu-id="659d1-159">Specify that the view will include a WITH TIES clause.</span></span> <span data-ttu-id="659d1-160">WITH TIES es útil si una vista incluye una cláusula ORDER BY y una cláusula TOP basadas en un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="659d1-160">WITH TIES is useful if a view includes an ORDER BY clause and a TOP clause based on percentage.</span></span> <span data-ttu-id="659d1-161">Si se establece esta opción y el límite del porcentaje queda dentro de un conjunto de filas con valores idénticos en la cláusula ORDER BY, se ampliará la vista hasta que incluya todas las filas que faltan.</span><span class="sxs-lookup"><span data-stu-id="659d1-161">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the ORDER BY clause, the view is extended to include all such rows.</span></span> <span data-ttu-id="659d1-162">(Solo se aplica a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o posterior.)</span><span class="sxs-lookup"><span data-stu-id="659d1-162">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659d1-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="659d1-163">See Also</span></span>  
 <span data-ttu-id="659d1-164">[Consultar con parámetros &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="659d1-164">[Query with Parameters &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="659d1-165">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="659d1-165">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
