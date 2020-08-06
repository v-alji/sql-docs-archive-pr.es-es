---
title: Crear el proxy del servicio web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: b1217843-8d3d-49f3-a0d2-d35b0db5b2df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d080b96fa29e906c044561a684d58275af9f61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745027"
---
# <a name="creating-the-web-service-proxy"></a><span data-ttu-id="61d2d-102">Creación del proxy del servicio web</span><span class="sxs-lookup"><span data-stu-id="61d2d-102">Creating the Web Service Proxy</span></span>
  <span data-ttu-id="61d2d-103">Un cliente y un servicio web pueden comunicarse utilizando mensajes SOAP, que encapsulan los parámetros de entrada y salida como XML.</span><span class="sxs-lookup"><span data-stu-id="61d2d-103">A client and a Web service can communicate using SOAP messages, which encapsulate the input and output parameters as XML.</span></span> <span data-ttu-id="61d2d-104">Una clase de proxy asigna los parámetros a los elementos XML y, a continuación, envía los mensajes SOAP a través de una red.</span><span class="sxs-lookup"><span data-stu-id="61d2d-104">A proxy class maps parameters to XML elements and then sends the SOAP messages over a network.</span></span> <span data-ttu-id="61d2d-105">De esta manera, la clase de proxy le evita tener que comunicarse con el servicio web en el nivel SOAP y le permite invocar a los métodos de servicio web en cualquier entorno de desarrollo que admita SOAP y proxys de servicio web.</span><span class="sxs-lookup"><span data-stu-id="61d2d-105">In this way, the proxy class frees you from having to communicate with the Web service at the SOAP level and allows you to invoke Web service methods in any development environment that supports SOAP and Web service proxies.</span></span>  
  
 <span data-ttu-id="61d2d-106">Hay dos maneras de agregar una clase de proxy a su proyecto de desarrollo mediante [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] : con la herramienta WSDL en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] y agregando una referencia Web en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61d2d-106">There are two ways to add a proxy class to your development project using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: with the WSDL tool in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], and by adding a Web reference in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="61d2d-107">En las secciones siguientes se explica esta cuestión con mayor detalle.</span><span class="sxs-lookup"><span data-stu-id="61d2d-107">The following sections discuss this subject in further detail.</span></span>  
  
## <a name="adding-the-proxy-using-the-wsdl-tool"></a><span data-ttu-id="61d2d-108">Agregar el proxy mediante la herramienta WSDL</span><span class="sxs-lookup"><span data-stu-id="61d2d-108">Adding the Proxy Using the WSDL Tool</span></span>  
 <span data-ttu-id="61d2d-109">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK incluye la herramienta Lenguaje de descripción de servicios web (Wsdl.exe), que permite generar un proxy de servicio web para usarse en el entorno de desarrollo de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61d2d-109">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK includes the Web Services Description Language tool (Wsdl.exe), which enables you to generate a Web service proxy for use in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] development environment.</span></span> <span data-ttu-id="61d2d-110">La forma más común de crear un proxy de cliente en lenguajes que admiten servicios web (actualmente C# y [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ) es usar la herramienta WSDL.</span><span class="sxs-lookup"><span data-stu-id="61d2d-110">The most common way to create a client proxy in languages that support Web services (currently C# and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) is to use the WSDL tool.</span></span>  
  
 <span data-ttu-id="61d2d-111">**Para agregar una clase de proxy a un proyecto mediante Wsdl.exe**</span><span class="sxs-lookup"><span data-stu-id="61d2d-111">**To add a proxy class to your project using Wsdl.exe**</span></span>  
  
1.  <span data-ttu-id="61d2d-112">Desde un símbolo del sistema, utilice Wsdl.exe para crear una clase de proxy, especificando, como mínimo, la dirección URL del servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="61d2d-112">From a command prompt, use Wsdl.exe to create a proxy class, specifying (at a minimum) the URL to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="61d2d-113">Por ejemplo, la siguiente instrucción del símbolo del sistema especifica una dirección URL para el extremo de administración del servicio web del servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="61d2d-113">For example, the following command prompt statement specifies a URL for the management endpoint of the Report Server Web service:</span></span>  
  
    ```  
    wsdl /language:CS /n:"Microsoft.SqlServer.ReportingServices2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="61d2d-114">La herramienta WSDL acepta varios argumentos de símbolo del sistema para generar un proxy.</span><span class="sxs-lookup"><span data-stu-id="61d2d-114">The WSDL tool accepts a number of command-prompt arguments for generating a proxy.</span></span> <span data-ttu-id="61d2d-115">El ejemplo anterior especifica el lenguaje C# y un espacio de nombres sugerido para utilizar en el proxy (para evitar el conflicto de nombres si se usa más de un extremo de servicios web), y genera un archivo de C# denominado ReportingService2010.cs.</span><span class="sxs-lookup"><span data-stu-id="61d2d-115">The preceding example specifies the language C#, a suggested namespace to use in the proxy (to prevent name collision if using more than one Web service endpoint), and generates a C# file called ReportingService2010.cs.</span></span> <span data-ttu-id="61d2d-116">Si el ejemplo hubiera especificado [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], el ejemplo habría generado un archivo de proxy con el nombre ReportingService2010.vb.</span><span class="sxs-lookup"><span data-stu-id="61d2d-116">If the example had specified [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], the example would have generated a proxy file with the name ReportingService2010.vb.</span></span> <span data-ttu-id="61d2d-117">Este archivo se crea en el directorio desde el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="61d2d-117">This file is created in the directory from which you run the command.</span></span>  
  
2.  <span data-ttu-id="61d2d-118">Compile la clase de proxy en un archivo de ensamblado (con la extensión .dll) y haga referencia a él en el proyecto o agregue la clase como un elemento de proyecto.</span><span class="sxs-lookup"><span data-stu-id="61d2d-118">Compile the proxy class into an assembly file (with the extension .dll) and reference it in your project, or add the class as a project item.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61d2d-119">Al agregar manualmente una clase de proxy al proyecto, tiene que agregar una referencia al archivo System.Web.Services.dll.</span><span class="sxs-lookup"><span data-stu-id="61d2d-119">When you add a proxy class to your project manually, you need to add a reference to System.Web.Services.dll.</span></span> <span data-ttu-id="61d2d-120">Si agrega el proxy utilizando una referencia web en Visual Studio .NET, la referencia se crea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="61d2d-120">If you add the proxy using a Web reference in Visual Studio .NET, the reference is automatically created for you.</span></span> <span data-ttu-id="61d2d-121">Para obtener más información, vea "Agregar el proxy usando una referencia web en Visual Studio" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="61d2d-121">For more information, see "Adding the Proxy Using a Web Reference in Visual Studio" later in this topic.</span></span>  
  
     <span data-ttu-id="61d2d-122">Después de agregar la clase de proxy como un elemento al proyecto, el archivo asociado aparece en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="61d2d-122">After you add the proxy class as an item to your project, the associated file appears in Solution Explorer.</span></span>  
  
3.  <span data-ttu-id="61d2d-123">Para llamar al servicio mediante programación, cree una instancia de la clase de proxy.</span><span class="sxs-lookup"><span data-stu-id="61d2d-123">To call the service programmatically, create an instance of the proxy class.</span></span>  
  
     <span data-ttu-id="61d2d-124">El ejemplo de código siguiente muestra la sintaxis para crear una instancia de la clase de proxy <xref:ReportService2010.ReportingService2010> en un proyecto:</span><span class="sxs-lookup"><span data-stu-id="61d2d-124">The following code example shows the syntax for creating an instance of the <xref:ReportService2010.ReportingService2010> proxy class in a project:</span></span>  
  
```vb  
Dim service As New ReportingService2010()  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
  
```  
  
 <span data-ttu-id="61d2d-125">Para obtener más información sobre la herramienta Wsdl.exe, incluida su sintaxis completa, vea "Herramienta Lenguaje de descripción de servicios web" en la documentación de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="61d2d-125">For more information about the Wsdl.exe tool, including its full syntax, see "Web Services Description Language Tool" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span> <span data-ttu-id="61d2d-126">Para obtener una explicación completa de los proxys del servicio web, vea "Crear un proxy de servicio web XML" en la documentación de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="61d2d-126">For a full explanation of Web service proxies, see "Creating an XML Web Service Proxy" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="adding-the-proxy-using-a-web-reference-in-visual-studio"></a><span data-ttu-id="61d2d-127">Agregar el proxy usando una referencia web en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="61d2d-127">Adding the Proxy Using a Web Reference in Visual Studio</span></span>  
 <span data-ttu-id="61d2d-128">Una referencia web permite a un proyecto usar uno o más servicios web.</span><span class="sxs-lookup"><span data-stu-id="61d2d-128">A Web reference enables a project to consume one or more Web services.</span></span> [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] <span data-ttu-id="61d2d-129">permite a los usuarios agregar referencias de servicio web a los proyectos siguiendo unos pasos simples.</span><span class="sxs-lookup"><span data-stu-id="61d2d-129">enables users to add Web service references to projects by following a few simple steps.</span></span>  
  
 <span data-ttu-id="61d2d-130">**Para agregar una referencia web a un proyecto**</span><span class="sxs-lookup"><span data-stu-id="61d2d-130">**To add a Web reference to a project**</span></span>  
  
1.  <span data-ttu-id="61d2d-131">En el **Explorador de soluciones**, seleccione el proyecto que consumirá el servicio web.</span><span class="sxs-lookup"><span data-stu-id="61d2d-131">In **Solution Explorer**, select the project that will consume the Web service.</span></span>  
  
2.  <span data-ttu-id="61d2d-132">En el menú **Proyecto**, haga clic en **Agregar referencia web**.</span><span class="sxs-lookup"><span data-stu-id="61d2d-132">On the **Project** menu, click **Add Web Reference**.</span></span>  
  
     <span data-ttu-id="61d2d-133">Se abrirá el cuadro de diálogo **Agregar referencia web**.</span><span class="sxs-lookup"><span data-stu-id="61d2d-133">The **Add Web Reference** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="61d2d-134">En el campo **Dirección URL**, escriba la ruta de acceso completa al servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="61d2d-134">In the **URL** field, enter the complete path to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="61d2d-135">Una dirección URL simplificada para el extremo de ejecución de informes del servicio web del servidor de informes podría ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="61d2d-135">A simplified URL for the report execution endpoint of the Report Server Web service might look like this:</span></span>  
  
    ```  
    http://<Server Name>/reportserver/reportexecution2005.asmx  
    ```  
  
     <span data-ttu-id="61d2d-136">La dirección URL contiene el dominio en el que se implementa el servicio web del servidor de informes, el nombre de la carpeta que contiene el servicio y el nombre del archivo de detección para el servicio.</span><span class="sxs-lookup"><span data-stu-id="61d2d-136">The URL contains the domain in which the Report Server Web service is deployed, the name of the folder containing the service, and the name of the discovery file for the service.</span></span> <span data-ttu-id="61d2d-137">Para obtener una descripción completa de los distintos elementos de dirección URL, vea [Acceso a la API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="61d2d-137">For a complete description of the different URL elements, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
     <span data-ttu-id="61d2d-138">Una descripción de los métodos y propiedades proporcionada por el servicio web aparece en el panel Explorador a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="61d2d-138">A description of the methods and properties provided by the Web service appears in the Browser pane on the left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61d2d-139">Para más información sobre los elementos asociados al servicio web del servidor de informes, vea [Métodos de servicio web del servidor de informes](../methods/report-server-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="61d2d-139">For more information about the items associated with the Report Server Web service, see [Report Server Web Service Methods](../methods/report-server-web-service-methods.md).</span></span>  
  
4.  <span data-ttu-id="61d2d-140">Compruebe que su proyecto puede utilizar el servicio web del servidor de informes y que tiene el permiso adecuado para tener acceso al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="61d2d-140">Verify that your project can use the Report Server Web service, and that you have appropriate permission to access the report server.</span></span>  
  
5.  <span data-ttu-id="61d2d-141">En el campo **Nombre de referencia web**, escriba el nombre que vaya a utilizar en el código para obtener acceso mediante programación al servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="61d2d-141">In the **Web reference name** field, enter a name that you will use in your code to access the Report Server Web service programmatically.</span></span>  
  
6.  <span data-ttu-id="61d2d-142">Seleccione el botón **Agregar referencia** para crear una referencia en la aplicación para el servicio web.</span><span class="sxs-lookup"><span data-stu-id="61d2d-142">Select the **Add Reference** button to create a reference in your application to the Web service.</span></span>  
  
     <span data-ttu-id="61d2d-143">La nueva referencia aparece en el **Explorador de soluciones** bajo el nodo Referencias web para el proyecto activo, denominado tal y como se especifica en el campo **Nombre de referencia web**.</span><span class="sxs-lookup"><span data-stu-id="61d2d-143">The new reference appears in **Solution Explorer** under the Web References node for the active project, named as specified in the **Web reference name** field.</span></span>  
  
7.  <span data-ttu-id="61d2d-144">En el **Explorador de soluciones**, expanda la carpeta Referencias web para anotar el espacio de nombres de las clases de referencias web que están disponibles para los elementos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="61d2d-144">In **Solution Explorer**, expand the Web References folder to note the namespace for the Web reference classes that are available to the items in your project.</span></span>  
  
     <span data-ttu-id="61d2d-145">Después de agregar una referencia web al proyecto, los archivos asociados se muestran en una carpeta dentro de la carpeta Referencias web del **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="61d2d-145">After adding a Web reference to your project, the associated files are displayed in a folder within the Web References folder of **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="61d2d-146">Después de agregar la referencia web, utilice la sintaxis siguiente para crear una instancia de la clase de proxy:</span><span class="sxs-lookup"><span data-stu-id="61d2d-146">After you add the Web reference, use the following syntax to create an instance of the proxy class:</span></span>  
  
```vb  
Dim rs As New myNamespace.myReferenceName.ReportExecutionService()  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
myNamespace.myReferenceName.ReportExecutionService rs = new myNamespace.myReferenceName.ReportExecutionService();  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
```  
  
 <span data-ttu-id="61d2d-147">También puede agregar una directiva **using** (**Import** en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) a la referencia del servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="61d2d-147">You can also add a **using** (**Import** in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) directive to the Report Server Web service reference.</span></span> <span data-ttu-id="61d2d-148">Si utiliza esta directiva, no es necesario utilizar nombres completos para los tipos en el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="61d2d-148">If you use this directive, you do not need to fully qualify the types in the namespace.</span></span> <span data-ttu-id="61d2d-149">En ello, agregue el siguiente código al archivo:</span><span class="sxs-lookup"><span data-stu-id="61d2d-149">To do this, add the following code to your file:</span></span>  
  
```vb  
Import myNamespace.myReferenceName  
```  
  
```csharp  
using myNamespace.myReferenceName;  
```  
  
## <a name="see-also"></a><span data-ttu-id="61d2d-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61d2d-150">See Also</span></span>  
 <span data-ttu-id="61d2d-151">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="61d2d-151">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="61d2d-152">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="61d2d-152">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="61d2d-153">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="61d2d-153">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
