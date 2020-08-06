---
title: Configuración de la información del dispositivo MHTML | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], MHTML rendering
- MHTML [Reporting Services]
ms.assetid: 60b85dd8-b4fb-4ad9-be6a-e7c89ac076fe
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 076a0179871775984799fc8ce5366a220f812867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675239"
---
# <a name="mhtml-device-information-settings"></a><span data-ttu-id="da5aa-102">Configuración de la información del dispositivo MHTML</span><span class="sxs-lookup"><span data-stu-id="da5aa-102">MHTML Device Information Settings</span></span>
  <span data-ttu-id="da5aa-103">En la tabla siguiente se muestra una lista de la configuración de información de dispositivos para representar los informes en formato de archivo web (MHTML).</span><span class="sxs-lookup"><span data-stu-id="da5aa-103">The following table lists the device information settings for rendering reports in Web archive (MHTML) format.</span></span>  
  
|<span data-ttu-id="da5aa-104">Configuración</span><span class="sxs-lookup"><span data-stu-id="da5aa-104">Setting</span></span>|<span data-ttu-id="da5aa-105">Value</span><span class="sxs-lookup"><span data-stu-id="da5aa-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="da5aa-106">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="da5aa-106">**JavaScript**</span></span>|<span data-ttu-id="da5aa-107">Indica si JavaScript se admite en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="da5aa-107">Indicates whether JavaScript is supported in the rendered report.</span></span>|  
|<span data-ttu-id="da5aa-108">**OutlookCompat**</span><span class="sxs-lookup"><span data-stu-id="da5aa-108">**OutlookCompat**</span></span>|<span data-ttu-id="da5aa-109">Indica si la representación se va a realizar con metadatos adicionales que hacen que el informe tenga una apariencia mejorada en Outlook.</span><span class="sxs-lookup"><span data-stu-id="da5aa-109">Indicates whether to render with extra metadata that makes the report look better in Outlook.</span></span> <span data-ttu-id="da5aa-110">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="da5aa-110">The default value is `true`.</span></span>|  
|<span data-ttu-id="da5aa-111">**Fragmento MHTML**</span><span class="sxs-lookup"><span data-stu-id="da5aa-111">**MHTML Fragment**</span></span>|<span data-ttu-id="da5aa-112">Indica si un fragmento MHTML se crea en lugar de un documento MHTML completo.</span><span class="sxs-lookup"><span data-stu-id="da5aa-112">Indicates whether an MHTML fragment is created in place of a full MHTML document.</span></span> <span data-ttu-id="da5aa-113">Un fragmento MHTML incluye el contenido del informe en un elemento TABLE y omite los elementos BODY y HTML.</span><span class="sxs-lookup"><span data-stu-id="da5aa-113">An MHTML fragment includes the report content in a TABLE element and omits the HTML and BODY elements.</span></span> <span data-ttu-id="da5aa-114">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="da5aa-114">The default value is `false`.</span></span>|  
|<span data-ttu-id="da5aa-115">**DataVisualizationFitSizing**</span><span class="sxs-lookup"><span data-stu-id="da5aa-115">**DataVisualizationFitSizing**</span></span>|<span data-ttu-id="da5aa-116">Indica el comportamiento de ajuste para la visualización de datos cuando se esté dentro de un Tablix.</span><span class="sxs-lookup"><span data-stu-id="da5aa-116">Indicates data visualization fit behavior when inside a tablix.</span></span> <span data-ttu-id="da5aa-117">Esto incluye un gráfico, un medidor y un mapa.</span><span class="sxs-lookup"><span data-stu-id="da5aa-117">This includes chart, gauge, and map.</span></span><br /><br /> <span data-ttu-id="da5aa-118">Los valores posibles son **Aproximado** y **Exacto**.</span><span class="sxs-lookup"><span data-stu-id="da5aa-118">The possible values are **Approximate** and **Exact**.</span></span><br /><br /> <span data-ttu-id="da5aa-119">El valor predeterminado es **Aproximado**.</span><span class="sxs-lookup"><span data-stu-id="da5aa-119">The default value is **Approximate**.</span></span> <span data-ttu-id="da5aa-120">Si se quita el valor de configuración del archivo **rsreportserver.config** , el comportamiento predeterminado es **Exacto**.</span><span class="sxs-lookup"><span data-stu-id="da5aa-120">If the setting is removed from the **rsreportserver.config** file then the default behavior is **Exact**.</span></span><br /><br /> <span data-ttu-id="da5aa-121">Si se habilita **Exacto** , podría afectar al rendimiento porque el procesamiento necesario para determinar el tamaño exacto puede tardar más tiempo.</span><span class="sxs-lookup"><span data-stu-id="da5aa-121">Enabling **Exact** may have performance impact because the processing to determine the exact size may take longer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da5aa-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da5aa-122">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="da5aa-123">[Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="da5aa-123">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="da5aa-124">[Personalizar los parámetros de extensión de representación en RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="da5aa-124">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="da5aa-125">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="da5aa-125">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
