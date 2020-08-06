---
title: Crear un componente de tiempo de diseño de elemento de informe personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: 323fd58a-a462-4c48-b188-77ebc0b4212e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b663dc3b0a9c54d1674bf153ee09dd36e0de7a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662672"
---
# <a name="creating-a-custom-report-item-design-time-component"></a><span data-ttu-id="9b7cd-102">Crear un componente de tiempo de diseño de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="9b7cd-102">Creating a Custom Report Item Design-Time Component</span></span>
  <span data-ttu-id="9b7cd-103">Un componente de tiempo de diseño de elemento de informe personalizado es un control que se puede utilizar en el entorno de Visual Studio Report Designer.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-103">A custom report item design-time component is a control that can be used in the Visual Studio Report Designer environment.</span></span> <span data-ttu-id="9b7cd-104">El componente de tiempo de diseño de elemento de informe personalizado proporciona una superficie de diseño activada que puede aceptar las operaciones de arrastrar y colocar, la integración con el explorador de propiedades de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], y la capacidad de proporcionar los editores de propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-104">The custom report item design-time component provides an activated design surface that can accept drag-and-drop operations, integration with the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser, and the ability to provide custom property editors.</span></span>  
  
 <span data-ttu-id="9b7cd-105">Con un componente de tiempo de diseño de elemento de informe personalizado, el usuario puede colocar un elemento de informe personalizado en un informe en el entorno de diseño, establecer las propiedades de datos personalizadas en el elemento de informe personalizado y, a continuación, guardar el elemento de informe personalizado como parte del proyecto de informe.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-105">With a custom report item design-time component, the user can position a custom report item on a report in the design environment, set custom data properties on the custom report item, and then save the custom report item as part of the report project.</span></span>  
  
 <span data-ttu-id="9b7cd-106">Las propiedades que se establecen utilizando el componente de tiempo de diseño en el entorno de desarrollo se serializan y deserializan por el entorno de diseño del host y, a continuación, se guardan como elementos en el archivo de lenguaje RDL (Report Definition Language).</span><span class="sxs-lookup"><span data-stu-id="9b7cd-106">The properties that are set using the design-time component in the development environment are serialized and deserialized by the host design environment and then stored as elements in the Report Definition Language (RDL) file.</span></span> <span data-ttu-id="9b7cd-107">Cuando el procesador de informes ejecuta el informe, pasa las propiedades que están establecidas utilizando el componente de tiempo de diseño a un componente de tiempo de ejecución del elemento de informe personalizado, que representa el elemento de informe personalizado y lo devuelve al procesador de informes.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-107">When the report is executed by the report processor, the properties that are set using the design-time component are passed by the report processor to a custom report item run-time component, which renders the custom report item and passes it back to the report processor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b7cd-108">El componente de tiempo de diseño de elemento de informe personalizado se implementa como un componente de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b7cd-108">The custom report item design-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component.</span></span> <span data-ttu-id="9b7cd-109">En este documento se describirán los detalles de la implementación específicos al componente de tiempo de diseño del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-109">This document will describe implementation details specific to the custom report item design-time component.</span></span> <span data-ttu-id="9b7cd-110">Para más información sobre cómo desarrollar componentes mediante [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vea [Componentes en Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-110">For more information about developing components using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see [Components in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) in the MSDN library.</span></span>  
  
 <span data-ttu-id="9b7cd-111">Para obtener un ejemplo de un elemento de informe personalizado totalmente implementado, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="9b7cd-111">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="implementing-a-design-time-component"></a><span data-ttu-id="9b7cd-112">Implementar un componente de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9b7cd-112">Implementing a Design-Time Component</span></span>  
 <span data-ttu-id="9b7cd-113">La clase principal de un componente de tiempo de diseño de elemento de informe personalizado está heredada de la clase `Microsoft.ReportDesigner.CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-113">The main class of a custom report item design-time component is inherited from the `Microsoft.ReportDesigner.CustomReportItemDesigner` class.</span></span> <span data-ttu-id="9b7cd-114">Además de los atributos estándar utilizados para un control [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], la clase de componente debería definir un atributo `CustomReportItem`.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-114">In addition to the standard attributes used for a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] control, your component class should define a `CustomReportItem` attribute.</span></span> <span data-ttu-id="9b7cd-115">Este atributo debe corresponder al nombre del elemento de informe personalizado como se define en el archivo reportserver.config.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-115">This attribute must correspond to the name of the custom report item as it is defined in the reportserver.config file.</span></span> <span data-ttu-id="9b7cd-116">Para obtener una lista de atributos [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vea Atributos en la documentación de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-116">For a list of [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] attributes, see Attributes in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
 <span data-ttu-id="9b7cd-117">El ejemplo de código siguiente muestra atributos que se aplican a un control de tiempo de diseño del elemento de informe personalizado:</span><span class="sxs-lookup"><span data-stu-id="9b7cd-117">The following code example shows attributes being applied to a custom report item design-time control:</span></span>  
  
```csharp  
namespace PolygonsCRI  
{  
    [LocalizedName("Polygons")]  
    [Editor(typeof(CustomEditor), typeof(ComponentEditor))]  
        [ToolboxBitmap(typeof(PolygonsDesigner),"Polygons.ico")]  
        [CustomReportItem("Polygons")]  
  
    public class PolygonsDesigner : CustomReportItemDesigner  
    {  
...  
```  
  
### <a name="initializing-the-component"></a><span data-ttu-id="9b7cd-118">Inicializar el componente</span><span class="sxs-lookup"><span data-stu-id="9b7cd-118">Initializing the Component</span></span>  
 <span data-ttu-id="9b7cd-119">Las propiedades especificadas por el usuario para un elemento de informe personalizado se pasan utilizando una clase <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-119">You pass user-specified properties for a custom report item using a <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class.</span></span> <span data-ttu-id="9b7cd-120">La implementación de la clase `CustomReportItemDesigner` debería invalidar el método `InitializeNewComponent` para crear una nueva instancia de la clase <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> del componente y establecerla en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-120">Your implementation of the `CustomReportItemDesigner` class should override the `InitializeNewComponent` method to create a new instance of your component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class and set it to default values.</span></span>  
  
 <span data-ttu-id="9b7cd-121">El ejemplo de código siguiente muestra un ejemplo de un una clase de componente de tiempo de tiempo de diseño de elemento de informe personalizado que invalida el método `CustomReportItemDesigner.InitializeNewComponent` para inicializar la clase <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> del componente:</span><span class="sxs-lookup"><span data-stu-id="9b7cd-121">The following code example shows an example of a custom report item design-time component class overriding the `CustomReportItemDesigner.InitializeNewComponent` method to initialize the component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class:</span></span>  
  
```csharp  
public override void InitializeNewComponent()  
        {  
            CustomData = new CustomData();  
            CustomData.DataRowHierarchy = new DataHierarchy();  
  
            // Shape grouping  
            CustomData.DataRowHierarchy.DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].Group.Name = Name + "_Shape";  
            CustomData.DataRowHierarchy.DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Point grouping  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.Name = Name + "_Point";  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Static column  
            CustomData.DataColumnHierarchy = new DataHierarchy();  
            CustomData.DataColumnHierarchy.DataMembers.Add(new DataMember());  
  
            // Points  
            IList<IList<DataValue>> dataValues = new List<IList<DataValue>>();  
            CustomData.DataRows.Add(dataValues);  
            CustomData.DataRows[0].Add(new List<DataValue>());  
            CustomData.DataRows[0][0].Add(NewDataValue("X", ""));  
            CustomData.DataRows[0][0].Add(NewDataValue("Y", ""));  
        }  
```  
  
### <a name="modifying-component-properties"></a><span data-ttu-id="9b7cd-122">Modificar propiedades de componentes</span><span class="sxs-lookup"><span data-stu-id="9b7cd-122">Modifying Component Properties</span></span>  
 <span data-ttu-id="9b7cd-123">Puede modificar las propiedades `CustomData` en el entorno de diseño de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-123">You can modify `CustomData` properties in the design environment in several ways.</span></span> <span data-ttu-id="9b7cd-124">Puede modificar cualquier propiedad que expuesta por el componente de tiempo de diseño que esté marcada con el atributo <xref:System.ComponentModel.BrowsableAttribute> utilizando el explorador de propiedades de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b7cd-124">You can modify any properties that are exposed by the design-time component that are marked with the <xref:System.ComponentModel.BrowsableAttribute> attribute by using the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser.</span></span> <span data-ttu-id="9b7cd-125">Además, puede modificar las propiedades si arrastra los elementos a la superficie de diseño del elemento de informe personalizado o si hace clic con el botón derecho en el control en el entorno de diseño y selecciona **Propiedades** en el menú contextual para mostrar una ventana de propiedades personalizada.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-125">In addition, you can modify properties by dragging items onto the custom report item's design surface, or by right-clicking the control in the design environment and selecting **Properties** on the shortcut menu to display a custom properties window.</span></span>  
  
 <span data-ttu-id="9b7cd-126">El ejemplo de código siguiente muestra una propiedad `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` que tiene el atributo <xref:System.ComponentModel.BrowsableAttribute> aplicado:</span><span class="sxs-lookup"><span data-stu-id="9b7cd-126">The following code example shows a `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` property that has the <xref:System.ComponentModel.BrowsableAttribute> attribute applied:</span></span>  
  
```csharp  
[Browsable(true), Category("Data")]  
public string DataSetName  
{  
      get  
      {  
         return CustomData.DataSetName;  
      }  
      set  
      {  
         CustomData.DataSetName = value;  
      }  
   }  
  
```  
  
 <span data-ttu-id="9b7cd-127">Puede proporcionar un cuadro de diálogo de editor de propiedades personalizado al componente de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-127">You can provide your design-time component with a custom properties editor dialog box.</span></span> <span data-ttu-id="9b7cd-128">La implementación personalizada del editor de propiedades debería heredar de la clase <xref:System.ComponentModel.ComponentEditor> y debería crear una instancia de un cuadro de diálogo que se puede utilizar para la edición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-128">The custom property editor implementation should inherit from the <xref:System.ComponentModel.ComponentEditor> class, and it should create an instance of a dialog box that can be used for property editing.</span></span>  
  
 <span data-ttu-id="9b7cd-129">En el ejemplo siguiente se muestra una implementación de una clase que hereda de <xref:System.ComponentModel.ComponentEditor> y muestra un cuadro de diálogo de editor de propiedades personalizado:</span><span class="sxs-lookup"><span data-stu-id="9b7cd-129">The following example shows an implementation of a class that inherits from <xref:System.ComponentModel.ComponentEditor> and displays a custom property editor dialog box:</span></span>  
  
```csharp  
internal sealed class CustomEditor : ComponentEditor  
{  
   public override bool EditComponent(  
      ITypeDescriptorContext context, object component)  
    {  
     PolygonsDesigner designer = (PolygonsDesigner)component;  
     PolygonProperties dialog = new PolygonProperties();  
     dialog.m_designerComponent = designer;  
     DialogResult result = dialog.ShowDialog();  
     if (result == DialogResult.OK)  
     {  
        designer.Invalidate();  
        designer.ChangeService().OnComponentChanged(designer, null, null, null);  
        return true;  
     }  
     else  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="9b7cd-130">El cuadro de diálogo de editor de propiedades personalizado puede invocar al editor de expresiones del diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-130">Your custom property editor dialog box can invoke the Report Designer Expression Editor.</span></span> <span data-ttu-id="9b7cd-131">En el ejemplo siguiente, el editor de expresiones se invoca cuando el usuario selecciona el primer elemento del cuadro combinado:</span><span class="sxs-lookup"><span data-stu-id="9b7cd-131">In the following example, the Expression Editor is invoked when the user selects the first element in the combo box:</span></span>  
  
```csharp  
private void EditableCombo_SelectedIndexChanged(object sender,   
    EventArgs e)  
{  
   ComboBox combo = (ComboBox)sender;  
   if (combo.SelectedIndex == 0 && m_launchEditor)  
   {  
      m_launchEditor = false;  
      ExpressionEditor editor = new ExpressionEditor();  
      string newValue;  
      newValue = (string)editor.EditValue(null, m_designerComponent.Site, m_oldComboValue);  
      combo.Items[0] = newValue;  
   }  
}  
  
```  
  
### <a name="using-designer-verbs"></a><span data-ttu-id="9b7cd-132">Utilizar los verbos de diseñador</span><span class="sxs-lookup"><span data-stu-id="9b7cd-132">Using Designer Verbs</span></span>  
 <span data-ttu-id="9b7cd-133">Un verbo de diseñador es un comando de menú vinculado a un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-133">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="9b7cd-134">Puede agregar verbos de diseñador que aparecerán en el menú contextual de un componente cuando el control de tiempo de ejecución del elemento de informe personalizado se utiliza en el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-134">You can add designer verbs that will appear in a component's shortcut menu when your custom report item run-time control is being used in the design environment.</span></span> <span data-ttu-id="9b7cd-135">Puede devolver la lista de verbos de diseñador disponibles desde el componente de tiempo de ejecución utilizando la propiedad `Verbs`.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-135">You can return the list of available designer verbs from your run-time component by using the `Verbs` property.</span></span>  
  
 <span data-ttu-id="9b7cd-136">El ejemplo de código siguiente muestra un verbo de diseñador y un controlador de eventos agregados a <xref:System.ComponentModel.Design.DesignerVerbCollection>, así como el código de controlador de eventos:</span><span class="sxs-lookup"><span data-stu-id="9b7cd-136">The following code example shows a designer verb and an event handler being added to the <xref:System.ComponentModel.Design.DesignerVerbCollection>, as well as the event handler code:</span></span>  
  
```csharp  
public override DesignerVerbCollection Verbs  
{  
    get  
    {  
        if (m_verbs == null)  
        {  
            m_verbs = new DesignerVerbCollection();  
            m_verbs.Add(new DesignerVerb("Proportional Scaling", new EventHandler(OnProportionalScaling)));  
         m_verbs[0].Checked = (GetCustomProperty("poly:Proportional") == bool.TrueString);  
        }  
  
        return m_verbs;  
    }  
}  
  
private void OnProportionalScaling(object sender, EventArgs e)  
{  
   bool proportional = !  
        (GetCustomProperty("poly:Proportional") == bool.TrueString);  
   m_verbs[0].Checked = proportional;  
   SetCustomProperty("poly:Proportional", proportional.ToString());  
   ChangeService().OnComponentChanged(this, null, null, null);  
   Invalidate();  
}  
```  
  
### <a name="using-adornments"></a><span data-ttu-id="9b7cd-137">Utilizar las opciones gráficas</span><span class="sxs-lookup"><span data-stu-id="9b7cd-137">Using Adornments</span></span>  
 <span data-ttu-id="9b7cd-138">Las clases de elemento de informe personalizado también pueden implementar una clase `Microsoft.ReportDesigner.Design.Adornment`.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-138">Custom report item classes can also implement a `Microsoft.ReportDesigner.Design.Adornment` class.</span></span> <span data-ttu-id="9b7cd-139">Una opción gráfica permite al control de elemento de informe personalizado proporcionar las áreas fuera del rectángulo principal de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-139">An adornment allows the custom report item control to provide areas outside the main rectangle of the design surface.</span></span> <span data-ttu-id="9b7cd-140">Estas áreas pueden administrar los eventos de interfaz de usuario, como los clics del mouse y las operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-140">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span> <span data-ttu-id="9b7cd-141">La `Adornment` clase que se define en el [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` espacio de nombres es una implementación de paso a través de la clase que se <xref:System.Windows.Forms.Design.Behavior.Adorner> encuentra en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-141">The `Adornment` class that is defined in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` namespace is a pass-through implementation of the <xref:System.Windows.Forms.Design.Behavior.Adorner> class found in Windows Forms.</span></span> <span data-ttu-id="9b7cd-142">Para obtener documentación completa sobre la `Adorner` clase, vea [información general sobre el servicio de comportamiento](https://go.microsoft.com/fwlink/?LinkId=116673) en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-142">For complete documentation on the `Adorner` class, see [Behavior Service Overview](https://go.microsoft.com/fwlink/?LinkId=116673) in the MSDN library.</span></span> <span data-ttu-id="9b7cd-143">Para ver el código de ejemplo que implementa una `Microsoft.ReportDesigner.Design.Adornment` clase, vea [SQL Server Reporting Services ejemplos de productos](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="9b7cd-143">For sample code that implements a `Microsoft.ReportDesigner.Design.Adornment` class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
 <span data-ttu-id="9b7cd-144">Para obtener más información acerca de cómo programar y usar Windows Forms en [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], vea estos temas en MSDN Library:</span><span class="sxs-lookup"><span data-stu-id="9b7cd-144">For more information about programming and using Windows Forms in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see these topics in the MSDN Library:</span></span>  
  
-   <span data-ttu-id="9b7cd-145">Atributos de tiempo de diseño para componentes</span><span class="sxs-lookup"><span data-stu-id="9b7cd-145">Design-Time Attributes for Components</span></span>  
  
-   <span data-ttu-id="9b7cd-146">Componentes de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7cd-146">Components in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
-   <span data-ttu-id="9b7cd-147">Tutorial: Crear un control de Windows Forms que aproveche las características de tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b7cd-147">Walkthrough: Creating a Windows Forms Control that Takes Advantage of Visual Studio Design-Time Features</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7cd-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b7cd-148">See Also</span></span>  
 <span data-ttu-id="9b7cd-149">[Arquitectura de elementos de informe personalizados](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="9b7cd-149">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="9b7cd-150">[Crear un componente de tiempo de ejecución de elemento de informe personalizado](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="9b7cd-150">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="9b7cd-151">[Bibliotecas de clases de elementos de informe personalizadas](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="9b7cd-151">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="9b7cd-152">Cómo: Implementar un elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="9b7cd-152">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
