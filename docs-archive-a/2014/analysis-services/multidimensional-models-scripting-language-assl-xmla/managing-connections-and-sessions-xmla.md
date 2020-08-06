---
title: Administrar conexiones y sesiones (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- statefulness [XML for Analysis]
- statelessness [XML for Analysis]
- XML for Analysis, sessions
- states [XML for Analysis]
- XMLA, sessions
- sessions [XML for Analysis]
ms.assetid: b83bb3ff-09be-4fda-9d1d-6248e04ffb21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bfe876f6874193fd0885f16d91caa9f6fe8b172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671763"
---
# <a name="managing-connections-and-sessions-xmla"></a><span data-ttu-id="7d34d-102">Administrar conexiones y sesiones (XMLA)</span><span class="sxs-lookup"><span data-stu-id="7d34d-102">Managing Connections and Sessions (XMLA)</span></span>
  <span data-ttu-id="7d34d-103">*Estados* es una condición en la que el servidor conserva la identidad y el contexto de un cliente entre las llamadas de método.</span><span class="sxs-lookup"><span data-stu-id="7d34d-103">*Statefulness* is a condition during which the server preserves the identity and context of a client between method calls.</span></span> <span data-ttu-id="7d34d-104">*Estados* es una condición en la que el servidor no recuerda la identidad y el contexto de un cliente después de que finalice una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="7d34d-104">*Statelessness* is a condition during which the server does not remember the identity and context of a client after a method call finishes.</span></span>  
  
 <span data-ttu-id="7d34d-105">Para proporcionar Estados, XML for Analysis (XMLA) admite *sesiones* que permiten realizar una serie de instrucciones juntas.</span><span class="sxs-lookup"><span data-stu-id="7d34d-105">To provide statefulness, XML for Analysis (XMLA) supports *sessions* that allow a series of statements to be performed together.</span></span> <span data-ttu-id="7d34d-106">Un ejemplo de este tipo de serie de instrucciones sería la creación de un miembro calculado que se vaya a utilizar en consultas posteriores.</span><span class="sxs-lookup"><span data-stu-id="7d34d-106">An example of such a series of statements would be the creation of a calculated member that is to be used in subsequent queries.</span></span>  
  
 <span data-ttu-id="7d34d-107">En general, en XMLA las sesiones se ajustan al comportamiento siguiente descrito por la especificación de OLE DB 2.6:</span><span class="sxs-lookup"><span data-stu-id="7d34d-107">In general, sessions in XMLA follow the following behavior outlined by the OLE DB 2.6 specification:</span></span>  
  
-   <span data-ttu-id="7d34d-108">Las sesiones definen el ámbito de contexto de comandos y transacciones.</span><span class="sxs-lookup"><span data-stu-id="7d34d-108">Sessions define transaction and command context scope.</span></span>  
  
-   <span data-ttu-id="7d34d-109">Se pueden ejecutar varios comandos en el contexto de una sesión única.</span><span class="sxs-lookup"><span data-stu-id="7d34d-109">Multiple commands can be run in the context of a single session.</span></span>  
  
-   <span data-ttu-id="7d34d-110">La compatibilidad con transacciones en el contexto XMLA se realiza a través de comandos específicos del proveedor que se envían con el método [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="7d34d-110">Support for transactions in the XMLA context is through provider-specific commands sent with the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
 <span data-ttu-id="7d34d-111">XMLA define una manera de admitir sesiones en un entorno web de modo similar al enfoque utilizado por el protocolo de creación y control de versiones distribuidas (DAV) para implementar el bloqueo en un entorno de acoplamiento flexible.</span><span class="sxs-lookup"><span data-stu-id="7d34d-111">XMLA defines a way to support sessions in a Web environment in a mode similar to the approach used by the Distributed Authoring and Versioning (DAV) protocol to implement locking in a loosely coupled environment.</span></span> <span data-ttu-id="7d34d-112">Esta implementación se asemeja a DAV en que se permite al proveedor finalizar sesiones por distintas razones (por ejemplo, se supera un tiempo de espera o se produce un error de conexión).</span><span class="sxs-lookup"><span data-stu-id="7d34d-112">This implementation parallels DAV in that the provider is allowed to expire sessions for various reasons (for example, a timeout or connection error).</span></span> <span data-ttu-id="7d34d-113">Cuando se admiten sesiones, los servicios web deben tenerlo en cuenta y estar listos para controlar conjuntos de comandos interrumpidos que se deben reiniciar.</span><span class="sxs-lookup"><span data-stu-id="7d34d-113">When sessions are supported, Web services must be aware and ready to handle interrupted sets of commands that must be restarted.</span></span>  
  
 <span data-ttu-id="7d34d-114">La especificación de protocolo simple de acceso a objetos (SOAP) de World Wide Web Consortium (W3C) recomienda utilizar encabezados SOAP para generar nuevos protocolos sobre mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="7d34d-114">The World Wide Web Consortium (W3C) Simple Object Access Protocol (SOAP) specification recommends using SOAP headers for building up new protocols on top of SOAP messages.</span></span> <span data-ttu-id="7d34d-115">En la tabla siguiente se enumeran los atributos y los elementos de encabezado SOAP que XMLA define para iniciar, mantener y cerrar una sesión.</span><span class="sxs-lookup"><span data-stu-id="7d34d-115">The following table lists the SOAP header elements and attributes that XMLA defines for initiating, maintaining, and closing a session.</span></span>  
  
|<span data-ttu-id="7d34d-116">Encabezado SOAP</span><span class="sxs-lookup"><span data-stu-id="7d34d-116">SOAP header</span></span>|<span data-ttu-id="7d34d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d34d-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7d34d-118">BeginSession</span><span class="sxs-lookup"><span data-stu-id="7d34d-118">BeginSession</span></span>|<span data-ttu-id="7d34d-119">Este encabezado solicita al proveedor que cree una nueva sesión.</span><span class="sxs-lookup"><span data-stu-id="7d34d-119">This header requests the provider to create a new session.</span></span> <span data-ttu-id="7d34d-120">El proveedor deber responder mediante la construcción de una nueva sesión y la devolución de su identificador de sesión como parte del encabezado Session en la respuesta SOAP.</span><span class="sxs-lookup"><span data-stu-id="7d34d-120">The provider should respond by constructing a new session and returning the session ID as part of the Session header in the SOAP response.</span></span>|  
|<span data-ttu-id="7d34d-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="7d34d-121">SessionId</span></span>|<span data-ttu-id="7d34d-122">El área para valor contiene el identificador de sesión que se debe utilizar en cada llamada a método para el resto de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7d34d-122">The value area contains the session ID that must be used in each method call for the rest of the session.</span></span> <span data-ttu-id="7d34d-123">El proveedor de la respuesta SOAP envía esta etiqueta y el cliente también debe enviar este atributo con cada elemento de encabezado Session.</span><span class="sxs-lookup"><span data-stu-id="7d34d-123">The provider in the SOAP response sends this tag and the client must also send this attribute with each Session header element.</span></span>|  
|<span data-ttu-id="7d34d-124">Sesión</span><span class="sxs-lookup"><span data-stu-id="7d34d-124">Session</span></span>|<span data-ttu-id="7d34d-125">Debe utilizarse este encabezado en cada una de las llamadas a método que tiene lugar en la sesión; además, el identificador de sesión debe incluirse en el área para valor del encabezado.</span><span class="sxs-lookup"><span data-stu-id="7d34d-125">For every method call that occurs in the session, this header must be used, and the session ID must be included in the value area of the header.</span></span>|  
|<span data-ttu-id="7d34d-126">EndSession</span><span class="sxs-lookup"><span data-stu-id="7d34d-126">EndSession</span></span>|<span data-ttu-id="7d34d-127">Para finalizar la sesión, utilice este encabezado.</span><span class="sxs-lookup"><span data-stu-id="7d34d-127">To terminate the session, use this header.</span></span> <span data-ttu-id="7d34d-128">El identificador de sesión debe incluirse en el área para valor.</span><span class="sxs-lookup"><span data-stu-id="7d34d-128">The session ID must be included with the value area.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="7d34d-129">Un identificador de sesión no garantiza que una sesión sea válida.</span><span class="sxs-lookup"><span data-stu-id="7d34d-129">A session ID does not guarantee that a session stays valid.</span></span> <span data-ttu-id="7d34d-130">Si la sesión expira (por ejemplo, se agota el tiempo de espera o se pierde la conexión), el proveedor puede optar por finalizar y revertir las acciones de esa sesión.</span><span class="sxs-lookup"><span data-stu-id="7d34d-130">If the session expires (for example, if it times out or the connection is lost), the provider can choose to end and roll back that session's actions.</span></span> <span data-ttu-id="7d34d-131">Como resultado, todas las llamadas a método realizadas posteriormente desde el cliente con el identificador de sesión generan un error que señala una sesión no válida.</span><span class="sxs-lookup"><span data-stu-id="7d34d-131">As a result, all subsequent method calls from the client on a session ID fail with an error signaling a session that is not valid.</span></span> <span data-ttu-id="7d34d-132">El cliente debe controlar esta condición y estar preparado para reenviar las llamadas a método de la sesión desde el principio.</span><span class="sxs-lookup"><span data-stu-id="7d34d-132">A client should handle this condition and be prepared to resend the session method calls from the beginning.</span></span>  
  
## <a name="legacy-code-example"></a><span data-ttu-id="7d34d-133">Ejemplo de código heredado</span><span class="sxs-lookup"><span data-stu-id="7d34d-133">Legacy Code Example</span></span>  
 <span data-ttu-id="7d34d-134">En el ejemplo siguiente se muestra cómo se admiten las sesiones.</span><span class="sxs-lookup"><span data-stu-id="7d34d-134">The following example shows how sessions are supported.</span></span>  
  
1.  <span data-ttu-id="7d34d-135">Para comenzar la sesión, agregue un encabezado BeginSession en SOAP a la llamada al método XMLA saliente desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="7d34d-135">To begin the session, add a BeginSession header in SOAP to the outbound XMLA method call from the client.</span></span> <span data-ttu-id="7d34d-136">El área para valor aparece inicialmente en blanco porque todavía no se conoce el identificador de sesión.</span><span class="sxs-lookup"><span data-stu-id="7d34d-136">The value area is initially blank because the session ID is not yet known.</span></span>  
  
    ```  
    <SOAP-ENV:Envelope  
       xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
       SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
       <SOAP-ENV:Header>  
          <XA:BeginSession  
             xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
             xsi:type="xsd:int"  
             mustUnderstand="1"/>  
       </SOAP-ENV:Header>  
       <SOAP-ENV:Body>  
          ...<!-- Discover or Execute call goes here.-->  
       </SOAP-ENV:Body>  
    </SOAP-ENV:Envelope>  
    ```  
  
2.  <span data-ttu-id="7d34d-137">El mensaje de respuesta SOAP del proveedor incluye el identificador de sesión en el área de encabezado de devolución, utilizando la etiqueta de encabezado XMLA \<SessionId> .</span><span class="sxs-lookup"><span data-stu-id="7d34d-137">The SOAP response message from the provider includes the session ID in the return header area, using the XMLA header tag \<SessionId>.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
3.  <span data-ttu-id="7d34d-138">El encabezado Session debe agregarse para cada llamada a método de la sesión, con el identificador de sesión devuelto por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="7d34d-138">For each method call in the session, the Session header must be added, containing the session ID returned from the provider.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
4.  <span data-ttu-id="7d34d-139">Una vez completada la sesión, \<EndSession> se usa la etiqueta, que contiene el valor de identificador de sesión relacionado.</span><span class="sxs-lookup"><span data-stu-id="7d34d-139">When the session is complete, the \<EndSession> tag is used, containing the related session ID value.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:EndSession  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          xsi:type="xsd:int"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7d34d-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d34d-140">See Also</span></span>  
 [<span data-ttu-id="7d34d-141">Desarrollar con XMLA en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7d34d-141">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
