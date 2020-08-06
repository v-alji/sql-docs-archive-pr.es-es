---
title: Agregar una vista del origen de datos con tablas anidadas (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a14cd7f1-7a10-4ec6-af6a-f5f0676a0308
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: da1a9bff093e0b59e9d1166554d95bcf61aded08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747795"
---
# <a name="adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial"></a><span data-ttu-id="b4a28-102">Agregar una vista del origen de datos con tablas anidadas (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="b4a28-102">Adding a Data Source View with Nested Tables (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="b4a28-103">Para crear un modelo de cesta de la compra, debe usar una vista del origen de datos que admita datos asociativos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-103">To create a market basket model, you must use a data source view that supports associative data.</span></span> <span data-ttu-id="b4a28-104">Esta vista del origen de datos también se utilizará para el escenario de agrupación en clústeres de secuencia.</span><span class="sxs-lookup"><span data-stu-id="b4a28-104">This data source view will also be used for the sequence clustering scenario.</span></span>  
  
 <span data-ttu-id="b4a28-105">Esta vista del origen de datos es diferente de la de otros usuarios con los que haya trabajado porque contiene una *tabla anidada*.</span><span class="sxs-lookup"><span data-stu-id="b4a28-105">This data source view is different from others that you may have worked with because it contains a *nested table*.</span></span> <span data-ttu-id="b4a28-106">Una *tabla anidada* es una tabla que contiene varias filas de información sobre una sola fila de la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-106">A *nested table* is a table that contains multiple rows of information about a single row in the case table.</span></span> <span data-ttu-id="b4a28-107">Por ejemplo, si el modelo analiza los hábitos de compra de los clientes, lo normal sería usar una tabla que tuviese una única fila para cada cliente como tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-107">For example, if your model analyzes the purchasing behavior of customers, you would typically use a table that has a unique row for each customer as the case table.</span></span> <span data-ttu-id="b4a28-108">Sin embargo, cada cliente puede hacer varias compras y es posible que se desee analizar el orden en que se realizan las compras o los productos que suelen comprarse juntos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-108">However, each customer might make multiple purchases, and you might want to analyze the sequence of purchases, or products that are frequently purchased together.</span></span> <span data-ttu-id="b4a28-109">Para representar estas compras de manera lógica en el modelo, agregará a la vista del origen de datos otra tabla que muestre las compras de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="b4a28-109">To logically represent these purchases in your model, you add another table to the data source view that lists the purchases for each customer.</span></span>  
  
 <span data-ttu-id="b4a28-110">Esta tabla de compras anidada se relaciona con la tabla de clientes mediante una relación de varios a uno.</span><span class="sxs-lookup"><span data-stu-id="b4a28-110">This nested purchases table is related to the customer table by a many-to-one relationship.</span></span> <span data-ttu-id="b4a28-111">La tabla anidada podría contener muchas filas para cada cliente, cada una con un único producto que se compró, quizás con información adicional sobre el orden en el que se realizaron las compras, el precio en el momento del pedido o cualquier promoción que se aplicara.</span><span class="sxs-lookup"><span data-stu-id="b4a28-111">The nested table might contain many rows for each customer, each row containing a single product that was purchased, perhaps with additional information about the order that the purchases were made, the price at the time of the order, or any promotions that applied.</span></span> <span data-ttu-id="b4a28-112">Puede utilizar la información de la tabla anidada como entrada para el modelo o como el atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="b4a28-112">You can use the information in the nested table as inputs to the model, or as the predictable attribute.</span></span>  
  
 <span data-ttu-id="b4a28-113">En esta lección, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4a28-113">In this lesson, you do the following tasks:</span></span>  
  
-   <span data-ttu-id="b4a28-114">Agregue una vista del origen de datos al [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-114">You add a data source view to the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source.</span></span>  
  
-   <span data-ttu-id="b4a28-115">Agregará las tablas anidadas y de casos a esta vista.</span><span class="sxs-lookup"><span data-stu-id="b4a28-115">You add the case and nested tables to this view.</span></span>  
  
-   <span data-ttu-id="b4a28-116">Especificará la relación de varios a uno entre la tabla de casos y la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="b4a28-116">You specify the many-to-one relationship between the case and nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4a28-117">.</span><span class="sxs-lookup"><span data-stu-id="b4a28-117">.</span></span> <span data-ttu-id="b4a28-118">Es importante que siga el procedimiento descrito de forma exacta, para especificar correctamente la relación entre la tabla de casos y la tabla anidada, y evitar errores al procesar el modelo.</span><span class="sxs-lookup"><span data-stu-id="b4a28-118">It is important that you follow the described procedure exactly, to correctly specify the relationship between the case table and the nested table and to avoid errors when you process the model.</span></span>  
  
-   <span data-ttu-id="b4a28-119">Definirá cómo se utilizan las columnas de datos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="b4a28-119">You define how the columns of data are used in the model.</span></span>  
  
 <span data-ttu-id="b4a28-120">Para obtener más información sobre cómo trabajar con tablas de casos y anidadas, y cómo elegir una clave de tabla anidada, vea [tablas anidadas &#40;Analysis Services-Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b4a28-120">For more information about working with case and nested tables, and how to choose a nested table key, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="b4a28-121">Para agregar una vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="b4a28-121">To add a data source view</span></span>  
  
1.  <span data-ttu-id="b4a28-122">En Explorador de soluciones, haga clic con el botón secundario en **vistas del origen de datos**y seleccione **nueva vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="b4a28-122">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
     <span data-ttu-id="b4a28-123">Se abrirá el Asistente para vistas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-123">The Data Source View Wizard opens.</span></span>  
  
2.  <span data-ttu-id="b4a28-124">En la página inicial del **Asistente para orígenes de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b4a28-124">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="b4a28-125">En la página **seleccionar un origen de datos** , en **orígenes de datos relacionales**, seleccione el [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] origen de datos que ha creado en el tutorial básico de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-125">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source that you created in the Basic Data Mining Tutorial.</span></span> <span data-ttu-id="b4a28-126">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b4a28-126">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="b4a28-127">En la página **seleccionar tablas y vistas** , seleccione las tablas siguientes y, a continuación, haga clic en la flecha derecha para incluirlas en la nueva vista del origen de datos:</span><span class="sxs-lookup"><span data-stu-id="b4a28-127">On the **Select Tables and Views** page, select the following tables, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   `vAssocSeqOrders`  
  
    -   `vAssocSeqLineItems`  
  
5.  <span data-ttu-id="b4a28-128">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b4a28-128">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b4a28-129">En la página **finalización del asistente** , la vista del origen de datos se denomina de forma predeterminada [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4a28-129">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="b4a28-130">Cambie el nombre a `Orders` y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b4a28-130">Change the name to `Orders`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="b4a28-131">Se abre el diseñador de vistas del origen de datos y `Orders` aparece la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4a28-131">Data Source View Designer opens and the `Orders` data source view appears.</span></span>  
  
### <a name="to-create-a-relationship-between-tables"></a><span data-ttu-id="b4a28-132">Crear una relación entre tablas</span><span class="sxs-lookup"><span data-stu-id="b4a28-132">To create a relationship between tables</span></span>  
  
1.  <span data-ttu-id="b4a28-133">En el Diseñador de vistas del origen de datos, coloque las dos tablas de modo que estén alineadas horizontalmente, con la tabla vAssocSeqLineItems en el lado izquierdo y la tabla vAssocSeqOrders en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="b4a28-133">In Data Source View Designer, position the two tables so that the tables are aligned horizontally, with the vAssocSeqLineItems table on the left side and the vAssocSeqOrders table on the right side.</span></span>  
  
2.  <span data-ttu-id="b4a28-134">Seleccione la columna **OrderNumber** en la tabla vAssocSeqLineItems.</span><span class="sxs-lookup"><span data-stu-id="b4a28-134">Select the **OrderNumber** column in the vAssocSeqLineItems table.</span></span>  
  
3.  <span data-ttu-id="b4a28-135">Arrastre la columna hasta la tabla vAssocSeqOrders y colóquela en la columna **OrderNumber** .</span><span class="sxs-lookup"><span data-stu-id="b4a28-135">Drag the column to the vAssocSeqOrders table, and put it on the **OrderNumber** column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b4a28-136">Asegúrese de arrastrar la columna **OrderNumber** de la tabla anidada vAssocSeqLineItems, que representa el lado "varios" de la combinación, a la tabla de casos vAssocSeqOrders, que representa el lado uno de la combinación.</span><span class="sxs-lookup"><span data-stu-id="b4a28-136">Make sure to drag the **OrderNumber** column from the vAssocSeqLineItems nested table, which represents the many side of the join, to the vAssocSeqOrders case table, which represents the one side of the join.</span></span>  
  
     <span data-ttu-id="b4a28-137">Ahora existe una nueva *relación de varios a uno* entre las tablas VAssocSeqLineItems y vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="b4a28-137">A new *many-to-one relationship* now exists between the vAssocSeqLineItems and vAssocSeqOrders tables.</span></span> <span data-ttu-id="b4a28-138">Si ha combinado correctamente las tablas, la vista del origen de datos debería aparecer como sigue:</span><span class="sxs-lookup"><span data-stu-id="b4a28-138">If you have joined the tables correctly, the data source view should appear as follows:</span></span>  
  
     <span data-ttu-id="b4a28-139">![combinación esperada de varios a uno en tabla de casos y anidada](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "combinación esperada de varios a uno en tabla de casos y anidada")</span><span class="sxs-lookup"><span data-stu-id="b4a28-139">![expected many-to-one join on nested and case table](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "expected many-to-one join on nested and case table")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b4a28-140">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="b4a28-140">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b4a28-141">Crear una estructura de cesta de la compra y un modelo &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b4a28-141">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4a28-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4a28-142">See Also</span></span>  
 <span data-ttu-id="b4a28-143">[Tutorial intermedio de minería de datos &#40;Analysis Services:&#41;de minería de datos](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b4a28-143">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="b4a28-144">[Estructuras de minería de datos &#40;Analysis Services:&#41;de minería de datos](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b4a28-144">[Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="b4a28-145">Modelos de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b4a28-145">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-models-analysis-services-data-mining.md)  
  
  
