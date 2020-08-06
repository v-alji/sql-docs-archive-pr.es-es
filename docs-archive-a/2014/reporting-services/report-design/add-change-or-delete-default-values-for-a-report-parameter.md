---
title: Agregar, cambiar o eliminar valores predeterminados para un parámetro de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10460"
- sql12.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1d50fdbbe42a656ef839785c0968b36c8c829e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672756"
---
# <a name="add-change-or-delete-default-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="7de4e-102">Agregar, cambiar o eliminar valores predeterminados para un parámetro de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="7de4e-102">Add, Change, or Delete Default Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7de4e-103">Después de crear un parámetro de informe, puede proporcionar una lista de valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="7de4e-103">After you create a report parameter, you can provide a list of default values.</span></span> <span data-ttu-id="7de4e-104">Si todos los parámetros tienen un valor predeterminado válido, el informe se ejecuta automáticamente al verlo u obtener su previa por primera vez.</span><span class="sxs-lookup"><span data-stu-id="7de4e-104">If all parameters have a valid default value, the report runs automatically when you first view or preview it.</span></span>  
  
 <span data-ttu-id="7de4e-105">Los parámetros de informe pueden representar uno o varios valores.</span><span class="sxs-lookup"><span data-stu-id="7de4e-105">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="7de4e-106">Para los valores únicos, puede proporcionar un literal o una expresión.</span><span class="sxs-lookup"><span data-stu-id="7de4e-106">For single values, you can provide a literal or expression.</span></span> <span data-ttu-id="7de4e-107">Para los valores múltiples, puede proporcionar una lista estática o una lista procedente de un conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="7de4e-107">For multiple values, you can provide a static list or a list from a report dataset.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="7de4e-108">Después de publicar un informe, puede invalidar los valores predeterminados que define en el informe en la herramienta de creación de informes; para ello, establezca los valores de propiedad de parámetro en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7de4e-108">After you publish a report, you can override the default values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="7de4e-109">También puede proporcionar varios conjuntos de valores de parámetros predeterminados creando informes vinculados.</span><span class="sxs-lookup"><span data-stu-id="7de4e-109">You can also provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="7de4e-110">Para más información, vea  [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="7de4e-110">For more information, see  [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md)</span></span>  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a><span data-ttu-id="7de4e-111">Para agregar o cambiar los valores predeterminados para un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="7de4e-111">To add or change the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="7de4e-112">En el panel Datos de informe, expanda el nodo **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="7de4e-112">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="7de4e-113">Haga clic con el botón derecho en el parámetro y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-113">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="7de4e-114">Se abrirá el cuadro de diálogo **Propiedades de parámetro de informe** .</span><span class="sxs-lookup"><span data-stu-id="7de4e-114">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7de4e-115">Si el panel Datos de informe no es visible, haga clic en **Ver** y, después, haga clic en **Datos de informe**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-115">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="7de4e-116">Haga clic en **Valores predeterminados**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-116">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="7de4e-117">Seleccione una opción predeterminada:</span><span class="sxs-lookup"><span data-stu-id="7de4e-117">Select a default option:</span></span>  
  
    -   <span data-ttu-id="7de4e-118">Para proporcionar manualmente un valor o una lista de valores, haga clic en **Especificar valores**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-118">To manually provide a value or list of values, click **Specify values**.</span></span> <span data-ttu-id="7de4e-119">Haga clic en **Agregar** y, a continuación, especifique el valor en el cuadro de texto **Valor** .</span><span class="sxs-lookup"><span data-stu-id="7de4e-119">Click **Add** and then enter the value in the **Value** text box.</span></span> <span data-ttu-id="7de4e-120">Puede escribir una expresión como valor.</span><span class="sxs-lookup"><span data-stu-id="7de4e-120">You can write an expression for a value.</span></span> <span data-ttu-id="7de4e-121">El tipo de datos debe coincidir con el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="7de4e-121">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="7de4e-122">No se pueden usar nombres de campo en una expresión para un parámetro.</span><span class="sxs-lookup"><span data-stu-id="7de4e-122">Field names cannot be used in an expression for a parameter.</span></span>  
  
         <span data-ttu-id="7de4e-123">Para los parámetros de varios valores, repita este paso cada uno de los valores que desea proporcionar.</span><span class="sxs-lookup"><span data-stu-id="7de4e-123">For multivalue parameters, repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="7de4e-124">El orden de los elementos en esta lista determina el orden en que los verá el usuario en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7de4e-124">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="7de4e-125">Para cambiar el orden de un elemento en la lista, haga clic en el cuadro de texto **Valor** para seleccionar el elemento y, a continuación, use los botones de flecha arriba y flecha abajo para mover el elemento hacia arriba o hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="7de4e-125">To change the order of an item in the list, click the **Value** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="7de4e-126">Para proporcionar el nombre de un conjunto de datos existente que recupere los valores, haga clic en **Obtener valores a partir de una consulta**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-126">To provide the name of an existing dataset that retrieves the values, click **Get values from a query**.</span></span> <span data-ttu-id="7de4e-127">En **Conjunto de datos**, elija el nombre del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="7de4e-127">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="7de4e-128">En **Campo de valor**, elija el nombre del campo que proporciona los valores de parámetro.</span><span class="sxs-lookup"><span data-stu-id="7de4e-128">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a><span data-ttu-id="7de4e-129">Para quitar los valores predeterminados para un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="7de4e-129">To remove the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="7de4e-130">En el panel Datos de informe, expanda el nodo **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="7de4e-130">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="7de4e-131">Haga clic con el botón derecho en el parámetro y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-131">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="7de4e-132">Se abrirá el cuadro de diálogo **Propiedades de parámetro de informe** .</span><span class="sxs-lookup"><span data-stu-id="7de4e-132">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7de4e-133">Haga clic en **Valores predeterminados**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-133">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="7de4e-134">En **Seleccione una de las opciones siguientes**, haga clic en **Ningún valor predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="7de4e-134">In **Select from one of the following options**, click **No default value**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7de4e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7de4e-135">See Also</span></span>  
 <span data-ttu-id="7de4e-136">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7de4e-136">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="7de4e-137">[Agregar parámetros en cascada a un informe &#40;Generador de informes y SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7de4e-137">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7de4e-138">[Tutorial: Agregar un parámetro a un informe &#40;Generador de informes&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="7de4e-138">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="7de4e-139">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7de4e-139">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="7de4e-140">[Usar referencias a la colección de parámetros &#40;generador de informes y SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="7de4e-140">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="7de4e-141">[Cambiar el orden de un parámetro de informe &#40;Generador de informes y SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7de4e-141">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7de4e-142">[Agregar, cambiar o eliminar parámetros de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7de4e-142">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7de4e-143">Expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7de4e-143">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
