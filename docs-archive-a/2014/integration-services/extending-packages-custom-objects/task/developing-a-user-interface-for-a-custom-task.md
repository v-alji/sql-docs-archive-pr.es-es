---
title: Desarrollar una interfaz de usuario para una tarea personalizada | Microsoft Docs
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
- custom user interfaces [Integration Services]
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- custom tasks [Integration Services], user interface
- custom user interface [Integration Services], custom tasks
- user interface [Integration Services]
- SSIS custom tasks, user interface
ms.assetid: 1e940cd1-c5f8-4527-b678-e89ba5dc398a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed96bbc302cba4c207e5ce7b2e4fb4b74fed4ee2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676586"
---
# <a name="developing-a-user-interface-for-a-custom-task"></a><span data-ttu-id="fb1e6-102">Desarrollar una interfaz de usuario para una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="fb1e6-102">Developing a User Interface for a Custom Task</span></span>
  <span data-ttu-id="fb1e6-103">El modelo de objetos de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] permite a los desarrolladores de tareas personalizadas crear con facilidad una interfaz de usuario personalizada para una tarea que posteriormente se puede integrar y mostrar en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1e6-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] object model provides custom task developers the ability to easily create a custom user interface for a task that can then be integrated and displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="fb1e6-104">La interfaz de usuario puede proporcionar información útil al usuario en el Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] y guiar a los usuarios para configurar correctamente las propiedades y los valores de la tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-104">The user interface can provide helpful information to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and guide users to correctly configure the properties and settings of the custom task.</span></span>  
  
 <span data-ttu-id="fb1e6-105">El desarrollo de una interfaz de usuario personalizada para una tarea implica la utilización de dos clases importantes.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-105">Developing a custom user interface for a task involves using two important classes.</span></span> <span data-ttu-id="fb1e6-106">En la siguiente tabla se describen estas clases.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-106">The following table describes those classes.</span></span>  
  
|<span data-ttu-id="fb1e6-107">Clase</span><span class="sxs-lookup"><span data-stu-id="fb1e6-107">Class</span></span>|<span data-ttu-id="fb1e6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb1e6-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>|<span data-ttu-id="fb1e6-109">Un atributo que identifica una tarea administrada y proporciona información en tiempo de diseño a través de sus propiedades para controlar cómo el Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] muestra e interactúa con el objeto.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-109">An attribute that identifies a managed task, and supplies design-time information through its properties to control how [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer displays and interacts with the object.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>|<span data-ttu-id="fb1e6-110">Una interfaz que utiliza la tarea para asociar ésta a su interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-110">An interface used by the task to associate the task with its custom user interface.</span></span>|  
  
 <span data-ttu-id="fb1e6-111">En esta sección se describe el rol del atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> y la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> cuando se está desarrollando una interfaz de usuario para una tarea personalizada y se proporcionan detalles sobre cómo crear, integrar, implementar y depurar la tarea en el Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1e6-111">This section describes the role of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface when you are developing a user interface for a custom task, and provides details about how to create, integrate, deploy, and debug the task within [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="fb1e6-112">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] proporciona varios puntos de entrada a la interfaz de usuario de la tarea: el usuario puede seleccionar **Editar** en el menú contextual, hacer doble clic en la tarea o hacer clic en el vínculo **Mostrar editor** en la parte inferior de la hoja de propiedades.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-112">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer provides multiple entry points to the user interface for the task: the user can select **Edit** on the shortcut menu, double-click the task, or click the **Show Editor** link at the bottom of the property sheet.</span></span> <span data-ttu-id="fb1e6-113">Cuando el usuario tiene acceso a uno de estos puntos de entrada, el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] busca y carga el ensamblado que contiene la interfaz de usuario para la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-113">When the user accesses one of these entry points, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer locates and loads the assembly that contains the user interface for the task.</span></span> <span data-ttu-id="fb1e6-114">Ésta es responsable de la creación del cuadro de diálogo de propiedades que se muestra al usuario en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1e6-114">The user interface for the task is responsible for creating the properties dialog box that is displayed to the user in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="fb1e6-115">Una tarea y su interfaz de usuario son entidades independientes.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-115">A task and its user interface are separate entities.</span></span> <span data-ttu-id="fb1e6-116">Se deben implementar en ensamblados independientes para reducir el trabajo de localización, implementación y mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-116">They should be implemented in separate assemblies to reduce localization, deployment, and maintenance work.</span></span> <span data-ttu-id="fb1e6-117">La DLL de la tarea no carga, llama ni generalmente contiene ningún conocimiento de su interfaz de usuario, salvo la información que se incluye en los valores de atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> codificados en la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-117">The task DLL does not load, call, or generally contain any knowledge of its user interface, except for the information that is contained in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute values coded in the task.</span></span> <span data-ttu-id="fb1e6-118">Ésta es la única manera en que se asocian una tarea y su interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-118">This is the only way that a task and its user interface are associated.</span></span>  
  
## <a name="the-dtstask-attribute"></a><span data-ttu-id="fb1e6-119">El atributo DtsTask</span><span class="sxs-lookup"><span data-stu-id="fb1e6-119">The DtsTask Attribute</span></span>  
 <span data-ttu-id="fb1e6-120">El atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> se incluye en el código de clase de la tarea para asociar una tarea a su interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-120">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute is included in the task class code to associate a task with its user interface.</span></span> <span data-ttu-id="fb1e6-121">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utiliza las propiedades del atributo para determinar cómo se muestra la tarea en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-121">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the properties of the attribute to determine how to display the task in the designer.</span></span> <span data-ttu-id="fb1e6-122">Estas propiedades incluyen el nombre para mostrar y el icono, si existe.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-122">These properties include the name to display and the icon, if any.</span></span>  
  
 <span data-ttu-id="fb1e6-123">En la tabla siguiente se describen las propiedades del atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-123">The following table describes the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute.</span></span>  
  
|<span data-ttu-id="fb1e6-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fb1e6-124">Property</span></span>|<span data-ttu-id="fb1e6-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb1e6-125">Description</span></span>|  
|--------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>|<span data-ttu-id="fb1e6-126">Muestra el nombre de tarea en el cuadro de herramientas Flujo de control.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-126">Displays the task name in the Control Flow toolbox.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>|<span data-ttu-id="fb1e6-127">La descripción de la tarea (se hereda de <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span><span class="sxs-lookup"><span data-stu-id="fb1e6-127">The task description (inherited from <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span></span> <span data-ttu-id="fb1e6-128">Esta propiedad se muestra en la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-128">This property is shown in ToolTips.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A>|<span data-ttu-id="fb1e6-129">El icono que se muestra en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1e6-129">The icon displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.RequiredProductLevel%2A>|<span data-ttu-id="fb1e6-130">Si se utiliza, establézcala en uno de los valores de la enumeración <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel>.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-130">If used, set it to one of the values in the <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel> enumeration.</span></span> <span data-ttu-id="fb1e6-131">Por ejemplo, `RequiredProductLevel = DTSProductLevel.None`.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-131">For example, `RequiredProductLevel = DTSProductLevel.None`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskContact%2A>|<span data-ttu-id="fb1e6-132">Contiene información de contacto para las ocasiones en que la tarea requiere soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-132">Holds contact information for occasions when the task requires technical support.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskType%2A>|<span data-ttu-id="fb1e6-133">Asigna un tipo a la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-133">Assigns a type to the task.</span></span>|  
|<span data-ttu-id="fb1e6-134">Attribute.TypeId</span><span class="sxs-lookup"><span data-stu-id="fb1e6-134">Attribute.TypeId</span></span>|<span data-ttu-id="fb1e6-135">Cuando se implementa en una clase derivada, obtiene un identificador único para este atributo.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-135">When implemented in a derived class, gets a unique identifier for this Attribute.</span></span> <span data-ttu-id="fb1e6-136">Para obtener más información, vea la propiedad `Attribute.TypeID` en la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-136">For more information, see `Attribute.TypeID` property in the .NET Framework Class Library.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>|<span data-ttu-id="fb1e6-137">El nombre de tipo del ensamblado que utiliza el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] para cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-137">The type name of the assembly that is used by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to load the assembly.</span></span> <span data-ttu-id="fb1e6-138">Esta propiedad se utiliza para buscar el ensamblado de interfaz de usuario para la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-138">This property is used to find the user interface assembly for the task.</span></span>|  
  
 <span data-ttu-id="fb1e6-139">En el ejemplo de código siguiente se muestra <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> tal como aparecería, codificado sobre la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-139">The following code example shows the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> as it would look, coded above the class definition.</span></span>  
  
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
  
 <span data-ttu-id="fb1e6-140">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utiliza la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> del atributo que incluye el nombre del ensamblado, nombre de tipo, versión, referencia cultural y token de clave pública, para buscar el ensamblado en la Caché de ensamblados global (GAC) y cargarlo para que lo utilice el diseñador.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-140">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property of the attribute that includes the assembly name, type name, version, culture, and public key token, to locate the assembly in the Global Assembly Cache (GAC) and load it for use by the designer.</span></span>  
  
 <span data-ttu-id="fb1e6-141">Una vez encontrado el ensamblado, el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utiliza las demás propiedades del atributo para mostrar información adicional sobre la tarea en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)], como el nombre, icono y descripción de la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-141">After the assembly has been located, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the other properties in the attribute to display additional information about the task in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, such as the name, icon, and description of the task.</span></span>  
  
 <span data-ttu-id="fb1e6-142">Las propiedades <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> especifican cómo se presenta la tarea al usuario.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-142">The <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> properties specify how the task is presented to the user.</span></span> <span data-ttu-id="fb1e6-143">La propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> contiene el identificador de recurso del icono incrustado en el ensamblado de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-143">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> property contains the resource ID of the icon embedded in the user interface assembly.</span></span> <span data-ttu-id="fb1e6-144">El diseñador carga el recurso de icono por identificador del ensamblado y lo muestra junto al nombre de tarea en el cuadro de herramientas y en la superficie del diseñador cuando la tarea se agrega a un paquete.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-144">The designer loads the icon resource by ID from the assembly, and displays it next to the task name in the toolbox and on the designer surface when the task is added to a package.</span></span> <span data-ttu-id="fb1e6-145">Si una tarea no proporciona un recurso de icono, el diseñador utiliza un icono predeterminado para la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-145">If a task does not provide an icon resource, the designer uses a default icon for the task.</span></span>  
  
## <a name="the-idtstaskui-interface"></a><span data-ttu-id="fb1e6-146">La interfaz IDTSTaskUI</span><span class="sxs-lookup"><span data-stu-id="fb1e6-146">The IDTSTaskUI Interface</span></span>  
 <span data-ttu-id="fb1e6-147">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> define la colección de métodos y propiedades invocada por el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] para inicializar y mostrar la interfaz de usuario asociada a la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-147">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface defines the collection of methods and properties called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to initialize and display the user interface associated with the task.</span></span> <span data-ttu-id="fb1e6-148">Cuando se invoca la interfaz de usuario de una tarea, el diseñador llama al método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A>, que implementa la interfaz de usuario de la tarea al escribirla y, a continuación, proporciona las colecciones <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> y <xref:Microsoft.SqlServer.Dts.Runtime.Connections> de la tarea y el paquete, respectivamente, como parámetros.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-148">When the user interface for a task is invoked, the designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A> method, implemented by the task user interface when you wrote it, and then provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collections of the task and package, respectively, as parameters.</span></span> <span data-ttu-id="fb1e6-149">Estas colecciones se almacenan localmente y se utilizan posteriormente en el método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-149">These collections are stored locally, and used subsequently in the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method.</span></span>  
  
 <span data-ttu-id="fb1e6-150">El diseñador llama al método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> para solicitar la ventana que se muestra en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1e6-150">The designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method to request the window that is displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="fb1e6-151">La tarea crea una instancia de la ventana que contiene la interfaz de usuario para la tarea y devuelve la interfaz de usuario al diseñador para mostrarla.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-151">The task creates an instance of the window that contains the user interface for the task, and returns the user interface to the designer for display.</span></span> <span data-ttu-id="fb1e6-152">Normalmente, los objetos <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> y <xref:Microsoft.SqlServer.Dts.Runtime.Connections> se proporcionan a la ventana a través de un constructor sobrecargado de modo que se puedan utilizar para configurar la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-152">Typically, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> objects are provided to the window through an overloaded constructor so they can be used to configure the task.</span></span>  
  
 <span data-ttu-id="fb1e6-153">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] llama al método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> de la UI de la tarea para mostrar la interfaz de usuario para la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-153">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method of the task UI to display the user interface for the task.</span></span> <span data-ttu-id="fb1e6-154">La interfaz de usuario de la tarea devuelve el formulario Windows Forms de este método y el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] muestra este formulario como un cuadro de diálogo modal.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-154">The task user interface returns the Windows form from this method, and [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer shows this form as a modal dialog box.</span></span> <span data-ttu-id="fb1e6-155">Cuando se cierra el formulario, el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] examina el valor de la propiedad `DialogResult` del formulario para determinar si se ha modificado la tarea y si estas modificaciones se deben guardar.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-155">When the form is closed, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer examines the value of the `DialogResult` property of the form to determine whether the task has been modified and if these modifications should be saved.</span></span> <span data-ttu-id="fb1e6-156">Si el valor de la propiedad `DialogResult` es `OK`, el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] llama a los métodos de persistencia de la tarea para guardar los cambios; de lo contrario, se descartan los cambios.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-156">If the value of the `DialogResult` property is `OK`, the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the persistence methods of the task to save the changes; otherwise, the changes are discarded.</span></span>  
  
 <span data-ttu-id="fb1e6-157">En el ejemplo de código siguiente se implementa la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> y se supone la existencia de una clase de formulario Windows Forms denominada SampleTaskForm.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-157">The following code sample implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface, and assumes the existence of a Windows form class named SampleTaskForm.</span></span>  
  
```csharp  
using System;  
using System.Windows.Forms;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Design;  
  
namespace Sample  
{  
   public class HelloWorldTaskUI : IDtsTaskUI  
   {  
      TaskHost   taskHost;  
      Connections connections;  
      public void Initialize(TaskHost taskHost, IServiceProvider serviceProvider)  
      {  
         this.taskHost = taskHost;  
         IDtsConnectionService cs = serviceProvider.GetService  
         ( typeof( IDtsConnectionService ) ) as   IDtsConnectionService;   
         this.connections = cs.GetConnections();  
      }  
      public ContainerControl GetView()  
      {  
        return new HelloWorldTaskForm(this.taskHost, this.connections);  
      }  
     public void Delete(IWin32Window parentWindow)  
     {  
     }  
     public void New(IWin32Window parentWindow)  
     {  
     }  
   }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Design  
Imports System.Windows.Forms  
  
Public Class HelloWorldTaskUI  
  Implements IDtsTaskUI  
  
  Dim taskHost As TaskHost  
  Dim connections As Connections  
  
  Public Sub Initialize(ByVal taskHost As TaskHost, ByVal serviceProvider As IServiceProvider) _  
    Implements IDtsTaskUI.Initialize  
  
    Dim cs As IDtsConnectionService  
  
    Me.taskHost = taskHost  
    cs = DirectCast(serviceProvider.GetService(GetType(IDtsConnectionService)), IDtsConnectionService)  
    Me.connections = cs.GetConnections()  
  
  End Sub  
  
  Public Function GetView() As ContainerControl _  
    Implements IDtsTaskUI.GetView  
  
    Return New HelloWorldTaskForm(Me.taskHost, Me.connections)  
  
  End Function  
  
  Public Sub Delete(ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.Delete  
  
  End Sub  
  
  Public Sub [New](ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.[New]  
  
  End Sub  
  
End Class  
```  
  
<span data-ttu-id="fb1e6-158">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fb1e6-158">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fb1e6-159">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="fb1e6-159">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fb1e6-160">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="fb1e6-160">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fb1e6-161">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="fb1e6-161">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb1e6-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb1e6-162">See Also</span></span>  
 <span data-ttu-id="fb1e6-163">[Creating a Custom Task](creating-a-custom-task.md)  (Crear una tarea personalizada)</span><span class="sxs-lookup"><span data-stu-id="fb1e6-163">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="fb1e6-164">[Programar una tarea personalizada](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="fb1e6-164">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="fb1e6-165">Desarrollar una interfaz de usuario para una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="fb1e6-165">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
