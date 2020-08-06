---
title: Mostrar el plan de ejecución estimado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- zoom [SQL Server]
- estimated execution plan [SQL Server]
- displaying execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
- customizing execution plan display [SQL Server]
- modifying execution plan display
- custom zoom [SQL Server]
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79c0972661d40eb9e359cf43f7a1f0b1b2ae4b0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745224"
---
# <a name="display-the-estimated-execution-plan"></a><span data-ttu-id="faa0a-102">Mostrar el plan de ejecución estimado</span><span class="sxs-lookup"><span data-stu-id="faa0a-102">Display the Estimated Execution Plan</span></span>
  <span data-ttu-id="faa0a-103">En este tema se describe cómo generar planes de ejecución estimados gráficos utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faa0a-103">This topic describes how to generate graphical estimated execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="faa0a-104">Cuando se generan planes de ejecución estimados, las consultas o lotes [!INCLUDE[tsql](../../includes/tsql-md.md)] no se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="faa0a-104">When estimated execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches do not execute.</span></span> <span data-ttu-id="faa0a-105">En su lugar, el plan de ejecución que se genera muestra el plan de ejecución de la consulta que el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilizaría con más probabilidad si se ejecutaran realmente las consultas.</span><span class="sxs-lookup"><span data-stu-id="faa0a-105">Instead, the execution plan that is generated displays the query execution plan that [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] would most probably use if the queries were actually executed.</span></span>  
  
 <span data-ttu-id="faa0a-106">Para utilizar esta característica, los usuarios deben tener los permisos correspondientes para ejecutar la consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] para la que se va a generar un plan de ejecución gráfico, y se les debe conceder el permiso SHOWPLAN para todas las bases de datos a las que haga referencia la consulta.</span><span class="sxs-lookup"><span data-stu-id="faa0a-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-display-the-estimated-execution-plan-for-a-query"></a><span data-ttu-id="faa0a-107">Para mostrar el plan de ejecución estimado de una consulta</span><span class="sxs-lookup"><span data-stu-id="faa0a-107">To display the estimated execution plan for a query</span></span>  
  
1.  <span data-ttu-id="faa0a-108">En la barra de herramientas, haga clic en **Consulta de motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="faa0a-108">On the toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="faa0a-109">También puede abrir una consulta existente y mostrar el plan de ejecución estimado haciendo clic en el botón **Abrir archivo** de la barra de herramientas y buscando la consulta existente.</span><span class="sxs-lookup"><span data-stu-id="faa0a-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="faa0a-110">Especifique la consulta para la que desea mostrar el plan de ejecución estimado.</span><span class="sxs-lookup"><span data-stu-id="faa0a-110">Enter the query for which you would like to display the estimated execution plan.</span></span>  
  
3.  <span data-ttu-id="faa0a-111">En el menú **Consulta** , haga clic en **Mostrar plan de ejecución estimado** o haga clic en el botón **Mostrar plan de ejecución estimado** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="faa0a-111">On the **Query** menu, click **Display Estimated Execution Plan** or click the **Display Estimated Execution Plan** toolbar button.</span></span> <span data-ttu-id="faa0a-112">El plan de ejecución estimado se muestra en la pestaña **Plan de ejecución** del panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="faa0a-112">The estimated execution plan is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="faa0a-113">Para ver información adicional, sitúe el cursor del mouse (ratón) sobre los iconos de operador lógico y físico, y vea la descripción y las propiedades del operador en la información sobre herramientas que se muestra.</span><span class="sxs-lookup"><span data-stu-id="faa0a-113">To view additional information, pause the mouse over the logical and physical operator icons and view the description and properties of the operator in the displayed ToolTip.</span></span> <span data-ttu-id="faa0a-114">También puede ver las propiedades del operador en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="faa0a-114">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="faa0a-115">Si las propiedades no están visibles, haga clic con el botón derecho en un operador y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="faa0a-115">If Properties is not visible, right-click an operator and click **Properties**.</span></span> <span data-ttu-id="faa0a-116">Seleccione un operador para ver sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="faa0a-116">Select an operator to view its properties.</span></span>  
  
4.  <span data-ttu-id="faa0a-117">Para cambiar la visualización del plan de ejecución, haga clic con el botón derecho en el plan de ejecución y seleccione **Acercar**, **Alejar**, **Zoom personalizado**o **Zoom para ajustar**.</span><span class="sxs-lookup"><span data-stu-id="faa0a-117">To alter the display of the execution plan, right-click the execution plan and select **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="faa0a-118">**Acercar** y **Alejar** permiten aumentar o reducir el plan de ejecución en incrementos fijos.</span><span class="sxs-lookup"><span data-stu-id="faa0a-118">**Zoom In** and **Zoom Out** allow you to magnify or reduce the execution plan by fixed amounts.</span></span> <span data-ttu-id="faa0a-119">**Zoom personalizado** le permite definir su propia ampliación de la visualización, como alejar hasta un 80 por ciento.</span><span class="sxs-lookup"><span data-stu-id="faa0a-119">**Custom Zoom** allows you to define your own display magnification, such as zooming at 80 percent.</span></span> <span data-ttu-id="faa0a-120">**Zoom para ajustar** amplía el plan de ejecución para que se ajuste al panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="faa0a-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
