---
title: Usar la API de SOAP en una aplicación web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], Web applications
- impersonation [Reporting Services]
- user impersonation [Reporting Services]
- report servers [Reporting Services], SOAP
- Web applications [Reporting Services]
ms.assetid: e8ca4455-0dc3-4741-8872-3636114938ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e228f01915df633f50b23bf93e892446863c28ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744532"
---
# <a name="using-the-soap-api-in-a-web-application"></a><span data-ttu-id="cd24f-102">Usar la API SOAP en una aplicación web</span><span class="sxs-lookup"><span data-stu-id="cd24f-102">Using the SOAP API in a Web Application</span></span>
  <span data-ttu-id="cd24f-103">Puede tener acceso a la funcionalidad completa del servidor de informes a través de la API SOAP de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="cd24f-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="cd24f-104">Dado que es un servicio web, se puede tener acceso con facilidad a esta API para proporcionar características de informes de empresa para aplicaciones empresariales personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cd24f-104">Because it's a Web service, the SOAP API can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="cd24f-105">Para tener acceso al servicio web del servidor de informes desde una aplicación web, se usa casi el mismo proceso que en el acceso a la API SOAP desde una aplicación para [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="cd24f-105">You access the Report Server Web service from a Web application in much the same way that you access the SOAP API from a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="cd24f-106">Con [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , puede generar una clase de proxy que exponga las propiedades y los métodos del servicio Web del servidor de informes y le permita usar una infraestructura y herramientas conocidas para compilar aplicaciones empresariales en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tecnología.</span><span class="sxs-lookup"><span data-stu-id="cd24f-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Report Server Web service and enables you to use a familiar infrastructure and tools to build business applications on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
 <span data-ttu-id="cd24f-107">El acceso a la funcionalidad de administración de informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se realiza con tanta facilidad desde una aplicación web como desde una aplicación para Windows.</span><span class="sxs-lookup"><span data-stu-id="cd24f-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report management functionality is just as easily accessed from a Web application as from a Windows application.</span></span> <span data-ttu-id="cd24f-108">Desde una aplicación web, puede agregar y quitar los elementos de la base de datos del servidor de informes, establecer la seguridad de los elementos, modificar los elementos de la base de datos del servidor de informes, administrar la programación y la entrega, etcétera.</span><span class="sxs-lookup"><span data-stu-id="cd24f-108">From a Web application, you can add and remove items from the report server database, set item security, modify report server database items, manage scheduling and delivery, and more.</span></span>  
  
## <a name="enabling-impersonation"></a><span data-ttu-id="cd24f-109">Habilitar la suplantación</span><span class="sxs-lookup"><span data-stu-id="cd24f-109">Enabling Impersonation</span></span>  
 <span data-ttu-id="cd24f-110">El primer paso para configurar una aplicación web es habilitar la suplantación desde el cliente de servicios web.</span><span class="sxs-lookup"><span data-stu-id="cd24f-110">The first step in configuring your Web application is to enable impersonation from the Web service client.</span></span> <span data-ttu-id="cd24f-111">Con la suplantación, las aplicaciones de [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] pueden ejecutarse con la identidad del cliente en cuyo el nombre operan.</span><span class="sxs-lookup"><span data-stu-id="cd24f-111">With impersonation, [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications can execute with the identity of the client on whose behalf they are operating.</span></span> [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="cd24f-112">se basa en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) para autenticar al usuario y pasar un token autenticado a la aplicación de [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] o, si no se puede autenticar al usuario, pasar un token sin autenticar.</span><span class="sxs-lookup"><span data-stu-id="cd24f-112">relies on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) to authenticate the user and either pass an authenticated token to the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application or, if unable to authenticate the user, pass an unauthenticated token.</span></span> <span data-ttu-id="cd24f-113">En cualquier caso, la aplicación de [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] suplanta al token que se reciba, si está habilitada la suplantación.</span><span class="sxs-lookup"><span data-stu-id="cd24f-113">In either case, the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application impersonates whichever token is received if impersonation is enabled.</span></span> <span data-ttu-id="cd24f-114">Puede habilitar la suplantación en el cliente modificando el archivo Web.config de la aplicación cliente como sigue:</span><span class="sxs-lookup"><span data-stu-id="cd24f-114">You can enable impersonation on the client, by modifying the Web.config file of the client application as follows:</span></span>  
  
```  
<!-- Web.config file. -->  
<identity impersonate="true"/>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="cd24f-115">De manera predeterminada, la suplantación está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="cd24f-115">Impersonation is disabled by default.</span></span>  
  
 <span data-ttu-id="cd24f-116">Para obtener más información acerca de [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] la suplantación, consulte la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentación del SDK.</span><span class="sxs-lookup"><span data-stu-id="cd24f-116">For more information about [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] impersonation, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="managing-the-report-server-using-soap-api"></a><span data-ttu-id="cd24f-117">Administrar el servidor de informes mediante la API SOAP</span><span class="sxs-lookup"><span data-stu-id="cd24f-117">Managing the Report Server using SOAP API</span></span>  
 <span data-ttu-id="cd24f-118">También puede utilizar la aplicación web para administrar un servidor de informes y su contenido.</span><span class="sxs-lookup"><span data-stu-id="cd24f-118">You can also use your Web application to manage a report server and its contents.</span></span> <span data-ttu-id="cd24f-119">El Administrador de informes, que se incluye con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], es un ejemplo de aplicación web que se genera completamente utilizando [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] y la API SOAP de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="cd24f-119">Report Manager, included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], is an example of a Web application that is completely built using [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] and the Reporting Services SOAP API.</span></span> <span data-ttu-id="cd24f-120">Puede agregar la funcionalidad de administración de informes del Administrador de informes a sus aplicaciones web personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cd24f-120">You can add the report management functionality of Report Manager to your custom Web applications.</span></span> <span data-ttu-id="cd24f-121">Por ejemplo, puede que desee devolver una lista de informes disponibles en la base de datos del servidor de informes y mostrarlos en un [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` control para que los usuarios elijan.</span><span class="sxs-lookup"><span data-stu-id="cd24f-121">For example, you might want to return a list of available reports in the report server database and display them in a [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` control for your users to choose from.</span></span> <span data-ttu-id="cd24f-122">El código siguiente se conecta a la base de datos del servidor de informes y devuelve una lista de los elementos de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="cd24f-122">The following code connects to the report server database and returns a list of items in the report server database.</span></span> <span data-ttu-id="cd24f-123">A continuación, los informes disponibles se agregan a un control Listbox, que muestra la ruta de acceso de cada informe.</span><span class="sxs-lookup"><span data-stu-id="cd24f-123">The available reports are then added to a Listbox control, which displays the path of each report.</span></span>  
  
```vb  
Private Sub Page_Load(sender As Object, e As System.EventArgs)  
   ' Create a Web service proxy object and set credentials  
   Dim rs As New ReportingService2005()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return a list of catalog items in the report server database  
   Dim items As CatalogItem() = rs.ListChildren("/", True)  
  
   ' For each report, display the path of the report in a Listbox  
   Dim ci As CatalogItem  
   For Each ci In  items  
      If ci.Type = ItemTypeEnum.Report Then  
         catalogListBox.Items.Add(ci.Path)  
      End If  
   Next ci  
End Sub ' Page_Load   
```  
  
```csharp  
private void Page_Load(object sender, System.EventArgs e)  
{  
   // Create a Web service proxy object and set credentials  
   ReportingService2005 rs = new ReportingService2005();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return a list of catalog items in the report server database  
   CatalogItem[] items = rs.ListChildren("/", true);  
  
   // For each report, display the path of the report in a Listbox  
   foreach(CatalogItem ci in items)  
   {  
      if (ci.Type == ItemTypeEnum.Report)  
         catalogListBox.Items.Add(ci.Path);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd24f-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd24f-124">See Also</span></span>  
 <span data-ttu-id="cd24f-125">[Creación de aplicaciones con el servicio web y .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="cd24f-125">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="cd24f-126">[Integración de Reporting Services en aplicaciones](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="cd24f-126">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="cd24f-127">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="cd24f-127">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="cd24f-128">Usar la API SOAP en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="cd24f-128">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
  
  
