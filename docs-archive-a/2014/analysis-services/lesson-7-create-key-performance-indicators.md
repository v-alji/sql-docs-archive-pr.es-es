---
title: 'Lección 8: crear indicadores clave de rendimiento | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a6c8ac2b-64ba-456f-b418-7bf0afe145d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3beaab8a34844ecbd633eb5fabbacf37edfede2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745472"
---
# <a name="lesson-8-create-key-performance-indicators"></a><span data-ttu-id="a1e69-102">Lección 8: Crear indicadores clave de rendimiento</span><span class="sxs-lookup"><span data-stu-id="a1e69-102">Lesson 8: Create Key Performance Indicators</span></span>
  <span data-ttu-id="a1e69-103">En esta lección, creará indicadores clave de rendimiento (KPI).</span><span class="sxs-lookup"><span data-stu-id="a1e69-103">In this lesson, you will create Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="a1e69-104">Los KPI miden el rendimiento de un valor, definido por una medida *base* , con respecto a un valor de *destino* , también definido por una medida o por un valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="a1e69-104">KPIs are used to gauge performance of a value, defined by a *Base* measure, against a *Target* value, also defined by a measure or by an absolute value.</span></span> <span data-ttu-id="a1e69-105">En aplicaciones cliente de generación de informes, los KPI pueden proporcionar a los profesionales de empresa una manera rápida y sencilla de comprender un resumen de logros empresariales o para identificar tendencias.</span><span class="sxs-lookup"><span data-stu-id="a1e69-105">In reporting client applications, KPIs can provide business professionals a quick and easy way to understand a summary of business success or to identify trends.</span></span> <span data-ttu-id="a1e69-106">Para obtener más información, consulte [KPI &#40;SSAS tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a1e69-106">To learn more, see [KPIs &#40;SSAS Tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="a1e69-107">Tiempo estimado para completar esta lección: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="a1e69-107">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1e69-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a1e69-108">Prerequisites</span></span>  
 <span data-ttu-id="a1e69-109">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="a1e69-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="a1e69-110">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 7: Crear medidas](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="a1e69-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
## <a name="create-key-performance-indicators"></a><span data-ttu-id="a1e69-111">Creación de indicadores clave de rendimiento</span><span class="sxs-lookup"><span data-stu-id="a1e69-111">Create Key Performance Indicators</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-sales-performance-kpi"></a><span data-ttu-id="a1e69-112">Para crear un KPI Rendimiento de ventas por Internet del trimestre actual</span><span class="sxs-lookup"><span data-stu-id="a1e69-112">To create an Internet Current Quarter Sales Performance KPI</span></span>  
  
1.  <span data-ttu-id="a1e69-113">En el diseñador de modelos, haga clic en la tabla (pestaña) **Ventas por Internet** .</span><span class="sxs-lookup"><span data-stu-id="a1e69-113">In the model designer, click the **Internet Sales** table (tab).</span></span>  
  
2.  <span data-ttu-id="a1e69-114">En la cuadrícula de medidas, haga clic en una celda vacía.</span><span class="sxs-lookup"><span data-stu-id="a1e69-114">In the measure grid, click an empty cell.</span></span>  
  
3.  <span data-ttu-id="a1e69-115">En la barra de fórmulas, encima de la tabla, escriba la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1e69-115">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Sales Performance :=IFERROR([Internet Current Quarter Sales]/[Internet Previous Quarter Sales Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="a1e69-116">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a1e69-116">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="a1e69-117">Esta medida servirá como la medida base del KPI.</span><span class="sxs-lookup"><span data-stu-id="a1e69-117">This measure will serve as the Base measure for the KPI.</span></span>  
  
4.  <span data-ttu-id="a1e69-118">En la cuadrícula de medidas, haga clic con el botón derecho en la medida **Rendimiento de ventas por Internet del trimestre actual** y haga clic en **Crear KPI**.</span><span class="sxs-lookup"><span data-stu-id="a1e69-118">In the measure grid, right-click the **Internet Current Quarter Sales Performance** measure, and then click **Create KPI**.</span></span>  
  
     <span data-ttu-id="a1e69-119">Se abre el cuadro de diálogo **Indicador clave de rendimiento** .</span><span class="sxs-lookup"><span data-stu-id="a1e69-119">The **Key Performance Indicator** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="a1e69-120">En el cuadro de diálogo **Indicador clave de rendimiento** , en **Definir valor de destino**, seleccione la opción **Valor absoluto** .</span><span class="sxs-lookup"><span data-stu-id="a1e69-120">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
6.  <span data-ttu-id="a1e69-121">En el campo **valor absoluto** , escriba `1.1` y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="a1e69-121">In the **Absolute Value** field, type `1.1`, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="a1e69-122">En **definir umbrales de estado**, en el campo de control deslizante de la izquierda (bajo), escriba `1` y, a continuación, en el campo de control deslizante derecho (alto), escriba `1.07` .</span><span class="sxs-lookup"><span data-stu-id="a1e69-122">In **Define Status Thresholds**, in the left (low) slider field, type `1`, and then in the right (high) slider field, type `1.07`.</span></span>  
  
8.  <span data-ttu-id="a1e69-123">En **Seleccionar el estilo de icono**, seleccione el tipo de icono de rombo (rojo), triángulo (amarillo), círculo (verde).</span><span class="sxs-lookup"><span data-stu-id="a1e69-123">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="a1e69-124">Observe en el campo expansible **Descripciones** los estilos de icono disponibles.</span><span class="sxs-lookup"><span data-stu-id="a1e69-124">Notice the **Descriptions** expandable field below the available icon styles.</span></span> <span data-ttu-id="a1e69-125">Puede especificar descripciones para los distintos elementos de KPI para que sean más fáciles de identificar en las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="a1e69-125">You can type descriptions for the various KPI elements to make them more identifiable in client applications.</span></span>  
  
9. <span data-ttu-id="a1e69-126">Haga clic en **Aceptar** para completar el KPI.</span><span class="sxs-lookup"><span data-stu-id="a1e69-126">Click **OK** to complete the KPI.</span></span>  
  
     <span data-ttu-id="a1e69-127">En la cuadrícula de medidas, observe el icono situado junto a la medida **Rendimiento de ventas por Internet del trimestre actual** .</span><span class="sxs-lookup"><span data-stu-id="a1e69-127">In the measure grid, notice the icon next to the **Internet Current Quarter Sales Performance** measure.</span></span> <span data-ttu-id="a1e69-128">Este icono indica que esta medida actúa como valor base de un KPI.</span><span class="sxs-lookup"><span data-stu-id="a1e69-128">This icon indicates that this measure serves as a Base value for a KPI.</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-margin-performance-kpi"></a><span data-ttu-id="a1e69-129">Para crear un KPI Rendimiento de margen de ventas por Internet del trimestre actual</span><span class="sxs-lookup"><span data-stu-id="a1e69-129">To create an Internet Current Quarter Margin Performance KPI</span></span>  
  
1.  <span data-ttu-id="a1e69-130">En la cuadrícula de medidas de la tabla **Ventas por Internet** , haga clic en una celda vacía.</span><span class="sxs-lookup"><span data-stu-id="a1e69-130">In the measure grid for the **Internet Sales** table, click an empty cell.</span></span>  
  
2.  <span data-ttu-id="a1e69-131">En la barra de fórmulas, encima de la tabla, escriba la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1e69-131">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Margin Performance :=IF([Internet Previous Quarter Margin Proportion to QTD]<>0,([Internet Current Quarter Margin]-[Internet Previous Quarter Margin Proportion to QTD])/[Internet Previous Quarter Margin Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="a1e69-132">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a1e69-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="a1e69-133">En la cuadrícula de medidas, haga clic con el botón derecho en la medida **Rendimiento de margen de ventas por Internet del trimestre actual** y haga clic en **Crear KPI**.</span><span class="sxs-lookup"><span data-stu-id="a1e69-133">In the measure grid, right-click the **Internet Current Quarter Margin Performance** measure, and then click **Create KPI**.</span></span>  
  
4.  <span data-ttu-id="a1e69-134">En el cuadro de diálogo **Indicador clave de rendimiento** , en **Definir valor de destino**, seleccione la opción **Valor absoluto** .</span><span class="sxs-lookup"><span data-stu-id="a1e69-134">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
5.  <span data-ttu-id="a1e69-135">En el campo **valor absoluto** , escriba `1.25` .</span><span class="sxs-lookup"><span data-stu-id="a1e69-135">In the **Absolute Value** field, type `1.25`.</span></span>  
  
6.  <span data-ttu-id="a1e69-136">En **Definir umbrales de estado**, desplace el campo de control deslizante de abajo a la izquierda hasta que el campo muestre **0.8**y el de arriba a la derecha hasta que muestre **1.03**.</span><span class="sxs-lookup"><span data-stu-id="a1e69-136">In **Define Status Thresholds**, slide the left (low) slider field until the field displays **0.8**, and then slide the right (high) slider field, until the field displays **1.03**.</span></span>  
  
7.  <span data-ttu-id="a1e69-137">En **Seleccionar el estilo de icono**, seleccione el tipo de icono de rombo (rojo), triángulo (amarillo) o círculo (verde) y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1e69-137">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type, and then click **OK**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a1e69-138">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="a1e69-138">Next Step</span></span>  
 <span data-ttu-id="a1e69-139">Para continuar este tutorial, vaya a la lección siguiente: [Lección 9: Crear perspectivas](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="a1e69-139">To continue this tutorial, go to the next lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
  
