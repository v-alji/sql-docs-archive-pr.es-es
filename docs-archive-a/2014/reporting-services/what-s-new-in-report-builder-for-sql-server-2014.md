---
title: Novedades de&#39;s en Generador de informes para SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8223c19b-4b0d-4b1d-a042-9a726c18e708
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ce72af225130bc3f081a53008a303c5213db636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674003"
---
# <a name="what39s-new-in-report-builder-for-sql-server-2014"></a><span data-ttu-id="65ae2-102">&#39;novedades de Generador de informes para SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="65ae2-102">What&#39;s New in Report Builder for SQL Server 2014</span></span>
  <span data-ttu-id="65ae2-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] presenta diversas características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65ae2-103">The [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] introduces a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span>  
  
 <span data-ttu-id="65ae2-104">Para obtener información acerca de las características de esta versión para otros [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] productos y tecnologías, consulte [novedades de SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="65ae2-104">For information about features in this release for other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="65ae2-105">Para obtener la información y los recursos más recientes con respecto a las nuevas características de esta versión, vea [Información adicional sobre las novedades de SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span><span class="sxs-lookup"><span data-stu-id="65ae2-105">For the most recent information and resources regarding new features in this release, see [Additional information on what is new in SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span></span>  
  
##  <a name="excel-renderer-for-microsoft-excel-2007-2010-and-microsoft-excel-2003"></a><a name="ExcelRenderer"></a><span data-ttu-id="65ae2-106">Representador de Excel para Microsoft Excel 2007-2010 y Microsoft Excel 2003</span><span class="sxs-lookup"><span data-stu-id="65ae2-106">Excel Renderer for Microsoft Excel 2007-2010 and Microsoft Excel 2003</span></span>  
 <span data-ttu-id="65ae2-107">La extensión de representación de Excel de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , nueva en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], procesa un informe como un documento de Excel compatible con [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010, así como con [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003, gracias al Paquete de compatibilidad de Microsoft Office para formatos de archivos de Word, Excel y PowerPoint instalado.</span><span class="sxs-lookup"><span data-stu-id="65ae2-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Excel rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as an Excel document that is compatible with [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 as well as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="65ae2-108">El formato es Office Open XML y la extensión de los archivos es .xlsx.</span><span class="sxs-lookup"><span data-stu-id="65ae2-108">The format is Office Open XML and the file extension of files is .xlsx.</span></span>  
  
 <span data-ttu-id="65ae2-109">Esta extensión de representación de Excel elimina las limitaciones de la versión anterior, compatible con Excel 2003.</span><span class="sxs-lookup"><span data-stu-id="65ae2-109">This Excel-rendering extension removes limitations of the earlier version, compatible with Excel 2003.</span></span> <span data-ttu-id="65ae2-110">A continuación se indican las mejoras de la extensión de representación:</span><span class="sxs-lookup"><span data-stu-id="65ae2-110">The following lists the improvement in the rendering extension:</span></span>  
  
-   <span data-ttu-id="65ae2-111">Número máximo de filas por hoja de cálculo: 1.048.576.</span><span class="sxs-lookup"><span data-stu-id="65ae2-111">Maximum rows per worksheet is 1,048,576.</span></span>  
  
-   <span data-ttu-id="65ae2-112">Número máximo de columnas por hoja de cálculo: 16.384.</span><span class="sxs-lookup"><span data-stu-id="65ae2-112">Maximum columns per worksheet is 16,384.</span></span>  
  
-   <span data-ttu-id="65ae2-113">Número de colores permitido en una hoja de cálculo: aproximadamente 16 millones (color de 24 bits).</span><span class="sxs-lookup"><span data-stu-id="65ae2-113">Number of colors allowed in a worksheet is approximately 16 million (24-bit color).</span></span>  
  
-   <span data-ttu-id="65ae2-114">La compresión ZIP proporciona archivos menores.</span><span class="sxs-lookup"><span data-stu-id="65ae2-114">ZIP compression provides smaller files sizes.</span></span>  
  
 <span data-ttu-id="65ae2-115">Para obtener más información, vea [Exportar a Microsoft Excel &#40;Generador de informes y SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="65ae2-115">For more information, see [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="word-renderer-for-microsoft-word-2007-2010-and-microsoft-word-2003"></a><a name="WordRenderer"></a><span data-ttu-id="65ae2-116">Representador de Word para Microsoft Word 2007-2010 y Microsoft Word 2003</span><span class="sxs-lookup"><span data-stu-id="65ae2-116">Word Renderer for Microsoft Word 2007-2010 and Microsoft Word 2003</span></span>  
 <span data-ttu-id="65ae2-117">La extensión de representación de Word de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , nueva en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], procesa un informe como un documento de Word compatible con [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010, así como con [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003, gracias al Paquete de compatibilidad de [!INCLUDE[msCoName](../includes/msconame-md.md)] Office para formatos de archivos de Word, Excel y PowerPoint instalado.</span><span class="sxs-lookup"><span data-stu-id="65ae2-117">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Word rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as a Word document that is compatible with [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 as well as [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="65ae2-118">El formato es Office Open XML y la extensión de los archivos es .docx.</span><span class="sxs-lookup"><span data-stu-id="65ae2-118">The format is Office Open XML and the file extension of files is docx.</span></span>  
  
 <span data-ttu-id="65ae2-119">Además de hacer que las características nuevas de Word 2007-2010 estén disponibles en los informes exportados, los archivos \*.docx de los informes exportados suelen ser menores.</span><span class="sxs-lookup"><span data-stu-id="65ae2-119">In addition to making the features that are new in Word 2007-2010 available to exported reports, \*.docx files of exported reports tend to be smaller.</span></span> <span data-ttu-id="65ae2-120">Los informes exportados mediante el representador de Word suelen ser mucho menores que los mismos informes exportados mediante el representador de Word 2003.</span><span class="sxs-lookup"><span data-stu-id="65ae2-120">Reports exported by using the Word renderer are typically significantly smaller than the same reports exported by using the Word 2003 renderer.</span></span>  
  
 <span data-ttu-id="65ae2-121">Para obtener más información, vea [Exportar a Microsoft Word &#40;Generador de informes y SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="65ae2-121">For more information, see [Exporting to Microsoft Word &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ae2-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65ae2-122">See Also</span></span>  
 [<span data-ttu-id="65ae2-123">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="65ae2-123">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
