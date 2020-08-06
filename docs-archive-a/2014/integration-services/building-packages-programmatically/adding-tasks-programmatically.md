---
title: Agregar tareas mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], packages
- adding package tasks
ms.assetid: 5d4652d5-228c-4238-905c-346dd8503fdf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa61eb2fb87f45fe5b534b96280b8b4e2c21788d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671645"
---
# <a name="adding-tasks-programmatically"></a><span data-ttu-id="36255-102">Agregar tareas mediante programación</span><span class="sxs-lookup"><span data-stu-id="36255-102">Adding Tasks Programmatically</span></span>
  <span data-ttu-id="36255-103">Se pueden agregar tareas a los siguientes tipos de objetos en el motor en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="36255-103">Tasks can be added to the following types of objects in the run-time engine:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Package>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Sequence>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>  
  
 <span data-ttu-id="36255-104">Estas clases se consideran contenedores y todas ellas heredan la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A>.</span><span class="sxs-lookup"><span data-stu-id="36255-104">These classes are considered containers, and they all inherit the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A> property.</span></span> <span data-ttu-id="36255-105">Los contenedores pueden contener una colección de tareas, que son objetos ejecutables procesados por el motor en tiempo de ejecución durante la ejecución del contenedor.</span><span class="sxs-lookup"><span data-stu-id="36255-105">Containers can contain a collection of tasks, which are executable objects processed by the runtime during execution of the container.</span></span> <span data-ttu-id="36255-106">El orden de ejecución de los objetos en la colección se determina mediante cualquier conjunto <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> de cada tarea en los contenedores.</span><span class="sxs-lookup"><span data-stu-id="36255-106">The order of execution of the objects in the collection is determined any <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> set on each task in the containers.</span></span> <span data-ttu-id="36255-107">Las restricciones de precedencia habilitan la bifurcación de la ejecución en función del éxito, error o finalización de <xref:Microsoft.SqlServer.Dts.Runtime.Executable> en la colección.</span><span class="sxs-lookup"><span data-stu-id="36255-107">Precedence constraints enable execution branching based on the success, failure, or completion of an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in the collection.</span></span>  
  
 <span data-ttu-id="36255-108">Cada contenedor incluye una colección <xref:Microsoft.SqlServer.Dts.Runtime.Executables> que contiene los objetos <xref:Microsoft.SqlServer.Dts.Runtime.Executable> individuales.</span><span class="sxs-lookup"><span data-stu-id="36255-108">Each container has an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection that contains the individual <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects.</span></span> <span data-ttu-id="36255-109">Cada tarea ejecutable hereda e implementa el método <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> y el método <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="36255-109">Each executable task inherits and implements the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> method and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> method.</span></span> <span data-ttu-id="36255-110">El motor en tiempo de ejecución llama a estos dos métodos para procesar cada <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="36255-110">These two methods are called by the run-time engine to process each <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span></span>  
  
 <span data-ttu-id="36255-111">Para agregar una tarea a un paquete, necesita un contenedor con una colección <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existente.</span><span class="sxs-lookup"><span data-stu-id="36255-111">To add a task to a package, you need a container with an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existing collection.</span></span> <span data-ttu-id="36255-112">En la mayoría de las ocasiones, la tarea que agregará a la colección es un paquete.</span><span class="sxs-lookup"><span data-stu-id="36255-112">Most of the time, the task that you will add to the collection is a package.</span></span> <span data-ttu-id="36255-113">Para agregar el nuevo ejecutable de tarea a la colección de dicho contenedor, debe llamar al método <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="36255-113">To add the new task executable into the collection for that container, you call the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method .</span></span> <span data-ttu-id="36255-114">El método tiene un parámetro único, una cadena, que contiene los valores CLSID, PROGID, moniker STOCK o <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> de la tarea que agrega.</span><span class="sxs-lookup"><span data-stu-id="36255-114">The method has a single parameter, a string, that contains the CLSID, PROGID, STOCK moniker, or <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> of the task you are adding.</span></span>  
  
## <a name="task-names"></a><span data-ttu-id="36255-115">Nombres de tarea</span><span class="sxs-lookup"><span data-stu-id="36255-115">Task Names</span></span>  
 <span data-ttu-id="36255-116">Aunque puede especificar una tarea por nombre o por identificador, el moniker `STOCK` es el parámetro utilizado con mayor frecuencia en el método <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="36255-116">Although you can specify a task by name or by ID, the `STOCK` moniker is the parameter used most often in the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method.</span></span> <span data-ttu-id="36255-117">Para agregar a un ejecutable una tarea identificada por el moniker `STOCK`, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="36255-117">To add a task to an executable identified by the `STOCK` moniker, use the following syntax:</span></span>  
  
```csharp  
Executable exec = package.Executables.Add("STOCK:BulkInsertTask");  
  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add("STOCK:BulkInsertTask")  
  
```  
  
 <span data-ttu-id="36255-118">La lista siguiente muestra los nombres para cada tarea que se utilizan después del moniker `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="36255-118">The following list shows the names for each task that are used after the `STOCK` moniker.</span></span>  
  
-   <span data-ttu-id="36255-119">ActiveXScriptTask</span><span class="sxs-lookup"><span data-stu-id="36255-119">ActiveXScriptTask</span></span>  
  
-   <span data-ttu-id="36255-120">BulkInsertTask</span><span class="sxs-lookup"><span data-stu-id="36255-120">BulkInsertTask</span></span>  
  
-   <span data-ttu-id="36255-121">ExecuteProcessTask</span><span class="sxs-lookup"><span data-stu-id="36255-121">ExecuteProcessTask</span></span>  
  
-   <span data-ttu-id="36255-122">ExecutePackageTask</span><span class="sxs-lookup"><span data-stu-id="36255-122">ExecutePackageTask</span></span>  
  
-   <span data-ttu-id="36255-123">Exec80PackageTask</span><span class="sxs-lookup"><span data-stu-id="36255-123">Exec80PackageTask</span></span>  
  
-   <span data-ttu-id="36255-124">FileSystemTask</span><span class="sxs-lookup"><span data-stu-id="36255-124">FileSystemTask</span></span>  
  
-   <span data-ttu-id="36255-125">FTPTask</span><span class="sxs-lookup"><span data-stu-id="36255-125">FTPTask</span></span>  
  
-   <span data-ttu-id="36255-126">MSMQTask</span><span class="sxs-lookup"><span data-stu-id="36255-126">MSMQTask</span></span>  
  
-   <span data-ttu-id="36255-127">PipelineTask</span><span class="sxs-lookup"><span data-stu-id="36255-127">PipelineTask</span></span>  
  
-   <span data-ttu-id="36255-128">ScriptTask</span><span class="sxs-lookup"><span data-stu-id="36255-128">ScriptTask</span></span>  
  
-   <span data-ttu-id="36255-129">SendMailTask</span><span class="sxs-lookup"><span data-stu-id="36255-129">SendMailTask</span></span>  
  
-   <span data-ttu-id="36255-130">SQLTask</span><span class="sxs-lookup"><span data-stu-id="36255-130">SQLTask</span></span>  
  
-   <span data-ttu-id="36255-131">TransferStoredProceduresTask</span><span class="sxs-lookup"><span data-stu-id="36255-131">TransferStoredProceduresTask</span></span>  
  
-   <span data-ttu-id="36255-132">TransferLoginsTask</span><span class="sxs-lookup"><span data-stu-id="36255-132">TransferLoginsTask</span></span>  
  
-   <span data-ttu-id="36255-133">TransferErrorMessagesTask</span><span class="sxs-lookup"><span data-stu-id="36255-133">TransferErrorMessagesTask</span></span>  
  
-   <span data-ttu-id="36255-134">TransferJobsTask</span><span class="sxs-lookup"><span data-stu-id="36255-134">TransferJobsTask</span></span>  
  
-   <span data-ttu-id="36255-135">TransferObjectsTask</span><span class="sxs-lookup"><span data-stu-id="36255-135">TransferObjectsTask</span></span>  
  
-   <span data-ttu-id="36255-136">TransferDatabaseTask</span><span class="sxs-lookup"><span data-stu-id="36255-136">TransferDatabaseTask</span></span>  
  
-   <span data-ttu-id="36255-137">WebServiceTask</span><span class="sxs-lookup"><span data-stu-id="36255-137">WebServiceTask</span></span>  
  
-   <span data-ttu-id="36255-138">WmiDataReaderTask</span><span class="sxs-lookup"><span data-stu-id="36255-138">WmiDataReaderTask</span></span>  
  
-   <span data-ttu-id="36255-139">WmiEventWatcherTask</span><span class="sxs-lookup"><span data-stu-id="36255-139">WmiEventWatcherTask</span></span>  
  
-   <span data-ttu-id="36255-140">XMLTask</span><span class="sxs-lookup"><span data-stu-id="36255-140">XMLTask</span></span>  
  
 <span data-ttu-id="36255-141">Si prefiere una sintaxis más explícita o si la tarea que desea agregar no tiene un moniker STOCK, puede agregar la tarea al ejecutable utilizando su nombre largo.</span><span class="sxs-lookup"><span data-stu-id="36255-141">If you prefer a more explicit syntax, or if the task that you want to add does not have a STOCK moniker, you can add the task to the executable using its long name.</span></span> <span data-ttu-id="36255-142">Esta sintaxis requiere que también especifique el número de versión de la tarea.</span><span class="sxs-lookup"><span data-stu-id="36255-142">This syntax requires that you also specify the version number of the task.</span></span>  
  
```csharp  
Executable exec = package.Executables.Add(  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " +  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " +  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91");  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add( _  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " & _  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " & _  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91")  
```  
  
 <span data-ttu-id="36255-143">Puede obtener el nombre largo de la tarea mediante programación, sin tener que especificar la versión de la tarea, con la propiedad **AssemblyQualifiedName** de la clase, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="36255-143">You can obtain the long name for the task programmatically, without having to specify the task version, by using the **AssemblyQualifiedName** property of the class, as shown in the following example.</span></span> <span data-ttu-id="36255-144">En este ejemplo se requiere una referencia al ensamblado Microsoft.SqlServer.SQLTask.</span><span class="sxs-lookup"><span data-stu-id="36255-144">This example requires a reference to the Microsoft.SqlServer.SQLTask assembly.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask;  
...  
      Executable exec = package.Executables.Add(  
        typeof(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName);  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask  
...  
    Dim exec As Executable = package.Executables.Add( _  
      GetType(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName)  
```  
  
 <span data-ttu-id="36255-145">En el ejemplo de código siguiente se muestra cómo crear una colección <xref:Microsoft.SqlServer.Dts.Runtime.Executables> a partir de un nuevo paquete y, a continuación, cómo agregar una tarea de sistema de archivos y una tarea de inserción masiva a la colección, con sus monikers `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="36255-145">The following code example shows how to create an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection from a new package, and then add a File System task and a Bulk Insert task to the collection, by using their `STOCK` monikers.</span></span> <span data-ttu-id="36255-146">En este ejemplo se requiere una referencia a los ensamblados Microsoft.SqlServer.FileSystemTask y Microsoft.SqlServer.BulkInsertTask.</span><span class="sxs-lookup"><span data-stu-id="36255-146">This example requires a reference to the Microsoft.SqlServer.FileSystemTask and Microsoft.SqlServer.BulkInsertTask assemblies.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thBulkInsertTask = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        Console.WriteLine("Type {0}", taskHost.InnerObject.ToString());  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thBulkInsertTask As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      Console.WriteLine("Type {0}", taskHost.InnerObject.ToString())  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="36255-147">**Salida del ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="36255-147">**Sample Output:**</span></span>  
  
 `Type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
## <a name="taskhost-container"></a><span data-ttu-id="36255-148">Contenedor TaskHost</span><span class="sxs-lookup"><span data-stu-id="36255-148">TaskHost Container</span></span>  
 <span data-ttu-id="36255-149">La clase <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> es un contenedor que no aparece en la interfaz gráfica de usuario, pero es muy importante en la programación.</span><span class="sxs-lookup"><span data-stu-id="36255-149">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class is a container that does not appear in the graphical user interface, but is very important in programming.</span></span> <span data-ttu-id="36255-150">Esta clase es un contenedor para cada tarea.</span><span class="sxs-lookup"><span data-stu-id="36255-150">This class is a wrapper for every task.</span></span> <span data-ttu-id="36255-151">Las tareas que se agregan al paquete mediante el método <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> como un objeto <xref:Microsoft.SqlServer.Dts.Runtime.Executable> se pueden convertir como un objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="36255-151">Tasks that are added to the package by using the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object can be cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object.</span></span> <span data-ttu-id="36255-152">Cuando una tarea se convierte como <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, puede utilizar propiedades y métodos adicionales en la tarea.</span><span class="sxs-lookup"><span data-stu-id="36255-152">When a task is cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, you can use additional properties and methods on the task.</span></span> <span data-ttu-id="36255-153">Además, se puede tener acceso a la propia tarea mediante la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="36255-153">Also, the task itself can be accessed through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="36255-154">Según sus necesidades, puede mantener la tarea como un objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> para utilizar sus propiedades a través de la colección <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="36255-154">Depending on your needs, you may decide to keep the task as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object so that you can use the properties of the task through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection.</span></span> <span data-ttu-id="36255-155">La ventaja de utilizar <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> es que puede escribir código más genérico.</span><span class="sxs-lookup"><span data-stu-id="36255-155">The advantage of using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> is that you can write more generic code.</span></span> <span data-ttu-id="36255-156">Si necesita código muy específico para una tarea, debe convertir la tarea a su objeto adecuado.</span><span class="sxs-lookup"><span data-stu-id="36255-156">If you need very specific code for a task, then you should cast the task to its appropriate object.</span></span>  
  
 <span data-ttu-id="36255-157">En el ejemplo de código siguiente se muestra cómo convertir <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, que contiene <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, a un objeto <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>.</span><span class="sxs-lookup"><span data-stu-id="36255-157">The following code example shows how to cast a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, that contains a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> object.</span></span>  
  
```csharp  
BulkInsertTask myTask = thBulkInsertTask.InnerObject as BulkInsertTask;  
```  
  
```vb  
Dim myTask As BulkInsertTask = CType(thBulkInsertTask.InnerObject, BulkInsertTask)  
```  
  
 <span data-ttu-id="36255-158">En el ejemplo de código siguiente se muestra cómo convertir el ejecutable a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> y, a continuación, cómo utilizar la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> para determinar qué tipo de ejecutable contiene el host.</span><span class="sxs-lookup"><span data-stu-id="36255-158">The following code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property to determine which type of executable is contained by the host.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask1 = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thFileSystemTask2 = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask)  
        {  
          // Do work with FileSystemTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        else if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask)  
        {  
          // Do work with BulkInsertTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        // Add additional statements to check InnerObject, if desired.  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask1 As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thFileSystemTask2 As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      If TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask Then  
        ' Do work with FileSystemTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      ElseIf TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask Then  
        ' Do work with BulkInsertTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      End If  
      ' Add additional statements to check InnerObject, if desired.  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="36255-159">**Salida del ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="36255-159">**Sample Output:**</span></span>  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
 <span data-ttu-id="36255-160">La instrucción <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> devuelve un ejecutable que se convierte a un objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> a partir del objeto <xref:Microsoft.SqlServer.Dts.Runtime.Executable> recién creado.</span><span class="sxs-lookup"><span data-stu-id="36255-160">The <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> statement returns an executable that is cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object from the newly created <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object.</span></span>  
  
 <span data-ttu-id="36255-161">Para establecer propiedades o llamar a métodos en el nuevo objeto, existen dos opciones:</span><span class="sxs-lookup"><span data-stu-id="36255-161">To set properties or to call methods on the new object, you have two options:</span></span>  
  
1.  <span data-ttu-id="36255-162">Utilice la colección <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="36255-162">Use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="36255-163">Por ejemplo, para obtener una propiedad del objeto, utilice `th.Properties["propertyname"].GetValue(th))`.</span><span class="sxs-lookup"><span data-stu-id="36255-163">For example, to obtain a property from the object, use `th.Properties["propertyname"].GetValue(th))`.</span></span> <span data-ttu-id="36255-164">Para establecer una propiedad, utilice `th.Properties["propertyname"].SetValue(th, <value>);`.</span><span class="sxs-lookup"><span data-stu-id="36255-164">To set a property, use `th.Properties["propertyname"].SetValue(th, <value>);`.</span></span>  
  
2.  <span data-ttu-id="36255-165">Convierta <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> a la clase de tarea.</span><span class="sxs-lookup"><span data-stu-id="36255-165">Cast the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task class.</span></span> <span data-ttu-id="36255-166">Por ejemplo, para convertir la tarea Inserción masiva a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> después de agregarla a un paquete como <xref:Microsoft.SqlServer.Dts.Runtime.Executable> y posteriormente convertirla a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, utilice `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span><span class="sxs-lookup"><span data-stu-id="36255-166">For example, to cast the Bulk Insert task to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> after it has been added to a package as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> and subsequently cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, use `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span></span>  
  
 <span data-ttu-id="36255-167">La utilización de la clase <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> en código, en lugar de convertir a la clase específica de la tarea presenta las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="36255-167">Using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class in code, instead of casting to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="36255-168">El proveedor <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> de la clase <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> no requiere una referencia al ensamblado en el código.</span><span class="sxs-lookup"><span data-stu-id="36255-168">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> provider does not require a reference to the assembly in the code.</span></span>  
  
-   <span data-ttu-id="36255-169">Puede codificar rutinas genéricas que funcionan en cualquier tarea, ya que no es necesario conocer el nombre de la tarea en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="36255-169">You can code generic routines that work for any task, because you do not have to know the name of the task at compile time.</span></span> <span data-ttu-id="36255-170">Estas rutinas genéricas incluyen métodos donde se pasa el nombre de la tarea al método; el código del método funciona en todas las tareas.</span><span class="sxs-lookup"><span data-stu-id="36255-170">Such generic routines include methods where you pass in the name of the task to the method, and the method code works for all tasks.</span></span> <span data-ttu-id="36255-171">Éste es un método adecuado para escribir código de prueba.</span><span class="sxs-lookup"><span data-stu-id="36255-171">This is a good method for writing test code.</span></span>  
  
 <span data-ttu-id="36255-172">La conversión de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> a la clase específica de la tarea presenta las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="36255-172">Casting from the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="36255-173">El proyecto de Visual Studio proporciona finalización de instrucciones (IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="36255-173">The Visual Studio project gives you statement completion (IntelliSense).</span></span>  
  
-   <span data-ttu-id="36255-174">El código se puede ejecutar con más rapidez.</span><span class="sxs-lookup"><span data-stu-id="36255-174">The code may run faster.</span></span>  
  
-   <span data-ttu-id="36255-175">Los objetos específicos de la tarea habilitan el enlace anticipado y las optimizaciones resultantes.</span><span class="sxs-lookup"><span data-stu-id="36255-175">Task-specific objects enable early binding and the resulting optimizations.</span></span> <span data-ttu-id="36255-176">Para obtener más información el enlace anticipado y el enlace en tiempo de ejecución, vea el tema correspondiente en Conceptos del lenguaje Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="36255-176">For more information about early and late binding, see the topic "Early and Late Binding" in Visual Basic Language Concepts.</span></span>  
  
 <span data-ttu-id="36255-177">En el ejemplo de código siguiente se amplía el concepto de reutilización de código de la tarea.</span><span class="sxs-lookup"><span data-stu-id="36255-177">The following code example expands on the concept of reusing task code.</span></span> <span data-ttu-id="36255-178">En lugar de convertir las tareas a sus equivalentes de clase específicos, el ejemplo de código muestra cómo convertir el ejecutable a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> y, a continuación, cómo utilizar <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> para escribir código genérico para todas las tareas.</span><span class="sxs-lookup"><span data-stu-id="36255-178">Instead of casting tasks to their specific class equivalents, the code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then uses the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> to write generic code against all the tasks.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
  
      string[] tasks = { "STOCK:SQLTask", "STOCK:ScriptTask",   
        "STOCK:ExecuteProcessTask", "STOCK:PipelineTask",   
        "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask" };  
  
      foreach (string s in tasks)  
      {  
        TaskHost taskhost = package.Executables.Add(s) as TaskHost;  
        DtsProperties props = taskhost.Properties;  
        Console.WriteLine("Enumerating properties on " + taskhost.Name);  
        Console.WriteLine(" TaskHost.InnerObject is " + taskhost.InnerObject.ToString());  
        Console.WriteLine();  
  
        foreach (DtsProperty prop in props)  
        {  
          Console.WriteLine("Properties for " + prop.Name);  
          Console.WriteLine("Name : " + prop.Name);  
          Console.WriteLine("Type : " + prop.Type.ToString());  
          Console.WriteLine("Readable : " + prop.Get.ToString());  
          Console.WriteLine("Writable : " + prop.Set.ToString());  
          Console.WriteLine();  
        }  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package = New Package()  
  
    Dim tasks() As String = New String() {"STOCK:SQLTask", "STOCK:ScriptTask", _  
              "STOCK:ExecuteProcessTask", "STOCK:PipelineTask", _  
              "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask"}  
  
    For Each s As String In tasks  
  
      Dim taskhost As TaskHost = CType(package.Executables.Add(s), TaskHost)  
      Dim props As DtsProperties = taskhost.Properties  
      Console.WriteLine("Enumerating properties on " & taskhost.Name)  
      Console.WriteLine(" TaskHost.InnerObject is " & taskhost.InnerObject.ToString())  
      Console.WriteLine()  
  
      For Each prop As DtsProperty In props  
        Console.WriteLine("Properties for " + prop.Name)  
        Console.WriteLine(" Name : " + prop.Name)  
        Console.WriteLine(" Type : " + prop.Type.ToString())  
        Console.WriteLine(" Readable : " + prop.Get.ToString())  
        Console.WriteLine(" Writable : " + prop.Set.ToString())  
        Console.WriteLine()  
      Next  
  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="36255-179">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="36255-179">External Resources</span></span>  
 <span data-ttu-id="36255-180">Entrada de blog sobre [EzAPI, actualizado para SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="36255-180">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="36255-181">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="36255-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="36255-182">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="36255-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="36255-183">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="36255-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="36255-184">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="36255-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36255-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36255-185">See Also</span></span>  
 [<span data-ttu-id="36255-186">Conectar tareas mediante programación</span><span class="sxs-lookup"><span data-stu-id="36255-186">Connecting Tasks Programmatically</span></span>](../building-packages-programmatically/connecting-tasks-programmatically.md)  
  
  
