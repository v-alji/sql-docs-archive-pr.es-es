---
title: Combinar tablas manualmente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- manual joins [SQL Server]
- joins [SQL Server], manual
- joins [SQL Server], creating
ms.assetid: 9c785356-646b-4c87-82d4-25efd6051d9d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83f7615be3f5f18164dd3ca0f62ef6cbd9167be3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743839"
---
# <a name="join-tables-manually-visual-database-tools"></a><span data-ttu-id="537f1-102">Combinar tablas manualmente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="537f1-102">Join Tables Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="537f1-103">Cuando se agregan dos o más tablas a una consulta, el [Diseñador de consultas y vistas](visual-database-tools.md) intenta combinarlas en función de datos comunes o de información almacenada en la base de datos acerca de cómo se relacionan las tablas.</span><span class="sxs-lookup"><span data-stu-id="537f1-103">When you add two (or more) tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to join them based on common data or on information stored in the database about how tables are related.</span></span> <span data-ttu-id="537f1-104">Para detalles, consulte [Combinar tablas automáticamente &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="537f1-104">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span></span> <span data-ttu-id="537f1-105">No obstante, si el Diseñador de consultas y vistas no ha combinado las tablas automáticamente o si desea crear otras condiciones de combinación entre tablas, puede combinar las tablas de forma manual.</span><span class="sxs-lookup"><span data-stu-id="537f1-105">However, if the Query and View Designer has not joined the tables automatically, or if you want to create additional join conditions between tables, you can join tables manually.</span></span>  
  
 <span data-ttu-id="537f1-106">Puede crear combinaciones basadas en comparaciones entre dos columnas cualesquiera y no solo entre columnas que contengan la misma información.</span><span class="sxs-lookup"><span data-stu-id="537f1-106">You can create joins based on comparisons between any two columns, not just columns that contain the same information.</span></span> <span data-ttu-id="537f1-107">Por ejemplo, si la base de datos contiene dos tablas, `titles` y `roysched`, puede comparar los valores de la columna `ytd_sales` de la tabla `titles` con las columnas `lorange` y `hirange` de la tabla `roysched` .</span><span class="sxs-lookup"><span data-stu-id="537f1-107">For example, if your database contains two tables, `titles` and `roysched`, you can compare values in the `ytd_sales` column of the `titles` table against the `lorange` and `hirange` columns in the `roysched` table.</span></span> <span data-ttu-id="537f1-108">Esta combinación le permitirá buscar títulos cuyas ventas anuales acumuladas estén comprendidas entre los intervalos inferior y superior de los pagos por regalías (royalties).</span><span class="sxs-lookup"><span data-stu-id="537f1-108">Creating this join would allow you to find titles for which the year-to-date sales falls between the low and high ranges for the royalty payments.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="537f1-109">Las combinaciones funcionan con más rapidez si se indizan las columnas de la condición de combinación.</span><span class="sxs-lookup"><span data-stu-id="537f1-109">Joins work fastest if the columns in the join condition have been indexed.</span></span> <span data-ttu-id="537f1-110">En algunas ocasiones, la combinación realizada en columnas no indizadas puede dar lugar a una consulta lenta.</span><span class="sxs-lookup"><span data-stu-id="537f1-110">In some cases, joining on unindexed columns can result in a slow query.</span></span>  
  
### <a name="to-manually-join-tables-or-table-structured-objects"></a><span data-ttu-id="537f1-111">Para combinar manualmente tablas u objetos estructurados en tablas</span><span class="sxs-lookup"><span data-stu-id="537f1-111">To manually join tables or table-structured objects</span></span>  
  
1.  <span data-ttu-id="537f1-112">Agregue al [panel Diagrama](diagram-pane-visual-database-tools.md) los objetos que desee combinar.</span><span class="sxs-lookup"><span data-stu-id="537f1-112">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the objects you want to join.</span></span>  
  
2.  <span data-ttu-id="537f1-113">Arrastre el nombre de la columna de combinación de la primera tabla u objeto estructurado en tabla y colóquelo en la columna relacionada de la segunda tabla u objeto estructurado en tabla.</span><span class="sxs-lookup"><span data-stu-id="537f1-113">Drag the name of the join column in the first table or table-structured object and drop it onto the related column in the second table or table-structured object.</span></span> <span data-ttu-id="537f1-114">No puede basar una combinación en columnas del tipo de datos `text`, `ntext` o `mage`.</span><span class="sxs-lookup"><span data-stu-id="537f1-114">You cannot base a join on `text`, `ntext`, or i`mage` columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="537f1-115">Las columnas de combinación deben tener el mismo tipo de datos (o compatibles).</span><span class="sxs-lookup"><span data-stu-id="537f1-115">The join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="537f1-116">Por ejemplo, si la columna de combinación de la primera tabla es una fecha, deberá relacionarla con una columna de fecha de la segunda tabla.</span><span class="sxs-lookup"><span data-stu-id="537f1-116">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="537f1-117">O bien, si la primera columna de combinación es un entero, la columna de combinación relacionada debe ser también de un tipo de datos entero, pero puede tener un tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="537f1-117">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="537f1-118">El Diseñador de consultas y vistas no comprobará los tipos de datos de las columnas que utilice para crear una combinación, pero al ejecutar la consulta, la base de datos mostrará un error si los tipos de datos no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="537f1-118">The Query and View Designer will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="537f1-119">Si es necesario, cambie el operador de combinación; de forma predeterminada, el operador es un signo igual (=).</span><span class="sxs-lookup"><span data-stu-id="537f1-119">If necessary, change the join operator; by default, the operator is an equal sign (=).</span></span> <span data-ttu-id="537f1-120">Para detalles, consulte [Modificar operadores de combinación &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="537f1-120">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="537f1-121">El Diseñador de consultas y vistas agrega una cláusula INNER JOIN a la instrucción SQL en el [panel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="537f1-121">The Query and View Designer adds an INNER JOIN clause to the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="537f1-122">Puede cambiar el tipo a una combinación externa.</span><span class="sxs-lookup"><span data-stu-id="537f1-122">You can change the type to an outer join.</span></span> <span data-ttu-id="537f1-123">Para detalles, consulte [Crear combinaciones externas &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="537f1-123">For details see [Create Outer Joins &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537f1-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="537f1-124">See Also</span></span>  
 [<span data-ttu-id="537f1-125">Realizar consultas con combinaciones &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="537f1-125">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
