---
title: Crear consultas de actualización (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], updating
- queries [SQL Server], types
- Update query
- updating tables
ms.assetid: 178b7b75-8078-4e61-b2a8-4719b9d8033d
author: stevestein
ms.author: sstein
ms.openlocfilehash: bbea575d544875dba73de923474cc11bbcb46a9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673984"
---
# <a name="create-update-queries-visual-database-tools"></a><span data-ttu-id="b0c5b-102">Crear consultas de actualización (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b0c5b-102">Create Update Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="b0c5b-103">Puede cambiar el contenido de varias filas en una sola operación mediante una consulta Update.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-103">You can change the contents of multiple rows in one operation by using an Update query.</span></span> <span data-ttu-id="b0c5b-104">Por ejemplo, en una tabla `titles` puede utilizar una consulta Update para sumar un 10% al precio de todos los libros de una editorial determinada.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-104">For example, in a `titles` table you can use an Update query to add 10% to the price of all books for a particular publisher.</span></span>  
  
 <span data-ttu-id="b0c5b-105">Cuando se crea una consulta Update, se especifica:</span><span class="sxs-lookup"><span data-stu-id="b0c5b-105">When you create an Update query, you specify:</span></span>  
  
-   <span data-ttu-id="b0c5b-106">La tabla que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-106">The table to update.</span></span>  
  
-   <span data-ttu-id="b0c5b-107">Las columnas cuyo contenido desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-107">The columns whose contents you want to update.</span></span>  
  
-   <span data-ttu-id="b0c5b-108">El valor o la expresión que se va a utilizar para actualizar cada una de las columnas.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-108">The value or expression to use to update the individual columns.</span></span>  
  
-   <span data-ttu-id="b0c5b-109">Las condiciones de búsqueda que definen las filas que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-109">Search conditions to define the rows you want to update.</span></span>  
  
 <span data-ttu-id="b0c5b-110">Por ejemplo, la siguiente consulta actualiza la tabla `titles` sumando un 10% al precio de todos los títulos de una editorial:</span><span class="sxs-lookup"><span data-stu-id="b0c5b-110">For example, the following query updates the `titles` table by adding 10% to the price of all titles for one publisher:</span></span>  
  
```  
UPDATE titles  
SET price = price * 1.1  
WHERE (pub_id = '0766')  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="b0c5b-111">No puede deshacer la ejecución de una consulta Update.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-111">You cannot undo the action of executing an Update query.</span></span> <span data-ttu-id="b0c5b-112">Como medida de precaución, haga una copia de seguridad de los datos antes de ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-112">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-update-query"></a><span data-ttu-id="b0c5b-113">Para crear una consulta Update</span><span class="sxs-lookup"><span data-stu-id="b0c5b-113">To create an Update query</span></span>  
  
1.  <span data-ttu-id="b0c5b-114">Agregue en el panel Diagrama la tabla que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-114">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="b0c5b-115">En el menú **Diseñador de consultas** , seleccione **Cambiar tipo**y, a continuación, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-115">From the **Query Designer** menu point to **Change Type**, and then click **Update**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0c5b-116">Si se muestra más de una tabla en el panel Diagrama al iniciar la consulta Update, el Diseñador de consultas y vistas muestra el [cuadro de diálogo Elegir tabla de destino para Insertar valores](visual-database-tools.md) para solicitarle el nombre de la tabla que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-116">If more than one table is displayed in the Diagram pane when you start the Update query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="b0c5b-117">En el panel Diagrama, active la casilla de cada columna en la que desea proporcionar nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-117">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="b0c5b-118">Estas columnas se mostrarán en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-118">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="b0c5b-119">Las columnas se actualizan solo si se agregan a la consulta.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-119">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="b0c5b-120">En la columna **Valor nuevo** del panel Criterios, escriba el valor de actualización para la columna.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-120">In the **New Value** column of the Criteria pane, enter the update value for the column.</span></span> <span data-ttu-id="b0c5b-121">Puede especificar valores literales, nombres de columna o expresiones.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-121">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="b0c5b-122">El valor debe coincidir (o ser compatible) con el tipo de datos de la columna que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-122">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="b0c5b-123">El Diseñador de consultas y vistas no comprueba si el valor se ajusta al tamaño de la columna que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-123">The Query and View Designer cannot check that a value fits within the length of the column you are updating.</span></span> <span data-ttu-id="b0c5b-124">Si especifica un valor demasiado largo, se truncará sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-124">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="b0c5b-125">Por ejemplo, si una columna `name` tiene una longitud de 20 caracteres y especifica un valor nuevo de 25 caracteres, se cortarán los cinco últimos caracteres.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-125">For example, if a `name` column is 20 characters long but you specify an update value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
5.  <span data-ttu-id="b0c5b-126">Defina las filas que desea actualizar especificando condiciones de búsqueda en la columna **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-126">Define the rows to update by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="b0c5b-127">Para detalles, consulte [Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0c5b-127">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="b0c5b-128">Si no especifica ninguna condición de búsqueda, se actualizarán todas las filas de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-128">If you do not specify a search condition, all rows in the specified table will be updated.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0c5b-129">Cuando se agrega una columna al panel Criterios para utilizarla en una condición de búsqueda, el Diseñador de consultas y vistas la agrega también a la lista de columnas que se van a actualizar.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-129">When you add a column to the Criteria pane for use in a search condition, the Query and View Designer also adds it to the list of columns to be updated.</span></span> <span data-ttu-id="b0c5b-130">Si desea utilizar una columna para una condición de búsqueda, pero no quiere actualizarla, desactive la casilla situada junto al nombre de la columna en el rectángulo que representa la tabla o el objeto con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-130">If you want to use a column for a search condition but not update it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
 <span data-ttu-id="b0c5b-131">Cuando se ejecuta una consulta Update, los resultados no se muestran en el [panel Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0c5b-131">When you execute an Update query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="b0c5b-132">En su lugar, aparece un mensaje que indica el número de filas que se han modificado.</span><span class="sxs-lookup"><span data-stu-id="b0c5b-132">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c5b-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0c5b-133">See Also</span></span>  
 <span data-ttu-id="b0c5b-134">[Tipos de consultas admitidos &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b0c5b-134">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b0c5b-135">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b0c5b-135">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b0c5b-136">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b0c5b-136">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
