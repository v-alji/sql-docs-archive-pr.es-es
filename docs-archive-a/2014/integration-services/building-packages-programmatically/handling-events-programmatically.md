---
title: Controlar eventos mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services packages, events
- SQL Server Integration Services packages, events
- SSIS events, programmatically handling
- packages [Integration Services], events
- DtsEventHandler object
- SSIS packages, events
- SSIS events
- events [Integration Services], programmatically
- tasks [Integration Services], events
- IDTSEvents interface
ms.assetid: 0f00bd66-efd5-4f12-9e1c-36195f739332
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70d2d8909df65f775fc3a3034931bb599597068
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671137"
---
# <a name="handling-events-programmatically"></a><span data-ttu-id="7641c-102">Controlar eventos mediante programación</span><span class="sxs-lookup"><span data-stu-id="7641c-102">Handling Events Programmatically</span></span>
  <span data-ttu-id="7641c-103">El motor de tiempo de ejecución de [!INCLUDE[ssIS](../../includes/ssis-md.md)] proporciona una recopilación de eventos que se producen antes, durante y después de la validación y la ejecución de un paquete.</span><span class="sxs-lookup"><span data-stu-id="7641c-103">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] runtime provides a collection of events that occur before, during, and after the validation and execution of a package.</span></span> <span data-ttu-id="7641c-104">Estos eventos se pueden capturar de dos formas.</span><span class="sxs-lookup"><span data-stu-id="7641c-104">These events can be captured in two ways.</span></span> <span data-ttu-id="7641c-105">El primer método consiste en implementar la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> en una clase y proporcionar la clase como parámetro a los métodos `Execute` y `Validate` del paquete.</span><span class="sxs-lookup"><span data-stu-id="7641c-105">The first method is by implementing the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface in a class, and supplying the class as a parameter to the `Execute` and `Validate` methods of the package.</span></span> <span data-ttu-id="7641c-106">El segundo método consiste en crear objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>, que pueden contener otros objetos [!INCLUDE[ssIS](../../includes/ssis-md.md)], como tareas y bucles, que se ejecutan cuando se produce un evento en <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="7641c-106">The second method is by creating <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects, which can contain other [!INCLUDE[ssIS](../../includes/ssis-md.md)] objects, such as tasks and loops, that are executed when an event in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> occurs.</span></span> <span data-ttu-id="7641c-107">En esta sección se describen ambos métodos y se proporcionan ejemplos de código que muestran su uso.</span><span class="sxs-lookup"><span data-stu-id="7641c-107">This section describes these two methods and provides code examples to demonstrate their use.</span></span>  
  
## <a name="receiving-idtsevents-callbacks"></a><span data-ttu-id="7641c-108">Recibir devoluciones de llamada de IDTSEvents</span><span class="sxs-lookup"><span data-stu-id="7641c-108">Receiving IDTSEvents Callbacks</span></span>  
 <span data-ttu-id="7641c-109">Los desarrolladores que generan y ejecutan paquetes mediante programación puede recibir notificaciones de eventos durante el proceso de validación y ejecución utilizando la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="7641c-109">Developers who build and execute packages programmatically can receive event notifications during the validation and execution process using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface.</span></span> <span data-ttu-id="7641c-110">Para ello, se crea una clase que implementa la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> y se proporciona esta clase como parámetro a los métodos `Validate` y `Execute` de un paquete.</span><span class="sxs-lookup"><span data-stu-id="7641c-110">This is done by creating a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface and providing this class as a parameter to the `Validate` and `Execute` methods of a package.</span></span> <span data-ttu-id="7641c-111">Después, el motor en tiempo de ejecución llama a los métodos de la clase cuando se producen los eventos.</span><span class="sxs-lookup"><span data-stu-id="7641c-111">The methods of the class are then called by the run-time engine when the events occur.</span></span>  
  
 <span data-ttu-id="7641c-112">La clase <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> es una clase que ya implementa la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>; por lo tanto, otra alternativa a la implementación directa de <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> es derivar de <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> e invalidar los eventos específicos a los que desea responder.</span><span class="sxs-lookup"><span data-stu-id="7641c-112">The <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class is a class that already implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface; therefore, another alternative to implementing <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> directly is to derive from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> and override the specific events that you want to respond to.</span></span> <span data-ttu-id="7641c-113">A continuación, se proporciona la clase como parámetro a los métodos `Validate` y `Execute` de <xref:Microsoft.SqlServer.Dts.Runtime.Package> para recibir devoluciones de llamada de evento.</span><span class="sxs-lookup"><span data-stu-id="7641c-113">You then provide your class as a parameter to the `Validate` and `Execute` methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Package> to receive event callbacks.</span></span>  
  
 <span data-ttu-id="7641c-114">El ejemplo de código siguiente muestra una clase que deriva de <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> e invalida el método <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="7641c-114">The following code sample demonstrates a class that derives from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, and overrides the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A> method.</span></span> <span data-ttu-id="7641c-115">A continuación, la clase se proporciona como parámetro a los `Validate` `Execute` métodos y del paquete.</span><span class="sxs-lookup"><span data-stu-id="7641c-115">The class is then provided as aparameter to the `Validate` and `Execute` methods of the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      MyEventsClass eventsClass = new MyEventsClass();  
  
      p.Validate(null, null, eventsClass, null);  
      p.Execute(null, null, eventsClass, null, null);  
  
      Console.Read();  
    }  
  }  
  class MyEventsClass : DefaultEvents  
  {  
    public override void OnPreExecute(Executable exec, ref bool fireAgain)  
    {  
      // TODO: Add custom code to handle the event.  
      Console.WriteLine("The PreExecute event of the " +  
        exec.ToString() + " has been raised.");  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim eventsClass As MyEventsClass = New MyEventsClass()  
  
    p.Validate(Nothing, Nothing, eventsClass, Nothing)  
    p.Execute(Nothing, Nothing, eventsClass, Nothing, Nothing)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
Class MyEventsClass  
  Inherits DefaultEvents  
  
  Public Overrides Sub OnPreExecute(ByVal exec As Executable, ByRef fireAgain As Boolean)  
  
    ' TODO: Add custom code to handle the event.  
    Console.WriteLine("The PreExecute event of the " & _  
      exec.ToString() & " has been raised.")  
  
  End Sub  
  
End Class  
```  
  
## <a name="creating-dtseventhandler-objects"></a><span data-ttu-id="7641c-116">Crear objetos DtsEventHandler</span><span class="sxs-lookup"><span data-stu-id="7641c-116">Creating DtsEventHandler Objects</span></span>  
 <span data-ttu-id="7641c-117">El motor en tiempo de ejecución proporciona un sistema de notificaciones y control de eventos extremadamente flexible y sólido a través del objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="7641c-117">The run-time engine provides a robust, highly flexible event handling and notification system through the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="7641c-118">Estos objetos permiten diseñar flujos de trabajo completos en el controlador de eventos que solamente se ejecutan cuando se produce el evento al que pertenece el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="7641c-118">These objects let you design whole workflows within the event handler, which execute only when the event that the event handler belongs to occurs.</span></span> <span data-ttu-id="7641c-119">El objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> es un contenedor que se ejecuta cuando se desencadena el evento correspondiente en su objeto primario.</span><span class="sxs-lookup"><span data-stu-id="7641c-119">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object is a container that is executed when the corresponding event on its parent object fires.</span></span> <span data-ttu-id="7641c-120">Esta arquitectura permite crear flujos de trabajo aislados que se ejecutan como respuesta a eventos que se producen en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="7641c-120">This architecture lets you create isolated workflows that are executed in response to events that occur on a container.</span></span> <span data-ttu-id="7641c-121">Dado que los objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> son sincrónicos, la ejecución no se reanuda hasta que se devuelven los controladores de eventos adjuntados al evento.</span><span class="sxs-lookup"><span data-stu-id="7641c-121">Because <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are synchronous, execution does not resume until the event handlers that are attached to the event have returned.</span></span>  
  
 <span data-ttu-id="7641c-122">En el código siguiente se muestra cómo se crea un objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="7641c-122">The following code demonstrates how to create a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="7641c-123">El código agrega un elemento <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> a la colección <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> del paquete y, a continuación, crea un objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> para el evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> de la tarea.</span><span class="sxs-lookup"><span data-stu-id="7641c-123">The code adds a <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> collection of the package, and then creates a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object for the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event of the task.</span></span> <span data-ttu-id="7641c-124">Se agrega un elemento <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> al controlador de eventos, que se ejecuta cuando se produce el evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> para el primer elemento <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span><span class="sxs-lookup"><span data-stu-id="7641c-124">A <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> is added to the event handler, which is executed when the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event occurs for the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span></span> <span data-ttu-id="7641c-125">En este ejemplo se da por supuesto que tiene un archivo denominado C:\Windows\Temp\DemoFile.txt con fines de pruebas.</span><span class="sxs-lookup"><span data-stu-id="7641c-125">This example assumes that you have a file that is named C:\Windows\Temp\DemoFile.txt for testing.</span></span> <span data-ttu-id="7641c-126">La primera vez que se ejecuta el ejemplo, copia el archivo correctamente y no se llama al controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="7641c-126">The first time that you run the sample, if copies the file successfully and the event handler is not called.</span></span> <span data-ttu-id="7641c-127">La segunda vez que se ejecuta el ejemplo, el primer elemento <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> no puede copiar el archivo (porque el valor de <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> es `false`), se llama al controlador de eventos, el segundo elemento <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> elimina el archivo de origen y el paquete informa del error producido.</span><span class="sxs-lookup"><span data-stu-id="7641c-127">The second time you run the sample, the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> fails to copy the file (because the value of <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> is `false`), the event handler is called, the second <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> deletes the source file, and the package reports failure because of the error that occurred.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7641c-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7641c-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string f = "DemoFile.txt";  
      Executable e;  
      TaskHost th;  
      FileSystemTask fst;  
  
      Package p = new Package();  
  
      p.Variables.Add("sourceFile", true, String.Empty,  
        @"C:\Windows\Temp\" + f);  
      p.Variables.Add("destinationFile", true, String.Empty,  
        Path.Combine(Directory.GetCurrentDirectory(), f));  
  
      // Create a first File System task and add it to the package.  
      // This task tries to copy a file from one folder to another.  
      e = p.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask1";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.CopyFile;  
      fst.OverwriteDestinationFile = false;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
      fst.Destination = "destinationFile";  
      fst.IsDestinationPathVariable = true;  
  
      // Add an event handler for the FileSystemTask's OnError event.  
      DtsEventHandler ehOnError = (DtsEventHandler)th.EventHandlers.Add("OnError");  
  
      // Create a second File System task and add it to the event handler.  
      // This task deletes the source file if the event handler is called.  
      e = ehOnError.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask2";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.DeleteFile;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
  
      DTSExecResult vr = p.Validate(null, null, null, null);  
      Console.WriteLine("ValidationResult = " + vr.ToString());  
      if (vr == DTSExecResult.Success)  
      {  
        DTSExecResult er = p.Execute(null, null, null, null, null);  
        Console.WriteLine("ExecutionResult = " + er.ToString());  
        if (er == DTSExecResult.Failure)  
          if (!File.Exists(@"C:\Windows\Temp\" + f))  
            Console.WriteLine("Source file has been deleted by the event handler.");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim f As String = "DemoFile.txt"  
    Dim e As Executable  
    Dim th As TaskHost  
    Dim fst As FileSystemTask  
  
    Dim p As Package = New Package()  
  
    p.Variables.Add("sourceFile", True, String.Empty, _  
      "C:\Windows\Temp\" & f)  
    p.Variables.Add("destinationFile", True, String.Empty, _  
      Path.Combine(Directory.GetCurrentDirectory(), f))  
  
    ' Create a first File System task and add it to the package.  
    ' This task tries to copy a file from one folder to another.  
    e = p.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.CopyFile  
    fst.OverwriteDestinationFile = False  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
    fst.Destination = "destinationFile"  
    fst.IsDestinationPathVariable = True  
  
    ' Add an event handler for the FileSystemTask's OnError event.  
    Dim ehOnError As DtsEventHandler = CType(th.EventHandlers.Add("OnError"), DtsEventHandler)  
  
    ' Create a second File System task and add it to the event handler.  
    ' This task deletes the source file if the event handler is called.  
    e = ehOnError.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.DeleteFile  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
  
    Dim vr As DTSExecResult = p.Validate(Nothing, Nothing, Nothing, Nothing)  
    Console.WriteLine("ValidationResult = " + vr.ToString())  
    If vr = DTSExecResult.Success Then  
      Dim er As DTSExecResult = p.Execute(Nothing, Nothing, Nothing, Nothing, Nothing)  
      Console.WriteLine("ExecutionResult = " + er.ToString())  
      If er = DTSExecResult.Failure Then  
        If Not File.Exists("C:\Windows\Temp\" + f) Then  
          Console.WriteLine("Source file has been deleted by the event handler.")  
        End If  
      End If  
    End If  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="7641c-129">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7641c-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7641c-130">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="7641c-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7641c-131">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="7641c-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7641c-132">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="7641c-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7641c-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7641c-133">See Also</span></span>  
 <span data-ttu-id="7641c-134">[Controladores de eventos de Integration Services &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="7641c-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="7641c-135">Agregar un controlador de eventos a un paquete</span><span class="sxs-lookup"><span data-stu-id="7641c-135">Add an Event Handler to a Package</span></span>](../add-an-event-handler-to-a-package.md)  
  
  
