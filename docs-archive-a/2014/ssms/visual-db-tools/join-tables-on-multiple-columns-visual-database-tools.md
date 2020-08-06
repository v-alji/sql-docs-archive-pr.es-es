---
title: Combinar tablas en varias columnas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiple column joins
- joins [SQL Server], multiple columns
ms.assetid: 56a158bc-a42a-4b78-baad-4721d2d22cd3
author: stevestein
ms.author: sstein
ms.openlocfilehash: dda52fe27b2034242c8cbf458dd010240c792146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673417"
---
# <a name="join-tables-on-multiple-columns-visual-database-tools"></a><span data-ttu-id="eccb3-102">Combinar tablas en varias columnas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="eccb3-102">Join Tables on Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="eccb3-103">Puede combinar tablas con varias columnas.</span><span class="sxs-lookup"><span data-stu-id="eccb3-103">You can join tables with multiple columns.</span></span> <span data-ttu-id="eccb3-104">Es decir, puede crear una consulta que compare filas de las dos tablas solo si cumplen varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="eccb3-104">That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions.</span></span> <span data-ttu-id="eccb3-105">Si la base de datos contiene una relación en la que varias columnas de clave externa de una tabla se corresponden con una clave principal de varias columnas en la otra tabla, puede utilizar esta relación para crear una combinación de varias columnas.</span><span class="sxs-lookup"><span data-stu-id="eccb3-105">If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join.</span></span> <span data-ttu-id="eccb3-106">Para detalles, consulte [Combinar tablas automáticamente &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eccb3-106">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="eccb3-107">Aunque la base de datos no contenga una relación de clave externa de varias columnas, puede crear la combinación manualmente.</span><span class="sxs-lookup"><span data-stu-id="eccb3-107">Even if the database contains no multi-column foreign-key relationship, you can create the join manually.</span></span>  
  
### <a name="to-manually-create-a-multicolumn-join"></a><span data-ttu-id="eccb3-108">Para crear una combinación de varias columnas manualmente</span><span class="sxs-lookup"><span data-stu-id="eccb3-108">To manually create a multicolumn join</span></span>  
  
1.  <span data-ttu-id="eccb3-109">Agregue al [panel Diagrama](diagram-pane-visual-database-tools.md) las tablas que desea combinar.</span><span class="sxs-lookup"><span data-stu-id="eccb3-109">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the tables you want to join.</span></span>  
  
2.  <span data-ttu-id="eccb3-110">Arrastre el nombre de la primera columna de combinación de la ventana de la primera tabla y colóquela en la columna relacionada de la ventana de la segunda tabla.</span><span class="sxs-lookup"><span data-stu-id="eccb3-110">Drag the name of the first join column in the first table window and drop it onto the related column in the second table window.</span></span> <span data-ttu-id="eccb3-111">No puede basar una combinación en columnas del tipo de datos text, ntext o image.</span><span class="sxs-lookup"><span data-stu-id="eccb3-111">You cannot base a join on text, ntext, or image columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eccb3-112">Por lo general, las columnas de combinación deben tener el mismo tipo de datos (o compatibles).</span><span class="sxs-lookup"><span data-stu-id="eccb3-112">In general, the join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="eccb3-113">Por ejemplo, si la columna de combinación de la primera tabla es una fecha, deberá relacionarla con una columna de fecha de la segunda tabla.</span><span class="sxs-lookup"><span data-stu-id="eccb3-113">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="eccb3-114">O bien, si la primera columna de combinación es un entero, la columna de combinación relacionada debe ser también de un tipo de datos entero, pero puede tener un tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="eccb3-114">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="eccb3-115">Sin embargo, puede haber casos en los que las conversiones de tipos de datos implícitas pueden unir columnas aparentemente incompatibles correctamente.</span><span class="sxs-lookup"><span data-stu-id="eccb3-115">However, there may be cases where implicit data type conversions can join seemingly incompatible columns will work.</span></span>  
    >   
    >  <span data-ttu-id="eccb3-116">El [Diseñador de consultas y vistas](query-and-view-designer-tools-visual-database-tools.md) no comprobará los tipos de datos de las columnas que utilice para crear una combinación, pero al ejecutar la consulta, la base de datos mostrará un error si los tipos de datos no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="eccb3-116">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="eccb3-117">Arrastre el nombre de la segunda columna de combinación de la ventana de la primera tabla y colóquela en la columna relacionada de la ventana de la segunda tabla.</span><span class="sxs-lookup"><span data-stu-id="eccb3-117">Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.</span></span>  
  
4.  <span data-ttu-id="eccb3-118">Repita el paso 3 para cada par adicional de columnas de combinación en las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="eccb3-118">Repeat step 3 for each additional pair of join columns in the two tables.</span></span>  
  
5.  <span data-ttu-id="eccb3-119">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="eccb3-119">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eccb3-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eccb3-120">See Also</span></span>  
 [<span data-ttu-id="eccb3-121">Realizar consultas con combinaciones &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="eccb3-121">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
