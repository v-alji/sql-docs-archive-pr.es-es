---
title: Realizar consultas con combinaciones (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [Visual Database Tools]
- View Designer, joins
- table joins [SQL Server]
- multiple table joins
- Visual Database Tools [SQL Server], queries
- Query Designer [SQL Server], joins
- joins [SQL Server], queries
ms.assetid: 8f068207-d777-4e64-8c4c-d821f0ddb450
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9d0053e6786d96508be8a87347cdc0b19975a3fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744954"
---
# <a name="query-with-joins-visual-database-tools"></a><span data-ttu-id="9e593-102">Realizar consultas con combinaciones (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-102">Query with Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="9e593-103">El resultado de una consulta puede incluir datos de varias tablas o de varios objetos con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="9e593-103">A query result can include data from multiple tables or table-valued objects.</span></span> <span data-ttu-id="9e593-104">Para combinar los datos provenientes de varios objetos de tabla, utilice la operación JOIN de SQL.</span><span class="sxs-lookup"><span data-stu-id="9e593-104">To combine data from multiple table-valued objects, you use the JOIN operation from SQL.</span></span>  
  
 <span data-ttu-id="9e593-105">Para obtener información sobre cómo crear consultas que utilizan varias tablas, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="9e593-105">For information about creating queries using multiple tables, see the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e593-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9e593-106">In This Section</span></span>  
 [<span data-ttu-id="9e593-107">Modificar operadores de combinación (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-107">Modify Join Operators &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
 <span data-ttu-id="9e593-108">Especifica que las tablas se deben combinar mediante un operador distinto de igual (=).</span><span class="sxs-lookup"><span data-stu-id="9e593-108">Specify that tables should be joined using an operator other than equal (=).</span></span>  
  
 [<span data-ttu-id="9e593-109">Cómo representa combinaciones el Diseñador de consultas y vistas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-109">How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;</span></span>](how-the-query-and-view-designer-represents-joins-visual-database-tools.md)  
 <span data-ttu-id="9e593-110">Explica la representación gráfica de la combinación tal y como se ve en el panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="9e593-110">Explains the graphic representation of the join as you see it in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="9e593-111">Combinar tablas automáticamente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-111">Join Tables Automatically &#40;Visual Database Tools&#41;</span></span>](join-tables-automatically-visual-database-tools.md)  
 <span data-ttu-id="9e593-112">Proporciona los pasos necesarios para permitir que el Diseñador de consultas y vistas determine si las tablas deben combinarse.</span><span class="sxs-lookup"><span data-stu-id="9e593-112">Steps for allowing the Query and View Designer determine if tables should be joined.</span></span>  
  
 [<span data-ttu-id="9e593-113">Combinar tablas manualmente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-113">Join Tables Manually &#40;Visual Database Tools&#41;</span></span>](join-tables-manually-visual-database-tools.md)  
 <span data-ttu-id="9e593-114">Proporciona los pasos necesarios para crear de forma manual una combinación en el panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="9e593-114">Steps for creating a join manually in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="9e593-115">Combinar tablas en varias columnas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-115">Join Tables on Multiple Columns &#40;Visual Database Tools&#41;</span></span>](join-tables-on-multiple-columns-visual-database-tools.md)  
 <span data-ttu-id="9e593-116">Proporciona los pasos para combinar tablas con varios criterios en cada tabla.</span><span class="sxs-lookup"><span data-stu-id="9e593-116">Steps for joining tables with multiple criteria for each table.</span></span>  
  
 [<span data-ttu-id="9e593-117">Crear combinaciones externas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-117">Create Outer Joins &#40;Visual Database Tools&#41;</span></span>](create-outer-joins-visual-database-tools.md)  
 <span data-ttu-id="9e593-118">Especifica que las tablas combinadas deben incluir filas, aunque no coincidan con las filas de la tabla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9e593-118">Specify that joined tables should include rows even when they do not match rows in the corresponding table.</span></span>  
  
 [<span data-ttu-id="9e593-119">Quitar combinaciones (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-119">Remove Joins &#40;Visual Database Tools&#41;</span></span>](remove-joins-visual-database-tools.md)  
 <span data-ttu-id="9e593-120">Proporciona los pasos necesarios para eliminar una combinación entre tablas.</span><span class="sxs-lookup"><span data-stu-id="9e593-120">Steps for removing a join between tables.</span></span>  
  
 [<span data-ttu-id="9e593-121">Crear autocombinaciones de forma automática (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-121">Create Self-Joins Automatically &#40;Visual Database Tools&#41;</span></span>](create-self-joins-automatically-visual-database-tools.md)  
 <span data-ttu-id="9e593-122">Proporciona los pasos necesarios para permitir que el Diseñador de consultas y vistas cree una autocombinación.</span><span class="sxs-lookup"><span data-stu-id="9e593-122">Steps for allowing the Query and View Designer to create a self-join.</span></span>  
  
 [<span data-ttu-id="9e593-123">Crear autocombinaciones manualmente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-123">Create Self-Joins Manually &#40;Visual Database Tools&#41;</span></span>](create-self-joins-manually-visual-database-tools.md)  
 <span data-ttu-id="9e593-124">Proporciona los pasos necesarios para utilizar una combinación para buscar subconjuntos de datos dentro de una única tabla.</span><span class="sxs-lookup"><span data-stu-id="9e593-124">Steps for using a join to find subsets of data within a single table.</span></span>  
  
 [<span data-ttu-id="9e593-125">Ver las propiedades de una combinación (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-125">View Join Properties &#40;Visual Database Tools&#41;</span></span>](view-join-properties-visual-database-tools.md)  
 <span data-ttu-id="9e593-126">Pasos para ver las propiedades de una combinación.</span><span class="sxs-lookup"><span data-stu-id="9e593-126">Steps for viewing the properties of a join.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9e593-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9e593-127">Related Sections</span></span>  
 [<span data-ttu-id="9e593-128">Tipos de consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-128">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
 <span data-ttu-id="9e593-129">Proporciona vínculos a temas en los que se describen los tipos de consultas admitidos.</span><span class="sxs-lookup"><span data-stu-id="9e593-129">Provides links to topics describing the supported query types.</span></span>  
  
 [<span data-ttu-id="9e593-130">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
 <span data-ttu-id="9e593-131">Proporciona vínculos a temas en los que se tratan las tareas de consulta más comunes.</span><span class="sxs-lookup"><span data-stu-id="9e593-131">Provides links to topics covering the most common query tasks.</span></span>  
  
 [<span data-ttu-id="9e593-132">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9e593-132">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
 <span data-ttu-id="9e593-133">Proporciona vínculos a temas en los que se tratan los distintos tipos de criterios de búsqueda y cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="9e593-133">Provides links to topics covering the various kinds of search criteria and how to use them.</span></span>  
  
  
