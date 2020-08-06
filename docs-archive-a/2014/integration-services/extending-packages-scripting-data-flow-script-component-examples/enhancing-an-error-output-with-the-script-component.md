---
title: Mejorar una salida de errores con el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], components
- Script component [Integration Services], examples
- error outputs [Integration Services], enhancing
- Script component [Integration Services], transformation components
ms.assetid: f7c02709-f1fa-4ebd-b255-dc8b81feeaa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 18637aa1e147ce989645ae859681929f4d0c438a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677220"
---
# <a name="enhancing-an-error-output-with-the-script-component"></a><span data-ttu-id="efb91-102">Mejorar una salida de errores con el componente de script</span><span class="sxs-lookup"><span data-stu-id="efb91-102">Enhancing an Error Output with the Script Component</span></span>
  <span data-ttu-id="efb91-103">De forma predeterminada, las dos columnas adicionales en una salida de errores de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], ErrorCode y ErrorColumn, únicamente contienen códigos numéricos que representan un número de error y el identificador de la columna en la que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="efb91-103">By default, the two extra columns in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error output, ErrorCode and ErrorColumn, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="efb91-104">Estos valores numéricos pueden tener un uso limitado sin la correspondiente descripción del error.</span><span class="sxs-lookup"><span data-stu-id="efb91-104">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="efb91-105">En este tema se describe cómo agregar una columna de descripción del error a los datos de salida de error existentes en el flujo de datos mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="efb91-105">This topic describes how to add an error description column to existing error output data in the data flow by using the Script component.</span></span> <span data-ttu-id="efb91-106">En el ejemplo se agrega la descripción del error que corresponde a un determinado código de error de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] predefinido mediante el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponible a través de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> del componente de script.</span><span class="sxs-lookup"><span data-stu-id="efb91-106">The example adds the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the Script component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="efb91-107">Si desea crear un componente que pueda reutilizar más fácilmente en varias tareas de flujo de datos y varios paquetes, puede utilizar el código de este ejemplo de componente de script como punto de inicio para el componente de flujo de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="efb91-107">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="efb91-108">Para obtener más información, vea [Desarrollar un componente de flujo de datos personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="efb91-108">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="efb91-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efb91-109">Example</span></span>  
 <span data-ttu-id="efb91-110">El ejemplo que aparece aquí utiliza un componente de script configurado como una transformación para agregar una columna de descripción del error a los datos de salida de error existentes en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="efb91-110">The example shown here uses a Script component configured as a transformation to add an error description column to existing error output data in the data flow.</span></span>  
  
 <span data-ttu-id="efb91-111">Para obtener más información sobre cómo configurar el componente de script para su uso como una transformación en el flujo de datos, vea [crear una transformación sincrónica con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)y [crear una transformación asincrónica con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="efb91-111">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="efb91-112">Para configurar este ejemplo de componente de script</span><span class="sxs-lookup"><span data-stu-id="efb91-112">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="efb91-113">Antes de crear el nuevo componente de script, configure un componente de nivel superior en el flujo de datos para redirigir las filas a su salida de error cuando se produce un error o truncamiento.</span><span class="sxs-lookup"><span data-stu-id="efb91-113">Before creating the new Script component, configure an upstream component in the data flow to redirect rows to its error output when an error or truncation occurs.</span></span> <span data-ttu-id="efb91-114">Con fines de prueba, puede que quiera configurar un componente de manera que garantice que se van a producir errores (por ejemplo, mediante la configuración de una transformación Búsqueda entre dos tablas donde se producirá un error en la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="efb91-114">For testing purposes, you may want to configure a component in a manner that ensures that errors will occur-for example, by configuring a Lookup transformation between two tables where the lookup will fail.</span></span>  
  
2.  <span data-ttu-id="efb91-115">Agregue un nuevo componente de script a la superficie del diseñador de flujo de datos y configúrelo como una transformación.</span><span class="sxs-lookup"><span data-stu-id="efb91-115">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span>  
  
3.  <span data-ttu-id="efb91-116">Conecte la salida de error del componente de nivel superior al nuevo componente de script.</span><span class="sxs-lookup"><span data-stu-id="efb91-116">Connect the error output from the upstream component to the new Script component.</span></span>  
  
4.  <span data-ttu-id="efb91-117">Abra el **Editor de transformación Script** y en la página **Script**, para la propiedad **ScriptLanguage**, seleccione el lenguaje de script.</span><span class="sxs-lookup"><span data-stu-id="efb91-117">Open the **Script Transformation Editor**, and on the **Script** page, for the **ScriptLanguage** property, select the script language.</span></span>  
  
5.  <span data-ttu-id="efb91-118">Haga clic en **Editar script** para abrir el IDE de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) y agregue el código de ejemplo que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="efb91-118">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE and add the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="efb91-119">Cierre VSTA.</span><span class="sxs-lookup"><span data-stu-id="efb91-119">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="efb91-120">En el editor de transformación script, en la página **columnas de entrada** , seleccione la columna ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="efb91-120">In the Script Transformation Editor, on the **Input Columns** page, select the ErrorCode column.</span></span>  
  
8.  <span data-ttu-id="efb91-121">En la página **entradas y salidas** , agregue una nueva columna de salida de tipo `String` denominada **ErrorDescription**.</span><span class="sxs-lookup"><span data-stu-id="efb91-121">On the **Inputs and Outputs** page, add a new output column of type `String` named **ErrorDescription**.</span></span> <span data-ttu-id="efb91-122">Aumente la longitud predeterminada de la nueva columna a 255 para admitir mensajes largos.</span><span class="sxs-lookup"><span data-stu-id="efb91-122">Increase the default length of the new column to 255 to support long messages.</span></span>  
  
9. <span data-ttu-id="efb91-123">Cierre el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="efb91-123">Close the **Script Transformation Editor.**</span></span>  
  
10. <span data-ttu-id="efb91-124">Adjunte la salida del componente de script a un destino conveniente.</span><span class="sxs-lookup"><span data-stu-id="efb91-124">Attach the output of the Script component to a suitable destination.</span></span> <span data-ttu-id="efb91-125">Para pruebas ad hoc, la manera más fácil de configurar es mediante un destino de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="efb91-125">A Flat File destination is the easiest to configure for ad hoc testing.</span></span>  
  
11. <span data-ttu-id="efb91-126">Ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="efb91-126">Run the package.</span></span>  
  
```vb  
Public Class ScriptMain  
    Inherits UserComponent  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  Row.ErrorDescription = _  
    Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain:  
    UserComponent  
{  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
  Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
    }  
}  
  
```  
  
<span data-ttu-id="efb91-127">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="efb91-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="efb91-128">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="efb91-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="efb91-129">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="efb91-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="efb91-130">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="efb91-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb91-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efb91-131">See Also</span></span>  
 <span data-ttu-id="efb91-132">[Control de errores en los datos](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="efb91-132">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="efb91-133">[Usar las salidas de error en un componente de flujo de datos](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="efb91-133">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="efb91-134">Crear una transformación sincrónica con el componente de script</span><span class="sxs-lookup"><span data-stu-id="efb91-134">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
