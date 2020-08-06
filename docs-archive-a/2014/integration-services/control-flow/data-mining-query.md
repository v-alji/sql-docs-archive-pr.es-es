---
title: Consulta de minería de datos| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquery.f1
ms.assetid: 948e358a-6245-429f-82c7-4cedc5e048fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 657e4e173815fa25458e296f7eadb3d4d0696a02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673849"
---
# <a name="data-mining-query"></a><span data-ttu-id="02b46-102">Consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="02b46-102">Data Mining Query</span></span>
  <span data-ttu-id="02b46-103">El panel de diseño contiene el generador de consultas de predicción de minería de datos, que puede utilizar para generar consultas de predicción de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="02b46-103">The design pane contains the data mining prediction query builder, which you can use to build data mining prediction queries.</span></span> <span data-ttu-id="02b46-104">Puede diseñar consultas de predicción basadas en tablas de entrada o consultas singleton de predicción.</span><span class="sxs-lookup"><span data-stu-id="02b46-104">You can design either prediction queries based on input tables, or singleton prediction queries.</span></span> <span data-ttu-id="02b46-105">Cambie a la vista de resultado para ejecutar la consulta y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="02b46-105">Switch to the result view to run the query and view the results.</span></span> <span data-ttu-id="02b46-106">La vista de consulta muestra la consulta de Extensiones de minería de datos (DMX) creada mediante el generador de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="02b46-106">The query view displays the Data Mining Extensions (DMX) query created by the prediction query builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="02b46-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="02b46-107">Options</span></span>  
 <span data-ttu-id="02b46-108">Botón Cambiar vista</span><span class="sxs-lookup"><span data-stu-id="02b46-108">Switch view button</span></span>  
 <span data-ttu-id="02b46-109">Haga clic en un icono para cambiar entre el panel de diseño y el de consulta.</span><span class="sxs-lookup"><span data-stu-id="02b46-109">Click an icon to switch between the design and query pane.</span></span> <span data-ttu-id="02b46-110">De forma predeterminada, el panel de diseño está abierto.</span><span class="sxs-lookup"><span data-stu-id="02b46-110">By default, the design pane is open.</span></span>  
  
 <span data-ttu-id="02b46-111">Para cambiar al panel de diseño, haga clic en el icono ![icono de diseño](../media/ssis-designicon.gif "Icono de diseño").</span><span class="sxs-lookup"><span data-stu-id="02b46-111">To switch to the design pane, click the ![Design icon](../media/ssis-designicon.gif "Design icon") icon.</span></span>  
  
 <span data-ttu-id="02b46-112">Para cambiar al panel de consulta, haga clic en el icono ![icono de SQL](../media/ssis-queryicon.gif "Icono de SQL").</span><span class="sxs-lookup"><span data-stu-id="02b46-112">To switch to the query pane, click the ![SQL icon](../media/ssis-queryicon.gif "SQL icon") icon.</span></span>  
  
 <span data-ttu-id="02b46-113">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="02b46-113">**Mining Model**</span></span>  
 <span data-ttu-id="02b46-114">Muestra el modelo de minería de datos seleccionado en el que desea basar las predicciones.</span><span class="sxs-lookup"><span data-stu-id="02b46-114">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="02b46-115">**Seleccionar modelo**</span><span class="sxs-lookup"><span data-stu-id="02b46-115">**Select Model**</span></span>  
 <span data-ttu-id="02b46-116">Abre el cuadro de diálogo **Seleccionar modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="02b46-116">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="02b46-117">**Columnas de entrada**</span><span class="sxs-lookup"><span data-stu-id="02b46-117">**Input Columns**</span></span>  
 <span data-ttu-id="02b46-118">Muestra las columnas de entrada seleccionadas que se utilizan para generar las predicciones.</span><span class="sxs-lookup"><span data-stu-id="02b46-118">Displays the selected input columns used to generate the predictions.</span></span>  
  
 <span data-ttu-id="02b46-119">**Origen**</span><span class="sxs-lookup"><span data-stu-id="02b46-119">**Source**</span></span>  
 <span data-ttu-id="02b46-120">Seleccione el origen que contiene el campo que utilizará para la columna desde la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="02b46-120">Select the source containing the field that you will use for the column from the dropdown list.</span></span> <span data-ttu-id="02b46-121">Puede usar el modelo de minería de datos seleccionado en la tabla **Modelo de minería de datos** , la tabla o las tablas de entrada seleccionadas en la tabla **Seleccionar tabla(s) de entrada** , una función de predicción o una expresión personalizada.</span><span class="sxs-lookup"><span data-stu-id="02b46-121">You can either use the mining model selected in the **Mining Model** table, the input table(s) selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="02b46-122">Las columnas pueden arrastrarse desde las tablas que contienen el modelo de minería de datos y las columnas de entrada a la celda.</span><span class="sxs-lookup"><span data-stu-id="02b46-122">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
 <span data-ttu-id="02b46-123">**Campo**</span><span class="sxs-lookup"><span data-stu-id="02b46-123">**Field**</span></span>  
 <span data-ttu-id="02b46-124">En la tabla de origen, seleccione una columna de la lista de columnas derivadas.</span><span class="sxs-lookup"><span data-stu-id="02b46-124">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="02b46-125">Si ha seleccionado **Función de predicción** en **Origen**, esta celda contiene una lista desplegable de las funciones de predicción disponibles para el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="02b46-125">If you selected **Prediction Function** in **Source**, this cell contains a drop-down list of the prediction functions available for the selected mining model.</span></span>  
  
 <span data-ttu-id="02b46-126">**Alias**</span><span class="sxs-lookup"><span data-stu-id="02b46-126">**Alias**</span></span>  
 <span data-ttu-id="02b46-127">El nombre de la columna que devuelve el servidor.</span><span class="sxs-lookup"><span data-stu-id="02b46-127">The name of the column returned by the server.</span></span>  
  
 <span data-ttu-id="02b46-128">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="02b46-128">**Show**</span></span>  
 <span data-ttu-id="02b46-129">Seleccione esta opción para devolver la columna o para utilizar solamente la columna en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="02b46-129">Select to return the column or to only use the column in the WHERE clause.</span></span>  
  
 <span data-ttu-id="02b46-130">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="02b46-130">**Group**</span></span>  
 <span data-ttu-id="02b46-131">Use esta opción con la columna **Y/O** para agrupar expresiones.</span><span class="sxs-lookup"><span data-stu-id="02b46-131">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="02b46-132">Por ejemplo, (expr1 O expr2) Y expr3.</span><span class="sxs-lookup"><span data-stu-id="02b46-132">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="02b46-133">**Y/O**</span><span class="sxs-lookup"><span data-stu-id="02b46-133">**And/Or**</span></span>  
 <span data-ttu-id="02b46-134">Utilice esta opción para crear una consulta lógica.</span><span class="sxs-lookup"><span data-stu-id="02b46-134">Use to create a logical query.</span></span> <span data-ttu-id="02b46-135">Por ejemplo, (expr1 O expr2) Y expr3.</span><span class="sxs-lookup"><span data-stu-id="02b46-135">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="02b46-136">**Criterios o argumento**</span><span class="sxs-lookup"><span data-stu-id="02b46-136">**Criteria/Argument**</span></span>  
 <span data-ttu-id="02b46-137">Especifique una condición o una expresión de usuario que se aplica a la columna.</span><span class="sxs-lookup"><span data-stu-id="02b46-137">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="02b46-138">Las columnas pueden arrastrarse desde las tablas que contienen el modelo de minería de datos y las columnas de entrada a la celda.</span><span class="sxs-lookup"><span data-stu-id="02b46-138">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b46-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02b46-139">See Also</span></span>  
 <span data-ttu-id="02b46-140">[Interfaces de consulta de minería de datos](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span><span class="sxs-lookup"><span data-stu-id="02b46-140">[Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span></span>  
 [<span data-ttu-id="02b46-141">Referencia de instrucciones de Extensiones de minería de datos &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="02b46-141">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
