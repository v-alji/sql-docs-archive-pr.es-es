---
title: Conectar componentes de flujo de datos mediante programación | Microsoft Docs
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
- data flow task [Integration Services], components
- paths [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 404ecab7-7698-447b-93d6-dd256beb11ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39494fee5314f309b79abfd30303fdd607fd3c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671639"
---
# <a name="connecting-data-flow-components-programmatically"></a><span data-ttu-id="e3a96-102">Conectar componentes de flujo de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="e3a96-102">Connecting Data Flow Components Programmatically</span></span>
  <span data-ttu-id="e3a96-103">Después de agregar componentes a la tarea de flujo de datos, los conecta para crear un árbol de ejecución que representa el flujo de datos desde los orígenes, pasando por las transformaciones, hasta los destinos.</span><span class="sxs-lookup"><span data-stu-id="e3a96-103">After you have added components to the data flow task, you connect them to create an execution tree that represents the flow of data from sources through transformations to destinations.</span></span> <span data-ttu-id="e3a96-104">Utiliza <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objeta para conectar los componentes en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="e3a96-104">You use <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects to connect the components in the data flow.</span></span>  
  
## <a name="creating-a-path"></a><span data-ttu-id="e3a96-105">Crear una ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="e3a96-105">Creating a Path</span></span>  
 <span data-ttu-id="e3a96-106">Llame al método New de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> para crear una nueva ruta de acceso y agregarla a la colección de rutas de acceso en la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="e3a96-106">Call the New method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> interface to create a new path and add it to the collection of paths in the data flow task.</span></span> <span data-ttu-id="e3a96-107">Este método devuelve un nuevo objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> desconectado, que posteriormente utiliza para conectar dos componentes.</span><span class="sxs-lookup"><span data-stu-id="e3a96-107">This method returns a new, disconnected <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, which you then use to connect two components.</span></span>  
  
 <span data-ttu-id="e3a96-108">Llame al método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> para conectarse a la ruta de acceso y notificar a los componentes que participan en la ruta de acceso que se han conectado.</span><span class="sxs-lookup"><span data-stu-id="e3a96-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> method to connect the path and to notify the components participating in the path that they have been connected.</span></span> <span data-ttu-id="e3a96-109">Este método acepta como parámetros <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> del componente de nivel superior y <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> del componente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="e3a96-109">This method accepts an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the upstream component and an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> of the downstream component as parameters.</span></span> <span data-ttu-id="e3a96-110">De forma predeterminada, la llamada al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> del componente crea una entrada única para los componentes que tienen entradas y una salida única para los componentes que tienen salidas.</span><span class="sxs-lookup"><span data-stu-id="e3a96-110">By default, the call to the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method creates a single input for components that have inputs, and a single output for components that have outputs.</span></span> <span data-ttu-id="e3a96-111">En el ejemplo siguiente se utiliza esta salida predeterminada del origen y entrada predeterminada del destino.</span><span class="sxs-lookup"><span data-stu-id="e3a96-111">The following example uses this default output of the source and input of the destination.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e3a96-112">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="e3a96-112">Next Step</span></span>  
 <span data-ttu-id="e3a96-113">Después de establecer una ruta de acceso entre dos componentes, el paso siguiente consiste en asignar columnas de entrada en el componente de nivel inferior. Este paso se describe en el tema [Seleccionar columnas de entrada mediante programación](../building-packages-programmatically/selecting-input-columns-programmatically.md) siguiente.</span><span class="sxs-lookup"><span data-stu-id="e3a96-113">After you establish a path between two components, the next step is to map input columns in the downstream component, which is discussed in the next topic, [Selecting Input Columns Programmatically](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="e3a96-114">Muestra</span><span class="sxs-lookup"><span data-stu-id="e3a96-114">Sample</span></span>  
 <span data-ttu-id="e3a96-115">En el ejemplo de código siguiente se muestra cómo establecer una ruta de acceso entre dos componentes.</span><span class="sxs-lookup"><span data-stu-id="e3a96-115">The following code sample shows how to establish a path between two components.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Create the source component.    
      IDTSComponentMetaData100 source =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      source.ComponentClassID = "DTSAdapter.OleDbSource";  
      CManagedComponentWrapper srcDesignTime = source.Instantiate();  
      srcDesignTime.ProvideComponentProperties();  
  
      // Create the destination component.  
      IDTSComponentMetaData100 destination =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      destination.ComponentClassID = "DTSAdapter.OleDbDestination";  
      CManagedComponentWrapper destDesignTime = destination.Instantiate();  
      destDesignTime.ProvideComponentProperties();  
  
      // Create the path.  
      IDTSPath100 path = dataFlowTask.PathCollection.New();  
      path.AttachPathAndPropagateNotifications(source.OutputCollection[0],  
        destination.InputCollection[0]);  
    }  
  }  
```  
  
 <span data-ttu-id="e3a96-116">}</span><span class="sxs-lookup"><span data-stu-id="e3a96-116">}</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Create the source component.    
    Dim source As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    source.ComponentClassID = "DTSAdapter.OleDbSource"  
    Dim srcDesignTime As CManagedComponentWrapper = source.Instantiate()  
    srcDesignTime.ProvideComponentProperties()  
  
    ' Create the destination component.  
    Dim destination As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    destination.ComponentClassID = "DTSAdapter.OleDbDestination"  
    Dim destDesignTime As CManagedComponentWrapper = destination.Instantiate()  
    destDesignTime.ProvideComponentProperties()  
  
    ' Create the path.  
    Dim path As IDTSPath100 = dataFlowTask.PathCollection.New()  
    path.AttachPathAndPropagateNotifications(source.OutputCollection(0), _  
      destination.InputCollection(0))  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="e3a96-117">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e3a96-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e3a96-118">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="e3a96-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e3a96-119">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="e3a96-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e3a96-120">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="e3a96-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a96-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3a96-121">See Also</span></span>  
 [<span data-ttu-id="e3a96-122">Seleccionar mediante programación las columnas de entrada</span><span class="sxs-lookup"><span data-stu-id="e3a96-122">Selecting Input Columns Programmatically</span></span>](../building-packages-programmatically/selecting-input-columns-programmatically.md)  
  
  
