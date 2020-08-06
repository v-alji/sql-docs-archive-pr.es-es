---
title: Configurar Administrador de informes para pasar cookies de autenticación personalizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: 91aeb053-149e-4562-ae4c-a688d0e1b2ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 90e8798fb91152ec64e7f290dc1522fc8eaa451c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670257"
---
# <a name="configure-report-manager-to-pass-custom-authentication-cookies"></a><span data-ttu-id="2ee46-102">Configurar el Administrador de informes para pasar cookies de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="2ee46-102">Configure Report Manager to Pass Custom Authentication Cookies</span></span>
  <span data-ttu-id="2ee46-103">Si está utilizando una extensión de autenticación personalizada, debe configurar el Administrador de informes para transmitir cookies de autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="2ee46-103">If you are using a custom authentication extension, you should configure Report Manager to transmit custom authentication cookies.</span></span> <span data-ttu-id="2ee46-104">De lo contrario, el Administrador de informes solamente transmitirá cookies por medio de solicitudes HTTP específicas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2ee46-104">Otherwise, Report Manager will only transmit cookies through HTTP requests specific to the report server.</span></span> <span data-ttu-id="2ee46-105">Si desea transmitir cookies adicionales, debe modificar el archivo RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="2ee46-105">If you want to transmit additional cookies, you must modify the RSReportServer.Config file.</span></span>  
  
## <a name="modifying-the-rsreportserverconfig-file"></a><span data-ttu-id="2ee46-106">Modificar el archivo RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="2ee46-106">Modifying the RSReportServer.Config File</span></span>  
 <span data-ttu-id="2ee46-107">Puede habilitar Administrador de informes para transmitir cookies adicionales a través del servidor de informes. para ello, agregue un `PassThroughCookies` elemento <> a los valores de configuración del administrador de informes en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="2ee46-107">You can enable Report Manager to transmit additional cookies through to the report server by adding a <`PassThroughCookies`> element to the Report Manager configuration settings in the RSReportServer.config file.</span></span> <span data-ttu-id="2ee46-108">La transmisión de cookies adicionales resulta útil en una solución de autenticación de inicio de sesión único que requiera no solo las cookies de autenticación del servidor de informes, sino también cookies de un sistema de autenticación de otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="2ee46-108">Transmitting additional cookies is helpful in a single sign-on authentication solution that requires not only the report server authentication cookies, but also cookies from a third-party authentication system.</span></span>  
  
 <span data-ttu-id="2ee46-109">Para permitir que se transmitan cookies adicionales mediante solicitudes HTTP al usar el Administrador de informes, configure los elementos siguientes en el archivo RSReportServer.config:</span><span class="sxs-lookup"><span data-stu-id="2ee46-109">To enable additional cookies to be transmitted through HTTP requests when using Report Manager, set the following elements in the RSReportServer.config file:</span></span>  
  
```  
<UI>  
   <CustomAuthenticationUI>  
      ...  
      <PassThroughCookies>  
         <PassThroughCookie>cookiename1</PassThroughCookie>  
         <PassThroughCookie>cookiename2</PassThroughCookie>  
      </PassThroughCookies>  
   </CustomAuthenticationUI>  
      ...  
</UI>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ee46-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ee46-110">See Also</span></span>  
 <span data-ttu-id="2ee46-111">[Autenticación con el servidor de informes](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="2ee46-111">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="2ee46-112">[Archivo de configuración RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="2ee46-112">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="2ee46-113">[Información general de extensiones de seguridad](../extensions/security-extension/security-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="2ee46-113">[Security Extensions Overview](../extensions/security-extension/security-extensions-overview.md) </span></span>  
 [<span data-ttu-id="2ee46-114">Configurar y administrar un servidor de informes &#40;modo nativo de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2ee46-114">Configure and Administer a Report Server &#40;SSRS Native Mode&#41;</span></span>](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  
