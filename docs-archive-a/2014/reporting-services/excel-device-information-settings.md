---
title: Configuración de la información del dispositivo Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d71c83195c8f91984bbbce95bd00402928fdb36e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747483"
---
# <a name="excel-device-information-settings"></a><span data-ttu-id="90832-102">Configuración de la información del dispositivo Excel</span><span class="sxs-lookup"><span data-stu-id="90832-102">Excel Device Information Settings</span></span>
  <span data-ttu-id="90832-103">En la tabla siguiente se muestra la configuración de la información de los dispositivos para la representación en formato de [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90832-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] format.</span></span>  
  
|<span data-ttu-id="90832-104">Configuración</span><span class="sxs-lookup"><span data-stu-id="90832-104">Setting</span></span>|<span data-ttu-id="90832-105">Value</span><span class="sxs-lookup"><span data-stu-id="90832-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="90832-106">**OmitDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="90832-106">**OmitDocumentMap**</span></span>|<span data-ttu-id="90832-107">Indica si omitir el mapa del documento para los informes que lo admiten.</span><span class="sxs-lookup"><span data-stu-id="90832-107">Indicates whether to omit the document map for reports that support it.</span></span> <span data-ttu-id="90832-108">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="90832-108">The default value is `false`.</span></span>|  
|<span data-ttu-id="90832-109">**OmitFormulas**</span><span class="sxs-lookup"><span data-stu-id="90832-109">**OmitFormulas**</span></span>|<span data-ttu-id="90832-110">Indica si omitir las fórmulas del informe representado.</span><span class="sxs-lookup"><span data-stu-id="90832-110">Indicates whether to omit formulas from the rendered report.</span></span> <span data-ttu-id="90832-111">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="90832-111">The default value is `false`.</span></span>|  
|<span data-ttu-id="90832-112">`SimplePageHeade`rs</span><span class="sxs-lookup"><span data-stu-id="90832-112">`SimplePageHeade`rs</span></span>|<span data-ttu-id="90832-113">Indica si el encabezado de página del informe se representa en el encabezado de página de Excel.</span><span class="sxs-lookup"><span data-stu-id="90832-113">Indicates whether the page header of the report is rendered to the Excel page header.</span></span> <span data-ttu-id="90832-114">El valor `false` indica que el encabezado de página se representa en la primera fila de la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="90832-114">A value of `false` indicates that the page header is rendered to the first row of the worksheet.</span></span> <span data-ttu-id="90832-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="90832-115">The default value is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90832-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90832-116">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="90832-117">[Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="90832-117">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="90832-118">[Personalizar los parámetros de extensión de representación en RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="90832-118">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="90832-119">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="90832-119">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
