---
title: Agregar un gráfico a un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6b595dc-f775-4a53-8554-74a0bf9335ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 789dd6cce10b0425833ea63f2f7941ea75970a25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662570"
---
# <a name="add-a-chart-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="b7651-102">Agregar un gráfico a un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="b7651-102">Add a Chart to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b7651-103">Si desea resumir datos y presentarlos con un formato visual, use una región de datos Gráfico.</span><span class="sxs-lookup"><span data-stu-id="b7651-103">When you want to summarize data in a visual format, use a Chart data region.</span></span> <span data-ttu-id="b7651-104">Es importante elegir el tipo de gráfico adecuado para el tipo de datos que se va a presentar.</span><span class="sxs-lookup"><span data-stu-id="b7651-104">It is important to choose an appropriate chart type for the type of data that you are presenting.</span></span> <span data-ttu-id="b7651-105">Esto determinará en qué medida se podrán interpretar correctamente los datos cuando se trasladen al gráfico.</span><span class="sxs-lookup"><span data-stu-id="b7651-105">This affects how well the data can be interpreted when put in chart form.</span></span> <span data-ttu-id="b7651-106">Para más información, vea [Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b7651-106">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="b7651-107">La manera más simple de agregar una región de datos de Gráfico a su informe es ejecutar el Asistente para nuevo gráfico.</span><span class="sxs-lookup"><span data-stu-id="b7651-107">The simplest way to add a Chart data region to your report is to run the New Chart Wizard.</span></span> <span data-ttu-id="b7651-108">El asistente proporciona gráficos de columna, línea, circular, barra y área.</span><span class="sxs-lookup"><span data-stu-id="b7651-108">The wizard offers column, line, pie, bar, and area charts.</span></span> <span data-ttu-id="b7651-109">Para éstos y otros tipos de gráfico, puede agregar también un gráfico manualmente.</span><span class="sxs-lookup"><span data-stu-id="b7651-109">For these and other chart types, you can also add a chart manually.</span></span>  
  
 <span data-ttu-id="b7651-110">Después de agregar una región de datos Gráfico a la superficie de diseño, puede arrastrar los campos de conjunto de datos de informe para los datos numéricos y no numéricos hasta el panel de Datos del gráfico en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="b7651-110">After you add a Chart data region to the design surface, you can drag report dataset fields for numeric and non-numeric data to the Chart Data pane of the chart.</span></span> <span data-ttu-id="b7651-111">Haga clic en el gráfico para mostrar el panel Datos del gráfico con sus tres áreas: Grupos de series, Grupos de categorías y Valores.</span><span class="sxs-lookup"><span data-stu-id="b7651-111">Click the chart to display the Chart Data pane with its three areas: Series Groups, Category Groups, and Values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-chart-to-a-report-by-using-the-chart-wizard"></a><span data-ttu-id="b7651-112">Para agregar un gráfico a un informe utilizando el Asistente para gráficos</span><span class="sxs-lookup"><span data-stu-id="b7651-112">To add a chart to a report by using the Chart Wizard</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="b7651-113">El Asistente para gráficos solamente está disponible en el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b7651-113">The Chart Wizard is only available in Report Builder.</span></span>  
  
     <span data-ttu-id="b7651-114">En la pestaña **Insertar** , haga clic en **Gráfico**y, a continuación, haga clic en **Asistente para gráficos**.</span><span class="sxs-lookup"><span data-stu-id="b7651-114">On the **Insert** tab, click **Chart**, and then click **Chart Wizard**.</span></span>  
  
2.  <span data-ttu-id="b7651-115">Siga los pasos en el Asistente para **Nuevo** gráfico.</span><span class="sxs-lookup"><span data-stu-id="b7651-115">Follow the steps in the **New** Chart wizard.</span></span>  
  
3.  <span data-ttu-id="b7651-116">En la pestaña **Inicio** , haga clic en **Ejecutar** para ver el informe representado.</span><span class="sxs-lookup"><span data-stu-id="b7651-116">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="b7651-117">En la pestaña **Ejecutar** , haga clic en **Diseño** para seguir trabajando en el informe.</span><span class="sxs-lookup"><span data-stu-id="b7651-117">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-chart-to-a-report"></a><span data-ttu-id="b7651-118">Para agregar un gráfico a un informe</span><span class="sxs-lookup"><span data-stu-id="b7651-118">To add a chart to a report</span></span>  
  
1.  <span data-ttu-id="b7651-119">Cree un informe y defina un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b7651-119">Create a report and define a dataset.</span></span> <span data-ttu-id="b7651-120">Para obtener más información, vea [Agregar datos a un informe &#40;generador de informes y SSRS&#41;](../report-data/report-datasets-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b7651-120">For more information, see [Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="b7651-121">En la pestaña **Insertar** , haga clic en **Gráfico**y, a continuación, haga clic en **Insertar gráfico**.</span><span class="sxs-lookup"><span data-stu-id="b7651-121">On the **Insert** tab, click **Chart**, and then click **Insert Chart**.</span></span>  
  
3.  <span data-ttu-id="b7651-122">Haga clic en la superficie de diseño en la que desea que se encuentre la esquina superior izquierda del gráfico y arrastre hasta donde desee que se encuentre la esquina inferior derecha del gráfico.</span><span class="sxs-lookup"><span data-stu-id="b7651-122">Click on the design surface where you want the upper-left corner of the chart, and then drag to where you want the lower-right corner of the chart.</span></span>  
  
     <span data-ttu-id="b7651-123">Aparece el cuadro de diálogo **Seleccionar tipo de gráfico** .</span><span class="sxs-lookup"><span data-stu-id="b7651-123">The **Select Chart Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b7651-124">Seleccione el tipo de gráfico que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="b7651-124">Select the type of chart you want to add.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="b7651-125">Haga clic en el gráfico para mostrar el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="b7651-125">Click the chart to display the **Chart Data** pane.</span></span>  
  
6.  <span data-ttu-id="b7651-126">Agregue uno o más campos al área **Valores** .</span><span class="sxs-lookup"><span data-stu-id="b7651-126">Add one or more fields to the **Values** area.</span></span> <span data-ttu-id="b7651-127">Esta información se representará en el eje de valores.</span><span class="sxs-lookup"><span data-stu-id="b7651-127">This information will be plotted on the value axis.</span></span>  
  
7.  <span data-ttu-id="b7651-128">Agregue un campo de agrupación al área **Grupos de categorías** .</span><span class="sxs-lookup"><span data-stu-id="b7651-128">Add a grouping field to the **Category Groups** area.</span></span> <span data-ttu-id="b7651-129">Al agregar este campo al área **Grupos de categorías** , se crea un campo de agrupación automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b7651-129">When you add this field to the **Category Groups** area, a grouping field is automatically created for you.</span></span> <span data-ttu-id="b7651-130">Cada grupo representa un punto de datos de la serie.</span><span class="sxs-lookup"><span data-stu-id="b7651-130">Each group represents a data point in your series.</span></span>  
  
8.  <span data-ttu-id="b7651-131">Para resumir los datos por categoría, haga clic con el botón derecho en el campo de datos y, después, haga clic en **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="b7651-131">To summarize the data by category, right-click the data field and click **Series Properties**.</span></span> <span data-ttu-id="b7651-132">En el cuadro **Categoría** , seleccione el campo de categoría en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b7651-132">In the **Category** box, select the category field from the drop-down list.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="b7651-133">En la pestaña **Inicio** , haga clic en **Ejecutar** para ver el informe representado.</span><span class="sxs-lookup"><span data-stu-id="b7651-133">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
10. <span data-ttu-id="b7651-134">En la pestaña **Ejecutar** , haga clic en **Diseño** para seguir trabajando en el informe.</span><span class="sxs-lookup"><span data-stu-id="b7651-134">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
 <span data-ttu-id="b7651-135">En los gráficos con ejes, como los gráficos de barras y de columnas, es posible que el eje de categorías no muestre todas las etiquetas de categoría.</span><span class="sxs-lookup"><span data-stu-id="b7651-135">On charts with axes, such as bar and column charts, the category axis may not display all the category labels.</span></span> <span data-ttu-id="b7651-136">Para más información sobre cómo cambiar las etiquetas de los ejes, vea [Especificar un intervalo de eje &#40;Generador de informes y SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b7651-136">For more information about how to change the axis labels, see [Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7651-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7651-137">See Also</span></span>  
 <span data-ttu-id="b7651-138">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b7651-138">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b7651-139">[Tipos de gráficos &#40;Generador de informes y SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b7651-139">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b7651-140">[Puntos de datos vacíos y nulos en los gráficos &#40;Generador de informes y SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b7651-140">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b7651-141">[Tutorial: Agregar un gráfico de barras a un informe (Generador de informes)](https://go.microsoft.com/fwlink/?LinkId=198052) </span><span class="sxs-lookup"><span data-stu-id="b7651-141">[Tutorial: Adding a Bar Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198052) </span></span>  
 <span data-ttu-id="b7651-142">[Tutorial: Agregar un gráfico de barras a un informe (Diseñador de informes)](https://go.microsoft.com/fwlink/?LinkId=198042) </span><span class="sxs-lookup"><span data-stu-id="b7651-142">[Tutorial: Adding a Bar Chart to a Report (Report Designer)](https://go.microsoft.com/fwlink/?LinkId=198042) </span></span>  
 <span data-ttu-id="b7651-143">[Tutorial: Agregar un gráfico circular al informe (Generador de informes)](https://go.microsoft.com/fwlink/?LinkId=198051) </span><span class="sxs-lookup"><span data-stu-id="b7651-143">[Tutorial: Adding a Pie Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198051) </span></span>  
 [<span data-ttu-id="b7651-144">Tutorial: Agregar un gráfico circular a un informe (Diseñador de informes)</span><span class="sxs-lookup"><span data-stu-id="b7651-144">Tutorial: Adding a Pie Chart to a Report (Report Designer)</span></span>](https://go.microsoft.com/fwlink/?LinkId=198041)  
  
  
