---
title: Bibliotecas de clases de elemento de informe personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, RDL
- RDL [Reporting Services], custom report items
ms.assetid: f18c5d8f-1d6b-4f0b-8657-c14896c2ce0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60f8cf912eb6ff3f5080e9cf757df40f37e65079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662670"
---
# <a name="custom-report-item-class-libraries"></a><span data-ttu-id="d5ad5-102">Bibliotecas de clases de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="d5ad5-102">Custom Report Item Class Libraries</span></span>
  <span data-ttu-id="d5ad5-103">Los elementos de informe personalizados utilizan las clases del espacio de nombres `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-103">Custom report items use classes from the `Microsoft.ReportDesigner` namespace.</span></span> <span data-ttu-id="d5ad5-104">Las clases utilizadas para implementar un elemento de informe personalizado pueden estar agrupadas en dos categorías principales: las clases únicas diseñadas para admitir la infraestructura del elemento de informe personalizado y las clases contenedora administradas que encapsulan la funcionalidad de los elementos del lenguaje RDL (Report Definition Language) pertinentes.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-104">The classes used to implement a custom report item can be grouped into two main categories: unique classes designed to support custom report item infrastructure, and managed wrapper classes that encapsulate the functionality of relevant Report Definition Language (RDL) elements.</span></span> <span data-ttu-id="d5ad5-105">Para obtener un ejemplo de código que ilustre cómo se usan estas clases, vea [Muestras de productos de SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="d5ad5-105">For a code sample on how to use these classes, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-infrastructure-classes"></a><span data-ttu-id="d5ad5-106">Clases de infraestructura del elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="d5ad5-106">Custom Report Item Infrastructure Classes</span></span>  
 <span data-ttu-id="d5ad5-107">Las clases siguientes se utilizan para implementar un elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-107">The following classes are used to implement a custom report item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5ad5-108">Las tablas siguientes no constituyen listas completas; incluyen solo las propiedades utilizadas de forma más habitual y los métodos para cada clase.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-108">The following tables are not complete listings; they include only the most commonly used properties and methods for each class.</span></span>  
  
### <a name="microsoftreportdesignercustomreportitemdesigner"></a><span data-ttu-id="d5ad5-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span><span class="sxs-lookup"><span data-stu-id="d5ad5-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span></span>  
 <span data-ttu-id="d5ad5-110">Ésta es la clase del elemento de informe personalizado principal.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-110">This is the main custom report item class.</span></span> <span data-ttu-id="d5ad5-111">La clase principal de la implementación del elemento de informe personalizado debe heredar de esta clase.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-111">The main class of your custom report item implementation must inherit from this class.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="d5ad5-112">Propiedades públicas</span><span class="sxs-lookup"><span data-stu-id="d5ad5-112">Public Properties</span></span>  
  
|||  
|-|-|  
|`Name`|<span data-ttu-id="d5ad5-113">El nombre del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-113">The name of the custom report item.</span></span>|  
|`Type`|<span data-ttu-id="d5ad5-114">El tipo del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-114">The type of the custom report item.</span></span>|  
|`CustomData`|<span data-ttu-id="d5ad5-115">Un objeto <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> que encapsula las propiedades de datos del elemento de informe personalizado especificado en el momento del diseño.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-115">A <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> object that encapsulates the custom report item data properties specified at design time.</span></span>|  
|`CustomProperties`|<span data-ttu-id="d5ad5-116">Una colección de propiedades personalizadas para el elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-116">A collection of custom properties for the custom report item.</span></span>|  
|`Height`|<span data-ttu-id="d5ad5-117">El alto del control de elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-117">The height of the custom report item control.</span></span>|  
|`Width`|<span data-ttu-id="d5ad5-118">El ancho del control de elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-118">The width of the custom report item control.</span></span>|  
|`Report`|<span data-ttu-id="d5ad5-119">Un contenedor para las propiedades del nivel de informe, como la lista de conjuntos de datos en el informe.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-119">A container for the report-level properties, such as the list of datasets in the report.</span></span>|  
|`AltReportItem`|<span data-ttu-id="d5ad5-120">El objeto de elemento de informe alternativo que se utilizará cuando no se admita el control en tiempo de ejecución del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-120">The alternate report item object, to be used where the custom report item run-time control is not supported.</span></span>|  
|`Style`|<span data-ttu-id="d5ad5-121">Las propiedades de estilo del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-121">The style properties for the custom report item.</span></span>|  
|`Adornment`|<span data-ttu-id="d5ad5-122">Una ventana de elementos gráficos utilizada para la edición interactiva del control.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-122">An adornment window used for interactive editing of the control.</span></span>|  
|`Site`|<span data-ttu-id="d5ad5-123">El `ISite` del componente.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-123">The `ISite` of the component.</span></span>|  
|`DesignerVerbCollection`|<span data-ttu-id="d5ad5-124">Una matriz de verbos personalizados para el menú contextual del control.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-124">An array of custom verbs for the control's shortcut menu.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="d5ad5-125">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="d5ad5-125">Public Methods</span></span>  
  
|||  
|-|-|  
|`BeginEdit`|<span data-ttu-id="d5ad5-126">Activa la edición interactiva para el control.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-126">Activates interactive editing for the control.</span></span>|  
|`DoDefaultAction`|<span data-ttu-id="d5ad5-127">Se le llama al hacer doble clic o al presionar Retorno en el control.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-127">Called in response to double-clicking or pressing Return on the control.</span></span>|  
|`EndEdit`|<span data-ttu-id="d5ad5-128">Desactiva la edición interactiva para el control.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-128">Deactivates interactive editing for the control.</span></span>|  
|`GetService`|<span data-ttu-id="d5ad5-129">Devuelve un objeto que representa un servicio.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-129">Returns an object which represents a service.</span></span>|  
|`InitializeNewComponent`|<span data-ttu-id="d5ad5-130">Se llama cuando se crea un nuevo elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-130">Called when a new custom report item is created.</span></span>|  
|`Invalidate`|<span data-ttu-id="d5ad5-131">Vuelve a dibujar toda la superficie del control.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-131">Repaints the entire surface of the control.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragDrop`|<span data-ttu-id="d5ad5-132">Se llama al arrastrar un objeto al control.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-132">Called when an object is dragged onto the control.</span></span>|  
|`OnPaint`|<span data-ttu-id="d5ad5-133">Se le llama como respuesta al evento `Paint`.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-133">Called in response to the `Paint` event.</span></span>|  
  
### <a name="microsoftreportdesignercustomreportitemattribute"></a><span data-ttu-id="d5ad5-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span><span class="sxs-lookup"><span data-stu-id="d5ad5-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span></span>  
 <span data-ttu-id="d5ad5-135">Este es el atributo utilizado para identificar el tipo del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-135">This is the attribute used to identify the type of the custom report item.</span></span> <span data-ttu-id="d5ad5-136">El nombre debe coincidir con el valor del `Name` atributo <> del `ReportItem` elemento en el archivo de configuración diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-136">The name must match the value of the <`Name`> attribute of the `ReportItem` element in the Report Designer configuration file.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="d5ad5-137">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="d5ad5-137">Public Methods</span></span>  
  
|||  
|-|-|  
|`CustomReportItemAttribute`|<span data-ttu-id="d5ad5-138">Construye el objeto CustomReportItemAttribute.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-138">Constructs the CustomReportItemAttribute object.</span></span>|  
  
### <a name="microsoftreportdesignerlocalizednameattribute"></a><span data-ttu-id="d5ad5-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span><span class="sxs-lookup"><span data-stu-id="d5ad5-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span></span>  
 <span data-ttu-id="d5ad5-140">Este es el atributo que se utiliza para especificar el nombre para mostrar que debe usarse con el diseñador de elementos de informe personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-140">This is the attribute used to specify display name to use for the custom report item designer.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="d5ad5-141">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="d5ad5-141">Public Methods</span></span>  
  
|||  
|-|-|  
|`LocalizedNameAttribute`|<span data-ttu-id="d5ad5-142">Construye el objeto LocalizedNameAttribute.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-142">Constructs the LocalizedNameAttribute object.</span></span>|  
  
### <a name="microsoftreportdesigneradornment"></a><span data-ttu-id="d5ad5-143">Microsoft.ReportDesigner.Adornment</span><span class="sxs-lookup"><span data-stu-id="d5ad5-143">Microsoft.ReportDesigner.Adornment</span></span>  
 <span data-ttu-id="d5ad5-144">El componente de tiempo de diseño del elemento de informe personalizado utiliza la clase `Adornment` para proporcionar áreas fuera del rectángulo principal de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-144">The `Adornment` class is used by the custom report item design-time component to provide areas outside of the main rectangle of the design surface.</span></span> <span data-ttu-id="d5ad5-145">Estas áreas pueden administrar los eventos de interfaz de usuario, como los clics del mouse y las operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-145">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="d5ad5-146">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="d5ad5-146">Public Methods</span></span>  
  
|||  
|-|-|  
|`OnShow`|<span data-ttu-id="d5ad5-147">Se llama cuando `Adornment` está activado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-147">Called when the `Adornment` is activated.</span></span>|  
|`OnHide`|<span data-ttu-id="d5ad5-148">Se llama cuando `Adornment` está desactivado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-148">Called when the `Adornment` is deactivated.</span></span>|  
|`Paint`|<span data-ttu-id="d5ad5-149">Se le llama como respuesta al evento `Paint`.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-149">Called in response to the `Paint` event.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragOver`<br /><br /> `OnDragLeave`<br /><br /> `OnDragDrop`|<span data-ttu-id="d5ad5-150">Se le llama cuando se arrastra un objeto a `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-150">Called when an object is dragged into the `Adornment`.</span></span>|  
  
### <a name="microsoftreportdesigneradornerservice"></a><span data-ttu-id="d5ad5-151">Microsoft.ReportDesigner.AdornerService</span><span class="sxs-lookup"><span data-stu-id="d5ad5-151">Microsoft.ReportDesigner.AdornerService</span></span>  
 <span data-ttu-id="d5ad5-152">Esta clase se utiliza para proporcionar una colección de servicios de presentación utilizada por el elemento de informe personalizado para admitir los objetos `Adornment` para el componente en tiempo de diseño del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-152">This class is used to provide a collection of display services used by the custom report item to support `Adornment` objects for the custom report item design-time component.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="d5ad5-153">Propiedades públicas</span><span class="sxs-lookup"><span data-stu-id="d5ad5-153">Public Properties</span></span>  
  
|||  
|-|-|  
|`AdornerWindowBounds`|<span data-ttu-id="d5ad5-154">Los límites de la ventana de adorno.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-154">The bounds of the Adorner window.</span></span>|  
|`AdornerWindowRegion`|<span data-ttu-id="d5ad5-155">La región de la ventana de adorno.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-155">The region of the Adorner window.</span></span>|  
|`AdornerWindowGraphics`|<span data-ttu-id="d5ad5-156">Un contexto gráfico para la ventana de adorno.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-156">A graphics context for the Adorner window.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="d5ad5-157">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="d5ad5-157">Public Methods</span></span>  
  
|||  
|-|-|  
|`ComponentRectInDesignerFrame`|<span data-ttu-id="d5ad5-158">Devuelve los límites del componente traducidos en coordenadas de marco de diseñador.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-158">Returns the bounds of the component translated into designer frame coordinates.</span></span>|  
|`InvalidateAdorner`|<span data-ttu-id="d5ad5-159">Invalida la ventana de adorno.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-159">Invalidates the Adorner window.</span></span>|  
|`PointToAdorner`|<span data-ttu-id="d5ad5-160">Devuelve un punto en coordenadas de pantalla traducido en las coordenadas de ventana de adorno.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-160">Returns a point in screen coordinates translated to Adorner window coordinates.</span></span>|  
  
### <a name="microsoftreportdesignerexpressioneditor"></a><span data-ttu-id="d5ad5-161">Microsoft.ReportDesigner.ExpressionEditor</span><span class="sxs-lookup"><span data-stu-id="d5ad5-161">Microsoft.ReportDesigner.ExpressionEditor</span></span>  
 <span data-ttu-id="d5ad5-162">Esta clase se puede utilizar desde el control en tiempo de diseño del elemento de informe personalizado para invocar el editor de expresiones.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-162">This class can be used from your custom report item design-time control to invoke the Expression Editor.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="d5ad5-163">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="d5ad5-163">Public Methods</span></span>  
  
|||  
|-|-|  
|`EditValue`|<span data-ttu-id="d5ad5-164">Invoca el editor de expresiones, inicializado con el valor del objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-164">Invokes the Expression Editor, initialized with the given object value.</span></span>|  
  
### <a name="microsoftreportdesignerifieldsdataobject"></a><span data-ttu-id="d5ad5-165">Microsoft.ReportDesigner.IFieldsDataObject</span><span class="sxs-lookup"><span data-stu-id="d5ad5-165">Microsoft.ReportDesigner.IFieldsDataObject</span></span>  
 <span data-ttu-id="d5ad5-166">Esta clase es una colección de campos [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y se utiliza para admitir los eventos arrastrar y colocar en el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-166">This class is a collection of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fields, and is used to support drag-and-drop events in the design environment.</span></span> <span data-ttu-id="d5ad5-167">Se hereda de `IReportItemDataObject`.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-167">Inherits from `IReportItemDataObject`.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="d5ad5-168">Propiedades públicas</span><span class="sxs-lookup"><span data-stu-id="d5ad5-168">Public Properties</span></span>  
  
|||  
|-|-|  
|`DataSetName`|<span data-ttu-id="d5ad5-169">El nombre del conjunto de datos que contiene los campos que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-169">The name of the dataset containing the fields to be dropped.</span></span>|  
|`Fields`|<span data-ttu-id="d5ad5-170">La colección de campos (`Microsoft.ReportDesigner.Field`) que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="d5ad5-170">The collection of fields (`Microsoft.ReportDesigner.Field`) to be dropped.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5ad5-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5ad5-171">See Also</span></span>  
 <span data-ttu-id="d5ad5-172">[Lenguaje de definición de informes &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d5ad5-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span></span>  
 <span data-ttu-id="d5ad5-173">[Crear un componente de tiempo de ejecución de elemento de informe personalizado](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="d5ad5-173">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 [<span data-ttu-id="d5ad5-174">Crear un componente de tiempo de diseño de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="d5ad5-174">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
  
  
