---
title: Establecer el idioma para los parámetros de informe en una dirección URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- overriding report language settings
- report servers [Reporting Services], language settings
- languages [Reporting Services]
- URL access [Reporting Services], language overrides
- international considerations [Reporting Services]
- global considerations [Reporting Services]
ms.assetid: e1ccf22f-80d6-45bc-aae0-f5f263275092
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8087a181906517bb60d4cd6839eed0681f52a5eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746148"
---
# <a name="set-the-language-for-report-parameters-in-a-url"></a><span data-ttu-id="76be4-102">Establecer el idioma para los parámetros de informe en una dirección URL</span><span class="sxs-lookup"><span data-stu-id="76be4-102">Set the Language for Report Parameters in a URL</span></span>
  <span data-ttu-id="76be4-103">El parámetro de acceso URL *rs:ParameterLanguage* reduce un problema por el que los parámetros de informe sujetos a referencias culturales (como las fechas, horas, monedas y cifras) se interpretan con el idioma del explorador.</span><span class="sxs-lookup"><span data-stu-id="76be4-103">The *rs:ParameterLanguage* URL access parameter alleviates a problem in which culture-sensitive report parameters, such as dates, times, currency, and numbers, are interpreted using the browser language.</span></span> <span data-ttu-id="76be4-104">Con *rs:ParameterLanguage*, la dirección URL se interpreta ahora independientemente del explorador.</span><span class="sxs-lookup"><span data-stu-id="76be4-104">With *rs:ParameterLanguage*, the URL is now interpreted independently of the browser.</span></span> <span data-ttu-id="76be4-105">Por ejemplo, si el servidor de informes está establecido en la configuración regional de alemán, pero un usuario tiene acceso a un informe a través de una dirección URL mediante un explorador que está configurado en inglés de Estados Unidos, los valores de los parámetros que se pasen a un servidor de informes se interpretarán mal.</span><span class="sxs-lookup"><span data-stu-id="76be4-105">For example, if the report server is set to a regional setting of German, but a user is accessing a report via a URL using a browser that is set to English-United States, parameter values that are passed to a report server will be misinterpreted.</span></span>  
  
 <span data-ttu-id="76be4-106">Considere la dirección URL siguiente para un informe:</span><span class="sxs-lookup"><span data-stu-id="76be4-106">Consider the following URL to a report:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008  
```  
  
 <span data-ttu-id="76be4-107">En el caso anterior, el servidor, que se ejecuta con la referencia cultural "de-de", genera una dirección URL a través de una suscripción de correo electrónico o un hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="76be4-107">In the above case, the server, running under a culture of "de-de", generates a URL either through an e-mail subscription or a hyperlink.</span></span> <span data-ttu-id="76be4-108">El hipervínculo indica que el informe debería parametrizarse con la fecha de inicio del 4 de octubre de 2008 y la fecha de fin del 11 de octubre de 2008, según los estándares de fecha y hora alemanas.</span><span class="sxs-lookup"><span data-stu-id="76be4-108">The hyperlink indicates that the report should be parameterized by a start date of October 4, 2008 and an end date of October 11, 2008 according to German date/time standards.</span></span> <span data-ttu-id="76be4-109">Sin embargo, un usuario que tenga acceso a la dirección URL a través de un explorador establecido en "en-us" obliga al servidor a interpretar los valores como 10 de abril de 2008 y 10 de noviembre de 2008 con los estándares de fecha y hora de inglés de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="76be4-109">However, a user that is accessing the URL through a browser set to "en-us" forces the server to interpret the values as April 10, 2008 and November 10, 2008 under United States English date/time standards.</span></span> <span data-ttu-id="76be4-110">Para corregir el problema, se puede utilizar *rs:ParameterLanguage* con el objeto de invalidar el idioma del explorador para la interpretación de los parámetros:</span><span class="sxs-lookup"><span data-stu-id="76be4-110">To fix the problem, *rs:ParameterLanguage* can be used to override the browser language for parameter interpretation:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008&rs:ParameterLanguage=de-DE  
```  
  
 <span data-ttu-id="76be4-111">Además del valor **true** y **false** para el parámetro de acceso URL *rc:Parameters*, ahora puede pasar el valor **Collapsed**.</span><span class="sxs-lookup"><span data-stu-id="76be4-111">In addition to a value of **true** and **false** for the URL access parameter *rc:Parameters*, you can now pass a value of **Collapsed**.</span></span> <span data-ttu-id="76be4-112">Al usar *rc:Parameters*=**Collapsed** en una dirección URL, el área de mensajes de parámetros del Visor HTML se contrae fuera de la vista, pero el usuario todavía puede cambiarla.</span><span class="sxs-lookup"><span data-stu-id="76be4-112">When using *rc:Parameters*=**Collapsed** on a URL, the parameter prompt area of the HTML viewer is collapsed out of sight, but can still be toggled by the user.</span></span> <span data-ttu-id="76be4-113">El valor **false** quita el área de mensajes de parámetros de la barra de herramientas del Visor HTML y hace que no esté disponible para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="76be4-113">A value of **false** removes the parameter prompt area from the HTML viewer toolbar and makes it unavailable to the end-user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76be4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76be4-114">See Also</span></span>  
 <span data-ttu-id="76be4-115">[Acceso URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76be4-115">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="76be4-116">Referencia de parámetros de acceso URL</span><span class="sxs-lookup"><span data-stu-id="76be4-116">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
