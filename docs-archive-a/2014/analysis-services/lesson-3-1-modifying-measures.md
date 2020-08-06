---
title: Modificar medidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7bd48810-15ce-45ff-862b-372d08606995
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd352cbca1d21f5842e075d9cb8e5e766aa369b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675630"
---
# <a name="modifying-measures"></a><span data-ttu-id="efcaf-102">Modificar medidas</span><span class="sxs-lookup"><span data-stu-id="efcaf-102">Modifying Measures</span></span>
  <span data-ttu-id="efcaf-103">Puede usar la propiedad **FormatString** para definir parámetros de formato que controlen cómo se presentan las medidas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="efcaf-103">You can use the **FormatString** property to define formatting settings that control how measures are displayed to users.</span></span> <span data-ttu-id="efcaf-104">En esta tarea, debe especificar las propiedades de formato para las medidas de moneda y porcentaje del cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efcaf-104">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
### <a name="to-modify-the-measures-of-the-cube"></a><span data-ttu-id="efcaf-105">Para modificar las medidas del cubo</span><span class="sxs-lookup"><span data-stu-id="efcaf-105">To modify the measures of the cube</span></span>  
  
1.  <span data-ttu-id="efcaf-106">Pase a la pestaña **Estructura de cubo** del Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , expanda el grupo de medida **Internet Sales** del panel **Medidas** , haga clic con el botón secundario en **Order Quantity**y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="efcaf-106">Switch to the **Cube Structure** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, expand the **Internet Sales** measure group in the **Measures** pane, right-click **Order Quantity**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="efcaf-107">En la ventana Propiedades, haga clic en el icono de chincheta **Ocultar automáticamente** para anclar la ventana Propiedades y dejarla abierta.</span><span class="sxs-lookup"><span data-stu-id="efcaf-107">In the Properties window, click the **Auto Hide** pushpin icon to pin the Properties window open.</span></span>  
  
     <span data-ttu-id="efcaf-108">Es más fácil cambiar las propiedades para varios elementos del cubo cuando la ventana Propiedades permanece abierta.</span><span class="sxs-lookup"><span data-stu-id="efcaf-108">It is easier to change properties for several items in the cube when the Properties window remains open.</span></span>  
  
3.  <span data-ttu-id="efcaf-109">En la ventana Propiedades, haga clic en la lista **FormatString** y escriba **#,#**.</span><span class="sxs-lookup"><span data-stu-id="efcaf-109">In the Properties window, click the **FormatString** list, and then type **#,#**.</span></span>  
  
4.  <span data-ttu-id="efcaf-110">En la barra de herramientas de la pestaña **Estructura de cubo** , haga clic en el icono **Mostrar la cuadrícula de medidas** situado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="efcaf-110">On the toolbar of the **Cube Structure** tab, click the **Show Measures Grid** icon on the left.</span></span>  
  
     <span data-ttu-id="efcaf-111">La vista de cuadrícula permite seleccionar varias medidas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="efcaf-111">The grid view lets you select multiple measures at the same time.</span></span>  
  
5.  <span data-ttu-id="efcaf-112">Seleccione una de las medidas siguientes.</span><span class="sxs-lookup"><span data-stu-id="efcaf-112">Select the following measures.</span></span> <span data-ttu-id="efcaf-113">Para seleccionar varias medidas, haga clic en cada una de ellas mientras mantiene presionada la tecla CTRL:</span><span class="sxs-lookup"><span data-stu-id="efcaf-113">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="efcaf-114">**Precio unitario**</span><span class="sxs-lookup"><span data-stu-id="efcaf-114">**Unit Price**</span></span>  
  
    -   <span data-ttu-id="efcaf-115">**Extended Amount**</span><span class="sxs-lookup"><span data-stu-id="efcaf-115">**Extended Amount**</span></span>  
  
    -   <span data-ttu-id="efcaf-116">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="efcaf-116">**Discount Amount**</span></span>  
  
    -   <span data-ttu-id="efcaf-117">**Product Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="efcaf-117">**Product Standard Cost**</span></span>  
  
    -   <span data-ttu-id="efcaf-118">**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="efcaf-118">**Total Product Cost**</span></span>  
  
    -   <span data-ttu-id="efcaf-119">**Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="efcaf-119">**Sales Amount**</span></span>  
  
    -   <span data-ttu-id="efcaf-120">**Tax Amt**</span><span class="sxs-lookup"><span data-stu-id="efcaf-120">**Tax Amt**</span></span>  
  
    -   <span data-ttu-id="efcaf-121">**Freight**</span><span class="sxs-lookup"><span data-stu-id="efcaf-121">**Freight**</span></span>  
  
6.  <span data-ttu-id="efcaf-122">En la ventana Propiedades, en la lista **FormatString** , seleccione **Currency**.</span><span class="sxs-lookup"><span data-stu-id="efcaf-122">In the Properties window, in the **FormatString** list, select **Currency**.</span></span>  
  
7.  <span data-ttu-id="efcaf-123">En la lista desplegable de la parte superior de la ventana Propiedades (justo debajo de la barra de título), seleccione la medida **Unit Price Discount Pct**y, después, seleccione **Porcentaje** en la lista **FormatString** .</span><span class="sxs-lookup"><span data-stu-id="efcaf-123">In the drop-down list at the top of the Properties window (right below the title bar), select the measure **Unit Price Discount Pct**, and then select **Percent** in the **FormatString** list.</span></span>  
  
8.  <span data-ttu-id="efcaf-124">En el ventana Propiedades, cambie la propiedad **nombre** de la medida **unidad de descuento por precio unitario** a `Unit Price Discount Percentage` .</span><span class="sxs-lookup"><span data-stu-id="efcaf-124">In the Properties window, change the **Name** property for the **Unit Price Discount Pct** measure to `Unit Price Discount Percentage`.</span></span>  
  
9. <span data-ttu-id="efcaf-125">En el panel **medidas** , haga clic en **Tax AMT** y cambie el nombre de esta medida a `Tax Amount` .</span><span class="sxs-lookup"><span data-stu-id="efcaf-125">In the **Measures** pane, click **Tax Amt** and change the name of this measure to `Tax Amount`.</span></span>  
  
10. <span data-ttu-id="efcaf-126">En la ventana Propiedades, haga clic en el icono **Ocultar automáticamente** para ocultar la ventana Propiedades y, a continuación, haga clic en **Mostrar el árbol de medidas** en la barra de herramientas de la pestaña **Estructura de cubo** .</span><span class="sxs-lookup"><span data-stu-id="efcaf-126">In the Properties window, click the **Auto Hide** icon to hide the Properties window, and then click **Show Measures Tree** on the toolbar of the **Cube Structure** tab.</span></span>  
  
11. <span data-ttu-id="efcaf-127">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="efcaf-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="efcaf-128">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="efcaf-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="efcaf-129">Modificar la dimensión Customer</span><span class="sxs-lookup"><span data-stu-id="efcaf-129">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="efcaf-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efcaf-130">See Also</span></span>  
 <span data-ttu-id="efcaf-131">[Definir dimensiones de base de datos](multidimensional-models/define-database-dimensions.md) </span><span class="sxs-lookup"><span data-stu-id="efcaf-131">[Define Database Dimensions](multidimensional-models/define-database-dimensions.md) </span></span>  
 [<span data-ttu-id="efcaf-132">Configurar propiedades de medidas</span><span class="sxs-lookup"><span data-stu-id="efcaf-132">Configure Measure Properties</span></span>](multidimensional-models/configure-measure-properties.md)  
  
  
