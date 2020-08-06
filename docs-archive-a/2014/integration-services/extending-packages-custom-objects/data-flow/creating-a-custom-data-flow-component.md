---
title: Crear un componente de flujo de datos personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- design-time component interface [Integration Services]
- custom data flow components [Integration Services], about data flow components
- custom data flow components [Integration Services]
- data flow components [Integration Services]
- data flow components [Integration Services], developing
ms.assetid: 9d96bcf5-eba8-44bd-b113-ed51ad0d0521
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 110d07ff88707ad1a01f299b6f532df99ce58404
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674224"
---
# <a name="creating-a-custom-data-flow-component"></a><span data-ttu-id="35269-102">Crear un componente de flujo de datos personalizado</span><span class="sxs-lookup"><span data-stu-id="35269-102">Creating a Custom Data Flow Component</span></span>
  <span data-ttu-id="35269-103">En [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], la tarea Flujo de datos expone un modelo de objetos que permite a los desarrolladores crear componentes de flujo de datos personalizados, orígenes, transformaciones y destinos mediante [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] y código administrado.</span><span class="sxs-lookup"><span data-stu-id="35269-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the data flow task exposes an object model that lets developers create custom data flow components-sources, transformations, and destinations-by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] and managed code.</span></span>  
  
 <span data-ttu-id="35269-104">Una tarea de flujo de datos consta de componentes que contienen una interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> y una colección de objetos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> que definen el movimiento de datos entre los componentes.</span><span class="sxs-lookup"><span data-stu-id="35269-104">A data flow task consists of components that contain an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface and a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects that define the movement of data between components.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35269-105">Cuando crea un proveedor personalizado, necesita actualizar el archivo ProviderDescriptors.xml con los valores de la columna de metadatos.</span><span class="sxs-lookup"><span data-stu-id="35269-105">When you create a custom provider, you need to update the ProviderDescriptors.xml file with the metadata column values.</span></span>  
  
## <a name="design-time-and-run-time"></a><span data-ttu-id="35269-106">Tiempo de diseño y tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="35269-106">Design Time and Run Time</span></span>  
 <span data-ttu-id="35269-107">Antes de la ejecución, se dice que la tarea Flujo de datos se encuentra en un estado en tiempo de diseño, cuando sufre cambios incrementales.</span><span class="sxs-lookup"><span data-stu-id="35269-107">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="35269-108">Los cambios pueden incluir la adición o eliminación de los componentes, la adición o eliminación de los objetos de ruta de acceso que conectan los componentes y cambios en los metadatos de los componentes.</span><span class="sxs-lookup"><span data-stu-id="35269-108">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="35269-109">Cuando se producen cambios en los metadatos, el componente puede supervisar y reaccionar a los cambios.</span><span class="sxs-lookup"><span data-stu-id="35269-109">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="35269-110">Por ejemplo, un componente puede no permitir ciertos cambios o realizar cambios adicionales en respuesta a un cambio.</span><span class="sxs-lookup"><span data-stu-id="35269-110">For example, a component can disallow certain changes or to make additional changes in response to a change.</span></span> <span data-ttu-id="35269-111">En tiempo de diseño, el diseñador interactúa con un componente a través de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="35269-111">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="35269-112">En tiempo de ejecución, la tarea de flujo de datos examina la secuencia de componentes, prepara un plan de ejecución y administra un grupo de subprocesos de trabajo que ejecutan el plan de trabajo.</span><span class="sxs-lookup"><span data-stu-id="35269-112">At execution time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="35269-113">Aunque cada subproceso de trabajo realiza algún trabajo que es interno a la tarea de flujo de datos, la tarea principal del subproceso de trabajo es llamar a los métodos del componente a través de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="35269-113">Although each worker thread performs some work that is internal to the data flow task, the principal task of the worker thread is to call the methods of the component through the run-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interface.</span></span>  
  
## <a name="creating-a-component"></a><span data-ttu-id="35269-114">Crear un componente</span><span class="sxs-lookup"><span data-stu-id="35269-114">Creating a Component</span></span>  
 <span data-ttu-id="35269-115">Para crear un componente de flujo de datos, puede derivar una clase de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>, aplicar la clase <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> y, a continuación, invalidar los métodos adecuados de la clase base.</span><span class="sxs-lookup"><span data-stu-id="35269-115">To create a data flow component, you derive a class from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class, apply the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> class, and then override the appropriate methods of the base class.</span></span> <span data-ttu-id="35269-116"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implementa las interfaces <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> y <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> y expone sus métodos para que los invalide en el componente.</span><span class="sxs-lookup"><span data-stu-id="35269-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interfaces, and exposes their methods for you to override in your component.</span></span>  
  
 <span data-ttu-id="35269-117">En función de los objetos que utiliza el componente, el proyecto requerirá las referencias a algunos o a todos los ensamblados siguientes:</span><span class="sxs-lookup"><span data-stu-id="35269-117">Depending on the objects used by your component, your project will require references to some or all of the following assemblies:</span></span>  
  
|<span data-ttu-id="35269-118">Característica</span><span class="sxs-lookup"><span data-stu-id="35269-118">Feature</span></span>|<span data-ttu-id="35269-119">Ensamblado para referencia</span><span class="sxs-lookup"><span data-stu-id="35269-119">Assembly to reference</span></span>|<span data-ttu-id="35269-120">Espacio de nombres a importar</span><span class="sxs-lookup"><span data-stu-id="35269-120">Namespace to import</span></span>|  
|-------------|---------------------------|-------------------------|  
|<span data-ttu-id="35269-121">flujo de datos</span><span class="sxs-lookup"><span data-stu-id="35269-121">Data flow</span></span>|<span data-ttu-id="35269-122">Microsoft.SqlServer.PipelineHost</span><span class="sxs-lookup"><span data-stu-id="35269-122">Microsoft.SqlServer.PipelineHost</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline>|  
|<span data-ttu-id="35269-123">Contenedor de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="35269-123">Data flow wrapper</span></span>|<span data-ttu-id="35269-124">Microsoft.SqlServer.DTSPipelineWrap</span><span class="sxs-lookup"><span data-stu-id="35269-124">Microsoft.SqlServer.DTSPipelineWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>|  
|<span data-ttu-id="35269-125">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="35269-125">Runtime</span></span>|<span data-ttu-id="35269-126">Microsoft.SQLServer.ManagedDTS</span><span class="sxs-lookup"><span data-stu-id="35269-126">Microsoft.SQLServer.ManagedDTS</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime>|  
|<span data-ttu-id="35269-127">Contenedor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="35269-127">Runtime wrapper</span></span>|<span data-ttu-id="35269-128">Microsoft.SqlServer.DTSRuntimeWrap</span><span class="sxs-lookup"><span data-stu-id="35269-128">Microsoft.SqlServer.DTSRuntimeWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Wrapper>|  
  
 <span data-ttu-id="35269-129">En el ejemplo de código siguiente se muestra un componente simple que deriva de la clase base y aplica <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="35269-129">The following code example shows a simple component that derives from the base class, and applies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="35269-130">Deberá agregar una referencia al ensamblado DTSPipelineWrap.</span><span class="sxs-lookup"><span data-stu-id="35269-130">You need to add a reference to the DTSPipelineWrap assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SampleComponent", ComponentType = ComponentType.Transform )]  
    public class BasicComponent: PipelineComponent  
    {  
        // TODO: Override the base class methods.  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(DisplayName:="SampleComponent", ComponentType:=ComponentType.Transform)> _  
Public Class BasicComponent  
  
    Inherits PipelineComponent  
  
    ' TODO: Override the base class methods.  
  
End Class  
```  
  
<span data-ttu-id="35269-131">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="35269-131">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="35269-132">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="35269-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="35269-133">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="35269-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="35269-134">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="35269-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35269-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35269-135">See Also</span></span>  
 [<span data-ttu-id="35269-136">Desarrollar una interfaz de usuario para un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="35269-136">Developing a User Interface for a Data Flow Component</span></span>](developing-a-user-interface-for-a-data-flow-component.md)  
  
  
