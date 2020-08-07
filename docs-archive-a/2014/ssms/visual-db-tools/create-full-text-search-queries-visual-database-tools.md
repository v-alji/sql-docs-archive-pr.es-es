---
title: Crear consultas de búsqueda de texto completo (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CONTAINS predicate (Transact-SQL)
- queries [full-text search], creating
- full-text queries [SQL Server], creating
ms.assetid: 537fa556-390e-4c88-9b8e-679848d94abc
author: stevestein
ms.author: sstein
ms.openlocfilehash: f84ab465da0a1b7ac1da1211de1d5199fd28ee95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745602"
---
# <a name="create-full-text-search-queries-visual-database-tools"></a><span data-ttu-id="7dc75-102">Crear consultas de búsqueda de texto completo (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7dc75-102">Create Full-Text Search Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="7dc75-103">Las búsquedas de texto completo utilizan el predicado CONTAINS para buscar las filas que contienen el texto especificado en una determinada columna.</span><span class="sxs-lookup"><span data-stu-id="7dc75-103">Full-text searches use the CONTAINS predicate to locate rows that have specified text in a given column.</span></span> <span data-ttu-id="7dc75-104">Las búsquedas de texto completo solo pueden realizarse en las columnas que tienen índices de texto completo activos.</span><span class="sxs-lookup"><span data-stu-id="7dc75-104">Full-Text searches are only possible on columns that have active full-text indexes.</span></span> <span data-ttu-id="7dc75-105">Si intenta utilizar la cláusula CONTAINS en una columna que no tiene un índice de texto completo activo, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="7dc75-105">If you attempt to use the CONTAINS clause on a column that does not have a currently active full-text index, you will receive an error.</span></span> <span data-ttu-id="7dc75-106">Para obtener más información sobre los índices de texto completo y la cláusula Contains, vea [búsqueda de texto completo](../../relational-databases/search/full-text-search.md) y [contiene &#40;&#41;de Transact-SQL ](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7dc75-106">For more information on full-text indexes and the CONTAINS clause, see [Full-Text Search](../../relational-databases/search/full-text-search.md) and [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
### <a name="to-create-a-full-text-search-query"></a><span data-ttu-id="7dc75-107">Para crear una consulta de búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="7dc75-107">To create a full-text search query</span></span>  
  
1.  <span data-ttu-id="7dc75-108">Abra una consulta del Explorador de soluciones o cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="7dc75-108">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="7dc75-109">Utilice la función CONTAINS en la cláusula WHERE de su consulta para buscar una columna de texto completo.</span><span class="sxs-lookup"><span data-stu-id="7dc75-109">In the WHERE clause of your query, use the CONTAINS function to search a full-text column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc75-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7dc75-110">See Also</span></span>  
 <span data-ttu-id="7dc75-111">[Tipos de consultas admitidos &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7dc75-111">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="7dc75-112">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7dc75-112">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7dc75-113">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7dc75-113">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
