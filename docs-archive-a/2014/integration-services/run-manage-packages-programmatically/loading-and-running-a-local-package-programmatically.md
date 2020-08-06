---
title: Cargar y ejecutar un paquete local mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Integration Services packages, running
- events [Integration Services], capturing
- packages [Integration Services], running
- loading packages programmatically
- Visual Basic [Integration Services]
- running packages [Integration Services]
- programmatically load and run packages [SSIS]
ms.assetid: 2f9fc1a8-a001-4c54-8c64-63b443725422
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a29faf623c02fea4fd8722c235f595f0fe4492e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744735"
---
# <a name="loading-and-running-a-local-package-programmatically"></a><span data-ttu-id="bc875-102">Cargar y ejecutar un paquete local mediante programación</span><span class="sxs-lookup"><span data-stu-id="bc875-102">Loading and Running a Local Package Programmatically</span></span>
  <span data-ttu-id="bc875-103">Puede ejecutar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] según sea necesario o en momentos predeterminados mediante los métodos descritos en [Ejecución de paquetes](../packages/run-integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="bc875-103">You can run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages as needed or at predetermined times by using the methods described in [Running Packages](../packages/run-integration-services-ssis-packages.md).</span></span> <span data-ttu-id="bc875-104">Sin embargo, con solo unas líneas de código, también puede ejecutar un paquete desde una aplicación personalizada como una aplicación Windows Forms, una aplicación de consola, un formulario Web Forms o servicio web ASP.NET o un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc875-104">However, with only a few lines of code, you can also run a package from a custom application such as a Windows Forms application, a console application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
 <span data-ttu-id="bc875-105">En este tema se describe:</span><span class="sxs-lookup"><span data-stu-id="bc875-105">This topic discusses:</span></span>  
  
-   <span data-ttu-id="bc875-106">Cargar un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="bc875-106">Loading a package programmatically</span></span>  
  
-   <span data-ttu-id="bc875-107">Ejecutar un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="bc875-107">Running a package programmatically</span></span>  
  
 <span data-ttu-id="bc875-108">Todos los métodos utilizados en este tema para cargar y ejecutar paquetes requieren una referencia al ensamblado `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="bc875-108">All of the methods used in this topic to load and run packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="bc875-109">Después de agregar la referencia en un proyecto nuevo, importe el espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> con una instrucción `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="bc875-109">After adding the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="loading-a-package-programmatically"></a><span data-ttu-id="bc875-110">Cargar un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="bc875-110">Loading a Package Programmatically</span></span>  
 <span data-ttu-id="bc875-111">Para cargar un paquete mediante programación en el equipo local, tanto si el paquete está almacenado localmente como si lo está de forma remota, llame a uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc875-111">To load a package programmatically on the local computer, whether the package is stored locally or remotely, call one of the following methods:</span></span>  
  
|<span data-ttu-id="bc875-112">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="bc875-112">Storage Location</span></span>|<span data-ttu-id="bc875-113">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="bc875-113">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="bc875-114">Archivo</span><span class="sxs-lookup"><span data-stu-id="bc875-114">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>|  
|<span data-ttu-id="bc875-115">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="bc875-115">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bc875-116">Los métodos de la clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> para trabajar con el almacén de paquetes SSIS solamente admiten ".", localhost o el nombre del servidor local.</span><span class="sxs-lookup"><span data-stu-id="bc875-116">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="bc875-117">No puede utilizar "(local)".</span><span class="sxs-lookup"><span data-stu-id="bc875-117">You cannot use "(local)".</span></span>  
  
## <a name="running-a-package-programmatically"></a><span data-ttu-id="bc875-118">Ejecutar un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="bc875-118">Running a Package Programmatically</span></span>  
 <span data-ttu-id="bc875-119">Al desarrollar una aplicación personalizada en código administrado que ejecuta un paquete en el equipo local, se requiere el enfoque siguiente.</span><span class="sxs-lookup"><span data-stu-id="bc875-119">Developing a custom application in managed code that runs a package on the local computer requires the following approach.</span></span> <span data-ttu-id="bc875-120">Los pasos resumidos aquí se muestran en la aplicación de consola de ejemplo que figura a continuación.</span><span class="sxs-lookup"><span data-stu-id="bc875-120">The steps summarized here are demonstrated in the sample console application that follows.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically"></a><span data-ttu-id="bc875-121">Para ejecutar un paquete mediante programación en el equipo local</span><span class="sxs-lookup"><span data-stu-id="bc875-121">To run a package on the local computer programmatically</span></span>  
  
1.  <span data-ttu-id="bc875-122">Inicie el entorno de desarrollo de Visual Studio y cree una nueva aplicación en su lenguaje de desarrollo preferido.</span><span class="sxs-lookup"><span data-stu-id="bc875-122">Start the Visual Studio development environment, and create a new application in your preferred development language.</span></span> <span data-ttu-id="bc875-123">En este ejemplo se utiliza una aplicación de consola; sin embargo, también puede ejecutar un paquete de una aplicación Windows Forms, un formulario Web Forms o servicio web ASP.NET o un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc875-123">This example uses a console application; however you can also run a package from a Windows Forms application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
2.  <span data-ttu-id="bc875-124">En el menú **Proyecto**, haga clic en **Agregar referencia** y agregue una referencia a **Microsoft.SqlServer.ManagedDTS.dll**.</span><span class="sxs-lookup"><span data-stu-id="bc875-124">On the **Project** menu, click **Add Reference** and add a reference to **Microsoft.SqlServer.ManagedDTS.dll**.</span></span> <span data-ttu-id="bc875-125">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc875-125">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="bc875-126">Use la `Imports` instrucción Visual Basic o la instrucción de C# `using` para importar el espacio de nombres **Microsoft. SqlServer. DTS. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="bc875-126">Use the Visual Basic `Imports` statement or the C# `using` statement to import the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
4.  <span data-ttu-id="bc875-127">Agregue el código siguiente en la rutina principal.</span><span class="sxs-lookup"><span data-stu-id="bc875-127">Add the following code in the main routine.</span></span> <span data-ttu-id="bc875-128">La aplicación de consola completada se debe parecer al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bc875-128">The completed console application should look like the following example.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc875-129">En el código de ejemplo se muestra cómo cargar el paquete desde el sistema de archivos mediante el método <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc875-129">The sample code demonstrates loading the package from the file system by using the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A> method.</span></span> <span data-ttu-id="bc875-130">No obstante, también puede cargar el paquete desde la base de datos MSDB mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> o bien desde el almacén de paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc875-130">However you can also load the package from the MSDB database by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> method, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> method.</span></span>  
  
5.  <span data-ttu-id="bc875-131">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bc875-131">Run the project.</span></span> <span data-ttu-id="bc875-132">En el código de ejemplo se ejecuta el paquete de ejemplo CalculatedColumns que se instala con los ejemplos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc875-132">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="bc875-133">El resultado de la ejecución del paquete se muestra en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="bc875-133">The result of package execution is displayed in the console window.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="bc875-134">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc875-134">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, Nothing)  
    pkgResults = pkg.Execute()  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, null);  
      pkgResults = pkg.Execute();  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
## <a name="capturing-events-from-a-running-package"></a><span data-ttu-id="bc875-135">Capturar eventos de un paquete en ejecución</span><span class="sxs-lookup"><span data-stu-id="bc875-135">Capturing Events from a Running Package</span></span>  
 <span data-ttu-id="bc875-136">Al ejecutar un paquete mediante programación tal como se muestra en el ejemplo anterior, también puede capturar los errores y otros eventos que se producen cuando se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="bc875-136">When you run a package programmatically as shown in the preceding sample, you may also want to capture errors and other events that occur as the package executes.</span></span> <span data-ttu-id="bc875-137">Para ello, agregue una clase que herede de la clase <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> y pase una referencia a dicha clase al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bc875-137">You can accomplish this by adding a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class, and by passing a reference to that class when you load the package.</span></span> <span data-ttu-id="bc875-138">Aunque en el ejemplo siguiente solamente se captura el evento <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A>, hay muchos otros eventos que la clase <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> permite capturar.</span><span class="sxs-lookup"><span data-stu-id="bc875-138">Although the following example captures only the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A> event, there are many other events that the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class lets you capture.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically-and-capture-package-events"></a><span data-ttu-id="bc875-139">Para ejecutar un paquete mediante programación en el equipo local y capturar los eventos del paquete</span><span class="sxs-lookup"><span data-stu-id="bc875-139">To run a package on the local computer programmatically and capture package events</span></span>  
  
1.  <span data-ttu-id="bc875-140">Siga los pasos del ejemplo anterior para crear un proyecto para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bc875-140">Follow the steps in the preceding example to create a project for this example.</span></span>  
  
2.  <span data-ttu-id="bc875-141">Agregue el código siguiente en la rutina principal.</span><span class="sxs-lookup"><span data-stu-id="bc875-141">Add the following code in the main routine.</span></span> <span data-ttu-id="bc875-142">La aplicación de consola completada se debe parecer al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bc875-142">The completed console application should look like the following example.</span></span>  
  
3.  <span data-ttu-id="bc875-143">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bc875-143">Run the project.</span></span> <span data-ttu-id="bc875-144">En el código de ejemplo se ejecuta el paquete de ejemplo CalculatedColumns que se instala con los ejemplos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc875-144">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="bc875-145">El resultado de la ejecución del paquete se muestra en la ventana de la consola, junto con cualquier error que se produzca.</span><span class="sxs-lookup"><span data-stu-id="bc875-145">The result of package execution is displayed in the console window, along with any errors that occur.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="bc875-146">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc875-146">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    Dim eventListener As New EventListener()  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, eventListener)  
    pkgResults = pkg.Execute(Nothing, Nothing, eventListener, Nothing, Nothing)  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
  
Class EventListener  
  Inherits DefaultEvents  
  
  Public Overrides Function OnError(ByVal source As Microsoft.SqlServer.Dts.Runtime.DtsObject, _  
    ByVal errorCode As Integer, ByVal subComponent As String, ByVal description As String, _  
    ByVal helpFile As String, ByVal helpContext As Integer, _  
    ByVal idofInterfaceWithError As String) As Boolean  
  
    ' Add application-specific diagnostics here.  
    Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description)  
    Return False  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppWithEventsCS  
{  
  class MyEventListener : DefaultEvents  
  {  
    public override bool OnError(DtsObject source, int errorCode, string subComponent,   
      string description, string helpFile, int helpContext, string idofInterfaceWithError)  
    {  
      // Add application-specific diagnostics here.  
      Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description);  
      return false;  
    }  
  }  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      MyEventListener eventListener = new MyEventListener();  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, eventListener);  
      pkgResults = pkg.Execute(null, null, eventListener, null, null);  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
<span data-ttu-id="bc875-147">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bc875-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bc875-148">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="bc875-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bc875-149">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="bc875-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bc875-150">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="bc875-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc875-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc875-151">See Also</span></span>  
 <span data-ttu-id="bc875-152">[Descripción de las diferencias entre la ejecución local y remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="bc875-152">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="bc875-153">[Cargar y ejecutar un paquete remoto mediante programación](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="bc875-153">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="bc875-154">Cargar la salida de un paquete local</span><span class="sxs-lookup"><span data-stu-id="bc875-154">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
