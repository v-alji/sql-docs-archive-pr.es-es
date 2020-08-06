---
title: Usar la API de SOAP en una aplicación Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- Windows applications [Reporting Services]
- Windows Forms [Reporting Services]
- SOAP [Reporting Services], Windows applications
ms.assetid: e4804792-20cd-4df2-9257-fb958ff447b4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 115ce02da69a8adb2c7a3de4175e528f281eb2b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661822"
---
# <a name="using-the-soap-api-in-a-windows-application"></a><span data-ttu-id="beb85-102">Usar la API SOAP en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="beb85-102">Using the SOAP API in a Windows Application</span></span>
  <span data-ttu-id="beb85-103">Puede tener acceso a la funcionalidad completa del servidor de informes a través de la API SOAP de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="beb85-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="beb85-104">Se trata de un servicio web y, como tal, se puede tener acceso con facilidad al mismo con el fin de proporcionar características de informes de empresa para aplicaciones empresariales personalizadas.</span><span class="sxs-lookup"><span data-stu-id="beb85-104">The SOAP API is a Web service and, as such, can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="beb85-105">Puede tener acceso al servicio web en una aplicación Windows simplemente escribiendo código que realice llamadas al servicio.</span><span class="sxs-lookup"><span data-stu-id="beb85-105">You can access the Web service in a Windows application simply by writing code that makes calls to the service.</span></span> <span data-ttu-id="beb85-106">Con [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , puede generar una clase de proxy que exponga las propiedades y los métodos del servicio Web y le permita usar una infraestructura y herramientas conocidas para compilar aplicaciones empresariales basadas en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tecnología.</span><span class="sxs-lookup"><span data-stu-id="beb85-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Web service and enables you to use a familiar infrastructure and tools to build business applications built on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
## <a name="integrating-report-management-functionality-using-windows-forms"></a><span data-ttu-id="beb85-107">Integrar la funcionalidad de administración de informes usando formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="beb85-107">Integrating Report Management Functionality Using Windows Forms</span></span>  
 <span data-ttu-id="beb85-108">A diferencia del acceso URL, la API SOAP expone el conjunto completo de funciones de administración que están disponibles a través del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="beb85-108">Unlike URL access, the SOAP API exposes the complete set of management functions that are available through the report server.</span></span> <span data-ttu-id="beb85-109">Esto significa que toda la funcionalidad administrativa del Administrador de informes está disponible para los programadores a través de SOAP.</span><span class="sxs-lookup"><span data-stu-id="beb85-109">This means that the entire administrative functionality of Report Manager is available to developers through SOAP.</span></span> <span data-ttu-id="beb85-110">Como tal, puede desarrollar una completa herramienta de administración utilizando formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="beb85-110">As such, you can develop a complete management and administration tool using Windows Forms.</span></span> <span data-ttu-id="beb85-111">Por ejemplo, en una aplicación Windows podría desear permitir que los usuarios recuperaran el contenido del espacio de nombres del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="beb85-111">For example, in your Windows application, you might want to enable your users to retrieve the contents of the report server namespace.</span></span> <span data-ttu-id="beb85-112">Para ello, podría usar el método <xref:ReportService2010.ReportingService2010.ListChildren%2A> del servicio web para mostrar todos los elementos de la base de datos del servidor de informes y, a continuación, usar un control Listview, Treeview o Combobox para mostrar esos elementos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="beb85-112">To do this, you could use the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method to list all the items in the report server database and then use a Listview, Treeview, or Combobox control to display those items to your users.</span></span> <span data-ttu-id="beb85-113">El código del servicio web siguiente se podría utilizar para recuperar la lista actual de informes disponibles en la carpeta Mis informes de un usuario cuando este haga clic en un botón de un formulario:</span><span class="sxs-lookup"><span data-stu-id="beb85-113">The following Web service code might be used to retrieve the current list of available reports in a user's My Reports folder when a user clicks a button on a form:</span></span>  
  
```vb  
' Button click event that retrieves a list of reports from  
' the My Reports folder and displays them in a combo box  
Private Sub listReportsButton_Click(sender As Object, e As System.EventArgs)  
   ' Create a new Web service object and set credentials  
   ' to Windows Authentication  
   Dim rs As New ReportingService2010()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return the list of items in My Reports  
   Dim items As CatalogItem() = rs.ListChildren("/Adventureworks 2008 Sample Reports", False)  
  
   Dim ci As CatalogItem  
   For Each ci In  items  
      ' If the item is a report, add it to   
      ' a combo box  
      If ci.TypeName = "Report" Then  
         catalogComboBox.Items.Add(ci.Name)  
      End If  
   Next ci  
End Sub 'listReportsButton_Click  
```  
  
```csharp  
// Button click event that retrieves a list of reports from  
// the My Reports folder and displays them in a combo box  
private void listReportsButton_Click(object sender, System.EventArgs e)  
{  
   // Create a new Web service object and set credentials  
   // to Windows Authentication  
   ReportingService2010 rs = new ReportingService2010();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return the list of items in My Reports  
   CatalogItem[] items = rs.ListChildren("/Adventureworks 2008 Sample Reports", false);  
  
   foreach (CatalogItem ci in items)  
   {  
      // If the item is a report, add it to   
      // a combo box  
      if (ci.TypeName == "Report")  
         catalogComboBox.Items.Add(ci.Name);  
   }  
}  
```  
  
 <span data-ttu-id="beb85-114">Desde allí, podría permitir que los usuarios seleccionen el informe en el cuadro combinado y obtener una vista previa del mismo en el formulario bien con un control de explorador web o con un control de imagen.</span><span class="sxs-lookup"><span data-stu-id="beb85-114">From there, you might enable users to select the report from the Combo box and preview the report on the form either using a Web browser control or an image control.</span></span>  
  
## <a name="enabling-report-viewing-and-navigation-using-windows-forms"></a><span data-ttu-id="beb85-115">Habilitar la visualización de informes y la navegación con formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="beb85-115">Enabling Report Viewing and Navigation Using Windows Forms</span></span>  
 <span data-ttu-id="beb85-116">Hay dos métodos disponibles para integrar los informes en aplicaciones de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="beb85-116">There are two methods available for integrating reports into your Windows Forms applications.</span></span>  
  
 <span data-ttu-id="beb85-117">Puede utilizar la API SOAP para representar los informes en cualquiera de los formatos de representación admitidos utilizando el método <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="beb85-117">You can use the SOAP API to render reports to any of the supported rendering formats using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="beb85-118">Habilitar la visualización de los informes y la navegación a través de SOAP presenta ligeras desventajas:</span><span class="sxs-lookup"><span data-stu-id="beb85-118">There are slight disadvantages to enabling report viewing and navigation through SOAP:</span></span>  
  
-   <span data-ttu-id="beb85-119">No puede aprovecharse de la funcionalidad integrada de la barra de herramientas de informe que se incluye con el Visor HTML a través del acceso URL.</span><span class="sxs-lookup"><span data-stu-id="beb85-119">You cannot take advantage of the built-in functionality of the report toolbar that is included with the HTML Viewer through URL access.</span></span>  
  
-   <span data-ttu-id="beb85-120">Si usa HTML para la representación, debe representar por separado las imágenes o recursos como flujos adicionales utilizando el método <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="beb85-120">If you render to HTML, you must separately render any images or resources as additional streams using the <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A> method.</span></span>  
  
-   <span data-ttu-id="beb85-121">Representar los informes mediante acceso URL supone una ligera ventaja de rendimiento sobre el uso de la API SOAP.</span><span class="sxs-lookup"><span data-stu-id="beb85-121">There is a slight performance advantage to rendering reports using URL access over using the SOAP API.</span></span>  
  
 <span data-ttu-id="beb85-122">Sin embargo, el método <xref:ReportExecution2005.ReportExecutionService.Render%2A> de la API SOAP se puede utilizar para representar los informes y guardarlos en varios formatos de salida mediante programación.</span><span class="sxs-lookup"><span data-stu-id="beb85-122">However, the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method of the SOAP API can be used to render reports and save them to various output formats programmatically.</span></span> <span data-ttu-id="beb85-123">Esto es una ventaja sobre el acceso URL, que requiere la interacción con el usuario.</span><span class="sxs-lookup"><span data-stu-id="beb85-123">This is an advantage over URL access, which requires user interaction.</span></span> <span data-ttu-id="beb85-124">Al representar un informe usando el método <xref:ReportExecution2005.ReportExecutionService.Render%2A> de la API SOAP, puede usar cualquiera de los formatos de salida admitidos.</span><span class="sxs-lookup"><span data-stu-id="beb85-124">When you render a report using the SOAP API <xref:ReportExecution2005.ReportExecutionService.Render%2A> method, you can render to any of the supported output formats.</span></span>  
  
 <span data-ttu-id="beb85-125">También puede usar los controles ReportViewer que se pueden distribuir libremente que se incluyen con [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="beb85-125">You can also use the freely distributable ReportViewer controls that are included with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span> <span data-ttu-id="beb85-126">Los controles ReportViewer permiten incrustar fácilmente la funcionalidad de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en las aplicaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="beb85-126">The ReportViewer controls make it easy to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] functionality into custom applications.</span></span> <span data-ttu-id="beb85-127">Los controles ReportViewer se han concebido para los programadores que desean proporcionar informes prediseñados, completamente creados, como parte del conjunto de características de una aplicación (por ejemplo, una aplicación de administración de un sitio web debería incluir informes que mostrasen análisis de flujos de clic de los sitios web de la compañía).</span><span class="sxs-lookup"><span data-stu-id="beb85-127">The ReportViewer controls are intended for developers who want to provide predesigned, fully authored reports as part of an application feature set (for example, a Web site management application might include reports that show click-stream analysis on company Web sites).</span></span> <span data-ttu-id="beb85-128">Incrustar los controles en una aplicación es una alternativa simplificada frente a incluir los componentes de servidor de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en la implementación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="beb85-128">Embedding the controls in an application provides a streamlined alternative to including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server components in your application deployment.</span></span> <span data-ttu-id="beb85-129">Los controles proporcionan funcionalidad de informes, pero sin las características de compatibilidad adicionales de creación, publicación, distribución y entrega de informes que se incluyen en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beb85-129">The controls provide report functionality, but without the additional report authoring, publication, or distribution and delivery support that you find in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="beb85-130">Hay dos versiones de los controles ReportViewer, una para aplicaciones cliente de Windows completas y otra para las aplicaciones [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beb85-130">There are two versions of the ReportViewer controls, one for rich Windows client applications and one for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications.</span></span> <span data-ttu-id="beb85-131">Los controles admiten tanto el modo de procesamiento local como el modo de procesamiento remoto.</span><span class="sxs-lookup"><span data-stu-id="beb85-131">The controls support both local processing and remote processing modes.</span></span> <span data-ttu-id="beb85-132">En el modo de procesamiento local, la aplicación proporciona la definición y los conjuntos de datos de los informes y desencadena el procesamiento de los informes.</span><span class="sxs-lookup"><span data-stu-id="beb85-132">In local processing mode, your application provides the report definition and datasets and triggers report processing.</span></span> <span data-ttu-id="beb85-133">En el modo de procesamiento remoto, la recuperación de datos y el procesamiento de informes tienen lugar en el servidor de informes y el control se utiliza para la visualización y navegación en informes.</span><span class="sxs-lookup"><span data-stu-id="beb85-133">In remote processing mode, data retrieval and report processing happen on the report server and the control is used for display and report navigation.</span></span> <span data-ttu-id="beb85-134">Este modelo le permite crear aplicaciones completas que pueden distribuirse del escritorio a la empresa.</span><span class="sxs-lookup"><span data-stu-id="beb85-134">This model allows you to build rich applications that can be scaled from desktop to the enterprise.</span></span>  
  
 <span data-ttu-id="beb85-135">Los controles ReportViewer se describen en la Ayuda en pantalla de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beb85-135">ReportViewer controls are documented in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] online Help.</span></span> <span data-ttu-id="beb85-136">Para obtener más información, vea la documentación del producto de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beb85-136">For more information, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] product documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb85-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="beb85-137">See Also</span></span>  
 <span data-ttu-id="beb85-138">[Creación de aplicaciones con el servicio web y .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="beb85-138">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="beb85-139">[Integración de Reporting Services en aplicaciones](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="beb85-139">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="beb85-140">Usar la API SOAP en una aplicación web</span><span class="sxs-lookup"><span data-stu-id="beb85-140">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
  
  
