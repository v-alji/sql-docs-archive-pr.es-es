---
title: Proporcionar argumentos de métodos de servicio web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, methods
- Web service [Reporting Services], methods
- methods [Reporting Services], arguments
- XML Web service [Reporting Services], methods
ms.assetid: f7b9ca05-fc4c-4b30-8e5d-172dd0f4a832
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ef5188934628589751fe92d1839da0efb265766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749067"
---
# <a name="supplying-web-service-method-arguments"></a><span data-ttu-id="aa646-102">Proporcionar argumentos de métodos de servicio web</span><span class="sxs-lookup"><span data-stu-id="aa646-102">Supplying Web Service Method Arguments</span></span>
  <span data-ttu-id="aa646-103">Un método de servicio web del servidor de informes envía una solicitud al servicio en una dirección URL determinada utilizando SOAP sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="aa646-103">A Report Server Web service method sends a request to the service at a given URL using SOAP over HTTP.</span></span> <span data-ttu-id="aa646-104">El servicio recibe la solicitud, la procesa y, a continuación, devuelve una respuesta.</span><span class="sxs-lookup"><span data-stu-id="aa646-104">The service receives the request, processes it, and then returns a response.</span></span> <span data-ttu-id="aa646-105">Estas solicitudes y respuestas tienen forma de documentos XML.</span><span class="sxs-lookup"><span data-stu-id="aa646-105">These requests and responses are in the form of XML documents.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="aa646-106">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="aa646-106">Optional Parameters</span></span>  
 <span data-ttu-id="aa646-107">En algunos casos, un método de servicio web puede tener parámetros de entrada opcionales.</span><span class="sxs-lookup"><span data-stu-id="aa646-107">In some cases, a Web service method can have optional input parameters.</span></span> <span data-ttu-id="aa646-108">Incluso aunque un parámetro de entrada para un método de servicio web sea opcional, todavía debe incluirlo y establecer el valor del parámetro en `null` (`Nothing` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="aa646-108">Even if an input parameter for a Web service method is optional, you must still include it and set the parameter value to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="aa646-109">Al establecer un valor de parámetro en `null`, el valor de elemento para ese parámetro se establece en la solicitud SOAP en `null`.</span><span class="sxs-lookup"><span data-stu-id="aa646-109">Setting a parameter value to `null` sets the element value for that parameter in the SOAP request to `null`.</span></span>  
  
 <span data-ttu-id="aa646-110">En el ejemplo siguiente se utiliza el método <xref:ReportService2010.ReportingService2010.CreateFolder%2A> para crear un carpeta nueva denominada Product Sales en la carpeta Sales.</span><span class="sxs-lookup"><span data-stu-id="aa646-110">The following example uses the <xref:ReportService2010.ReportingService2010.CreateFolder%2A> method to create a new folder named Product Sales in the Sales folder.</span></span> <span data-ttu-id="aa646-111">Al ofrecer un valor `null` para las propiedades de la carpeta, no se proporciona ninguna propiedad específica del usuario para la carpeta:</span><span class="sxs-lookup"><span data-stu-id="aa646-111">By supplying a `null` value for the folder properties, no user-specific properties are supplied for the folder:</span></span>  
  
```  
// C#  
rs.CreateFolder("Product Sales", "/Sales", null);  
```  
  
## <a name="complex-data-types"></a><span data-ttu-id="aa646-112">Tipos de data complejos</span><span class="sxs-lookup"><span data-stu-id="aa646-112">Complex Data Types</span></span>  
 <span data-ttu-id="aa646-113">La clase principal del servicio web del servidor de informes es <xref:ReportService2010.ReportingService2010>, que se utiliza para invocar las operaciones SOAP o los métodos web de la clase de proxy.</span><span class="sxs-lookup"><span data-stu-id="aa646-113">The core class of the Report Server Web service is <xref:ReportService2010.ReportingService2010>, which you use to invoke the SOAP operations or Web methods of the proxy class.</span></span> <span data-ttu-id="aa646-114">Para admitir esta clase y sus métodos, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] incluye tipos de datos complejos definidos por el usuario que son específicos de los parámetros de entrada y salida de los métodos de servicio web.</span><span class="sxs-lookup"><span data-stu-id="aa646-114">To support this class and its methods, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes user-defined, complex data types that are specific to the input and output parameters of the Web service methods.</span></span> <span data-ttu-id="aa646-115">Estos tipos de datos complejos forman parte de la clase de proxy generada, que puede usar al desarrollar en el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="aa646-115">These complex data types are part of the generated proxy class, which you can use when developing in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] environment.</span></span>  
  
 <span data-ttu-id="aa646-116">Al generar una clase de proxy, los tipos de datos complejos que se definen en el archivo WSDL se representan mediante las clases de proxy, que incluyen las propiedades correspondientes a los diversos elementos de SOAP de los tipos de datos complejos.</span><span class="sxs-lookup"><span data-stu-id="aa646-116">When you generate a proxy class, the complex data types that are defined in the WSDL file are represented by the classes of the proxy, which include properties that correspond to the various SOAP elements of the complex data types.</span></span> <span data-ttu-id="aa646-117">Las secuencias de estos tipos de datos se convierten en matrices de objetos que puede enumerar en el código.</span><span class="sxs-lookup"><span data-stu-id="aa646-117">Sequences of these data types become arrays of objects that you can enumerate through in your code.</span></span> <span data-ttu-id="aa646-118">Esto evita tener que trabajar directamente con las estructuras XML que se envían en los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="aa646-118">This eliminates the need to work directly with the XML structures sent in SOAP messages.</span></span> <span data-ttu-id="aa646-119">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] realiza traducción en su lugar.</span><span class="sxs-lookup"><span data-stu-id="aa646-119">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] handles that translation for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa646-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa646-120">See Also</span></span>  
 <span data-ttu-id="aa646-121">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="aa646-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="aa646-122">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="aa646-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="aa646-123">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="aa646-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
