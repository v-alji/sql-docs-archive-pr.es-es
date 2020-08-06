---
title: Crear una tarea personalizada | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom tasks [Integration Services], creating
ms.assetid: 42965c09-1782-4cdb-9ce1-216af4c23e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f752acad7a442a8e0aad2d24e94938c14195a35d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674215"
---
# <a name="creating-a-custom-task"></a><span data-ttu-id="22a01-102">Crear una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="22a01-102">Creating a Custom Task</span></span>
  <span data-ttu-id="22a01-103">Los pasos necesarios para crear una tarea personalizada son similares a los pasos para crear cualquier otro objeto personalizado para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="22a01-103">The steps involved in creating a custom task are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="22a01-104">Cree una clase nueva que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="22a01-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="22a01-105">En una tarea, la clase base es [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span><span class="sxs-lookup"><span data-stu-id="22a01-105">For a task, the base class is [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span></span>  
  
-   <span data-ttu-id="22a01-106">Aplique el atributo que identifica el tipo de objeto para la clase.</span><span class="sxs-lookup"><span data-stu-id="22a01-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="22a01-107">En una tarea, el atributo es <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="22a01-107">For a task, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span></span>  
  
-   <span data-ttu-id="22a01-108">Invalide la implementación de los métodos y las propiedades de la clase base.</span><span class="sxs-lookup"><span data-stu-id="22a01-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="22a01-109">En una tarea, incluyen los métodos <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="22a01-109">For a task, these include the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
-   <span data-ttu-id="22a01-110">Si lo desea, desarrolle una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="22a01-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="22a01-111">En una tarea, esto requiere una clase que implemente la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>.</span><span class="sxs-lookup"><span data-stu-id="22a01-111">For a task, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface.</span></span>  
  
## <a name="getting-started-with-a-custom-task"></a><span data-ttu-id="22a01-112">Introducción a una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="22a01-112">Getting Started with a Custom Task</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="22a01-113">Crear proyectos y clases</span><span class="sxs-lookup"><span data-stu-id="22a01-113">Creating Projects and Classes</span></span>  
 <span data-ttu-id="22a01-114">Dado que todas las tareas administradas se derivan de la clase base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), el primer paso al crear una tarea personalizada consiste en crear un proyecto de bibliotecas de clases en el lenguaje de programación administrado que prefiera y crear una clase que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="22a01-114">Because all managed tasks derive from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, the first step when you create a custom task is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="22a01-115">En esta clase derivada se invalidarán los métodos y las propiedades de la clase base para implementar la funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="22a01-115">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="22a01-116">En la misma solución, cree un segundo proyecto de bibliotecas de clases para la interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="22a01-116">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="22a01-117">Se recomienda utilizar un ensamblado independiente para la interfaz de usuario a fin de facilitar la implementación, ya que le permite actualizar y volver a implementar la tarea o su interfaz de usuario de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="22a01-117">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="22a01-118">Configure ambos proyectos para firmar los ensamblados que se generarán en tiempo de compilación mediante un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="22a01-118">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtstask-attribute"></a><span data-ttu-id="22a01-119">Aplicar el atributo DtsTask</span><span class="sxs-lookup"><span data-stu-id="22a01-119">Applying the DtsTask Attribute</span></span>  
 <span data-ttu-id="22a01-120">Aplique el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> a la clase que ha creado para identificarla como una tarea.</span><span class="sxs-lookup"><span data-stu-id="22a01-120">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class that you have created to identify it as a task.</span></span> <span data-ttu-id="22a01-121">Este atributo proporciona información en tiempo de diseño, como el nombre, la descripción y el tipo de tarea de la tarea.</span><span class="sxs-lookup"><span data-stu-id="22a01-121">This attribute provides design-time information such as the name, description, and task type of the task.</span></span>  
  
 <span data-ttu-id="22a01-122">Utilice la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> para vincular la tarea a su interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="22a01-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property to link the task to its custom user interface.</span></span> <span data-ttu-id="22a01-123">Para obtener el token de clave pública necesario para esta propiedad, puede usar **sn.exe -t** con el fin de mostrar el token de clave pública del archivo de pares de claves (.snk) que quiere usar para firmar el ensamblado de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="22a01-123">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
## <a name="building-deploying-and-debugging-a-custom-task"></a><span data-ttu-id="22a01-124">Generar, implementar y depurar una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="22a01-124">Building, Deploying, and Debugging a Custom Task</span></span>  
 <span data-ttu-id="22a01-125">Los pasos para generar, implementar y depurar una tarea personalizada en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] son similares a los pasos necesarios en otros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="22a01-125">The steps for building, deploying, and debugging a custom task in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="22a01-126">Para obtener más información, consulte [Generar, implementar y depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="22a01-126">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="22a01-127">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="22a01-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="22a01-128">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="22a01-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="22a01-129">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="22a01-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="22a01-130">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="22a01-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a01-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22a01-131">See Also</span></span>  
 <span data-ttu-id="22a01-132">[Creating a Custom Task](creating-a-custom-task.md)  (Crear una tarea personalizada)</span><span class="sxs-lookup"><span data-stu-id="22a01-132">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="22a01-133">[Programar una tarea personalizada](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="22a01-133">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="22a01-134">Desarrollar una interfaz de usuario para una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="22a01-134">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
