---
title: Dar formato a un archivo de script de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], formats
- formats [Reporting Services], script files
ms.assetid: 85a207dd-4e0f-4d40-a41e-0c75f65d719c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c98a2f6561c3242fec34f7ca11c8304286ccebae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746137"
---
# <a name="format-a-reporting-services-script-file"></a><span data-ttu-id="8e974-102">Dar formato a un archivo de script de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8e974-102">Format a Reporting Services Script File</span></span>
  <span data-ttu-id="8e974-103">Un script de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] es un archivo de código de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET, escrito frente a un proxy generado en el Lenguaje de descripción de servicios web (WSDL), que define la API de SOAP de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8e974-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET code file, written against a proxy that is built on Web Service Description Language (WSDL), which defines the Reporting Services SOAP API.</span></span> <span data-ttu-id="8e974-104">Un archivo de script se almacena como archivo de texto Unicode o UTF-8 con la extensión .rss.</span><span class="sxs-lookup"><span data-stu-id="8e974-104">A script file is stored as a Unicode or UTF-8 text file with the extension .rss.</span></span>  
  
 <span data-ttu-id="8e974-105">El archivo de script actúa como módulo [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] y contiene procedimientos definidos por el usuario y variables de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="8e974-105">The script file acts as a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] module and can contain user-defined procedures and module-level variables.</span></span> <span data-ttu-id="8e974-106">Para que el archivo de script se ejecute correctamente, debe contener un procedimiento Main.</span><span class="sxs-lookup"><span data-stu-id="8e974-106">For the script file to run successfully, it must contain a Main procedure.</span></span> <span data-ttu-id="8e974-107">El procedimiento Main es el primer procedimiento al que se tiene acceso cuando se ejecuta su archivo de script.</span><span class="sxs-lookup"><span data-stu-id="8e974-107">The Main procedure is the first procedure that is accessed when your script file runs.</span></span> <span data-ttu-id="8e974-108">Main es donde puede agregar sus operaciones del servicio web y ejecutar sus subprocedimientos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8e974-108">Main is where you can add your Web service operations and run your user defined subprocedures.</span></span> <span data-ttu-id="8e974-109">El código siguiente crea un procedimiento Main:</span><span class="sxs-lookup"><span data-stu-id="8e974-109">The following code creates a Main procedure:</span></span>  
  
```  
Public Sub Main()  
    ' Your code goes here.  
End Sub  
```  
  
 <span data-ttu-id="8e974-110">El entorno de scripts se conecta automáticamente al servidor de informes, crea la clase de proxy web y genera una variable de referencia (*rs*) al objeto proxy del servicio web.</span><span class="sxs-lookup"><span data-stu-id="8e974-110">The script environment automatically connects to the report server, creates the Web proxy class, and generates a reference variable (*rs*) to the Web service proxy object.</span></span> <span data-ttu-id="8e974-111">Las instrucciones individuales que cree solo tienen que hacer referencia a la variable a nivel del módulo *rs* para realizar cualquiera de las operaciones del servicio web que están disponibles en la biblioteca del servicio web.</span><span class="sxs-lookup"><span data-stu-id="8e974-111">Individual statements that you create need only refer to the *rs* module-level variable to perform any of the Web service operations that are available in the Web service library.</span></span> <span data-ttu-id="8e974-112">El código [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] siguiente llama al método <xref:ReportService2010.ReportingService2010.ListChildren%2A> del servicio web desde dentro de un archivo de script:</span><span class="sxs-lookup"><span data-stu-id="8e974-112">The following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code calls the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method from within a script file:</span></span>  
  
```  
Public Sub Main()  
    Dim items() As CatalogItem  
    items = rs.ListChildren("/", True)  
  
    Dim item As CatalogItem  
    For Each item In items  
        Console.WriteLine(item.Name)  
    Next item  
End Sub   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e974-113">Las credenciales de usuario se administran por el entorno de script y pasan a través de los argumentos del símbolo del sistema mediante el uso de RS.exe.</span><span class="sxs-lookup"><span data-stu-id="8e974-113">User credentials are managed by the script environment and passed through command prompt arguments through the use of RS.exe.</span></span> <span data-ttu-id="8e974-114">Aunque puede usar la variable *rs* para establecer la autenticación del servicio web, se recomienda que use el entorno de script.</span><span class="sxs-lookup"><span data-stu-id="8e974-114">Although you can use the *rs* variable to set the authentication of the Web service, it is recommended that you use the script environment.</span></span> <span data-ttu-id="8e974-115">No tiene que autenticar el servicio web en el propio archivo de script.</span><span class="sxs-lookup"><span data-stu-id="8e974-115">You do not need to authenticate the Web service in the script file itself.</span></span> <span data-ttu-id="8e974-116">Para más información sobre la autenticación del entorno de scripts, vea [Utilidad RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8e974-116">For more information about authenticating the script environment, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span>  
  
 <span data-ttu-id="8e974-117">No declara espacios de nombres dentro del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="8e974-117">You do not declare namespaces within the script file.</span></span> <span data-ttu-id="8e974-118">El entorno de scripting hace que haya varios espacios de nombres de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] útiles disponibles: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml** y **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="8e974-118">The scripting environment makes several useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces available to you: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml**, and **System.IO**.</span></span>  
  
 <span data-ttu-id="8e974-119">Para obtener ejemplos del script, vea [Muestras de productos de SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="8e974-119">For script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e974-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e974-120">See Also</span></span>  
 <span data-ttu-id="8e974-121">[Servicio web del servidor de informes](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="8e974-121">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="8e974-122">[Referencia técnica &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8e974-122">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="8e974-123">Utilidad RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e974-123">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
