---
title: El rol de SOAP en Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- SOAP [Reporting Services], role in Reporting Services
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: f229c3ef-f2ca-448f-98f1-b8df350b9992
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05445eb1c95c5761595944867b6d0c20a6f1a412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746166"
---
# <a name="the-role-of-soap-in-reporting-services"></a><span data-ttu-id="a158f-102">El rol de SOAP en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a158f-102">The Role of SOAP in Reporting Services</span></span>
  <span data-ttu-id="a158f-103">El servicio web del servidor de informes utiliza la mensajería del Protocolo simple de acceso a objetos (SOAP, Simple Object Access Protocol) para enviar comandos basados en texto a través de una red.</span><span class="sxs-lookup"><span data-stu-id="a158f-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) messaging to send text-based commands over a network.</span></span> <span data-ttu-id="a158f-104">Estos comandos adoptan la forma de texto XML que se envía a través de World Wide Web utilizando HTTP.</span><span class="sxs-lookup"><span data-stu-id="a158f-104">These commands take the form of XML text that is sent over the World Wide Web using HTTP.</span></span> <span data-ttu-id="a158f-105">Al usar SOAP como protocolo de comunicaciones, el servicio web del servidor de informes permite a las aplicaciones y componentes intercambiar datos con el servidor de informes utilizando una infraestructura abierta y ampliamente aceptada.</span><span class="sxs-lookup"><span data-stu-id="a158f-105">By using SOAP as its communication protocol, the Report Server Web service allows applications and components to exchange data with the report server using an open and widely accepted infrastructure.</span></span> <span data-ttu-id="a158f-106">El estándar SOAP se define en www.w3.org/TR/SOAP.</span><span class="sxs-lookup"><span data-stu-id="a158f-106">The SOAP standard is defined at www.w3.org/TR/SOAP.</span></span>  
  
 <span data-ttu-id="a158f-107">Cualquier aplicación cliente puede actuar como cliente SOAP siempre que conozca dicho protocolo y pueda enviar solicitudes SOAP.</span><span class="sxs-lookup"><span data-stu-id="a158f-107">Any client application can act as a SOAP client as long as it is SOAP-aware and can send SOAP requests.</span></span> <span data-ttu-id="a158f-108">El Administrador de informes es un cliente SOAP de este tipo.</span><span class="sxs-lookup"><span data-stu-id="a158f-108">Report Manager is one such SOAP client.</span></span> <span data-ttu-id="a158f-109">Proporciona una interfaz para la base de datos del servidor de informes en la que se almacenan todos los informes y el contenido relacionado con los informes.</span><span class="sxs-lookup"><span data-stu-id="a158f-109">It provides an interface to the report server database in which all reports and report-related content is stored.</span></span> <span data-ttu-id="a158f-110">Los usuarios finales pueden utilizar la aplicación para explorar y administrar los informes y carpetas en el espacio de nombres del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a158f-110">End users can use the application to browse through and manage reports and folders in the report server namespace.</span></span> <span data-ttu-id="a158f-111">El Administrador de informes se integra en la infraestructura del servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a158f-111">Report Manager is built on the Report Server Web service infrastructure.</span></span>  
  
 <span data-ttu-id="a158f-112">Un servidor de informes actúa como servidor SOAP, un servicio que conoce SOAP y puede aceptar las solicitudes de los clientes SOAP y crear las respuestas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="a158f-112">A report server acts as a SOAP server, a SOAP-aware service that can accept requests from SOAP clients and create appropriate responses.</span></span> <span data-ttu-id="a158f-113">El servidor administra las solicitudes y envía las respuestas codificadas al cliente.</span><span class="sxs-lookup"><span data-stu-id="a158f-113">The server handles the requests and sends encoded responses back to the client.</span></span>  
  
 <span data-ttu-id="a158f-114">Los mensajes SOAP en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] adoptan muchas formas diferentes, según el tipo de solicitud que realice el cliente.</span><span class="sxs-lookup"><span data-stu-id="a158f-114">SOAP messages in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] take many different forms, depending on the type of request made by the client.</span></span> <span data-ttu-id="a158f-115">En el ejemplo siguiente se representa una solicitud de cliente SOAP simple para quitar un elemento de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a158f-115">The following example represents a simple SOAP client request to remove an item from the report server database.</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItem xmlns="https://www.microsoft.com/sql/ReportingServer">  
            <item>/Samples/Report1</item>  
        </DeleteItem>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="a158f-116">El propio SOAP requiere que los mensajes se coloquen en un elemento `Envelope`, con la mayoría del mensaje dentro de un elemento `Body`.</span><span class="sxs-lookup"><span data-stu-id="a158f-116">The SOAP itself requires that messages be put into an `Envelope` element, with the bulk of the message inside a `Body` element.</span></span> <span data-ttu-id="a158f-117">En este ejemplo, el cuerpo contiene una llamada al método <xref:ReportService2010.ReportingService2010.DeleteItem%2A>, que acepta un parámetro de cadena que representa la ruta de acceso al elemento que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="a158f-117">In this example, the body contains a call to the <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method, which takes a string parameter representing the path of the item to delete.</span></span> <span data-ttu-id="a158f-118">Puede crear una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] clase de proxy de cliente que encapsule todas las operaciones SOAP en métodos.</span><span class="sxs-lookup"><span data-stu-id="a158f-118">You can create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] client proxy class that encapsulates all SOAP operations into methods.</span></span> <span data-ttu-id="a158f-119">El [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] método siguiente representa el ejemplo de SOAP proporcionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a158f-119">The following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] method represents the SOAP example given earlier.</span></span>  
  
```  
public void DeleteItem(string item);  
```  
  
 <span data-ttu-id="a158f-120">La respuesta del servidor podría ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a158f-120">The response from the server might look like the following:</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItemResponse xmlns="https://www.microsoft.com/sql/ReportingServer" />  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="a158f-121">El método <xref:ReportService2010.ReportingService2010.DeleteItem%2A> no devuelve ningún valor, de modo que se devuelve una respuesta vacía.</span><span class="sxs-lookup"><span data-stu-id="a158f-121">The <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method has no return value, so an empty response is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a158f-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a158f-122">See Also</span></span>  
 <span data-ttu-id="a158f-123">[Obtener acceso a la API de SOAP](accessing-the-soap-api.md) </span><span class="sxs-lookup"><span data-stu-id="a158f-123">[Accessing the SOAP API](accessing-the-soap-api.md) </span></span>  
 <span data-ttu-id="a158f-124">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a158f-124">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="a158f-125">[Reporting Services servidor de informes](../reporting-services-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="a158f-125">[Reporting Services Report Server](../reporting-services-report-server.md) </span></span>  
 [<span data-ttu-id="a158f-126">Servicio web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="a158f-126">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
