---
title: Algoritmo de regresión lineal de Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- linear regression algorithms [Analysis Services]
- linear regression [Analysis Services]
- regression algorithms [Analysis Services]
ms.assetid: 50a4abb8-c0b0-4380-ba5e-c49b305b9d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6d03f4d60131471d1a978fd66306cc73f274a536
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677297"
---
# <a name="microsoft-linear-regression-algorithm"></a><span data-ttu-id="b6f3f-102">Algoritmo de regresión lineal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b6f3f-102">Microsoft Linear Regression Algorithm</span></span>
  <span data-ttu-id="b6f3f-103">El algoritmo de regresión lineal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] es una variación del algoritmo de árboles de decisión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] que ayuda a calcular una relación lineal entre una variable independiente y otra dependiente y, a continuación, utilizar esa relación para la predicción.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm is a variation of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees algorithm that helps you calculate a linear relationship between a dependent and independent variable, and then use that relationship for prediction.</span></span>

 <span data-ttu-id="b6f3f-104">La relación toma la forma de una ecuación para la línea que mejor represente una serie de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-104">The relationship takes the form of an equation for a line that best represents a series of data.</span></span> <span data-ttu-id="b6f3f-105">Por ejemplo, la línea del siguiente diagrama muestra la mejor representación lineal de los datos.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-105">For example, the line in the following diagram is the best possible linear representation of the data.</span></span>

 <span data-ttu-id="b6f3f-106">![Línea que modela un conjunto de datos](../media/linear-regression.gif "Línea que modela un conjunto de datos")</span><span class="sxs-lookup"><span data-stu-id="b6f3f-106">![A line that models a set of data](../media/linear-regression.gif "A line that models a set of data")</span></span>

 <span data-ttu-id="b6f3f-107">Cada punto de datos del diagrama tiene un error asociado con su distancia con respecto a la línea de regresión.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-107">Each data point in the diagram has an error associated with its distance from the regression line.</span></span> <span data-ttu-id="b6f3f-108">Los coeficientes a y b de la ecuación de regresión ajustan el ángulo y la ubicación de la recta de regresión.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-108">The coefficients a and b in the regression equation adjust the angle and location of the regression line.</span></span> <span data-ttu-id="b6f3f-109">Puede obtener la ecuación de regresión ajustando a y b hasta que la suma de los errores asociados a todos los puntos alcance su valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-109">You can obtain the regression equation by adjusting a and b until the sum of the errors that are associated with all the points reaches its minimum.</span></span>

 <span data-ttu-id="b6f3f-110">Hay otros tipos de regresión que utilizan varias variables y también hay métodos no lineales de regresión.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-110">There are other kinds of regression that use multiple variables, and also nonlinear methods of regression.</span></span> <span data-ttu-id="b6f3f-111">Sin embargo, la regresión lineal es un método útil y conocido para modelar una respuesta a un cambio de algún factor subyacente.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-111">However, linear regression is a useful and well-known method for modeling a response to a change in some underlying factor.</span></span>

## <a name="example"></a><span data-ttu-id="b6f3f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6f3f-112">Example</span></span>
 <span data-ttu-id="b6f3f-113">Puede utilizar la regresión lineal para determinar una relación entre dos columnas continuas.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-113">You can use linear regression to determine a relationship between two continuous columns.</span></span> <span data-ttu-id="b6f3f-114">Por ejemplo, puede utilizar la regresión lineal para calcular una línea de tendencias en los datos de fabricación o ventas.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-114">For example, you can use linear regression to compute a trend line from manufacturing or sales data.</span></span> <span data-ttu-id="b6f3f-115">También podría utilizar la regresión lineal como precursor para el desarrollo de modelos de minería de datos más complejos, con el fin de evaluar las relaciones entre las columnas de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-115">You could also use the linear regression as a precursor to development of more complex data mining models, to assess the relationships among data columns.</span></span>

 <span data-ttu-id="b6f3f-116">Aunque hay muchas maneras de calcular la regresión lineal que no requieren herramientas de minería de datos, la ventaja de utilizar el algoritmo de regresión lineal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] para esta tarea es que se calculan y se prueban automáticamente todas las posibles relaciones entre las variables.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-116">Although there are many ways to compute linear regression that do not require data mining tools, the advantage of using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm for this task is that all the possible relationships among the variables are automatically computed and tested.</span></span> <span data-ttu-id="b6f3f-117">No tiene que seleccionar un método de cálculo, como por ejemplo para resolver los mínimos cuadrados.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-117">You do not have to select a computation method, such as solving for least squares.</span></span> <span data-ttu-id="b6f3f-118">Sin embargo, la regresión lineal podría simplificar en exceso las relaciones en escenarios en los que varios factores afectan al resultado.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-118">However, linear regression might oversimplify the relationships in scenarios where multiple factors affect the outcome.</span></span>

## <a name="how-the-algorithm-works"></a><span data-ttu-id="b6f3f-119">Cómo funciona el algoritmo</span><span class="sxs-lookup"><span data-stu-id="b6f3f-119">How the Algorithm Works</span></span>
 <span data-ttu-id="b6f3f-120">El algoritmo de regresión lineal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] es una variación del algoritmo de árboles de decisión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6f3f-120">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm is a variation of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="b6f3f-121">Al seleccionar el algoritmo de regresión lineal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] , se invoca un caso especial del algoritmo de árboles de decisión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] , con parámetros que restringen el comportamiento del algoritmo y requieren ciertos tipos de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-121">When you select the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm, a special case of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees algorithm is invoked, with parameters that constrain the behavior of the algorithm and require certain input data types.</span></span> <span data-ttu-id="b6f3f-122">Además, en un modelo de regresión lineal, el conjunto de datos completo se utiliza para calcular las relaciones en el paso inicial, mientras que en un modelo de árboles de decisión estándar los datos se dividen repetidamente en árboles o subconjuntos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-122">Moreover, in a linear regression model, the whole data set is used for computing relationships in the initial pass, whereas a standard decision trees model splits the data repeatedly into smaller subsets or trees.</span></span>

## <a name="data-required-for-linear-regression-models"></a><span data-ttu-id="b6f3f-123">Datos requeridos para los modelos de regresión lineal</span><span class="sxs-lookup"><span data-stu-id="b6f3f-123">Data Required for Linear Regression Models</span></span>
 <span data-ttu-id="b6f3f-124">Cuando se preparan datos para utilizarse en un modelo de regresión lineal, se deben entender los requisitos del algoritmo determinado.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-124">When you prepare data for use in a linear regression model, you should understand the requirements for the particular algorithm.</span></span> <span data-ttu-id="b6f3f-125">Esto incluye saber cuántos datos se necesitan y cómo se utilizan.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-125">This includes how much data is needed, and how the data is used.</span></span> <span data-ttu-id="b6f3f-126">Los requisitos para este tipo de modelo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6f3f-126">The requirements for this model type are as follows:</span></span>

-   <span data-ttu-id="b6f3f-127">**Una columna de una sola clave** : cada modelo debe contener una columna numérica o de texto que identifique cada registro de manera única.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-127">**A single key column** Each model must contain one numeric or text column that uniquely identifies each record.</span></span> <span data-ttu-id="b6f3f-128">No están permitidas las claves compuestas.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-128">Compound keys are not permitted.</span></span>

-   <span data-ttu-id="b6f3f-129">**Una columna de predicción** . Se requiere al menos una columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-129">**A predictable column** Requires at least one predictable column.</span></span> <span data-ttu-id="b6f3f-130">Se pueden incluir varios atributos de predicción en un modelo, pero deben ser tipos de datos numéricos continuos.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-130">You can include multiple predictable attributes in a model, but the predictable attributes must be continuous numeric data types.</span></span> <span data-ttu-id="b6f3f-131">No se puede utilizar un tipo de datos de fecha y hora como atributo de predicción aunque el almacenamiento nativo para los datos sea numérico.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-131">You cannot use a datetime data type as a predictable attribute even if the native storage for the data is numeric.</span></span>

-   <span data-ttu-id="b6f3f-132">**Columnas de entrada** Deben contener datos numéricos continuos y se les debe asignarse el tipo de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-132">**Input columns** Input columns must contain continuous numeric data and be assigned the appropriate data type.</span></span>

 <span data-ttu-id="b6f3f-133">Para obtener más información, vea la sección Requisitos de [Referencia técnica del algoritmo de regresión lineal de Microsoft](microsoft-linear-regression-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b6f3f-133">For more information, see the Requirements section of [Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md).</span></span>

## <a name="viewing-a-linear-regression-model"></a><span data-ttu-id="b6f3f-134">Ver un modelo de regresión lineal</span><span class="sxs-lookup"><span data-stu-id="b6f3f-134">Viewing a Linear Regression Model</span></span>
 <span data-ttu-id="b6f3f-135">Para examinar el modelo, puede utilizar el **Visor de árboles de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-135">To explore the model, you use the **Microsoft Tree Viewer**.</span></span> <span data-ttu-id="b6f3f-136">La estructura de árbol de un modelo de regresión lineal es muy simple, con toda la información sobre la ecuación de regresión contenida en un nodo único.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-136">The tree structure for a linear regression model is very simple, with all the information about the regression equation contained in a single node.</span></span> <span data-ttu-id="b6f3f-137">Para obtener más información, vea [Examinar un modelo usando el Visor de árboles de Microsoft](browse-a-model-using-the-microsoft-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="b6f3f-137">For more information, see [Browse a Model Using the Microsoft Tree Viewer](browse-a-model-using-the-microsoft-tree-viewer.md).</span></span>

 <span data-ttu-id="b6f3f-138">Si desea obtener información más detallada sobre la ecuación, también puede ver los coeficientes y otros detalles utilizando el [Visor de árbol de contenido genérico de Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="b6f3f-138">If you want to know more detail about the equation, you can also view the coefficients and other details by using the [Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>

 <span data-ttu-id="b6f3f-139">En un modelo de regresión lineal, el contenido incluye metadatos, la fórmula de regresión y estadísticas sobre la distribución de los valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-139">For a linear regression model, the model content includes metadata, the regression formula, and statistics about the distribution of input values.</span></span> <span data-ttu-id="b6f3f-140">Para obtener más información, vea [Contenido del modelo de minería de datos para los modelos de regresión lineal &#40;Analysis Services - Minería de datos&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b6f3f-140">For more information, see [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span></span>

## <a name="creating-predictions"></a><span data-ttu-id="b6f3f-141">Crear predicciones</span><span class="sxs-lookup"><span data-stu-id="b6f3f-141">Creating Predictions</span></span>
 <span data-ttu-id="b6f3f-142">Una vez procesado el modelo, los resultados se almacenan como un conjunto de estadísticas junto con la fórmula de regresión lineal, que se puede utilizar para calcular tendencias futuras.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-142">After the model has been processed, the results are stored as a set of statistics together with the linear regression formula, which you can use to compute future trends.</span></span> <span data-ttu-id="b6f3f-143">Para obtener ejemplos de consultas que se usan con un modelo regresión lineal, vea [Ejemplos de consultas de modelos de regresión lineal](linear-regression-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="b6f3f-143">For examples of queries to use with a linear regression model, see [Linear Regression Model Query Examples](linear-regression-model-query-examples.md).</span></span>

 <span data-ttu-id="b6f3f-144">Para obtener información general sobre cómo crear consultas con modelos de minería de datos, vea [Consultas de minería de datos](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b6f3f-144">For general information about how to create queries against mining models, see [Data Mining Queries](data-mining-queries.md).</span></span>

 <span data-ttu-id="b6f3f-145">Además de crear un modelo de regresión lineal seleccionando el algoritmo de regresión lineal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] , si el atributo de predicción es un tipo de datos numéricos continuo, puede crear un modelo de árbol de decisión que contenga regresiones.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-145">In addition to creating a linear regression model by selecting the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm, if the predictable attribute is a continuous numeric data type, you can create a decision tree model that contains regressions.</span></span> <span data-ttu-id="b6f3f-146">En este caso, el algoritmo dividirá los datos cuando encuentre puntos de separación adecuados, pero en cambio creará una fórmula de regresión para algunas regiones de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-146">In this case, the algorithm will split the data when it finds appropriate separation points, but for some regions of data, will create a regression formula instead.</span></span> <span data-ttu-id="b6f3f-147">Para obtener más información sobre los árboles de regresión en un modelo de árboles de decisión, vea [Contenido del modelo de minería de datos para los modelos de árboles de decisión &#40;Analysis Services - Minería de datos&#41;](mining-model-content-for-decision-tree-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b6f3f-147">For more information about regression trees within a decision trees model, see [Mining Model Content for Decision Tree Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-decision-tree-models-analysis-services-data-mining.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="b6f3f-148">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b6f3f-148">Remarks</span></span>

-   <span data-ttu-id="b6f3f-149">No se admite el uso del Lenguaje de marcado de modelos de predicción (PMML) para crear modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-149">Does not support the use of Predictive Model Markup Language (PMML) to create mining models.</span></span>

-   <span data-ttu-id="b6f3f-150">No admite la creación de dimensiones de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-150">Does not support the creation of data mining dimensions.</span></span>

-   <span data-ttu-id="b6f3f-151">Admite la obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-151">Supports drillthrough.</span></span>

-   <span data-ttu-id="b6f3f-152">Admite el uso de modelos de minería de datos OLAP.</span><span class="sxs-lookup"><span data-stu-id="b6f3f-152">Supports the use of OLAP mining models.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6f3f-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6f3f-153">See Also</span></span>
 <span data-ttu-id="b6f3f-154">[Algoritmos de minería de datos &#40;Analysis Services de minería de datos&#41;](data-mining-algorithms-analysis-services-data-mining.md) algoritmo de regresión lineal de [referencia técnica del algoritmo](microsoft-linear-regression-algorithm-technical-reference.md) de regresión [lineal ejemplo de consulta de modelo](linear-regression-model-query-examples.md) [de minería de datos para los modelos de regresión lineal &#40;Analysis Services-Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="b6f3f-154">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) [Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) [Linear Regression Model Query Examples](linear-regression-model-query-examples.md) [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)</span></span>

