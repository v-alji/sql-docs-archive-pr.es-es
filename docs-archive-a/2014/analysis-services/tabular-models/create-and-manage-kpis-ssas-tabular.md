---
title: Crear y administrar KPI (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.kpi.f1
ms.assetid: c96026c2-4394-4c3c-986b-4c95a4421900
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8e9d7ef77939efe407ed6ab0d725a6d788c58b49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671205"
---
# <a name="create-and-manage-kpis-ssas-tabular"></a><span data-ttu-id="a9d8b-102">Crear y administrar KPI (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="a9d8b-102">Create and Manage KPIs (SSAS Tabular)</span></span>
  <span data-ttu-id="a9d8b-103">En este tema se describe cómo crear, editar o eliminar un KPI (indicador clave de rendimiento) en un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-103">This topic describes how to create, edit, or delete a KPI (Key Performance Indicator) in a tabular model.</span></span> <span data-ttu-id="a9d8b-104">Para crear un KPI, seleccione una medida que se evalúe como el valor base del KPI.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-104">To create a KPI, you select a measure that evaluates to the KPI's Base value.</span></span> <span data-ttu-id="a9d8b-105">A continuación, use el cuadro de diálogo Indicador clave de rendimiento para seleccionar una segunda medida o un valor absoluto que se evalúe como un valor de destino.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-105">You then use the Key Performance Indicator dialog box to select a second measure or an absolute value that evaluates to a target value.</span></span> <span data-ttu-id="a9d8b-106">Después puede definir umbrales de estado que miden el rendimiento entre las medidas Base y Destino.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-106">You can then define status thresholds that measure the performance between the Base and Target measures.</span></span>  
  
 <span data-ttu-id="a9d8b-107">En este tema se incluyen las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9d8b-107">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="a9d8b-108">Para crear un KPI</span><span class="sxs-lookup"><span data-stu-id="a9d8b-108">To create a KPI</span></span>](#bkmk_create_KPI)  
  
-   [<span data-ttu-id="a9d8b-109">Para editar un KPI</span><span class="sxs-lookup"><span data-stu-id="a9d8b-109">To edit a KPI</span></span>](#bkmk_edit_KPI)  
  
-   [<span data-ttu-id="a9d8b-110">Para eliminar un KPI y la medida base</span><span class="sxs-lookup"><span data-stu-id="a9d8b-110">To delete a KPI and the base measure</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="a9d8b-111">Para eliminar un KPI, pero mantener la medida base</span><span class="sxs-lookup"><span data-stu-id="a9d8b-111">To delete a KPI, but keep the base measure</span></span>](#bkmk_delete_KPI)  
  
## <a name="tasks"></a><span data-ttu-id="a9d8b-112">Tareas</span><span class="sxs-lookup"><span data-stu-id="a9d8b-112">Tasks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a9d8b-113">Antes de crear un KPI, debe crear primero una medida base que se evalúe como un valor.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-113">Before creating a KPI, you must first create a Base measure that evaluates to value.</span></span> <span data-ttu-id="a9d8b-114">Después, extienda la medida base a un KPI.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-114">You then extend the Base measure to a KPI.</span></span> <span data-ttu-id="a9d8b-115">La forma de crear medidas se describe en el tema [Crear y administrar medidas &#40;SSAS tabular&#41;](measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a9d8b-115">How to create measures are described in another topic, [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md).</span></span> <span data-ttu-id="a9d8b-116">Un KPI también necesita un valor de destino.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-116">A KPI also requires a target value.</span></span> <span data-ttu-id="a9d8b-117">Este valor puede ser de otra medida predefinida o puede ser un valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-117">This value can be from another pre-defined measure or an absolute value.</span></span> <span data-ttu-id="a9d8b-118">Una vez extendida una medida base a un KPI, puede seleccionar el valor de destino y definir umbrales de estado en el cuadro de diálogo Indicador clave de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-118">Once you have extended a Base measure to a KPI, you can then select the target value and define status thresholds in the Key Performance Indicator dialog box.</span></span>  
  
###  <a name="to-create-a-kpi"></a><a name="bkmk_create_KPI"></a> <span data-ttu-id="a9d8b-119">Para crear un KPI</span><span class="sxs-lookup"><span data-stu-id="a9d8b-119">To create a KPI</span></span>  
  
1.  <span data-ttu-id="a9d8b-120">En la cuadrícula de medidas, haga clic con el botón derecho en la medida que actuará como medida base (valor) y, después, haga clic en **Crear KPI**.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-120">In the measure grid, right-click the measure that will serve as the Base measure (value), and then click **Create KPI**.</span></span>  
  
2.  <span data-ttu-id="a9d8b-121">En el cuadro de diálogo **Indicador clave de rendimiento** , en **Definir el valor de destino**, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9d8b-121">In the **Key Performance Indicator** dialog box, in **Define target value**, select from one of the following:</span></span>  
  
     <span data-ttu-id="a9d8b-122">Seleccione **Medida**y, a continuación, seleccione una medida de destino en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-122">Select **Measure**, and then select a target measure from the listbox.</span></span>  
  
     <span data-ttu-id="a9d8b-123">Seleccione **Valor absoluto**y escriba un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-123">Select **Absolute value**, and then type a numerical value.</span></span>  
  
3.  <span data-ttu-id="a9d8b-124">En **Definir umbrales de estado**, haga clic y deslice los valores de umbral inferior y superior.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-124">In **Define status thresholds**, click and slide the low and high threshold values.</span></span>  
  
4.  <span data-ttu-id="a9d8b-125">En **Seleccionar estilo de icono**, haga clic en un tipo de imagen.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-125">In **Select icon style**, click an image type.</span></span>  
  
5.  <span data-ttu-id="a9d8b-126">Haga clic en **Descripciones**y, a continuación, escriba las descripciones para KPI, Valor, Estado y Destino.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-126">Click on **Descriptions**, and then type descriptions for KPI, Value, Status, and Target.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a9d8b-127">Puede usar la característica Analizar en Excel para probar el KPI.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-127">You can use the Analyze in Excel feature to test your KPI.</span></span> <span data-ttu-id="a9d8b-128">Para obtener más información, vea [Analizar en Excel &#40;SSAS tabular&#41;](analyze-in-excel-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a9d8b-128">For more information, see [Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md).</span></span>  
  
###  <a name="to-edit-a-kpi"></a><a name="bkmk_edit_KPI"></a> <span data-ttu-id="a9d8b-129">Para editar un KPI</span><span class="sxs-lookup"><span data-stu-id="a9d8b-129">To edit a KPI</span></span>  
  
-   <span data-ttu-id="a9d8b-130">En la cuadrícula de medidas, haga clic con el botón derecho en la medida que actúa como medida base (valor) del KPI y, después, haga clic en **Editar configuración de KPI**.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-130">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Edit KPI Settings**.</span></span>  
  
###  <a name="to-delete-a-kpi-and-the-base-measure"></a><a name="bkmk_delete"></a> <span data-ttu-id="a9d8b-131">Para eliminar un KPI y la medida base</span><span class="sxs-lookup"><span data-stu-id="a9d8b-131">To delete a KPI and the base measure</span></span>  
  
-   <span data-ttu-id="a9d8b-132">En la cuadrícula de medidas, haga clic con el botón derecho en la medida que actúa como medida base (valor) del KPI y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-132">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete**.</span></span>  
  
###  <a name="to-delete-a-kpi-but-keep-the-base-measure"></a><a name="bkmk_delete_KPI"></a><span data-ttu-id="a9d8b-133">Para eliminar un KPI, pero mantener la medida base</span><span class="sxs-lookup"><span data-stu-id="a9d8b-133">To delete a KPI, but keep the base measure</span></span>  
  
-   <span data-ttu-id="a9d8b-134">En la cuadrícula de medidas, haga clic con el botón derecho en la medida que actúa como medida base (valor) del KPI y, después, haga clic en **Eliminar KPI**.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-134">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete KPI**.</span></span>  
  
## <a name="alt-shortcuts"></a><span data-ttu-id="a9d8b-135">Accesos directos con ALT</span><span class="sxs-lookup"><span data-stu-id="a9d8b-135">ALT Shortcuts</span></span>  
  
|<span data-ttu-id="a9d8b-136">Sección IU</span><span class="sxs-lookup"><span data-stu-id="a9d8b-136">UI section</span></span>|<span data-ttu-id="a9d8b-137">Comando de teclas</span><span class="sxs-lookup"><span data-stu-id="a9d8b-137">Key command</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="a9d8b-138">Medida de base de KPI</span><span class="sxs-lookup"><span data-stu-id="a9d8b-138">KPI base measure</span></span>|<span data-ttu-id="a9d8b-139">ALT+B</span><span class="sxs-lookup"><span data-stu-id="a9d8b-139">ALT+B</span></span>|  
|<span data-ttu-id="a9d8b-140">Estado de KPI</span><span class="sxs-lookup"><span data-stu-id="a9d8b-140">KPI Status</span></span>|<span data-ttu-id="a9d8b-141">ALT+S</span><span class="sxs-lookup"><span data-stu-id="a9d8b-141">ALT+S</span></span>|  
|<span data-ttu-id="a9d8b-142">Measure</span><span class="sxs-lookup"><span data-stu-id="a9d8b-142">Measure</span></span>|<span data-ttu-id="a9d8b-143">ALT+M</span><span class="sxs-lookup"><span data-stu-id="a9d8b-143">ALT+M</span></span>|  
|<span data-ttu-id="a9d8b-144">Valor absoluto</span><span class="sxs-lookup"><span data-stu-id="a9d8b-144">Absolute value</span></span>|<span data-ttu-id="a9d8b-145">ALT + A</span><span class="sxs-lookup"><span data-stu-id="a9d8b-145">ALT+A</span></span>|  
|<span data-ttu-id="a9d8b-146">Definir umbrales de estado</span><span class="sxs-lookup"><span data-stu-id="a9d8b-146">Define status thresholds</span></span>|<span data-ttu-id="a9d8b-147">ALT+U</span><span class="sxs-lookup"><span data-stu-id="a9d8b-147">ALT+U</span></span>|  
|<span data-ttu-id="a9d8b-148">Seleccionar estilo de icono</span><span class="sxs-lookup"><span data-stu-id="a9d8b-148">Select icon style</span></span>|<span data-ttu-id="a9d8b-149">Alt+I</span><span class="sxs-lookup"><span data-stu-id="a9d8b-149">ALT+I</span></span>|  
|<span data-ttu-id="a9d8b-150">Tendencia</span><span class="sxs-lookup"><span data-stu-id="a9d8b-150">Trend</span></span>|<span data-ttu-id="a9d8b-151">ALT+T</span><span class="sxs-lookup"><span data-stu-id="a9d8b-151">ALT+T</span></span>|  
|<span data-ttu-id="a9d8b-152">Descripciones</span><span class="sxs-lookup"><span data-stu-id="a9d8b-152">Descriptions</span></span>|<span data-ttu-id="a9d8b-153">ALT+D</span><span class="sxs-lookup"><span data-stu-id="a9d8b-153">ALT+D</span></span>|  
|<span data-ttu-id="a9d8b-154">Tendencia</span><span class="sxs-lookup"><span data-stu-id="a9d8b-154">Trend</span></span>|<span data-ttu-id="a9d8b-155">ALT+T</span><span class="sxs-lookup"><span data-stu-id="a9d8b-155">ALT+T</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9d8b-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9d8b-156">See Also</span></span>  
 <span data-ttu-id="a9d8b-157">[KPI &#40;&#41;tabular de SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a9d8b-157">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 <span data-ttu-id="a9d8b-158">[Medidas &#40;&#41;tabular de SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a9d8b-158">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a9d8b-159">Crear y administrar medidas &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="a9d8b-159">Create and Manage Measures &#40;SSAS Tabular&#41;</span></span>](create-and-manage-measures-ssas-tabular.md)  
  
  
