---
title: Filtrar una regla en un modelo de reglas de asociación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filtering rules [Analysis Services]
- Mining Model Viewer [Analysis Services], rules
- Rules Viewer
ms.assetid: 26cdba5b-5bf1-439e-80a3-8759774e918b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c904713acc6eaf132e7cb1195186165f21d971a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674446"
---
# <a name="filter-a-rule-in-an-association-rules-model"></a><span data-ttu-id="b7f19-102">Filtrar una regla en un modelo de reglas de asociación</span><span class="sxs-lookup"><span data-stu-id="b7f19-102">Filter a Rule in an Association Rules Model</span></span>
  <span data-ttu-id="b7f19-103">Puede usar filtros con los modelos de asociación para restringir los resultados a las asociaciones que le interesan.</span><span class="sxs-lookup"><span data-stu-id="b7f19-103">You can use filtering with association models to restrict the results to just the associations that interest you.</span></span> <span data-ttu-id="b7f19-104">Por ejemplo, puede filtrar las reglas para mostrar solo las que incluyan un producto concreto.</span><span class="sxs-lookup"><span data-stu-id="b7f19-104">For example, you might filter the rules to show only those that include a specific product.</span></span>  
  
 <span data-ttu-id="b7f19-105">En el Diseñador de minería de datos, use los controles de la pestaña **Reglas** del Visor de reglas de asociación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] para filtrar las reglas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="b7f19-105">In Data Mining Designer, you use the controls on the **Rules** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer to filter the rules that are displayed.</span></span>  <span data-ttu-id="b7f19-106">También puede crear una consulta en el modelo para ver solo el conjunto de elementos que contiene un valor determinado.</span><span class="sxs-lookup"><span data-stu-id="b7f19-106">You can also create a query on the model to see only itemset that contains a particular value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7f19-107">Esta opción solo está disponible para los modelos de minería de datos creados usando el algoritmo de asociación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7f19-107">This option is available only for mining models that have been created by using the Microsoft Association Algorithm.</span></span>  
  
### <a name="filter-a-rule-in-an-association-model"></a><span data-ttu-id="b7f19-108">Filtrar una regla en un modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="b7f19-108">Filter a rule in an association model</span></span>  
  
1.  <span data-ttu-id="b7f19-109">Abra el modelo de minería de datos usando el **Visor de reglas de asociación**.</span><span class="sxs-lookup"><span data-stu-id="b7f19-109">Open the mining model by using the **Association Rules Viewer**.</span></span> <span data-ttu-id="b7f19-110">Para hacer esto en SQL Server Management Studio, haga clic con el botón secundario en el nombre del modelo y seleccione **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="b7f19-110">To do this in SQL Server Management Studio, right click the model name and select **Browse**.</span></span> <span data-ttu-id="b7f19-111">Para hacerlo en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga doble clic en la estructura de minería de datos que contiene el modelo y, después, haga clic en la pestaña **Visor de modelos de minería de datos** del **Diseñador de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="b7f19-111">To do this in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the model, and then click the **Mining Model Viewer** tab of **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="b7f19-112">Haga clic en la pestaña **Reglas** del **Visor de reglas de asociación**.</span><span class="sxs-lookup"><span data-stu-id="b7f19-112">Click the **Rules** tab of the **Association Rules Viewer**.</span></span>  
  
3.  <span data-ttu-id="b7f19-113">Escriba una condición de regla en el cuadro **Regla del filtro** .</span><span class="sxs-lookup"><span data-stu-id="b7f19-113">Type a rule condition into the **Filter Rule** box.</span></span> <span data-ttu-id="b7f19-114">Por ejemplo, una condición de regla podría ser "Bike Stand", que también devuelve "Bike Stands".</span><span class="sxs-lookup"><span data-stu-id="b7f19-114">For example, a rule condition might be "Bike Stand", which also returns "Bike Stands".</span></span>  
  
     <span data-ttu-id="b7f19-115">El cuadro de texto **Regla del filtro** admite expresiones regulares según se definan en el lenguaje de .NET.</span><span class="sxs-lookup"><span data-stu-id="b7f19-115">The **Filter Rule** text box supports regular expressions as defined by the .NET language.</span></span> <span data-ttu-id="b7f19-116">Por consiguiente, puede utilizar expresiones como esta: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`</span><span class="sxs-lookup"><span data-stu-id="b7f19-116">Therefore, you can use expressions such as the following: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span></span> <span data-ttu-id="b7f19-117">Esta expresión devolvería cualquier conjunto de elementos que incluya atributos con las palabras Helmets y Fenders, en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="b7f19-117">This expression would return any itemsets that include attributes with the words Helmets and Fenders, in any order.</span></span>  
  
4.  <span data-ttu-id="b7f19-118">En **Probabilidad mínima**, aumente el valor de probabilidad para ver menos reglas o disminuya el valor para ver más reglas.</span><span class="sxs-lookup"><span data-stu-id="b7f19-118">For **Minimum probability**, increase the value of probability to see fewer rules, or decrease the value to see more rules.</span></span>  
  
5.  <span data-ttu-id="b7f19-119">En **Importancia mínima**, aumente el valor de importancia para ver menos reglas o disminuya el valor para ver más reglas.</span><span class="sxs-lookup"><span data-stu-id="b7f19-119">For **Minimum importance**, increase the value of importance to see fewer rules, or decrease the value to see more rules.</span></span>  
  
6.  <span data-ttu-id="b7f19-120">En **Mostrar**, seleccione una de las opciones siguientes: **Mostrar el valor y el nombre del atributo**, **Mostrar solo el nombre del atributo**o **Mostrar solo el valor del atributo**.</span><span class="sxs-lookup"><span data-stu-id="b7f19-120">For **Show**, select one of the following options: **Show attribute name and value**, **Show attribute name only**, or **Show attribute value only**.</span></span>  
  
7.  <span data-ttu-id="b7f19-121">En **Número máximo de filas**, aumente el valor para aumentar el número total de reglas que cumplen las condiciones especificadas o disminuya el valor para limitar el número de reglas devueltas.</span><span class="sxs-lookup"><span data-stu-id="b7f19-121">For **Maximum rows**, increase the value to increase the total number of rules that meet the specified conditions, or decrease the value to limit the number of rules returned.</span></span> <span data-ttu-id="b7f19-122">Las reglas se ordenan por probabilidad, de modo que podría eliminar reglas adicionales que cumplan las condiciones especificadas para la probabilidad o la importancia.</span><span class="sxs-lookup"><span data-stu-id="b7f19-122">Rules are ordered by probability, so you might eliminate additional rules that meet the specified conditions for probability or importance.</span></span>  
  
8.  <span data-ttu-id="b7f19-123">Seleccione o anule la selección de la casilla **Mostrar nombre largo** para alternar la manera en que se muestran los nombres de las reglas.</span><span class="sxs-lookup"><span data-stu-id="b7f19-123">Select or deselect the **Show long name** check box to toggle the way that the rules names are displayed.</span></span>  
  
     <span data-ttu-id="b7f19-124">Las reglas se filtran ahora para mostrar únicamente las reglas que contengan el elemento indicado.</span><span class="sxs-lookup"><span data-stu-id="b7f19-124">The rules are now filtered to only display rules that contain the indicated item.</span></span> <span data-ttu-id="b7f19-125">La condición de filtro se aplica a los valores de atributo antes o después del delimitador de la regla, "->".</span><span class="sxs-lookup"><span data-stu-id="b7f19-125">The filter condition applies to attribute values either before or after the rule delimiter, "->".</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7f19-126">El visor almacena en memoria caché la lista inicial de reglas, según una consulta del modelo de minería de datos, y no actualiza la lista de reglas a menos que cambie las condiciones de la consulta estableciendo las filas máximas, la probabilidad, la importancia o la presentación de nombres largos.</span><span class="sxs-lookup"><span data-stu-id="b7f19-126">The viewer caches the initial list of rules, based on a query to the mining model, and does not refresh the list of rules unless you change the conditions of the query by setting the maximum rows, the probability, importance, or the display of long names.</span></span> <span data-ttu-id="b7f19-127">Por consiguiente, si escribe una condición y la presentación no se actualiza inmediatamente, puede obligar al visor a que actualice los datos seleccionando y anulando la selección de la casilla **Mostrar nombres largos** .</span><span class="sxs-lookup"><span data-stu-id="b7f19-127">Therefore, if you type a condition and the display does not immediately refresh, you can force the viewer to refresh the data by selecting and then deselecting the **Show long names** check box.</span></span>  
  
### <a name="create-a-query-on-the-itemsets-in-an-association-model"></a><span data-ttu-id="b7f19-128">Crear una consulta en los conjuntos de elementos en un modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="b7f19-128">Create a query on the itemsets in an association model</span></span>  
  
-   [<span data-ttu-id="b7f19-129">Ejemplos de consultas del modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="b7f19-129">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7f19-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7f19-130">See Also</span></span>  
 <span data-ttu-id="b7f19-131">[Tareas y procedimientos del visor de modelos de minería de datos](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="b7f19-131">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="b7f19-132">[Examinar un modelo mediante el visor de reglas de Asociación de Microsoft](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="b7f19-132">[Browse a Model Using the Microsoft Association Rules Viewer](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span></span>  
 [<span data-ttu-id="b7f19-133">Lección 3: Generar un escenario de cesta de la compra &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b7f19-133">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
  
