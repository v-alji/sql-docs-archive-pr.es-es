---
title: Crear una estructura de modelos de minería de datos de clústeres de secuencia (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671287"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="bdba5-102">Crear una estructura del modelo de minería de datos de agrupación en clústeres de secuencia (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="bdba5-102">Creating a Sequence Clustering Mining Model Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="bdba5-103">El primer paso para crear un modelo de minería de datos de agrupación en clústeres de secuencia es utilizar el Asistente para minería de datos con el objeto de crear una nueva estructura de minería de datos y un modelo de minería basados en el algoritmo de clústeres de secuencia de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdba5-103">The first step in creating a sequence clustering mining model is to use the Data Mining Wizard to create a new mining structure and a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span>  
  
 <span data-ttu-id="bdba5-104">Utilizará la misma vista del origen de datos que utilizó para el análisis de la cesta de la compra, pero agregará una columna que contenga el identificador `sequence`.</span><span class="sxs-lookup"><span data-stu-id="bdba5-104">You will use the same data source view that you used for the market basket analysis, but you will add a column that contains the `sequence` identifier.</span></span> <span data-ttu-id="bdba5-105">En este escenario, la secuencia significa el orden en el que el cliente agregó los elementos a la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="bdba5-105">In this scenario, the sequence means the order in which the customer added items to the shopping basket.</span></span>  
  
 <span data-ttu-id="bdba5-106">También agregará algunas columnas que se utilizan en uno de los modelos para agrupar los clientes por datos demográficos.</span><span class="sxs-lookup"><span data-stu-id="bdba5-106">You will also add some columns that are used in one of the models to group customers by demographics.</span></span>  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a><span data-ttu-id="bdba5-107">Para crear un modelo y una estructura de agrupación en clústeres de secuencia</span><span class="sxs-lookup"><span data-stu-id="bdba5-107">To create a sequence clustering structure and model</span></span>  
  
1.  <span data-ttu-id="bdba5-108">En Explorador de soluciones en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , haga clic con el botón secundario en **estructuras de minería de datos** y seleccione **nueva estructura de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-108">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="bdba5-109">En la página de inicio del **Asistente para minería de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-109">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="bdba5-110">En la página **seleccionar el método de definición** , compruebe que la opción **de base de datos relacional o del almacenamiento de datos existente** está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-110">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="bdba5-111">En la página **crear la estructura de minería de datos** , compruebe que está seleccionada la opción **crear estructura de minería de datos con un modelo de minería de** datos.</span><span class="sxs-lookup"><span data-stu-id="bdba5-111">On the **Create the Data Mining Structure** page, verify that the option **Create mining structure with a mining model** is selected.</span></span> <span data-ttu-id="bdba5-112">A continuación, haga clic en la lista desplegable de la opción **¿qué técnica de minería de datos desea utilizar?** y seleccione **agrupación en clústeres de secuencia de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-112">Next, click the dropdown list for the option, **Which data mining technique do you want to use?**, and select **Microsoft Sequence Clustering**.</span></span> <span data-ttu-id="bdba5-113">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-113">Click **Next**.</span></span>  
  
     <span data-ttu-id="bdba5-114">Aparece la página **seleccionar vista del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="bdba5-114">The **Select Data Source View** page appears.</span></span> <span data-ttu-id="bdba5-115">En **vistas del origen de datos disponibles**, seleccione `Orders` .</span><span class="sxs-lookup"><span data-stu-id="bdba5-115">Under **Available data source views**, select `Orders`.</span></span>  
  
     <span data-ttu-id="bdba5-116">Orders es la misma vista del origen de datos que utilizó para el escenario de la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="bdba5-116">Orders is the same data source view that you used for the market basket scenario.</span></span> <span data-ttu-id="bdba5-117">Si no ha creado esta vista del origen de datos, vea [Agregar una vista del origen de datos con tablas anidadas &#40;tutorial intermedio de minería de datos&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="bdba5-117">If you have not created this data source view, see [Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="bdba5-118">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="bdba5-119">En la página **especificar tipos de tablas** , active la casilla de verificación de **mayúsculas y minúsculas** junto a la tabla **VAssocSeqOrders** y active la casilla **anidada** junto a la tabla **vAssocSeqLineItems** .</span><span class="sxs-lookup"><span data-stu-id="bdba5-119">On the **Specify Table Types** page, select the **Case** check box next to the **vAssocSeqOrders** table, and select the **Nested** check box next to the **vAssocSeqLineItems** table.</span></span> <span data-ttu-id="bdba5-120">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-120">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bdba5-121">Si se produce un error al activar las **casillas de verificación de** **mayúsculas o minúsculas** , es posible que la combinación de la vista del origen de datos no sea correcta.</span><span class="sxs-lookup"><span data-stu-id="bdba5-121">If an error occurs when you select the **Case** or **Nested** check boxes, it may be that the join in the data source view is not correct.</span></span> <span data-ttu-id="bdba5-122">La tabla anidada, **vAssocSeqLineItems**, debe estar conectada a la tabla de casos, **vAssocSeqOrders,** por una combinación de varios a uno.</span><span class="sxs-lookup"><span data-stu-id="bdba5-122">The nested table, **vAssocSeqLineItems**, must be connected to the case table, **vAssocSeqOrders,** by a many-to-one join.</span></span> <span data-ttu-id="bdba5-123">Puede modificar la relación haciendo clic con el botón secundario en la línea de combinación e invirtiendo entonces la dirección de la unión.</span><span class="sxs-lookup"><span data-stu-id="bdba5-123">You can edit the relationship by right-clicking on the join line and then reversing the direction of the join.</span></span> <span data-ttu-id="bdba5-124">Para obtener más información, vea [cuadro de diálogo crear o editar relación &#40;Analysis Services-&#41;de datos multidimensionales ](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bdba5-124">For more information, see [Create or Edit Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
7.  <span data-ttu-id="bdba5-125">En la página **especificar los datos de entrenamiento** , elija las columnas que se van a usar en el modelo activando una casilla como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="bdba5-125">On the **Specify the Training Data** page, choose the columns for use in the model by selecting a check box as follows:</span></span>  
  
    -   <span data-ttu-id="bdba5-126">**IncomeGroup** Active la casilla **entrada** .</span><span class="sxs-lookup"><span data-stu-id="bdba5-126">**IncomeGroup** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="bdba5-127">Esta columna contiene información interesante sobre los clientes que puede utilizar para la agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="bdba5-127">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="bdba5-128">La utilizará en el primer modelo y, a continuación, la omitirá en el segundo.</span><span class="sxs-lookup"><span data-stu-id="bdba5-128">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="bdba5-129">**OrderNumber** Active la `Key` casilla.</span><span class="sxs-lookup"><span data-stu-id="bdba5-129">**OrderNumber** Select the `Key` check box.</span></span>  
  
         <span data-ttu-id="bdba5-130">Este campo se utilizará como identificador para la tabla de casos o `Key`.</span><span class="sxs-lookup"><span data-stu-id="bdba5-130">This field will be used as the identifier for the case table, or `Key`.</span></span> <span data-ttu-id="bdba5-131">En general, nunca debería utilizar el campo clave de la tabla de casos como una entrada, porque la clave contiene valores únicos que no son útiles para la agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="bdba5-131">In general, you should never use the key field of the case table as an input, because the key contains unique values that are not useful for clustering.</span></span>  
  
    -   <span data-ttu-id="bdba5-132">**Región** de Active la casilla **entrada** .</span><span class="sxs-lookup"><span data-stu-id="bdba5-132">**Region** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="bdba5-133">Esta columna contiene información interesante sobre los clientes que puede utilizar para la agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="bdba5-133">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="bdba5-134">La utilizará en el primer modelo y, a continuación, la omitirá en el segundo.</span><span class="sxs-lookup"><span data-stu-id="bdba5-134">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="bdba5-135">**LineNumber** Active las `Key` casillas **de** verificación y.</span><span class="sxs-lookup"><span data-stu-id="bdba5-135">**LineNumber** Select the `Key` and **Input** check boxes.</span></span>  
  
         <span data-ttu-id="bdba5-136">El campo **lineNumber** se usará como el identificador de la tabla anidada o `Sequence Key` .</span><span class="sxs-lookup"><span data-stu-id="bdba5-136">The **LineNumber** field will be used as the identifier for the nested table, or `Sequence Key`.</span></span> <span data-ttu-id="bdba5-137">La clave para una tabla anidada siempre se debe utilizar para la entrada.</span><span class="sxs-lookup"><span data-stu-id="bdba5-137">The key for a nested table must always be used for input.</span></span>  
  
    -   <span data-ttu-id="bdba5-138">**Modelo** de Active las casillas de verificación de **entrada** y de **predicción** .</span><span class="sxs-lookup"><span data-stu-id="bdba5-138">**Model** Select the **Input** and **Predictable** check boxes.</span></span>  
  
     <span data-ttu-id="bdba5-139">Compruebe que las selecciones sean correctas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-139">Verify that the selections are correct, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="bdba5-140">En la página **especificar el contenido y el tipo de datos de las columnas** , compruebe que la cuadrícula contiene las columnas, los tipos de contenido y los tipos de datos que se muestran en la tabla siguiente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-140">On the **Specify Columns' Content and Data Type** page, verify that the grid contains the columns, content types, and data types shown in the following table, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="bdba5-141">Tablas y columnas</span><span class="sxs-lookup"><span data-stu-id="bdba5-141">Tables/Columns</span></span>|<span data-ttu-id="bdba5-142">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="bdba5-142">Content Type</span></span>|<span data-ttu-id="bdba5-143">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="bdba5-143">Data Type</span></span>|  
    |---------------------|------------------|---------------|  
    |<span data-ttu-id="bdba5-144">IncomeGroup</span><span class="sxs-lookup"><span data-stu-id="bdba5-144">IncomeGroup</span></span>|<span data-ttu-id="bdba5-145">Discrete</span><span class="sxs-lookup"><span data-stu-id="bdba5-145">Discrete</span></span>|<span data-ttu-id="bdba5-146">Texto</span><span class="sxs-lookup"><span data-stu-id="bdba5-146">Text</span></span>|  
    |<span data-ttu-id="bdba5-147">OrderNumber</span><span class="sxs-lookup"><span data-stu-id="bdba5-147">OrderNumber</span></span>|<span data-ttu-id="bdba5-148">Clave</span><span class="sxs-lookup"><span data-stu-id="bdba5-148">Key</span></span>|<span data-ttu-id="bdba5-149">Texto</span><span class="sxs-lookup"><span data-stu-id="bdba5-149">Text</span></span>|  
    |<span data-ttu-id="bdba5-150">Region</span><span class="sxs-lookup"><span data-stu-id="bdba5-150">Region</span></span>|<span data-ttu-id="bdba5-151">Discrete</span><span class="sxs-lookup"><span data-stu-id="bdba5-151">Discrete</span></span>|<span data-ttu-id="bdba5-152">Texto</span><span class="sxs-lookup"><span data-stu-id="bdba5-152">Text</span></span>|  
    |<span data-ttu-id="bdba5-153">vAssocSeqLineItems</span><span class="sxs-lookup"><span data-stu-id="bdba5-153">vAssocSeqLineItems</span></span>|||  
    |<span data-ttu-id="bdba5-154">Line Number</span><span class="sxs-lookup"><span data-stu-id="bdba5-154">Line Number</span></span>|<span data-ttu-id="bdba5-155">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="bdba5-155">Key Sequence</span></span>|<span data-ttu-id="bdba5-156">long</span><span class="sxs-lookup"><span data-stu-id="bdba5-156">Long</span></span>|  
    |<span data-ttu-id="bdba5-157">Modelo</span><span class="sxs-lookup"><span data-stu-id="bdba5-157">Model</span></span>|<span data-ttu-id="bdba5-158">Discrete</span><span class="sxs-lookup"><span data-stu-id="bdba5-158">Discrete</span></span>|<span data-ttu-id="bdba5-159">Texto</span><span class="sxs-lookup"><span data-stu-id="bdba5-159">Text</span></span>|  
  
9. <span data-ttu-id="bdba5-160">En la página **crear conjunto de pruebas** , cambie el **porcentaje de datos de prueba** a 20 y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-160">On the **Create Testing Set** page, change the **Percentage of data for testing** to 20, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="bdba5-161">En la página **finalización del asistente** , en **nombre**de la estructura de minería de datos, escriba `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="bdba5-161">On the **Completing the Wizard** page, for the **Mining structure name**, type `Sequence Clustering with Region`.</span></span>  
  
11. <span data-ttu-id="bdba5-162">En el **nombre del modelo de minería de datos**, escriba `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="bdba5-162">For the **Mining model name**, type `Sequence Clustering with Region`.</span></span>  
  
12. <span data-ttu-id="bdba5-163">Active la casilla **permitir obtención de detalles** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bdba5-163">Check the **Allow drill through** box, and then click **Finish**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="bdba5-164">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="bdba5-164">Next Task in Lesson</span></span>  
 [<span data-ttu-id="bdba5-165">Procesar el modelo de agrupación en clústeres de secuencia</span><span class="sxs-lookup"><span data-stu-id="bdba5-165">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="bdba5-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdba5-166">See Also</span></span>  
 <span data-ttu-id="bdba5-167">[Diseñador de minería de datos](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="bdba5-167">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="bdba5-168">Algoritmo de clústeres de secuencia de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bdba5-168">Microsoft Sequence Clustering Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  
