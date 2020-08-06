---
title: Cuadro de diálogo Propiedades de la acción (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.action.f1
- "10413"
- "10504"
- sql12.rtp.rptdesigner.calculatedseriesproperties.action.f1
- sql12.rtp.rptdesigner.pictureproperties.action.f1
- sql12.rtp.rptdesigner.actionproperties.f1
- sql12.rtp.rptdesigner.charttitleproperties.action.f1
- "10133"
- "10052"
- "10147"
- sql12.rtp.rptdesigner.chartproperties.action.f1
- "10122"
- sql12.rtp.rptdesigner.serieslabelproperties.action.f1
- sql12.rtp.rptdesigner.textboxproperties.action.f1
- "10162"
- "10168"
- sql12.rtp.rptdesigner.textproperties.action.f1
- sql12.rtp.rptdesigner.placeholderproperties.action.f1
- "10250"
- "10129"
- "10244"
- sql12.rtp.rptdesigner.seriesproperties.action.f1
ms.assetid: 2c5d915b-4f97-42cf-b8f1-49ca3ff3d0f9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77b51af0763010676b95fcedb433ab963fc7fcdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674656"
---
# <a name="action-properties-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="ae9d1-102">Cuadro de diálogo Propiedades de acción (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="ae9d1-102">Action Properties Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ae9d1-103">El cuadro de diálogo **Acción** se puede usar para habilitar las opciones de hipervínculo para los elementos de gráfico, medidor y mapa que admitan vínculos.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-103">The **Action** dialog box can be used to enable hyperlink options for a chart, gauge, and map elements that support links.</span></span> <span data-ttu-id="ae9d1-104">Defina una acción para que un usuario pueda hacer clic en el informe y vincularse a una dirección URL, a un informe diferente en el mismo servidor de informes o a un sitio de SharePoint integrado con un servidor de informes, o a una ubicación diferente del mismo informe.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-104">Define an action so that a user can click on the report and link to a URL, to a different report on the same report server or on a SharePoint site that is integrated with a report server, or to a different location in the same report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae9d1-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="ae9d1-105">Options</span></span>  
 <span data-ttu-id="ae9d1-106">**Habilitar como una acción**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-106">**Enable as an action**</span></span>  
 <span data-ttu-id="ae9d1-107">Seleccione una opción para indicar la acción que tendrá lugar cuando el usuario haga clic en el elemento.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-107">Select an option to indicate the action to perform when the user clicks the item.</span></span>  
  
 <span data-ttu-id="ae9d1-108">**None**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-108">**None**</span></span>  
 <span data-ttu-id="ae9d1-109">Elija esta opción para indicar que el elemento no tiene ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-109">Choose this option to indicate that the item has no action.</span></span>  
  
 <span data-ttu-id="ae9d1-110">**Ir al informe**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-110">**Go to report**</span></span>  
 <span data-ttu-id="ae9d1-111">Elija esta opción para crear un vínculo a un informe detallado que se encuentra en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-111">Choose this option to create a link to a drillthrough report that is located on a report server.</span></span> <span data-ttu-id="ae9d1-112">Al seleccionar **Ir a informe**, aparecen las siguientes opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-112">The following additional options appear when you select **Go to report**.</span></span>  
  
 <span data-ttu-id="ae9d1-113">**Especificar un informe**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-113">**Specify a report**</span></span>  
 <span data-ttu-id="ae9d1-114">Escriba o seleccione el nombre del informe que desea utilizar como informe detallado.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-114">Type or select the name of the report that you want to use as a drillthrough report.</span></span> <span data-ttu-id="ae9d1-115">Los informes detallados deben estar en el mismo servidor de informes que este informe.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-115">Drillthrough reports must be on the same report server as this report.</span></span>  
  
 <span data-ttu-id="ae9d1-116">En el caso de un informe publicado en un servidor de informes configurado para el modo nativo, use una ruta de acceso completa o relativa sin la extensión del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-116">For a report published to a report server configured for native mode, use a full or relative path without the file name extension.</span></span> <span data-ttu-id="ae9d1-117">Si el informe se encuentra en la misma carpeta que el actual, use solo el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-117">If the report is in the same folder as the current report, use the name of the report only.</span></span> <span data-ttu-id="ae9d1-118">Si el informe está en una carpeta diferente del mismo servidor de informes, use una ruta de acceso relativa o una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-118">If the report is in a different folder on the same report server, use a relative path or a full path.</span></span> <span data-ttu-id="ae9d1-119">Una ruta de acceso relativa comienza en la carpeta actual y sube por la jerarquía de carpetas, por ejemplo, ../Carpeta2/Informe1.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-119">A relative path starts from the current folder and moves up the folder hierarchy, for example, ../Folder2/Report1.</span></span> <span data-ttu-id="ae9d1-120">Una ruta de acceso completa se inicia en /, la carpeta Inicio.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-120">A full path starts from /, the Home folder.</span></span> <span data-ttu-id="ae9d1-121">Por ejemplo, /Informes/Informe1.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-121">For example, /Reports/Report1.</span></span>  
  
 <span data-ttu-id="ae9d1-122">En el caso de un informe publicado en un servidor de informes configurado en el modo integrado de SharePoint, utilice una dirección URL completa, incluida la extensión del nombre de archivo (.rdl).</span><span class="sxs-lookup"><span data-stu-id="ae9d1-122">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL including the file name extension (.rdl).</span></span> <span data-ttu-id="ae9d1-123">Por ejemplo, http:// *\<SharePointservername>/\<site>* /Documents/Report1.RDL.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-123">For example, http://*\<SharePointservername>/\<site>*/Documents/Report1.rdl.</span></span> <span data-ttu-id="ae9d1-124">No se admiten las rutas de acceso relativas.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-124">Relative paths are not supported.</span></span>  
  
 <span data-ttu-id="ae9d1-125">Para obtener más información, vea [Especificar las rutas de acceso a los elementos externos &#40;Generador de informes y SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) en la [la documentación del Generador de informes](https://go.microsoft.com/fwlink/?LinkId=154494) en msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-125">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) in the [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="ae9d1-126">**Usar estos parámetros para ejecutar el informe**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-126">**Use these parameters to run the report**</span></span>  
 <span data-ttu-id="ae9d1-127">Agregue una lista de parámetros para pasárselos al informe detallado.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-127">Add a list of parameters to pass to the drillthrough report.</span></span> <span data-ttu-id="ae9d1-128">Los nombres de los parámetros deben coincidir con los de los parámetros definidos para el informe de destino.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-128">The parameter names must match the parameters defined for the target report.</span></span> <span data-ttu-id="ae9d1-129">Use los botones **Agregar** y **Eliminar** para agregar y quitar parámetros, y las flechas hacia arriba y hacia abajo para ordenar la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-129">Use the **Add** and **Delete** buttons to add and remove parameters and use the up and down arrows to order the list of parameters.</span></span>  
  
 <span data-ttu-id="ae9d1-130">**Add**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-130">**Add**</span></span>  
 <span data-ttu-id="ae9d1-131">Agregue un nuevo parámetro para pasárselo al informe detallado.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-131">Add a new parameter to pass to the drillthrough report.</span></span>  
  
 <span data-ttu-id="ae9d1-132">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-132">**Delete**</span></span>  
 <span data-ttu-id="ae9d1-133">Elimina un parámetro del informe detallado.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-133">Delete a parameter for the drillthrough report.</span></span>  
  
 <span data-ttu-id="ae9d1-134">**Flecha arriba**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-134">**Up arrow**</span></span>  
 <span data-ttu-id="ae9d1-135">Mueve el parámetro hacia arriba en la lista.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-135">Move the parameter up in the list.</span></span>  
  
 <span data-ttu-id="ae9d1-136">**Flecha abajo**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-136">**Down arrow**</span></span>  
 <span data-ttu-id="ae9d1-137">Mueve el parámetro hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-137">Move the parameter down in the list.</span></span>  
  
 <span data-ttu-id="ae9d1-138">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-138">**Name**</span></span>  
 <span data-ttu-id="ae9d1-139">Escriba el nombre de un parámetro definido en el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-139">Type text that is the name of a parameter defined in the drillthrough report.</span></span>  
  
 <span data-ttu-id="ae9d1-140">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-140">**Value**</span></span>  
 <span data-ttu-id="ae9d1-141">Escriba o seleccione el valor que debe pasarse al parámetro especificado para el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-141">Type or select a value to pass for the named parameter in the drillthrough report.</span></span> <span data-ttu-id="ae9d1-142">Haga clic en el botón **Expresión** (*fx*) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-142">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="ae9d1-143">**Omitir**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-143">**Omit**</span></span>  
 <span data-ttu-id="ae9d1-144">Seleccione esta opción para impedir que el parámetro se ejecute.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-144">Select to prevent the parameter from running.</span></span> <span data-ttu-id="ae9d1-145">De forma predeterminada, esta casilla está desactivada.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-145">By default, this check box is cleared and not active.</span></span> <span data-ttu-id="ae9d1-146">Para activar la casilla, haga clic en el botón **Expresión** (*fx*) y escriba **True** o cree una expresión.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-146">To select the check box, click the **Expression** (*fx*) button and either type **True** or create an expression.</span></span> <span data-ttu-id="ae9d1-147">La casilla se activa al hacer clic en **Aceptar** en el cuadro de diálogo **expresión** .</span><span class="sxs-lookup"><span data-stu-id="ae9d1-147">The check box is selected when you click **OK** in the **Expression** dialog box.</span></span>  
  
 <span data-ttu-id="ae9d1-148">**Ir a marcador**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-148">**Go to bookmark**</span></span>  
 <span data-ttu-id="ae9d1-149">Elija esta opción para definir un vínculo a un marcador en el informe actual.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-149">Choose this option to define a link to a bookmark in the current report.</span></span> <span data-ttu-id="ae9d1-150">Al seleccionar **Ir a marcador**, aparece la siguiente opción adicional.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-150">The following additional option appears when you select **Go to bookmark**.</span></span>  
  
 <span data-ttu-id="ae9d1-151">**Seleccionar marcador**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-151">**Select bookmark**</span></span>  
 <span data-ttu-id="ae9d1-152">Escriba o seleccione el identificador de marcador al que debe saltar el informe cuando el usuario haga clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-152">Type or select the bookmark ID for the report to jump to when the user clicks the link.</span></span> <span data-ttu-id="ae9d1-153">Haga clic en el botón Expresión (**fx**) para modificar la expresión.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-153">Click the Expression (**fx**) button to change the expression.</span></span> <span data-ttu-id="ae9d1-154">El identificador de marcador puede ser un identificador estático o una expresión que se evalúa como un identificador de marcador.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-154">The bookmark ID can be either a static ID or an expression that evaluates to a bookmark ID.</span></span> <span data-ttu-id="ae9d1-155">La expresión puede incluir un campo que contenga un identificador de marcador.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-155">The expression can include a field that contains a bookmark ID.</span></span>  
  
 <span data-ttu-id="ae9d1-156">Para crear un vínculo a un marcador, debe definir primero la propiedad Bookmark de un elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-156">To link to a bookmark, you must first set the Bookmark property of a report item.</span></span> <span data-ttu-id="ae9d1-157">Para definir la propiedad Bookmark, seleccione un elemento de informe y en el panel Propiedades, escriba un valor o expresión para el identificador de marcador; por ejemplo, SalesChart o 5TopSales.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-157">To set the Bookmark property, select a report item, and in the Properties pane, type a value or expression for the bookmark ID; for example, SalesChart or 5TopSales.</span></span>  
  
 <span data-ttu-id="ae9d1-158">**Ir a dirección URL**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-158">**Go to URL**</span></span>  
 <span data-ttu-id="ae9d1-159">Elija esta opción para definir un vínculo a una página web.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-159">Choose this option to define a link to a Web page.</span></span> <span data-ttu-id="ae9d1-160">Escriba o seleccione la dirección URL de una página web o una expresión que se evalúe como la dirección URL de una página web.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-160">Type or select the URL of a Web page or an expression that evaluates to the URL of a Web page.</span></span> <span data-ttu-id="ae9d1-161">Haga clic en el botón **Expresión** (*fx*) para modificar la expresión.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-161">Click the **Expression** (*fx*) button to change the expression.</span></span> <span data-ttu-id="ae9d1-162">Esta expresión puede incluir un campo que contenga una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-162">This expression can include a field that contains a URL.</span></span> <span data-ttu-id="ae9d1-163">Al seleccionar **Ir a dirección URL**, aparece la siguiente opción adicional.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-163">The following additional option appears when you select **Go to URL**.</span></span>  
  
 <span data-ttu-id="ae9d1-164">**Seleccionar dirección URL**</span><span class="sxs-lookup"><span data-stu-id="ae9d1-164">**Select URL**</span></span>  
 <span data-ttu-id="ae9d1-165">Escriba o especifique la dirección URL del elemento.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-165">Type or enter the URL of the item.</span></span> <span data-ttu-id="ae9d1-166">En el caso de un elemento publicado en un servidor de informes configurado para el modo nativo, use una ruta de acceso completa o relativa.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-166">For an item published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="ae9d1-167">Por ejemplo, http:// *\<servername>* /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="ae9d1-167">For example, http://*\<servername>*/images/image1.jpg.</span></span> <span data-ttu-id="ae9d1-168">En el caso de un elemento publicado en un servidor de informes configurado en el modo integrado de SharePoint, use una dirección URL completa (por ejemplo, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="ae9d1-168">For an item published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9d1-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae9d1-169">See Also</span></span>  
 <span data-ttu-id="ae9d1-170">[Gráficos &#40;Generador de informes y SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ae9d1-170">[Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ae9d1-171">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="ae9d1-171">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="ae9d1-172">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="ae9d1-172">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="ae9d1-173">[Agregar un subinforme y parámetros &#40;Generador de informes y SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ae9d1-173">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ae9d1-174">Ordenación interactiva, mapas de documento y vínculos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ae9d1-174">Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;</span></span>](report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)  
  
  
