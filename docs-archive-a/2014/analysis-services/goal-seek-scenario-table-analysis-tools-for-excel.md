---
title: Escenario de búsqueda de objetivos (herramientas de análisis de tabla para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3b4df4f78a2d3652b1dac3c566e66507b523ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671255"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="46604-102">Buscar objetivo (escenario de Herramientas de análisis de tabla para Excel)</span><span class="sxs-lookup"><span data-stu-id="46604-102">Goal Seek Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="46604-103">![Botón Buscar objetivo, Herramientas de análisis de tabla](media/tat-goalseek.gif "Botón Buscar objetivo, Herramientas de análisis de tabla")</span><span class="sxs-lookup"><span data-stu-id="46604-103">![Goal Seek button in Table Analysis tools](media/tat-goalseek.gif "Goal Seek button in Table Analysis tools")</span></span>  
  
 <span data-ttu-id="46604-104">La herramienta de escenario **Buscar objetivo** es complementaria a la herramienta escenario de [What if](what-if-scenario-table-analysis-tools-for-excel.md) .</span><span class="sxs-lookup"><span data-stu-id="46604-104">The **Goal Seek** scenario tool is complementary to the [What If](what-if-scenario-table-analysis-tools-for-excel.md) scenario tool.</span></span> <span data-ttu-id="46604-105">La herramienta **qué** le indica el impacto de realizar un cambio, mientras que la herramienta **Buscar objetivo** le indica los factores subyacentes que deben cambiar para lograr el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="46604-105">The **What-If** tool tells you the impact of making a change, whereas the **Goal Seek** tool tells you the underlying factors that must change to achieve a desired result.</span></span>  
  
 <span data-ttu-id="46604-106">Por ejemplo, supongamos que su objetivo es aumentar la satisfacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="46604-106">For example, let's say your goal is to increase customer satisfaction.</span></span> <span data-ttu-id="46604-107">Puede usar el análisis de **búsqueda de objetivo** para determinar qué factores serían más probables para aumentar la satisfacción del cliente y decidir si esos cambios son rentables.</span><span class="sxs-lookup"><span data-stu-id="46604-107">You can use **Goal Seek** analysis to determine which factors would be most likely to increase customer satisfaction, and decide whether those changes are cost-effective.</span></span>  
  
 <span data-ttu-id="46604-108">Cuando la herramienta finaliza su análisis, crea dos columnas nuevas en la tabla de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="46604-108">When the tool finishes its analysis, it creates two new columns in the source data table.</span></span> <span data-ttu-id="46604-109">Estas columnas muestran la *probabilidad* de que se pueda lograr el resultado de destino y el cambio recomendado, si existe.</span><span class="sxs-lookup"><span data-stu-id="46604-109">These columns show the *likelihood* that the targeted outcome can be achieved, and the recommended change, if any.</span></span>  
  
 <span data-ttu-id="46604-110">La herramienta puede analizar un conjunto de datos y hacer predicciones para el conjunto completo; también es posible crear el análisis y, a continuación, ir probando los escenarios de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="46604-110">The tool can analyze a set of data and make predictions for the entire set, or you can create the analysis and then test scenarios one at a time.</span></span>  
  
## <a name="using-the-goal-seek-scenario-tool"></a><span data-ttu-id="46604-111">Usar la herramienta de escenario Buscar objetivo</span><span class="sxs-lookup"><span data-stu-id="46604-111">Using the Goal Seek Scenario Tool</span></span>  
  
1.  <span data-ttu-id="46604-112">Abra una tabla de Excel.</span><span class="sxs-lookup"><span data-stu-id="46604-112">Open an Excel table.</span></span>  
  
2.  <span data-ttu-id="46604-113">Haga clic en **escenarios**y seleccione **Buscar objetivo**.</span><span class="sxs-lookup"><span data-stu-id="46604-113">Click **Scenarios**, and select **Goal Seek**.</span></span>  
  
3.  <span data-ttu-id="46604-114">En el cuadro de diálogo **análisis de escenario: Buscar objetivo** , seleccione la columna que contiene el valor de destino de la lista.</span><span class="sxs-lookup"><span data-stu-id="46604-114">In the **Scenario Analysis: Goal Seek** dialog box, select the column that contains the target value from the list.</span></span>  
  
4.  <span data-ttu-id="46604-115">Especifique el valor que desea conseguir.</span><span class="sxs-lookup"><span data-stu-id="46604-115">Specify the value that you want to achieve.</span></span>  
  
     <span data-ttu-id="46604-116">Si el objetivo de la columna contiene valores numéricos continuos, también puede especificar el aumento o la disminución que desea para el valor.</span><span class="sxs-lookup"><span data-stu-id="46604-116">If the column goal contains continuous numeric values, you can also specify a desired increase or decrease in the value.</span></span> <span data-ttu-id="46604-117">Por ejemplo, puede elegir **ventas** como columna y especificar que el destino es un aumento del 120%.</span><span class="sxs-lookup"><span data-stu-id="46604-117">For example, you might choose **Sales** as the column and specify that the target is an increase of 120%.</span></span>  
  
     <span data-ttu-id="46604-118">También puede especificar el objetivo como un intervalo de valores, escribiendo un límite inferior y uno superior.</span><span class="sxs-lookup"><span data-stu-id="46604-118">Or, you can specify the goal as a range of values, by typing a lower and upper limit.</span></span>  
  
5.  <span data-ttu-id="46604-119">Especifique la columna que contiene los valores que cambiará.</span><span class="sxs-lookup"><span data-stu-id="46604-119">Specify the column that contains the values you will change.</span></span> <span data-ttu-id="46604-120">En otras palabras, escoja la columna que se manipulará para obtener el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="46604-120">In other words, pick the column that will be manipulated to produce the desired result.</span></span>  
  
6.  <span data-ttu-id="46604-121">Opcionalmente, haga clic en **elegir las columnas que se van a usar para el análisis**y seleccione las columnas que contengan información útil.</span><span class="sxs-lookup"><span data-stu-id="46604-121">Optionally, click **Choose columns to be used for analysis**, and select columns that contain useful information.</span></span> <span data-ttu-id="46604-122">Anule la selección de las columnas que no contribuyan al análisis.</span><span class="sxs-lookup"><span data-stu-id="46604-122">Deselect columns that will not contribute to the analysis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="46604-123">No anule la selección de las columnas que usará como objetivo o para los cambios.</span><span class="sxs-lookup"><span data-stu-id="46604-123">Do not deselect columns that you will use for either the goal or the change.</span></span> <span data-ttu-id="46604-124">Estas columnas son necesarias.</span><span class="sxs-lookup"><span data-stu-id="46604-124">These columns are required.</span></span>  
  
7.  <span data-ttu-id="46604-125">Especifique si desea realizar predicciones para toda la tabla o solo para la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="46604-125">Specify whether you want to make predictions for the entire table, or for only the selected row.</span></span>  
  
8.  <span data-ttu-id="46604-126">Si ha seleccionado la opción de **tabla completa** , la herramienta agrega las predicciones a la tabla de origen en dos nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="46604-126">If you selected the **Entire table** option, the tool adds the predictions to the source table in two new columns.</span></span>  
  
9. <span data-ttu-id="46604-127">Si ha seleccionado la opción **en esta fila**, los resultados del análisis se muestran en el cuadro de diálogo para su revisión.</span><span class="sxs-lookup"><span data-stu-id="46604-127">If you selected the option **On this row**, the results of analysis are output to the dialog box for review.</span></span> <span data-ttu-id="46604-128">El cuadro de diálogo permanece abierto para que pueda seguir probando valores y objetivos diferentes.</span><span class="sxs-lookup"><span data-stu-id="46604-128">The dialog box stays open so that you can continue trying out different values and goals.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="46604-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46604-129">Requirements</span></span>  
 <span data-ttu-id="46604-130">Esta herramienta usa el algoritmo de regresión logística de Microsoft, que puede procesar valores numéricos o discretos.</span><span class="sxs-lookup"><span data-stu-id="46604-130">This tool uses the Microsoft Logistic Regression algorithm, which can process either numeric or discrete values.</span></span>  
  
 <span data-ttu-id="46604-131">Puede ejecutar la predicción varias veces y seleccionar otras columnas posteriormente, pero cada combinación de un objetivo y un cambio debe calcularse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="46604-131">You can run the prediction multiple times, and select different columns later, but each combination of a goal and a change must be calculated separately.</span></span>  
  
 <span data-ttu-id="46604-132">Puede obtener mejores resultados si selecciona columnas para el análisis que contengan información útil.</span><span class="sxs-lookup"><span data-stu-id="46604-132">You can achieve better results if you select columns for analysis that contain useful information.</span></span> <span data-ttu-id="46604-133">No obstante, si incluye muy pocas columnas, puede resultar difícil obtener un resultado.</span><span class="sxs-lookup"><span data-stu-id="46604-133">However, if you include too few columns, it might be difficult to obtain a result.</span></span>  
  
 <span data-ttu-id="46604-134">Cuando cree predicciones de una en una, asegúrese de que selecciona una fila que no contiene el resultado deseado o puede obtener un error.</span><span class="sxs-lookup"><span data-stu-id="46604-134">When you create predictions one at a time, be sure to select a row that does not already contain the desired result, or you may get an error.</span></span> <span data-ttu-id="46604-135">En otras palabras, si el propósito de la búsqueda de un objetivo consiste en determinar factores que animan a comprar bicicletas, solo debería incluir los clientes que no han comprado una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="46604-135">In other words, if the purpose of goal seeking is to determine factors that encourage bike purchases, you should only include customers who did not purchase a bike.</span></span>  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a><span data-ttu-id="46604-136">Descripción de los resultados de un análisis Buscar objetivo</span><span class="sxs-lookup"><span data-stu-id="46604-136">Understanding the Results of Goal Seek Analysis</span></span>  
 <span data-ttu-id="46604-137">Cuando se crea un escenario de búsqueda de objetivo, la herramienta hace tres cosas:</span><span class="sxs-lookup"><span data-stu-id="46604-137">When you create a goal seeking scenario, the tool does three things:</span></span>  
  
-   <span data-ttu-id="46604-138">Crea una estructura de minería de datos que almacena hechos clave sobre los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="46604-138">Creates a data mining structure that stores key facts about the data in your table.</span></span>  
  
-   <span data-ttu-id="46604-139">Crea un modelo de minería de datos de regresión logística basado en los datos.</span><span class="sxs-lookup"><span data-stu-id="46604-139">Creates a logistic regression mining model based on the data.</span></span>  
  
-   <span data-ttu-id="46604-140">Crea una predicción para cada valor especificado.</span><span class="sxs-lookup"><span data-stu-id="46604-140">Creates a prediction for each value that you specify.</span></span>  
  
 <span data-ttu-id="46604-141">Si prueba los escenarios de búsqueda de objetivo de uno en uno, puede ver los resultados interactivamente.</span><span class="sxs-lookup"><span data-stu-id="46604-141">If you test goal-seeking scenarios one at a time, you can view the results interactively.</span></span> <span data-ttu-id="46604-142">Esto es lo mismo que crear una *consulta de predicción singleton*.</span><span class="sxs-lookup"><span data-stu-id="46604-142">This is the same as creating a *singleton prediction query*.</span></span>  
  
 <span data-ttu-id="46604-143">La herramienta informa en el panel de **resultados** del cuadro de diálogo si fue correcto encontrar un escenario que logre el objetivo deseado.</span><span class="sxs-lookup"><span data-stu-id="46604-143">The tool reports in the **Results** pane of the dialog box whether it was successful in finding a scenario that achieves the desired goal.</span></span> <span data-ttu-id="46604-144">Si se encontró una solución correcta, la herramienta también genera una recomendación que le indica el cambio necesario.</span><span class="sxs-lookup"><span data-stu-id="46604-144">If a successful solution was found, the tool also generates a recommendation that tells you the required change.</span></span> <span data-ttu-id="46604-145">Por ejemplo, la herramienta **Buscar objetivo** puede indicarle que la distancia de trabajo debe ser inferior a 5 kilómetros.</span><span class="sxs-lookup"><span data-stu-id="46604-145">For example, the **Goal Seek** tool might tell you that the commuting distance should be less than 5 miles.</span></span>  
  
 <span data-ttu-id="46604-146">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46604-146">Example results:</span></span>  
  
 <span data-ttu-id="46604-147">**La búsqueda de objetivo para Interest in Buying encontró una solución.**</span><span class="sxs-lookup"><span data-stu-id="46604-147">**Goal Seeking for Interest in Buying has found a solution.**</span></span>  
  
 <span data-ttu-id="46604-148">**Coincidencia más cercana obtenida al cambiar 'Conmute distance' a '2-5 miles'.**</span><span class="sxs-lookup"><span data-stu-id="46604-148">**Closest match obtained by changing 'Commute distance' to '2-5 miles'.**</span></span>  
  
 <span data-ttu-id="46604-149">Dado que este resultado se basa en una fila existente de la tabla de datos, eso significa que, para un cliente concreto, si todos los demás datos sobre ese cliente permanecieran iguales, pero su distancia al trabajo se redujera hasta situarse entre 2 y 5 millas, habría más probabilidades de que comprase una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="46604-149">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's commute was reduced to 2-5 miles, the customer would be somewhat more likely buy a bicycle.</span></span>  
  
 <span data-ttu-id="46604-150">Si crea predicciones de búsqueda de objetivos para todas las filas de la tabla de Excel especificando **toda la tabla**, la herramienta crea dos nuevas columnas en la tabla de datos original.</span><span class="sxs-lookup"><span data-stu-id="46604-150">If you create goal-seeking predictions for all the rows in the Excel table by specifying **Entire table**, thetool creates two new columns in the original data table.</span></span> <span data-ttu-id="46604-151">La primera columna que se agrega a la tabla contiene una marca de verificación en un círculo verde para indicar que se puede conseguir el objetivo o una marca X en un círculo rojo para indicar que no es posible realizar ningún cambio que permita alcanzar el objetivo.</span><span class="sxs-lookup"><span data-stu-id="46604-151">The first column that is added to the table contains either a check mark in a green circle, to indicate that the goal can be met, or an X mark in a red circle, to indicate that no changes can be made that will enable the goal.</span></span>  
  
 <span data-ttu-id="46604-152">La segunda columna contiene el cambio recomendado.</span><span class="sxs-lookup"><span data-stu-id="46604-152">The second column contains the recommended change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="46604-153">El nivel de confianza de la recomendación y su éxito están predeterminados por el algoritmo y no se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="46604-153">The confidence level for the recommendation and its success are predetermined by the algorithm and cannot be changed.</span></span>  
  
## <a name="related-tools"></a><span data-ttu-id="46604-154">Herramientas relacionadas</span><span class="sxs-lookup"><span data-stu-id="46604-154">Related Tools</span></span>  
 <span data-ttu-id="46604-155">El Cliente de minería de datos para Excel, que es un complemento independiente que ofrece funciones de minería de datos más avanzadas, incluye asistentes para crear modelos de minería de datos que predicen el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="46604-155">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="46604-156">Para obtener más información, vea [crear un modelo de minería de datos](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="46604-156">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
 <span data-ttu-id="46604-157">Para obtener más información acerca del algoritmo usado por la herramienta de escenario **Buscar objetivo** , vea el tema "algoritmo de regresión logística de Microsoft" en los [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] libros en pantalla de.</span><span class="sxs-lookup"><span data-stu-id="46604-157">For more information about the algorithm used by the **Goal Seek** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46604-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46604-158">See Also</span></span>  
 [<span data-ttu-id="46604-159">Herramientas de análisis de tabla para Excel</span><span class="sxs-lookup"><span data-stu-id="46604-159">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
