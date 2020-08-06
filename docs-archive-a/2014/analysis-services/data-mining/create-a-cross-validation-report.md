---
title: Crear un informe de validación cruzada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- validating data mining models
- mining structures [Analysis Services], how-to topics
- cross-validation [data mining]
- statistical standard deviation
ms.assetid: 7b1fec4c-7053-41eb-b030-5179257967a4
author: minewiskan
ms.author: owend
ms.openlocfilehash: ccbafe63b0026cd45a15ea71fd84e223c1b32a9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743697"
---
# <a name="create-a-cross-validation-report"></a><span data-ttu-id="6c8f3-102">Crear un informe de validación cruzada</span><span class="sxs-lookup"><span data-stu-id="6c8f3-102">Create a Cross-Validation Report</span></span>
  <span data-ttu-id="6c8f3-103">Este tema le guía a través del proceso de creación de un informe de validación cruzada utilizando la pestaña Gráfico de precisión del Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-103">This topic walks you through creation of a cross-validation report using the Accuracy Chart tab in Data Mining Designer.</span></span> <span data-ttu-id="6c8f3-104">Para obtener información general sobre el aspecto de un informe de validación cruzada y sobre las medidas estadísticas que se incluyen en este, vea [Validación cruzada &#40;Analysis Services - Minería de datos&#41;](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6c8f3-104">For general information about what a cross-validation report looks like, and the statistical measures it includes, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="6c8f3-105">Un informe de validación cruzada es totalmente diferente de un gráfico de precisión, como un gráfico de mejora respecto al modelo predictivo o una matriz de clasificación.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-105">A cross-validation report is fundamentally different from an accuracy chart, such as a lift chart or classification matrix.</span></span>  
  
-   <span data-ttu-id="6c8f3-106">La validación cruzada evalúa la distribución global de los datos utilizados en un modelo o una estructura; por lo tanto, no es necesario especificar un conjunto de datos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-106">Cross-validation assesses the overall distribution of data that is used in a model or structure; therefore, you do not specify a testing data set.</span></span> <span data-ttu-id="6c8f3-107">La validación cruzada utiliza siempre únicamente los datos originales que se utilizaron para entrenar al modelo o a la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-107">Cross-validation always uses only the original data that was used to train the model or the mining structure.</span></span>  
  
-   <span data-ttu-id="6c8f3-108">Este tipo de validación solo se puede realizar con respecto a un único resultado de predicción.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-108">Cross-validation can only be performed with respect to a single predictable outcome.</span></span> <span data-ttu-id="6c8f3-109">Si la estructura admite modelos con atributos de predicción diferentes, deberá crear informes independientes para cada resultado de predicción.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-109">If the structure supports models that have different predictable attributes, you must create separate reports for each predictable output.</span></span>  
  
-   <span data-ttu-id="6c8f3-110">Solo los modelos que se relacionan con la estructura seleccionada actualmente están disponibles para la validación cruzada.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-110">Only models that are related to the currently selected structure are available for cross-validation.</span></span>  
  
-   <span data-ttu-id="6c8f3-111">Si la estructura que está seleccionada actualmente admite una combinación de modelos de agrupación en clústeres y de no agrupación en clústeres, al hacer clic en **Obtener resultados**, el procedimiento almacenado de validación cruzada cargará automáticamente los modelos que tengan la misma columna predicha y omitirá los modelos de agrupación en clústeres que no compartan el mismo atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-111">If the structure that is currently selected supports a combination of clustering and non-clustering models, when you click **Get Results**, the cross-validation stored procedure will automatically load models that have the same predicted column, and ignore clustering models that do not share the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="6c8f3-112">Solo podrá crear un informe de validación cruzada en un modelo de agrupación en clústeres que no tenga un atributo de predicción si la estructura de minería de datos no admite ningún otro atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-112">You can create a cross-validation report on a clustering model that does not have a predictable attribute only if the mining structure does not support any other predictable attributes.</span></span>  
  
### <a name="select-a-mining-structure"></a><span data-ttu-id="6c8f3-113">Seleccionar una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6c8f3-113">Select a mining structure</span></span>  
  
1.  <span data-ttu-id="6c8f3-114">Abra el Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c8f3-114">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="6c8f3-115">En el Explorador de soluciones, abra la base de datos que contiene la estructura o el modelo para el que desea crear un informe.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-115">In Solution Explorer, open the database that contains the structure or model for which you want to create a report.</span></span>  
  
3.  <span data-ttu-id="6c8f3-116">Haga doble clic en la estructura de minería de datos para abrir la estructura y sus modelos relacionados en el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-116">Double-click the mining structure to open the structure and its related models in Data Mining Designer.</span></span>  
  
4.  <span data-ttu-id="6c8f3-117">Haga clic en la pestaña **Gráfico de precisión de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="6c8f3-117">Click the **Mining Accuracy Chart** tab.</span></span>  
  
5.  <span data-ttu-id="6c8f3-118">Haga clic en la pestaña **Validación cruzada** .</span><span class="sxs-lookup"><span data-stu-id="6c8f3-118">Click the **Cross Validation** tab.</span></span>  
  
### <a name="set-cross-validation-options"></a><span data-ttu-id="6c8f3-119">Establecer opciones de validación cruzada</span><span class="sxs-lookup"><span data-stu-id="6c8f3-119">Set cross-validation options</span></span>  
  
1.  <span data-ttu-id="6c8f3-120">En la pestaña **Validación cruzada** , en **Recuento de plegamientos**, haga clic en la flecha abajo para seleccionar un número entre 1 y 10.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-120">On the **Cross Validation** tab, for **Fold Count**, click the down arrow to select a number between 1 and 10.</span></span> <span data-ttu-id="6c8f3-121">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-121">The default value is 10.</span></span>  
  
     <span data-ttu-id="6c8f3-122">El **Recuento de plegamientos** representa el número de particiones que se creará dentro del conjunto de datos original.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-122">The **Fold Count** represents the number of partitions that will be created within the original data set.</span></span> <span data-ttu-id="6c8f3-123">Si establece Recuento de plegamientos en 1, el conjunto de entrenamiento se utilizará sin particiones.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-123">If you set Fold Count to 1, the training set will be used without partitioning.</span></span>  
  
2.  <span data-ttu-id="6c8f3-124">En **Atributo de destino**, haga clic en la flecha abajo y seleccione una columna en la lista.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-124">For **Target Attribute**, click the down arrow, and select a column from the list.</span></span> <span data-ttu-id="6c8f3-125">Si el modelo es un modelo de agrupación en clústeres, seleccione **#Cluster** para indicar que el modelo no tiene un atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-125">If the model is a clustering model, select **#Cluster** to indicate that the model does not have a predictable attribute.</span></span> <span data-ttu-id="6c8f3-126">Tenga en cuenta que el valor **#Cluster**solo estará disponible si la estructura de minería de datos no admite otros tipos de atributos de predicción.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-126">Note that the value, **#Cluster**, is available only when the mining structure does not support other types of predictable attributes.</span></span>  
  
     <span data-ttu-id="6c8f3-127">Puede seleccionar solo un atributo de predicción para cada informe.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-127">You can select only one predictable attribute per report.</span></span> <span data-ttu-id="6c8f3-128">De forma predeterminada, todos los modelos relacionados que tienen el mismo atributo de predicción se incluyen en el informe.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-128">By default, all related models that have the same predictable attribute are included in the report.</span></span>  
  
3.  <span data-ttu-id="6c8f3-129">En **Máximo de casos**, escriba un número que sea suficientemente grande para proporcionar una muestra representativa de datos cuando los datos se dividen entre el número especificado de plegamientos.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-129">For **Max Cases**, type a number that is large enough to provide a representative sample of data when the data is split among the specified number of folds.</span></span> <span data-ttu-id="6c8f3-130">Si el número es mayor que el recuento de casos en el conjunto de entrenamiento del modelo, se utilizarán todos los casos.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-130">If the number is greater than the count of cases in the model training set, all cases will be used.</span></span>  
  
     <span data-ttu-id="6c8f3-131">Si el conjunto de datos de entrenamiento es muy grande, al establecer el valor de **Máximo de casos** se limita el número total de casos procesados y se permite que el informe finalice más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-131">If the training data set is very large, setting the value for **Max Cases** limits the total number of cases processed, and lets the report finish faster.</span></span> <span data-ttu-id="6c8f3-132">Pero no establezca el valor de **Máximo de casos** en un valor demasiado bajo, ya que es posible que no haya datos suficientes para la validación cruzada.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-132">However, you should not set **Max Cases** too low or there may be insufficient data for cross-validation.</span></span>  
  
4.  <span data-ttu-id="6c8f3-133">Si lo desea, en **Estado de destino**, escriba el valor del atributo de predicción que desea modelar.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-133">Optionally, for **Target State**, type the value of the predictable attribute that you want to model.</span></span> <span data-ttu-id="6c8f3-134">Por ejemplo, si la columna [Bike Buyer] tiene dos valores posibles, 1 (Sí) y 2 (No), puede especificar el valor 1 para evaluar la exactitud del modelo solo para el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-134">For example, if the column [Bike Buyer] has two possible values, 1 (Yes) and 2 (No), you can enter the value 1 to assess the accuracy of the model for just the desired outcome.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6c8f3-135"> Si no especifica un valor, la opción **Umbral de destino** no está disponible y el modelo se evalúa para todos los valores posibles del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-135">If you do not enter a value, the **Target Threshold** option is not available, and the model is assessed for all possible values of the predictable attribute.</span></span>  
  
5.  <span data-ttu-id="6c8f3-136">Opcionalmente, en **Umbral de destino**, escriba un número decimal comprendido entre 0 y 1 para especificar la probabilidad mínima que una predicción debe tener para que se considere que es precisa.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-136">Optionally, for **Target Threshold**, type a decimal number between 0 and 1 to specify the minimum probability that a prediction must have to be counted as accurate.</span></span>  
  
     <span data-ttu-id="6c8f3-137">Para más información sobre cómo establecer los umbrales de probabilidad, vea [Medidas en el informe de validación cruzada](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="6c8f3-137">For additional tips about how to set probability thresholds, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
6.  <span data-ttu-id="6c8f3-138">Haga clic en **Obtener resultados**.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-138">Click **Get Results**.</span></span>  
  
### <a name="print-the-cross-validation-report"></a><span data-ttu-id="6c8f3-139">Imprimir el informe de validación cruzada</span><span class="sxs-lookup"><span data-stu-id="6c8f3-139">Print the cross-validation report</span></span>  
  
1.  <span data-ttu-id="6c8f3-140">Haga clic con el botón derecho en la pestaña **Validación cruzada** del informe completado.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-140">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="6c8f3-141">En el menú contextual, seleccione **Imprimir** o **Vista previa de impresión** para revisar el informe primero.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-141">In the shortcut menu, select **Print** or **Print Preview** to review the report first.</span></span>  
  
### <a name="create-a-copy-of-the-report-in-microsoft-excel"></a><span data-ttu-id="6c8f3-142">Crear una copia del informe en Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="6c8f3-142">Create a copy of the report in Microsoft Excel</span></span>  
  
1.  <span data-ttu-id="6c8f3-143">Haga clic con el botón derecho en la pestaña **Validación cruzada** del informe completado.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-143">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="6c8f3-144">En el menú contextual, seleccione **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-144">In the shortcut menu, select **Select All**.</span></span>  
  
3.  <span data-ttu-id="6c8f3-145">Haga clic con el botón derecho en el texto seleccionado y, después, haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-145">Right-click the selected text, and select **Copy**.</span></span>  
  
4.  <span data-ttu-id="6c8f3-146">Pegue la selección en un libro de Excel abierto.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-146">Paste the selection into an open Excel workbook.</span></span> <span data-ttu-id="6c8f3-147">Si utiliza la opción **Pegar** , el informe se pega en Excel como HTML, con lo que se conserva el formato de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-147">If you use the **Paste** option, the report is pasted into Excel as HTML, which preserves row and column formatting.</span></span> <span data-ttu-id="6c8f3-148">Si pega el informe con las opciones de **Pegado especial** para texto o texto Unicode, el informe se pegará con un formato delimitado por filas.</span><span class="sxs-lookup"><span data-stu-id="6c8f3-148">If you paste the report by using the **Paste Special** options for text or Unicode text, the report is pasted in row-delimited format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c8f3-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c8f3-149">See Also</span></span>  
 [<span data-ttu-id="6c8f3-150">Medidas en el informe de validación cruzada</span><span class="sxs-lookup"><span data-stu-id="6c8f3-150">Measures in the Cross-Validation Report</span></span>](measures-in-the-cross-validation-report.md)  
  
  
