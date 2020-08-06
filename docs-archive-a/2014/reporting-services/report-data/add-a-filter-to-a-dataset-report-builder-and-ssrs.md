---
title: Agregar un filtro a un conjunto de datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eed37e74-6a43-4d7c-9959-2d5fa6a6aba9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f51411d31d8ee29bf0f163085077dcee8fd79bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662607"
---
# <a name="add-a-filter-to-a-dataset-report-builder-and-ssrs"></a><span data-ttu-id="e5e01-102">Agregar un filtro a un conjunto de datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="e5e01-102">Add a Filter to a Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e5e01-103">Agregue un filtro a un conjunto de datos para limitar los datos en un informe una vez recuperados de un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="e5e01-103">Add a filter to a dataset to limit the data in a report after the data is retrieved from an external data source.</span></span> <span data-ttu-id="e5e01-104">Al agregar un filtro a un conjunto de datos, todos los elementos de informe o regiones de datos usan solo los datos que cumplen las condiciones del filtro.</span><span class="sxs-lookup"><span data-stu-id="e5e01-104">When you add a filter to a dataset, all report parts or data regions use only data that matches the filter conditions.</span></span>  
  
 <span data-ttu-id="e5e01-105">En el caso de un conjunto de datos compartido, un filtro que se aplica a todos los elementos dependientes debe formar parte de la definición del conjunto de datos compartida en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e5e01-105">For a shared dataset, a filter that applies to all dependent items must be part of the shared dataset definition on the report server.</span></span> <span data-ttu-id="e5e01-106">Un informe o elemento de informe que contenga una instancia de un conjunto de datos compartido puede crear un filtro adicional que se aplique solo a esa instancia.</span><span class="sxs-lookup"><span data-stu-id="e5e01-106">A report or report part that contains an instance of a shared dataset can create an additional filter that applies only to the instance.</span></span>  
  
 <span data-ttu-id="e5e01-107">Para agregar un filtro, debe especificar una o varias condiciones que son las ecuaciones del filtro.</span><span class="sxs-lookup"><span data-stu-id="e5e01-107">To add a filter, you must specify one or more conditions that are filter equations.</span></span> <span data-ttu-id="e5e01-108">Una ecuación de filtro se compone de una expresión que identifica los datos que se van a filtrar, un operador y el valor con el que se va a llevar a cabo la comparación.</span><span class="sxs-lookup"><span data-stu-id="e5e01-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="e5e01-109">Los tipos de datos de los datos filtrados y el valor deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="e5e01-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="e5e01-110">No está permitido el filtrado por valores agregados para un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e5e01-110">Filtering on aggregate values for a dataset is not supported.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-filter-to-a-shared-dataset"></a><span data-ttu-id="e5e01-111">Para agregar un filtro a un conjunto de datos compartido</span><span class="sxs-lookup"><span data-stu-id="e5e01-111">To add a filter to a shared dataset</span></span>  
  
1.  <span data-ttu-id="e5e01-112">Abra un conjunto de datos compartido en modo de conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="e5e01-112">Open a shared dataset in shared dataset mode.</span></span>  
  
2.  <span data-ttu-id="e5e01-113">En la pestaña **Inicio** , en el grupo **Conjuntos de datos compartidos** , haga clic en Conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="e5e01-113">On the **Home** tab, in the **Shared Datasets** group, click Datasets.</span></span> <span data-ttu-id="e5e01-114">Se abre el cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="e5e01-114">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e5e01-115">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="e5e01-115">Click **Filters**.</span></span> <span data-ttu-id="e5e01-116">Aparece la lista actual de ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="e5e01-116">This displays the current list of filter equations.</span></span> <span data-ttu-id="e5e01-117">La lista aparece vacía de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e5e01-117">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="e5e01-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e5e01-118">Click **Add**.</span></span> <span data-ttu-id="e5e01-119">Aparece una nueva ecuación de filtro en blanco.</span><span class="sxs-lookup"><span data-stu-id="e5e01-119">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="e5e01-120">En **Expresión**, escriba o seleccione la expresión para el campo que va a filtrar.</span><span class="sxs-lookup"><span data-stu-id="e5e01-120">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="e5e01-121">Para editar la expresión, haga clic en el botón de expresión (*fx*).</span><span class="sxs-lookup"><span data-stu-id="e5e01-121">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="e5e01-122">En el cuadro de lista, seleccione el tipo de datos que coincide con el tipo de datos de la expresión que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="e5e01-122">From the list box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="e5e01-123">En el cuadro **Operador** , seleccione el operador que deberá usar el filtro para comparar los valores de los cuadros **Expresión** y **Valor** .</span><span class="sxs-lookup"><span data-stu-id="e5e01-123">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="e5e01-124">El operador que elija determinará el número de valores que se usarán en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5e01-124">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="e5e01-125">En el cuadro **Valor** , escriba la expresión o el valor que deberá usar el filtro para evaluar el valor de **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="e5e01-125">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="e5e01-126">Para obtener ejemplos de ecuaciones de filtro, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e5e01-126">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-filter-to-an-embedded-dataset-or-a-shared-dataset-instance"></a><span data-ttu-id="e5e01-127">Para agregar un filtro a un conjunto de datos incrustado o una instancia de conjunto de datos compartido</span><span class="sxs-lookup"><span data-stu-id="e5e01-127">To add a filter to an embedded dataset or a shared dataset instance</span></span>  
  
1.  <span data-ttu-id="e5e01-128">Abra un informe en el modo de diseño de informes.</span><span class="sxs-lookup"><span data-stu-id="e5e01-128">Open a report in report design mode.</span></span>  
  
2.  <span data-ttu-id="e5e01-129">En el panel **Datos de informe** , haga clic con el botón derecho en un conjunto de datos y, después, haga clic en **Propiedades del conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="e5e01-129">Right-click a dataset in the **Report Data** pane and then click **Dataset Properties**.</span></span> <span data-ttu-id="e5e01-130">Se abre el cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="e5e01-130">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e5e01-131">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="e5e01-131">Click **Filters**.</span></span> <span data-ttu-id="e5e01-132">Aparece la lista actual de ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="e5e01-132">This displays the current list of filter equations.</span></span> <span data-ttu-id="e5e01-133">La lista aparece vacía de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e5e01-133">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="e5e01-134">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e5e01-134">Click **Add**.</span></span> <span data-ttu-id="e5e01-135">Aparece una nueva ecuación de filtro en blanco.</span><span class="sxs-lookup"><span data-stu-id="e5e01-135">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="e5e01-136">En **Expresión**, escriba o seleccione la expresión para el campo que va a filtrar.</span><span class="sxs-lookup"><span data-stu-id="e5e01-136">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="e5e01-137">Para editar la expresión, haga clic en el botón de expresión (*fx*).</span><span class="sxs-lookup"><span data-stu-id="e5e01-137">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="e5e01-138">En la lista desplegable, seleccione el tipo de datos que coincide con el tipo de datos de la expresión que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="e5e01-138">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="e5e01-139">En el cuadro **Operador** , seleccione el operador que deberá usar el filtro para comparar los valores de los cuadros **Expresión** y **Valor** .</span><span class="sxs-lookup"><span data-stu-id="e5e01-139">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="e5e01-140">El operador que elija determinará el número de valores que se usarán en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5e01-140">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="e5e01-141">En el cuadro **Valor** , escriba la expresión o el valor que deberá usar el filtro para evaluar el valor de **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="e5e01-141">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="e5e01-142">Para obtener ejemplos de ecuaciones de filtro, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e5e01-142">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e5e01-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5e01-143">See Also</span></span>  
 <span data-ttu-id="e5e01-144">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="e5e01-144">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="e5e01-145">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e5e01-145">[Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e5e01-146">Agregar un filtro &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e5e01-146">Add a Filter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/add-a-filter-report-builder-and-ssrs.md)  
  
  
