---
title: Configuración de la información del dispositivo Word | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Word [Reporting Services]
- device information settings [Reporting Services], Word
ms.assetid: 28146498-fae7-4b13-b47f-6ec05aa8e057
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ddd145c5073003a8dc189e3ed9b1bbb25dc11d09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662522"
---
# <a name="word-device-information-settings"></a><span data-ttu-id="42725-102">Configuración de la información del dispositivo web</span><span class="sxs-lookup"><span data-stu-id="42725-102">Word Device Information Settings</span></span>
  <span data-ttu-id="42725-103">En la tabla siguiente se muestra la configuración de la información de los dispositivos para la representación en formato de [!INCLUDE[ofprword](../includes/ofprword-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42725-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprword](../includes/ofprword-md.md)] format.</span></span>  
  
|<span data-ttu-id="42725-104">Configuración</span><span class="sxs-lookup"><span data-stu-id="42725-104">Setting</span></span>|<span data-ttu-id="42725-105">Value</span><span class="sxs-lookup"><span data-stu-id="42725-105">Value</span></span>|  
|-------------|-----------|  
|`AutoFit`|<span data-ttu-id="42725-106">`False`.</span><span class="sxs-lookup"><span data-stu-id="42725-106">`False`.</span></span> <span data-ttu-id="42725-107">AutoFit está establecido en `false` en cualquier tabla de Word.</span><span class="sxs-lookup"><span data-stu-id="42725-107">AutoFit is set to `false` set on any Word table.</span></span><br /><br /> <span data-ttu-id="42725-108">`True`.</span><span class="sxs-lookup"><span data-stu-id="42725-108">`True`.</span></span> <span data-ttu-id="42725-109">AutoaFit está establecido en `true` en cada tabla de Word.</span><span class="sxs-lookup"><span data-stu-id="42725-109">AutoFit is set to `true` on every Word table.</span></span><br /><br /> <span data-ttu-id="42725-110">`Never`.</span><span class="sxs-lookup"><span data-stu-id="42725-110">`Never`.</span></span> <span data-ttu-id="42725-111">Los valores de AutoFit no están establecidos en ninguna tabla de Word y el comportamiento revierte al predeterminado de Word.</span><span class="sxs-lookup"><span data-stu-id="42725-111">AutoFit values are not set on any Word table and behavior reverts to the Word default.</span></span><br /><br /> <span data-ttu-id="42725-112">`Default`.</span><span class="sxs-lookup"><span data-stu-id="42725-112">`Default`.</span></span> <span data-ttu-id="42725-113">AutoFit se establece en las tablas que son más estrechas que el área física de dibujo (ancho de página física excepto los márgenes) por la página lógica.</span><span class="sxs-lookup"><span data-stu-id="42725-113">AutoFit is set on tables that are narrower than the physical drawing area (physical page width excluding margins) per logical page.</span></span>|  
|`ExpandToggles`|<span data-ttu-id="42725-114">Indica si todos los elementos que se pueden alternar deberían representarse en su estado totalmente expandido.</span><span class="sxs-lookup"><span data-stu-id="42725-114">Indicates whether all items that can be toggled should render in their fully-expanded state.</span></span> <span data-ttu-id="42725-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="42725-115">The default value is `false`.</span></span>|  
|`FixedPageWidth`|<span data-ttu-id="42725-116">Indica si el ancho de página escrito en el archivo DOC crecerá para alojar el ancho de la página más grande en el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="42725-116">Indicates whether the Page Width written to the DOC file will grow to accommodate the width of the largest page in the Report Body.</span></span> <span data-ttu-id="42725-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="42725-117">The default value is `false`.</span></span>|  
|<span data-ttu-id="42725-118">**OmitHyperlinks**</span><span class="sxs-lookup"><span data-stu-id="42725-118">**OmitHyperlinks**</span></span>|<span data-ttu-id="42725-119">Indica si omitir la acción Hyperlink en todos los elementos donde se establezca.</span><span class="sxs-lookup"><span data-stu-id="42725-119">Indicates whether to omit the Hyperlink action on all items where it is set.</span></span> <span data-ttu-id="42725-120">El valor predeterminado es `false`</span><span class="sxs-lookup"><span data-stu-id="42725-120">The default value is `false`</span></span>|  
|`OmitDrillthroughs`|<span data-ttu-id="42725-121">Indica si omitir la acción de obtención de detalles en todos los elementos donde se establezca.</span><span class="sxs-lookup"><span data-stu-id="42725-121">Indicates whether to omit the Drillthrough action on all items where it is set.</span></span> <span data-ttu-id="42725-122">El valor predeterminado es `false`</span><span class="sxs-lookup"><span data-stu-id="42725-122">The default value is `false`</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42725-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42725-123">See Also</span></span>  
 <span data-ttu-id="42725-124">[Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="42725-124">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="42725-125">[Personalizar los parámetros de extensión de representación en RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="42725-125">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="42725-126">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="42725-126">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
