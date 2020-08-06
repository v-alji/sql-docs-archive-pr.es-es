---
title: 'Lección 6: crear columnas calculadas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d126766a-5699-4e9f-8213-8c7eea0fc14e
author: minewiskan
ms.author: owend
ms.openlocfilehash: dcebf61955e230c9e61c955683b897026553cb52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671789"
---
# <a name="lesson-6-create-calculated-columns"></a><span data-ttu-id="7cf4f-102">Lección 6: Crear columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="7cf4f-102">Lesson 6: Create Calculated Columns</span></span>
  <span data-ttu-id="7cf4f-103">En esta lección creará nuevos datos en el modelo agregando columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-103">In this lesson, you will create new data in your model by adding calculated columns.</span></span> <span data-ttu-id="7cf4f-104">Una columna calculada está basada en datos que ya existen en el modelo.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-104">A calculated column is based on data that already exists in the model.</span></span> <span data-ttu-id="7cf4f-105">Para obtener más información, consulte [Columnas calculadas &#40;SSAS tabular&#41;](tabular-models/ssas-calculated-columns.md).</span><span class="sxs-lookup"><span data-stu-id="7cf4f-105">To learn more, see [Calculated Columns &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns.md).</span></span>  
  
 <span data-ttu-id="7cf4f-106">Creará cinco columnas calculadas en tres tablas diferentes.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-106">You will create five new calculated columns in three different tables.</span></span> <span data-ttu-id="7cf4f-107">Los pasos son ligeramente diferentes para cada tarea.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-107">The steps are slightly different for each task.</span></span> <span data-ttu-id="7cf4f-108">Esto es así para mostrarle que hay varias formas de crear nuevas columnas, cambiarles el nombre y colocarlas en distintos lugares de una tabla.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-108">This is to show you there are several ways to create new columns, rename them, and place them in various locations in a table.</span></span>  
  
 <span data-ttu-id="7cf4f-109">Tiempo estimado para completar esta lección: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="7cf4f-109">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7cf4f-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7cf4f-110">Prerequisites</span></span>  
 <span data-ttu-id="7cf4f-111">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="7cf4f-112">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 5: Crear relaciones](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="7cf4f-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
## <a name="create-calculated-columns"></a><span data-ttu-id="7cf4f-113">Crear columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="7cf4f-113">Create Calculated Columns</span></span>  
  
#### <a name="create-a-month-calendar-calculated-column-in-the-date-table"></a><span data-ttu-id="7cf4f-114">Crear una columna calculada Calendario del mes en la tabla Date</span><span class="sxs-lookup"><span data-stu-id="7cf4f-114">Create a Month Calendar calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="7cf4f-115">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** , elija **Vista de modelo**y, después, haga clic en **Vista de datos**.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-115">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Model View**, and then click **Data View**.</span></span>  
  
     <span data-ttu-id="7cf4f-116">Las columnas calculadas solo se pueden crear mediante el diseñador de modelos en la Vista de datos.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-116">Calculated columns can only be created by using the model designer in Data View.</span></span>  
  
2.  <span data-ttu-id="7cf4f-117">En el diseñador de modelos, haga clic en la tabla **Date** (pestaña).</span><span class="sxs-lookup"><span data-stu-id="7cf4f-117">In the model designer, click the **Date** table (tab).</span></span>  
  
3.  <span data-ttu-id="7cf4f-118">Haga clic con el botón secundario en la columna **Calendar Quarter** y, a continuación, haga clic en **Insertar columna**.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-118">Right-click the **Calendar Quarter** column, and then click **Insert Column**.</span></span>  
  
     <span data-ttu-id="7cf4f-119">Se inserta una nueva columna denominada **CalculatedColumn1** a la izquierda de la columna **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-119">A new column named **CalculatedColumn1** is inserted to the left of the **Calendar Quarter** column.</span></span>  
  
4.  <span data-ttu-id="7cf4f-120">En la barra de fórmulas situada encima de la tabla, escriba la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-120">In the formula bar above the table, type the following formula.</span></span> <span data-ttu-id="7cf4f-121">Autocompletar le ayuda a escribir los nombres completos de columnas y tablas y enumera las funciones que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-121">AutoComplete helps you type the fully qualified names of columns and tables, and lists the functions that are available.</span></span>  
  
     `=RIGHT(" " & FORMAT([Month],"#0"), 2) & " - " & [Month Name]`  
  
     <span data-ttu-id="7cf4f-122">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-122">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="7cf4f-123">Después, se rellenan los valores de todas las filas de la columna calculada.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-123">Values are then populated for all the rows in the calculated column.</span></span> <span data-ttu-id="7cf4f-124">Si se desplaza hacia abajo por la tabla, verá que las filas pueden tener valores diferentes para esta columna, en función de los datos incluidos en cada fila.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-124">If you scroll down through the table, you will see that rows can have different values for this column, based on the data that is in each row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7cf4f-125">Si aparece un error, compruebe que los nombres de columna de la fórmula coinciden con los nombres de columna que cambió en [Lección 3: Cambiar el nombre de las columnas](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="7cf4f-125">If you receive an error, verify the column names in the formula match the column names you changed in [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
5.  <span data-ttu-id="7cf4f-126">Cambie el nombre de esta columna a `Month Calendar` .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-126">Rename this column to `Month Calendar`.</span></span>  
  
 <span data-ttu-id="7cf4f-127">La columna calculada Calendario del mes proporciona un nombre ordenable del mes.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-127">The Month Calendar calculated column provides a sortable name for Month.</span></span>  
  
#### <a name="create-a-day-of-week-calculated-column-in-the-date-table"></a><span data-ttu-id="7cf4f-128">Crear una columna calculada Día de la semana en la tabla Date</span><span class="sxs-lookup"><span data-stu-id="7cf4f-128">Create a Day of Week calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="7cf4f-129">Con la tabla **Date** activa, haga clic en el menú **Columna** y luego en **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-129">With the **Date** table still active, click on the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="7cf4f-130">Se agrega una columna nueva a la derecha de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-130">A new column is added to the far right of the table</span></span>  
  
2.  <span data-ttu-id="7cf4f-131">En la barra de fórmulas, escriba la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="7cf4f-131">In the formula bar, type the following formula:</span></span>  
  
     `=RIGHT(" " & FORMAT([Day Number Of Week],"#0"), 2) & " - " & [Day Name]`  
  
     <span data-ttu-id="7cf4f-132">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="7cf4f-133">Cambie el nombre de la columna a `Day of Week` .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-133">Rename the column to `Day of Week`.</span></span>  
  
4.  <span data-ttu-id="7cf4f-134">Haga clic en el encabezado de columna y, después, arrastre la columna entre la columna **Day Name** y la columna **Day of Month** .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-134">Click on the column heading, and then drag the column between the **Day Name** column and the **Day of Month** column.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="7cf4f-135">El movimiento de columnas en la tabla simplifica la navegación.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-135">Moving columns in your table makes it easier to navigate.</span></span>  
  
 <span data-ttu-id="7cf4f-136">La columna calculada Día de la semana proporciona un nombre ordenable del día de la semana.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-136">The Day of Week calculated column provides a sortable name for the day of week.</span></span>  
  
#### <a name="create-a-product-subcategory-name-calculated-column-in-the-product-table"></a><span data-ttu-id="7cf4f-137">Crear una columna calculada Nombre de subcategoría del producto en la tabla Product</span><span class="sxs-lookup"><span data-stu-id="7cf4f-137">Create a Product Subcategory Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="7cf4f-138">En el diseñador de modelos, seleccione la tabla **Product** .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-138">In the model designer, select the **Product** table.</span></span>  
  
2.  <span data-ttu-id="7cf4f-139">Desplácese hasta el extremo derecho de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-139">Scroll to the far right of the table.</span></span> <span data-ttu-id="7cf4f-140">Observe que la columna de la derecha se denomina **Agregar columna** (en cursiva). Haga clic en el encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-140">Notice the right-most column is named **Add Column** (italicized), click the column heading.</span></span>  
  
3.  <span data-ttu-id="7cf4f-141">En la barra de fórmulas, escriba la fórmula siguiente.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-141">In the formula bar, type the following formula.</span></span>  
  
     `=RELATED('Product Subcategory'[Product Subcategory Name])`  
  
     <span data-ttu-id="7cf4f-142">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-142">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="7cf4f-143">Cambie el nombre de la columna a `Product Subcategory Name` .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-143">Rename the column to `Product Subcategory Name`.</span></span>  
  
 <span data-ttu-id="7cf4f-144">La columna calculada Nombre de subcategoría del producto se utiliza para crear una jerarquía en la tabla Product que incluya los datos de la columna con igual nombre en la tabla Product Subcategory.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-144">The Product Subcategory Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Subcategory Name column in the Product Subcategory table.</span></span> <span data-ttu-id="7cf4f-145">Las jerarquías no pueden abarcar más de una tabla.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-145">Hierarchies cannot span more than one table.</span></span> <span data-ttu-id="7cf4f-146">Más adelante, en la lección 7, creará jerarquías.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-146">You will create hierarchies later in Lesson 7.</span></span>  
  
#### <a name="create-a-product-category-name-calculated-column-in-the-product-table"></a><span data-ttu-id="7cf4f-147">Crear una columna calculada Nombre de categoría del producto en la tabla Product</span><span class="sxs-lookup"><span data-stu-id="7cf4f-147">Create a Product Category Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="7cf4f-148">Con la tabla **Product** activa, haga clic en el menú **Columna** y, después, en **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-148">With the **Product** table still active, click the **Column** menu, and then click **Add Column**.</span></span>  
  
2.  <span data-ttu-id="7cf4f-149">En la barra de fórmulas, escriba la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="7cf4f-149">In the formula bar, type the following formula:</span></span>  
  
     `=RELATED('Product Category'[Product Category Name])`  
  
     <span data-ttu-id="7cf4f-150">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-150">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="7cf4f-151">Cambie el nombre de la columna a `Product Category Name` .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-151">Rename the column to `Product Category Name`.</span></span>  
  
 <span data-ttu-id="7cf4f-152">La columna calculada Nombre de categoría del producto se utiliza para crear una jerarquía en la tabla Product que incluya los datos de la columna con igual nombre en la tabla Product Category.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-152">The Product Category Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Category Name column in the Product Category table.</span></span> <span data-ttu-id="7cf4f-153">Las jerarquías no pueden abarcar más de una tabla.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-153">Hierarchies cannot span more than one table.</span></span>  
  
#### <a name="create-a-margin-calculated-column-in-the-internet-sales-table"></a><span data-ttu-id="7cf4f-154">Crear una columna calculada Margen en la tabla Internet Sales</span><span class="sxs-lookup"><span data-stu-id="7cf4f-154">Create a Margin calculated column in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="7cf4f-155">En el diseñador de modelos, seleccione la tabla **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-155">In the model designer, select the **Internet Sales** table.</span></span>  
  
2.  <span data-ttu-id="7cf4f-156">Agregue una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-156">Add a new column.</span></span>  
  
3.  <span data-ttu-id="7cf4f-157">En la barra de fórmulas, escriba la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="7cf4f-157">In the formula bar, type the following formula:</span></span>  
  
     `=[Sales Amount]-[Total Product Cost]`  
  
     <span data-ttu-id="7cf4f-158">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7cf4f-158">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="7cf4f-159">Cambie el nombre de la columna a `Margin` .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-159">Rename the column to `Margin`.</span></span>  
  
5.  <span data-ttu-id="7cf4f-160">Arrastre la columna entre la columna **Sales Amount** y la columna **Tax Amt** .</span><span class="sxs-lookup"><span data-stu-id="7cf4f-160">Drag the column between the **Sales Amount** column and the **Tax Amt** column.</span></span>  
  
 <span data-ttu-id="7cf4f-161">La columna calculada Margen se utiliza para analizar los márgenes de beneficios de cada fila (producto).</span><span class="sxs-lookup"><span data-stu-id="7cf4f-161">The Margin calculated column is used to analyze profit margins for each (product) row.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7cf4f-162">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="7cf4f-162">Next Step</span></span>  
 <span data-ttu-id="7cf4f-163">Para continuar esta lección, vaya a la lección siguiente: [Lección 7: Crear medidas](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="7cf4f-163">To continue this lesson, go to the next lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
  
