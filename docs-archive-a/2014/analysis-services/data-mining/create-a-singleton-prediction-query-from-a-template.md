---
title: Crear una consulta de predicción singleton desde una plantilla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton query predictions [DMX]
ms.assetid: e0a68ab0-bece-4d25-b464-47f1719302e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80e853875cce349dd8623fab3c30f1ad09bfbf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663799"
---
# <a name="create-a-singleton-prediction-query-from-a-template"></a><span data-ttu-id="d2f35-102">Crear una consulta de predicción singleton desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="d2f35-102">Create a Singleton Prediction Query from a Template</span></span>
  <span data-ttu-id="d2f35-103">Una consulta singleton es útil cuando tiene un modelo que desea usar para la predicción, pero no desea asignarlo a un conjunto de datos de entrada externo ni realizar predicciones masivas.</span><span class="sxs-lookup"><span data-stu-id="d2f35-103">A singleton query is useful when you have a model that you want to use for prediction, but don't want to map it to an external input data set or make bulk predictions.</span></span> <span data-ttu-id="d2f35-104">Una consulta singleton le permite proporcionar un valor o varios valores al modelo y ver al momento el valor predicho.</span><span class="sxs-lookup"><span data-stu-id="d2f35-104">With a singleton query, you can provide a value or values to the model and instantly see the predicted value.</span></span>  
  
 <span data-ttu-id="d2f35-105">Por ejemplo, la consulta DMX siguiente representa una consulta singleton frente al modelo de correo directo, TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="d2f35-105">For example, the following DMX query represents a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="d2f35-106">El procedimiento siguiente describe cómo utilizar el Explorador de plantillas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para crear rápidamente esta consulta.</span><span class="sxs-lookup"><span data-stu-id="d2f35-106">The procedure that follows describes how to use the Template Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to quickly create this query.</span></span>  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a><span data-ttu-id="d2f35-107">Abrir las plantillas de Analysis Services en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2f35-107">To open the Analysis Services templates in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d2f35-108">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en el **Explorador de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="d2f35-109">Haga clic en el icono de cubo para abrir las plantillas de **Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-109">Click the cube icon to open the **Analysis Server**templates.</span></span>  
  
### <a name="to-open-a-prediction-query-template"></a><span data-ttu-id="d2f35-110">Abrir una plantilla de consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="d2f35-110">To open a prediction query template</span></span>  
  
1.  <span data-ttu-id="d2f35-111">En el **Explorador de plantillas**, en la lista de plantillas de Analysis Server, expanda **DMX**y, luego, expanda **Consultas de predicción**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-111">In **Template Explorer**, in the list of Analysis Server templates, expand **DMX**, and thenexpand **Prediction Queries**.</span></span>  
  
2.  <span data-ttu-id="d2f35-112">Haga doble clic en **Predicción de singleton**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-112">Double-click **Singleton Prediction**.</span></span>  
  
3.  <span data-ttu-id="d2f35-113">En el cuadro de diálogo **Conectar a Analysis Services** , escriba el nombre del servidor que tiene la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene el modelo de minería de datos que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="d2f35-113">In the **Connect to Analysis Services** dialog box, type the name of the server that has the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining model to be queried.</span></span>  
  
4.  <span data-ttu-id="d2f35-114">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-114">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="d2f35-115">La plantilla se abre en la base de datos especificada junto con un Explorador de objetos del modelo de minería de datos que contiene las funciones de minería de datos y una lista de estructuras de minería de datos y los modelos relacionados.</span><span class="sxs-lookup"><span data-stu-id="d2f35-115">The template opens in the specified database, together with a mining model Object Browser that contains data mining functions and a list of data mining structures and related models.</span></span>  
  
### <a name="to-customize-the-singleton-query-template"></a><span data-ttu-id="d2f35-116">Personalizar la plantilla de consulta singleton</span><span class="sxs-lookup"><span data-stu-id="d2f35-116">To customize the singleton query template</span></span>  
  
1.  <span data-ttu-id="d2f35-117">En la plantilla, haga clic en la lista desplegable **Bases de datos disponibles** y, después, seleccione una instancia de Analysis Services en la lista.</span><span class="sxs-lookup"><span data-stu-id="d2f35-117">In the template, click the **Available Databases** drop-down list, and then select an instance of Analysis Service from the list.</span></span>  
  
2.  <span data-ttu-id="d2f35-118">En la lista **Modelo de minería de datos** , seleccione el modelo de minería de datos que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="d2f35-118">In the **Mining Model** list, select the mining model that you want to query.</span></span>  
  
     <span data-ttu-id="d2f35-119">La lista de columnas del modelo de minería de datos aparece en el panel **Metadatos** del explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="d2f35-119">The list of columns in the mining model appears in the **Metadata** pane of the object browser.</span></span>  
  
3.  <span data-ttu-id="d2f35-120">En el menú **Consulta** , seleccione **Especificar valores para parámetros de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-120">On the **Query** menu, select **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="d2f35-121">En la fila **seleccionar lista** , escriba \* para devolver todas las columnas o escriba una lista delimitada por comas de columnas y expresiones para devolver columnas concretas.</span><span class="sxs-lookup"><span data-stu-id="d2f35-121">In the **select list** row, type \* to return all columns, or type a comma-delimited list of columns and expressions to return specific columns.</span></span>  
  
     <span data-ttu-id="d2f35-122">Si escribe \*, se devuelve la columna de predicción, junto con cualquier columna para la que proporciona nuevos valores en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="d2f35-122">If you type \*, the predictable column is returned, together with any columns for which you provide new values for in step 6.</span></span>  
  
     <span data-ttu-id="d2f35-123">En el código de ejemplo que se muestra al principio de este tema, la fila **Select List** se estableció en \*.</span><span class="sxs-lookup"><span data-stu-id="d2f35-123">For the sample code shown at the start of this topic, the **select list** row was set to \*.</span></span>  
  
5.  <span data-ttu-id="d2f35-124">En la fila **modelo de minería de datos** , escriba el nombre del modelo de minería de datos entre la lista de modelos de minería de datos que aparecen en el **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-124">In the **mining model** row, type the name of the mining model from among the list of mining models that appear in **Object Explorer**.</span></span>  
  
     <span data-ttu-id="d2f35-125">En el código de ejemplo que se muestra al principio de este tema, la fila del **modelo de minería de datos** se estableció en el nombre `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="d2f35-125">For the sample code shown at the start of this topic, the **mining model** row was set to the name, `TM_Decision_Tree`.</span></span>  
  
6.  <span data-ttu-id="d2f35-126">En la fila **value** , escriba el nuevo valor de datos para el que desea realizar una predicción.</span><span class="sxs-lookup"><span data-stu-id="d2f35-126">In the **value** row, type the new data value for which you want to make a prediction.</span></span>  
  
     <span data-ttu-id="d2f35-127">En el código de ejemplo que se muestra al principio de este tema, la fila **Value** se estableció en `2` para predecir el comportamiento de compra de bicicletas en función del número de hijos en casa.</span><span class="sxs-lookup"><span data-stu-id="d2f35-127">For the sample code shown at the start of this topic, the **value** row was set to `2` to predict bike buying behavior based on the number of children at home.</span></span>  
  
7.  <span data-ttu-id="d2f35-128">En la fila **column** , escriba el nombre de la columna del modelo de minería de datos al que deberían estar asignados los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="d2f35-128">In the **column** row, type the name of the column in the mining model to which the new data should be mapped.</span></span>  
  
     <span data-ttu-id="d2f35-129">En el código de ejemplo que se muestra al principio de este tema, la fila de la **columna** estaba establecida en `Number Children at Home` .</span><span class="sxs-lookup"><span data-stu-id="d2f35-129">For the sample code shown at the start of this topic, the **column** row was set to `Number Children at Home`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d2f35-130">Al usar el cuadro de diálogo **Especificar valores para parámetros de plantilla** , no tiene que agregar corchetes al nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="d2f35-130">When you use the **Specify Values for Template Parameters** dialog box, you do not have to add square brackets around the column name.</span></span> <span data-ttu-id="d2f35-131">Los corchetes se agregarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d2f35-131">The brackets will automatically be added for you.</span></span>  
  
8.  <span data-ttu-id="d2f35-132">Deje el **alias de entrada** como `t` .</span><span class="sxs-lookup"><span data-stu-id="d2f35-132">Leave the **input alias** as `t`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="d2f35-133">En el panel de texto de consulta, busque las marcas en zigzag rojas debajo de la coma y los puntos suspensivos que indican un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="d2f35-133">In the query text pane, find the red squiggle under the comma and ellipsis that indicates a syntax error.</span></span> <span data-ttu-id="d2f35-134">Elimine los puntos suspensivos y agregue cualquier condición de consulta adicional que desee.</span><span class="sxs-lookup"><span data-stu-id="d2f35-134">Delete the ellipsis, and add any additional query condition that you want.</span></span> <span data-ttu-id="d2f35-135">Si no agrega ninguna otra condición, elimine la coma.</span><span class="sxs-lookup"><span data-stu-id="d2f35-135">If you do not add any other conditions, delete the comma.</span></span>  
  
     <span data-ttu-id="d2f35-136">En el caso del código de ejemplo que se muestra en el comienzo de este tema, la condición de consulta adicional se estableció en `'45' as [Age]`.</span><span class="sxs-lookup"><span data-stu-id="d2f35-136">For the sample code shown at the start of this topic, the additional query condition was set to `'45' as [Age]`.</span></span>  
  
11. <span data-ttu-id="d2f35-137">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d2f35-137">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f35-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2f35-138">See Also</span></span>  
 [<span data-ttu-id="d2f35-139">Crear predicciones &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d2f35-139">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
  
