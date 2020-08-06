---
title: Formato del archivo de salida XML (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose]
- ssbdiagnose
ms.assetid: 3ceb991b-6f15-4504-8828-de5adf448bc5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 612b317f7220f502faf1adc82cf9c1dcc8bc20a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747808"
---
# <a name="xml-output-file-format-ssbdiagnose"></a><span data-ttu-id="9a87e-102">Formato del archivo de salida XML (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="9a87e-102">XML Output File Format (ssbdiagnose)</span></span>
  <span data-ttu-id="9a87e-103">La utilidad **ssbdiagnose** genera la salida en forma de archivo XML si se ejecuta con el modificador **-XML** .</span><span class="sxs-lookup"><span data-stu-id="9a87e-103">The **ssbdiagnose** utility delivers its output as an XML file when you run it with the **-XML** switch.</span></span> <span data-ttu-id="9a87e-104">El archivo de salida XML incluye la información de encabezado y los errores encontrados en la configuración de [!INCLUDE[ssSB](../../includes/sssb-md.md)] o la conversación que se analizó.</span><span class="sxs-lookup"><span data-stu-id="9a87e-104">The XML output file lists header information and the errors that it found in the [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration or conversation that was analyzed.</span></span> <span data-ttu-id="9a87e-105">Si lo desea, puede escribir una aplicación para analizar o notificar los errores incluidos en el archivo.</span><span class="sxs-lookup"><span data-stu-id="9a87e-105">You can write an application to analyze or report on the errors listed in the file.</span></span> <span data-ttu-id="9a87e-106">O bien, puede ver el archivo XML en un editor XML estándar, como XML Notepad.</span><span class="sxs-lookup"><span data-stu-id="9a87e-106">Or, you can view the XML file in a general XML editor, such as XML Notepad.</span></span>  
  
 <span data-ttu-id="9a87e-107">Un archivo de resultados de **ssbdiangose** contiene un elemento raíz DiagnosticInformation con dos tipos secundarios:</span><span class="sxs-lookup"><span data-stu-id="9a87e-107">An **ssbdiangose** output file contains a DiagnosticInformation root element with two child types:</span></span>  
  
-   <span data-ttu-id="9a87e-108">Un elemento Banner con información de encabezado.</span><span class="sxs-lookup"><span data-stu-id="9a87e-108">A Banner element with header information.</span></span>  
  
-   <span data-ttu-id="9a87e-109">Un elemento Issue para cada problema notificado por **ssbdiangose**.</span><span class="sxs-lookup"><span data-stu-id="9a87e-109">An Issue element for each issue that is reported by **ssbdiagnose**.</span></span>  
  
## <a name="diagnosticinformation-root-element"></a><span data-ttu-id="9a87e-110">Elemento raíz DiagnosticInformation</span><span class="sxs-lookup"><span data-stu-id="9a87e-110">DiagnosticInformation Root Element</span></span>  
  
-   [<span data-ttu-id="9a87e-111">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9a87e-111">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a><span data-ttu-id="9a87e-112">Elemento Banner</span><span class="sxs-lookup"><span data-stu-id="9a87e-112">Banner Element</span></span>  
  
-   [<span data-ttu-id="9a87e-113">Elemento Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9a87e-113">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a><span data-ttu-id="9a87e-114">Elemento Issue</span><span class="sxs-lookup"><span data-stu-id="9a87e-114">Issue Element</span></span>  
  
-   [<span data-ttu-id="9a87e-115">Elemento Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9a87e-115">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a87e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a87e-116">See Also</span></span>  
 [<span data-ttu-id="9a87e-117">Utilidad ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="9a87e-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
