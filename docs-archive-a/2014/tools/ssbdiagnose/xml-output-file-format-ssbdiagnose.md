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
# <a name="xml-output-file-format-ssbdiagnose"></a>Formato del archivo de salida XML (ssbdiagnose)
  La utilidad **ssbdiagnose** genera la salida en forma de archivo XML si se ejecuta con el modificador **-XML** . El archivo de salida XML incluye la información de encabezado y los errores encontrados en la configuración de [!INCLUDE[ssSB](../../includes/sssb-md.md)] o la conversación que se analizó. Si lo desea, puede escribir una aplicación para analizar o notificar los errores incluidos en el archivo. O bien, puede ver el archivo XML en un editor XML estándar, como XML Notepad.  
  
 Un archivo de resultados de **ssbdiangose** contiene un elemento raíz DiagnosticInformation con dos tipos secundarios:  
  
-   Un elemento Banner con información de encabezado.  
  
-   Un elemento Issue para cada problema notificado por **ssbdiangose**.  
  
## <a name="diagnosticinformation-root-element"></a>Elemento raíz DiagnosticInformation  
  
-   [Elemento DiagnosticInformation &#40;ssbdiagnose&#41;](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a>Elemento Banner  
  
-   [Elemento Banner &#40;ssbdiagnose&#41;](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a>Elemento Issue  
  
-   [Elemento Issue &#40;ssbdiagnose&#41;](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a>Consulte también  
 [Utilidad ssbdiagnose &#40;Service Broker&#41;](ssbdiagnose-utility-service-broker.md)  
  
  
