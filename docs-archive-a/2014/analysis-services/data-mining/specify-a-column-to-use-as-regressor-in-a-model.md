---
title: Especificar una columna para utilizar como Regresor en un modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8e0cb8e-302a-4166-9ed0-e2d9e2919b0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 86899d3793985b5e3c07618360d7b6a540935a54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662350"
---
# <a name="specify-a-column-to-use-as-regressor-in-a-model"></a><span data-ttu-id="2a533-102">Especificar una columna para utilizar como regresor en un modelo</span><span class="sxs-lookup"><span data-stu-id="2a533-102">Specify a Column to Use as Regressor in a Model</span></span>
  <span data-ttu-id="2a533-103">Un modelo de regresión lineal representa el valor del atributo de predicción como resultado de una fórmula que combina las entradas de manera que los datos se ajusten lo más posible a una línea de regresión estimada.</span><span class="sxs-lookup"><span data-stu-id="2a533-103">A linear regression model represents the value of the predictable attribute as the result of a formula that combines the inputs in such a way that the data is fitted as a closely as possible to an estimated regression line.</span></span> <span data-ttu-id="2a533-104">El algoritmo acepta solamente valores numéricos como entradas y detecta automáticamente las entradas que proporcionan el ajuste óptimo.</span><span class="sxs-lookup"><span data-stu-id="2a533-104">The algorithm accepts only numeric values as inputs, and automatically detects the inputs that provide the best fit.</span></span>  
  
 <span data-ttu-id="2a533-105">Sin embargo, se puede especificar que una columna se incluya como regresor agregando el parámetro FORCE_REGRESSOR al modelo y especificando los regresores que se han de usar.</span><span class="sxs-lookup"><span data-stu-id="2a533-105">However, you can specify that a column be included as a regressor by adding the FORCE_REGRESSOR parameter to the model and specifying the regressors to use.</span></span> <span data-ttu-id="2a533-106">Esto se puede realizar en los casos en que el atributo es significativo aunque el efecto sea demasiado bajo para ser detectado por el modelo, o cuando se desee asegurarse de que el atributo se incluya en la fórmula.</span><span class="sxs-lookup"><span data-stu-id="2a533-106">You might want to do this in cases where the attribute has meaning even if the effect is too small to be detected by the model, or when you want to ensure that the attribute is included in the formula.</span></span>  
  
 <span data-ttu-id="2a533-107">El procedimiento siguiente describe cómo crear un modelo de regresión lineal simple, utilizando los mismos datos de ejemplo que se utilizan para el [tutorial de redes neuronales](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2a533-107">The following procedure describes how to create a simple linear regression model, using the same sample data that is used for the [neural networks tutorial](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="2a533-108">El modelo no es necesariamente robusto, pero muestra cómo se usa el Diseñador de minería de datos para personalizar un modelo de regresión lineal.</span><span class="sxs-lookup"><span data-stu-id="2a533-108">The model is not necessarily robust, but demonstrates how to use the Data Mining Designer to customize a linear regression model.</span></span>  
  
### <a name="how-to-create-a-simple-linear-regression-model"></a><span data-ttu-id="2a533-109">Cómo se crea un modelo de regresión lineal simple</span><span class="sxs-lookup"><span data-stu-id="2a533-109">How to create a simple linear regression model</span></span>  
  
1.  <span data-ttu-id="2a533-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , en **Explorador de soluciones**, expanda **estructuras de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="2a533-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, expand **Mining Structures**.</span></span>  
  
2.  <span data-ttu-id="2a533-111">Haga doble clic en Call Center.dmm para abrirlo en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="2a533-111">Double-click Call Center.dmm to open it in the designer.</span></span>  
  
3.  <span data-ttu-id="2a533-112">En el menú **Modelo de minería de datos** , seleccione **Nuevo modelo de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="2a533-112">From the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="2a533-113">Para el algoritmo, seleccione **Regresión lineal de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="2a533-113">For the algorithm, select **Microsoft Linear Regression**.</span></span> <span data-ttu-id="2a533-114">Para el nombre, escriba **Call Center Regression**.</span><span class="sxs-lookup"><span data-stu-id="2a533-114">For the name, type **Call Center Regression**.</span></span>  
  
5.  <span data-ttu-id="2a533-115">En la pestaña **Modelos de minería de datos** , cambie el uso de columnas como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="2a533-115">In the **Mining Models** tab, change the column usage as follows.</span></span> <span data-ttu-id="2a533-116">Todas las columnas que no estén en la lista siguiente deben establecerse en **Ignore**, si no lo están.</span><span class="sxs-lookup"><span data-stu-id="2a533-116">All columns not in the following list should be set to **Ignore**, if they are not already.</span></span>  
  
     <span data-ttu-id="2a533-117">FactCallCenterID**Key**</span><span class="sxs-lookup"><span data-stu-id="2a533-117">FactCallCenterID**Key**</span></span>  
  
     <span data-ttu-id="2a533-118">ServiceGrade**PredictOnly**</span><span class="sxs-lookup"><span data-stu-id="2a533-118">ServiceGrade**PredictOnly**</span></span>  
  
     <span data-ttu-id="2a533-119">Total Operators**Input**</span><span class="sxs-lookup"><span data-stu-id="2a533-119">Total Operators**Input**</span></span>  
  
     <span data-ttu-id="2a533-120">AverageTimePerIssue**Input**</span><span class="sxs-lookup"><span data-stu-id="2a533-120">AverageTimePerIssue**Input**</span></span>  
  
6.  <span data-ttu-id="2a533-121">En el menú **Modelo de minería de datos** , seleccione **Establecer parámetros de algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="2a533-121">From the **Mining Model** menu, select **Set Model Parameters**.</span></span>  
  
7.  <span data-ttu-id="2a533-122">Para el parámetro, FORCE_REGRESSOR, en la columna **Valor** , escriba los nombres de columna ente corchetes y separados por una coma, como se indica abajo:</span><span class="sxs-lookup"><span data-stu-id="2a533-122">For the parameter, FORCE_REGRESSOR, in the **Value** column, type the column names enclosed in brackets and separated by a comma, as follows:</span></span>  
  
    ```  
    [Average Time Per Issue],[Total Operators]  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a533-123">El algoritmo detectará automáticamente qué columnas son los regresores óptimos.</span><span class="sxs-lookup"><span data-stu-id="2a533-123">The algorithm will automatically detect which columns are the best regressors.</span></span> <span data-ttu-id="2a533-124">Tan solo es necesario forzar los regresores cuando se desee asegurarse de que una columna esté incluida en la fórmula final.</span><span class="sxs-lookup"><span data-stu-id="2a533-124">You only need to force regressors when you want to ensure that a column is included in the final formula.</span></span>  
  
8.  <span data-ttu-id="2a533-125">En el menú **Modelo de minería de datos** , seleccione **Procesar modelo**.</span><span class="sxs-lookup"><span data-stu-id="2a533-125">From the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="2a533-126">En el visor, el modelo se representa en un solo nodo que contiene la fórmula de regresión.</span><span class="sxs-lookup"><span data-stu-id="2a533-126">In the viewer, the model is represented a single node containing the regression formula.</span></span> <span data-ttu-id="2a533-127">Se puede ver la fórmula en la **Leyenda de minería de datos**o se pueden extraer los coeficientes para la fórmula mediante el uso de consultas.</span><span class="sxs-lookup"><span data-stu-id="2a533-127">You can view the formula in the **Mining Legend**, or you can extract the coefficients for the formula by using queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a533-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a533-128">See Also</span></span>  
 <span data-ttu-id="2a533-129">[Algoritmo de regresión lineal de Microsoft](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="2a533-129">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="2a533-130">[Consultas de minería de datos](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="2a533-130">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="2a533-131">[Referencia técnica del algoritmo de regresión lineal de Microsoft](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2a533-131">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="2a533-132">Contenido del modelo de minería de datos para los modelos de regresión lineal &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2a533-132">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
