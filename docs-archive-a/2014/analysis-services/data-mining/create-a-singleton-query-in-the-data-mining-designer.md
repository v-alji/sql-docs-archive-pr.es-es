---
title: Crear una consulta Singleton en el diseñador de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton queries [Analysis Services]
- Mining Model Prediction [Analysis Services], singleton queries
ms.assetid: 6cdca8a0-cf16-46eb-a652-0bff820625ab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07491924dbcf0bd35d049e6a7c290d49becfb45d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663798"
---
# <a name="create-a-singleton-query-in-the-data-mining-designer"></a><span data-ttu-id="8f2b5-102">Crear una consulta singleton en el Diseñador de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8f2b5-102">Create a Singleton Query in the Data Mining Designer</span></span>
  <span data-ttu-id="8f2b5-103">Una consulta singleton es útil para crear una predicción para un único caso.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-103">A singleton query is useful if you want to create a prediction for a single case.</span></span> <span data-ttu-id="8f2b5-104">Para obtener más información sobre las consultas singleton, vea [Consultas de minería de datos](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8f2b5-104">For more information about singleton queries, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
 <span data-ttu-id="8f2b5-105">En la pestaña **Predicción de modelo de minería de datos** del Diseñador de minería de datos, puede crear muchos tipos diferentes de consultas.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-105">In the **Mining Model Prediction** tab of Data Mining Designer, you can create many different types of queries.</span></span> <span data-ttu-id="8f2b5-106">Puede crear una consulta usando el diseñador o escribiendo las instrucciones de Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="8f2b5-106">You can create a query by using the designer, or by typing Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="8f2b5-107">Puede iniciar con el diseñador y modificar la consulta que crea cambiando las instrucciones de DMX o agregando una cláusula WHERE u ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-107">You can also start with the designer and modify the query that it creates by changing the DMX statements, or by adding a WHERE or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="8f2b5-108">Para intercambiar entre la vista de diseño de consulta y la vista de texto de consulta, haga clic en el primer botón de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-108">To switch between the query design view and the query text view, click the first button on the toolbar.</span></span> <span data-ttu-id="8f2b5-109">En la vista del texto de la consulta es posible ver el código DMX creado por el Generador de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-109">When you are in the query text view, you can view the DMX code that Prediction Query Builder creates.</span></span> <span data-ttu-id="8f2b5-110">También puede ejecutar la consulta, modificarla y ejecutar la consulta modificada.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-110">You can also run the query, modify the query, and run the modified query.</span></span> <span data-ttu-id="8f2b5-111">No obstante, la consulta modificada no se mantiene si se cambia a la vista de diseño de la consulta.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-111">However, the modified query is not persisted if you switch back to the query design view.</span></span>  
  
 <span data-ttu-id="8f2b5-112">El código siguiente muestra un ejemplo de una consulta singleton frente al modelo de correo directo, TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-112">The following code shows an example of a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT [Bike Buyer], PredictProbability([Bike Buyer]) as ProbableBuyer  
FROM [TM_Decision_Tree]  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="8f2b5-113">Los pasos siguientes explican cómo crear esta consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-113">The following steps explain how to create this prediction query.</span></span>  
  
### <a name="to-create-a-singleton-query-by-using-the-data-mining-designer"></a><span data-ttu-id="8f2b5-114">Para crear una consulta singleton con el Diseñador de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8f2b5-114">To create a singleton query by using the Data Mining Designer</span></span>  
  
1.  <span data-ttu-id="8f2b5-115">Haga clic en la pestaña **Predicción de modelo de minería de datos** del Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-115">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="8f2b5-116">Haga clic en **Seleccionar modelo** en la tabla **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8f2b5-116">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="8f2b5-117">Se abre el cuadro de diálogo **Seleccionar modelo de minería de datos** , donde se muestran todas las estructuras de minería de datos que existen en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-117">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
     <span data-ttu-id="8f2b5-118">Seleccione el modelo que desea usar para crear una predicción.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-118">Select the model that you want to use for creating a prediction.</span></span>  
  
     <span data-ttu-id="8f2b5-119">Por ejemplo, para crear el código de ejemplo mostrado al inicio de este tema, seleccione TM_Decision_Tree y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-119">For example, to create the sample code shown at the start of this topic, select TM_Decision_Tree, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8f2b5-120">Haga clic en **Consulta singleton** en la barra de herramientas de la pestaña **Predicción de modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8f2b5-120">Click **Singleton query** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="8f2b5-121">Aparece en la pestaña la tabla **Entrada de consulta singleton** con las columnas automáticamente asignadas a las columnas de la tabla **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8f2b5-121">The **Singleton Query Input** table appears on the tab, with the columns automatically mapped to the columns in the **Mining Model** table.</span></span>  
  
4.  <span data-ttu-id="8f2b5-122">En la tabla **Entrada de consulta singleton** , seleccione los valores de la columna **Valor** para describir el caso para el que desea crear una predicción.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-122">On the **Singleton Query Input** table, select values in the **Value** column to describe the case for which you want to create a prediction.</span></span>  
  
     <span data-ttu-id="8f2b5-123">Por ejemplo, seleccione **2** en **número de hijos en Inicio**y, a continuación, escriba `45` para **edad**.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-123">For example, select **2** for **Number Children At Home**, and then type `45` for **Age**.</span></span>  
  
5.  <span data-ttu-id="8f2b5-124">Arrastre una columna de predicción de la tabla **modelo de minería de datos** a la columna de **origen** en la parte inferior de la pestaña. opcionalmente, puede escribir un alias para la columna.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-124">Drag a predictable column from the **Mining Model** table to the **Source** column at the bottom of the tab. Optionally, you can type an alias for the column.</span></span>  
  
     <span data-ttu-id="8f2b5-125">Por ejemplo, arrastre **Bike Buyer** a la columna **Origen** .</span><span class="sxs-lookup"><span data-stu-id="8f2b5-125">For example, drag **Bike Buyer** to the **Source** column.</span></span>  
  
6.  <span data-ttu-id="8f2b5-126">Para agregar funciones adicionales a la consulta, seleccione **Función de predicción** o **Expresión personalizada** en la lista desplegable de la columna **Origen** .</span><span class="sxs-lookup"><span data-stu-id="8f2b5-126">Add any additional functions to the query by selecting **Prediction Function** or **Custom Expression** from the drop-down list in the **Source** column.</span></span>  
  
     <span data-ttu-id="8f2b5-127">Por ejemplo, haga clic en **Función de predicción**y seleccione **PredictProbability**.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-127">For example, click **Prediction Function**, and select **PredictProbability**.</span></span>  
  
7.  <span data-ttu-id="8f2b5-128">Haga clic en **Criterios o argumento** en la fila **PredictProbability** y escriba el nombre de la columna que se va a predecir y, opcionalmente, un valor concreto para predecir.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-128">Click **Criteria/Argument** in the **PredictProbability** row, and type the name of the column to predict, and optionally a specific value to predict.</span></span>  
  
     <span data-ttu-id="8f2b5-129">Por ejemplo, escriba `[Bike Buyer], 1`.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-129">For example, type `[Bike Buyer], 1`.</span></span>  
  
8.  <span data-ttu-id="8f2b5-130">Haga clic en el cuadro **Alias** en la fila **PredictProbability** y escriba un nombre al que hacer referencia a la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-130">Click the **Alias** box in the **PredictProbability** row, and type a name to refer to the new column.</span></span>  
  
     <span data-ttu-id="8f2b5-131">Por ejemplo, escriba `ProbableBuyer`.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-131">For example, type `ProbableBuyer`.</span></span>  
  
9. <span data-ttu-id="8f2b5-132">Haga clic en **Cambiar a vista de resultado de consulta** en la barra de herramientas de la pestaña **Predicción de modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8f2b5-132">Click **Switch to query result view** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="8f2b5-133">Aparece una nueva ventana mostrando el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-133">A new screen opens to show the result of the query.</span></span> <span data-ttu-id="8f2b5-134">Para ver la instrucción DMX que acaba de crear, haga clic en **SQL**.</span><span class="sxs-lookup"><span data-stu-id="8f2b5-134">To view the DMX statement that you just created, click **SQL**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f2b5-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f2b5-135">See Also</span></span>  
 [<span data-ttu-id="8f2b5-136">Consultas de predicción &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8f2b5-136">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
