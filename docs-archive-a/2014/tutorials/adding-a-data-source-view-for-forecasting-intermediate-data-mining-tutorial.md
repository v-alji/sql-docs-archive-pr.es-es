---
title: Agregar una vista del origen de datos para la previsión (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2665040a-1291-4064-ba01-f458637dda57
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9424988efa6a9856f4ef0d558992fc90ac303861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747794"
---
# <a name="adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial"></a><span data-ttu-id="b3be6-102">Agregar una vista del origen de datos para las previsiones (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="b3be6-102">Adding a Data Source View for Forecasting (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="b3be6-103">En esta tarea, agregará una vista del origen de datos que se utilizará para el escenario de pronóstico.</span><span class="sxs-lookup"><span data-stu-id="b3be6-103">In this task, you add a data source view that will be used for the forecasting scenario.</span></span> <span data-ttu-id="b3be6-104">Un modelo de previsión requiere que los datos contengan una columna que se pueda utilizar para identificar pasos en una serie temporal.</span><span class="sxs-lookup"><span data-stu-id="b3be6-104">A forecasting model requires that the data contains a column that can be used to identify steps in a time series.</span></span> <span data-ttu-id="b3be6-105">Si piensa analizar varias series de datos, todas ellas deben finalizar en la misma fecha o estadio temporal.</span><span class="sxs-lookup"><span data-stu-id="b3be6-105">If you plan to analyze multiple series of data, all series must end on the same date or time step.</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="b3be6-106">Para agregar una vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="b3be6-106">To add a data source view</span></span>  
  
1.  <span data-ttu-id="b3be6-107">En Explorador de soluciones, haga clic con el botón secundario en **vistas del origen de datos**y seleccione **nueva vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="b3be6-107">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="b3be6-108">En la página inicial del **Asistente para orígenes de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b3be6-108">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="b3be6-109">En la página **seleccionar un origen de datos** , en **orígenes de datos relacionales**, seleccione el origen de [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] datos.</span><span class="sxs-lookup"><span data-stu-id="b3be6-109">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source.</span></span> <span data-ttu-id="b3be6-110">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b3be6-110">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3be6-111">Si no tiene este origen de datos, puede encontrar los pasos para crear el origen de datos en el [tutorial básico de minería de datos](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b3be6-111">If you do not have this data source, you can find the steps to create the data source in the [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
4.  <span data-ttu-id="b3be6-112">En la página **seleccionar tablas y vistas** , seleccione la tabla vTimeSeries (DBO) y, a continuación, haga clic en la flecha derecha para agregarla a la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b3be6-112">On the **Select Tables and Views** page, select the table, vTimeSeries (dbo), and then click the right arrow to add it to the data source view.</span></span>  
  
5.  <span data-ttu-id="b3be6-113">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b3be6-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b3be6-114">En la página **finalización del asistente** , la vista del origen de datos se denomina de forma predeterminada [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3be6-114">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="b3be6-115">Cambie el nombre a **SalesByRegion**y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b3be6-115">Change the name to **SalesByRegion**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="b3be6-116">Se abre el diseñador de vistas del origen de datos y aparece la vista del origen de datos **SalesByRegion** .</span><span class="sxs-lookup"><span data-stu-id="b3be6-116">Data Source View Designer opens and the **SalesByRegion** data source view appears.</span></span>  
  
## <a name="working-with-the-data-source-view"></a><span data-ttu-id="b3be6-117">Trabajar con la vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="b3be6-117">Working with the Data Source View</span></span>  
 <span data-ttu-id="b3be6-118">Una vez creada la vista del origen de datos, puede explorar los datos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b3be6-118">After you have created the data source view, you can explore the data in the following ways:</span></span>  
  
-   <span data-ttu-id="b3be6-119">Haga clic con el botón secundario en la tabla vTimeSeries en el diseñador y seleccione **explorar datos** para abrir la tabla seleccionada en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="b3be6-119">Right-click the table vTimeSeries in the designer, and select **Explore Data** to open the selected table in a grid.</span></span>  
  
-   <span data-ttu-id="b3be6-120">Haga clic en **Opciones de muestreo** y, a continuación, use el cuadro de diálogo Opciones de **exploración de datos** para cambiar el método de muestreo.</span><span class="sxs-lookup"><span data-stu-id="b3be6-120">Click **Sampling options** and then use the **Data Exploration Options** dialog box to change the sampling method.</span></span> <span data-ttu-id="b3be6-121">Haga clic en **Actualizar** para cargar los datos en la tabla con la nueva configuración de opciones.</span><span class="sxs-lookup"><span data-stu-id="b3be6-121">Click **Refresh** to load data in the table using the new option settings.</span></span> <span data-ttu-id="b3be6-122">Por ejemplo, puede especificar el número de filas que se van a generar en el ejemplo o elegir las n primeras filas.</span><span class="sxs-lookup"><span data-stu-id="b3be6-122">For example, you could specify the number of rows to output in the sample, or choose the top n rows.</span></span>  
  
-   <span data-ttu-id="b3be6-123">Haga clic con el botón secundario en la tabla vTimeSeries y seleccione **propiedades** para asignar un nuevo nombre a la tabla.</span><span class="sxs-lookup"><span data-stu-id="b3be6-123">Right-click the table vTimeSeries and select **Properties** to assign a new name to the table.</span></span> <span data-ttu-id="b3be6-124">También puede seleccionar columnas individuales de la vista del origen de datos y modificar las propiedades de columna.</span><span class="sxs-lookup"><span data-stu-id="b3be6-124">You can also select individual columns from the data source view, and the modify the column properties.</span></span>  
  
-   <span data-ttu-id="b3be6-125">Haga clic en cualquier lugar del área de diseño de la vista del origen de datos para crear una nueva consulta y asignarle un nombre, crear relaciones entre las tablas o cambiar la disposición del área de diseño.</span><span class="sxs-lookup"><span data-stu-id="b3be6-125">Click anywhere in the data source view design area to create a new query and assign a name to it, to create relationships between tables, or to change the layout of the design area.</span></span>  
  
-   <span data-ttu-id="b3be6-126">Haga clic con el botón secundario en una tabla y seleccione **nuevo cálculo con nombre** para crear columnas derivadas, incluidas las agregaciones.</span><span class="sxs-lookup"><span data-stu-id="b3be6-126">Right-click a table and select **New Named Calculation** to create derived columns, including aggregations.</span></span> <span data-ttu-id="b3be6-127">También puede añadir nuevas tablas y vistas del origen de datos a esta vista.</span><span class="sxs-lookup"><span data-stu-id="b3be6-127">You can also add new tables and views from the data source in this view.</span></span>  
  
 <span data-ttu-id="b3be6-128">En la tarea siguiente, explorará los datos de la serie temporal y determinará la mejor columna para utilizar como identificador de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="b3be6-128">In the next task, you will explore the time series data and determine the best column to use as the time series identifier.</span></span> <span data-ttu-id="b3be6-129">También aprenderá a administrar los vacíos en los datos de la serie temporal.</span><span class="sxs-lookup"><span data-stu-id="b3be6-129">You will also learn how to handle gaps in time series data.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b3be6-130">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="b3be6-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b3be6-131">Descripción de los requisitos de un modelo de serie temporal &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b3be6-131">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3be6-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3be6-132">See Also</span></span>  
 [<span data-ttu-id="b3be6-133">Algoritmo de serie temporal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b3be6-133">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
