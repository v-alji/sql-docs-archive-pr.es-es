---
title: Dibujar relaciones reflexivas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- drawing reflexive relationships
- reflexive relationships
- database diagrams [SQL Server], relationships
ms.assetid: e218363f-faec-46d5-9904-a537fbcc994d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e5056b1a5d0d884edbc4fc818fe8c7ef5cc8ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674490"
---
# <a name="draw-reflexive-relationships-visual-database-tools"></a><span data-ttu-id="cef4f-102">Dibujar relaciones reflexivas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="cef4f-102">Draw Reflexive Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="cef4f-103">Puede crear una relación reflexiva para vincular una o más columnas de una tabla con una o más columnas de la misma tabla.</span><span class="sxs-lookup"><span data-stu-id="cef4f-103">You create a reflexive relationship to link a column or columns in a table with another column or columns in the same table.</span></span> <span data-ttu-id="cef4f-104">Por ejemplo, suponga que la tabla `employee` contiene una columna `emp_id` y una columna `mgr_id` .</span><span class="sxs-lookup"><span data-stu-id="cef4f-104">For example, suppose the `employee` table has an `emp_id` column and a `mgr_id` column.</span></span> <span data-ttu-id="cef4f-105">Como cada director también es un empleado, para relacionar estas dos columnas debe dibujar una línea de relación desde la tabla hasta la propia tabla.</span><span class="sxs-lookup"><span data-stu-id="cef4f-105">Because each manager is also an employee, you relate these two columns by drawing a relationship line from the table to itself.</span></span> <span data-ttu-id="cef4f-106">Esta relación garantiza que cada Id. de director que se agregue a la tabla coincida con un Id. de empleado existente.</span><span class="sxs-lookup"><span data-stu-id="cef4f-106">This relationship ensures each manager ID that is added to the table matches an existing employee ID.</span></span>  
  
 <span data-ttu-id="cef4f-107">Antes de crear una relación debe definir una restricción PRIMARY KEY o UNIQUE para la tabla.</span><span class="sxs-lookup"><span data-stu-id="cef4f-107">Before you create a relationship, you must first define a primary key or unique constraint for your table.</span></span> <span data-ttu-id="cef4f-108">Después debe relacionar la columna de clave principal con una columna coincidente.</span><span class="sxs-lookup"><span data-stu-id="cef4f-108">You then relate the primary key column to a matching column.</span></span> <span data-ttu-id="cef4f-109">Cuando haya creado la relación, la columna coincidente se convertirá en una clave externa de la tabla.</span><span class="sxs-lookup"><span data-stu-id="cef4f-109">Once you create the relationship, the matching column becomes a foreign key of the table.</span></span>  
  
### <a name="to-draw-a-reflexive-relationship"></a><span data-ttu-id="cef4f-110">Para dibujar una relación reflexiva</span><span class="sxs-lookup"><span data-stu-id="cef4f-110">To draw a reflexive relationship</span></span>  
  
1.  <span data-ttu-id="cef4f-111">En el diagrama de base de datos, haga clic en el selector de fila de la columna de base de datos que desea relacionar con otra columna y arrastre el puntero fuera de la tabla hasta que aparezca una línea.</span><span class="sxs-lookup"><span data-stu-id="cef4f-111">In your database diagram, click the row selector for the database column that you want to relate to another column and drag the pointer outside the table until a line appears.</span></span>  
  
2.  <span data-ttu-id="cef4f-112">Arrastre la línea hasta la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cef4f-112">Drag the line back to the selected table.</span></span>  
  
3.  <span data-ttu-id="cef4f-113">Suelte el botón del mouse (ratón).</span><span class="sxs-lookup"><span data-stu-id="cef4f-113">Release the mouse button.</span></span> <span data-ttu-id="cef4f-114">Aparecerá el cuadro de diálogo **Tablas y columnas** .</span><span class="sxs-lookup"><span data-stu-id="cef4f-114">The **Tables and Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="cef4f-115">Seleccione la columna de clave externa y la tabla y columna de clave principal con las desea establecer una relación.</span><span class="sxs-lookup"><span data-stu-id="cef4f-115">Select the foreign key column and the primary key table and column with which you want form a relationship.</span></span>  
  
5.  <span data-ttu-id="cef4f-116">Elija **Aceptar** dos veces para crear la relación.</span><span class="sxs-lookup"><span data-stu-id="cef4f-116">Choose **OK** twice to create the relationship.</span></span>  
  
 <span data-ttu-id="cef4f-117">Cuando ejecute consultas en una tabla, puede utilizar una relación reflexiva para crear una autocombinación.</span><span class="sxs-lookup"><span data-stu-id="cef4f-117">When you run queries against a table, you can use a reflexive relationship to create a self-join.</span></span> <span data-ttu-id="cef4f-118">Para más información sobre cómo consultar las tablas con combinaciones, consulte [Realizar consultas con combinaciones &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cef4f-118">For information about querying tables with joins, see [Query with Joins &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef4f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cef4f-119">See Also</span></span>  
 [<span data-ttu-id="cef4f-120">Realizar consultas con combinaciones &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="cef4f-120">Query with Joins &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
