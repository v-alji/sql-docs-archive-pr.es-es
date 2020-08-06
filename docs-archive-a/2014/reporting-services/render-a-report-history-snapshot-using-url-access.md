---
title: Representar instantáneas del historial de informes mediante acceso URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], report history
- history snapshots [Reporting Services]
- historical data [Reporting Services]
- snapshots [Reporting Services], URL access
- snapshots [Reporting Services], rendering report history
ms.assetid: 3f87f82d-0e61-4492-9c4b-f5238c39e8cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 67854a39ab7e38289627d03ac00cc4b2a6dca6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672784"
---
# <a name="render-a-report-history-snapshot-using-url-access"></a><span data-ttu-id="6f231-102">Representar instantáneas del historial de informes mediante acceso URL</span><span class="sxs-lookup"><span data-stu-id="6f231-102">Render a Report History Snapshot Using URL Access</span></span>
  <span data-ttu-id="6f231-103">Puede representar un informe basado en una instantánea del historial de informes si proporciona el parámetro *rs:Snapshot* y establece su valor en un identificador de instantánea válido.</span><span class="sxs-lookup"><span data-stu-id="6f231-103">You can render a report based on a report history snapshot by supplying the *rs:Snapshot* parameter and setting its value to a valid snapshot ID.</span></span> <span data-ttu-id="6f231-104">El valor del parámetro está en el formato AAAA-MM-DDTHH:MM:SS, según el estándar 8601 de la Organización internacional de normalización (ISO).</span><span class="sxs-lookup"><span data-stu-id="6f231-104">The parameter value is in the format YYYY-MM-DDTHH:MM:SS, based on the International Organization for Standardization (ISO) 8601 standard.</span></span>  
  
 <span data-ttu-id="6f231-105">Si omite este parámetro, el informe se representa según la configuración de la ejecución del informe y de la administración de la memoria caché del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6f231-105">If you omit this parameter, the report is rendered according to the report execution and cache management option settings of the report server.</span></span> <span data-ttu-id="6f231-106">Para obtener más información sobre la ejecución del informe, vea [Establecer las propiedades del procesamiento de informes](report-server/set-report-processing-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6f231-106">For more information about report execution, see [Set Report Processing Properties](report-server/set-report-processing-properties.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f231-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f231-107">Example</span></span>  
 <span data-ttu-id="6f231-108">En el ejemplo siguiente se muestra una dirección URL que recupera una instantánea del historial de informes:</span><span class="sxs-lookup"><span data-stu-id="6f231-108">The following example shows a URL that retrieves a report history snapshot:</span></span>  
  
```  
http://myrshost/reportserver?/SampleReports/Company Sales&rs:Snapshot=2003-04-07T13:40:02  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f231-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f231-109">See Also</span></span>  
 <span data-ttu-id="6f231-110">[Acceso URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f231-110">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="6f231-111">Referencia de parámetros de acceso URL</span><span class="sxs-lookup"><span data-stu-id="6f231-111">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
