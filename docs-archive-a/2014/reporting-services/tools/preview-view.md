---
title: Vista previa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.previewview.f1
helpviewer_keywords:
- Preview view [Reporting Services]
ms.assetid: 108255d1-5be8-47c1-80f3-1f2a055e4d02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1ff7c59c3ac5143d4f4103edea1a5ee309046547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746128"
---
# <a name="preview-view"></a><span data-ttu-id="fce6d-102">Vista previa, vista</span><span class="sxs-lookup"><span data-stu-id="fce6d-102">Preview View</span></span>
  <span data-ttu-id="fce6d-103">Use la **Vista previa** para mostrar el informe representado.</span><span class="sxs-lookup"><span data-stu-id="fce6d-103">Use **Preview** view to display the rendered report.</span></span> <span data-ttu-id="fce6d-104">Antes de abrir un informe en Vista previa, el Diseñador de informes lo ejecuta localmente.</span><span class="sxs-lookup"><span data-stu-id="fce6d-104">When a report is previewed, Report Designer runs the report locally and displays it in the Preview view.</span></span> <span data-ttu-id="fce6d-105">En el modo de vista previa, el informe se procesa por completo.</span><span class="sxs-lookup"><span data-stu-id="fce6d-105">In preview mode, the report is processed in full.</span></span> <span data-ttu-id="fce6d-106">Si el informe tiene una consulta compleja o una gran cantidad de datos, es posible que se necesiten algunos minutos para que se complete la vista previa la primera vez que la muestre.</span><span class="sxs-lookup"><span data-stu-id="fce6d-106">If the report has a complex query or has a large amount of data, preview might take several minutes to complete the first time you view it.</span></span> <span data-ttu-id="fce6d-107">Para los cambios posteriores que solo afectan al formato del informe, la vista previa utiliza datos en caché.</span><span class="sxs-lookup"><span data-stu-id="fce6d-107">For subsequent changes that affect only the format of the report, preview uses cached data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fce6d-108">Cuando [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] se ejecuta como RemoteApp, no se pueden mostrar los informes en la **Vista previa** en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fce6d-108">When [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] is run as a RemoteApp, reports cannot be displayed in **Preview** view in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="fce6d-109">Los programas RemoteApp son programas a los que se tiene acceso remoto mediante Servicios de Escritorio remoto.</span><span class="sxs-lookup"><span data-stu-id="fce6d-109">RemoteApp programs are programs that are accessed remotely through Remote Desktop Services.</span></span> <span data-ttu-id="fce6d-110">Para obtener más información, vea [Guía paso a paso sobre RemoteApp de TS](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="fce6d-110">For more information, see [TS RemoteApp Step-by-Step Guide](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fce6d-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="fce6d-111">Options</span></span>  
 <span data-ttu-id="fce6d-112">Use la barra de herramientas para administrar las funciones de vista previa.</span><span class="sxs-lookup"><span data-stu-id="fce6d-112">Use the toolbar to manage preview functions.</span></span>  
  
 <span data-ttu-id="fce6d-113">**Mostrar u ocultar mapa del documento**</span><span class="sxs-lookup"><span data-stu-id="fce6d-113">**Show or Hide Document Map**</span></span>  
 <span data-ttu-id="fce6d-114">Elija esta opción para mostrar u ocultar el mapa del documento si existe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-114">Choose this option to show or hide the document map if one exists.</span></span>  
  
 <span data-ttu-id="fce6d-115">**Mostrar u ocultar área de parámetros**</span><span class="sxs-lookup"><span data-stu-id="fce6d-115">**Show or Hide Parameter Area**</span></span>  
 <span data-ttu-id="fce6d-116">Elija esta opción para mostrar u ocultar los cuadros de parámetros en informes con parámetros.</span><span class="sxs-lookup"><span data-stu-id="fce6d-116">Choose this option to show or hide the parameters boxes for reports with parameters.</span></span>  
  
 <span data-ttu-id="fce6d-117">**Primera página**</span><span class="sxs-lookup"><span data-stu-id="fce6d-117">**First Page**</span></span>  
 <span data-ttu-id="fce6d-118">Elija esta opción para ir a la primera página del informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-118">Choose this option to go to the first page of the report.</span></span>  
  
 <span data-ttu-id="fce6d-119">**Página anterior**</span><span class="sxs-lookup"><span data-stu-id="fce6d-119">**Previous Page**</span></span>  
 <span data-ttu-id="fce6d-120">Elija esta opción para ir a la página anterior del informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-120">Choose this option to go to the previous page of the report.</span></span>  
  
 <span data-ttu-id="fce6d-121">**Página actual**</span><span class="sxs-lookup"><span data-stu-id="fce6d-121">**Current Page**</span></span>  
 <span data-ttu-id="fce6d-122">Muestra la página actual del informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-122">Displays the current page of the report.</span></span>  
  
 <span data-ttu-id="fce6d-123">**Páginas totales**</span><span class="sxs-lookup"><span data-stu-id="fce6d-123">**Total Pages**</span></span>  
 <span data-ttu-id="fce6d-124">Muestra el número total de páginas del informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-124">Displays the total number of pages in the report.</span></span>  
  
 <span data-ttu-id="fce6d-125">**Página siguiente**</span><span class="sxs-lookup"><span data-stu-id="fce6d-125">**Next Page**</span></span>  
 <span data-ttu-id="fce6d-126">Elija esta opción para ir a la siguiente página del informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-126">Choose this option to go to the next page of the report.</span></span>  
  
 <span data-ttu-id="fce6d-127">**Última página**</span><span class="sxs-lookup"><span data-stu-id="fce6d-127">**Last Page**</span></span>  
 <span data-ttu-id="fce6d-128">Elija esta opción para ir a la última página del informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-128">Choose this option to go to the last page of the report.</span></span>  
  
 <span data-ttu-id="fce6d-129">**Volver al informe primario**</span><span class="sxs-lookup"><span data-stu-id="fce6d-129">**Back to Parent Report**</span></span>  
 <span data-ttu-id="fce6d-130">Elija esta opción para ir al informe primario.</span><span class="sxs-lookup"><span data-stu-id="fce6d-130">Choose this option to go to the parent report.</span></span> <span data-ttu-id="fce6d-131">Esta opción se utiliza para navegar entre informes detallados.</span><span class="sxs-lookup"><span data-stu-id="fce6d-131">This option is used to navigate drillthrough reports.</span></span>  
  
 <span data-ttu-id="fce6d-132">**Detener representación**</span><span class="sxs-lookup"><span data-stu-id="fce6d-132">**Stop Rendering**</span></span>  
 <span data-ttu-id="fce6d-133">Elija esta opción para detener el proceso de representación.</span><span class="sxs-lookup"><span data-stu-id="fce6d-133">Choose this option to stop the rendering process.</span></span>  
  
 <span data-ttu-id="fce6d-134">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="fce6d-134">**Refresh**</span></span>  
 <span data-ttu-id="fce6d-135">Elija esta opción para actualizar la caché de datos y ejecutar el informe de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fce6d-135">Choose this option to refresh the data cache and run the report again.</span></span>  
  
 <span data-ttu-id="fce6d-136">**Imprimir**</span><span class="sxs-lookup"><span data-stu-id="fce6d-136">**Print**</span></span>  
 <span data-ttu-id="fce6d-137">Elija esta opción para imprimir el informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-137">Choose this option to print the report.</span></span>  
  
 <span data-ttu-id="fce6d-138">**Diseño de impresión**</span><span class="sxs-lookup"><span data-stu-id="fce6d-138">**Print Layout**</span></span>  
 <span data-ttu-id="fce6d-139">Elija esta opción para alternar entre la vista previa del informe y la vista del informe tal como aparecerá en la página impresa.</span><span class="sxs-lookup"><span data-stu-id="fce6d-139">Choose this option to toggle between the preview report and the view of the report as it will appear on the printed page.</span></span>  
  
 <span data-ttu-id="fce6d-140">**Configurar página**</span><span class="sxs-lookup"><span data-stu-id="fce6d-140">**Page Setup**</span></span>  
 <span data-ttu-id="fce6d-141">Elija esta opción para cambiar las propiedades de impresión y página según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fce6d-141">Choose this option to conveniently change page and print properties.</span></span> <span data-ttu-id="fce6d-142">Utilice Diseño de impresión para ver los cambios antes de imprimir.</span><span class="sxs-lookup"><span data-stu-id="fce6d-142">Use Print Layout to view changes before printing.</span></span>  
  
 <span data-ttu-id="fce6d-143">**Exportarar**</span><span class="sxs-lookup"><span data-stu-id="fce6d-143">**Export**</span></span>  
 <span data-ttu-id="fce6d-144">Elija esta opción para exportar el informe representado en un formato concreto.</span><span class="sxs-lookup"><span data-stu-id="fce6d-144">Choose this option to export the rendered report in a specific format.</span></span>  
  
 <span data-ttu-id="fce6d-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="fce6d-145">**Zoom**</span></span>  
 <span data-ttu-id="fce6d-146">Seleccione un factor de zoom para acercar o alejar el informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-146">Select a zoom factor to zoom in or out on the report.</span></span>  
  
 <span data-ttu-id="fce6d-147">**Buscar texto**</span><span class="sxs-lookup"><span data-stu-id="fce6d-147">**Search Text**</span></span>  
 <span data-ttu-id="fce6d-148">Escriba el texto que desea buscar en el informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-148">Type text to search for a match within the report.</span></span> <span data-ttu-id="fce6d-149">No puede utilizar operadores de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fce6d-149">You cannot use search operators.</span></span> <span data-ttu-id="fce6d-150">Haga clic en **Buscar** para buscar la primera instancia.</span><span class="sxs-lookup"><span data-stu-id="fce6d-150">Click **Find** to search for the first instance.</span></span>  
  
 <span data-ttu-id="fce6d-151">**Localización**</span><span class="sxs-lookup"><span data-stu-id="fce6d-151">**Find**</span></span>  
 <span data-ttu-id="fce6d-152">Elija esta opción para empezar a buscar el texto de búsqueda en el informe.</span><span class="sxs-lookup"><span data-stu-id="fce6d-152">Choose this option to begin searching the report for the search text.</span></span>  
  
 <span data-ttu-id="fce6d-153">**Buscar siguiente**</span><span class="sxs-lookup"><span data-stu-id="fce6d-153">**Find Next**</span></span>  
 <span data-ttu-id="fce6d-154">Elija esta opción para buscar la siguiente aparición del texto de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fce6d-154">Choose this option to search for the next instance of the search text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce6d-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fce6d-155">See Also</span></span>  
 <span data-ttu-id="fce6d-156">[Obtener una vista previa de informes](../reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="fce6d-156">[Previewing Reports](../reports/previewing-reports.md) </span></span>  
 [<span data-ttu-id="fce6d-157">Diseñador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="fce6d-157">Report Designer F1 Help</span></span>](report-designer-f1-help.md)  
  
  
