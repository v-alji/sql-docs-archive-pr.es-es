---
title: Asistente para estimación (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- estimation
ms.assetid: 7f2b1d5f-c9b3-4939-b35a-34ae099af15f
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace9fa3a62690061677312d4f7dbb6b8a1d0ea5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747239"
---
# <a name="estimate-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="bc53e-102">Asistente para estimación (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="bc53e-102">Estimate Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="bc53e-103">![Asistente para estimación, cinta de opciones Minería de datos](media/dmc-estimate.gif "Asistente para estimación, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="bc53e-103">![Estimate wizard in Data Mining ribbon](media/dmc-estimate.gif "Estimate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="bc53e-104">El Asistente para **estimación** le ayuda a crear un modelo de estimación.</span><span class="sxs-lookup"><span data-stu-id="bc53e-104">The **Estimate** wizard helps you create an estimation model.</span></span> <span data-ttu-id="bc53e-105">Un modelo de estimación extrae patrones de los datos y usa los patrones para predecir los factores que afectan a los resultados.</span><span class="sxs-lookup"><span data-stu-id="bc53e-105">An estimation model extracts patterns from data and uses the patterns to predict the factors that affect outcomes.</span></span>  
  
 <span data-ttu-id="bc53e-106">La estimación se utiliza para predecir los resultados numéricos.</span><span class="sxs-lookup"><span data-stu-id="bc53e-106">Estimation is used for predicting numeric outcomes.</span></span> <span data-ttu-id="bc53e-107">Por ejemplo, si la columna de destino contiene las tasas de aprobados de varios centros escolares, expresadas como porcentaje, podría analizar factores que potencialmente aumentan o disminuyen dicha tasa, como el número de alumnos por centro, la proporción entre alumnos y profesores, y el número de profesores.</span><span class="sxs-lookup"><span data-stu-id="bc53e-107">For example, if your target column contains graduation rates for schools, with graduation rates expressed as percentages, you could analyze factors that potentially increase or decrease graduation rates, such as the number of students per school, the student-teacher ratio, and the number of teachers.</span></span>  
  
## <a name="using-the-estimate-data-wizard"></a><span data-ttu-id="bc53e-108">Usar el Asistente para estimación de datos</span><span class="sxs-lookup"><span data-stu-id="bc53e-108">Using the Estimate Data Wizard</span></span>  
  
1.  <span data-ttu-id="bc53e-109">En la cinta de opciones **minería de datos** , haga clic en **estimar**.</span><span class="sxs-lookup"><span data-stu-id="bc53e-109">On the **Data Mining** ribbon, click **Estimate**.</span></span>  
  
2.  <span data-ttu-id="bc53e-110">En el cuadro de diálogo **seleccionar datos de origen** , seleccione los datos de origen que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="bc53e-110">In the **Select Source Data** dialog box, select the source data to use.</span></span> <span data-ttu-id="bc53e-111">Puede utilizar los datos de una **tabla**de Excel, un **intervalo de datos**de Excel o un **origen de datos externo**.</span><span class="sxs-lookup"><span data-stu-id="bc53e-111">You can use data in an Excel **Table**, an Excel **Data Range**, or from an **External data source**.</span></span>  
  
     <span data-ttu-id="bc53e-112">Si utiliza un origen de datos externo, puede crear vistas personalizadas o consultas y guardarlas como un origen de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc53e-112">If you use an external data source, you can create custom views or queries and save them as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="bc53e-113">En el cuadro de diálogo **estimación** , seleccione la **columna que se va a analizar**.</span><span class="sxs-lookup"><span data-stu-id="bc53e-113">In the **Estimation** dialog box, select the **Column to analyze**.</span></span>  
  
     <span data-ttu-id="bc53e-114">La columna de destino debe contener datos numéricos continuos.</span><span class="sxs-lookup"><span data-stu-id="bc53e-114">The target column must contain continuous numeric data.</span></span>  
  
4.  <span data-ttu-id="bc53e-115">Seleccione las columnas que desea usar como entrada activando la casilla **columnas de entrada** .</span><span class="sxs-lookup"><span data-stu-id="bc53e-115">Select columns to use as input by checking the **Input columns** checkbox.</span></span>  
  
     <span data-ttu-id="bc53e-116">Estas columnas se usarán para crear los patrones.</span><span class="sxs-lookup"><span data-stu-id="bc53e-116">These columns will be used to create the patterns.</span></span> <span data-ttu-id="bc53e-117">Debe excluir del análisis las columnas que no sean útiles, como las que contienen números de identificador o datos irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="bc53e-117">You should eliminate from analysis any columns that are not likely to help, such as ID numbers, or columns that contain irrelevant data.</span></span>  
  
5.  <span data-ttu-id="bc53e-118">El Asistente para **estimación** selecciona el algoritmo óptimo para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="bc53e-118">The **Estimate** wizard selects the optimum algorithm for your data set.</span></span> <span data-ttu-id="bc53e-119">Sin embargo, puede hacer clic en **parámetros** para abrir el cuadro de diálogo **parámetros de algoritmo** y establecer opciones avanzadas.</span><span class="sxs-lookup"><span data-stu-id="bc53e-119">However, you can click **Parameters** to open the **Algorithm Parameters** dialog box and set advanced options.</span></span>  
  
6.  <span data-ttu-id="bc53e-120">Si los datos son numéricos y puede usar el método de regresión lineal de Microsoft, puede activar el cuadro **regresor** para cualquier columna numérica que sepa (o sospeche) que se va a correlacionar con el valor de predicción.</span><span class="sxs-lookup"><span data-stu-id="bc53e-120">If your data is numeric and you can use the Microsoft Linear Regression method, you can check the **Regressor** box for any numeric columns that you know (or strongly suspect) to be correlated with the predictable value.</span></span>  
  
     <span data-ttu-id="bc53e-121">El algoritmo comprobará entonces los valores de esa columna para determinar si afectan a los resultados.</span><span class="sxs-lookup"><span data-stu-id="bc53e-121">The algorithm will then test the values in that column to determine if they affect the outcomes.</span></span> <span data-ttu-id="bc53e-122">Si no está seguro, haga clic en **sugerir** y el algoritmo probará todas las columnas y detecte automáticamente los mejores valores que se usarán como regresores.</span><span class="sxs-lookup"><span data-stu-id="bc53e-122">If you are unsure, click **Suggest** and the algorithm will test all column and automatically detect the best values to use as regressors.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc53e-123">Para crear una estimación, se necesita un regresor.</span><span class="sxs-lookup"><span data-stu-id="bc53e-123">A regressor is required to create an estimate.</span></span> <span data-ttu-id="bc53e-124">El asistente siempre recomienda el mejor regresor basándose en un análisis inicial de los datos.</span><span class="sxs-lookup"><span data-stu-id="bc53e-124">The wizard always recommends the best regressor, based on an initial pass over the data.</span></span> <span data-ttu-id="bc53e-125">Por consiguiente, si no está seguro, es mejor que acepte las selecciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="bc53e-125">Therefore, if you are not sure, it is best to accept the recommended selections.</span></span>  
  
7.  <span data-ttu-id="bc53e-126">En la página **dividir datos en conjuntos de entrenamiento y de prueba** , especifique si desea crear un pequeño subconjunto de los datos para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="bc53e-126">On the **Split data into training and testing sets** page, specify whether you want to create a small subset of the data for testing.</span></span>  
  
8.  <span data-ttu-id="bc53e-127">En la página **Finalizar** , proporcione nombres para la nueva estructura de minería de datos y el modo de minería de datos, o acepte los nombres predeterminados que se proporcionan.</span><span class="sxs-lookup"><span data-stu-id="bc53e-127">On the **Finish** page, provide names for the new mining structure and mining mode, or accept the default names that are provided.</span></span>  
  
9. <span data-ttu-id="bc53e-128">Establezca las opciones para usar el modelo.</span><span class="sxs-lookup"><span data-stu-id="bc53e-128">Set options for using the model.</span></span>  
  
    -   <span data-ttu-id="bc53e-129">Seleccione **examinar** para abrir inmediatamente el modelo en un visor.</span><span class="sxs-lookup"><span data-stu-id="bc53e-129">Select **Browse** to immediately open the model in a viewer.</span></span>  
  
         <span data-ttu-id="bc53e-130">Este visor gráfico muestra un gráfico de red de dependencias y el árbol de decisión generado por el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="bc53e-130">This graphical viewer displays a dependency network graph and the decision tree generated by the algorithm.</span></span> <span data-ttu-id="bc53e-131">Si examina esta información, entenderá mejor los factores que contribuyen a los valores estimados.</span><span class="sxs-lookup"><span data-stu-id="bc53e-131">By exploring this information, you can better understand the factors that contribute to the estimated values.</span></span>  
  
    -   <span data-ttu-id="bc53e-132">Seleccione **Habilitar obtención de detalles** para permitir que los usuarios de su análisis vean los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="bc53e-132">Select **Enable drillthrough** to let users of your analysis view the underlying data.</span></span>  
  
         <span data-ttu-id="bc53e-133">Esta opción solo está disponible si utiliza algoritmos de regresión lineal o de árboles de decisión.</span><span class="sxs-lookup"><span data-stu-id="bc53e-133">This option is available only if you use the Decision Trees opr Linear Regression algorithms.</span></span>  
  
    -   <span data-ttu-id="bc53e-134">**Usar modelo temporal**.</span><span class="sxs-lookup"><span data-stu-id="bc53e-134">**Use temporary model**.</span></span> <span data-ttu-id="bc53e-135">Si selecciona esta opción, el modelo no se guardará en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bc53e-135">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="bc53e-136">Se eliminan los modelos temporales al cerrar Excel.</span><span class="sxs-lookup"><span data-stu-id="bc53e-136">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-estimation-models"></a><span data-ttu-id="bc53e-137">Más información sobre los modelos de estimación</span><span class="sxs-lookup"><span data-stu-id="bc53e-137">More About Estimation Models</span></span>  
 <span data-ttu-id="bc53e-138">El Asistente para **estimación** admite el uso de cualquiera de los siguientes algoritmos:</span><span class="sxs-lookup"><span data-stu-id="bc53e-138">The **Estimate** wizard supports the use of any of the following algorithms:</span></span>  
  
-   <span data-ttu-id="bc53e-139">Algoritmo de árbol de decisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-139">Microsoft Decision Tree algorithm</span></span>  
  
-   <span data-ttu-id="bc53e-140">Algoritmo de regresión lineal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-140">Microsoft Linear Regression algorithm</span></span>  
  
-   <span data-ttu-id="bc53e-141">Algoritmo de regresión logística de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-141">Microsoft Logistic Regression algorithm</span></span>  
  
-   <span data-ttu-id="bc53e-142">Algoritmo de red neuronal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-142">Microsoft Neural network algorithm</span></span>  
  
 <span data-ttu-id="bc53e-143">En el cuadro de diálogo **parámetros de algoritmo** , puede establecer opciones avanzadas adicionales, en función del algoritmo que elija.</span><span class="sxs-lookup"><span data-stu-id="bc53e-143">In the **Algorithm Parameters** dialog box, you can set additional advanced options, depending on which algorithm you chose.</span></span> <span data-ttu-id="bc53e-144">Para obtener información sobre las opciones de cada algoritmo, vea estos temas en los Libros en pantalla de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="bc53e-144">For information on the options for each algorithm see these topics in SQL Server Books Online:</span></span>  
  
 [<span data-ttu-id="bc53e-145">Referencia técnica del algoritmo de árboles de decisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-145">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="bc53e-146">Referencia técnica del algoritmo de regresión lineal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-146">Microsoft Linear Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-linear-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="bc53e-147">Referencia técnica del algoritmo de regresión logística de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-147">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="bc53e-148">Referencia técnica del algoritmo de red neuronal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc53e-148">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="bc53e-149">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc53e-149">Requirements</span></span>  
 <span data-ttu-id="bc53e-150">Para usar el Asistente para estimación de datos, debe estar conectado a una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc53e-150">To use the Estimate Data Wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="bc53e-151">Para obtener información sobre cómo crear una conexión, vea [conectarse a los datos de origen &#40;cliente de minería de datos para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="bc53e-151">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="bc53e-152">Para usar el algoritmo de estimación, el resultado que está intentando predecir debería expresarse como un valor numérico, como una moneda, cantidad de ventas, fecha u hora.</span><span class="sxs-lookup"><span data-stu-id="bc53e-152">To use the estimation algorithm, the outcome that you are trying to predict must be expressed as a numeric value, such as a currency, sales amount, date, or time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc53e-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc53e-153">See Also</span></span>  
 <span data-ttu-id="bc53e-154">[Crear un modelo de minería de datos](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="bc53e-154">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="bc53e-155">Tutorial del diagrama de árbol de decisión &#40;complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="bc53e-155">Decision Tree Diagram Walkthrough  &#40;Data Mining Add-ins&#41;</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
  
