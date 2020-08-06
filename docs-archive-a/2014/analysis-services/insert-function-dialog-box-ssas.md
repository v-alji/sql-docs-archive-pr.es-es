---
title: Cuadro de diálogo Insertar función (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- SQL12.ASVS.BIDTOOLSET.INSERTFUNCTIONDB.F1
ms.assetid: c4b36d8f-2328-45f7-8bd4-cc0111571e25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0d92dd34e671dc026215d79e7eaed88bebfac15f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673395"
---
# <a name="insert-function-dialog-box-ssas"></a><span data-ttu-id="64286-102">Cuadro de diálogo Insertar función (SSAS)</span><span class="sxs-lookup"><span data-stu-id="64286-102">Insert Function Dialog Box (SSAS)</span></span>
  <span data-ttu-id="64286-103">El cuadro de diálogo **Insertar función** le permite elegir funciones en una lista y usarlas para generar fórmulas.</span><span class="sxs-lookup"><span data-stu-id="64286-103">The **Insert Function** dialog box enables you to choose from a list of functions that can be used when building formulas.</span></span> <span data-ttu-id="64286-104">Para obtener acceso a este cuadro de diálogo desde el diseñador de modelos, haga clic en el botón de función (**fx**) de la barra de fórmulas situada encima de cada tabla.</span><span class="sxs-lookup"><span data-stu-id="64286-104">To access this dialog box from the model designer, in the formula bar above each table, click the function (**fx**) button.</span></span> <span data-ttu-id="64286-105">Para obtener más información sobre cómo elegir las funciones que puede usar en las fórmulas, vea Introducción a DAX y Generar una fórmula.</span><span class="sxs-lookup"><span data-stu-id="64286-105">For more information about choosing functions to use in formulas, see DAX Introduction and Build a Formula.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64286-106">Elemento</span><span class="sxs-lookup"><span data-stu-id="64286-106">Item</span></span>|<span data-ttu-id="64286-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="64286-107">Description</span></span>|  
|<span data-ttu-id="64286-108">**Seleccionar una categoría**</span><span class="sxs-lookup"><span data-stu-id="64286-108">**Select a category**</span></span>|<span data-ttu-id="64286-109">Si tiene una idea general de qué tipo de función necesita, elija una categoría en la lista o seleccione **Todos** para ver una lista alfabética de funciones.</span><span class="sxs-lookup"><span data-stu-id="64286-109">If you have a general idea which kind of function you need, choose a category from the list; or select **All** to view an alphabetical list of functions.</span></span>|  
|<span data-ttu-id="64286-110">**Selección de una función**</span><span class="sxs-lookup"><span data-stu-id="64286-110">**Select a function**</span></span>|<span data-ttu-id="64286-111">Muestra una lista de las funciones en la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64286-111">Displays a list of the functions in the selected category.</span></span>|  
|<span data-ttu-id="64286-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="64286-112">**Description**</span></span>|<span data-ttu-id="64286-113">Muestra una descripción de lo que hace la función, junto con cualquier argumento obligatorio u opcional, como nombres de columna y expresiones.</span><span class="sxs-lookup"><span data-stu-id="64286-113">Displays a description of what the function does, together with any required or optional arguments, such as column names and expressions.</span></span>|  
  
## <a name="function-categories"></a><span data-ttu-id="64286-114">Categorías de funciones</span><span class="sxs-lookup"><span data-stu-id="64286-114">Function Categories</span></span>  
 <span data-ttu-id="64286-115">DAX (Expresiones de análisis de datos) proporciona los siguientes tipos de categorías de función en el cuadro de diálogo **Insertar función** .</span><span class="sxs-lookup"><span data-stu-id="64286-115">Data Analysis Expressions (DAX) provides the following types of function categories in the **Insert Functions** dialog box.</span></span>  
  
 <span data-ttu-id="64286-116">All</span><span class="sxs-lookup"><span data-stu-id="64286-116">All</span></span>  
  
 <span data-ttu-id="64286-117">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="64286-117">Date & Time</span></span>  
  
 <span data-ttu-id="64286-118">Filter</span><span class="sxs-lookup"><span data-stu-id="64286-118">Filter</span></span>  
  
 <span data-ttu-id="64286-119">Lógicos</span><span class="sxs-lookup"><span data-stu-id="64286-119">Logical</span></span>  
  
 <span data-ttu-id="64286-120">Matemáticas y trigonométricas</span><span class="sxs-lookup"><span data-stu-id="64286-120">Math & Trig</span></span>  
  
 <span data-ttu-id="64286-121">Estadística</span><span class="sxs-lookup"><span data-stu-id="64286-121">Statistical</span></span>  
  
 <span data-ttu-id="64286-122">Texto</span><span class="sxs-lookup"><span data-stu-id="64286-122">Text</span></span>  
  
## <a name="measures-and-formulas"></a><span data-ttu-id="64286-123">Medidas y fórmulas</span><span class="sxs-lookup"><span data-stu-id="64286-123">Measures and Formulas</span></span>  
 <span data-ttu-id="64286-124">El cuadro de diálogo **Insertar función** solo está disponible cuando se está generando una fórmula.</span><span class="sxs-lookup"><span data-stu-id="64286-124">The **Insert Function** dialog box is available only when you are building a formula.</span></span> <span data-ttu-id="64286-125">Puede crear los cálculos en una columna calculada, en una tabla dinámica o en un gráfico dinámico.</span><span class="sxs-lookup"><span data-stu-id="64286-125">You can create calculations either in a calculated column, or in a PivotTable or PivotChart.</span></span> <span data-ttu-id="64286-126">Las fórmulas que genera expresamente para usarse en una tabla dinámica también se denominan *medidas*.</span><span class="sxs-lookup"><span data-stu-id="64286-126">Formulas that you build expressly for use in a PivotTable are also called *measures*.</span></span> <span data-ttu-id="64286-127">Para obtener más información, vea [Crear una columna calculada &#40;SSAS tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) y [Crear y administrar medidas &#40;SSAS tabular&#41;](tabular-models/measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="64286-127">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) and [Create and Manage Measures &#40;SSAS Tabular&#41;](tabular-models/measures-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64286-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64286-128">See Also</span></span>  
 [<span data-ttu-id="64286-129">Cálculos &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="64286-129">Calculations &#40;SSAS Tabular&#41;</span></span>](tabular-models/calculations-ssas-tabular.md)  
  
  
