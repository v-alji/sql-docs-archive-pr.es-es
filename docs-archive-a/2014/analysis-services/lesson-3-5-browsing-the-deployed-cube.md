---
title: Examinar el cubo implementado | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 849c6109-1453-4fe4-a892-c49a982cfadb
author: minewiskan
ms.author: owend
ms.openlocfilehash: b876c8b2876aaf4ad28b0f4ea3fb8bab32cd787b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674425"
---
# <a name="browsing-the-deployed-cube"></a><span data-ttu-id="afb9f-102">Examinar el cubo implementado</span><span class="sxs-lookup"><span data-stu-id="afb9f-102">Browsing the Deployed Cube</span></span>
  <span data-ttu-id="afb9f-103">En la tarea siguiente, examinará el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afb9f-103">In the following task, you browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="afb9f-104">Puesto que nuestro análisis compara las medidas en varias dimensiones, usará una tabla dinámica de Excel para examinar los datos.</span><span class="sxs-lookup"><span data-stu-id="afb9f-104">Because our analysis compares measure across multiple dimensions, you will use an Excel PivotTable to browse your data.</span></span> <span data-ttu-id="afb9f-105">El uso de una tabla dinámica le permite colocar la información de clientes, fechas y productos en diferentes ejes de modo que pueda ver cómo cambian las ventas por Internet cuando se ven en determinados períodos de tiempo, datos demográficos de los clientes y líneas de productos.</span><span class="sxs-lookup"><span data-stu-id="afb9f-105">Using a PivotTable lets you place customer, date, and product information on different axes so that you can see how Internet Sales change when viewed across specific time periods, customer demographics, and product lines.</span></span>  
  
### <a name="to-browse-the-deployed-cube"></a><span data-ttu-id="afb9f-106">Para examinar el cubo implementado</span><span class="sxs-lookup"><span data-stu-id="afb9f-106">To browse the deployed cube</span></span>  
  
1.  <span data-ttu-id="afb9f-107">Para cambiar al diseñador de cubos de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , haga doble clic en el cubo \*\* [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tutorial\*\* de en la carpeta **cubos** del explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="afb9f-107">To switch to Cube Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], double-click the **[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial** cube in the **Cubes** folder of the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="afb9f-108">Abra la pestaña **Explorador** y haga clic en el botón **Volver a conectar** de la barra de herramientas del diseñador.</span><span class="sxs-lookup"><span data-stu-id="afb9f-108">Open the **Browser** tab, and then click the **Reconnect** button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="afb9f-109">Haga clic en el icono de Excel para iniciar Excel usando la base de datos del área de trabajo como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="afb9f-109">Click the Excel icon to launch Excel using the workspace database as the data source.</span></span> <span data-ttu-id="afb9f-110">Cuando se le pida que habilite las conexiones, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="afb9f-110">When prompted to enable connections, click **Enable**.</span></span>  
  
4.  <span data-ttu-id="afb9f-111">En la lista de campos de la tabla dinámica, expanda **Internet Sales**y arrastre la medida **Sales Amount** hasta el área **Valores** .</span><span class="sxs-lookup"><span data-stu-id="afb9f-111">In the PivotTable Field List, expand **Internet Sales**, and then drag the **Sales Amount** measure to the **Values** area.</span></span>  
  
5.  <span data-ttu-id="afb9f-112">En la lista de campos de la tabla dinámica, expanda **Product**.</span><span class="sxs-lookup"><span data-stu-id="afb9f-112">In the PivotTable Field List, expand **Product**.</span></span>  
  
6.  <span data-ttu-id="afb9f-113">Arrastre la jerarquía de usuario **Product Model Lines** hasta el área **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="afb9f-113">Drag the **Product Model Lines** user hierarchy to the **Columns** area.</span></span>  
  
7.  <span data-ttu-id="afb9f-114">En la lista de campos de la tabla dinámica, expanda **Customer**, expanda **Location**y arrastre la jerarquía **Customer Geography** desde la carpeta para mostrar Location de la dimensión Customer hasta el área **Filas** .</span><span class="sxs-lookup"><span data-stu-id="afb9f-114">In the PivotTable Field List, expand **Customer**, expand **Location**, and then drag the **Customer Geography** hierarchy from the Location display folder in the Customer dimension to the **Rows** area.</span></span>  
  
8.  <span data-ttu-id="afb9f-115">En la lista de campos de la tabla dinámica, expanda **Order Date**y arrastre la jerarquía **Order Date.Calendar Date** hasta el área **Filtro de informe** .</span><span class="sxs-lookup"><span data-stu-id="afb9f-115">In the PivotTable Field List, expand **Order Date**, and then drag the **Order Date.Calendar Date** hierarchy to the **Report Filter** area.</span></span>  
  
9. <span data-ttu-id="afb9f-116">Haga clic en la flecha que se encuentra a la derecha del filtro **Order Date.Calendar Date** del panel de datos, desactive la casilla del nivel **(All)** , expanda sucesivamente **2006**, **H1 CY 2006**y **Q1 CY 2006**, active la casilla **February 2006**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="afb9f-116">Click the arrow to the right of the **Order Date.Calendar Date** filter in the data pane, clear the check box for the **(All)** level, expand **2006**, expand **H1 CY 2006**, expand **Q1 CY 2006**, select the check box for **February 2006**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="afb9f-117">De este modo, se muestran las ventas realizadas por Internet por región y por línea de productos en el mes de febrero de 2006, como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="afb9f-117">Internet sales by region and product line for the month of February, 2006 appear as shown in the following image.</span></span>  
  
     <span data-ttu-id="afb9f-118">![Internet Sales por línea de productos y región](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet Sales por línea de productos y región")</span><span class="sxs-lookup"><span data-stu-id="afb9f-118">![Internet sales by region and product line](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet sales by region and product line")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="afb9f-119">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="afb9f-119">Next Lesson</span></span>  
 [<span data-ttu-id="afb9f-120">Lección 4: definir propiedades avanzadas de atributos y dimensiones</span><span class="sxs-lookup"><span data-stu-id="afb9f-120">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>](lesson-4-defining-advanced-attribute-and-dimension-properties.md)  
  
  
