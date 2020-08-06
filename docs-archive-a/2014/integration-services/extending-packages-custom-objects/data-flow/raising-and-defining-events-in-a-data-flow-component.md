---
title: Provocar y definir eventos en un componente de flujo de datos | Microsoft Docs
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
- data flow components [Integration Services], events
- events [Integration Services], custom
- custom events [Integration Services]
- custom data flow components [Integration Services], events
- events [Integration Services], raising
- predefined events [Integration Services]
ms.assetid: 1d8c5358-9384-47a8-b7cb-7b0650384119
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 25f4572f8a8af829145da4e4d685f5dddad4a29a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744779"
---
# <a name="raising-and-defining-events-in-a-data-flow-component"></a><span data-ttu-id="95f9f-102">Provocar y definir eventos en un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="95f9f-102">Raising and Defining Events in a Data Flow Component</span></span>
  <span data-ttu-id="95f9f-103">Los desarrolladores de componentes pueden producir un subconjunto de los eventos definido en la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> mediante una llamada a los métodos expuestos en la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="95f9f-103">Component developers can raise a subset of the events defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface by calling the methods exposed on the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="95f9f-104">También puede definir eventos personalizados con la colección <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> y provocarlos durante la ejecución con el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="95f9f-104">You can also define custom events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection, and raise them during execution by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="95f9f-105">En esta sección se describe cómo crear y provocar un evento y se proporcionan instrucciones sobre el momento en que se deben provocar los eventos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="95f9f-105">This section describes how to create and raise an event, and provides guidelines on when you should raise events at design time.</span></span>

## <a name="raising-events"></a><span data-ttu-id="95f9f-106">Provocar eventos</span><span class="sxs-lookup"><span data-stu-id="95f9f-106">Raising Events</span></span>
 <span data-ttu-id="95f9f-107">Los componentes generan eventos mediante los métodos **Fire\<X>** de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="95f9f-107">Components raise events by using the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="95f9f-108">Puede provocar eventos durante el diseño y la ejecución de los componentes.</span><span class="sxs-lookup"><span data-stu-id="95f9f-108">You can raise events during component design and execution.</span></span> <span data-ttu-id="95f9f-109">Normalmente, en el diseño de los componentes, se llama a los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> durante la validación.</span><span class="sxs-lookup"><span data-stu-id="95f9f-109">Typically, during component design, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> methods are called during validation.</span></span> <span data-ttu-id="95f9f-110">Estos eventos muestran mensajes en el panel **Lista de errores** de [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] y proporcionan información a los usuarios del componente cuando este está configurado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="95f9f-110">These events display messages in the **Error List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] and provide feedback to users of the component when a component is incorrectly configured.</span></span>

 <span data-ttu-id="95f9f-111">Los componentes también pueden provocar eventos en cualquier momento durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="95f9f-111">Components can also raise events at any point during execution.</span></span> <span data-ttu-id="95f9f-112">Los eventos permiten a los programadores de componentes proporcionar información a los usuarios del componente cuando éste se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="95f9f-112">Events allow component developers to provide feedback to users of the component as it executes.</span></span> <span data-ttu-id="95f9f-113">Es probable que la llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> durante la ejecución produzca un error en el paquete.</span><span class="sxs-lookup"><span data-stu-id="95f9f-113">Calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> method during execution is likely to fail the package.</span></span>

## <a name="defining-and-raising-custom-events"></a><span data-ttu-id="95f9f-114">Definir y provocar eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="95f9f-114">Defining and Raising Custom Events</span></span>

### <a name="defining-a-custom-event"></a><span data-ttu-id="95f9f-115">Definir un evento personalizado</span><span class="sxs-lookup"><span data-stu-id="95f9f-115">Defining a Custom Event</span></span>
 <span data-ttu-id="95f9f-116">Los eventos personalizados se crean mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> de la colección <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>.</span><span class="sxs-lookup"><span data-stu-id="95f9f-116">Custom events are created by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection.</span></span> <span data-ttu-id="95f9f-117">La tarea de flujo de datos establece esta colección, que se proporciona al programador de componentes a través de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="95f9f-117">This collection is set by the data flow task and provided as a property to the component developer through the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="95f9f-118">Esta clase contiene eventos personalizados definidos por la tarea de flujo de datos y eventos personalizados definidos por el componente durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>.</span><span class="sxs-lookup"><span data-stu-id="95f9f-118">This class contains custom events defined by the data flow task and custom events defined by the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method.</span></span>

 <span data-ttu-id="95f9f-119">Los eventos personalizados de un componente no se conservan en el paquete XML.</span><span class="sxs-lookup"><span data-stu-id="95f9f-119">The custom events of a component are not persisted in the package XML.</span></span> <span data-ttu-id="95f9f-120">Por tanto, se llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> durante el diseño y la ejecución para permitir al componente definir los eventos que provoca.</span><span class="sxs-lookup"><span data-stu-id="95f9f-120">Therefore, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method is called during both design and execution to allow the component to define the events it raises.</span></span>

 <span data-ttu-id="95f9f-121">El parámetro *allowEventHandlers* del método <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> especifica si el componente permite crear objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> para el evento.</span><span class="sxs-lookup"><span data-stu-id="95f9f-121">The *allowEventHandlers* parameter of the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method specifies whether the component allows <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects to be created for the event.</span></span> <span data-ttu-id="95f9f-122">Observe que los objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> son sincrónicos.</span><span class="sxs-lookup"><span data-stu-id="95f9f-122">Note that <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> are synchronous.</span></span> <span data-ttu-id="95f9f-123">Por tanto, el componente no reanuda la ejecución hasta que ha terminado de ejecutarse un objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> adjuntado al evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="95f9f-123">Therefore the component does not resume execution until an <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> attached to the custom event has finished executing.</span></span> <span data-ttu-id="95f9f-124">Si el parámetro *allowEventHandlers* es `true` , cada parámetro del evento pasa a estar disponible automáticamente para cualquier <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objeto a través de variables que se crean y rellenan automáticamente en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="95f9f-124">If the *allowEventHandlers* parameter is `true`, each parameter of the event is automatically made available to any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects through variables that are created and populated automatically by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

### <a name="raising-a-custom-event"></a><span data-ttu-id="95f9f-125">Provocar un evento personalizado</span><span class="sxs-lookup"><span data-stu-id="95f9f-125">Raising a Custom Event</span></span>
 <span data-ttu-id="95f9f-126">Los componentes provocan eventos personalizados mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> y proporcionando el nombre, texto y parámetros del evento.</span><span class="sxs-lookup"><span data-stu-id="95f9f-126">Components raise custom events by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method, and providing the name, text, and parameters of the event.</span></span> <span data-ttu-id="95f9f-127">Si el parámetro *allowEventHandlers* es `true` , <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> el motor en tiempo de ejecución ejecuta cualquier que se cree para el evento personalizado [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95f9f-127">If the *allowEventHandlers* parameter is `true`, any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> that are created for the custom event are executed by the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] run-time engine.</span></span>

### <a name="custom-event-sample"></a><span data-ttu-id="95f9f-128">Ejemplo de evento personalizado</span><span class="sxs-lookup"><span data-stu-id="95f9f-128">Custom Event Sample</span></span>
 <span data-ttu-id="95f9f-129">En el ejemplo de código siguiente se muestra un componente que define un evento personalizado durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> y, a continuación, provoca el evento en tiempo de ejecución mediante una llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="95f9f-129">The following code example shows a component that defines a custom event during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method, and then raises the event at run time by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span>

```csharp
public override void RegisterEvents()
{
    string [] parameterNames = new string[2]{"RowCount", "StartTime"};
    ushort [] parameterTypes = new ushort[2]{ DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)};
    string [] parameterDescriptions = new string[2]{"The number of rows to sort.", "The start time of the Sort operation."};
    EventInfos.Add("StartingSort","Fires when the component begins sorting the rows.",false,ref parameterNames, ref parameterTypes, ref parameterDescriptions);
}
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
    while (buffer.NextRow())
    {
       // Process buffer rows.
    }

    IDTSEventInfo100 eventInfo = EventInfos["StartingSort"];
    object []arguments = new object[2]{buffer.RowCount, DateTime.Now };
    ComponentMetaData.FireCustomEvent("StartingSort", "Beginning sort operation.", ref arguments, ComponentMetaData.Name, ref FireSortEventAgain);
}
```

```vb
Public  Overrides Sub RegisterEvents() 
  Dim parameterNames As String() = New String(2) {"RowCount", "StartTime"} 
  Dim parameterTypes As System.UInt16() = New System.UInt16(2) {DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)} 
  Dim parameterDescriptions As String() = New String(2) {"The number of rows to sort.", "The start time of the Sort operation."} 
  EventInfos.Add("StartingSort", "Fires when the component begins sorting the rows.", False, parameterNames, parameterTypes, parameterDescriptions) 
End Sub 

Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
  While buffer.NextRow 
  End While 
  Dim eventInfo As IDTSEventInfo100 = EventInfos("StartingSort") 
  Dim arguments As Object() = New Object(2) {buffer.RowCount, DateTime.Now} 
  ComponentMetaData.FireCustomEvent("StartingSort", _
    "Beginning sort operation.", arguments, _
    ComponentMetaData.Name, FireSortEventAgain) 
End Sub
```

<span data-ttu-id="95f9f-130">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="95f9f-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="95f9f-131">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="95f9f-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="95f9f-132">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="95f9f-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="95f9f-133">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="95f9f-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="95f9f-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95f9f-134">See Also</span></span>
 <span data-ttu-id="95f9f-135">[Integration Services los controladores de eventos de &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) [Agregar un controlador de eventos a un paquete](../../add-an-event-handler-to-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="95f9f-135">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) [Add an Event Handler to a Package](../../add-an-event-handler-to-a-package.md)</span></span>


