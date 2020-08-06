---
title: 'Lección 2: agregar una referencia Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2c2b8b8-6b13-45ca-ab3b-1582447b6807
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 02ca614cb042211ac468246c3003efaa5f2e8fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746650"
---
# <a name="lesson-2-adding-a-web-reference"></a><span data-ttu-id="e9588-102">Lección 2: Adición de una referencia web</span><span class="sxs-lookup"><span data-stu-id="e9588-102">Lesson 2: Adding a Web Reference</span></span>
  <span data-ttu-id="e9588-103">Se llama detección de servicios web al proceso por el que un cliente busca un servicio web y obtiene la descripción del servicio.</span><span class="sxs-lookup"><span data-stu-id="e9588-103">Web service discovery is the process by which a client locates a Web service and obtains its service description.</span></span> <span data-ttu-id="e9588-104">El proceso de detección de servicios web en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] conlleva la interrogación de un sitio web de acuerdo con un algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e9588-104">The process of Web service discovery in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] involves interrogating a Web site following a predetermined algorithm.</span></span> <span data-ttu-id="e9588-105">El objetivo del proceso es encontrar la descripción del servicio, que es un documento XML que utiliza el Lenguaje de descripción de servicios web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="e9588-105">The goal of the process is to locate the service description, which is an XML document that uses the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="e9588-106">En la descripción del servicio, se explican los servicios disponibles y la forma de interactuar con ellos.</span><span class="sxs-lookup"><span data-stu-id="e9588-106">The service description describes what services are available and how to interact with those services.</span></span> <span data-ttu-id="e9588-107">Sin una descripción del servicio, no se puede interactuar con el servicio web mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e9588-107">Without a service description, it is impossible to programmatically interact with a Web service.</span></span>  
  
 <span data-ttu-id="e9588-108">La aplicación debe disponer de un método para comunicarse con el servicio web y buscarlo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e9588-108">Your application must have a means to communicate with the Web service and to locate it at run time.</span></span> <span data-ttu-id="e9588-109">Esto se consigue agregando al proyecto una referencia del servicio web, porque se genera una clase proxy que sirve de interfaz con el servicio web y proporciona una representación local del servicio web.</span><span class="sxs-lookup"><span data-stu-id="e9588-109">Adding a Web reference to your project for the Web service does this by generating a proxy class that interfaces with the Web service and provides a local representation of the Web service.</span></span> <span data-ttu-id="e9588-110">Para obtener más información, vea el tema sobre generación de un proxy de servicio web XML en la documentación de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9588-110">For more information, see "How to: Generate an XML Web Service Proxy" in your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] documentation.</span></span>  
  
### <a name="to-add-a-web-reference"></a><span data-ttu-id="e9588-111">Para agregar una referencia web</span><span class="sxs-lookup"><span data-stu-id="e9588-111">To add a Web reference</span></span>  
  
1.  <span data-ttu-id="e9588-112">En el menú **proyecto** , haga clic en **Agregar referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e9588-112">On the **Project** menu, click **Add Service Reference**.</span></span>  
  
2.  <span data-ttu-id="e9588-113">En el cuadro de diálogo **Agregar referencia de servicio** , haga clic en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e9588-113">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
3.  <span data-ttu-id="e9588-114">En el cuadro de diálogo **configuración de referencia de servicio** , haga clic en **Agregar referencia Web**.</span><span class="sxs-lookup"><span data-stu-id="e9588-114">In the **Service Reference Settings** dialog box, click **Add Web Reference**.</span></span>  
  
4.  <span data-ttu-id="e9588-115">En el cuadro **dirección URL** del cuadro de diálogo **Agregar referencia Web** , escriba la dirección URL para obtener la descripción del servicio Web del servidor de informes, como http://localhost/reportserver/reportservice2010.asmx .</span><span class="sxs-lookup"><span data-stu-id="e9588-115">In the **URL** box of the **Add Web Reference** dialog box, type the URL to obtain the service description of the Report Server Web service, such as http://localhost/reportserver/reportservice2010.asmx.</span></span> <span data-ttu-id="e9588-116">A continuación, haga clic en el botón **ir** para recuperar información sobre el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="e9588-116">Then click the **Go** button to retrieve information about the Web service.</span></span>  
  
     <span data-ttu-id="e9588-117">\- o -</span><span class="sxs-lookup"><span data-stu-id="e9588-117">\- or -</span></span>  
  
     <span data-ttu-id="e9588-118">Si el servicio Web del servidor de informes existe en el equipo local, haga clic en el vínculo **servicios web del equipo local** en el panel explorador.</span><span class="sxs-lookup"><span data-stu-id="e9588-118">If the Report Server Web service exists on the local machine, click the **Web services on the local machine** link in the browser pane.</span></span> <span data-ttu-id="e9588-119">A continuación, haga clic en el vínculo del servicio web ReportService2010 de la lista proporcionada.</span><span class="sxs-lookup"><span data-stu-id="e9588-119">Then click the link for the ReportService2010 Web service from the list provided.</span></span>  
  
5.  <span data-ttu-id="e9588-120">En el cuadro **nombre de referencia Web** , cambie el nombre de la referencia Web a ReportService2010, que es el espacio de nombres que va a utilizar para esta referencia Web.</span><span class="sxs-lookup"><span data-stu-id="e9588-120">In the **Web reference name** box, rename the Web reference to ReportService2010, which is the namespace you will use for this Web reference.</span></span>  
  
6.  <span data-ttu-id="e9588-121">Haga clic en **Agregar referencia** para agregar una referencia Web para el servicio Web de destino.</span><span class="sxs-lookup"><span data-stu-id="e9588-121">Click **Add Reference** to add a Web reference for the target Web service.</span></span>  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] <span data-ttu-id="e9588-122">descarga la descripción del servicio y genera una clase proxy que sirve de interfaz entre la aplicación y el servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e9588-122">downloads the service description and generates a proxy class to interface between your application and the Report Server Web service.</span></span> <span data-ttu-id="e9588-123">También necesitará agregar una referencia al espacio de nombres <xref:System.Web.Services> para que su referencia web funcione.</span><span class="sxs-lookup"><span data-stu-id="e9588-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
7.  <span data-ttu-id="e9588-124">En el menú Proyecto, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e9588-124">On the Project menu, click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="e9588-125">En el cuadro de diálogo **Agregar referencia** , en la pestaña **.net** , seleccione **System. Web. Services**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e9588-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
 <span data-ttu-id="e9588-126">Para más información, vea [Acceso a la API de SOAP](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="e9588-126">For more information, see [Accessing the SOAP API](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9588-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9588-127">See Also</span></span>  
 <span data-ttu-id="e9588-128">[Servicio web del servidor de informes](../reporting-services/report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="e9588-128">[Report Server Web Service](../reporting-services/report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="e9588-129">[Lección 3: acceso al servicio Web](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="e9588-129">[Lesson 3: Accessing the Web Service](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span></span>  
 [<span data-ttu-id="e9588-130">Obtener acceso al servicio Web del servidor de informes mediante el tutorial de Visual Basic o Visual C&#35; &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e9588-130">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
