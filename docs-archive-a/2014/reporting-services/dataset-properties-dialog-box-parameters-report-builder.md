---
title: Propiedades del conjunto de propiedades (cuadro de diálogo), parámetros (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10023"
ms.assetid: 3a0672ad-c969-455b-b952-585164ce1dda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ef038e7cbf113556b11af9a0e6c59aa190b2400b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677437"
---
# <a name="dataset-properties-dialog-box-parameters-report-builder"></a><span data-ttu-id="2484a-102">Propiedades del conjunto de datos (cuadro de diálogo), Parámetros (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="2484a-102">Dataset Properties Dialog Box, Parameters (Report Builder)</span></span>
  <span data-ttu-id="2484a-103">Seleccione **parámetros** en el cuadro de diálogo **propiedades del conjunto de propiedades** para agregar, cambiar y eliminar parámetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="2484a-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters.</span></span>  
  
 <span data-ttu-id="2484a-104">Para un conjunto de datos incrustado, las opciones se aplican al conjunto de datos de la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="2484a-104">For an embedded dataset, options apply to the dataset in the report definition.</span></span>  
  
 <span data-ttu-id="2484a-105">Para un conjunto de datos compartido, las opciones se aplican a la definición del conjunto de datos compartido del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2484a-105">For a shared dataset, options apply to the shared dataset definition on the report server.</span></span>  
  
 <span data-ttu-id="2484a-106">Para más información, vea [Conjuntos de datos incrustados y compartidos &#40;Generador de informes y SSRS&#41;](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2484a-106">For more information, see [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2484a-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="2484a-107">Options</span></span>  
 <span data-ttu-id="2484a-108">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="2484a-108">**Add**</span></span>  
 <span data-ttu-id="2484a-109">Agrega un parámetro nuevo a la lista.</span><span class="sxs-lookup"><span data-stu-id="2484a-109">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="2484a-110">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="2484a-110">**Delete**</span></span>  
 <span data-ttu-id="2484a-111">Quita el parámetro seleccionado de la lista.</span><span class="sxs-lookup"><span data-stu-id="2484a-111">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="2484a-112">**Flecha arriba**</span><span class="sxs-lookup"><span data-stu-id="2484a-112">**Up arrow**</span></span>  
 <span data-ttu-id="2484a-113">Mueve el parámetro seleccionado hacia arriba en la lista.</span><span class="sxs-lookup"><span data-stu-id="2484a-113">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="2484a-114">**Flecha abajo**</span><span class="sxs-lookup"><span data-stu-id="2484a-114">**Down arrow**</span></span>  
 <span data-ttu-id="2484a-115">Mueve el parámetro seleccionado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="2484a-115">Move the selected parameter down in the list.</span></span>  
  
 <span data-ttu-id="2484a-116">**Nombre del parámetro**</span><span class="sxs-lookup"><span data-stu-id="2484a-116">**Parameter name**</span></span>  
 <span data-ttu-id="2484a-117">Escriba el nombre de un parámetro de consulta que agregó al conjunto de datos en la pestaña **Consulta** del cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="2484a-117">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="2484a-118">**Valor del parámetro**</span><span class="sxs-lookup"><span data-stu-id="2484a-118">**Parameter value**</span></span>  
 <span data-ttu-id="2484a-119">Para conjuntos de datos incrustados únicamente.</span><span class="sxs-lookup"><span data-stu-id="2484a-119">For embedded datasets only.</span></span>  
  
 <span data-ttu-id="2484a-120">Escriba un valor para el parámetro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="2484a-120">Enter a value for the query parameter.</span></span> <span data-ttu-id="2484a-121">Puede ser un valor estático o una expresión que haga referencia a un objeto del informe, pero no puede hacer referencia a elementos o campos de informe.</span><span class="sxs-lookup"><span data-stu-id="2484a-121">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="2484a-122">De forma predeterminada, **Valor** contiene una expresión que apunta a un parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="2484a-122">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="2484a-123">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="2484a-123">**Default value**</span></span>  
 <span data-ttu-id="2484a-124">Para conjuntos de datos compartidos únicamente.</span><span class="sxs-lookup"><span data-stu-id="2484a-124">For shared datasets only.</span></span>  
  
 <span data-ttu-id="2484a-125">Active la casilla para especificar un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2484a-125">Select the check box to specify a default value.</span></span>  
  
 <span data-ttu-id="2484a-126">Escriba un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2484a-126">Enter a default value.</span></span> <span data-ttu-id="2484a-127">Puede ser un valor estático o una expresión que haga referencia a un objeto del informe.</span><span class="sxs-lookup"><span data-stu-id="2484a-127">This can be a static value or an expression that refers to an object within the report.</span></span> <span data-ttu-id="2484a-128">La expresión no puede hacer referencia a elementos de informe, parámetros de informe ni campos.</span><span class="sxs-lookup"><span data-stu-id="2484a-128">The expression cannot refer to report items, report parameters, or fields.</span></span>  
  
 <span data-ttu-id="2484a-129">Para especificar un espacio en blanco, deje el cuadro de texto vacío.</span><span class="sxs-lookup"><span data-stu-id="2484a-129">To specify a blank, leave the text box empty.</span></span>  
  
 <span data-ttu-id="2484a-130">Para especificar un valor nulo, seleccione la opción de aceptación de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="2484a-130">To specify a null, select the Nullable option.</span></span>  
  
 <span data-ttu-id="2484a-131">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="2484a-131">**Read Only**</span></span>  
 <span data-ttu-id="2484a-132">Para conjuntos de datos compartidos únicamente.</span><span class="sxs-lookup"><span data-stu-id="2484a-132">For shared datasets only.</span></span>  
  
 <span data-ttu-id="2484a-133">Seleccione esta opción para marcar este parámetro como de solo lectura en la definición del conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="2484a-133">Select this option to mark this parameter read only in the shared dataset definition.</span></span> <span data-ttu-id="2484a-134">Cuando el conjunto de datos compartido se agrega a un informe, el parámetro no aparece en las propiedades.</span><span class="sxs-lookup"><span data-stu-id="2484a-134">When the shared dataset is added to a report, the parameter does not appear in the properties.</span></span> <span data-ttu-id="2484a-135">Cuando el conjunto de datos compartido está almacenado en la memoria caché del servidor de informes, el valor no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="2484a-135">When the shared dataset is cached on the report server, the value cannot be changed.</span></span>  
  
 <span data-ttu-id="2484a-136">**Admisión de valores NULL**</span><span class="sxs-lookup"><span data-stu-id="2484a-136">**Nullable**</span></span>  
 <span data-ttu-id="2484a-137">Para conjuntos de datos compartidos únicamente.</span><span class="sxs-lookup"><span data-stu-id="2484a-137">For shared datasets only.</span></span>  
  
 <span data-ttu-id="2484a-138">Seleccione esta opción para admitir un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="2484a-138">Select this option to allow a null value.</span></span>  
  
 <span data-ttu-id="2484a-139">**Omitir en la consulta**</span><span class="sxs-lookup"><span data-stu-id="2484a-139">**Omit From Query**</span></span>  
 <span data-ttu-id="2484a-140">Para conjuntos de datos compartidos únicamente.</span><span class="sxs-lookup"><span data-stu-id="2484a-140">For shared datasets only.</span></span>  
  
 <span data-ttu-id="2484a-141">Seleccione esta opción cuando una referencia a un parámetro de informe esté en una expresión en el filtro del conjunto de datos compartido y no en la consulta.</span><span class="sxs-lookup"><span data-stu-id="2484a-141">Select this option when a reference to a report parameter is in an expression in the shared dataset filter and not in the query.</span></span> <span data-ttu-id="2484a-142">Al seleccionar esta opción, no necesita especificar un valor predeterminado para este parámetro cuando se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="2484a-142">When you select this option, you do not need to specify a default value for this parameter when the query runs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2484a-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2484a-143">See Also</span></span>  
 <span data-ttu-id="2484a-144">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-144">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="2484a-145">[Cuadro de diálogo Propiedades del conjunto de propiedades, &#40;de consultas Generador de informes&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-145">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="2484a-146">[Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-146">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2484a-147">[Tutorial: agregar un parámetro a un informe &#40;Generador de informes&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-147">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="2484a-148">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-148">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="2484a-149">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-149">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2484a-150">[Diseñadores de consultas &#40;Generador de informes&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-150">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="2484a-151">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2484a-151">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2484a-152">Crear un conjunto de datos compartido o un conjunto de datos incrustado &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2484a-152">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
  
