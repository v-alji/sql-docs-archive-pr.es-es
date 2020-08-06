---
title: Agregar efectos 3D a un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab9625d8-6557-4a4d-8123-eefa7c066ff5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4fcd90452e32b760bc446ac5d085ed00520a2f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676368"
---
# <a name="add-3d-effects-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="0b2b1-102">Agregar efectos 3D a un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="0b2b1-102">Add 3D Effects to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0b2b1-103">Se pueden usar efectos tridimensionales (3D) para dar profundidad y agregar impacto visual a un gráfico.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-103">Three-dimensional (3D) effects can be used to provide depth and add visual impact to your chart.</span></span> <span data-ttu-id="0b2b1-104">Por ejemplo, si desea resaltar un sector específico de un gráfico circular seccionado, puede girar y cambiar la perspectiva del gráfico para que los usuarios se fijen primero en dicho sector.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-104">For example, if you want to emphasize a particular slice of an exploded pie chart, you can rotate and change the perspective of the chart so that people notice that slice first.</span></span> <span data-ttu-id="0b2b1-105">Cuando se aplican efectos 3D al gráfico, se deshabilitan todos los colores de degradado y los estilos de sombreado.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-105">When 3D effects are applied to your chart, all gradient colors and hatching styles are disabled.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-3d-effects-to-a-range-area-line-scatter-or-polar-chart"></a><span data-ttu-id="0b2b1-106">Para aplicar efectos 3D a un gráfico de intervalos, áreas, líneas, dispersión o polar</span><span class="sxs-lookup"><span data-stu-id="0b2b1-106">To apply 3D effects to a Range, Area, Line, Scatter or Polar chart</span></span>  
  
1.  <span data-ttu-id="0b2b1-107">Haga clic con el botón derecho en cualquier parte dentro del área del gráfico y seleccione **Efectos 3D**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-107">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="0b2b1-108">Aparecerá el cuadro de diálogo **Propiedades del área de gráfico** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-108">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="0b2b1-109">En **Opciones 3D**, seleccione la opción **Habilitar 3D** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-109">In **3D Options**, select the **Enable 3D** option.</span></span>  
  
3.  <span data-ttu-id="0b2b1-110">(Opcional) En **Opciones 3D**, puede establecer diversas propiedades relacionadas con opciones de ángulos y escenas 3D.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-110">(Optional) In **3D Options**, you can set a variety of properties relating to 3D angles and scene options.</span></span> <span data-ttu-id="0b2b1-111">Para obtener más información sobre estas propiedades, vea [Aplicar 3D, bisel y otros efectos a un gráfico &#40;Generador de informes y SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="0b2b1-111">For more information about these properties, see [3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md).</span></span>  
  
4.  <span data-ttu-id="0b2b1-112">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-112">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-funnel-chart"></a><span data-ttu-id="0b2b1-113">Para aplicar efectos 3D a un gráfico de embudo</span><span class="sxs-lookup"><span data-stu-id="0b2b1-113">To apply 3D effects to a Funnel chart</span></span>  
  
1.  <span data-ttu-id="0b2b1-114">Haga clic con el botón derecho en cualquier parte dentro del área del gráfico y seleccione **Efectos 3D**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-114">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="0b2b1-115">Aparecerá el cuadro de diálogo **Propiedades del área de gráfico** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-115">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="0b2b1-116">En **Opciones 3D**, seleccione la opción **Habilitar 3D** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-116">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="0b2b1-117">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-117">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="0b2b1-118">(Opcional) Para personalizar el aspecto visual del gráfico de embudo, puede ir al panel Propiedades y cambiar propiedades específicas para ese tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-118">(Optional) To customize the funnel chart visual appearance, you can go to the Properties pane and change properties specific to the funnel chart.</span></span>  
  
    1.  <span data-ttu-id="0b2b1-119">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-119">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="0b2b1-120">En la superficie de diseño, haga clic en cualquier parte del gráfico de embudo.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-120">On the design surface, click anywhere on the funnel.</span></span> <span data-ttu-id="0b2b1-121">Se muestran las propiedades de las series del gráfico de embudo en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-121">The properties for the series of the funnel chart are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="0b2b1-122">En la sección **General** , expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-122">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="0b2b1-123">Para la propiedad **Funnel3DDrawingStyle** , seleccione si el embudo se mostrará como circular o cuadrado.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-123">For the **Funnel3DDrawingStyle** property, select whether the funnel will be shown with as circular or square.</span></span>  
  
    5.  <span data-ttu-id="0b2b1-124">Para la propiedad **Funnel3DRotationAngle** , establezca un valor entre -10 y 10.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-124">For the **Funnel3DRotationAngle** property, set a value between -10 and 10.</span></span> <span data-ttu-id="0b2b1-125">Esto determinará el grado de inclinación que se mostrará en el gráfico de embudo 3D.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-125">This will determine the degree of tilt that will be displayed on the 3D funnel chart.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-pie-chart"></a><span data-ttu-id="0b2b1-126">Para aplicar efectos 3D a un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="0b2b1-126">To apply 3D effects to a Pie chart</span></span>  
  
1.  <span data-ttu-id="0b2b1-127">Haga clic con el botón secundario en cualquier parte dentro del área del gráfico y seleccione Efectos 3D.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-127">Right-click anywhere inside the chart area and select 3D Effects.</span></span> <span data-ttu-id="0b2b1-128">Aparecerá el cuadro de diálogo **Propiedades del área de gráfico** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-128">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="0b2b1-129">En **Opciones 3D**, seleccione la opción **Habilitar 3D** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-129">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="0b2b1-130">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-130">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="0b2b1-131">(Opcional) En **Giro**, escriba un valor entero que represente el giro horizontal del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-131">(Optional) In **Rotation**, type an integer value that represents the horizontal rotation of the pie chart.</span></span>  
  
4.  <span data-ttu-id="0b2b1-132">(Opcional) En **Inclinación**, escriba un valor entero que represente el giro de inclinación vertical del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-132">(Optional) In **Inclination**, type an integer value that represents the vertical tilt rotation of the pie chart.</span></span>  
  
5.  <span data-ttu-id="0b2b1-133">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-133">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-bar-or-column-chart"></a><span data-ttu-id="0b2b1-134">Para aplicar efectos 3D a un gráfico de barras o de columnas</span><span class="sxs-lookup"><span data-stu-id="0b2b1-134">To apply 3D effects to a Bar or Column chart</span></span>  
  
1.  <span data-ttu-id="0b2b1-135">Haga clic con el botón derecho en cualquier parte dentro del área del gráfico y seleccione **Efectos 3D**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-135">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="0b2b1-136">Aparecerá el cuadro de diálogo **Propiedades del área de gráfico** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-136">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="0b2b1-137">Seleccione la opción **Habilitar 3D** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-137">Select the **Enable 3D** option.</span></span> <span data-ttu-id="0b2b1-138">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-138">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="0b2b1-139">(Opcional) Seleccione la opción **Habilitar agrupación en clústeres** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-139">(Optional) Select the **Enable series clustering** option.</span></span> <span data-ttu-id="0b2b1-140">Si el gráfico contiene varias series de gráficos de barras o de columnas, esta opción mostrará las series agrupadas en clústeres.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-140">If your chart contains multiple bar or column chart series, this option will display the series as clustered.</span></span> <span data-ttu-id="0b2b1-141">De forma predeterminada, cuando hay varias series de barras o de columnas se muestran unas al lado de otras.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-141">By default, multiple bar or column series are shown side-by-side.</span></span>  
  
4.  <span data-ttu-id="0b2b1-142">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-142">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="0b2b1-143">(Opcional) Para agregar efectos de cilindro a un gráfico de barras o de columnas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0b2b1-143">(Optional) To add cylinder effects to a bar or column chart, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="0b2b1-144">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-144">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="0b2b1-145">En la superficie de diseño, haga clic en cualquiera de las barras en la serie.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-145">On the design surface, click any of the bars in the series.</span></span> <span data-ttu-id="0b2b1-146">Las propiedades de la serie se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b2b1-146">The properties for the series are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="0b2b1-147">En la sección **General** , expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-147">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="0b2b1-148">Para la propiedad **DrawingStyle** , especifique el valor **Cylinder** .</span><span class="sxs-lookup"><span data-stu-id="0b2b1-148">For the **DrawingStyle** property, specify the **Cylinder** value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b2b1-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b2b1-149">See Also</span></span>  
 <span data-ttu-id="0b2b1-150">[Aplicar 3D, bisel y otros efectos a un gráfico &#40;Generador de informes y SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="0b2b1-150">[3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span></span>  
 <span data-ttu-id="0b2b1-151">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0b2b1-151">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0b2b1-152">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0b2b1-152">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
