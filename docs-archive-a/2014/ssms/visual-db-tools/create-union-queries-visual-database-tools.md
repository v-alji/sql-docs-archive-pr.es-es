---
title: Crear consultas UNION (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3c10f39c3e44844c4ec8a6a2328c41ea2de350d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673985"
---
# <a name="create-union-queries-visual-database-tools"></a><span data-ttu-id="86b6e-102">Crear consultas UNION (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="86b6e-102">Create UNION Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="86b6e-103">La palabra clave UNION permite incluir los resultados de dos instrucciones SELECT en una única tabla.</span><span class="sxs-lookup"><span data-stu-id="86b6e-103">The UNION keyword enables you to include the results of two SELECT statements in one resulting table.</span></span> <span data-ttu-id="86b6e-104">Todas las filas devueltas desde la instrucción SELECT se combinan como resultado de la expresión UNION.</span><span class="sxs-lookup"><span data-stu-id="86b6e-104">All rows returned from either SELECT statement are combined into the result of the UNION expression.</span></span> <span data-ttu-id="86b6e-105">Para obtener ejemplos, vea [ejemplos de SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="86b6e-105">For examples, see [SELECT Examples &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86b6e-106">En el panel Diagrama solo puede aparecer una cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="86b6e-106">The Diagram pane can only display one SELECT clause.</span></span> <span data-ttu-id="86b6e-107">Por tanto, cuando trabaje con la consulta UNION, el Diseñador de consultas ocultará el panel de operaciones de tablas.</span><span class="sxs-lookup"><span data-stu-id="86b6e-107">Therefore, when you are working with a UNION query, Query Designer hides the Table Operations pane.</span></span>  
  
### <a name="to-create-a-merged-select-query"></a><span data-ttu-id="86b6e-108">Para crear una consulta SELECT mezclada</span><span class="sxs-lookup"><span data-stu-id="86b6e-108">To create a Merged SELECT query</span></span>  
  
1.  <span data-ttu-id="86b6e-109">Abra una consulta o cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="86b6e-109">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="86b6e-110">En el panel SQL, escriba una expresión UNION válida.</span><span class="sxs-lookup"><span data-stu-id="86b6e-110">In the SQL pane, type a valid UNION expression.</span></span>  
  
     <span data-ttu-id="86b6e-111">El ejemplo siguiente es una expresión UNION válida.</span><span class="sxs-lookup"><span data-stu-id="86b6e-111">The following example is a valid UNION expression.</span></span>  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  <span data-ttu-id="86b6e-112">En el menú **Diseñador de consultas** , haga clic en **Ejecutar SQL** para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="86b6e-112">On the **Query Designer** menu, click **Execute SQL** to run the query.</span></span>  
  
     <span data-ttu-id="86b6e-113">El Diseñador de consultas da formato a su consulta UNION.</span><span class="sxs-lookup"><span data-stu-id="86b6e-113">Your UNION query is now formatted by Query Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b6e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86b6e-114">See Also</span></span>  
 <span data-ttu-id="86b6e-115">[Tipos de consultas admitidos &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="86b6e-115">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="86b6e-116">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="86b6e-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="86b6e-117">[Realizar operaciones básicas con consultas &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="86b6e-117">[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="86b6e-118">UNION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="86b6e-118">UNION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/set-operators-union-transact-sql)  
  
  
