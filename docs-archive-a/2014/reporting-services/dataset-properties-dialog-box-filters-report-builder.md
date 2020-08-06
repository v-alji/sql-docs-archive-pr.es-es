---
title: Cuadro de diálogo Propiedades del conjunto de propiedades, filtros (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10025"
ms.assetid: 933a6f44-4eb7-4e73-9c40-ac0fd17b23d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7bc13b0eeff1eaf27fb0ec0c4279ff00d0809e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669529"
---
# <a name="dataset-properties-dialog-box-filters-report-builder"></a><span data-ttu-id="7aea9-102">Propiedades del conjunto de datos (cuadro de diálogo), Filtros (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="7aea9-102">Dataset Properties Dialog Box, Filters (Report Builder)</span></span>
  <span data-ttu-id="7aea9-103">Seleccione **Filtros** en el cuadro de diálogo **Propiedades del conjunto de datos** para crear filtros para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="7aea9-103">Select **Filters** on the **Dataset Properties** dialog box to create filters for the dataset.</span></span>  
  
 <span data-ttu-id="7aea9-104">Los filtros que forman parte de una definición de conjunto de datos compartido en el servidor de informes afectan a todos los informes que utilizan el conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="7aea9-104">Filters that are part of a shared dataset definition on the report server affect all reports that use the shared dataset.</span></span> <span data-ttu-id="7aea9-105">Los filtros adicionales para el conjunto de datos compartido se pueden especificar una vez agregado a un informe.</span><span class="sxs-lookup"><span data-stu-id="7aea9-105">Additional filters for the shared dataset can be specified after it is added to a report.</span></span> <span data-ttu-id="7aea9-106">Estos filtros solo afectan al informe en el que se definen.</span><span class="sxs-lookup"><span data-stu-id="7aea9-106">These filters affect only the report in which they are defined.</span></span>  
  
 <span data-ttu-id="7aea9-107">Los filtros para un conjunto de datos incrustado solo afectan al informe en el que se definen.</span><span class="sxs-lookup"><span data-stu-id="7aea9-107">Filters for an embedded dataset affect only the report in which they are defined.</span></span>  
  
 <span data-ttu-id="7aea9-108">Para obtener más información, vea [Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7aea9-108">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7aea9-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="7aea9-109">Options</span></span>  
 <span data-ttu-id="7aea9-110">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="7aea9-110">**Add**</span></span>  
 <span data-ttu-id="7aea9-111">Agrega una nueva cláusula de filtro a la lista.</span><span class="sxs-lookup"><span data-stu-id="7aea9-111">Add a new filter clause to the list.</span></span>  
  
 <span data-ttu-id="7aea9-112">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="7aea9-112">**Delete**</span></span>  
 <span data-ttu-id="7aea9-113">Elimina de la lista la cláusula de filtro seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7aea9-113">Delete the selected filter clause from the list.</span></span>  
  
 <span data-ttu-id="7aea9-114">**Flecha arriba**</span><span class="sxs-lookup"><span data-stu-id="7aea9-114">**Up arrow**</span></span>  
 <span data-ttu-id="7aea9-115">Mueve el filtro seleccionado hacia arriba en la lista.</span><span class="sxs-lookup"><span data-stu-id="7aea9-115">Move the selected filter up in the list.</span></span>  
  
 <span data-ttu-id="7aea9-116">**Flecha abajo**</span><span class="sxs-lookup"><span data-stu-id="7aea9-116">**Down arrow**</span></span>  
 <span data-ttu-id="7aea9-117">Mueve el filtro seleccionado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="7aea9-117">Move the selected filter down in the list</span></span>  
  
 <span data-ttu-id="7aea9-118">**Expression**</span><span class="sxs-lookup"><span data-stu-id="7aea9-118">**Expression**</span></span>  
 <span data-ttu-id="7aea9-119">Escriba o elija la expresión a la que desea aplicar un filtro.</span><span class="sxs-lookup"><span data-stu-id="7aea9-119">Type or choose the expression to which you want to apply a filter.</span></span> <span data-ttu-id="7aea9-120">Haga clic en el botón Expresión (**fx**) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="7aea9-120">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
 <span data-ttu-id="7aea9-121">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7aea9-121">**Data type**</span></span>  
 <span data-ttu-id="7aea9-122">Elija el tipo de datos para **Valor**.</span><span class="sxs-lookup"><span data-stu-id="7aea9-122">Choose the data type for **Value**.</span></span> <span data-ttu-id="7aea9-123">Si es posible, elija un tipo de datos que coincida con el tipo de datos de **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="7aea9-123">When possible, choose a data type that matches the data type for **Expression**.</span></span>  
  
 <span data-ttu-id="7aea9-124">Los valores de **Expresión** y de **Valor** deben devolver el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="7aea9-124">The values in **Expression** and **Value** must evaluate to the same data type.</span></span> <span data-ttu-id="7aea9-125">Por ejemplo, si **Expresión** se establece en un campo que tiene el tipo de datos System.Int32 y **Valor** se establece en 7, en la lista desplegable, elija **Integer**.</span><span class="sxs-lookup"><span data-stu-id="7aea9-125">For example, if **Expression** is set to a field that has the data type System.Int32 and **Value** is set to 7, from the drop-down list, choose **Integer**.</span></span>  
  
 <span data-ttu-id="7aea9-126">Si la opción de tipos de datos que necesita no está en la lista desplegable, escriba una expresión que convierta el valor al tipo de datos correcto.</span><span class="sxs-lookup"><span data-stu-id="7aea9-126">If the data type option you need is not in the drop-down list, write an expression to convert the value to the correct data type.</span></span> <span data-ttu-id="7aea9-127">Para más información, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7aea9-127">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="7aea9-128">**Operador**</span><span class="sxs-lookup"><span data-stu-id="7aea9-128">**Operator**</span></span>  
 <span data-ttu-id="7aea9-129">Elija el operador que se va a utilizar para comparar la expresión y el valor.</span><span class="sxs-lookup"><span data-stu-id="7aea9-129">Choose the operator to use to compare the expression and the value.</span></span>  
  
 <span data-ttu-id="7aea9-130">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7aea9-130">**Value**</span></span>  
 <span data-ttu-id="7aea9-131">Escriba la expresión o el valor que se debe usar al evaluar la expresión especificada en el cuadro **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="7aea9-131">Type the expression or value to use when evaluating the expression specified in the **Expression** box.</span></span> <span data-ttu-id="7aea9-132">Haga clic en el botón Expresión (**fx**) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="7aea9-132">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aea9-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7aea9-133">See Also</span></span>  
 <span data-ttu-id="7aea9-134">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7aea9-134">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7aea9-135">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7aea9-135">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="7aea9-136">[Agregar un filtro a un conjunto de &#40;Generador de informes y SSRS&#41;](report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7aea9-136">[Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7aea9-137">Usar expresiones en informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7aea9-137">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
