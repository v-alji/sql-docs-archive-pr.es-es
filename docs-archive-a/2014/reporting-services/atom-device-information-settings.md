---
title: Configuración de la información del dispositivo ATOM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdbac1500063accf868d4b538b82ba9f3b5aebb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672812"
---
# <a name="atom-device-information-settings"></a><span data-ttu-id="eb07f-102">Configuración de la información del dispositivo ATOM</span><span class="sxs-lookup"><span data-stu-id="eb07f-102">ATOM Device Information Settings</span></span>
  <span data-ttu-id="eb07f-103">La configuración de información de dispositivo para la extensión de representación Atom admite el envío de un nombre de una fuente Atom y la codificación de caracteres que se usará.</span><span class="sxs-lookup"><span data-stu-id="eb07f-103">The device information settings for the Atom rendering extension support submittal of the name of an Atom feed and character encoding to use.</span></span>  
  
 <span data-ttu-id="eb07f-104">En la siguiente tabla se enumera la configuración de información de dispositivo para la representación en un documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="eb07f-104">The following table lists the device information settings for rendering to a data service document.</span></span>  
  
|<span data-ttu-id="eb07f-105">Configuración</span><span class="sxs-lookup"><span data-stu-id="eb07f-105">Setting</span></span>|<span data-ttu-id="eb07f-106">Value</span><span class="sxs-lookup"><span data-stu-id="eb07f-106">Value</span></span>|  
|-------------|-----------|  
|`DataFeed`|<span data-ttu-id="eb07f-107">Si se especifica, representa la fuente Atom que corresponde al nombre de fuente proporcionado en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="eb07f-107">If specified, renders the Atom feed corresponding to the feed name provided in this setting.</span></span> <span data-ttu-id="eb07f-108">De lo contrario, representa el documento de servicio Atom para el informe.</span><span class="sxs-lookup"><span data-stu-id="eb07f-108">If not, renders the Atom service document for the report.</span></span> <span data-ttu-id="eb07f-109">El identificador único generado automáticamente de la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="eb07f-109">The unique auto-generated identifier of the data feed.</span></span> <span data-ttu-id="eb07f-110">Este valor se usa internamente y no se debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="eb07f-110">This  value is used internally and you should not change it.</span></span>|  
|<span data-ttu-id="eb07f-111">**Codificación**</span><span class="sxs-lookup"><span data-stu-id="eb07f-111">**Encoding**</span></span>|<span data-ttu-id="eb07f-112">Nombre del organismo Internet Assigned Numbers Authority (IANA) de una codificación de caracteres que es compatible con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb07f-112">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="eb07f-113">El valor predeterminado es `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="eb07f-113">The default value is `UTF-8`.</span></span> <span data-ttu-id="eb07f-114">Entre los ejemplos de otros valores se incluyen ASCII, UTF-7 y UTF-16.</span><span class="sxs-lookup"><span data-stu-id="eb07f-114">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb07f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb07f-115">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="eb07f-116">[Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="eb07f-116">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="eb07f-117">[Personalizar los parámetros de extensión de representación en RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="eb07f-117">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="eb07f-118">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb07f-118">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
