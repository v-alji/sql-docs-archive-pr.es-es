---
title: Gráfico de beneficios (complementos de minería de datos de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- accuracy chart
- profit chart
- mining models, charting
- mining models, testing
ms.assetid: 5c902543-4da9-4db3-99d5-4ce04c43d7ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 030e511047b816543c12c81bdab307e599bbc5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673292"
---
# <a name="profit-chart-sql-server-data-mining-add-ins"></a><span data-ttu-id="3570c-102">Gráfico de beneficios (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3570c-102">Profit Chart (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="3570c-103">![Botón Gráfico de beneficios, cinta de opciones Minería de datos](media/dmc-profitchart.gif "Botón Gráfico de beneficios, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="3570c-103">![Profit Chart button in Data Mining ribbon](media/dmc-profitchart.gif "Profit Chart button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="3570c-104">Un gráfico de beneficios muestra el incremento estimado de beneficios relacionado con el uso de un modelo de minería de datos para determinar con qué clientes debe ponerse en contacto una empresa en un escenario empresarial.</span><span class="sxs-lookup"><span data-stu-id="3570c-104">A profit chart displays the estimated profit increase that is associated with using a mining model to determine which customers a company should contact in a business scenario.</span></span> <span data-ttu-id="3570c-105">El eje Y del gráfico representa el beneficio, en tanto que el eje X representa el porcentaje de la población con la que la empresa se ha puesto en contacto.</span><span class="sxs-lookup"><span data-stu-id="3570c-105">The Y-axis of the chart represents the profit, while the X-axis represents the percentage of the population that the company contacted.</span></span> <span data-ttu-id="3570c-106">Un gráfico de beneficios típico muestra un incremento en los beneficios hasta un determinado punto, después del cual los beneficios disminuyen a medida que crece la población con la que se entra en contacto.</span><span class="sxs-lookup"><span data-stu-id="3570c-106">A typical profit chart shows an increase in profits up to a point, after which profits decrease as more of the population is contacted.</span></span>  
  
## <a name="configuring-the-profit-chart"></a><span data-ttu-id="3570c-107">Configurar el gráfico de beneficios</span><span class="sxs-lookup"><span data-stu-id="3570c-107">Configuring the Profit Chart</span></span>  
 <span data-ttu-id="3570c-108">Mientras que el gráfico de precisión evalúa sólo la probabilidad de que las predicciones sean correctas o incorrectas, el gráfico de beneficios incorpora datos reales sobre las consecuencias de actuar en función de una predicción.</span><span class="sxs-lookup"><span data-stu-id="3570c-108">Whereas the accuracy chart assesses only the probability that predictions are right or wrong, the profit chart incorporates real-world knowledge about the consequences of taking action on a prediction.</span></span> <span data-ttu-id="3570c-109">Esto se consigue teniendo en cuenta los factores siguientes, que se especifican al ejecutar el asistente:</span><span class="sxs-lookup"><span data-stu-id="3570c-109">This is achieved by taking into account the following factors, which you specify when you run the wizard:</span></span>  
  
-   <span data-ttu-id="3570c-110">**Llenado**</span><span class="sxs-lookup"><span data-stu-id="3570c-110">**Population**</span></span>  
  
     <span data-ttu-id="3570c-111">Número de casos del conjunto de datos que se utiliza para crear el gráfico de elevación.</span><span class="sxs-lookup"><span data-stu-id="3570c-111">The number of cases in the dataset that is being used to create the lift chart.</span></span> <span data-ttu-id="3570c-112">Por ejemplo, el número de clientes potenciales.</span><span class="sxs-lookup"><span data-stu-id="3570c-112">For example, the number of potential customers.</span></span>  
  
-   <span data-ttu-id="3570c-113">**Costo fijo**</span><span class="sxs-lookup"><span data-stu-id="3570c-113">**Fixed Cost**</span></span>  
  
     <span data-ttu-id="3570c-114">Costo fijo asociado con el problema de la empresa.</span><span class="sxs-lookup"><span data-stu-id="3570c-114">The fixed cost that is associated with the business problem.</span></span> <span data-ttu-id="3570c-115">Si se calculase para una solución de correo directo, el costo no dependería de variables como el número de llamadas telefónicas o el número de envíos de correo promocional.</span><span class="sxs-lookup"><span data-stu-id="3570c-115">If this were for a targeted mailing solution, the cost would not depend on variables such as the number of telephone calls made or the number of promotional mailings sent.</span></span>  
  
-   <span data-ttu-id="3570c-116">**Costo individual**</span><span class="sxs-lookup"><span data-stu-id="3570c-116">**Individual Cost**</span></span>  
  
     <span data-ttu-id="3570c-117">Costos adicionales al costo fijo y que se pueden asociar con cada contacto con el cliente.</span><span class="sxs-lookup"><span data-stu-id="3570c-117">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="3570c-118">Por ejemplo, el correo promocional o las llamadas de teléfono.</span><span class="sxs-lookup"><span data-stu-id="3570c-118">For example, promotional mailings or telephone calls.</span></span>  
  
-   <span data-ttu-id="3570c-119">**Ingresos por individuo**</span><span class="sxs-lookup"><span data-stu-id="3570c-119">**Revenue Per Individual**</span></span>  
  
     <span data-ttu-id="3570c-120">Cantidad de ingresos asociados con cada venta realizada con éxito.</span><span class="sxs-lookup"><span data-stu-id="3570c-120">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="using-the-profit-chart-wizard"></a><span data-ttu-id="3570c-121">Usar el Asistente para gráfico de beneficios</span><span class="sxs-lookup"><span data-stu-id="3570c-121">Using the Profit Chart Wizard</span></span>  
 <span data-ttu-id="3570c-122">Para crear un gráfico de beneficios, se debe hacer referencia a un modelo de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="3570c-122">To create a profit chart, you must reference an existing data mining model.</span></span> <span data-ttu-id="3570c-123">Puede examinar los modelos para buscar un modelo que coincida con los datos haciendo clic en **administrar modelos** o en **examinar** para ver detalles sobre el algoritmo que se usó y las columnas del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3570c-123">You can browse models to find a model that matches your data by clicking **Manage Models** or **Browse** to see details about the algorithm that was used and the columns in the mining model.</span></span>  
  
 <span data-ttu-id="3570c-124">Para obtener más información, vea [examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) y [administrar modelos &#40;SQL Server complementos de minería de datos&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="3570c-124">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) and [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
#### <a name="to-create-a-profit-chart"></a><span data-ttu-id="3570c-125">Para crear un gráfico de beneficios</span><span class="sxs-lookup"><span data-stu-id="3570c-125">To create a profit chart</span></span>  
  
1.  <span data-ttu-id="3570c-126">Seleccione un modelo existente.</span><span class="sxs-lookup"><span data-stu-id="3570c-126">Select an existing model.</span></span>  
  
2.  <span data-ttu-id="3570c-127">Especifique la columna que desea predecir y, si es necesario, un valor de destino.</span><span class="sxs-lookup"><span data-stu-id="3570c-127">Specify the column that you want to predict, and a target value, if appropriate.</span></span>  
  
3.  <span data-ttu-id="3570c-128">Seleccione los datos de origen, que son los datos que se pasarán a través del modelo para crear una predicción.</span><span class="sxs-lookup"><span data-stu-id="3570c-128">Select the source data, which means the data you will pass through the model in order to create a prediction.</span></span> <span data-ttu-id="3570c-129">No deben ser los mismos datos que se usaron para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="3570c-129">This should not be the same data that you used to create the model.</span></span>  
  
4.  <span data-ttu-id="3570c-130">Asigne las columnas de los nuevos datos (de origen) a las columnas utilizadas en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3570c-130">Map the columns in the new (source) date to the columns used in the data mining model.</span></span> <span data-ttu-id="3570c-131">Si los nombres de las columnas son similares, el asistente hará la asignación automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3570c-131">If the column names are similar, the wizard will automatically map them.</span></span>  
  
5.  <span data-ttu-id="3570c-132">Especifique la información de costo que requiere el asistente: el costo fijo, el costo individual, la población y los ingresos esperados.</span><span class="sxs-lookup"><span data-stu-id="3570c-132">Enter the cost information required by the wizard: the fixed cost, individual cost, the population, and the revenue expected.</span></span>  
  
6.  <span data-ttu-id="3570c-133">Opcionalmente, puede especificar una serie graduada de costos (haga clic en el botón examinar **(...)** ).</span><span class="sxs-lookup"><span data-stu-id="3570c-133">Optionally, you can enter a graduated series of costs (click the browse **(...)** button).</span></span> <span data-ttu-id="3570c-134">Por ejemplo, una campaña de correo puede ser más económica a medida que aumenta el número de elementos enviados, por lo que puede especificarse un costo diferente en función del número de elementos, y el asistente ajustará automáticamente los costos para cada tamaño de muestra.</span><span class="sxs-lookup"><span data-stu-id="3570c-134">For example, a mailing might become cheaper as you increase the number of items that are sent, so you can enter a different cost depending on the number of items, and the wizard will automatically adjust the costs for each sample size.</span></span>  
  
7.  <span data-ttu-id="3570c-135">El asistente crea un gráfico que incluye el análisis de costos y beneficios para el modelo.</span><span class="sxs-lookup"><span data-stu-id="3570c-135">The wizard creates a chart that includes the cost-benefit analysis for the model.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="3570c-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3570c-136">Requirements</span></span>  
 <span data-ttu-id="3570c-137">Si se va a predecir un valor numérico discreto, debe seleccionarse el valor de destino exacto que se desea predecir.</span><span class="sxs-lookup"><span data-stu-id="3570c-137">If you are predicting a discrete numeric value, you must select the exact target value to predict.</span></span>  
  
## <a name="understanding-the-profit-chart"></a><span data-ttu-id="3570c-138">Descripción del gráfico de beneficios</span><span class="sxs-lookup"><span data-stu-id="3570c-138">Understanding the Profit Chart</span></span>  
 <span data-ttu-id="3570c-139">El gráfico de beneficios contiene una línea vertical gris que puede desplazar haciendo clic en una ubicación del gráfico.</span><span class="sxs-lookup"><span data-stu-id="3570c-139">The profit chart contains a gray vertical line, which you can move by clicking a location in the chart.</span></span> <span data-ttu-id="3570c-140">La **leyenda de minería de datos** muestra una puntuación, la población correcta y la probabilidad de predicción que están asociadas a la ubicación de la línea gris en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3570c-140">The **Mining Legend** displays a score, the population correct, and the predict probability that are associated with the location of the gray line on the chart.</span></span> <span data-ttu-id="3570c-141">Si selecciona el punto máximo de beneficios en el gráfico utilizando la línea gris, puede usar el valor de probabilidad de predicción para determinar un umbral de probabilidad para el contacto con un cliente.</span><span class="sxs-lookup"><span data-stu-id="3570c-141">If you select the maximum point of profits in the chart by using the gray line, you can use the predict probability value to determine a probability threshold for contacting a customer.</span></span>  
  
 <span data-ttu-id="3570c-142">Por ejemplo, si el máximo de la curva de beneficios está en el 55 por ciento de la población y la probabilidad de predicción asociada es del 20 por ciento, esto indica que para conseguir los máximos beneficios sólo debe ponerse en contacto con aquellos clientes cuya respuesta se predice con una probabilidad del 20 por ciento o superior.</span><span class="sxs-lookup"><span data-stu-id="3570c-142">For example, if the peak of the profit curve is at 55 percent of the population and the associated predict probability is 20 percent, this indicates that to achieve maximum profits you should only contact those customers whose response is predicted with a 20 percent or greater probability.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3570c-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3570c-143">See Also</span></span>  
 [<span data-ttu-id="3570c-144">Validar modelos y usar modelos para la predicción &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3570c-144">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
