---
title: Exportar un informe como otro tipo de archivo (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b577568b-ecbd-44c3-be88-31dab6fc38a2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 240d3266b7b8c9a445658a9fd21fb9ea18a4c113
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743998"
---
# <a name="export-a-report-as-another-file-type-report-builder-and-ssrs"></a><span data-ttu-id="e3aae-102">Exportar un informe como otro tipo de archivo (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="e3aae-102">Export a Report as Another File Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e3aae-103">Puede representar el informe en otro formato de archivo, como CSV, Imagen, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)]o [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]mientras obtiene una vista previa del mismo en el Generador de informes o el Diseñador de informes, o puede representar el informe mientras lo ve en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e3aae-103">You can render a report to another file format, such as CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)], or [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], while previewing your report in Report Builder or Report Designer, or you can render the report while viewing the report on the report server.</span></span> <span data-ttu-id="e3aae-104">Representar el informe en un formato concreto resulta útil si se desea guardar el informe de manera inmediata como otro tipo de archivo sin publicarlo en el servidor de informes o si se desea ver el aspecto que presentará su diseño cuando se entregue a los lectores en un formato determinado.</span><span class="sxs-lookup"><span data-stu-id="e3aae-104">Rendering the report in a specific format in is helpful when you want to immediately save the report as another file type without publishing the report to the report server or when you want to see how your report design will appear when delivered to your report readers in a specific format.</span></span> <span data-ttu-id="e3aae-105">Representar el informe en el servidor de informes resulta útil si se configuran suscripciones o se entregan informes a través del correo electrónico o si se desea guardar un informe que está disponible en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e3aae-105">Rendering the report on the report server is useful when you set up subscriptions or deliver your reports via e-mail, or if you want to save a report that is available on the report server.</span></span> <span data-ttu-id="e3aae-106">Para obtener más información, vea [Suscripciones y entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="e3aae-106">For more information, see [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-export-a-report-as-another-file-type-in-report-builder"></a><span data-ttu-id="e3aae-107">Exportar un informe como otro tipo de archivo en el Generador de informes</span><span class="sxs-lookup"><span data-stu-id="e3aae-107">To export a report as another file type in Report Builder</span></span>  
  
1.  <span data-ttu-id="e3aae-108">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-108">Preview the report.</span></span>  
  
2.  <span data-ttu-id="e3aae-109">En la cinta, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-109">On the ribbon, click **Export**.</span></span>  
  
3.  <span data-ttu-id="e3aae-110">Seleccione el formato que desea usar.</span><span class="sxs-lookup"><span data-stu-id="e3aae-110">Select the format that you want to use.</span></span>  
  
     <span data-ttu-id="e3aae-111">Se abre el cuadro de diálogo **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-111">The **Save As** dialog box opens.</span></span> <span data-ttu-id="e3aae-112">De forma predeterminada, aparece el nombre de archivo del informe que exportó.</span><span class="sxs-lookup"><span data-stu-id="e3aae-112">By default, the file name is that of the report that you exported.</span></span> <span data-ttu-id="e3aae-113">Si lo desea, puede cambiar el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="e3aae-113">Optionally, you can change the file name.</span></span>  
  
4.  <span data-ttu-id="e3aae-114">Navegue hasta la ubicación donde guardó el informe exportado y ábralo.</span><span class="sxs-lookup"><span data-stu-id="e3aae-114">Navigate to the location where you saved the exported report and open it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3aae-115">Si el programa no puede abrir el informe en el formato que ha elegido porque no tiene un programa asociado a este tipo de archivo, le solicitará que guarde el informe exportado o que busque un programa en línea para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="e3aae-115">If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-report-manager"></a><span data-ttu-id="e3aae-116">Para exportar un informe como otro tipo de archivo en el Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="e3aae-116">To export a report as another file type in Report Manager</span></span>  
  
1.  <span data-ttu-id="e3aae-117">En la página **Inicio** del Administrador de informes, navegue hasta el informe que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="e3aae-117">From the Report Manager **Home** page, navigate to the report that you want to export.</span></span>  
  
2.  <span data-ttu-id="e3aae-118">Haga clic en el informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-118">Click the report.</span></span>  
  
     <span data-ttu-id="e3aae-119">Se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-119">The report is generated.</span></span>  
  
3.  <span data-ttu-id="e3aae-120">En la barra de herramientas del Visor de informes, haga clic en la flecha de lista desplegable **Seleccionar un formato** .</span><span class="sxs-lookup"><span data-stu-id="e3aae-120">On the Report Viewer toolbar, click the **Select a format** drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="e3aae-121">Seleccione el formato que desea usar.</span><span class="sxs-lookup"><span data-stu-id="e3aae-121">Select the format that you want to use.</span></span>  
  
5.  <span data-ttu-id="e3aae-122">Haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-122">Click **Export**.</span></span>  
  
     <span data-ttu-id="e3aae-123">Aparece un mensaje preguntándole si desea abrir o guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="e3aae-123">A message appears asking you if you want to open or save the file.</span></span>  
  
6.  <span data-ttu-id="e3aae-124">Para ver el informe en el formato de exportación seleccionado, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-124">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="e3aae-125">\- o -</span><span class="sxs-lookup"><span data-stu-id="e3aae-125">\- or -</span></span>  
  
     <span data-ttu-id="e3aae-126">Para guardar de manera inmediata el informe en el formato de exportación seleccionado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-126">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="e3aae-127">El informe se muestra o se guarda mediante la aplicación asociada al formato elegido.</span><span class="sxs-lookup"><span data-stu-id="e3aae-127">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="e3aae-128">Si hace clic en **Guardar**, se le solicitará una ubicación para guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-128">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="e3aae-129">**Nota** : si el programa no puede abrir el informe en el formato que ha elegido porque no tiene un programa asociado a este tipo de archivo, se le pedirá que guarde el informe exportado o que busque un programa en línea para abrir el informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-129">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-a-sharepoint-library"></a><span data-ttu-id="e3aae-130">Para exportar un informe como otro tipo de archivo en una biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3aae-130">To export a report as another file type in a SharePoint library</span></span>  
  
1.  <span data-ttu-id="e3aae-131">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-131">Preview the report.</span></span>  
  
2.  <span data-ttu-id="e3aae-132">En la barra de herramientas, haga clic en **Acciones**, seleccione **Exportar**y, a continuación, seleccione el formato que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="e3aae-132">On the toolbar, click **Actions**, point to **Export**, and then select the format that you want to use.</span></span>  
  
     <span data-ttu-id="e3aae-133">Se abre el cuadro de diálogo **Descarga de archivos** .</span><span class="sxs-lookup"><span data-stu-id="e3aae-133">The **File Download** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e3aae-134">Para ver el informe en el formato de exportación seleccionado, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-134">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="e3aae-135">\- o -</span><span class="sxs-lookup"><span data-stu-id="e3aae-135">\- or -</span></span>  
  
     <span data-ttu-id="e3aae-136">Para guardar de manera inmediata el informe en el formato de exportación seleccionado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-136">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="e3aae-137">El informe se muestra o se guarda mediante la aplicación asociada al formato elegido.</span><span class="sxs-lookup"><span data-stu-id="e3aae-137">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="e3aae-138">Si hace clic en **Guardar**, se le solicitará una ubicación para guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-138">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="e3aae-139">Opcionalmente, cambie el nombre de archivo del informe exportado.</span><span class="sxs-lookup"><span data-stu-id="e3aae-139">Optionally, change the file name of the exported report.</span></span>  
  
     <span data-ttu-id="e3aae-140">**Nota** : si el programa no puede abrir el informe en el formato que ha elegido porque no tiene un programa asociado a este tipo de archivo, se le pedirá que guarde el informe exportado o que busque un programa en línea para abrir el informe.</span><span class="sxs-lookup"><span data-stu-id="e3aae-140">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3aae-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3aae-141">See Also</span></span>  
 <span data-ttu-id="e3aae-142">[Exportar informes &#40;Generador de informes y SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e3aae-142">[Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e3aae-143">[Paginación en Reporting Services &#40;Generador de informes y SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e3aae-143">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e3aae-144">Funcionalidad interactiva para diferentes extensiones de representación de informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e3aae-144">Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;</span></span>](report-builder/interactive-functionality-different-report-rendering-extensions.md)  
  
  
