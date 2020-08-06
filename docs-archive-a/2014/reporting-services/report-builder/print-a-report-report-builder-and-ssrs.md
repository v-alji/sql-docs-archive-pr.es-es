---
title: Imprimir un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b96936c9-c387-41a9-8c19-6eb325769ffd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe029019cdf9739153256db399cfa1426d3ba632
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670825"
---
# <a name="print-a-report-report-builder-and-ssrs"></a><span data-ttu-id="6dafe-102">Imprimir un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6dafe-102">Print a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6dafe-103">Después de guardar un informe en un servidor de informes, puede ver e imprimir el informe desde un explorador, el Administrador de informes o cualquier aplicación que use para ver un informe exportado.</span><span class="sxs-lookup"><span data-stu-id="6dafe-103">After you save a report to a report server, you can view and print the report from a browser, Report Manager, or any application that you use to view an exported report.</span></span> <span data-ttu-id="6dafe-104">Antes de guardar un informe, puede imprimirlo desde su vista previa.</span><span class="sxs-lookup"><span data-stu-id="6dafe-104">Before saving a report, you can print it when you preview it.</span></span>  
  
 <span data-ttu-id="6dafe-105">Cuando imprime un informe, puede especificar el tamaño del papel que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="6dafe-105">When you print a report, you can specify the size of the paper to use.</span></span> <span data-ttu-id="6dafe-106">El tamaño del papel determina el número de páginas de un informe y los datos del informe que caben en cada página.</span><span class="sxs-lookup"><span data-stu-id="6dafe-106">The size of the paper determines the number of pages in a report and which report data fits on each page.</span></span> <span data-ttu-id="6dafe-107">El tamaño del papel solamente afecta a los informes representados con representadores de saltos de página forzados: PDF, Imagen e Imprimir.</span><span class="sxs-lookup"><span data-stu-id="6dafe-107">Paper size affects only reports that are rendered with hard page-break renders: PDF, Image, and Print.</span></span> <span data-ttu-id="6dafe-108">El establecimiento del tamaño del papel no tiene ningún efecto en otros representadores.</span><span class="sxs-lookup"><span data-stu-id="6dafe-108">Setting the paper size has no effect on other renderers.</span></span> <span data-ttu-id="6dafe-109">Para más información, vea [Comportamientos de la representación &#40;Generador de informes y SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6dafe-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="6dafe-110">Desde la barra de herramientas del visor de informes del Administrador de informes o en la vista previa del Generador de informes, puede exportar un informe a un representador de saltos de página duros o hacer clic en el botón Imprimir para imprimir una copia del informe.</span><span class="sxs-lookup"><span data-stu-id="6dafe-110">From the report viewer toolbar in Report Manager or in preview in Report Builder, you can export a report to a hard page-break renderer or click the Print button to print a copy of the report.</span></span> <span data-ttu-id="6dafe-111">Es posible que necesite establecer el tamaño del papel u otras propiedades de configuración de página.</span><span class="sxs-lookup"><span data-stu-id="6dafe-111">You might need to set the paper size or other page setup properties.</span></span> <span data-ttu-id="6dafe-112">Use el cuadro de diálogo **Propiedades del informe** para cambiar las propiedades de configuración de página, incluyendo el tamaño del papel.</span><span class="sxs-lookup"><span data-stu-id="6dafe-112">Use the **Report Properties** dialog box to change page setup properties, including paper size.</span></span>  
  
 <span data-ttu-id="6dafe-113">Puede especificar los márgenes de impresión de la página en dos ubicaciones diferentes: en modo de diseño y en modo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6dafe-113">You can specify print page margins in two different locations: in design mode and in run mode.</span></span>  
  
-   <span data-ttu-id="6dafe-114">**Modo de diseño.**</span><span class="sxs-lookup"><span data-stu-id="6dafe-114">**Design mode.**</span></span> <span data-ttu-id="6dafe-115">Al establecer los márgenes de página en modo de diseño, esta configuración se guarda en la definición de informe al guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="6dafe-115">When you set page margins in design mode, these settings are saved in the report definition when you save the report.</span></span>  
  
-   <span data-ttu-id="6dafe-116">**Modo de ejecución.**</span><span class="sxs-lookup"><span data-stu-id="6dafe-116">**Run mode.**</span></span> <span data-ttu-id="6dafe-117">Al establecer los márgenes de página en modo de ejecución, esta información no se guarda en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="6dafe-117">When you set page margins in run mode, this information is not saved in the report definition.</span></span> <span data-ttu-id="6dafe-118">La siguiente vez que imprima el informe, recibirá la configuración de la definición de informe, a menos que indique de nuevo sus márgenes de impresión.</span><span class="sxs-lookup"><span data-stu-id="6dafe-118">The next time you print the report, you will get the settings from the report definition, unless you indicate your print margins again.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6dafe-119">Los márgenes de impresión no se muestran en los modos de diseño o de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6dafe-119">Print margins are not displayed in design or run modes.</span></span> <span data-ttu-id="6dafe-120">No hay ninguna relación entre el área expuesta de diseño y el área de impresión de su informe.</span><span class="sxs-lookup"><span data-stu-id="6dafe-120">There is no relationship between the design surface area and the print area of your report.</span></span> <span data-ttu-id="6dafe-121">Para ver los márgenes de impresión, en modo de ejecución haga clic en Diseño de impresión en la pestaña **Ejecutar** de la Cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="6dafe-121">To see print margins, in run mode, click Print Layout on the **Run** tab on the Ribbon.</span></span>  
  
 <span data-ttu-id="6dafe-122">Para más información sobre la paginación de informes, vea [Paginación en Reporting Services &#40;Generador de informes y SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6dafe-122">For more information about report paging, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-print-a-report-in-report-builder"></a><span data-ttu-id="6dafe-123">Para imprimir un informe en el Generador de informes</span><span class="sxs-lookup"><span data-stu-id="6dafe-123">To print a report in Report Builder</span></span>  
  
1.  <span data-ttu-id="6dafe-124">Abra un informe.</span><span class="sxs-lookup"><span data-stu-id="6dafe-124">Open a report.</span></span>  
  
2.  <span data-ttu-id="6dafe-125">En la pestaña Inicio, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6dafe-125">On the Home tab, click **Run**.</span></span>  
  
3.  <span data-ttu-id="6dafe-126">(opcional) Haga clic en **Diseño de impresión** para ver el aspecto que tendrá el informe cuando se imprima.</span><span class="sxs-lookup"><span data-stu-id="6dafe-126">(optional) Click **Print Layout** to see how the report will look when it is printed.</span></span>  
  
4.  <span data-ttu-id="6dafe-127">(opcional) Haga clic en **Configurar página** para configurar el papel, la orientación y los márgenes.</span><span class="sxs-lookup"><span data-stu-id="6dafe-127">(optional) Click **Page Setup** to set paper, orientation, and margins.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6dafe-128">Los valores predeterminados de estas opciones proceden de las propiedades de informe, que se establecen en la vista Diseño.</span><span class="sxs-lookup"><span data-stu-id="6dafe-128">The default values for these come from the report properties, which are set in Design view.</span></span> <span data-ttu-id="6dafe-129">Los valores que establece en el cuadro de diálogo **Configurar página** solamente valen para esta sesión.</span><span class="sxs-lookup"><span data-stu-id="6dafe-129">The values you set here in the **Page Setup** dialog box are for this session only.</span></span> <span data-ttu-id="6dafe-130">Cuando cierre este informe y lo vuelva a abrir, tendrá de nuevo los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="6dafe-130">When you close this report and reopen it, it will have the default values again.</span></span>  
  
5.  <span data-ttu-id="6dafe-131">Haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="6dafe-131">Click **Print**.</span></span>  
  
6.  <span data-ttu-id="6dafe-132">En el cuadro de diálogo **Imprimir** , seleccione una impresora y especifique otras opciones de impresión.</span><span class="sxs-lookup"><span data-stu-id="6dafe-132">In the **Print** dialog box, select a printer and specify other printing options.</span></span>  
  
### <a name="to-print-a-report-from-a-web-browser-application"></a><span data-ttu-id="6dafe-133">Para imprimir un informe desde una aplicación de explorador web</span><span class="sxs-lookup"><span data-stu-id="6dafe-133">To print a report from a Web browser application</span></span>  
  
1.  <span data-ttu-id="6dafe-134">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6dafe-134">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="6dafe-135">En el Administrador de informes, navegue al informe que desea imprimir.</span><span class="sxs-lookup"><span data-stu-id="6dafe-135">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="6dafe-136">Abra el informe.</span><span class="sxs-lookup"><span data-stu-id="6dafe-136">Open the report.</span></span>  
  
3.  <span data-ttu-id="6dafe-137">En la barra de herramientas que se encuentra en la parte superior del informe, haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="6dafe-137">On the toolbar at the top of the report, click **Print**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6dafe-138">La primera vez que imprima un informe HTML, el servidor de informes le pedirá que instale el control ActiveX que se usa para imprimir.</span><span class="sxs-lookup"><span data-stu-id="6dafe-138">The first time you print an HTML report, the report server prompts you to install an ActiveX control used for printing.</span></span> <span data-ttu-id="6dafe-139">Para poder imprimir, deberá instalar y configurar el control.</span><span class="sxs-lookup"><span data-stu-id="6dafe-139">You must install and configure the control to print.</span></span>  
  
4.  <span data-ttu-id="6dafe-140">En el cuadro de diálogo **Imprimir** , seleccione una impresora y haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="6dafe-140">In the **Print** dialog box, select a printer, and then click **Prin**t.</span></span>  
  
### <a name="to-print-a-report-from-other-applications"></a><span data-ttu-id="6dafe-141">Para imprimir un informe desde otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6dafe-141">To print a report from other applications</span></span>  
  
1.  <span data-ttu-id="6dafe-142">En el Administrador de informes, navegue al informe que desea imprimir.</span><span class="sxs-lookup"><span data-stu-id="6dafe-142">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="6dafe-143">Abra el informe.</span><span class="sxs-lookup"><span data-stu-id="6dafe-143">Open the report.</span></span>  
  
2.  <span data-ttu-id="6dafe-144">En la barra de herramientas situada en la parte superior del informe, seleccione un formato de representación y, a continuación, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="6dafe-144">On the toolbar at the top of the report, select a rendering format, and then click **Export**.</span></span> <span data-ttu-id="6dafe-145">El informe se abre en la aplicación de visor correspondiente al formato de representación.</span><span class="sxs-lookup"><span data-stu-id="6dafe-145">The report opens in a viewer application that corresponds to the rendering format.</span></span>  
  
     <span data-ttu-id="6dafe-146">Por ejemplo, si selecciona PDF, el informe se abre en Adobe Acrobat Reader.</span><span class="sxs-lookup"><span data-stu-id="6dafe-146">For example, if you select PDF, the report opens in Adobe Acrobat Reader.</span></span>  
  
3.  <span data-ttu-id="6dafe-147">En el menú **Archivo** de dicho programa, haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="6dafe-147">On the **File** menu in that program, click **Print**.</span></span>  
  
### <a name="to-change-paper-size"></a><span data-ttu-id="6dafe-148">Para cambiar el tamaño del papel</span><span class="sxs-lookup"><span data-stu-id="6dafe-148">To change paper size</span></span>  
  
1.  <span data-ttu-id="6dafe-149">Haga clic con el botón derecho fuera del cuerpo del informe y haga clic en **Propiedades del informe**.</span><span class="sxs-lookup"><span data-stu-id="6dafe-149">Right-click outside of the report body and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="6dafe-150">En **Configurar página**, seleccione un valor en la lista **Tamaño de papel** .</span><span class="sxs-lookup"><span data-stu-id="6dafe-150">In **Page Setup**, select a value from the **Paper Size** list.</span></span> <span data-ttu-id="6dafe-151">Cada opción rellena las propiedades **Ancho** y **Alto** .</span><span class="sxs-lookup"><span data-stu-id="6dafe-151">Each option populates the **Width** and **Height** properties.</span></span> <span data-ttu-id="6dafe-152">También puede especificar un tamaño personalizado escribiendo valores numéricos en los cuadros **Ancho** y **Alto** .</span><span class="sxs-lookup"><span data-stu-id="6dafe-152">You can also specify a custom size by typing numeric values in the **Width** and **Height** boxes.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="6dafe-153">Los valores de tamaño tienen una unidad predeterminada en función de la configuración regional del usuario.</span><span class="sxs-lookup"><span data-stu-id="6dafe-153">Size values have a default unit based on the user's locale settings.</span></span> <span data-ttu-id="6dafe-154">Para designar una unidad diferente, escriba un designador de unidad física, por ejemplo cm, mm, pt o pc después del valor numérico.</span><span class="sxs-lookup"><span data-stu-id="6dafe-154">To designate a different unit, type a physical unit designator such as cm, mm, pt, or pc after the numeric value.</span></span>  
  
### <a name="to-set-page-margins-in-design-mode"></a><span data-ttu-id="6dafe-155">Para establecer los márgenes de página en modo de diseño</span><span class="sxs-lookup"><span data-stu-id="6dafe-155">To set page margins in design mode</span></span>  
  
-   <span data-ttu-id="6dafe-156">Haga clic con el botón derecho en el área azul que rodea la superficie de diseño, haga clic en **Propiedades del informe**y luego en la página **Configurar página** .</span><span class="sxs-lookup"><span data-stu-id="6dafe-156">Right-click the blue area around the design surface, click **Report Properties**, and then click the **Page Setup** page.</span></span>  
  
### <a name="to-set-page-margins-in-run-mode"></a><span data-ttu-id="6dafe-157">Para establecer los márgenes de página en modo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6dafe-157">To set page margins in run mode</span></span>  
  
-   <span data-ttu-id="6dafe-158">Haga clic en **Configurar página** en la pestaña **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="6dafe-158">Click **Page Setup** on the **Run** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dafe-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6dafe-159">See Also</span></span>  
 <span data-ttu-id="6dafe-160">[Imprimir informes &#40;Generador de informes y SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6dafe-160">[Print Reports &#40;Report Builder and SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6dafe-161">[Exportar informes &#40;Generador de informes y SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6dafe-161">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6dafe-162">[Propiedades del informe (cuadro de diálogo), Configurar página &#40;Generador de informes&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6dafe-162">[Report Properties Dialog Box, Page Setup &#40;Report Builder&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span></span>  
 [<span data-ttu-id="6dafe-163">Vista de diseño de informe &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="6dafe-163">Report Design View &#40;Report Builder&#41;</span></span>](report-design-view-report-builder.md)  
  
  
