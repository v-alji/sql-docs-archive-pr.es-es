---
title: Exportar a un archivo de imagen (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 020d8ea2-de07-4212-a2bb-2ed0df2c8db8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dc1c8539b39a99c252ebfcb0275b674f657de6c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672783"
---
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a><span data-ttu-id="fe972-102">Exportar a un archivo de imagen (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="fe972-102">Exporting to an Image File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fe972-103">La extensión de presentación en imágenes presenta un informe en un mapa de bits o metarchivo.</span><span class="sxs-lookup"><span data-stu-id="fe972-103">The Image rendering extension renders a report to a bitmap or metafile.</span></span> <span data-ttu-id="fe972-104">De manera predeterminada, una extensión de representación en imágenes genera un archivo TIFF del informe, que se puede ver en varias páginas.</span><span class="sxs-lookup"><span data-stu-id="fe972-104">By default, the Image rendering extension produces a TIFF file of the report, which can be viewed in multiple pages.</span></span> <span data-ttu-id="fe972-105">Cuando el cliente recibe la imagen, se puede mostrar en un visor de imágenes y se puede imprimir.</span><span class="sxs-lookup"><span data-stu-id="fe972-105">When the client receives the image, it can be displayed in an image viewer and printed.</span></span> <span data-ttu-id="fe972-106">En este tema se proporciona información específica del representador de imágenes y se describen las excepciones a las reglas de representación.</span><span class="sxs-lookup"><span data-stu-id="fe972-106">This topic provides Image renderer-specific information and describes exceptions to the rendering rules.</span></span>  
  
 <span data-ttu-id="fe972-107">La extensión de presentación en imágenes puede generar archivos en cualquiera de los formatos que admite [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG y TIFF.</span><span class="sxs-lookup"><span data-stu-id="fe972-107">The Image rendering extension can generate files in any of the formats supported by [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="fe972-108">En el caso del formato TIFF, el nombre de archivo del flujo principal es *ReportName*.tif.</span><span class="sxs-lookup"><span data-stu-id="fe972-108">For TIFF format, the file name of the primary stream is *ReportName*.tif.</span></span> <span data-ttu-id="fe972-109">Para los demás formatos, que se representan como una única página por archivo, el nombre del archivo es *ReportName_Page.ext* donde.</span><span class="sxs-lookup"><span data-stu-id="fe972-109">For all other formats, which render as a single page per file, the file name is *ReportName_Page.ext* where.</span></span> <span data-ttu-id="fe972-110">*ext* es la extensión de archivo correspondiente al formato elegido.</span><span class="sxs-lookup"><span data-stu-id="fe972-110">*ext* is the file extension for the chosen format.</span></span> <span data-ttu-id="fe972-111">Para generar un archivo en otro formato admitido por Imagen, especifique cualquiera de las cadenas anteriores en el parámetro **OutputFormatDeviceInfo** .</span><span class="sxs-lookup"><span data-stu-id="fe972-111">To produce a file in another Image-supported format, specify any of the above listed strings in the **OutputFormatDeviceInfo** setting.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="supported-image-formats"></a><a name="SupportedImageFormats"></a> <span data-ttu-id="fe972-112">Formatos de imagen admitidos</span><span class="sxs-lookup"><span data-stu-id="fe972-112">Supported Image Formats</span></span>  
 <span data-ttu-id="fe972-113">En la tabla siguiente se muestra la extensión de archivo y el elemento MimeType para cada formato de representador de imágenes.</span><span class="sxs-lookup"><span data-stu-id="fe972-113">The following table shows the file extension and MimeType for each Image renderer format.</span></span>  
  
|<span data-ttu-id="fe972-114">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fe972-114">**Type**</span></span>|<span data-ttu-id="fe972-115">**Extensión**</span><span class="sxs-lookup"><span data-stu-id="fe972-115">**Extension**</span></span>|<span data-ttu-id="fe972-116">**MIMEType**</span><span class="sxs-lookup"><span data-stu-id="fe972-116">**MIMEType**</span></span>|  
|--------------|-------------------|------------------|  
|<span data-ttu-id="fe972-117">BMP</span><span class="sxs-lookup"><span data-stu-id="fe972-117">BMP</span></span>|<span data-ttu-id="fe972-118">bmp</span><span class="sxs-lookup"><span data-stu-id="fe972-118">bmp</span></span>|<span data-ttu-id="fe972-119">image/bmp</span><span class="sxs-lookup"><span data-stu-id="fe972-119">image/bmp</span></span>|  
|<span data-ttu-id="fe972-120">GIF</span><span class="sxs-lookup"><span data-stu-id="fe972-120">GIF</span></span>|<span data-ttu-id="fe972-121">GIF</span><span class="sxs-lookup"><span data-stu-id="fe972-121">gif</span></span>|<span data-ttu-id="fe972-122">image/gif</span><span class="sxs-lookup"><span data-stu-id="fe972-122">image/gif</span></span>|  
|<span data-ttu-id="fe972-123">JPEG</span><span class="sxs-lookup"><span data-stu-id="fe972-123">JPEG</span></span>|<span data-ttu-id="fe972-124">jpeg</span><span class="sxs-lookup"><span data-stu-id="fe972-124">jpeg</span></span>|<span data-ttu-id="fe972-125">image/jpeg</span><span class="sxs-lookup"><span data-stu-id="fe972-125">image/jpeg</span></span>|  
|<span data-ttu-id="fe972-126">PNG</span><span class="sxs-lookup"><span data-stu-id="fe972-126">PNG</span></span>|<span data-ttu-id="fe972-127">png</span><span class="sxs-lookup"><span data-stu-id="fe972-127">png</span></span>|<span data-ttu-id="fe972-128">image/png</span><span class="sxs-lookup"><span data-stu-id="fe972-128">image/png</span></span>|  
|<span data-ttu-id="fe972-129">TIFF</span><span class="sxs-lookup"><span data-stu-id="fe972-129">TIFF</span></span>|<span data-ttu-id="fe972-130">tif</span><span class="sxs-lookup"><span data-stu-id="fe972-130">tif</span></span>|<span data-ttu-id="fe972-131">image/tiff</span><span class="sxs-lookup"><span data-stu-id="fe972-131">image/tiff</span></span>|  
|<span data-ttu-id="fe972-132">EMF</span><span class="sxs-lookup"><span data-stu-id="fe972-132">EMF</span></span>|<span data-ttu-id="fe972-133">EMF</span><span class="sxs-lookup"><span data-stu-id="fe972-133">emf</span></span>|<span data-ttu-id="fe972-134">image/emf</span><span class="sxs-lookup"><span data-stu-id="fe972-134">image/emf</span></span>|  
|<span data-ttu-id="fe972-135">EMFPlus</span><span class="sxs-lookup"><span data-stu-id="fe972-135">EMFPlus</span></span>|<span data-ttu-id="fe972-136">EMF</span><span class="sxs-lookup"><span data-stu-id="fe972-136">emf</span></span>|<span data-ttu-id="fe972-137">image/emf</span><span class="sxs-lookup"><span data-stu-id="fe972-137">image/emf</span></span>|  
  
  
##  <a name="rendering-multiple-pages"></a><a name="RenderingMultiplePages"></a> <span data-ttu-id="fe972-138">Representar varias páginas</span><span class="sxs-lookup"><span data-stu-id="fe972-138">Rendering Multiple Pages</span></span>  
 <span data-ttu-id="fe972-139">TIFF es el único formato que admite varios documentos de página en un único archivo.</span><span class="sxs-lookup"><span data-stu-id="fe972-139">TIFF is the only format that supports multiple page documents in a single file.</span></span> <span data-ttu-id="fe972-140">Otros formatos, como JPG o PNG, generan las páginas de una en una y requieren una llamada independiente a la extensión de representación para cada página.</span><span class="sxs-lookup"><span data-stu-id="fe972-140">Other formats, such as JPG or PNG, output one page at a time and require a separate call to the rendering extension for each page.</span></span>  
  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="fe972-141">Interactividad</span><span class="sxs-lookup"><span data-stu-id="fe972-141">Interactivity</span></span>  
 <span data-ttu-id="fe972-142">Ninguno de los formatos de imagen generados por este representador admite la interactividad.</span><span class="sxs-lookup"><span data-stu-id="fe972-142">Interactivity is not supported in any Image formats generated by this renderer.</span></span> <span data-ttu-id="fe972-143">No se representan los elementos interactivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe972-143">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="fe972-144">Hipervínculos</span><span class="sxs-lookup"><span data-stu-id="fe972-144">Hyperlinks</span></span>  
  
-   <span data-ttu-id="fe972-145">Mostrar u ocultar</span><span class="sxs-lookup"><span data-stu-id="fe972-145">Show or Hide</span></span>  
  
-   <span data-ttu-id="fe972-146">Mapa del documento</span><span class="sxs-lookup"><span data-stu-id="fe972-146">Document Map</span></span>  
  
-   <span data-ttu-id="fe972-147">Vínculos de obtención de detalles o vínculos click-through</span><span class="sxs-lookup"><span data-stu-id="fe972-147">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="fe972-148">Ordenación de usuarios finales</span><span class="sxs-lookup"><span data-stu-id="fe972-148">End user sort</span></span>  
  
-   <span data-ttu-id="fe972-149">Encabezados fijos</span><span class="sxs-lookup"><span data-stu-id="fe972-149">Fixed headers</span></span>  
  
-   <span data-ttu-id="fe972-150">Marcadores</span><span class="sxs-lookup"><span data-stu-id="fe972-150">Bookmarks</span></span>  
  
  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="fe972-151">Configuración de la información del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fe972-151">Device Information Settings</span></span>  
 <span data-ttu-id="fe972-152">Puede cambiar parte de la configuración predeterminada de este representador cambiando los valores de configuración de la información del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe972-152">You can change some default settings for this renderer by changing the device information settings.</span></span> <span data-ttu-id="fe972-153">Para obtener más información, vea [Image Device Information Settings](../image-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fe972-153">For more information, see [Image Device Information Settings](../image-device-information-settings.md).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="fe972-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe972-154">See Also</span></span>  
 <span data-ttu-id="fe972-155">[Paginación en Reporting Services &#40;Generador de informes y SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fe972-155">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fe972-156">[Comportamientos de representación &#40;Generador de informes y SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fe972-156">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fe972-157">[Funcionalidad interactiva para diferentes extensiones de representación de informes &#40;Generador de informes y SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="fe972-157">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="fe972-158">[Representar elementos de informe &#40;Generador de informes y SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fe972-158">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fe972-159">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fe972-159">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
