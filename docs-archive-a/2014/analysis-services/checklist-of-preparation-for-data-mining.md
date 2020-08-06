---
title: Lista de comprobación de preparación para la minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e056c95-ba06-413e-8dc1-4d411a447c3b
author: minewiskan
ms.author: owend
ms.openlocfilehash: e37b1adb6aebe5d5f8fd23f5289f52425f752a6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670700"
---
# <a name="checklist-of-preparation-for-data-mining"></a><span data-ttu-id="eb558-102">Lista de comprobación de la preparación para la minería de datos</span><span class="sxs-lookup"><span data-stu-id="eb558-102">Checklist of Preparation for Data Mining</span></span>
  <span data-ttu-id="eb558-103">Pese a que los complementos de minería de datos facilitan y hacen más agradable la creación de modelos y la experimentación con los mismos, cuando se necesita obtener resultados repetibles y procesables, se debe prever un periodo adecuado para la formulación de requisitos de negocio básicos y para la obtención y preparación de los datos.</span><span class="sxs-lookup"><span data-stu-id="eb558-103">Although the Data Mining Add-ins make it fairly easy and fun to create and experiment with models, when you need to get repeatable, actionable results, you must allow adequate time for formulating basic business requirements, and for obtaining and preparing data.</span></span> <span data-ttu-id="eb558-104">En esta sección encontrará una lista de comprobación para ayudarle a planear la investigación, así como descripciones de los problemas comunes.</span><span class="sxs-lookup"><span data-stu-id="eb558-104">This section provides a checklist to help you plan your investigation, and describes common problems.</span></span>  
  
## <a name="checklist-of-data-preparation"></a><span data-ttu-id="eb558-105">Lista de comprobación para la preparación de datos</span><span class="sxs-lookup"><span data-stu-id="eb558-105">Checklist of Data Preparation</span></span>  
 <span data-ttu-id="eb558-106">**He identificado un resultado claramente definido.**</span><span class="sxs-lookup"><span data-stu-id="eb558-106">**I have identified a clearly defined output.**</span></span>  
 <span data-ttu-id="eb558-107">Prepare un plan sobre el modo en que utilizará los resultados.</span><span class="sxs-lookup"><span data-stu-id="eb558-107">Have a plan for how you will use the results.</span></span> <span data-ttu-id="eb558-108">Cada tipo de modelo tiene su propia salida.</span><span class="sxs-lookup"><span data-stu-id="eb558-108">Different types of models have different outputs.</span></span> <span data-ttu-id="eb558-109">Un modelo de serie temporal genera los valores de una serie en el futuro, que pueden entenderse y procesarse fácilmente.</span><span class="sxs-lookup"><span data-stu-id="eb558-109">A time series model generates values for a series in the future, which are easily understood and acted on.</span></span> <span data-ttu-id="eb558-110">Otros modelos generan conjuntos complejos que deben analizar los expertos en la materia para producir el máximo valor.</span><span class="sxs-lookup"><span data-stu-id="eb558-110">Other models generate complex sets that must be analyzed by subject matter experts to yield the most value.</span></span>  
  
-   <span data-ttu-id="eb558-111">¿Qué salida desea?</span><span class="sxs-lookup"><span data-stu-id="eb558-111">What output do you want?</span></span>  
  
-   <span data-ttu-id="eb558-112">¿Puede definir salida como una sola columna o valor, u otro resultado procesable?</span><span class="sxs-lookup"><span data-stu-id="eb558-112">Can you define the output as a single column or value, or other actionable result?</span></span>  
  
-   <span data-ttu-id="eb558-113">¿Cuáles son los criterios para saber que el modelo fue útil?</span><span class="sxs-lookup"><span data-stu-id="eb558-113">What are your criteria for knowing that the model was useful?</span></span>  
  
-   <span data-ttu-id="eb558-114">¿Cómo utilizará e interpretará los resultados?</span><span class="sxs-lookup"><span data-stu-id="eb558-114">How will you use and interpret those results?</span></span>  
  
-   <span data-ttu-id="eb558-115">¿Puede asignar datos de entrada nuevos a los resultados esperados?</span><span class="sxs-lookup"><span data-stu-id="eb558-115">Can you map new input data to the expected results?</span></span>  
  
 <span data-ttu-id="eb558-116">**Conozco el significado, los tipos de datos y la distribución de los datos de entrada.**</span><span class="sxs-lookup"><span data-stu-id="eb558-116">**I know the meaning, data types, and distribution of the input data.**</span></span>  
 <span data-ttu-id="eb558-117">Tómese un tiempo para explorar y comprender los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="eb558-117">Take some time to explore and understand your source data.</span></span> <span data-ttu-id="eb558-118">Es importante que las personas que revisen el modelo conozcan el tipo de datos de entrada que se usaron y sepan cómo interpretar los tipos de datos y la variabilidad, así como el equilibrio y la calidad.</span><span class="sxs-lookup"><span data-stu-id="eb558-118">It is important that people who review the model understand what kind of input data was used and know how to interpret the data types and the variability, as well as the balance and the quality.</span></span>  
  
-   <span data-ttu-id="eb558-119">¿Cuántos datos tiene?</span><span class="sxs-lookup"><span data-stu-id="eb558-119">How much data do you have?</span></span> <span data-ttu-id="eb558-120">¿Hay suficientes datos para el modelado?</span><span class="sxs-lookup"><span data-stu-id="eb558-120">Is there sufficient data for modeling?</span></span>  
  
     <span data-ttu-id="eb558-121">No es necesario que sea una cantidad enorme: más pequeña y equilibrada puede ser mejor.</span><span class="sxs-lookup"><span data-stu-id="eb558-121">It need not be a huge amount - smaller and balanced can be better.</span></span>  
  
-   <span data-ttu-id="eb558-122">¿Proceden los datos de varios orígenes, o de uno solo?</span><span class="sxs-lookup"><span data-stu-id="eb558-122">Is the data from multiple sources, or a single source?</span></span>  
  
-   <span data-ttu-id="eb558-123">¿Están los datos ya procesados y limpios?</span><span class="sxs-lookup"><span data-stu-id="eb558-123">Is the data already processed and clean?</span></span> <span data-ttu-id="eb558-124">¿Hay más datos de entrada disponibles?</span><span class="sxs-lookup"><span data-stu-id="eb558-124">Is more input data available?</span></span>  
  
-   <span data-ttu-id="eb558-125">¿Sabe cómo se ha manipulado antes de recibirlo? ¿cómo se pueden truncar, resumir o convertir los datos?</span><span class="sxs-lookup"><span data-stu-id="eb558-125">Do you know how it was manipulated before you received it - how data might have been truncated, summarized, or converted?</span></span>  
  
-   <span data-ttu-id="eb558-126">¿Tienen los datos de entrada algunos resultados de ejemplo que se pueden utilizar para el entrenamiento?</span><span class="sxs-lookup"><span data-stu-id="eb558-126">Does the input data have some example results that can be used for training?</span></span>  
  
 <span data-ttu-id="eb558-127">**Comprendo cuál es el nivel de integridad de los datos que tenemos y el nivel que necesitamos.**</span><span class="sxs-lookup"><span data-stu-id="eb558-127">**I understand the level of data integrity we have and the level we need.**</span></span>  
 <span data-ttu-id="eb558-128">Los datos incorrectos pueden afectar a la calidad del modelo, o impedir que este se genere.</span><span class="sxs-lookup"><span data-stu-id="eb558-128">Bad data can affect the quality of the model, or prevent the model from being built at all.</span></span> <span data-ttu-id="eb558-129">Debe contar con un buen conocimiento de la distribución y del significado de los datos, y saber cómo llegaron a este estado.</span><span class="sxs-lookup"><span data-stu-id="eb558-129">You should have a good understanding of both the distribution and meaning of the data, and how it came to this state.</span></span> <span data-ttu-id="eb558-130">Deberá saber si es posible o adecuado simplificar los datos mediante el etiquetado, el truncamiento de tipos de datos numéricos o la resumir.</span><span class="sxs-lookup"><span data-stu-id="eb558-130">You'll need to understand if it is possible or appropriate to simplify the data by labeling, truncating numeric data types, or by summarizing.</span></span>  
  
-   <span data-ttu-id="eb558-131">Etiquetas de datos: ¿son claras y correctas?</span><span class="sxs-lookup"><span data-stu-id="eb558-131">Data labels: are they clear and correct?</span></span>  
  
-   <span data-ttu-id="eb558-132">Tipos de datos: ¿son apropiados y se han modificado?</span><span class="sxs-lookup"><span data-stu-id="eb558-132">Data types: are they appropriate, and have they been changed?</span></span>  
  
-   <span data-ttu-id="eb558-133">¿Ha ordenado, limpiado o descartado datos incorrectos?</span><span class="sxs-lookup"><span data-stu-id="eb558-133">Have you sorted, cleaned up, or discarded wrong data?</span></span>  
  
     <span data-ttu-id="eb558-134">¿Ha comprobado que no haya duplicados?</span><span class="sxs-lookup"><span data-stu-id="eb558-134">Have you verified there are no duplicates?</span></span>  
  
-   <span data-ttu-id="eb558-135">¿Cómo trataría las situaciones donde faltan valores?</span><span class="sxs-lookup"><span data-stu-id="eb558-135">How will you handle missing values?</span></span> <span data-ttu-id="eb558-136">¿Qué indica la falta de valores?</span><span class="sxs-lookup"><span data-stu-id="eb558-136">Do missing values have a meaning?</span></span>  
  
-   <span data-ttu-id="eb558-137">¿Ha comprobado los orígenes para ver si se han podido introducir errores durante el proceso de importación?</span><span class="sxs-lookup"><span data-stu-id="eb558-137">Have you verified the sources to see if any errors might have been introduced in the import process?</span></span>  
  
     <span data-ttu-id="eb558-138">¿Dónde está almacenada la entrada?</span><span class="sxs-lookup"><span data-stu-id="eb558-138">Where is the input stored?</span></span> <span data-ttu-id="eb558-139">¿Cuánto tiempo estará disponible?</span><span class="sxs-lookup"><span data-stu-id="eb558-139">How long does it stay available?</span></span>  
  
     <span data-ttu-id="eb558-140">¿Existe un diccionario de datos?</span><span class="sxs-lookup"><span data-stu-id="eb558-140">Is there a data dictionary?</span></span> <span data-ttu-id="eb558-141">¿Puede crear uno?</span><span class="sxs-lookup"><span data-stu-id="eb558-141">Can you create one?</span></span>  
  
-   <span data-ttu-id="eb558-142">¿Si combinó conjuntos de datos, comprobó si había varias columnas que representaban los mismos datos?</span><span class="sxs-lookup"><span data-stu-id="eb558-142">If you combined data sets, did you check for multiple columns representing the same data?</span></span>  
  
 <span data-ttu-id="eb558-143">**Sé dónde se almacenan los datos de origen, de dónde proceden y cómo se procesan. El proceso puede repetirse fácilmente si es necesario.**</span><span class="sxs-lookup"><span data-stu-id="eb558-143">**I know where source data is stored, where it came from, and how it is processed. The process can be easily repeated if needed.**</span></span>  
 <span data-ttu-id="eb558-144">Los conjuntos de datos de un solo uso son correctos para los experimentos, pero si alguna vez desea trasladar el modelo a producción, querrá pensar de antemano en cómo se puede aplicar el proceso de limpieza a los datos operativos.</span><span class="sxs-lookup"><span data-stu-id="eb558-144">One-off data sets are fine for experiments, but if you ever want to move the model into production, you'll want to think in advance about how the cleaning process can be applied to operational data.</span></span> <span data-ttu-id="eb558-145">Además, si tiene datos operativos, debe saber cómo se han modificado antes de que lo haya hecho; deberá saber cómo se redondeó, o resume, con certeza.</span><span class="sxs-lookup"><span data-stu-id="eb558-145">Also, if you have operational data, you need to know how it might have been altered before you got it-you'll need to know how it was rounded, or summarized, certainly.</span></span>  
  
-   <span data-ttu-id="eb558-146">¿Desea poder repetir el experimento?</span><span class="sxs-lookup"><span data-stu-id="eb558-146">Do you want to be able to repeat the experiment?</span></span>  
  
-   <span data-ttu-id="eb558-147">¿Qué herramientas utilizaría para preparar datos en un formato que admita el análisis de datos?</span><span class="sxs-lookup"><span data-stu-id="eb558-147">What tools will you use to prepare data in a format that supports data analysis?</span></span> <span data-ttu-id="eb558-148">¿Se pueden automatizar las operaciones de revisión y limpieza o se necesita a alguien para realizarlas en Excel?</span><span class="sxs-lookup"><span data-stu-id="eb558-148">Can it be automated or do you need someone to review and clean up in Excel?</span></span>  
  
-   <span data-ttu-id="eb558-149">Si los datos proceden de otro sistema, ¿podrá capturar y hacer el seguimiento de los filtros que se aplicaron?</span><span class="sxs-lookup"><span data-stu-id="eb558-149">If you are sourcing data from another system, will you be able to capture and track filters that were applied?</span></span>  
  
-   <span data-ttu-id="eb558-150">¿Puede aplicar también el marco de procesamiento de datos algoritmos de aprendizaje automático, realizar pruebas y visualizar resultados?</span><span class="sxs-lookup"><span data-stu-id="eb558-150">Can your data processing framework also apply machine learning algorithms, perform tests, and visualize results?</span></span>  
  
 <span data-ttu-id="eb558-151">**Ha habido acuerdo respecto a la granularidad deseada de las predicciones y nuestros datos se han modificado para generar esas unidades.**</span><span class="sxs-lookup"><span data-stu-id="eb558-151">**We have agreed on the desired granularity of predictions and our data has been modified to output those units.**</span></span>  
 <span data-ttu-id="eb558-152">Antes de preparar los datos, debe decidir cuál va a ser la granularidad de los resultados. Por ejemplo, debe indicar si desea que los pronósticos de ventas sean por día o por trimestre.</span><span class="sxs-lookup"><span data-stu-id="eb558-152">Decide on the granularity of the results you want before preparing data, For example, do you want sales predictions by the day, or for each quarter?</span></span> <span data-ttu-id="eb558-153">Puede considerar la posibilidad de configurar diferentes estructuras de datos para los mismos datos con objeto de controlar distintos niveles de resumen.</span><span class="sxs-lookup"><span data-stu-id="eb558-153">You might consider setting up different data structures for the same data, to handle different levels of summary.</span></span>  
  
-   <span data-ttu-id="eb558-154">¿Cuál es la unidad de medida o la unidad de tiempo actual?</span><span class="sxs-lookup"><span data-stu-id="eb558-154">What is the current unit of measure or unit of time?</span></span>  
  
     <span data-ttu-id="eb558-155">¿Qué unidad desea usar en los resultados?</span><span class="sxs-lookup"><span data-stu-id="eb558-155">What unit do you want to use in the results?</span></span>  
  
-   <span data-ttu-id="eb558-156">¿Es posible definir una unidad básica (por ejemplo, día/hora/minuto/llamada de instrucción) para todos los datos de entrada?</span><span class="sxs-lookup"><span data-stu-id="eb558-156">Is it possible to define a basic unit (e.g. day/ hour / min / instruction call) for all input data?</span></span>  
  
     <span data-ttu-id="eb558-157">¿Desea resumirlos en unidades de mayor nivel?</span><span class="sxs-lookup"><span data-stu-id="eb558-157">Do you want to rollup to higher units?</span></span>  
  
-   <span data-ttu-id="eb558-158">¿Están etiquetadas las categorías de forma coherente?</span><span class="sxs-lookup"><span data-stu-id="eb558-158">Are categories labeled consistently?</span></span> <span data-ttu-id="eb558-159">¿Es fácil agregar o quitar categorías?</span><span class="sxs-lookup"><span data-stu-id="eb558-159">Is it easy to add or remove categories?</span></span>  
  
 <span data-ttu-id="eb558-160">**Nuestro diseño experimental es repetible y reproducible.**</span><span class="sxs-lookup"><span data-stu-id="eb558-160">**Our experimental design is repeatable and reproducible.**</span></span>  
 <span data-ttu-id="eb558-161">Considere las estrategias para analizar y validar los resultados y cree un plan para capturar una instantánea de los datos que le permitirá asegurarse de que puede correlacionar los efectos con los datos.</span><span class="sxs-lookup"><span data-stu-id="eb558-161">Consider strategies for analyzing and validating your results and plan to capture a data snapshot, to make sure you can trace back effects to data.</span></span> <span data-ttu-id="eb558-162">Si utiliza un valor de inicialización aleatorio, los resultados pueden diferir ligeramente.</span><span class="sxs-lookup"><span data-stu-id="eb558-162">If a random seed is used, the results can differ subtly.</span></span> <span data-ttu-id="eb558-163">Esto puede dificultar la comparación y validación de modelos.</span><span class="sxs-lookup"><span data-stu-id="eb558-163">This can make it difficult to compare and validate models.</span></span>  
  
-   <span data-ttu-id="eb558-164">¿Si realiza muchos cambios personalizados en los datos, qué sucede la próxima vez desea generar el modelo?</span><span class="sxs-lookup"><span data-stu-id="eb558-164">If you make a lot of custom changes to the data, what happens the next time you want to build the model?</span></span>  
  
-   <span data-ttu-id="eb558-165">¿Se ha definido previamente un procedimiento manual o un proceso aprobado que se debe usar para procesar la entrada y obtener los resultados deseados?</span><span class="sxs-lookup"><span data-stu-id="eb558-165">Has a manual procedure or approved process already been defined that you should use to process input and get the desired outputs?</span></span>  
  
-   <span data-ttu-id="eb558-166">¿Ha decidido usar un valor de inicialización para el modelo?</span><span class="sxs-lookup"><span data-stu-id="eb558-166">Have you decided to use a seed for the model?</span></span>  
  
 <span data-ttu-id="eb558-167">**Disponemos de un conocimiento del dominio para validar los resultados, o disponemos de acceso a los expertos de contenido que nos pueden aconsejar.**</span><span class="sxs-lookup"><span data-stu-id="eb558-167">**We have the domain knowledge to validate the results, or have access to subject matter experts who can advise.**</span></span>  
 <span data-ttu-id="eb558-168">Emplee tiempo en validar las variables, el modelo y los resultados.</span><span class="sxs-lookup"><span data-stu-id="eb558-168">Take time to validate the variables, the model, and the results.</span></span> <span data-ttu-id="eb558-169">Pida ayuda a los expertos para evaluar las interacciones y los resultados.</span><span class="sxs-lookup"><span data-stu-id="eb558-169">Get the help of experts to assess interactions and results.</span></span> <span data-ttu-id="eb558-170">Sin embargo, no permita que las suposiciones impongan evidencias.</span><span class="sxs-lookup"><span data-stu-id="eb558-170">However, don't let assumptions overrule evidence.</span></span> <span data-ttu-id="eb558-171">Esté abierto a los hallazgos nuevos e inesperados.</span><span class="sxs-lookup"><span data-stu-id="eb558-171">Be open to new and unexpected findings.</span></span>  
  
-   <span data-ttu-id="eb558-172">¿Existe conocimiento del dominio disponible para ayudar a filtrar los datos y a reducir el ruido en la entrada?</span><span class="sxs-lookup"><span data-stu-id="eb558-172">Is domain knowledge available to help in filtering data and reducing input noise?</span></span>  
  
-   <span data-ttu-id="eb558-173">¿Pueden los expertos del dominio ayudar a interpretar los resultados y sugerir mejoras?</span><span class="sxs-lookup"><span data-stu-id="eb558-173">Can domain experts help understand interpret the results and suggest improvements?</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb558-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb558-174">See Also</span></span>  
 [<span data-ttu-id="eb558-175">Elegir datos para minería de datos</span><span class="sxs-lookup"><span data-stu-id="eb558-175">Choosing Data for Data Mining</span></span>](choosing-data-for-data-mining.md)  
  
  
