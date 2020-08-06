---
title: 'Lección 4: Agregar una tabla al informe (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ddf2914-bcdd-427d-8cba-0ccb8342f819
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52694168bd60b8e3807db6204f33a89815573093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669512"
---
# <a name="lesson-4-adding-a-table-to-the-report-reporting-services"></a><span data-ttu-id="74fd4-102">Lección 4: Agregar una tabla al informe (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="74fd4-102">Lesson 4: Adding a Table to the Report (Reporting Services)</span></span>
  <span data-ttu-id="74fd4-103">Después de definir un conjunto de datos, puede comenzar a diseñar el diseño.</span><span class="sxs-lookup"><span data-stu-id="74fd4-103">After the dataset is defined, you can start designing the report.</span></span> <span data-ttu-id="74fd4-104">El diseño del informe se crea arrastrando y colocando en la superficie de diseño regiones de datos, cuadros de texto, imágenes y otros elementos que se desean incluir en el informe.</span><span class="sxs-lookup"><span data-stu-id="74fd4-104">You create a report layout by dragging and dropping data regions, text boxes, images, and other items that you want to include in your report to the design surface.</span></span>  
  
 <span data-ttu-id="74fd4-105">Los elementos que contienen filas de datos repetidas procedentes de conjuntos de datos subyacentes se denominan *regiones de datos*.</span><span class="sxs-lookup"><span data-stu-id="74fd4-105">Items that contain repeated rows of data from underlying datasets are called *data regions*.</span></span> <span data-ttu-id="74fd4-106">Un informe básico solo contendrá una región de datos, pero puede agregar más si, por ejemplo, desea agregar un gráfico al informe de tabla.</span><span class="sxs-lookup"><span data-stu-id="74fd4-106">A basic report will have only one data region, but you can add more, for example, if you want to add a chart to your tabular report.</span></span> <span data-ttu-id="74fd4-107">Después de agregar una región de datos, puede agregar campos a la misma.</span><span class="sxs-lookup"><span data-stu-id="74fd4-107">After you add a data region, you can add fields to the data region.</span></span>  
  
### <a name="to-add-a-table-data-region-and-fields-to-a-report-layout"></a><span data-ttu-id="74fd4-108">Para agregar una región de datos de tabla y campos a un diseño de informe</span><span class="sxs-lookup"><span data-stu-id="74fd4-108">To add a Table data region and fields to a report layout</span></span>  
  
1.  <span data-ttu-id="74fd4-109">En el **Cuadro de herramientas**, haga clic en **Tabla**y, después, haga clic en la superficie de diseño y arrastre el mouse.</span><span class="sxs-lookup"><span data-stu-id="74fd4-109">In the **Toolbox**, click **Table**, and then click on the design surface and drag the mouse.</span></span> <span data-ttu-id="74fd4-110">El Diseñador de informes dibuja una región de datos de tabla con tres columnas en el centro de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="74fd4-110">Report Designer draws a table data region with three columns in the center of the design surface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="74fd4-111">El **Cuadro de herramientas** puede aparecer como una pestaña a la izquierda del panel **Datos de informe** .</span><span class="sxs-lookup"><span data-stu-id="74fd4-111">The **Toolbox** may appear as a tab on the left side of the **Report Data** pane.</span></span> <span data-ttu-id="74fd4-112">Para abrir el **cuadro de herramientas**, mueva el puntero sobre la pestaña **cuadro de herramientas** . Si el **cuadro de herramientas** no está visible, en el menú **Ver** , haga clic en **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="74fd4-112">To open the **Toolbox**, move the pointer over the **Toolbox** tab. If the **Toolbox** is not visible, from the **View** menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="74fd4-113">En el panel **datos de informe** , expanda el conjunto de datos **AdventureWorksDataset** para mostrar los campos.</span><span class="sxs-lookup"><span data-stu-id="74fd4-113">In the **Report Data** pane, expand the **AdventureWorksDataset** dataset to display the fields.</span></span>  
  
3.  <span data-ttu-id="74fd4-114">Arrastre el campo Date desde el panel **Datos de informe** hasta la primera columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="74fd4-114">Drag the Date field from the **Report Data** pane to the first column in the table.</span></span>  
  
     <span data-ttu-id="74fd4-115">Al colocar el campo en la primera columna, suceden dos cosas.</span><span class="sxs-lookup"><span data-stu-id="74fd4-115">When you drop the field into the first column, two things happen.</span></span> <span data-ttu-id="74fd4-116">En primer lugar, la celda de datos mostrará el nombre del campo, que se conoce como la *expresión de campo*, entre corchetes: `[Date]`.</span><span class="sxs-lookup"><span data-stu-id="74fd4-116">First, the data cell will display the field name, known as the *field expression*, in brackets: `[Date]`.</span></span> <span data-ttu-id="74fd4-117">En segundo lugar, se agrega automáticamente un valor de encabezado de columna a la fila Encabezado, inmediatamente encima de la expresión de campo.</span><span class="sxs-lookup"><span data-stu-id="74fd4-117">Second, a column header value is automatically added to Header row, just above the field expression.</span></span> <span data-ttu-id="74fd4-118">De forma predeterminada, la columna tiene el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="74fd4-118">By default, the column is the name of the field.</span></span> <span data-ttu-id="74fd4-119">Puede seleccionar el texto de la fila Encabezado y escribir un nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="74fd4-119">You can select the Header row text and type a new name.</span></span>  
  
4.  <span data-ttu-id="74fd4-120">Arrastre el campo Order desde el panel **Datos de informe** hasta la segunda columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="74fd4-120">Drag the Order field from the **Report Data** pane to the second column in the table.</span></span>  
  
5.  <span data-ttu-id="74fd4-121">Arrastre el campo Product desde el panel **Datos de informe** hasta la tercera columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="74fd4-121">Drag the Product field from the **Report Data** pane to the third column in the table.</span></span>  
  
6.  <span data-ttu-id="74fd4-122">Arrastre el campo Qty hasta el borde derecho de la tercera columna hasta que obtenga un cursor vertical y el puntero del mouse tenga un signo más [+].</span><span class="sxs-lookup"><span data-stu-id="74fd4-122">Drag the Qty field to the right edge of the third column until you get a vertical cursor and the mouse pointer has a plus sign [+].</span></span> <span data-ttu-id="74fd4-123">Cuando suelte el botón, se creará una cuarta columna para `[Qty]`.</span><span class="sxs-lookup"><span data-stu-id="74fd4-123">When you release the mouse button, a fourth column is created for `[Qty]`.</span></span>  
  
7.  <span data-ttu-id="74fd4-124">Agregue el campo LineTotal de la misma manera, creando una quinta columna.</span><span class="sxs-lookup"><span data-stu-id="74fd4-124">Add the LineTotal field in the same way, creating a fifth column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="74fd4-125">El encabezado de columna es Line Total.</span><span class="sxs-lookup"><span data-stu-id="74fd4-125">The column header is Line Total.</span></span> <span data-ttu-id="74fd4-126">El Diseñador de informes crea automáticamente un nombre descriptivo para la columna, para lo cual, divide LineTotal en dos palabras.</span><span class="sxs-lookup"><span data-stu-id="74fd4-126">Report Designer automatically creates a friendly name for the column by splitting LineTotal into two words.</span></span>  
  
     <span data-ttu-id="74fd4-127">En el diagrama siguiente se muestra una región de datos de tabla rellenada con estos campos: Date, Order, Product, Qty y LineTotal.</span><span class="sxs-lookup"><span data-stu-id="74fd4-127">The following diagram shows a table data region that has been populated with these fields: Date, Order, Product, Qty, and Line Total.</span></span>  
  
     <span data-ttu-id="74fd4-128">![Diseño, Tabla con fila de encabezado y fila de detalle](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Diseño, Tabla con fila de encabezado y fila de detalle")</span><span class="sxs-lookup"><span data-stu-id="74fd4-128">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
## <a name="preview-your-report"></a><span data-ttu-id="74fd4-129">Obtener una vista previa del informe</span><span class="sxs-lookup"><span data-stu-id="74fd4-129">Preview Your Report</span></span>  
 <span data-ttu-id="74fd4-130">Al obtener una vista previa de un informe, se puede ver el informe representado sin tener que publicarlo antes en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="74fd4-130">Previewing a report enables you to view the rendered report without having to first publish it to a report server.</span></span> <span data-ttu-id="74fd4-131">Es probable que desee obtener frecuentemente una vista previa de un informe durante su diseño.</span><span class="sxs-lookup"><span data-stu-id="74fd4-131">You will probably want to preview your report frequently during design time.</span></span> <span data-ttu-id="74fd4-132">Al obtener la vista previa del informe, también se ejecutará la validación en el diseño y las conexiones de datos de modo que pueda corregir los errores y los problemas antes de publicar el informe en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="74fd4-132">Previewing the report will also run validation on the design and data connections so you can correct errors and issues before publishing the report to a report server.</span></span>  
  
#### <a name="to-preview-a-report"></a><span data-ttu-id="74fd4-133">Para obtener una vista previa de un informe</span><span class="sxs-lookup"><span data-stu-id="74fd4-133">To preview a report</span></span>  
  
-   <span data-ttu-id="74fd4-134">Haga clic en la pestaña **vista previa** . diseñador de informes ejecuta el informe y lo muestra en la vista previa.</span><span class="sxs-lookup"><span data-stu-id="74fd4-134">Click the **Preview** tab. Report Designer runs the report and displays it in Preview view.</span></span>  
  
     <span data-ttu-id="74fd4-135">El diagrama siguiente muestra parte del informe en la Vista previa.</span><span class="sxs-lookup"><span data-stu-id="74fd4-135">The following diagram shows part of the report in Preview view.</span></span>  
  
     <span data-ttu-id="74fd4-136">![Vista previa, filas de detalle de la tabla con 5 columnas](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Vista previa, filas de detalle de la tabla con 5 columnas")</span><span class="sxs-lookup"><span data-stu-id="74fd4-136">![Preview, Detail rows of table with 5 columns](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Preview, Detail rows of table with 5 columns")</span></span>  
  
     <span data-ttu-id="74fd4-137">Observe que la moneda (en la columna de Line Total) tiene seis posiciones decimales, y que la fecha incluye una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="74fd4-137">Notice that the currency (in the Line Total column) has six places after the decimal, and the date has includes a time stamp.</span></span> <span data-ttu-id="74fd4-138">En la lección siguiente corregirá ese formato.</span><span class="sxs-lookup"><span data-stu-id="74fd4-138">You're going to fix that formatting in the next lesson.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74fd4-139">En el menú **Archivo** , haga clic en **Guardar todo** para guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="74fd4-139">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="74fd4-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="74fd4-140">Next Steps</span></span>  
 <span data-ttu-id="74fd4-141">Ha agregado correctamente una región de datos de tabla al informe, ha agregado campos a la región de datos y ha obtenido una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="74fd4-141">You have successfully added a Table data region to your report, added fields to the data region, and previewed your report.</span></span> <span data-ttu-id="74fd4-142">A continuación, dará formato a los encabezados de columna y a los valores de fecha y de moneda.</span><span class="sxs-lookup"><span data-stu-id="74fd4-142">Next, you will format column headers and date and currency values.</span></span> <span data-ttu-id="74fd4-143">Vea [Lección 5: Aplicar formato a un informe &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="74fd4-143">See [Lesson 5: Formatting a Report &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74fd4-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74fd4-144">See Also</span></span>  
 <span data-ttu-id="74fd4-145">[Tablas &#40;Generador de informes y SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="74fd4-145">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="74fd4-146">Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="74fd4-146">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
  
  
