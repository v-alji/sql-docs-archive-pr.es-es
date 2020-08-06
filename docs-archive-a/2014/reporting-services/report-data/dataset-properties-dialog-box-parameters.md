---
title: Propiedades del conjunto de datos (cuadro de diálogo), parámetros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10150"
- sql12.rtp.rptdesigner.datasetproperties.parameters.f1
ms.assetid: 43b00aab-e2c3-4e85-abe1-a2b5a21efeed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0073971de373321ce347f416657671e1f497dd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751789"
---
# <a name="dataset-properties-dialog-box-parameters"></a><span data-ttu-id="6db0b-102">Propiedades del conjunto de datos (cuadro de diálogo), Parámetros</span><span class="sxs-lookup"><span data-stu-id="6db0b-102">Dataset Properties Dialog Box, Parameters</span></span>
  <span data-ttu-id="6db0b-103">Seleccione **Parámetros** en el cuadro de diálogo **Propiedades del conjunto de datos** para agregar, cambiar y eliminar parámetros de la consulta, incluso los que vinculan a los parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="6db0b-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters, including query parameters that link to report parameters.</span></span>  
  
 <span data-ttu-id="6db0b-104">Siempre que se modifica la consulta en la pestaña de consulta, se analiza el comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="6db0b-104">Whenever the query is changed on the query tab, the query command is parsed.</span></span> <span data-ttu-id="6db0b-105">Para cada parámetro de consulta que se identifica, se crea un parámetro de informe con un nombre idéntico que distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6db0b-105">For each query parameter that is identified, a report parameter with an identical case-sensitive name is created.</span></span> <span data-ttu-id="6db0b-106">De forma predeterminada, el parámetro de la consulta se agrega automáticamente a la lista de parámetros de la consulta y se vincula al parámetro de informe correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6db0b-106">By default, the query parameter is automatically added to the query parameter list and linked to the corresponding report parameter.</span></span>  
  
 <span data-ttu-id="6db0b-107">Si los valores predeterminados de un parámetro de informe tienen dependencias en otro parámetro de informe vinculado a un parámetro de la consulta, el orden de los parámetros de informe (tal como aparecen en el cuadro de diálogo **Propiedades de parámetro de informe** ) es importante.</span><span class="sxs-lookup"><span data-stu-id="6db0b-107">If there are dependencies for the default values of one report parameter on another report parameter that is linked to a query parameter, the order of report parameters (as they appear in the **Report Parameters Properties** dialog box) is important.</span></span> <span data-ttu-id="6db0b-108">Los parámetros de informe que figuran más abajo en la lista pueden hacer referencia a los parámetros que les preceden en la lista.</span><span class="sxs-lookup"><span data-stu-id="6db0b-108">Report parameters later in the list can refer to report parameters earlier in the list.</span></span> <span data-ttu-id="6db0b-109">Para más información sobre parámetros de informe, vea [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="6db0b-109">For more information about report parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6db0b-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="6db0b-110">Options</span></span>  
 <span data-ttu-id="6db0b-111">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="6db0b-111">**Add**</span></span>  
 <span data-ttu-id="6db0b-112">Agrega un parámetro nuevo a la lista.</span><span class="sxs-lookup"><span data-stu-id="6db0b-112">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="6db0b-113">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="6db0b-113">**Delete**</span></span>  
 <span data-ttu-id="6db0b-114">Quita el parámetro seleccionado de la lista.</span><span class="sxs-lookup"><span data-stu-id="6db0b-114">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="6db0b-115">**Nombre de parámetro**</span><span class="sxs-lookup"><span data-stu-id="6db0b-115">**Parameter name**</span></span>  
 <span data-ttu-id="6db0b-116">Escriba el nombre de un parámetro de consulta que agregó al conjunto de datos en la pestaña **Consulta** del cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="6db0b-116">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="6db0b-117">**Valor del parámetro**</span><span class="sxs-lookup"><span data-stu-id="6db0b-117">**Parameter value**</span></span>  
 <span data-ttu-id="6db0b-118">Escriba un valor para el parámetro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6db0b-118">Enter a value for the query parameter.</span></span> <span data-ttu-id="6db0b-119">Puede ser un valor estático o una expresión que haga referencia a un objeto del informe, pero no puede hacer referencia a elementos o campos de informe.</span><span class="sxs-lookup"><span data-stu-id="6db0b-119">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="6db0b-120">De forma predeterminada, **Valor** contiene una expresión que apunta a un parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="6db0b-120">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="6db0b-121">**Flecha arriba**</span><span class="sxs-lookup"><span data-stu-id="6db0b-121">**Up arrow**</span></span>  
 <span data-ttu-id="6db0b-122">Mueve el parámetro seleccionado hacia arriba en la lista.</span><span class="sxs-lookup"><span data-stu-id="6db0b-122">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="6db0b-123">**Flecha abajo**</span><span class="sxs-lookup"><span data-stu-id="6db0b-123">**Down arrow**</span></span>  
 <span data-ttu-id="6db0b-124">Mueve el parámetro seleccionado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="6db0b-124">Move the selected parameter down in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db0b-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6db0b-125">See Also</span></span>  
 <span data-ttu-id="6db0b-126">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="6db0b-126">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="6db0b-127">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6db0b-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="6db0b-128">Cambiar el orden de un parámetro de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6db0b-128">Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
  
