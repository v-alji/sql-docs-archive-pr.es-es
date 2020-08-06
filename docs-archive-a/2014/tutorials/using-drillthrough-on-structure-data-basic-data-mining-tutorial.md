---
title: Usar la obtención de detalles en datos de estructura (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a693979c-0564-4d6d-b35d-cbbc8f350469
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 49a1ced27150676def541548f47a90a3f847c8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662386"
---
# <a name="using-drillthrough-on-structure-data-basic-data-mining-tutorial"></a><span data-ttu-id="4cf48-102">Usar la obtención de detalles en datos de estructura (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="4cf48-102">Using Drillthrough on Structure Data (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4cf48-103">[!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] está enviando un formulario a los clientes potenciales de entre 34 y 40 años de edad como parte de su campaña de publicidad.</span><span class="sxs-lookup"><span data-stu-id="4cf48-103">As part of their advertising campaign, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] is sending a mailer to potential customers in the 34-40 age demographic.</span></span> <span data-ttu-id="4cf48-104">El departamento de marketing ha decidido que quieren enviar también el formulario a los clientes que compraron bicicletas de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] hace más de cinco años.</span><span class="sxs-lookup"><span data-stu-id="4cf48-104">The marketing department has decided that they would also like to send the mailer to the customers who purchased bikes from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] more than five years ago.</span></span> <span data-ttu-id="4cf48-105">En esta lección, identificará los clientes con bicicletas anteriores y recuperará su información de contacto.</span><span class="sxs-lookup"><span data-stu-id="4cf48-105">In this lesson you will identify customers with older bikes and retrieve their contact information.</span></span> <span data-ttu-id="4cf48-106">Esta información no está incluida en el modelo, pero se incluye en la estructura.</span><span class="sxs-lookup"><span data-stu-id="4cf48-106">This information is not included in the model, but is included in the structure.</span></span> <span data-ttu-id="4cf48-107">Para recuperar la información de contacto, primero se asegurará de que la obtención de detalles está habilitada para la estructura y, a continuación, la utilizará para revelar los nombres y direcciones de los clientes objetivo.</span><span class="sxs-lookup"><span data-stu-id="4cf48-107">To retrieve the contact information you will first ensure that drillthrough is enabled for the structure and then you will use drillthrough to reveal the names and addresses of the targeted customers.</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="4cf48-108">Para habilitar la obtención de detalles en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="4cf48-108">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="4cf48-109">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, haga clic con el botón secundario en el modelo **TM_Decision_Tree** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4cf48-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the **TM_Decision_Tree** model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4cf48-110">En las ventanas Propiedades, haga clic en **AllowDrillThrough**y seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="4cf48-110">In the Properties windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="4cf48-111">En la pestaña Modelos de minería de datos, haga clic con el botón secundario en el modelo y seleccione **Procesar modelo**.</span><span class="sxs-lookup"><span data-stu-id="4cf48-111">In the Mining Models tab, right-click the model, and select **Process Model**.</span></span>  
  
 <span data-ttu-id="4cf48-112">Para obtener más información, vea [consultas de obtención de detalles &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="4cf48-112">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a><span data-ttu-id="4cf48-113">Para ver los datos de obtención de detalles de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="4cf48-113">To view drillthrough data from a mining model</span></span>  
  
1.  <span data-ttu-id="4cf48-114">En el Diseñador de minería de datos, haga clic en la pestaña **Visor de modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="4cf48-114">In Data Mining Designer, click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="4cf48-115">Seleccione el modelo **TM_Decision_Tree** en la lista **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="4cf48-115">Select the **TM_Decision_Tree** model from the **Mining Model** list.</span></span>  
  
3.  <span data-ttu-id="4cf48-116">Cambie el valor de **fondo** a `1` .</span><span class="sxs-lookup"><span data-stu-id="4cf48-116">Change the **Background** value to `1`.</span></span> <span data-ttu-id="4cf48-117">De esta forma, se muestra solo la parte del modelo que está relacionada con los clientes que compraron bicicletas.</span><span class="sxs-lookup"><span data-stu-id="4cf48-117">By doing this, you show only the part of the model that is related to customer who bought bikes.</span></span>  
  
4.  <span data-ttu-id="4cf48-118">En la lista **Visor** , seleccione Visor de árboles de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4cf48-118">Select the Microsoft Tree viewer from the **Viewer** list.</span></span> <span data-ttu-id="4cf48-119">De esta manera, se forzará la actualización del visor con las condiciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="4cf48-119">This will force the viewer to refresh with the new filter conditions.</span></span> <span data-ttu-id="4cf48-120">A continuación, busque el nodo **Age >= 34 y <41** y haga clic con el botón secundario en el nodo.</span><span class="sxs-lookup"><span data-stu-id="4cf48-120">Then, locate the **Age >=34 and <41** node and right-click the node.</span></span>  
  
5.  <span data-ttu-id="4cf48-121">Seleccione **Obtener detalles**y después **Columnas de modelo y estructura** para abrir la ventana **Obtener detalles** .</span><span class="sxs-lookup"><span data-stu-id="4cf48-121">Select **Drill Through**, and then select **Model and Structure Columns** to open the **Drill Through** window.</span></span>  
  
6.  <span data-ttu-id="4cf48-122">Desplácese a la columna **Structure.Date First Purchase** para ver la fecha de compra de las bicicletas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4cf48-122">Scroll to the **Structure.Date First Purchase** column to view the purchase dates for the older bikes.</span></span>  
  
7.  <span data-ttu-id="4cf48-123">Para copiar los datos en el Portapapeles, haga clic con el botón derecho en cualquier fila de la tabla y seleccione **Copiar todo**.</span><span class="sxs-lookup"><span data-stu-id="4cf48-123">To copy the data to the Clipboard, right-click any row in the table, and select **Copy All**.</span></span>  
  
 <span data-ttu-id="4cf48-124">Felicidades, ha completado el Tutorial básico de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="4cf48-124">Congratulations, you have completed the basic data mining tutorial.</span></span> <span data-ttu-id="4cf48-125">Ahora que conoce más las herramientas de minería de datos, recomendamos que también complete el Tutorial intermedio de minería de datos, que demuestra cómo crear modelos de pronóstico, análisis de la cesta de la compra y agrupación en clústeres de secuencia.</span><span class="sxs-lookup"><span data-stu-id="4cf48-125">Now that you are comfortable using the data mining tools, we recommend that you also complete the intermediate data mining tutorial, which demonstrates how to create models for forecasting, market basket analysis, and sequence clustering.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="4cf48-126">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="4cf48-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="4cf48-127">Crear predicciones &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4cf48-127">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cf48-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4cf48-128">See Also</span></span>  
 [<span data-ttu-id="4cf48-129">Crear una consulta de predicción con el Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="4cf48-129">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
