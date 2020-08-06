---
title: Cómo representa combinaciones el diseñador de consultas y vistas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL pane [Visual Database Tools]
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 20a99dcb-83bd-4aa6-9139-92e2e5ba4887
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55fdea533436f9fa7c2a902667b3166085c27e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673973"
---
# <a name="how-the-query-and-view-designer-represents-joins-visual-database-tools"></a><span data-ttu-id="b40a4-102">Cómo representa combinaciones el Diseñador de consultas y vistas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b40a4-102">How the Query and View Designer Represents Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="b40a4-103">Si las tablas están combinadas, el [Diseñador de consultas y vistas](visual-database-tools.md) representa la combinación de forma gráfica en el [panel Diagrama](diagram-pane-visual-database-tools.md) y mediante sintaxis SQL en el [panel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b40a4-103">If tables are joined, the [Query and View Designer](visual-database-tools.md) represents the join graphically in the [Diagram pane](diagram-pane-visual-database-tools.md) and by using SQL syntax in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="diagram-pane"></a><span data-ttu-id="b40a4-104">panel Diagrama</span><span class="sxs-lookup"><span data-stu-id="b40a4-104">Diagram Pane</span></span>  
 <span data-ttu-id="b40a4-105">En el panel Diagrama, el Diseñador de consultas y vistas muestra una línea de combinación entre las columnas de datos implicadas en la combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-105">In the Diagram pane the Query and View Designer displays a join line between the data columns involved in the join.</span></span> <span data-ttu-id="b40a4-106">El Diseñador de consultas y vistas muestra una línea de combinación para cada condición de combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-106">The Query and View Designer displays one join line for each join condition.</span></span> <span data-ttu-id="b40a4-107">Por ejemplo, la ilustración siguiente muestra una línea de combinación entre dos tablas que están combinadas:</span><span class="sxs-lookup"><span data-stu-id="b40a4-107">For example, the following illustration shows a join line between two tables that are joined:</span></span>  
  
 <span data-ttu-id="b40a4-108">![La línea de combinación muestra la relación entre dos tablas](../../database-engine/media//dv3wbig.gif "La línea de combinación muestra la relación entre dos tablas")</span><span class="sxs-lookup"><span data-stu-id="b40a4-108">![Join line shows relationship between two tables](../../database-engine/media//dv3wbig.gif "Join line shows relationship between two tables")</span></span>  
  
 <span data-ttu-id="b40a4-109">Si las tablas están combinadas mediante más de una condición de combinación, el Diseñador de consultas y vistas muestra varias líneas de combinación, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b40a4-109">If tables are joined using more than one join condition, the Query and View Designer displays multiple join lines, as in the following example:</span></span>  
  
 <span data-ttu-id="b40a4-110">![Tablas combinadas usando más de una condición de combinación](../../database-engine/media//dv3w9n1.gif "Tablas combinadas usando más de una condición de combinación")</span><span class="sxs-lookup"><span data-stu-id="b40a4-110">![Tables joined using more than one join condition](../../database-engine/media//dv3w9n1.gif "Tables joined using more than one join condition")</span></span>  
  
 <span data-ttu-id="b40a4-111">Si no se muestran las columnas de datos combinadas (por ejemplo, el rectángulo que representa la tabla o el objeto con estructura de tabla está minimizado o la combinación incluye una expresión), el Diseñador de consultas coloca la línea de combinación en la barra de título del rectángulo que representa la tabla o el objeto con estructura de tabla.</span><span class="sxs-lookup"><span data-stu-id="b40a4-111">If the joined data columns are not displayed (for example, the rectangle representing the table or table-structured object is minimized or the join involves an expression), the Query and View Designer places the join line at the title bar of the rectangle representing the table or table-structured object.</span></span>  
  
 <span data-ttu-id="b40a4-112">La forma del icono situado en el centro de la línea de combinación indica cómo se combinan las tablas u objetos con estructura de tabla.</span><span class="sxs-lookup"><span data-stu-id="b40a4-112">The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined.</span></span> <span data-ttu-id="b40a4-113">Si la cláusula de combinación utiliza un operador que no sea igual (=), el operador se muestra en el icono de línea de combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-113">If the join clause uses an operator other than equal (=), the operator appears in the join line icon.</span></span> <span data-ttu-id="b40a4-114">La tabla siguiente muestra los iconos que aparecen en la línea de combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-114">The following table lists the icons that appear in the join line.</span></span>  
  
|<span data-ttu-id="b40a4-115">**Icono de línea de combinación**</span><span class="sxs-lookup"><span data-stu-id="b40a4-115">**Join line icon**</span></span>|<span data-ttu-id="b40a4-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b40a4-116">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="b40a4-117">![Icono de Visual Database Tools](../../database-engine/media//dv3wbih.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-117">![Visual Database Tools icon](../../database-engine/media//dv3wbih.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-118">Combinación interna (creada mediante un signo igual).</span><span class="sxs-lookup"><span data-stu-id="b40a4-118">Inner join (created using an equal sign).</span></span>|  
|<span data-ttu-id="b40a4-119">![Icono de Visual Database Tools](../../database-engine/media//dv3wbii.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-119">![Visual Database Tools icon](../../database-engine/media//dv3wbii.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-120">Combinación interna basada en el operador "mayor que".</span><span class="sxs-lookup"><span data-stu-id="b40a4-120">Inner join based on the "greater than" operator.</span></span>|  
|<span data-ttu-id="b40a4-121">![Icono de Visual Database Tools](../../database-engine/media//dv3wbij.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-121">![Visual Database Tools icon](../../database-engine/media//dv3wbij.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-122">Combinación externa en la que se incluirán todas las filas de la tabla representada a la izquierda, incluso si no tienen coincidencias en la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="b40a4-122">Outer join in which all rows from the table represented on the left will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="b40a4-123">![Icono de Visual Database Tools](../../database-engine/media//dv3wbik.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-123">![Visual Database Tools icon](../../database-engine/media//dv3wbik.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-124">Combinación externa en la que se incluirán todas las filas de la tabla representada a la derecha, incluso si no tienen coincidencias en la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="b40a4-124">Outer join in which all rows from the table represented on the right will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="b40a4-125">![Icono de Visual Database Tools](../../database-engine/media//dv3wbil.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-125">![Visual Database Tools icon](../../database-engine/media//dv3wbil.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-126">Combinación externa completa en la que se incluirán todas las filas de ambas tablas, incluso si no tienen coincidencias en la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="b40a4-126">Full outer join in which all rows from both tables will be included, even if they do not have matches in the related table.</span></span>|  
  
 <span data-ttu-id="b40a4-127">Los símbolos situados en los extremos de la línea de combinación indican el tipo de combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-127">The symbols on the ends of the join line indicate the type of join.</span></span> <span data-ttu-id="b40a4-128">La tabla siguiente muestra los tipos de combinaciones y los iconos que aparecen en los extremos de la línea de combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-128">The following table lists the types of joins and the icons displayed on the ends of the join line.</span></span>  
  
|<span data-ttu-id="b40a4-129">**Icono situado en los extremos de la línea de combinación**</span><span class="sxs-lookup"><span data-stu-id="b40a4-129">**Icon on ends of join line**</span></span>|<span data-ttu-id="b40a4-130">**Tipo de combinación**</span><span class="sxs-lookup"><span data-stu-id="b40a4-130">**Type of join**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="b40a4-131">![Icono de Visual Database Tools](../../database-engine/media//dv3wbim.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-131">![Visual Database Tools icon](../../database-engine/media//dv3wbim.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-132">Combinación uno a uno.</span><span class="sxs-lookup"><span data-stu-id="b40a4-132">One-to-one join.</span></span>|  
|<span data-ttu-id="b40a4-133">![Icono de Visual Database Tools](../../database-engine/media//dv3wbin.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-133">![Visual Database Tools icon](../../database-engine/media//dv3wbin.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-134">Combinación uno a varios.</span><span class="sxs-lookup"><span data-stu-id="b40a4-134">One-to-many join.</span></span>|  
|<span data-ttu-id="b40a4-135">![Icono de Visual Database Tools](../../database-engine/media//dv3wbio.gif "Icono de Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="b40a4-135">![Visual Database Tools icon](../../database-engine/media//dv3wbio.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="b40a4-136">El Diseñador de consultas y vistas no puede determinar el tipo de combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-136">Query and View Designer cannot determine the join type.</span></span> <span data-ttu-id="b40a4-137">Esta situación ocurre con más frecuencia cuando ha creado una combinación de forma manual.</span><span class="sxs-lookup"><span data-stu-id="b40a4-137">This situation occurs most often when you have created a join manually.</span></span>|  
  
## <a name="sql-pane"></a><span data-ttu-id="b40a4-138">panel SQL</span><span class="sxs-lookup"><span data-stu-id="b40a4-138">SQL Pane</span></span>  
 <span data-ttu-id="b40a4-139">Una combinación puede expresarse de varias maneras en una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="b40a4-139">A join can be expressed in a number of ways in an SQL statement.</span></span> <span data-ttu-id="b40a4-140">La sintaxis exacta depende de la base de datos que esté utilizando y de la forma en que haya definido la combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-140">The exact syntax depends on the database you are using and on how you have defined the join.</span></span>  
  
 <span data-ttu-id="b40a4-141">Las opciones de sintaxis para combinar tablas incluyen:</span><span class="sxs-lookup"><span data-stu-id="b40a4-141">Syntax options for joining tables include:</span></span>  
  
-   <span data-ttu-id="b40a4-142">**Calificador JOIN para la cláusula FROM**.</span><span class="sxs-lookup"><span data-stu-id="b40a4-142">**JOIN qualifier for the FROM clause**.</span></span>   <span data-ttu-id="b40a4-143">Las palabras clave INNER y OUTER especifican el tipo de combinación.</span><span class="sxs-lookup"><span data-stu-id="b40a4-143">The keywords INNER and OUTER specify the join type.</span></span> <span data-ttu-id="b40a4-144">Esta sintaxis es estándar para SQL ANSI 92.</span><span class="sxs-lookup"><span data-stu-id="b40a4-144">This syntax is standard for ANSI 92 SQL.</span></span>  
  
     <span data-ttu-id="b40a4-145">Por ejemplo, si combina las tablas `publishers` y `pub_info` según la columna `pub_id` de cada tabla, la instrucción SQL resultante podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b40a4-145">For example, if you join the `publishers` and `pub_info` tables based on the `pub_id` column in each table, the resulting SQL statement might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM publishers INNER JOIN pub_info ON  
       publishers.pub_id = pub_info.pub_id  
    ```  
  
     <span data-ttu-id="b40a4-146">Si crea una combinación externa, aparecen las palabras LEFT OUTER o RIGHT OUTER en lugar de la palabra INNER.</span><span class="sxs-lookup"><span data-stu-id="b40a4-146">If you create an outer join, the words LEFT OUTER or RIGHT OUTER appear in place of the word INNER.</span></span>  
  
-   <span data-ttu-id="b40a4-147">**La cláusula WHERE compara columnas de ambas tablas**.</span><span class="sxs-lookup"><span data-stu-id="b40a4-147">**WHERE clause compares columns in both tables**.</span></span>   <span data-ttu-id="b40a4-148">Aparecerá una cláusula WHERE si la base de datos no admite la sintaxis JOIN, o si la especificó el usuario.</span><span class="sxs-lookup"><span data-stu-id="b40a4-148">A WHERE clause appears if the database does not support the JOIN syntax (or if you entered it yourself).</span></span> <span data-ttu-id="b40a4-149">Si la combinación se crea en la cláusula WHERE, ambos nombres de tabla aparecen en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="b40a4-149">If the join is created in the WHERE clause, both table names appear in the FROM clause.</span></span>  
  
     <span data-ttu-id="b40a4-150">Por ejemplo, la instrucción siguiente combina las tablas `publishers` y `pub_info` .</span><span class="sxs-lookup"><span data-stu-id="b40a4-150">For example, the following statement joins the `publishers` and `pub_info` tables.</span></span>  
  
    ```  
    SELECT *  
    FROM publishers, pub_info  
    WHERE publishers.pub_id = pub_info.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b40a4-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b40a4-151">See Also</span></span>  
 <span data-ttu-id="b40a4-152">[Realizar consultas con combinaciones &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b40a4-152">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b40a4-153">Cuadro de diálogo Combinar &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b40a4-153">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
