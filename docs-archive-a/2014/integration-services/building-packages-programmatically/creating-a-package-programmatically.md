---
title: Crear un paquete mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: e44bcc70-32d3-43e8-a84b-29aef819d5d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1159784fc95dd86d9d33c4354291cc7c52812982
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745945"
---
# <a name="creating-a-package-programmatically"></a><span data-ttu-id="da276-102">Crear un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="da276-102">Creating a Package Programmatically</span></span>
  <span data-ttu-id="da276-103">El objeto <xref:Microsoft.SqlServer.Dts.Runtime.Package> es el contenedor de nivel superior para todos los demás objetos de una solución de proyecto [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da276-103">The <xref:Microsoft.SqlServer.Dts.Runtime.Package> object is the top-level container for all other objects in an [!INCLUDE[ssIS](../../includes/ssis-md.md)] project solution.</span></span> <span data-ttu-id="da276-104">Al igual que el contenedor de nivel superior, el paquete es el primer objeto creado y los objetos subsiguientes se agregan a él y, a continuación, se ejecutan dentro del contexto del paquete.</span><span class="sxs-lookup"><span data-stu-id="da276-104">As the top-level container, the package is the first object created, and subsequent objects are added to it, and then executed within the context of the package.</span></span> <span data-ttu-id="da276-105">El propio paquete no mueve o transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="da276-105">The package itself does not move or transform data.</span></span> <span data-ttu-id="da276-106">El paquete se basa en las tareas que contiene para realizar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="da276-106">The package relies on the tasks it contains to perform the work.</span></span> <span data-ttu-id="da276-107">Las tareas realizan la mayor parte del trabajo que realiza un paquete y definen la funcionalidad de un paquete.</span><span class="sxs-lookup"><span data-stu-id="da276-107">Tasks perform most of the work performed by a package, and define the functionality of a package.</span></span> <span data-ttu-id="da276-108">Un paquete se crea y ejecuta con solo tres líneas de código, pero se agregan varias tareas y los objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> para proporcionar una funcionalidad adicional al paquete.</span><span class="sxs-lookup"><span data-stu-id="da276-108">A package is created and executed with just three lines of code, but various tasks and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects are added to give additional functionality to your package.</span></span> <span data-ttu-id="da276-109">En esta sección se describe cómo crear un paquete mediante programación.</span><span class="sxs-lookup"><span data-stu-id="da276-109">This section discusses how to programmatically create a package.</span></span> <span data-ttu-id="da276-110">No proporciona información acerca de cómo crear las tareas o <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="da276-110">It does not provide information about how to create the tasks or the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span> <span data-ttu-id="da276-111">Estos temas se tratan en secciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="da276-111">These are covered in later sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da276-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da276-112">Example</span></span>  
 <span data-ttu-id="da276-113">Para escribir código mediante el IDE de Visual Studio, se exige una referencia a Microsoft.SqlServer.ManagedDTS.DLL para crear una instrucción `using` (`Imports` en Visual Basic .NET) a Microsoft.SqlServer.Dts.Runtime.</span><span class="sxs-lookup"><span data-stu-id="da276-113">To write code using the Visual Studio IDE, a reference to Microsoft.SqlServer.ManagedDTS.DLL is required in order to create a `using` statement (`Imports` in Visual Basic .NET) to the Microsoft.SqlServer.Dts.Runtime.</span></span> <span data-ttu-id="da276-114">En el ejemplo de código siguiente se muestra cómo crear un paquete vacío.</span><span class="sxs-lookup"><span data-stu-id="da276-114">The following code sample demonstrates creating an empty package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package;  
      package = new Package();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package  
    package = New Package  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="da276-115">Para compilar y ejecutar el ejemplo, presione F5 en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="da276-115">To compile and run the sample, press F5 in Visual Studio.</span></span> <span data-ttu-id="da276-116">Para compilar el código mediante el compilador de C#, **csc.exe**, en el símbolo del sistema para compilar, use las siguientes referencias de comando y archivo, reemplazando *\<filename>* por el nombre del archivo .cs o .vb, y dándole el *\<outputfilename>* que elija.</span><span class="sxs-lookup"><span data-stu-id="da276-116">To build the code using the C# compiler, **csc.exe**, at the command prompt to compile, use the following command and file references, replacing the *\<filename>* with the name of the .cs or .vb file, and giving it an *\<outputfilename>* of your choice.</span></span>  
  
 <span data-ttu-id="da276-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="da276-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="da276-118">Para compilar el código mediante el compilador de Visual Basic .NET, **vbc.exe**, en el símbolo del sistema que se debe compilar, use las siguientes referencias de comando y archivo.</span><span class="sxs-lookup"><span data-stu-id="da276-118">To build the code using the Visual Basic .NET compiler, **vbc.exe**, at the command prompt to compile, use the following command and file references.</span></span>  
  
 <span data-ttu-id="da276-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="da276-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="da276-120">También puede crear un paquete cargando un paquete existente que se guardó en disco, en el sistema de archivos o en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da276-120">You can also create a package by loading an existing package that was saved on disk, in the file system, or to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da276-121">La diferencia es que primero se crea el objeto <xref:Microsoft.SqlServer.Dts.Runtime.Application> y, a continuación, uno de los métodos sobrecargados de la aplicación rellena el objeto de paquete: `LoadPackage` para archivos planos, `LoadFromSQLServer` para archivos guardados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> para los paquetes guardados al sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="da276-121">The difference is that the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object is first created, and then the package object is filled by one of the Application's overloaded methods: `LoadPackage` for flat files, `LoadFromSQLServer` for packages saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> for packages saved to the file system.</span></span> <span data-ttu-id="da276-122">En el ejemplo siguiente se carga un paquete existente desde el disco y, a continuación, se muestran varias propiedades en el paquete.</span><span class="sxs-lookup"><span data-stu-id="da276-122">The following example loads an existing package from disk, and then views several properties on the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class ApplicationTests  
  {  
    static void Main(string[] args)  
    {  
      // The variable pkg points to the location of the  
      // ExecuteProcess package sample that was installed with  
      // the SSIS samples.  
      string pkg = @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx";  
  
      Application app = new Application();  
      Package p = app.LoadPackage(pkg, null);  
  
      // Now that the package is loaded, we can query on  
      // its properties.  
      int n = p.Configurations.Count;  
      DtsProperty p2 = p.Properties["VersionGUID"];  
      DTSProtectionLevel pl = p.ProtectionLevel;  
  
      Console.WriteLine("Number of configurations = " + n.ToString());  
      Console.WriteLine("VersionGUID = " + (string)p2.GetValue(p));  
      Console.WriteLine("ProtectionLevel = " + pl.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module ApplicationTests  
  
  Sub Main()  
  
    ' The variable pkg points to the location of the  
    ' ExecuteProcess package sample that was installed with  
    ' the SSIS samples.  
    Dim pkg As String = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx"  
  
    Dim app As Application = New Application()  
    Dim p As Package = app.LoadPackage(pkg, Nothing)  
  
    ' Now that the package is loaded, we can query on  
    ' its properties.  
    Dim n As Integer = p.Configurations.Count  
    Dim p2 As DtsProperty = p.Properties("VersionGUID")  
    Dim pl As DTSProtectionLevel = p.ProtectionLevel  
  
    Console.WriteLine("Number of configurations = " & n.ToString())  
    Console.WriteLine("VersionGUID = " & CType(p2.GetValue(p), String))  
    Console.WriteLine("ProtectionLevel = " & pl.ToString())  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="da276-123">**Salida del ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="da276-123">**Sample Output:**</span></span>  
  
 `Number of configurations = 2`  
  
 `VersionGUID = {09016682-89B8-4406-AAC9-AF1E527FF50F}`  
  
 `ProtectionLevel = DontSaveSensitive`  
  
## <a name="external-resources"></a><span data-ttu-id="da276-124">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="da276-124">External Resources</span></span>  
  
-   <span data-ttu-id="da276-125">Entrada del blog sobre el [ejemplo de API, origen OleDB y destino OleDB](https://go.microsoft.com/fwlink/?LinkId=220824), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="da276-125">Blog entry, [API Sample - OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), on blogs.msdn.com.</span></span>  
  
-   <span data-ttu-id="da276-126">Entrada de blog sobre [EzAPI, actualizado para SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="da276-126">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="da276-127">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="da276-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="da276-128">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="da276-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="da276-129">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="da276-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="da276-130">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="da276-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da276-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da276-131">See Also</span></span>  
 [<span data-ttu-id="da276-132">Agregar tareas mediante programación</span><span class="sxs-lookup"><span data-stu-id="da276-132">Adding Tasks Programmatically</span></span>](../building-packages-programmatically/adding-tasks-programmatically.md)  
  
  
