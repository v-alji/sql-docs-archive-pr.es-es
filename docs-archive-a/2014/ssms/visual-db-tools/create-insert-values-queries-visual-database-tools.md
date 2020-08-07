---
title: Crear consultas de inserción de valores (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting values
- queries [SQL Server], types
- adding values
- row additions [SQL Server], Insert Values query
- inserting rows
- Insert Values query
- adding rows
- table values [SQL Server]
ms.assetid: 2d4b2f6d-cc09-434b-8a0e-ccce40628064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fc71b0148ee8a7e92c517fe75b56c329b3c88f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745599"
---
# <a name="create-insert-values-queries-visual-database-tools"></a><span data-ttu-id="6b82a-102">Crear consultas de inserción de valores (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6b82a-102">Create Insert Values Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="6b82a-103">Puede crear una nueva fila en la tabla actual mediante una consulta de inserción de valores.</span><span class="sxs-lookup"><span data-stu-id="6b82a-103">You can create a new row in the current table using an Insert Values query.</span></span> <span data-ttu-id="6b82a-104">Cuando se crea una consulta de inserción de valores, se especifica:</span><span class="sxs-lookup"><span data-stu-id="6b82a-104">When you create an Insert Values query, you specify:</span></span>  
  
-   <span data-ttu-id="6b82a-105">La tabla de base de datos a la que se va a agregar la fila.</span><span class="sxs-lookup"><span data-stu-id="6b82a-105">The database table to add the row to.</span></span>  
  
-   <span data-ttu-id="6b82a-106">Las columnas cuyo contenido desea agregar.</span><span class="sxs-lookup"><span data-stu-id="6b82a-106">The columns whose contents you want to add.</span></span>  
  
-   <span data-ttu-id="6b82a-107">El valor o la expresión que se va a insertar en las distintas columnas.</span><span class="sxs-lookup"><span data-stu-id="6b82a-107">The value or expression to insert into the individual columns.</span></span>  
  
 <span data-ttu-id="6b82a-108">Por ejemplo, en la siguiente consulta se agrega una fila a la tabla `titles` , que especifica valores para el título, el tipo, la editorial y el precio:</span><span class="sxs-lookup"><span data-stu-id="6b82a-108">For example, the following query adds a row to the `titles` table, specifying values for the title, type, publisher, and price:</span></span>  
  
```  
INSERT INTO titles  
         (title_id, title, type, pub_id, price)  
VALUES   ('BU9876', 'Creating Web Pages', 'business', '1389', '29.99')  
```  
  
 <span data-ttu-id="6b82a-109">Cuando se crea una consulta de inserción de valores, el panel Criterios cambia para reflejar las únicas opciones disponibles para insertar una nueva fila: el nombre de columna y el valor que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="6b82a-109">When you create an Insert Values query, the Criteria pane changes to reflect the only options available for inserting a new row: the column name and the value to insert.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6b82a-110">No se puede deshacer la operación de ejecutar una consulta de inserción de valores.</span><span class="sxs-lookup"><span data-stu-id="6b82a-110">You cannot undo the action of executing an Insert Values query.</span></span> <span data-ttu-id="6b82a-111">Como medida de precaución, haga una copia de seguridad de los datos antes de ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="6b82a-111">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-values-query"></a><span data-ttu-id="6b82a-112">Para crear una Consulta de inserción de valores</span><span class="sxs-lookup"><span data-stu-id="6b82a-112">To create an Insert Values query</span></span>  
  
1.  <span data-ttu-id="6b82a-113">Agregue en el panel Diagrama la tabla que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="6b82a-113">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="6b82a-114">En el menú **Diseñador de consultas** , seleccione **Cambiar tipo**y, a continuación, haga clic en **Insertar valores**.</span><span class="sxs-lookup"><span data-stu-id="6b82a-114">From the **Query Designer** menu point to **Change Type**, and then click **Insert Values**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b82a-115">Si aparece más de una tabla en el panel Diagrama al iniciar la consulta de inserción de valores, el Diseñador de consultas y vistas mostrará el [cuadro de diálogo Elegir tabla de destino para Insertar valores](visual-database-tools.md) para solicitarle el nombre de la tabla que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="6b82a-115">If more than one table is displayed in the Diagram pane when you start the Insert Values query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="6b82a-116">En el panel Diagrama, active la casilla de cada columna en la que desea proporcionar nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="6b82a-116">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="6b82a-117">Estas columnas se mostrarán en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="6b82a-117">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="6b82a-118">Las columnas se actualizan solo si se agregan a la consulta.</span><span class="sxs-lookup"><span data-stu-id="6b82a-118">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="6b82a-119">En la columna **Valor nuevo** del panel Criterios, escriba el nuevo valor para la columna.</span><span class="sxs-lookup"><span data-stu-id="6b82a-119">In the **New Value** column of the Criteria pane, enter the new value for the column.</span></span> <span data-ttu-id="6b82a-120">Puede especificar valores literales, nombres de columna o expresiones.</span><span class="sxs-lookup"><span data-stu-id="6b82a-120">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="6b82a-121">El valor debe coincidir (o ser compatible) con el tipo de datos de la columna que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="6b82a-121">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="6b82a-122">El Diseñador de consultas y vistas no puede comprobar si el valor se ajusta al tamaño de la columna que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="6b82a-122">The Query and View Designer cannot check that a value fits within the length of the column you are inserting.</span></span> <span data-ttu-id="6b82a-123">Si especifica un valor demasiado largo, se truncará sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="6b82a-123">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="6b82a-124">Por ejemplo, si una columna `name` tiene una longitud de 20 caracteres y especifica un valor de inserción de 25 caracteres, se cortarán los cinco últimos caracteres.</span><span class="sxs-lookup"><span data-stu-id="6b82a-124">For example, if a `name` column is 20 characters long but you specify an insert value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
 <span data-ttu-id="6b82a-125">Cuando se ejecuta una consulta de inserción de valores, los resultados no se muestran en el [panel Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b82a-125">When you execute an Insert Values query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="6b82a-126">En su lugar, aparece un mensaje que indica el número de filas que se han modificado.</span><span class="sxs-lookup"><span data-stu-id="6b82a-126">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b82a-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b82a-127">See Also</span></span>  
 <span data-ttu-id="6b82a-128">[Tipos de consultas admitidos &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6b82a-128">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6b82a-129">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6b82a-129">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6b82a-130">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6b82a-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
