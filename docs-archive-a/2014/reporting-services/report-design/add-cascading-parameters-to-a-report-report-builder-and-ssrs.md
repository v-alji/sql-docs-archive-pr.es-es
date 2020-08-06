---
title: Agregar parámetros en cascada a un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a22eec3-57a7-478e-b6fc-102a9dbe0591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5419d448b2fa9526224e1bccd80d5c195e2763d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744482"
---
# <a name="add-cascading-parameters-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="dd36d-102">Agregar parámetros en cascada a un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="dd36d-102">Add Cascading Parameters to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dd36d-103">Los parámetros en cascada permiten administrar grandes cantidades de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="dd36d-103">Cascading parameters provide a way of managing large amounts of report data.</span></span> <span data-ttu-id="dd36d-104">Es posible definir un conjunto de parámetros relacionados de manera que la lista de valores de uno de ellos dependa del valor seleccionado en otro parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-104">You can define a set of related parameters so that the list of values for one parameter depends on the value chosen in another parameter.</span></span> <span data-ttu-id="dd36d-105">Por ejemplo, el primer parámetro es independiente y podría presentar una lista de categorías de productos.</span><span class="sxs-lookup"><span data-stu-id="dd36d-105">For example, the first parameter is independent and might present a list of product categories.</span></span> <span data-ttu-id="dd36d-106">Cuando el usuario selecciona una categoría, el segundo parámetro depende del valor del primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-106">When the user selects a category, the second parameter is dependent on the value of the first parameter.</span></span> <span data-ttu-id="dd36d-107">Sus valores se actualizan con una lista de subcategorías para la categoría elegida.</span><span class="sxs-lookup"><span data-stu-id="dd36d-107">Its values are updated with a list of subcategories within the chosen category.</span></span> <span data-ttu-id="dd36d-108">Cuando el usuario ve el informe, los valores de los parámetros de categoría y subcategoría se usan para filtrar los datos del informe.</span><span class="sxs-lookup"><span data-stu-id="dd36d-108">When the user views the report, the values for both the category and subcategory parameters are used to filter report data.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="dd36d-109">Para crear parámetros en cascada, primero debe definir la consulta del conjunto de datos e incluir un parámetro de consulta para cada parámetro en cascada que necesite.</span><span class="sxs-lookup"><span data-stu-id="dd36d-109">To create cascading parameters, you define the dataset query first and include a query parameter for each cascading parameter that you need.</span></span> <span data-ttu-id="dd36d-110">También debe crear un conjunto de datos independiente para que para cada parámetro en cascada proporcione los valores disponibles.</span><span class="sxs-lookup"><span data-stu-id="dd36d-110">You must also create a separate dataset for each cascading parameter to provide available values.</span></span> <span data-ttu-id="dd36d-111">Para más información, vea [Agregar, cambiar o eliminar los valores disponibles para un parámetro de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="dd36d-111">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
 <span data-ttu-id="dd36d-112">El orden es importante para los parámetros en cascada, dado que la consulta del conjunto de datos de un parámetro que aparece más adelante en la lista incluye una referencia a cada parámetro que aparece antes en la lista.</span><span class="sxs-lookup"><span data-stu-id="dd36d-112">Order is important for cascading parameters because the dataset query for a parameter later in the list includes a reference to each parameter that is earlier in the list.</span></span> <span data-ttu-id="dd36d-113">En tiempo de ejecución, el orden de los parámetros en el panel Datos de informe determina el orden en que aparecen las consultas de parámetros en el informe, y por consiguiente, el orden en el que el usuario elige cada uno de los valores de los parámetros sucesivos.</span><span class="sxs-lookup"><span data-stu-id="dd36d-113">At run time, the order of the parameters in the Report Data pane determines the order in which the parameter queries appear in the report, and therefore, the order in which a user chooses each successive parameter value.</span></span>  
  
 <span data-ttu-id="dd36d-114">Para obtener información sobre la creación de parámetros en cascada con varios valores e incluso la función Select All, vea [Tener un parámetro en cascada con varios valores y Select All](https://go.microsoft.com/fwlink/?LinkId=184757).</span><span class="sxs-lookup"><span data-stu-id="dd36d-114">For information about creating cascading parameters with multiple values and including the Select All feature, see [How to have a Select All Multivalue Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757).</span></span>  
  
### <a name="to-create-the-main-dataset-with-a-query-that-includes-multiple-related-parameters"></a><span data-ttu-id="dd36d-115">Para crear el conjunto de datos principal con una consulta que incluye varios parámetros relacionados</span><span class="sxs-lookup"><span data-stu-id="dd36d-115">To create the main dataset with a query that includes multiple related parameters</span></span>  
  
1.  <span data-ttu-id="dd36d-116">En el panel Datos de informe, haga clic con el botón derecho en un origen de datos y, después, haga clic en **Agregar conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-116">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="dd36d-117">En **Nombre**, escriba el nombre del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="dd36d-117">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="dd36d-118">En **Origen de datos**, elija el nombre del origen de datos o haga clic en **Nuevo** para crear uno.</span><span class="sxs-lookup"><span data-stu-id="dd36d-118">In **Data source**, choose the name of the data source or click **New** to create one.</span></span>  
  
4.  <span data-ttu-id="dd36d-119">En **Tipo de consulta**, elija el tipo de consulta para el origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dd36d-119">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="dd36d-120">En este tema, se supone que el tipo de consulta es **Texto** .</span><span class="sxs-lookup"><span data-stu-id="dd36d-120">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="dd36d-121">En **Consulta**, escriba la consulta que se debe usar para recuperar los datos para este informe.</span><span class="sxs-lookup"><span data-stu-id="dd36d-121">In **Query**, type the query to use to retrieve data for this report.</span></span> <span data-ttu-id="dd36d-122">La consulta debe incluir las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd36d-122">The query must include the following parts:</span></span>  
  
    1.  <span data-ttu-id="dd36d-123">Una lista de campos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="dd36d-123">A list of data source fields.</span></span> <span data-ttu-id="dd36d-124">Por ejemplo, en una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] , la instrucción SELECT especifica una lista de nombres de columnas de la base de datos de una tabla o vista determinada.</span><span class="sxs-lookup"><span data-stu-id="dd36d-124">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, the SELECT statement specifies a list of database column names from a given table or view.</span></span>  
  
    2.  <span data-ttu-id="dd36d-125">Un parámetro de consulta para cada parámetro en cascada.</span><span class="sxs-lookup"><span data-stu-id="dd36d-125">One query parameter for each cascading parameter.</span></span> <span data-ttu-id="dd36d-126">Un parámetro de consulta limita los datos recuperados del origen de datos especificando determinados valores para incluirlos o excluirlos de la consulta.</span><span class="sxs-lookup"><span data-stu-id="dd36d-126">A query parameter limits the data retrieved from the data source by specifying certain values to include or exclude from the query.</span></span> <span data-ttu-id="dd36d-127">Normalmente, los parámetros de consulta se sitúan en una cláusula de restricción de la consulta.</span><span class="sxs-lookup"><span data-stu-id="dd36d-127">Typically, query parameters occur in a restriction clause in the query.</span></span> <span data-ttu-id="dd36d-128">Por ejemplo, en una instrucción SELECT de [!INCLUDE[tsql](../../includes/tsql-md.md)] , los parámetros de consulta se sitúan en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="dd36d-128">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement, query parameters occur in the WHERE clause.</span></span> <span data-ttu-id="dd36d-129">Para obtener más información, vea "Filtrar filas mediante WHERE y HAVING" en la documentación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en los [Libros en pantalla de SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="dd36d-129">For more information, see "Filtering Rows by Using WHERE and HAVING" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
6.  <span data-ttu-id="dd36d-130">Haga clic en **Ejecutar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="dd36d-130">Click **Run** (**!**).</span></span> <span data-ttu-id="dd36d-131">Una vez incluidos los parámetros de la consulta y ejecutada la consulta, automáticamente se crean parámetros de informe correspondientes a los parámetros de la consulta.</span><span class="sxs-lookup"><span data-stu-id="dd36d-131">After you include query parameters and then run the query, report parameters that correspond to the query parameters are automatically created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd36d-132">El orden que tienen los parámetros de la consulta la primera vez se ejecuta una consulta determina el orden en que se crean en el informe.</span><span class="sxs-lookup"><span data-stu-id="dd36d-132">The order of query parameters the first time you run a query determines the order that they are created in the report.</span></span> <span data-ttu-id="dd36d-133">Para cambiar el orden, vea [Cambiar el orden de un parámetro de informe &#40;Generador de informes y SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd36d-133">To change the order, see [Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="dd36d-134">A continuación, creará un conjunto de datos que proporciona los valores para el parámetro independiente.</span><span class="sxs-lookup"><span data-stu-id="dd36d-134">Next, you will create a dataset that provides the values for the independent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-an-independent-parameter"></a><span data-ttu-id="dd36d-135">Para crear un conjunto de datos para proporcionar los valores para un parámetro independiente</span><span class="sxs-lookup"><span data-stu-id="dd36d-135">To create a dataset to provide values for an independent parameter</span></span>  
  
1.  <span data-ttu-id="dd36d-136">En el panel Datos de informe, haga clic con el botón derecho en un origen de datos y, después, haga clic en **Agregar conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-136">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="dd36d-137">En **Nombre**, escriba el nombre del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="dd36d-137">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="dd36d-138">En **Origen de datos**, compruebe que el nombre es el nombre del origen de datos que eligió en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="dd36d-138">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="dd36d-139">En **Tipo de consulta**, elija el tipo de consulta para el origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dd36d-139">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="dd36d-140">En este tema, se supone que el tipo de consulta es **Texto** .</span><span class="sxs-lookup"><span data-stu-id="dd36d-140">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="dd36d-141">En **Consulta**, escriba la consulta que se debe usar para recuperar los valores para este parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-141">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="dd36d-142">Las consultas para los parámetros independientes normalmente no contienen los parámetros de la consulta.</span><span class="sxs-lookup"><span data-stu-id="dd36d-142">Queries for independent parameters typically do not contain query parameters.</span></span> <span data-ttu-id="dd36d-143">Por ejemplo, para crear una consulta para un parámetro que proporciona los valores de todas las categorías, podría usar una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd36d-143">For example, to create a query for a parameter that provides all category values, you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT <column name> FROM <table>  
    ```  
  
     <span data-ttu-id="dd36d-144">El comando SELECT DISTINCT quita los valores duplicados del conjunto de resultados para que obtenga cada valor único de la columna y la tabla especificadas.</span><span class="sxs-lookup"><span data-stu-id="dd36d-144">The SELECT DISTINCT command removes duplicate values from the result set so that you get each unique value from the specified column in the specified table.</span></span>  
  
     <span data-ttu-id="dd36d-145">Haga clic en **Ejecutar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="dd36d-145">Click **Run** (**!**).</span></span> <span data-ttu-id="dd36d-146">El conjunto de resultados muestra los valores disponibles para este primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-146">The result set shows the values that are available for this first parameter.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="dd36d-147">A continuación, establecerá las propiedades del primer parámetro que se debe usar en este conjunto de datos para rellenar sus valores disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd36d-147">Next, you will set the properties of the first parameter to use this dataset to populate its available values at run-time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="dd36d-148">Para establecer los valores disponibles para un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="dd36d-148">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="dd36d-149">En la carpeta Parámetros del panel Datos de informe, haga clic con el botón derecho en el primer parámetro y, después, haga clic en **Propiedades del parámetro**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-149">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="dd36d-150">En **Nombre**, compruebe que el nombre del parámetro es correcto.</span><span class="sxs-lookup"><span data-stu-id="dd36d-150">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="dd36d-151">Haga clic en **Valores disponibles**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-151">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="dd36d-152">Haga clic en **Obtener valores a partir de una consulta**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-152">Click **Get values from a query**.</span></span> <span data-ttu-id="dd36d-153">Aparecen tres campos.</span><span class="sxs-lookup"><span data-stu-id="dd36d-153">Three fields appear.</span></span>  
  
5.  <span data-ttu-id="dd36d-154">En **Conjunto de datos**, en la lista desplegable, haga clic en el nombre del conjunto de datos que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="dd36d-154">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="dd36d-155">En el campo **Valor** , haga clic en el nombre del campo que proporciona el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-155">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="dd36d-156">En el campo **Etiqueta** , haga clic en el nombre del campo que proporciona la etiqueta del parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-156">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="dd36d-157">A continuación, creará un conjunto de datos que proporcione los valores para el parámetro dependiente.</span><span class="sxs-lookup"><span data-stu-id="dd36d-157">Next, you will create a dataset that provides the values for a dependent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-a-dependent-parameter"></a><span data-ttu-id="dd36d-158">Para crear un conjunto de datos para proporcionar los valores para un parámetro dependiente</span><span class="sxs-lookup"><span data-stu-id="dd36d-158">To create a dataset to provide values for a dependent parameter</span></span>  
  
1.  <span data-ttu-id="dd36d-159">En el panel Datos de informe, haga clic con el botón derecho en un origen de datos y, después, haga clic en **Agregar conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-159">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="dd36d-160">En **Nombre**, escriba el nombre del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="dd36d-160">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="dd36d-161">En **Origen de datos**, compruebe que el nombre es el nombre del origen de datos que eligió en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="dd36d-161">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="dd36d-162">En **Tipo de consulta**, elija el tipo de consulta para el origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dd36d-162">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="dd36d-163">En este tema, se supone que el tipo de consulta es **Texto** .</span><span class="sxs-lookup"><span data-stu-id="dd36d-163">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="dd36d-164">En **Consulta**, escriba la consulta que se debe usar para recuperar los valores para este parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-164">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="dd36d-165">Las consultas para los parámetros dependientes normalmente incluyen parámetros de consulta para cada parámetro del que depende este parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-165">Queries for dependent parameters typically include query parameters for each parameter that this parameter is dependent on.</span></span> <span data-ttu-id="dd36d-166">Por ejemplo, para crear una consulta para un parámetro que proporciona todos los valores de subcategoría (parámetro dependiente) para una categoría (parámetro independiente), podría usar una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd36d-166">For example, to create a query for a parameter that provides all subcategory (dependent parameter) values for a category (independent parameter), you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT Subcategory FROM <table>   
    WHERE (Category = @Category)  
    ```  
  
     <span data-ttu-id="dd36d-167">En la cláusula WHERE, Category es el nombre de un campo de \<table> y @Category es un parámetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="dd36d-167">In the WHERE clause, Category is the name of a field from \<table> and @Category is a query parameter.</span></span> <span data-ttu-id="dd36d-168">Esta instrucción genera una lista de subcategorías para la categoría especificada en @Category.</span><span class="sxs-lookup"><span data-stu-id="dd36d-168">This statement produces a list of subcategories for the category specified in @Category.</span></span> <span data-ttu-id="dd36d-169">En tiempo de ejecución, este valor se rellenará con el valor elegido por el usuario para el parámetro de informe que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="dd36d-169">At run time, this value will be filled in with the value that the user chooses for the report parameter that has the same name.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="dd36d-170">A continuación, establecerá las propiedades del segundo parámetro que se debe usar en este conjunto de datos para rellenar sus valores disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd36d-170">Next, you will set the properties of the second parameter to use this dataset to populate its available values at run time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="dd36d-171">Para establecer los valores disponibles para un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="dd36d-171">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="dd36d-172">En la carpeta Parámetros del panel Datos de informe, haga clic con el botón derecho en el primer parámetro y, después, haga clic en **Propiedades del parámetro**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-172">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="dd36d-173">En **Nombre**, compruebe que el nombre del parámetro es correcto.</span><span class="sxs-lookup"><span data-stu-id="dd36d-173">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="dd36d-174">Haga clic en **Valores disponibles**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-174">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="dd36d-175">Haga clic en **Obtener valores a partir de una consulta**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-175">Click **Get values from a query**.</span></span>  
  
5.  <span data-ttu-id="dd36d-176">En **Conjunto de datos**, en la lista desplegable, haga clic en el nombre del conjunto de datos que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="dd36d-176">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="dd36d-177">En el campo **Valor** , haga clic en el nombre del campo que proporciona el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-177">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="dd36d-178">En el campo **Etiqueta** , haga clic en el nombre del campo que proporciona la etiqueta del parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-178">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-cascading-parameters"></a><span data-ttu-id="dd36d-179">Para probar los parámetros en cascada</span><span class="sxs-lookup"><span data-stu-id="dd36d-179">To test the cascading parameters</span></span>  
  
1.  <span data-ttu-id="dd36d-180">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-180">Click **Run**.</span></span>  
  
2.  <span data-ttu-id="dd36d-181">En la lista desplegable del primer parámetro, el parámetro independiente, elija un valor.</span><span class="sxs-lookup"><span data-stu-id="dd36d-181">From the drop-down list for the first, independent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="dd36d-182">El procesador de informes ejecuta la consulta del conjunto de datos para el parámetro siguiente y le pasa el valor que eligió para el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-182">The report processor runs the dataset query for the next parameter and passes it the value you chose for the first parameter.</span></span> <span data-ttu-id="dd36d-183">La lista desplegable del segundo parámetro se rellena con los valores disponibles basados en el valor del primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="dd36d-183">The drop-down list for the second parameter is populated with the available values based on the first parameter value.</span></span>  
  
3.  <span data-ttu-id="dd36d-184">De la lista desplegable del segundo parámetro, el parámetro dependiente, elija un valor.</span><span class="sxs-lookup"><span data-stu-id="dd36d-184">From the drop-down list for the second, dependent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="dd36d-185">El informe no se ejecuta automáticamente después de elegir el último parámetro para que pueda cambiar su elección.</span><span class="sxs-lookup"><span data-stu-id="dd36d-185">The report does not run automatically after you choose the last parameter so that you can change your choice.</span></span>  
  
4.  <span data-ttu-id="dd36d-186">Haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="dd36d-186">Click **View Report**.</span></span> <span data-ttu-id="dd36d-187">El informe actualiza la presentación basándose en los parámetros que ha elegido.</span><span class="sxs-lookup"><span data-stu-id="dd36d-187">The report updates the display based on the parameters you have chosen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd36d-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd36d-188">See Also</span></span>  
 <span data-ttu-id="dd36d-189">[Agregar, cambiar o eliminar un parámetro de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd36d-189">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd36d-190">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="dd36d-190">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="dd36d-191">[Tutorial: agregar un parámetro a un informe &#40;Generador de informes&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="dd36d-191">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="dd36d-192">[Tutoriales &#40;Generador de informes&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="dd36d-192">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="dd36d-193">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="dd36d-193">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="dd36d-194">Conjuntos de datos incrustados y compartidos de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dd36d-194">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
