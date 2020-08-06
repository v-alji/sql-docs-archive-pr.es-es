---
title: Tipos de consultas compatibles (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Delete query
- queries [SQL Server], types
- Update query
- Query Designer [SQL Server], query types
- Criteria pane
- Insert Values query
- Select query
- Make Table query
- Insert Results query
- Diagram pane [Visual Database Tools]
- View Designer, query types
ms.assetid: 72b9116c-c128-4078-a78d-257a2955a3f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b00b7018fc6d0b631696811bd1870e09842b4162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747849"
---
# <a name="supported-query-types-visual-database-tools"></a><span data-ttu-id="a01f3-102">Tipos de consultas compatibles (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a01f3-102">Supported Query Types (Visual Database Tools)</span></span>
  <span data-ttu-id="a01f3-103">Puede crear los siguientes tipos de consulta en los paneles Diagrama y Criterios (paneles gráficos) del [Diseñador de consultas y vistas](visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="a01f3-103">You can create the following types of queries in the Diagram and Criteria panes (the graphical panes) of the [Query and View Designer](visual-database-tools.md):</span></span>  
  
-   <span data-ttu-id="a01f3-104">**Consulta Select** Recupera datos de una o más tablas o vistas.</span><span class="sxs-lookup"><span data-stu-id="a01f3-104">**Select query** Retrieves data from one or more tables or views.</span></span> <span data-ttu-id="a01f3-105">Este tipo de consulta crea una instrucción SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="a01f3-105">This type of query creates an SQL SELECT statement.</span></span>  
  
-   <span data-ttu-id="a01f3-106">**Insertar resultados** Crea filas nuevas mediante la copia de filas existentes de una tabla a otra, o a la misma tabla como nuevas filas.</span><span class="sxs-lookup"><span data-stu-id="a01f3-106">**Insert Results** Creates new rows by copying existing rows from one table into another, or into the same table as new rows.</span></span> <span data-ttu-id="a01f3-107">Este tipo de consulta crea una instrucción SQL INSERT INTO...SELECT.</span><span class="sxs-lookup"><span data-stu-id="a01f3-107">This type of query creates an SQL INSERT INTO...SELECT statement.</span></span>  
  
-   <span data-ttu-id="a01f3-108">**Insertar valores** Crea una nueva fila e inserta valores en columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="a01f3-108">**Insert Values** Creates a new row and inserts values into specified columns.</span></span> <span data-ttu-id="a01f3-109">Este tipo de consulta crea una instrucción SQL INSERT INTO...VALUES.</span><span class="sxs-lookup"><span data-stu-id="a01f3-109">This type of query creates an SQL INSERT INTO...VALUES statement.</span></span>  
  
-   <span data-ttu-id="a01f3-110">**Consulta de actualización** Cambia los valores de columnas individuales de una o más filas existentes en una tabla.</span><span class="sxs-lookup"><span data-stu-id="a01f3-110">**Update query** Changes the values of individual columns in one or more existing rows in a table.</span></span> <span data-ttu-id="a01f3-111">Este tipo de consulta crea una instrucción SQL UPDATE...SET.</span><span class="sxs-lookup"><span data-stu-id="a01f3-111">This type of query creates an SQL UPDATE...SET statement.</span></span>  
  
-   <span data-ttu-id="a01f3-112">**Consulta de eliminación** Quita una o más filas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="a01f3-112">**Delete query** Removes one or more rows from a table.</span></span> <span data-ttu-id="a01f3-113">Este tipo de consulta crea una instrucción SQL DELETE.</span><span class="sxs-lookup"><span data-stu-id="a01f3-113">This type of query creates an SQL DELETE statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a01f3-114">Una consulta Delete quita filas completas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a01f3-114">A Delete query removes entire rows from the table.</span></span> <span data-ttu-id="a01f3-115">Si desea eliminar valores de columnas de datos individuales, utilice una consulta Update.</span><span class="sxs-lookup"><span data-stu-id="a01f3-115">If you want to delete values from individual data columns, use an Update query.</span></span>  
  
-   <span data-ttu-id="a01f3-116">**Consulta de creación de tabla** Crea una nueva tabla y crea filas en ella copiando los resultados de una consulta en la misma.</span><span class="sxs-lookup"><span data-stu-id="a01f3-116">**Make Table query** Creates a new table and creates rows in it by copying the results of a query into it.</span></span> <span data-ttu-id="a01f3-117">Este tipo de consulta crea una instrucción SQL SELECT...INTO.</span><span class="sxs-lookup"><span data-stu-id="a01f3-117">This type of query creates an SQL SELECT...INTO statement.</span></span>  
  
 <span data-ttu-id="a01f3-118">Además de las consultas que puede crear mediante el uso de los paneles gráficos, puede especificar cualquier instrucción SQL en el panel SQL, como consultas de unión.</span><span class="sxs-lookup"><span data-stu-id="a01f3-118">In addition to the queries you can create using the graphical panes, you can enter any SQL statement into the SQL pane, such as Union queries.</span></span>  
  
 <span data-ttu-id="a01f3-119">Cuando crea consultas mediante instrucciones SQL que no puedan representarse en los paneles gráficos, el Diseñador de consultas y vistas atenúa esos paneles para indicar que no reflejan la consulta que está creando.</span><span class="sxs-lookup"><span data-stu-id="a01f3-119">When you create queries using SQL statements that cannot be represented in the graphical panes, the Query and View Designer dims those panes to indicate that they do not reflect the query you are creating.</span></span> <span data-ttu-id="a01f3-120">Sin embargo, los paneles atenuados están activos todavía y, en muchos casos, puede realizar cambios en la consulta en esos paneles.</span><span class="sxs-lookup"><span data-stu-id="a01f3-120">However, the dimmed panes are still active and, in many cases, you can make changes to the query in those panes.</span></span> <span data-ttu-id="a01f3-121">Si los cambios que realiza tienen como resultado una consulta que puede representarse en los paneles gráficos, esos paneles ya no estarán atenuados.</span><span class="sxs-lookup"><span data-stu-id="a01f3-121">If the changes you make result in a query that can be represented in the graphical panes, those panes are no longer dimmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a01f3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a01f3-122">See Also</span></span>  
 <span data-ttu-id="a01f3-123">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a01f3-123">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a01f3-124">Tipos de consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a01f3-124">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
