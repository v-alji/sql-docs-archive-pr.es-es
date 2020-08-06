---
title: Autenticación del servicio web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], authentication
- XML Web service [Reporting Services], authentication
- Report Server Web service, authentication
ms.assetid: 852b4947-a090-4e54-8555-5a503945ceab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0c7836d6eba8c6ab3f0a8e705ebb79c7ed73eb17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749064"
---
# <a name="web-service-authentication"></a><span data-ttu-id="e271e-102">Autenticación del servicio web</span><span class="sxs-lookup"><span data-stu-id="e271e-102">Web Service Authentication</span></span>
  <span data-ttu-id="e271e-103">Puede utilizar la autenticación de Windows o la autenticación básica para autenticar las llamadas realizadas al servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e271e-103">You can use either Windows Authentication or Basic authentication to authenticate the calls made to the Report Server Web service.</span></span> <span data-ttu-id="e271e-104">Cualquier cliente que realice solicitudes SOAP al servidor de informes debe implementar la parte del cliente de uno de los protocolos de autenticación admitidos.</span><span class="sxs-lookup"><span data-stu-id="e271e-104">Any client that makes SOAP requests to the report server must implement the client portion of one of the supported authentication protocols.</span></span> <span data-ttu-id="e271e-105">Si usa [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , puede usar las clases http de código administrado para implementar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="e271e-105">If you are using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], you can use the managed code HTTP classes to implement authentication.</span></span> <span data-ttu-id="e271e-106">El uso de estas API facilita el envío de información de autenticación junto con las solicitudes SOAP.</span><span class="sxs-lookup"><span data-stu-id="e271e-106">Using these APIs makes it easy to send authentication information along with the SOAP requests.</span></span>  
  
 <span data-ttu-id="e271e-107">Si no tiene las credenciales adecuadas antes de realizar una llamada al servicio web del servidor de informes, se produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="e271e-107">If you do not have appropriate credentials before you make a call to the Report Server Web service, the call fails.</span></span> <span data-ttu-id="e271e-108">En tiempo de ejecución, se pueden pasar credenciales al servicio web estableciendo la propiedad **Credentials** del objeto del lado cliente que representa el servicio web antes de llamar a sus métodos.</span><span class="sxs-lookup"><span data-stu-id="e271e-108">At run time, you can pass credentials to the Web service by setting the **Credentials** property of the client-side object that represents the Web service before you call its methods.</span></span>  
  
 <span data-ttu-id="e271e-109">Las secciones siguientes contienen código de ejemplo que envía credenciales mediante [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e271e-109">The following sections contain example code that sends credentials using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="e271e-110">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="e271e-110">Windows Authentication</span></span>  
 <span data-ttu-id="e271e-111">El código siguiente pasa las credenciales de Windows al servicio web.</span><span class="sxs-lookup"><span data-stu-id="e271e-111">The following code passes Windows credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
ReportingService rs = new ReportingService();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
```  
  
## <a name="basic-authentication"></a><span data-ttu-id="e271e-112">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="e271e-112">Basic Authentication</span></span>  
 <span data-ttu-id="e271e-113">El código siguiente pasa las credenciales básicas al servicio web.</span><span class="sxs-lookup"><span data-stu-id="e271e-113">The following code passes Basic credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = New System.Net.NetworkCredential("username", "password", "domain")  
```  
  
```csharp  
ReportingService service = new ReportingService();  
service.Credentials = new System.Net.NetworkCredential("username", "password", "domain");  
```  
  
 <span data-ttu-id="e271e-114">Se deben establecer las credenciales antes de llamar a cualquiera de los métodos del servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e271e-114">The credentials must be set before you call any of the methods of the Report Server Web service.</span></span> <span data-ttu-id="e271e-115">Si no establece las credenciales, recibe el código de error HTTP 401 Error: Acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="e271e-115">If you do not set the credentials, you receive the error code an HTTP 401 Error: Access Denied.</span></span> <span data-ttu-id="e271e-116">Debe autenticar el servicio antes de utilizarlo, pero después de haber establecido las credenciales, no necesita establecerlas de nuevo siempre que continúe utilizando la misma variable de servicio (como *rs*).</span><span class="sxs-lookup"><span data-stu-id="e271e-116">You must authenticate the service before you use it, but after you have set the credentials, you do not need to set them again as long as you continue to use the same service variable (such as *rs*).</span></span>  
  
## <a name="custom-authentication"></a><span data-ttu-id="e271e-117">Autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="e271e-117">Custom Authentication</span></span>  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="e271e-118">incluye una API de programación que proporciona a los programadores la oportunidad de diseñar y desarrollar extensiones de autenticación personalizadas, conocidas como extensiones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e271e-118">includes a programming API that provides developers with the opportunity to design and develop custom authentication extensions, known as security extensions.</span></span> <span data-ttu-id="e271e-119">Para obtener más información, vea [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="e271e-119">For more information, see [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e271e-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e271e-120">See Also</span></span>  
 <span data-ttu-id="e271e-121">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="e271e-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="e271e-122">Servicio web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="e271e-122">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
