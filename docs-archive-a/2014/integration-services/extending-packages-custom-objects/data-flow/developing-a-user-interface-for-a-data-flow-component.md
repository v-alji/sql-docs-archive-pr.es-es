---
title: Desarrollar una interfaz de usuario para un componente de flujo de datos | Microsoft Docs
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
- data flow components [Integration Services], custom editors
- user interfaces [Integration Services]
- custom data flow components [Integration Services], custom editors
- custom component editors [Integration Services]
- IDtsComponentUI interface
- UITypeName property
- custom user interface [Integration Services], custom data flow component
- editors [Integration Services]
ms.assetid: 10b829a1-609b-42e3-9070-cfe5a2bb698c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f97f21ad14a5fa67fb49192931a0cb46d0cb41da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744790"
---
# <a name="developing-a-user-interface-for-a-data-flow-component"></a><span data-ttu-id="3e8b0-102">Desarrollar una interfaz de usuario para un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="3e8b0-102">Developing a User Interface for a Data Flow Component</span></span>
  <span data-ttu-id="3e8b0-103">Los desarrolladores de componentes pueden proporcionar una interfaz de usuario personalizada para un componente, que se muestre en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] cuando se edite el componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-103">Component developers can provide a custom user interface for a component, which is displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] when the component is edited.</span></span> <span data-ttu-id="3e8b0-104">La implementación de una interfaz de usuario personalizada proporciona notificaciones cuando el componente se agrega o se elimina en una tarea de flujo de datos, así como cuando se solicita ayuda para el componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-104">Implementing a custom user interface provides you with notification when the component is added to or deleted from a data flow task, and when help is requested for the component.</span></span>

 <span data-ttu-id="3e8b0-105">Aunque no proporcione una interfaz de usuario personalizada para su componente, los usuarios podrán configurar el componente y sus propiedades personalizadas mediante el editor avanzado.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-105">If you do not provide a custom user interface for your component, users can still configure the component and its custom properties by using the Advanced Editor.</span></span> <span data-ttu-id="3e8b0-106">Para asegurarse de que el editor avanzado permita a los usuarios editar los valores de las propiedades personalizadas de forma adecuada, use las propiedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> cuando proceda.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-106">You can ensure that the Advanced Editor allows users to edit custom property values appropriately by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> properties of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> when appropriate.</span></span> <span data-ttu-id="3e8b0-107">Para obtener más información, consulte la sección "Creating Custom Properties (Crear propiedades personalizadas)" en [Design-time Methods of a Data Flow Component (Métodos en tiempo de diseño de un componente de flujo de datos)](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="3e8b0-107">For more information, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>

## <a name="setting-the-uitypename-property"></a><span data-ttu-id="3e8b0-108">Establecer la propiedad UITypeName</span><span class="sxs-lookup"><span data-stu-id="3e8b0-108">Setting the UITypeName Property</span></span>
 <span data-ttu-id="3e8b0-109">Para proporcionar una interfaz de usuario personalizada, el desarrollador debe establecer la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> en el nombre de una clase que implemente la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-109">To provide a custom user interface, the developer must set the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> to the name of a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="3e8b0-110">Cuando el componente establece esta propiedad, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] carga y llama a la interfaz de usuario personalizada mientras el componente se edita en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e8b0-110">When this property is set by the component, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] loads and calls the custom user interface when the component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="3e8b0-111">La propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> es una cadena delimitada por comas que identifica el nombre completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property is a comma-delimited string that identifies the fully qualified name of the type.</span></span> <span data-ttu-id="3e8b0-112">En la lista siguiente se muestran en orden los elementos que identifican el tipo:</span><span class="sxs-lookup"><span data-stu-id="3e8b0-112">The following list shows, in order, the elements that identify the type:</span></span>

-   <span data-ttu-id="3e8b0-113">Nombre del tipo</span><span class="sxs-lookup"><span data-stu-id="3e8b0-113">Type name</span></span>

-   <span data-ttu-id="3e8b0-114">Nombre del ensamblado</span><span class="sxs-lookup"><span data-stu-id="3e8b0-114">Assembly name</span></span>

-   <span data-ttu-id="3e8b0-115">Versión del archivo</span><span class="sxs-lookup"><span data-stu-id="3e8b0-115">File version</span></span>

-   <span data-ttu-id="3e8b0-116">Referencia cultural</span><span class="sxs-lookup"><span data-stu-id="3e8b0-116">Culture</span></span>

-   <span data-ttu-id="3e8b0-117">Token de clave pública</span><span class="sxs-lookup"><span data-stu-id="3e8b0-117">Public key token</span></span>

 <span data-ttu-id="3e8b0-118">En el ejemplo de código siguiente se muestra una clase que deriva de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> y especifica la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-118">The following code example shows a class that derives from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class and specifies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property.</span></span>

```csharp
[DtsPipelineComponent(
DisplayName="SampleComponent",
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...",
ComponentType = ComponentType.Transform)]
public class SampleComponent : PipelineComponent
{
//TODO: Implement the component here.
}
```

```vb
<DtsPipelineComponent(DisplayName="SampleComponent", _
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...", ComponentType=ComponentType.Transform)> _ 
Public Class SampleComponent 
 Inherits PipelineComponent 
End Class
```

## <a name="implementing-the-idtscomponentui-interface"></a><span data-ttu-id="3e8b0-119">Implementar la interfaz IDtsComponentUI</span><span class="sxs-lookup"><span data-stu-id="3e8b0-119">Implementing the IDtsComponentUI Interface</span></span>
 <span data-ttu-id="3e8b0-120">La interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> contiene métodos a los que llama el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] cuando se agrega, elimina o edita un componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-120">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface contains methods that [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls when a component is added, deleted, and edited.</span></span> <span data-ttu-id="3e8b0-121">Los desarrolladores de componentes pueden proporcionar código en su implementación de estos métodos para interactuar con los usuarios del componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-121">Component developers can provide code in their implementation of these methods to interact with users of the component.</span></span>

 <span data-ttu-id="3e8b0-122">Normalmente, esta clase se implementa en un ensamblado independiente del propio componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-122">This class is typically implemented in an assembly separate from the component itself.</span></span> <span data-ttu-id="3e8b0-123">Aunque no se requiere el uso de un ensamblado independiente, esto permite al desarrollador generar e implementar el componente y la interfaz de usuario de forma independiente entre sí y mantiene una superficie binaria reducida del componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-123">Although use of a separate assembly is not required, this lets the developer build and deploy the component and the user interface independently of each other, and keeps the binary footprint of the component small.</span></span>

 <span data-ttu-id="3e8b0-124">La implementación de una interfaz de usuario personalizada proporciona al desarrollador de componentes un mayor control sobre el componente al editarlo en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e8b0-124">Implementing a custom user interface gives the component developer more control over the component as it is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="3e8b0-125">Por ejemplo, un componente puede agregar código al método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> (al que se llama cuando un componente se agrega inicialmente a una tarea de flujo de datos) y mostrar un asistente que guía al usuario a lo largo del proceso de configuración inicial del componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-125">For example, a component can add code to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> method, which is called when a component is initially added to a data flow task, and display a wizard that guides the user through the initial configuration of the component.</span></span>

 <span data-ttu-id="3e8b0-126">Después de haber creado una clase que implementa la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, debe agregar código para responder a la interacción del usuario con el componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-126">After you have created a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, you must add code to respond to user interaction with the component.</span></span> <span data-ttu-id="3e8b0-127">El método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> proporciona la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> del componente y se llama a este método antes que a los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-127">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component, and is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> methods.</span></span> <span data-ttu-id="3e8b0-128">Esta referencia debería almacenarse en una variable miembro privada y usarse para modificar los metadatos del componente posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-128">This reference should be stored in a private member variable and used to modify the component's metadata thereafter.</span></span>

## <a name="modifying-a-component-and-persisting-changes"></a><span data-ttu-id="3e8b0-129">Modificar un componente y conservar los cambios</span><span class="sxs-lookup"><span data-stu-id="3e8b0-129">Modifying a Component and Persisting Changes</span></span>
 <span data-ttu-id="3e8b0-130">La interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> se proporciona como parámetro para el método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-130">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface is provided as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method.</span></span> <span data-ttu-id="3e8b0-131">Esta referencia debería almacenarse en caché en una variable miembro mediante el código de interfaz de usuario y usarse después para modificar el componente como respuesta a la interacción del usuario con la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-131">This reference should be cached in a member variable by the user interface code, and then used to modify the component in response to user interaction with the user interface.</span></span>

 <span data-ttu-id="3e8b0-132">Aunque puede modificar directamente el componente a través de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, es mejor crear una instancia de <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> mediante el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-132">Although you can modify the component directly through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, it is better to create an instance of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method.</span></span> <span data-ttu-id="3e8b0-133">Al editar el componente directamente con la interfaz, se omiten las medidas de seguridad de validación del componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-133">When you edit the component directly by using the interface, you bypass the component's validation safeguards.</span></span> <span data-ttu-id="3e8b0-134">La ventaja de usar la instancia en tiempo de diseño del componente mediante <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> es que se asegura de que el componente tenga control sobre los cambios realizados en él.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-134">The advantage of using the design-time instance of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> is that you ensure that the component has control over the changes made to it.</span></span>

 <span data-ttu-id="3e8b0-135">El valor devuelto por el método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> determina si se conservan o se descartan los cambios realizados en un componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-135">The return value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method determines whether changes made to a component are persisted or discarded.</span></span> <span data-ttu-id="3e8b0-136">Cuando este método devuelve `false`, se descartan todos los cambios; si devuelve `true`, se conservan los cambios realizados en el componente y el paquete se marca con la indicación de que debe guardarse.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-136">When this method returns `false`, all changes are discarded; `true` persists the changes to the component and marks the package as needing to be saved.</span></span>

### <a name="using-the-services-of-the-ssis-designer"></a><span data-ttu-id="3e8b0-137">Usar los servicios del Diseñador SSIS</span><span class="sxs-lookup"><span data-stu-id="3e8b0-137">Using the Services of the SSIS Designer</span></span>
 <span data-ttu-id="3e8b0-138">El parámetro `IServiceProvider` del método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> proporciona acceso a los siguientes servicios del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3e8b0-138">The `IServiceProvider` parameter of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides access to the following services of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer:</span></span>

|<span data-ttu-id="3e8b0-139">Servicio</span><span class="sxs-lookup"><span data-stu-id="3e8b0-139">Service</span></span>|<span data-ttu-id="3e8b0-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e8b0-140">Description</span></span>|
|-------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsClipboardService>|<span data-ttu-id="3e8b0-141">Se usa para determinar si el componente se generó como parte de una operación de copiar y pegar o de cortar y pegar.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-141">Used to determine whether the component was generated as part of a copy/paste or cut/paste operation.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionService>|<span data-ttu-id="3e8b0-142">Se usa para obtener acceso a las conexiones existentes o crear nuevas conexiones en el paquete.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-142">Used to access existing connections or to create new connections in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IErrorCollectionService>|<span data-ttu-id="3e8b0-143">Se usa para capturar eventos de los componentes de flujo de datos cuando es necesario capturar todos los errores y advertencias generados por el componente en lugar de recibir solamente el último error o advertencia.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-143">Used to capture events from data flow components when you need to capture all the errors and warnings raised by the component instead of receiving only the last error or warning.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsVariableService>|<span data-ttu-id="3e8b0-144">Se usa para obtener acceso a las variables existentes o para crear nuevas variables en el paquete.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-144">Used to access existing variables or to create new variables in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsPipelineEnvironmentService>|<span data-ttu-id="3e8b0-145">Lo usan los componentes de flujo de datos para obtener acceso a la tarea Flujo de datos primaria y a otros componentes del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-145">Used by data flow components to access the parent Data Flow task and other components in the data flow.</span></span> <span data-ttu-id="3e8b0-146">Esta característica podría usarse para desarrollar un componente como el Asistente para dimensiones de variación lenta, que crea y conecta componentes de flujo de datos adicionales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-146">This feature could be used to develop a component like the Slowly Changing Dimension Wizard that creates and connects additional data flow components as needed.</span></span>|

 <span data-ttu-id="3e8b0-147">Estos servicios proporcionan a los desarrolladores de componentes la capacidad de crear objetos en el paquete donde se carga el componente y de obtener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-147">These services provide component developers the ability to access and create objects in the package in which the component is loaded.</span></span>

## <a name="sample"></a><span data-ttu-id="3e8b0-148">Muestra</span><span class="sxs-lookup"><span data-stu-id="3e8b0-148">Sample</span></span>
 <span data-ttu-id="3e8b0-149">En el ejemplo de código siguiente se muestra la integración de una clase de interfaz de usuario personalizada que implementa la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> y un formulario Windows Forms que actúa como editor de un componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-149">The following code example shows the integration of a custom user interface class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, and a Windows form that serves as the editor for a component.</span></span>

### <a name="custom-user-interface-class"></a><span data-ttu-id="3e8b0-150">Clase de interfaz de usuario personalizada</span><span class="sxs-lookup"><span data-stu-id="3e8b0-150">Custom User Interface Class</span></span>
 <span data-ttu-id="3e8b0-151">El código siguiente muestra la clase que implementa la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-151">The following code shows the class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="3e8b0-152">El método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> crea el editor de componentes y, a continuación, muestra el formulario.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-152">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method creates the component editor and then displays the form.</span></span> <span data-ttu-id="3e8b0-153">El valor devuelto por el formulario determina si se conservan los cambios realizados en el componente.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-153">The return value of the form determines whether changes to the component are persisted.</span></span>

```csharp
using System;
using System.Windows.Forms;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Pipeline.Design;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    public class SampleComponentUI : IDtsComponentUI
    {
        IDTSComponentMetaData100 md;
        IServiceProvider sp;

        public void Help(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void New(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void Delete(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Variables vars, Connections cons)
        {
            // Create and display the form for the user interface.
            SampleComponentUIForm componentEditor = new SampleComponentUIForm(cons, vars, md);

            DialogResult result  = componentEditor.ShowDialog(parentWindow);

            if (result == DialogResult.OK)
                return true;

            return false;
        }
        public void Initialize(IDTSComponentMetaData100 dtsComponentMetadata, IServiceProvider serviceProvider)
        {
            // Store the component metadata.
            this.md = dtsComponentMetadata;
        }
    }
}
```

```vb
Imports System 
Imports System.Windows.Forms 
Imports Microsoft.SqlServer.Dts.Runtime 
Imports Microsoft.SqlServer.Dts.Pipeline.Design 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Class SampleComponentUI 
 Implements IDtsComponentUI 
   Private md As IDTSComponentMetaData100 
   Private sp As IServiceProvider 

   Public Sub Help(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub New(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub Delete(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal vars As Variables, ByVal cons As Connections) As Boolean 
     ' Create and display the form for the user interface.
     Dim componentEditor As SampleComponentUIForm = New SampleComponentUIForm(cons, vars, md) 
     Dim result As DialogResult = componentEditor.ShowDialog(parentWindow) 
     If result = DialogResult.OK Then 
       Return True 
     End If 
     Return False 
   End Function 

   Public Sub Initialize(ByVal dtsComponentMetadata As IDTSComponentMetaData100, ByVal serviceProvider As IServiceProvider) 
     Me.md = dtsComponentMetadata 
   End Sub 
 End Class 

End Namespace
```

### <a name="custom-editor"></a><span data-ttu-id="3e8b0-154">Editor personalizado</span><span class="sxs-lookup"><span data-stu-id="3e8b0-154">Custom Editor</span></span>
 <span data-ttu-id="3e8b0-155">El código siguiente muestra la implementación del formulario Windows Forms que se muestra durante la llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-155">The following code shows the implementation of the Windows form that is shown during the call to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method.</span></span>

```csharp
using System;
using System.Drawing;
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using System.Data;

using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    public partial class SampleComponentUIForm : System.Windows.Forms.Form
    {
        private Connections connections;
        private Variables variables;
        private IDTSComponentMetaData100 metaData;
        private CManagedComponentWrapper designTimeInstance;
        private System.ComponentModel.IContainer components = null;

        public SampleComponentUIForm( Connections cons, Variables vars, IDTSComponentMetaData100 md)
        {
            variables = vars;
            connections = cons;
            metaData = md;
        }

        private void btnOk_Click(object sender, System.EventArgs e)
        {
            if (designTimeInstance == null)
                designTimeInstance = metaData.Instantiate();

            designTimeInstance.SetComponentProperty( "CustomProperty", txtCustomPropertyValue.Text);

            this.Close();
        }

        private void btnCancel_Click(object sender, System.EventArgs e)
        {
            this.Close();
        }
    }
}
```

```vb
Imports System 
Imports System.Drawing 
Imports System.Collections 
Imports System.ComponentModel 
Imports System.Windows.Forms 
Imports System.Data 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Partial Class SampleComponentUIForm 
  Inherits System.Windows.Forms.Form 
   Private connections As Connections 
   Private variables As Variables 
   Private metaData As IDTSComponentMetaData100 
   Private designTimeInstance As CManagedComponentWrapper 
   Private components As System.ComponentModel.IContainer = Nothing 

   Public Sub New(ByVal cons As Connections, ByVal vars As Variables, ByVal md As IDTSComponentMetaData100) 
     variables = vars 
     connections = cons 
     metaData = md 
   End Sub 

   Private Sub btnOk_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     If designTimeInstance Is Nothing Then 
       designTimeInstance = metaData.Instantiate 
     End If 
     designTimeInstance.SetComponentProperty("CustomProperty", txtCustomPropertyValue.Text) 
     Me.Close 
   End Sub 

   Private Sub btnCancel_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     Me.Close 
   End Sub 
 End Class 

End Namespace
```

<span data-ttu-id="3e8b0-156">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3e8b0-156">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3e8b0-157">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="3e8b0-157">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3e8b0-158">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="3e8b0-158">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3e8b0-159">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="3e8b0-159">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e8b0-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e8b0-160">See Also</span></span>
 [<span data-ttu-id="3e8b0-161">Crear un componente de flujo de datos personalizado</span><span class="sxs-lookup"><span data-stu-id="3e8b0-161">Creating a Custom Data Flow Component</span></span>](creating-a-custom-data-flow-component.md)


