---
title: Cuadro de diálogo especificar asignación de columna (gráfico de precisión de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.coltotablecolmapping.f1
ms.assetid: 68e9e2d2-173f-4363-a515-fc60bfee3af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ede835567f678f4152b3d1944f3c2c7160c6837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675560"
---
# <a name="specify-column-mapping-dialog-box-mining-accuracy-chart"></a><span data-ttu-id="09cc6-102">Cuadro de diálogo Especificar asignación de columna (gráfico de precisión de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="09cc6-102">Specify Column Mapping Dialog Box (Mining Accuracy Chart)</span></span>
  <span data-ttu-id="09cc6-103">Utilice la pestaña **Especificar asignación de columnas** para seleccionar las tablas de un origen de datos externo y asignar las columnas a un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="09cc6-103">Use the **Specify Column Mapping** tab to select tables from an external data source and map the columns to a data mining model.</span></span> <span data-ttu-id="09cc6-104">Después puede utilizar los datos externos para probar la exactitud de un modelo de minería y mostrar los resultados en el gráfico de precisión.</span><span class="sxs-lookup"><span data-stu-id="09cc6-104">You can then use the external data to test the accuracy of a mining model and displays the results in the accuracy chart.</span></span>  
  
 <span data-ttu-id="09cc6-105">**Para más información:** [Prueba y validación &#40;minería de datos&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="09cc6-105">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="09cc6-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="09cc6-106">Options</span></span>  
 <span data-ttu-id="09cc6-107">**Estructura de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="09cc6-107">**Mining Structure**</span></span>  
 <span data-ttu-id="09cc6-108">Muestra la estructura de minería de datos seleccionada que contiene el modelo que probará.</span><span class="sxs-lookup"><span data-stu-id="09cc6-108">Displays the selected mining structure that contains the model that you will test.</span></span>  
  
 <span data-ttu-id="09cc6-109">**Seleccionar estructura**</span><span class="sxs-lookup"><span data-stu-id="09cc6-109">**Select Structure**</span></span>  
 <span data-ttu-id="09cc6-110">Haga clic para abrir el cuadro de diálogo **Seleccionar estructura de minería de datos** y seleccione una estructura de minería de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="09cc6-110">Click to open the **Select Mining Structure** dialog box and select a different mining structure.</span></span>  
  
 <span data-ttu-id="09cc6-111">**Seleccionar tabla(s) de entrada**</span><span class="sxs-lookup"><span data-stu-id="09cc6-111">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="09cc6-112">Muestra las tablas de entrada seleccionadas que se usan para generar el gráfico de elevación.</span><span class="sxs-lookup"><span data-stu-id="09cc6-112">Displays the selected input tables that are used to generate the lift chart.</span></span> <span data-ttu-id="09cc6-113">Seleccione la tabla que contiene los datos de prueba que va a utilizar para probar la precisión de los modelos.</span><span class="sxs-lookup"><span data-stu-id="09cc6-113">Select the table that contains the test data that you will use to test the accuracy of the models.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09cc6-114">Si el panel no contiene ninguna tabla, haga clic en **Seleccionar tabla de casos** para agregar las tablas de una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="09cc6-114">If the pane does not contain any tables, click **Select Case Table** to add tables from a data source view.</span></span>  
  
 <span data-ttu-id="09cc6-115">**Quitar tabla**</span><span class="sxs-lookup"><span data-stu-id="09cc6-115">**Remove Table**</span></span>  
 <span data-ttu-id="09cc6-116">Quita la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="09cc6-116">Removes the selected table.</span></span> <span data-ttu-id="09cc6-117">Este botón está deshabilitado si no se ha seleccionado una tabla o si no se muestra ninguna tabla en la lista **Seleccionar tabla(s) de entrada** .</span><span class="sxs-lookup"><span data-stu-id="09cc6-117">This button is disabled if a table has not been selected or if no tables are displayed in the **Select Input Tables** list.</span></span>  
  
 <span data-ttu-id="09cc6-118">**Seleccionar tabla de casos**</span><span class="sxs-lookup"><span data-stu-id="09cc6-118">**Select Case Table**</span></span>  
 <span data-ttu-id="09cc6-119">Haga clic para abrir el cuadro de diálogo **Seleccionar tabla** y seleccione una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="09cc6-119">Click to open the **Select Table** dialog box and select a data source view.</span></span>  
  
 <span data-ttu-id="09cc6-120">**Nota** : este botón solo aparece si no se ha seleccionado una tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="09cc6-120">**Note** This button appears only if a case table has not been selected.</span></span> <span data-ttu-id="09cc6-121">Para habilitar el botón de modo que pueda seleccionar una tabla de casos diferente, borre la lista seleccionando todas las tablas existentes y haciendo clic en **Quitar tabla**.</span><span class="sxs-lookup"><span data-stu-id="09cc6-121">To enable the button so that you can select a different case table, clear the list by selecting all existing tables and then clicking **Remove Table**.</span></span>  
  
 <span data-ttu-id="09cc6-122">**Seleccionar tabla anidada**</span><span class="sxs-lookup"><span data-stu-id="09cc6-122">**Select Nested Table**</span></span>  
 <span data-ttu-id="09cc6-123">Abre el cuadro de diálogo **Seleccionar tabla** .</span><span class="sxs-lookup"><span data-stu-id="09cc6-123">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="09cc6-124">Este botón solo aparece si se ha seleccionado una tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="09cc6-124">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="09cc6-125">Este botón se deshabilita si la estructura de minería de datos asociada no contiene una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="09cc6-125">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="09cc6-126">**Modificar combinación**</span><span class="sxs-lookup"><span data-stu-id="09cc6-126">**Modify Join**</span></span>  
 <span data-ttu-id="09cc6-127">Abre el cuadro de diálogo **Especificar combinación anidada** .</span><span class="sxs-lookup"><span data-stu-id="09cc6-127">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="09cc6-128">Este botón solo está activo si se ha seleccionado una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="09cc6-128">This button is active only if the nested table is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09cc6-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09cc6-129">See Also</span></span>  
 <span data-ttu-id="09cc6-130">[Tareas y procedimientos de prueba y validación &#40;&#41;de minería de datos](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="09cc6-130">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="09cc6-131">Diseñador de gráficos de precisión de minería de datos &#40;&#41;de minería de datos</span><span class="sxs-lookup"><span data-stu-id="09cc6-131">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
