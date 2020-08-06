---
title: Métodos en tiempo de diseño de un componente de flujo de datos | Microsoft Docs
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
- custom data flow components [Integration Services], method execution sequence
- ProcessInput method
- method execution sequence [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], method execution sequence
ms.assetid: b5a121a1-b87c-441b-a42c-2cec628dc81c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e33fc4eb5805318dac217d2c5cbaedfd4bca70fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674957"
---
# <a name="design-time-methods-of-a-data-flow-component"></a><span data-ttu-id="dade3-102">Métodos en tiempo de diseño de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="dade3-102">Design-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="dade3-103">Antes de la ejecución, se dice que la tarea Flujo de datos se encuentra en un estado en tiempo de diseño, cuando sufre cambios incrementales.</span><span class="sxs-lookup"><span data-stu-id="dade3-103">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="dade3-104">Los cambios pueden incluir la adición o eliminación de los componentes, la adición o eliminación de los objetos de ruta de acceso que conectan los componentes y cambios en los metadatos de los componentes.</span><span class="sxs-lookup"><span data-stu-id="dade3-104">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="dade3-105">Cuando se producen cambios en los metadatos, el componente puede supervisar y reaccionar a los cambios.</span><span class="sxs-lookup"><span data-stu-id="dade3-105">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="dade3-106">Por ejemplo, puede que un componente no permita ciertos cambios o realizar cambios adicionales en respuesta a un cambio.</span><span class="sxs-lookup"><span data-stu-id="dade3-106">For example, a component can disallow certain changes or make additional changes in response to a change.</span></span> <span data-ttu-id="dade3-107">En tiempo de diseño, el diseñador interactúa con un componente a través de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="dade3-107">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>

## <a name="design-time-implementation"></a><span data-ttu-id="dade3-108">Implementación en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="dade3-108">Design-Time Implementation</span></span>
 <span data-ttu-id="dade3-109">La interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> describe la interfaz en tiempo de diseño de un componente.</span><span class="sxs-lookup"><span data-stu-id="dade3-109">The design-time interface of a component is described by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span> <span data-ttu-id="dade3-110">Aunque no implemente explícitamente esta interfaz, algunos conocimientos sobre los métodos definidos en esta interfaz le servirán de ayuda para entender qué métodos de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> corresponden a la instancia en tiempo de diseño de un componente.</span><span class="sxs-lookup"><span data-stu-id="dade3-110">Although you do not explicitly implement this interface, a familiarity with the methods defined in this interface will help you understand which methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class correspond to the design-time instance of a component.</span></span>

 <span data-ttu-id="dade3-111">Cuando se carga un componente en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], se crea la instancia en tiempo de diseño del componente y se llama a los métodos de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> cuando se edita el componente.</span><span class="sxs-lookup"><span data-stu-id="dade3-111">When a component is loaded in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], the design-time instance of the component is instantiated and the methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface are called as the component is edited.</span></span> <span data-ttu-id="dade3-112">La implementación de la clase base le permite invalidar únicamente los métodos que requieren su componente.</span><span class="sxs-lookup"><span data-stu-id="dade3-112">The implementation of the base class lets you override only those methods that your component requires.</span></span> <span data-ttu-id="dade3-113">En muchos casos, puede invalidar estos métodos para impedir las modificaciones inapropiadas a un componente.</span><span class="sxs-lookup"><span data-stu-id="dade3-113">In many cases, you may override these methods to prevent inappropriate edits to a component.</span></span> <span data-ttu-id="dade3-114">Por ejemplo, para evitar que los usuarios agreguen una salida a un componente, invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="dade3-114">For example, to prevent users from adding an output to a component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A> method.</span></span> <span data-ttu-id="dade3-115">De lo contrario, cuando la clase base llama a la implementación de este método, agrega una salida al componente.</span><span class="sxs-lookup"><span data-stu-id="dade3-115">Otherwise, when the implementation of this method by the base class is called, it adds an output to the component.</span></span>

 <span data-ttu-id="dade3-116">Independientemente del propósito o funcionalidad del componente, debería invalidar los métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="dade3-116">Regardless of the purpose or functionality of your component, you should override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> methods.</span></span> <span data-ttu-id="dade3-117">Para obtener más información sobre <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> y <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, vea [Validar un componente de flujo de datos](validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="dade3-117">For more information about <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, see [Validating a Data Flow Component](validating-a-data-flow-component.md).</span></span>

## <a name="providecomponentproperties-method"></a><span data-ttu-id="dade3-118">Método ProvideComponentProperties</span><span class="sxs-lookup"><span data-stu-id="dade3-118">ProvideComponentProperties Method</span></span>
 <span data-ttu-id="dade3-119">La inicialización de un componente se produce en el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="dade3-119">The initialization of a component occurs in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="dade3-120">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] llama a este método cuando se agrega un componente a la tarea de flujo de datos, y es similar a un constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="dade3-120">This method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer when a component is added to the data flow task, and is similar to a class constructor.</span></span> <span data-ttu-id="dade3-121">Los desarrolladores de componentes deberían crear e inicializar sus entradas, salidas y propiedades personalizadas durante esta llamada al método.</span><span class="sxs-lookup"><span data-stu-id="dade3-121">Component developers should create and initialize their inputs, outputs, and custom properties during this method call.</span></span> <span data-ttu-id="dade3-122">El método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> se diferencia de un constructor porque no se llama cada vez que se crea la instancia en tiempo de diseño o la instancia en tiempo de ejecución del componente.</span><span class="sxs-lookup"><span data-stu-id="dade3-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method differs from a constructor because it is not called every time that the design-time instance or run-time instance of the component is instantiated.</span></span>

 <span data-ttu-id="dade3-123">La implementación de la clase base del método agrega una entrada y una salida al componente y asigna el identificador de la entrada a la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="dade3-123">The base class implementation of the method adds an input and an output to the component and assigns the ID of the input to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property.</span></span> <span data-ttu-id="dade3-124">Sin embargo, en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], no se asigna ningún nombre a los objetos de entrada y salida que agrega la clase base.</span><span class="sxs-lookup"><span data-stu-id="dade3-124">However, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the input and output objects added by the base class are not named.</span></span> <span data-ttu-id="dade3-125">Los paquetes que contienen un componente con objetos de entrada o salida cuya propiedad Name no está establecida, no se cargarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="dade3-125">Packages that contain a component with input or output objects whose Name property is not set will not successfully load.</span></span> <span data-ttu-id="dade3-126">Por lo tanto, al usar la implementación base, debe asignar explícitamente valores a la propiedad Name de la entrada y salida predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="dade3-126">Therefore, when you use the base implementation, you must assign values explicitly to the Name property of the default input and output.</span></span>

```csharp
public override void ProvideComponentProperties()
{
    /// TODO: Reset the component.
    /// TODO: Add custom properties.
    /// TODO: Add input objects.
    /// TODO: Add output objects.
}
```

```vb
Public Overrides Sub ProvideComponentProperties()
    ' TODO: Reset the component.
    ' TODO: Add custom properties.
    ' TODO: Add input objects.
    ' TODO: Add output objects.
End Sub
```

### <a name="creating-custom-properties"></a><span data-ttu-id="dade3-127">Crear propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="dade3-127">Creating Custom Properties</span></span>
 <span data-ttu-id="dade3-128">La llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> es donde los desarrolladores de componentes deberían agregar al componente las propiedades personalizadas (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>).</span><span class="sxs-lookup"><span data-stu-id="dade3-128">The call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method is where component developers should add custom properties (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) to the component.</span></span> <span data-ttu-id="dade3-129">Las propiedades personalizadas no tienen una propiedad de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="dade3-129">Custom properties do not have a data type property.</span></span> <span data-ttu-id="dade3-130">El tipo de datos de una propiedad personalizada se establece por el tipo de datos del valor que asigne a su propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="dade3-130">The data type of a custom property is set by the data type of the value that you assign to its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A> property.</span></span> <span data-ttu-id="dade3-131">Sin embargo, después de haber asignado un valor inicial a la propiedad personalizada, no puede asignar un valor con un tipo de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="dade3-131">However, after you have assigned an initial value to the custom property, you cannot assign a value with a different data type.</span></span>

> [!NOTE]
>  <span data-ttu-id="dade3-132">La interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> admite de forma limitada los valores de propiedad de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="dade3-132">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> interface has limited support for property values of type `Object`.</span></span> <span data-ttu-id="dade3-133">El único objeto que puede almacenar como el valor de una propiedad personalizada es una matriz de tipos simples como cadenas o enteros.</span><span class="sxs-lookup"><span data-stu-id="dade3-133">The only object that you can store as the value of a custom property is an array of simple types such as strings or integers.</span></span>

 <span data-ttu-id="dade3-134">Puede indicar que su propiedad personalizada admite las expresiones de propiedad estableciendo el valor de su propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> en `CPET_NOTIFY` de la enumeración <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dade3-134">You can indicate that your custom property supports property expressions by setting the value of its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> property to `CPET_NOTIFY` from the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType> enumeration, as shown in the following example.</span></span> <span data-ttu-id="dade3-135">No tiene que agregar cualquier código para controlar o validar la expresión de propiedad especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="dade3-135">You do not have to add any code to handle or to validate the property expression entered by the user.</span></span> <span data-ttu-id="dade3-136">Puede establecer un valor predeterminado de la propiedad, validar su valor y leer y utilizar su valor normalmente.</span><span class="sxs-lookup"><span data-stu-id="dade3-136">You can set a default value for the property, validate its value, and read and use its value normally.</span></span>

```csharp
IDTSCustomProperty100 myCustomProperty;
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY;
```

```vb
Dim myCustomProperty As IDTSCustomProperty100
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY
```

 <span data-ttu-id="dade3-137">Puede limitar a los usuarios que seleccionen un valor de propiedad personalizado de una enumeración mediante la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> propiedad, como se muestra en el ejemplo siguiente, en el que se supone que ha definido una enumeración pública denominada `MyValidValues` .</span><span class="sxs-lookup"><span data-stu-id="dade3-137">You can limit users to selecting a custom property value from an enumeration by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> property, as shown in the following example, which assumes that you have defined a public enumeration named `MyValidValues`.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the type with the custom property.
customProperty.TypeConverter = typeof(MyValidValues).AssemblyQualifiedName;
// Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne;  
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the type with the custom property.
customProperty.TypeConverter = GetType(MyValidValues).AssemblyQualifiedName 
' Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne
```

 <span data-ttu-id="dade3-138">Para obtener más información, vea "Conversión de tipos generalizada" e "Implementar un convertidor de tipos" en [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="dade3-138">For more information, see "Generalized Type Conversion" and "Implementing a Type Converter" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

 <span data-ttu-id="dade3-139">Puede especificar un cuadro de diálogo del editor personalizado para el valor de su propiedad personalizada mediante la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dade3-139">You can specify a custom editor dialog box for the value of your custom property by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property, as shown in the following example.</span></span> <span data-ttu-id="dade3-140">Primero, debe crear un editor de tipo personalizado que herede de `System.Drawing.Design.UITypeEditor`, si no puede buscar ninguna clase de editor de tipo de interfaz de usuario existente que se ajuste a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="dade3-140">First, you must create a custom type editor that inherits from `System.Drawing.Design.UITypeEditor`, if you cannot locate an existing UI type editor class that fits your needs.</span></span>

```csharp
public class MyCustomTypeEditor : UITypeEditor
{
...
}
```

```vb
Public Class MyCustomTypeEditor
  Inherits UITypeEditor 
  ...
End Class
```

 <span data-ttu-id="dade3-141">A continuación, especifique esta clase como el valor de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> de su propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="dade3-141">Next, specify this class as the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property of your custom property.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the editor with the custom property.
customProperty.UITypeEditor = typeof(MyCustomTypeEditor).AssemblyQualifiedName;
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the editor with the custom property.
customProperty.UITypeEditor = GetType(MyCustomTypeEditor).AssemblyQualifiedName
```

 <span data-ttu-id="dade3-142">Para obtener más información, vea "Implementar un editor de tipo con interfaz de usuario" en [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="dade3-142">For more information, see "Implementing a UI Type Editor" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

<span data-ttu-id="dade3-143">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dade3-143">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dade3-144">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="dade3-144">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dade3-145">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="dade3-145">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dade3-146">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="dade3-146">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="dade3-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dade3-147">See Also</span></span>
 [<span data-ttu-id="dade3-148">Métodos en tiempo de ejecución de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="dade3-148">Run-time Methods of a Data Flow Component</span></span>](run-time-methods-of-a-data-flow-component.md)


