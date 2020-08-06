---
title: Crear una estructura y un modelo de previsión (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5f55cbf6-0db4-4cb4-a0f5-e27441873d4f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d77b15a9a8efe9a9c6faec49a2274ee182706992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743722"
---
# <a name="creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="b5fad-102">Crear una estructura de pronóstico y un modelo (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="b5fad-102">Creating a Forecasting Structure and Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="b5fad-103">A continuación utilizará el Asistente para minería de datos con el objeto de crear una nueva estructura de minería de datos y el modelo de minería de datos según la vista del origen de datos recién creada.</span><span class="sxs-lookup"><span data-stu-id="b5fad-103">Next, you will use the Data Mining Wizard to create a new mining structure and mining model based on the data source view that you just created.</span></span> <span data-ttu-id="b5fad-104">En esta tarea, especificará que el modelo de minería de datos debería utilizar el algoritmo de serie temporal de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5fad-104">In this task you will specify that the mining model should use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm.</span></span>  
  
### <a name="to-create-a-forecasting-mining-structure"></a><span data-ttu-id="b5fad-105">Para crear una estructura de minería de datos de previsión</span><span class="sxs-lookup"><span data-stu-id="b5fad-105">To create a forecasting mining structure</span></span>  
  
1.  <span data-ttu-id="b5fad-106">En Explorador de soluciones en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , haga clic con el botón secundario en **estructuras de minería de datos** y seleccione **nueva estructura de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-106">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="b5fad-107">En la página de inicio del **Asistente para minería de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="b5fad-108">En la página **seleccionar el método de definición** , compruebe que la opción **de base de datos relacional o del almacenamiento de datos existente** está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-108">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="b5fad-109">En la página **crear la estructura de minería de datos** , en **¿qué técnica de minería de datos desea utilizar?**, seleccione **serie temporal de Microsoft**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-109">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Time Series**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="b5fad-110">En la página **seleccionar vista del origen de datos** , en vistas del origen de **datos disponibles**, seleccione **SalesByRegion**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-110">On the **Select Data Source View** page, under **Available data source views**, select **SalesByRegion**.</span></span>  
  
6.  <span data-ttu-id="b5fad-111">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-111">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b5fad-112">En la página **especificar tipos de tablas** , asegúrese de que está seleccionada la casilla de la columna **caso** de la tabla vTimeSeries y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-112">On the **Specify Table Types** page, ensure that the check box in the **Case** column for the vTimeSeries table is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="b5fad-113">En la página **especificar los datos de aprendizaje** , active las casillas de la columna de **clave** para las columnas ModelRegion y ReportingDate.</span><span class="sxs-lookup"><span data-stu-id="b5fad-113">On the **Specify the Training Data** page, select the check boxes in the **Key** column for the ModelRegion and ReportingDate columns.</span></span>  
  
     <span data-ttu-id="b5fad-114">ReportingDate debería estar activada de forma predeterminada, porque esta columna se especificó como la clave principal lógica cuando se creó la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b5fad-114">ReportingDate should be selected by default, because you specified this column as the logical primary key when you created the data source view.</span></span> <span data-ttu-id="b5fad-115">Al agregar la columna ModelRegion como una segunda clave, se está indicando al algoritmo que cree una serie temporal independiente para cada combinación de modelo y región enumerada en este campo.</span><span class="sxs-lookup"><span data-stu-id="b5fad-115">By adding ModelRegion as a second key, you are telling the algorithm to create a separate time series for each combination of model and region listed in this field.</span></span>  
  
9. <span data-ttu-id="b5fad-116">Active las casillas de las columnas de **entrada** y de **predicción** para la columna quantity y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-116">Select the check boxes in the **Input** and **Predictable** columns for the Quantity, column, and then click **Next**.</span></span>  
  
     <span data-ttu-id="b5fad-117">Al seleccionar predecible, indica que desea crear **predicciones**sobre los datos de esta columna.</span><span class="sxs-lookup"><span data-stu-id="b5fad-117">By selecting **Predictable**, you indicate that you want to create forecasts on the data in this column.</span></span> <span data-ttu-id="b5fad-118">Sin embargo, dado que desea basar los pronósticos en datos previos, también debe agregar la columna como una entrada.</span><span class="sxs-lookup"><span data-stu-id="b5fad-118">However, because you want to base the forecasts on past data, you must also add the column as an input.</span></span>  
  
10. <span data-ttu-id="b5fad-119">En la página **especificar el contenido y el tipo de datos de las columnas**, revise las selecciones.</span><span class="sxs-lookup"><span data-stu-id="b5fad-119">On the page **Specify Columns' Content and Data Type**, review the selections.</span></span>  
  
     <span data-ttu-id="b5fad-120">La columna ModelRegion se designa como columna de **clave** y la columna ReportingDate se designa automáticamente como una columna **key Time** .</span><span class="sxs-lookup"><span data-stu-id="b5fad-120">The ModelRegion column is designated as a **Key** column and the ReportingDate column is automatically designated as a **Key Time** column.</span></span> <span data-ttu-id="b5fad-121">Puede tener solo una clave de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="b5fad-121">You can have only one of each type of key.</span></span>  
  
11. <span data-ttu-id="b5fad-122">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-122">Click **Next**.</span></span>  
  
12. <span data-ttu-id="b5fad-123">En la página **finalización del asistente** , en nombre de la **estructura de minería de datos**, escriba `Forecasting` .</span><span class="sxs-lookup"><span data-stu-id="b5fad-123">On the **Completing the Wizard** page, for **Mining structure name**, type `Forecasting`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5fad-124">La opción para habilitar la obtención de detalles no está disponible para los modelos de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="b5fad-124">The option to enable drillthrough is not available for time series models.</span></span>  
  
13. <span data-ttu-id="b5fad-125">En **nombre del modelo de minería de datos**, escriba `Forecasting` y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b5fad-125">In **Mining model name**, type `Forecasting`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="b5fad-126">El diseñador de minería de datos se abre para mostrar la estructura de minería de datos `Forecasting` que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="b5fad-126">Data Mining Designer opens to display the `Forecasting` mining structure that you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b5fad-127">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="b5fad-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b5fad-128">Modificar la estructura de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b5fad-128">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5fad-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5fad-129">See Also</span></span>  
 <span data-ttu-id="b5fad-130">[Diseñador de minería de datos](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b5fad-130">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="b5fad-131">Algoritmo de serie temporal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5fad-131">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
