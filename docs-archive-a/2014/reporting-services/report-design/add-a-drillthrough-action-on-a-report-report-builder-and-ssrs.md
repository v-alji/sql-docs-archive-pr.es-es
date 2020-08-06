---
title: Agregar una acción de obtención de detalles en un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 153729c4-d01e-4629-b78f-0cfd5a7f83da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a429380f677a309e4e1437a2e3c5036bb4e8a455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670800"
---
# <a name="add-a-drillthrough-action-on-a-report-report-builder-and-ssrs"></a><span data-ttu-id="2e3df-102">Agregar una acción de obtención de detalles en un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="2e3df-102">Add a Drillthrough Action on a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2e3df-103">El informe que se abre al hacer clic en el vínculo del informe principal se denomina *informe detallado*.</span><span class="sxs-lookup"><span data-stu-id="2e3df-103">The report that opens when you click the link in the main report is known as a *drillthrough report*.</span></span> <span data-ttu-id="2e3df-104">Este vínculo de obtención de detalles habilita una acción de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="2e3df-104">This drillthrough link enables a drillthrough action.</span></span>  
  
 <span data-ttu-id="2e3df-105">Los informes detallados deben publicarse en el mismo servidor de informes que el informe principal, pero pueden estar en carpetas diferentes.</span><span class="sxs-lookup"><span data-stu-id="2e3df-105">Drillthrough reports must be published to the same report server as the main report, but they can be in different folders.</span></span> <span data-ttu-id="2e3df-106">Puede agregar un vínculo de obtención de detalles a cualquier elemento que tenga una propiedad **Action** , como un cuadro de texto, una imagen o los puntos de datos de un gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e3df-106">You can add a drillthrough link to any item that has an **Action** property, such as a text box, an image, or data points on a chart.</span></span>  
  
 <span data-ttu-id="2e3df-107">Para agregar un vínculo de obtención de detalles a un informe, debe crear primero el informe detallado al que se vinculará el informe principal.</span><span class="sxs-lookup"><span data-stu-id="2e3df-107">To add a drillthrough link to a report, you must first create the drillthrough report that the main report will link to.</span></span> <span data-ttu-id="2e3df-108">Un informe detallado contiene normalmente los detalles sobre un elemento que está incluido en el informe de resumen original y a menudo contiene los parámetros que filtran el informe detallado en función de los parámetros que han pasado a él desde el informe principal.</span><span class="sxs-lookup"><span data-stu-id="2e3df-108">A drillthrough report commonly contains details about an item that is contained in the original summary report, and often contains parameters that filter the drillthrough report based on parameters passed to it from the main report.</span></span> <span data-ttu-id="2e3df-109">Para más información sobre cómo crear el informe detallado, vea [Informes detallados &#40;Generador de informes y SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2e3df-109">For more information on creating the drillthrough report, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-drillthrough-action"></a><span data-ttu-id="2e3df-110">Para agregar una acción de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="2e3df-110">To add a drillthrough action</span></span>  
  
1.  <span data-ttu-id="2e3df-111">En la vista Diseño, haga clic con el botón derecho en el gráfico, la imagen o el cuadro de texto al que quiere agregar el vínculo y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2e3df-111">In Design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="2e3df-112">En el cuadro de diálogo **Propiedades** del elemento, haga clic en **Acción**.</span><span class="sxs-lookup"><span data-stu-id="2e3df-112">In the item's **Properties** dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="2e3df-113">Seleccione **Ir a informe**.</span><span class="sxs-lookup"><span data-stu-id="2e3df-113">Select **Go to report**.</span></span> <span data-ttu-id="2e3df-114">Aparecen secciones adicionales en el cuadro de diálogo para esta opción.</span><span class="sxs-lookup"><span data-stu-id="2e3df-114">Additional sections appear in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="2e3df-115">En **Especificar un informe**, haga clic en **Examinar** para localizar el informe al que desea ir o escriba el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="2e3df-115">In **Specify a report**, click **Browse** to locate the report that you want to jump to, or type the name of the report.</span></span> <span data-ttu-id="2e3df-116">O bien, puede hacer clic en el botón de la expresión (**fx**) para crear una expresión para el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="2e3df-116">Alternatively, click the expression (**fx**) button to create an expression for the report name.</span></span>  
  
     <span data-ttu-id="2e3df-117">El formato de la ruta de acceso al informe detallado difiere para el modo nativo y para el modo integrado en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2e3df-117">The format of the path to the drillthrough report differs for native and SharePoint integrated mode.</span></span> <span data-ttu-id="2e3df-118">Si busca el informe, se proporcionará una ruta de acceso con el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="2e3df-118">If you browse to the report, a path of the correct format is provided.</span></span> <span data-ttu-id="2e3df-119">Para más información, vea [Especificar las rutas de acceso a los elementos externos &#40;Generador de informes y SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2e3df-119">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="2e3df-120">Si tiene que especificar parámetros para el informe detallado, siga el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e3df-120">If you have to specify parameters for the drillthrough report, follow the next step.</span></span>  
  
5.  <span data-ttu-id="2e3df-121">En **Utilizar estos parámetros para ejecutar el informe**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2e3df-121">In **Use these parameters to run the report**, click **Add**.</span></span> <span data-ttu-id="2e3df-122">Se agrega una nueva fila a la cuadrícula de parámetros.</span><span class="sxs-lookup"><span data-stu-id="2e3df-122">A new row is added to the parameter grid.</span></span>  
  
    -   <span data-ttu-id="2e3df-123">En el cuadro de texto **Nombre** , haga clic en la lista desplegable o escriba el nombre del parámetro de informe del informe detallado.</span><span class="sxs-lookup"><span data-stu-id="2e3df-123">In the **Name** text box, click the drop-down list or type the name of the report parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2e3df-124">Los nombres de la lista de parámetros deben coincidir exactamente con los parámetros previstos en el informe de destino.</span><span class="sxs-lookup"><span data-stu-id="2e3df-124">The names in the parameter list must match the expected parameters in the target report exactly.</span></span> <span data-ttu-id="2e3df-125">Por ejemplo, los nombres de parámetro deben coincidir en mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2e3df-125">For example, parameter names must match by case.</span></span> <span data-ttu-id="2e3df-126">Si los nombres no coinciden o si en la lista falta algún parámetro previsto, se produce un error en el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="2e3df-126">If the names do not match, or if an expected parameter is not listed, the drillthrough report fails.</span></span>  
  
    -   <span data-ttu-id="2e3df-127">En **Valor**, escriba o seleccione el valor que se va a pasar al parámetro del informe detallado.</span><span class="sxs-lookup"><span data-stu-id="2e3df-127">In **Value**, type or select the value to pass to the parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2e3df-128">Los valores pueden contener una expresión que se evalúe como un valor que se pasará al parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="2e3df-128">Values can contain an expression that evaluates to a value to pass to the report parameter.</span></span> <span data-ttu-id="2e3df-129">En la lista de valores, las expresiones incluyen la lista de campos del informe actual.</span><span class="sxs-lookup"><span data-stu-id="2e3df-129">The expressions in the value list include the field list for the current report.</span></span>  
  
     <span data-ttu-id="2e3df-130">Para información sobre cómo ocultar parámetros en informes, vea [Agregar, cambiar o eliminar parámetros de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2e3df-130">For information on how to hide parameters in reports, see [Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="2e3df-131">(Opcional) En los cuadros de texto, resulta útil cambiar el color y el efecto del texto en la pestaña **Inicio** de la cinta de opciones para indicar al usuario que el texto es un vínculo.</span><span class="sxs-lookup"><span data-stu-id="2e3df-131">(Optional) For text boxes, it is helpful to indicate to the user that the text is a link by changing the color and effect of the text on the **Home** tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="2e3df-132">Para probar el vínculo, ejecute el informe y haga clic en el elemento de informe en el que ha establecido este vínculo.</span><span class="sxs-lookup"><span data-stu-id="2e3df-132">To test the link, run the report and click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e3df-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e3df-133">See Also</span></span>  
 <span data-ttu-id="2e3df-134">[Cuadro de diálogo Propiedades de acción &#40;Generador de informes y SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e3df-134">[Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e3df-135">[Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e3df-135">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2e3df-136">Mostrar la información sobre herramientas en una serie &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2e3df-136">Show ToolTips on a Series &#40;Report Builder and SSRS&#41;</span></span>](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
  
