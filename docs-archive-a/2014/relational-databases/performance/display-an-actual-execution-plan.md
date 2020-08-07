---
title: Mostrar un plan de ejecución real | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- displaying execution plans
- actual execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
ms.assetid: 9e583a18-5f4a-4054-bfe1-4b2a76630db6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f384e2d2752b7601fbb46b8ee7f7b56a2615651c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745230"
---
# <a name="display-an-actual-execution-plan"></a><span data-ttu-id="76848-102">Mostrar un plan de ejecución real</span><span class="sxs-lookup"><span data-stu-id="76848-102">Display an Actual Execution Plan</span></span>
  <span data-ttu-id="76848-103">En este tema se describe cómo generar planes de ejecución gráficos reales mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76848-103">This topic describes how to generate actual graphical execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="76848-104">Cuando se generan planes de ejecución reales, se ejecutan los lotes o consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76848-104">When actual execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches execute.</span></span> <span data-ttu-id="76848-105">El plan de ejecución que se ha generado muestra el plan de ejecución de consultas real que utiliza el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] para ejecutar las consultas.</span><span class="sxs-lookup"><span data-stu-id="76848-105">The execution plan that is generated displays the actual query execution plan that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses to execute the queries.</span></span>  
  
 <span data-ttu-id="76848-106">Para utilizar esta característica, los usuarios deben tener los permisos apropiados para ejecutar las consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] para las que se genera un plan de ejecución gráfico y deben tener concedido el permiso SHOWPLAN para todas las bases de datos a las que hace referencia la consulta.</span><span class="sxs-lookup"><span data-stu-id="76848-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-include-an-execution-plan-for-a-query-during-execution"></a><span data-ttu-id="76848-107">Para incluir un plan de ejecución para una consulta durante la ejecución</span><span class="sxs-lookup"><span data-stu-id="76848-107">To include an execution plan for a query during execution</span></span>  
  
1.  <span data-ttu-id="76848-108">En la barra de herramientas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , haga clic en **Consulta de motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="76848-108">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="76848-109">También puede abrir una consulta existente y mostrar el plan de ejecución estimado haciendo clic en el botón **Abrir archivo** de la barra de herramientas y buscando la consulta existente.</span><span class="sxs-lookup"><span data-stu-id="76848-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="76848-110">Especifique la consulta para la que desee mostrar el plan de ejecución real.</span><span class="sxs-lookup"><span data-stu-id="76848-110">Enter the query for which you would like to display the actual execution plan.</span></span>  
  
3.  <span data-ttu-id="76848-111">En el menú **consulta** , haga clic en **incluir plan de ejecución real** o en el botón **incluir plan de ejecución real** .</span><span class="sxs-lookup"><span data-stu-id="76848-111">On the **Query** menu, click **Include Actual Execution Plan** or click the **Include Actual Execution Plan** toolbar button</span></span>  
  
4.  <span data-ttu-id="76848-112">Ejecute la consulta haciendo clic en el botón **Ejecutar** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="76848-112">Execute the query by clicking the **Execute** toolbar button.</span></span> <span data-ttu-id="76848-113">El plan utilizado por el optimizador de consultas se muestra en la pestaña **Plan de ejecución** del panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="76848-113">The plan used by the query optimizer is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="76848-114">Coloque el mouse (ratón) sobre los operadores lógicos y físicos para ver la descripción y las propiedades de los operadores en la información sobre herramientas que se muestra.</span><span class="sxs-lookup"><span data-stu-id="76848-114">Pause the mouse over the logical and physical operators to view the description and properties of the operators in the displayed ToolTip.</span></span>  
  
     <span data-ttu-id="76848-115">También puede ver las propiedades del operador en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="76848-115">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="76848-116">Si las propiedades no están visibles, haga clic con el botón derecho en un operador y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="76848-116">If Properties is not visible, right-click an operator and select **Properties**.</span></span> <span data-ttu-id="76848-117">Seleccione un operador para ver sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="76848-117">Select an operator to view its properties.</span></span>  
  
5.  <span data-ttu-id="76848-118">Para cambiar la visualización del plan de ejecución, haga clic con el botón derecho en el plan de ejecución y seleccione **Acercar**, **Alejar**, **Zoom personalizado**o **Zoom para ajustar**.</span><span class="sxs-lookup"><span data-stu-id="76848-118">You can alter the display of the execution plan by right-clicking the execution plan and selecting **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="76848-119">**Acercar** y **Alejar** permiten acercarse o alejarse del plan de ejecución, mientras que **Zoom personalizado** permite definir su propio zoom, como por ejemplo un 80 por ciento de zoom.</span><span class="sxs-lookup"><span data-stu-id="76848-119">**Zoom In** and **Zoom Out** allow you to zoom in or out on the execution plan, while **Custom Zoom** allows you to define your own zoom, such as zooming at 80 percent.</span></span> <span data-ttu-id="76848-120">**Zoom para ajustar** amplía el plan de ejecución para que se ajuste al panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="76848-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
