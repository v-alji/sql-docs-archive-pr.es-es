---
title: Agregar atributos a dimensiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80551dad-97ac-40d0-90af-b810780321ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76a04c42cc501fdca3e5ceb6481452052966796b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662294"
---
# <a name="adding-attributes-to-dimensions"></a><span data-ttu-id="af247-102">Agregar atributos a dimensiones</span><span class="sxs-lookup"><span data-stu-id="af247-102">Adding Attributes to Dimensions</span></span>
  <span data-ttu-id="af247-103">Ahora que ha definido las dimensiones, puede rellenarlas con atributos que representan cada elemento de datos de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="af247-103">Now that you have defined dimensions, you can populate them with attributes that represent each data element in the dimension.</span></span> <span data-ttu-id="af247-104">Los atributos suelen estar basados en campos de una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="af247-104">Attributes are commonly based on fields from a data source view.</span></span> <span data-ttu-id="af247-105">Al agregar atributos a una dimensión, puede incluir campos de cualquier tabla de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="af247-105">When adding attributes to a dimension, you can include fields from any table in the data source view.</span></span>  
  
 <span data-ttu-id="af247-106">En esta tarea, usará el Diseñador de dimensiones para agregar atributos a las dimensiones Customer y Product.</span><span class="sxs-lookup"><span data-stu-id="af247-106">In this task, you will use Dimension Designer to add attributes to the Customer and Product dimensions.</span></span> <span data-ttu-id="af247-107">La dimensión Customer incluirá atributos basados en campos de las tablas Customer y Geography.</span><span class="sxs-lookup"><span data-stu-id="af247-107">The Customer dimension will include attributes based on fields from both the Customer and Geography tables.</span></span>  
  
## <a name="adding-attributes-to-the-customer-dimension"></a><span data-ttu-id="af247-108">Agregar atributos a la dimensión Customer</span><span class="sxs-lookup"><span data-stu-id="af247-108">Adding Attributes to the Customer Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="af247-109">Para agregar atributos</span><span class="sxs-lookup"><span data-stu-id="af247-109">To add attributes</span></span>  
  
1.  <span data-ttu-id="af247-110">Abra el Diseñador de dimensiones para la dimensión Customer.</span><span class="sxs-lookup"><span data-stu-id="af247-110">Open Dimension Designer for the Customer dimension.</span></span> <span data-ttu-id="af247-111">Para ello, haga doble clic en la dimensión **Customer** del nodo **Dimensiones** del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="af247-111">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="af247-112">En el panel **Atributos** , observe los atributos Customer Key y Geography Key creados mediante el Asistente para cubos.</span><span class="sxs-lookup"><span data-stu-id="af247-112">In the **Attributes** pane, notice the Customer Key and Geography Key attributes that were created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="af247-113">En la barra de herramientas de la pestaña **Estructura de dimensión** , asegúrese de que el icono Zoom para ver las tablas del panel **Vista del origen de datos** está establecido al 100 por cien.</span><span class="sxs-lookup"><span data-stu-id="af247-113">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="af247-114">Arrastre las columnas siguientes de la tabla **Customer** del panel **Vista del origen de datos** al panel **Atributos** :</span><span class="sxs-lookup"><span data-stu-id="af247-114">Drag the following columns from the **Customer** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="af247-115">**BirthDate**</span><span class="sxs-lookup"><span data-stu-id="af247-115">**BirthDate**</span></span>  
  
    -   <span data-ttu-id="af247-116">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="af247-116">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="af247-117">**Mujer**</span><span class="sxs-lookup"><span data-stu-id="af247-117">**Gender**</span></span>  
  
    -   <span data-ttu-id="af247-118">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="af247-118">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="af247-119">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="af247-119">**YearlyIncome**</span></span>  
  
    -   <span data-ttu-id="af247-120">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="af247-120">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="af247-121">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="af247-121">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="af247-122">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="af247-122">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="af247-123">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="af247-123">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="af247-124">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="af247-124">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="af247-125">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="af247-125">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="af247-126">**Teléfono**</span><span class="sxs-lookup"><span data-stu-id="af247-126">**Phone**</span></span>  
  
    -   <span data-ttu-id="af247-127">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="af247-127">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="af247-128">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="af247-128">**CommuteDistance**</span></span>  
  
5.  <span data-ttu-id="af247-129">Arrastre las columnas siguientes de la tabla **Geography** del panel **Vista del origen de datos** al panel **Atributos** :</span><span class="sxs-lookup"><span data-stu-id="af247-129">Drag the following columns from the **Geography** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="af247-130">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="af247-130">**City**</span></span>  
  
    -   <span data-ttu-id="af247-131">**StateProvinceName**</span><span class="sxs-lookup"><span data-stu-id="af247-131">**StateProvinceName**</span></span>  
  
    -   <span data-ttu-id="af247-132">**EnglishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="af247-132">**EnglishCountryRegionName**</span></span>  
  
    -   <span data-ttu-id="af247-133">**PostalCode**</span><span class="sxs-lookup"><span data-stu-id="af247-133">**PostalCode**</span></span>  
  
6.  <span data-ttu-id="af247-134">En el menú Archivo, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="af247-134">On the File menu, click **Save All**.</span></span>  
  
## <a name="adding-attributes-to-the-product-dimension"></a><span data-ttu-id="af247-135">Agregar atributos a la dimensión Product</span><span class="sxs-lookup"><span data-stu-id="af247-135">Adding Attributes to the Product Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="af247-136">Para agregar atributos</span><span class="sxs-lookup"><span data-stu-id="af247-136">To add attributes</span></span>  
  
1.  <span data-ttu-id="af247-137">Abra el Diseñador de dimensiones para la dimensión Product.</span><span class="sxs-lookup"><span data-stu-id="af247-137">Open Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="af247-138">Haga doble clic en la dimensión **Product** en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="af247-138">Double-click the **Product** dimension in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="af247-139">En el panel **Atributos** , observe el atributo Product Key creado mediante el Asistente para cubos.</span><span class="sxs-lookup"><span data-stu-id="af247-139">In the **Attributes** pane, notice the Product Key attribute that was created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="af247-140">En la barra de herramientas de la pestaña **Estructura de dimensión** , asegúrese de que el icono Zoom para ver las tablas del panel **Vista del origen de datos** está establecido al 100 por cien.</span><span class="sxs-lookup"><span data-stu-id="af247-140">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="af247-141">Arrastre las columnas siguientes de la tabla **Product** del panel **Vista del origen de datos** al panel **Atributos** :</span><span class="sxs-lookup"><span data-stu-id="af247-141">Drag the following columns from the **Product** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="af247-142">**StandardCost**</span><span class="sxs-lookup"><span data-stu-id="af247-142">**StandardCost**</span></span>  
  
    -   <span data-ttu-id="af247-143">**Color**</span><span class="sxs-lookup"><span data-stu-id="af247-143">**Color**</span></span>  
  
    -   <span data-ttu-id="af247-144">**SafetyStockLevel**</span><span class="sxs-lookup"><span data-stu-id="af247-144">**SafetyStockLevel**</span></span>  
  
    -   <span data-ttu-id="af247-145">**ReorderPoint**</span><span class="sxs-lookup"><span data-stu-id="af247-145">**ReorderPoint**</span></span>  
  
    -   <span data-ttu-id="af247-146">**ListPrice**</span><span class="sxs-lookup"><span data-stu-id="af247-146">**ListPrice**</span></span>  
  
    -   <span data-ttu-id="af247-147">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="af247-147">**Size**</span></span>  
  
    -   <span data-ttu-id="af247-148">**SizeRange**</span><span class="sxs-lookup"><span data-stu-id="af247-148">**SizeRange**</span></span>  
  
    -   <span data-ttu-id="af247-149">**Peso**</span><span class="sxs-lookup"><span data-stu-id="af247-149">**Weight**</span></span>  
  
    -   <span data-ttu-id="af247-150">**DaysToManufacture**</span><span class="sxs-lookup"><span data-stu-id="af247-150">**DaysToManufacture**</span></span>  
  
    -   <span data-ttu-id="af247-151">**ProductLine**</span><span class="sxs-lookup"><span data-stu-id="af247-151">**ProductLine**</span></span>  
  
    -   <span data-ttu-id="af247-152">**DealerPrice**</span><span class="sxs-lookup"><span data-stu-id="af247-152">**DealerPrice**</span></span>  
  
    -   <span data-ttu-id="af247-153">**Clase**</span><span class="sxs-lookup"><span data-stu-id="af247-153">**Class**</span></span>  
  
    -   <span data-ttu-id="af247-154">**Estilo**</span><span class="sxs-lookup"><span data-stu-id="af247-154">**Style**</span></span>  
  
    -   <span data-ttu-id="af247-155">**ModelName**</span><span class="sxs-lookup"><span data-stu-id="af247-155">**ModelName**</span></span>  
  
    -   <span data-ttu-id="af247-156">**StartDate**</span><span class="sxs-lookup"><span data-stu-id="af247-156">**StartDate**</span></span>  
  
    -   <span data-ttu-id="af247-157">**EndDate**</span><span class="sxs-lookup"><span data-stu-id="af247-157">**EndDate**</span></span>  
  
    -   <span data-ttu-id="af247-158">**Estado**</span><span class="sxs-lookup"><span data-stu-id="af247-158">**Status**</span></span>  
  
5.  <span data-ttu-id="af247-159">En el menú Archivo, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="af247-159">On the File menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="af247-160">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="af247-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="af247-161">Revisar las propiedades de cubo y dimensión</span><span class="sxs-lookup"><span data-stu-id="af247-161">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="af247-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af247-162">See Also</span></span>  
 [<span data-ttu-id="af247-163">Referencia de las propiedades de los atributos de dimensión</span><span class="sxs-lookup"><span data-stu-id="af247-163">Dimension Attribute Properties Reference</span></span>](multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
