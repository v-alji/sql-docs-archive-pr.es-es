---
title: Exportar un informe mediante el acceso URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- formats [Reporting Services], URL rendering
- URL access [Reporting Services], rendering formats
ms.assetid: 6a3b7fc3-3d91-4d12-8371-42ea12e74517
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 69f340855e37ffde49aec0af096c094a142659d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743995"
---
# <a name="export-a-report-using-url-access"></a><span data-ttu-id="80b2a-102">Exportar un informe mediante el acceso URL</span><span class="sxs-lookup"><span data-stu-id="80b2a-102">Export a Report Using URL Access</span></span>
  <span data-ttu-id="80b2a-103">Opcionalmente, puede especificar el formato en el que se representará un informe mediante el parámetro *RS: Format* .</span><span class="sxs-lookup"><span data-stu-id="80b2a-103">You can optionally specify the format in which to render a report by using the *rs:Format* parameter.</span></span> <span data-ttu-id="80b2a-104">Por ejemplo, para obtener una copia PDF de un informe directamente desde un servidor de informes en modo nativo:</span><span class="sxs-lookup"><span data-stu-id="80b2a-104">For example, to get a PDF copy of a report directly from a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/myreport&rs:Format=PDF  
```  
  
 <span data-ttu-id="80b2a-105">Y desde un servidor de informes en el modo integrado de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="80b2a-105">And, from a SharePoint integrated mode report server:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/myrereport.rdl&rs:Format=PDF  
```  
  
 <span data-ttu-id="80b2a-106">Los valores válidos para este parámetro están basados en las extensiones de representación del informe instaladas en el servidor de informes al que se está obteniendo acceso.</span><span class="sxs-lookup"><span data-stu-id="80b2a-106">Valid values for this parameter are based on the report rendering extensions that are installed on the report server being accessed.</span></span> <span data-ttu-id="80b2a-107">Las extensiones comunes son HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML y NULL.</span><span class="sxs-lookup"><span data-stu-id="80b2a-107">Common extensions are HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML, and NULL.</span></span> <span data-ttu-id="80b2a-108">Si una extensión de representación especificada no se instala en el servidor de informes, no se representa el informe y se genera un error que se muestra en el explorador.</span><span class="sxs-lookup"><span data-stu-id="80b2a-108">If a specified rendering extension is not installed on the report server, the report is not rendered and an error is generated and displayed in the browser.</span></span>  
  
 <span data-ttu-id="80b2a-109">Si no incluye el parámetro *Format* como parte de la dirección URL, el servidor de informes detecta el explorador y representa el informe en el formato HTML adecuado.</span><span class="sxs-lookup"><span data-stu-id="80b2a-109">If you do not include the *Format* parameter as part of the URL, the report server detects the browser and renders the report in the appropriate HTML format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b2a-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80b2a-110">See Also</span></span>  
 <span data-ttu-id="80b2a-111">[Acceso URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80b2a-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="80b2a-112">Referencia de parámetros de acceso URL</span><span class="sxs-lookup"><span data-stu-id="80b2a-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
