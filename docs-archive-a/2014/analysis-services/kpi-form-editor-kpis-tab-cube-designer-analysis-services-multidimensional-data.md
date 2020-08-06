---
title: Editor de formulario de KPI (pestaña KPI, diseñador de cubos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpidefinitionpane.f1
ms.assetid: 45c6453a-bbe2-4ca5-836e-c7ef11cfcb65
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c88d6fcec60634f37ddad8b6d0f5cb2124fa1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669944"
---
# <a name="kpi-form-editor-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="dfbd8-102">Editor de Formulario de KPI (pestaña KPI, Diseñador de cubos) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="dfbd8-102">KPI Form Editor (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="dfbd8-103">Use el panel **Editor de Formulario de KPI** de la pestaña **KPI** del Diseñador de cubos para crear o modificar el indicador clave de rendimiento (KPI) seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-103">Use the **KPI Form Editor** pane on the **KPIs** tab in Cube Designer to create or modify the selected Key Performance Indicator (KPI).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfbd8-104">Este panel solo se muestra en la vista de formulario.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dfbd8-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="dfbd8-105">Options</span></span>  
 <span data-ttu-id="dfbd8-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-106">**Name**</span></span>  
 <span data-ttu-id="dfbd8-107">Escriba el nombre del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-107">Type the name of the KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-108">**Grupo de medida asociado**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-108">**Associated measure group**</span></span>  
 <span data-ttu-id="dfbd8-109">Seleccione el grupo de medida asociado con el KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-109">Select the measure group associated with the KPI.</span></span> <span data-ttu-id="dfbd8-110">La aplicación cliente puede utilizar esta información para determinar qué dimensiones están disponibles cuando el usuario examina este KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-110">The client application can use this information to determine which dimensions are available when the user browses this KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-111">**Expresión de valor**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-111">**Value Expression**</span></span>  
 <span data-ttu-id="dfbd8-112">Expanda para ver o editar la expresión MDX (Expresiones multidimensionales) para el valor del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-112">Expand to view or edit the Multidimensional Expressions (MDX) expression for the value of the KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-113">Escriba la expresión MDX que devuelve el valor del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-113">Type the MDX expression that returns the value of the KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-114">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-114">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="dfbd8-115">**Expresión objetivo**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-115">**Goal Expression**</span></span>  
 <span data-ttu-id="dfbd8-116">Expanda para ver o editar la expresión MDX para el valor objetivo del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-116">Expand to view or edit the MDX expression for the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-117">Escriba la expresión MDX que devuelve el valor objetivo del KPI cuando éste se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-117">Type the MDX expression that returns the goal value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="dfbd8-118">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-118">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="dfbd8-119">**Estado**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-119">**Status**</span></span>  
 <span data-ttu-id="dfbd8-120">Expanda para ver las opciones **Gráfico de estado** y **Expresión de estado** .</span><span class="sxs-lookup"><span data-stu-id="dfbd8-120">Expand to view the **Status graphic** and **Status expression** options.</span></span>  
  
 <span data-ttu-id="dfbd8-121">**Gráfico de estado**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-121">**Status graphic**</span></span>  
 <span data-ttu-id="dfbd8-122">Seleccione el gráfico que utilizará la aplicación cliente para representar el valor de estado en forma gráfica.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-122">Select the graphic to be used by the client application to represent the status value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfbd8-123">La aplicación cliente puede admitir el gráfico seleccionado o reemplazarlo con una alternativa adecuada.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-123">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="dfbd8-124">**Expresión de estado**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-124">**Status expression**</span></span>  
 <span data-ttu-id="dfbd8-125">Escriba la expresión MDX que devuelve el valor de estado del KPI cuando éste se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-125">Type the MDX expression that returns the status value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="dfbd8-126">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-126">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="dfbd8-127">Se recomienda que esta expresión devuelva un número decimal entre-1 y 1.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-127">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="dfbd8-128">Un número menor representa una situación negativa, mientras que un número mayor representa una situación positiva.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-128">A lower number represents a negative situation, while a higher number represents a positive situation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfbd8-129">Los valores inferiores a 1 y superiores a 1 son posibles, pero es posible que las aplicaciones cliente de terceros no los interpreten correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-129">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="dfbd8-130">**Tendencia**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-130">**Trend**</span></span>  
 <span data-ttu-id="dfbd8-131">Expanda para ver las opciones **Gráfico de tendencia** y **Expresión de tendencia** .</span><span class="sxs-lookup"><span data-stu-id="dfbd8-131">Expand to view the **Trend graphic** and **Trend expression** options.</span></span>  
  
 <span data-ttu-id="dfbd8-132">**Gráfico de tendencia**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-132">**Trend graphic**</span></span>  
 <span data-ttu-id="dfbd8-133">Seleccione el gráfico que utilizará la aplicación cliente para representar el valor de tendencia en forma gráfica.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-133">Select the graphic to be used by the client application to represent the trend value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfbd8-134">La aplicación cliente puede admitir el gráfico seleccionado o reemplazarlo con una alternativa adecuada.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-134">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="dfbd8-135">**Expresión de tendencia**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-135">**Trend expression**</span></span>  
 <span data-ttu-id="dfbd8-136">Escriba la expresión MDX que devuelve el valor de tendencia del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-136">Type the MDX expression that returns the trend value of the KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-137">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-137">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="dfbd8-138">La expresión de tendencia puede basarse en cualquier criterio basado en el tiempo que tenga sentido en un contexto empresarial determinado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-138">The trend expression can be based on any time-based criteria that makes sense in a given business context.</span></span> <span data-ttu-id="dfbd8-139">Se recomienda que esta expresión devuelva un número decimal entre-1 y 1.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-139">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="dfbd8-140">Un número menor representa una tendencia negativa a lo largo del tiempo; un número mayor representa una tendencia positiva a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-140">A lower number represents a negative trend over time; a higher number represents a positive trend over time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfbd8-141">Los valores inferiores a 1 y superiores a 1 son posibles, pero es posible que las aplicaciones cliente de terceros no los interpreten correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-141">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="dfbd8-142">**Propiedades adicionales**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-142">**Additional Properties**</span></span>  
 <span data-ttu-id="dfbd8-143">Expanda para ver las opciones **Carpeta para mostrar**, **KPI primario**, **Miembro de hora actual**, **Peso**y **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="dfbd8-143">Expand to view the **Display folder**, **Parent KPI**, **Current time member**, **Weight**, and **Description** options.</span></span>  
  
 <span data-ttu-id="dfbd8-144">**Carpeta para mostrar**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-144">**Display folder**</span></span>  
 <span data-ttu-id="dfbd8-145">Escriba la categorización del KPI que se utilizará en la aplicación cliente para mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-145">Type the categorization of the KPI for use by the client application for display purposes.</span></span>  
  
 <span data-ttu-id="dfbd8-146">Use una barra inversa (\\) para separar nombres de carpetas en una carpeta para mostrar y un punto y coma (;) para separar varias carpetas para mostrar.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-146">Use a backward slash (\\) to separate folder names in a display folder and a semicolon (;) to separate multiple display folders.</span></span> <span data-ttu-id="dfbd8-147">Por ejemplo, escriba `Category\Goal\Scientific;Category\Goal\Metric`.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-147">For example, type `Category\Goal\Scientific;Category\Goal\Metric`.</span></span>  
  
 <span data-ttu-id="dfbd8-148">**KPI primario**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-148">**Parent KPI**</span></span>  
 <span data-ttu-id="dfbd8-149">Seleccione un KPI existente en el que categorizar el KPI que se utilizará en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-149">Select an existing KPI under which to categorize the KPI for use by the client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfbd8-150">Si esta opción está establecida en un KPI existente, se omite **Carpeta para mostrar** .</span><span class="sxs-lookup"><span data-stu-id="dfbd8-150">If this option is set to an existing KPI, **Display folder** is ignored.</span></span>  
  
 <span data-ttu-id="dfbd8-151">**Miembro de hora actual**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-151">**Current time member**</span></span>  
 <span data-ttu-id="dfbd8-152">Escriba la expresión MDX que devuelve el miembro que identifica el contexto temporal del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-152">Type the MDX expression that returns the member that identifies the temporal context of the KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-153">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dfbd8-154">La expresión MDX debe devolver el nombre único de un miembro en una dimensión de tiempo asociada con el grupo de medida especificado en **Grupo de medida asociado**.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-154">The MDX expression must return the unique name of a member within a time dimension associated with the measure group specified in **Associated measure group**.</span></span>  
  
 <span data-ttu-id="dfbd8-155">**Peso**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-155">**Weight**</span></span>  
 <span data-ttu-id="dfbd8-156">Expanda para ver o editar la expresión MDX para el factor de peso del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-156">Expand to view or edit the MDX expression for the weighting factor of the KPI.</span></span>  
  
 <span data-ttu-id="dfbd8-157">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-157">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="dfbd8-158">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dfbd8-158">**Description**</span></span>  
 <span data-ttu-id="dfbd8-159">Escriba la descripción opcional del KPI.</span><span class="sxs-lookup"><span data-stu-id="dfbd8-159">Type the optional description of the KPI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfbd8-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dfbd8-160">See Also</span></span>  
 [<span data-ttu-id="dfbd8-161">KPI &#40;diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbd8-161">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
