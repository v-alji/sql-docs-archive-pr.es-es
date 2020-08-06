---
title: 'Lección 10: crear jerarquías | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e2561d3-4890-4495-a9cd-84eb88508938
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d0982a05c37c28167e44e3f9f082ea5113b59bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746045"
---
# <a name="lesson-10-create-hierarchies"></a><span data-ttu-id="34c78-102">Lección 10: Crear jerarquías</span><span class="sxs-lookup"><span data-stu-id="34c78-102">Lesson 10: Create Hierarchies</span></span>
  <span data-ttu-id="34c78-103">En esta lección, creará jerarquías.</span><span class="sxs-lookup"><span data-stu-id="34c78-103">In this lesson, you will create hierarchies.</span></span> <span data-ttu-id="34c78-104">Las jerarquías son grupos de columnas dispuestas en niveles; por ejemplo, una jerarquía Geografía puede tener subniveles para País, Provincia y Ciudad.</span><span class="sxs-lookup"><span data-stu-id="34c78-104">Hierarchies are groups of columns arranged in levels; for example, a Geography hierarchy might have sub-levels for Country, State, County, and City.</span></span> <span data-ttu-id="34c78-105">Las jerarquías pueden aparecer separadas de otras columnas en una lista de campos de aplicación cliente de generación de informes, lo que facilita que los usuarios puedan navegar por ellas e incluirlas en un informe.</span><span class="sxs-lookup"><span data-stu-id="34c78-105">Hierarchies can appear separate from other columns in a reporting client application field list, making them easier for client users to navigate and include in a report.</span></span> <span data-ttu-id="34c78-106">Para obtener más información, vea [Jerarquías &#40;SSAS tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="34c78-106">To learn more, see [Hierarchies &#40;SSAS Tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="34c78-107">Para crear jerarquías, usará el diseñador de modelos en *Vista de diagrama*.</span><span class="sxs-lookup"><span data-stu-id="34c78-107">To create hierarchies, you will use the model designer in *Diagram View*.</span></span> <span data-ttu-id="34c78-108">La creación y administración de jerarquías no se admite en la vista de datos del diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="34c78-108">Creating and managing hierarchies is not supported in the model designer in Data View.</span></span>  
  
 <span data-ttu-id="34c78-109">Tiempo estimado para completar esta lección: **20 minutos**</span><span class="sxs-lookup"><span data-stu-id="34c78-109">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34c78-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="34c78-110">Prerequisites</span></span>  
 <span data-ttu-id="34c78-111">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="34c78-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="34c78-112">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 9: Crear perspectivas](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="34c78-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
## <a name="create-hierarchies"></a><span data-ttu-id="34c78-113">Crear jerarquías</span><span class="sxs-lookup"><span data-stu-id="34c78-113">Create Hierarchies</span></span>  
  
#### <a name="to-create-a-category-hierarchy-in-the-product-table"></a><span data-ttu-id="34c78-114">Para crear una jerarquía Categoría en la tabla Product</span><span class="sxs-lookup"><span data-stu-id="34c78-114">To create a Category hierarchy in the Product table</span></span>  
  
1.  <span data-ttu-id="34c78-115">En el diseñador de modelos, haga clic en el `Model` menú, elija **vista de modelo**y, a continuación, haga clic en **vista de diagrama**.</span><span class="sxs-lookup"><span data-stu-id="34c78-115">In the model designer, click on the `Model` menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="34c78-116">Utilice los controles de Minimapa situados en la parte superior derecha del diseñador de modelos para cambiar el modo en que se muestran los objetos en la vista de diagrama.</span><span class="sxs-lookup"><span data-stu-id="34c78-116">Use the Minimap controls at the top-right of the model designer to change how you can view objects in Diagram View.</span></span> <span data-ttu-id="34c78-117">Si cambia la posición de los objetos en la vista de diagrama, esa vista se conservará cuando guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="34c78-117">If you reposition objects in Diagram View, that view will be retained when you save the project.</span></span>  
  
2.  <span data-ttu-id="34c78-118">En el diseñador de modelos, haga clic con el botón secundario en la `Product` tabla y, a continuación, haga clic en **crear jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="34c78-118">In the model designer, right-click the `Product` table, and then click **Create Hierarchy**.</span></span> <span data-ttu-id="34c78-119">Aparece una nueva jerarquía en la parte inferior de la ventana de tabla.</span><span class="sxs-lookup"><span data-stu-id="34c78-119">A new hierarchy appears at the bottom of the table window.</span></span>  
  
3.  <span data-ttu-id="34c78-120">En el nombre de la jerarquía, cambie el nombre de la jerarquía; para ello, escriba y, `Category` a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="34c78-120">In the hierarchy name, rename the hierarchy by typing `Category`, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="34c78-121">En la `Product` tabla, haga clic en la columna **Product Category Name** , arrástrela a la `Category` jerarquía y suelte el `Category` nombre.</span><span class="sxs-lookup"><span data-stu-id="34c78-121">In the `Product` table, click the **Product Category Name** column, then drag it to the `Category` hierarchy, and then release on top of the `Category` name.</span></span>  
  
5.  <span data-ttu-id="34c78-122">En la `Category` jerarquía, haga clic con el botón secundario en la columna **Product Category Name** , haga clic en cambiar **nombre**y, a continuación, escriba `Category` .</span><span class="sxs-lookup"><span data-stu-id="34c78-122">In the `Category` hierarchy, right-click the **Product Category Name** column, then click **Rename**, and then type `Category`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34c78-123">Al cambiar el nombre de una columna de la jerarquía no se cambia el nombre de esa columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="34c78-123">Renaming a column in a hierarchy does not rename that column in the table.</span></span> <span data-ttu-id="34c78-124">Una columna de una jerarquía es simplemente una representación de la columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="34c78-124">A column in a hierarchy is just a representation of the column in the table.</span></span>  
  
6.  <span data-ttu-id="34c78-125">En la `Product` tabla, haga clic con el botón secundario en la columna **Product subcategory Name** , en el menú contextual, seleccione **Agregar a jerarquía**y, a continuación, haga clic en `Category` .</span><span class="sxs-lookup"><span data-stu-id="34c78-125">In the `Product` table, right-click the **Product Subcategory Name** column, then in the context menu, point to **Add to Hierarchy**, and then click `Category`.</span></span>  
  
7.  <span data-ttu-id="34c78-126">Cambie el nombre de la **subcategoría de producto** a `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="34c78-126">Rename **Product Subcategory Name** to `Subcategory`.</span></span>  
  
8.  <span data-ttu-id="34c78-127">Con hacer clic y arrastrar, o mediante el comando **Agregar a la jerarquía** en el menú contextual, agregue las columnas **nombre del modelo** y **nombre del producto** (en orden) y colóquelas debajo de la columna Nombre de **subcategoría del producto** .</span><span class="sxs-lookup"><span data-stu-id="34c78-127">By using click and drag, or by using the **Add to Hierarchy** command in the context menu, add the **Model Name** and **Product Name** columns (in order) and place them beneath the **Product Subcategory Name** column.</span></span> <span data-ttu-id="34c78-128">Cambie el nombre de estas columnas `Model` y `Product` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="34c78-128">Rename these columns `Model` and `Product`, respectively.</span></span>  
  
#### <a name="to-create-hierarchies-in-the-date-table"></a><span data-ttu-id="34c78-129">Para crear jerarquías en la tabla Date</span><span class="sxs-lookup"><span data-stu-id="34c78-129">To create hierarchies in the Date table</span></span>  
  
1.  <span data-ttu-id="34c78-130">En el diseñador de modelos, haga clic con el botón derecho en la tabla **Fecha** y, después, haga clic en **Crear jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="34c78-130">In the model designer, right-click the **Date** table, and then click **Create Hierarchy**.</span></span>  
  
2.  <span data-ttu-id="34c78-131">Cambie el nombre de la jerarquía a **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="34c78-131">Rename the hierarchy to **Calendar**.</span></span>  
  
3.  <span data-ttu-id="34c78-132">Agregue las columnas siguientes, en orden, y después cámbieles el nombre:</span><span class="sxs-lookup"><span data-stu-id="34c78-132">Add the following columns, in-order, and then rename them:</span></span>  
  
    |<span data-ttu-id="34c78-133">Columna</span><span class="sxs-lookup"><span data-stu-id="34c78-133">Column</span></span>|<span data-ttu-id="34c78-134">Cambiar el nombre a:</span><span class="sxs-lookup"><span data-stu-id="34c78-134">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="34c78-135">Año del calendario</span><span class="sxs-lookup"><span data-stu-id="34c78-135">Calendar Year</span></span>|<span data-ttu-id="34c78-136">Year</span><span class="sxs-lookup"><span data-stu-id="34c78-136">Year</span></span>|  
    |<span data-ttu-id="34c78-137">Semestre del calendario</span><span class="sxs-lookup"><span data-stu-id="34c78-137">Calendar Semester</span></span>|<span data-ttu-id="34c78-138">Semestre</span><span class="sxs-lookup"><span data-stu-id="34c78-138">Semester</span></span>|  
    |<span data-ttu-id="34c78-139">Trimestre del calendario</span><span class="sxs-lookup"><span data-stu-id="34c78-139">Calendar Quarter</span></span>|<span data-ttu-id="34c78-140">Quarter (Trimestre)</span><span class="sxs-lookup"><span data-stu-id="34c78-140">Quarter</span></span>|  
    |<span data-ttu-id="34c78-141">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="34c78-141">Month Calendar</span></span>|<span data-ttu-id="34c78-142">Month</span><span class="sxs-lookup"><span data-stu-id="34c78-142">Month</span></span>|  
    |<span data-ttu-id="34c78-143">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="34c78-143">Day Of Month</span></span>|<span data-ttu-id="34c78-144">Día</span><span class="sxs-lookup"><span data-stu-id="34c78-144">Day</span></span>|  
  
4.  <span data-ttu-id="34c78-145">En la tabla **Fecha** , repita los pasos anteriores y cree una jerarquía **Fiscal** que incluya las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="34c78-145">In the **Date** table, repeat the above steps, creating a **Fiscal** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="34c78-146">Columna</span><span class="sxs-lookup"><span data-stu-id="34c78-146">Column</span></span>|<span data-ttu-id="34c78-147">Cambiar el nombre a:</span><span class="sxs-lookup"><span data-stu-id="34c78-147">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="34c78-148">Año fiscal</span><span class="sxs-lookup"><span data-stu-id="34c78-148">Fiscal Year</span></span>|<span data-ttu-id="34c78-149">Year</span><span class="sxs-lookup"><span data-stu-id="34c78-149">Year</span></span>|  
    |<span data-ttu-id="34c78-150">Semestre fiscal</span><span class="sxs-lookup"><span data-stu-id="34c78-150">Fiscal Semester</span></span>|<span data-ttu-id="34c78-151">Semestre</span><span class="sxs-lookup"><span data-stu-id="34c78-151">Semester</span></span>|  
    |<span data-ttu-id="34c78-152">Trimestre fiscal</span><span class="sxs-lookup"><span data-stu-id="34c78-152">Fiscal Quarter</span></span>|<span data-ttu-id="34c78-153">Quarter (Trimestre)</span><span class="sxs-lookup"><span data-stu-id="34c78-153">Quarter</span></span>|  
    |<span data-ttu-id="34c78-154">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="34c78-154">Month Calendar</span></span>|<span data-ttu-id="34c78-155">Month</span><span class="sxs-lookup"><span data-stu-id="34c78-155">Month</span></span>|  
    |<span data-ttu-id="34c78-156">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="34c78-156">Day Of Month</span></span>|<span data-ttu-id="34c78-157">Día</span><span class="sxs-lookup"><span data-stu-id="34c78-157">Day</span></span>|  
  
5.  <span data-ttu-id="34c78-158">Finalmente, en la tabla **Fecha** , repita los pasos anteriores y cree una jerarquía **Calendario de producción** que incluya las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="34c78-158">Finally, in the **Date** table, repeat the above steps, creating a **Production Calendar** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="34c78-159">Columna</span><span class="sxs-lookup"><span data-stu-id="34c78-159">Column</span></span>|<span data-ttu-id="34c78-160">Cambiar el nombre a:</span><span class="sxs-lookup"><span data-stu-id="34c78-160">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="34c78-161">Año del calendario</span><span class="sxs-lookup"><span data-stu-id="34c78-161">Calendar Year</span></span>|<span data-ttu-id="34c78-162">Year</span><span class="sxs-lookup"><span data-stu-id="34c78-162">Year</span></span>|  
    |<span data-ttu-id="34c78-163">Week Number Of Year</span><span class="sxs-lookup"><span data-stu-id="34c78-163">Week Number Of Year</span></span>|<span data-ttu-id="34c78-164">Semana</span><span class="sxs-lookup"><span data-stu-id="34c78-164">Week</span></span>|  
    |<span data-ttu-id="34c78-165">Day Of Week</span><span class="sxs-lookup"><span data-stu-id="34c78-165">Day Of Week</span></span>|<span data-ttu-id="34c78-166">Día</span><span class="sxs-lookup"><span data-stu-id="34c78-166">Day</span></span>|  
  
## <a name="next-steps"></a><span data-ttu-id="34c78-167">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="34c78-167">Next Steps</span></span>  
 <span data-ttu-id="34c78-168">Para continuar este tutorial, vaya a la lección siguiente: [Lección 11: Crear particiones](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="34c78-168">To continue this tutorial, go to the next lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
  
