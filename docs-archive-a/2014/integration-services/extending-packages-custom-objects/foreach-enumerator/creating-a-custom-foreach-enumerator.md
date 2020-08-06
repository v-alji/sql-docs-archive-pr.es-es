---
title: Crear un enumerador Para cada uno personalizado | Microsoft Docs
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
- custom foreach enumerators [Integration Services], creating
ms.assetid: 050e8455-2ed0-4b6d-b3ea-4e80e6c28487
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d99970d466aa53d25a80f0600f1fce7819e94956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670447"
---
# <a name="creating-a-custom-foreach-enumerator"></a><span data-ttu-id="21fea-102">Crear un enumerador foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="21fea-102">Creating a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="21fea-103">Los pasos necesarios para crear un enumerador foreach personalizado son similares a los pasos para crear cualquier otro objeto personalizado para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="21fea-103">The steps involved in creating a custom foreach enumerator are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="21fea-104">Cree una clase nueva que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="21fea-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="21fea-105">Para un enumerador foreach, la clase base es <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="21fea-105">For a foreach enumerator, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span></span>  
  
-   <span data-ttu-id="21fea-106">Aplique el atributo que identifica el tipo de objeto para la clase.</span><span class="sxs-lookup"><span data-stu-id="21fea-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="21fea-107">Para un enumerador foreach, el atributo es <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="21fea-107">For a foreach enumerator, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span></span>  
  
-   <span data-ttu-id="21fea-108">Invalide la implementación de los métodos y las propiedades de la clase base.</span><span class="sxs-lookup"><span data-stu-id="21fea-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="21fea-109">Para un enumerador foreach, el más importante es el método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="21fea-109">For a foreach enumerator, the most important is the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
-   <span data-ttu-id="21fea-110">Si lo desea, desarrolle una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="21fea-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="21fea-111">Para un enumerador foreach, esto requiere una clase que implemente la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI>.</span><span class="sxs-lookup"><span data-stu-id="21fea-111">For a foreach enumerator, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI> interface.</span></span>  
  
 <span data-ttu-id="21fea-112">El contenedor <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> hospeda un enumerador personalizado.</span><span class="sxs-lookup"><span data-stu-id="21fea-112">A custom enumerator is hosted by the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container.</span></span> <span data-ttu-id="21fea-113">En tiempo de ejecución, el contenedor <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> llama al método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> del enumerador personalizado.</span><span class="sxs-lookup"><span data-stu-id="21fea-113">At run time, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="21fea-114">El enumerador personalizado devuelve un objeto que implementa la interfaz `IEnumerable`, por ejemplo, un objeto `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="21fea-114">The custom enumerator returns an object that implements the `IEnumerable` interface, such as an `ArrayList`.</span></span> <span data-ttu-id="21fea-115">A continuación, <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> establece una iteración en cada elemento de la colección, proporciona el valor del elemento actual al flujo de control a través de una variable definida por el usuario y ejecuta el flujo de control en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21fea-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates over each element in the collection, provides the value of the current element to the control flow through a user-defined variable, and executes the control flow in the container.</span></span>  
  
## <a name="getting-started-with-a-custom-foreach-enumerator"></a><span data-ttu-id="21fea-116">Introducción a los enumeradores Foreach personalizados</span><span class="sxs-lookup"><span data-stu-id="21fea-116">Getting Started with a Custom ForEach Enumerator</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="21fea-117">Crear proyectos y clases</span><span class="sxs-lookup"><span data-stu-id="21fea-117">Creating Projects and Classes</span></span>  
 <span data-ttu-id="21fea-118">Dado que todos los enumeradores foreach administrados se derivan de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, el primer paso al crear un enumerador foreach personalizado consiste en crear un proyecto de bibliotecas de clases en el lenguaje de programación administrado que prefiera y crear una clase que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="21fea-118">Because all managed foreach enumerators derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, the first step when you create a custom foreach enumerator is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="21fea-119">En esta clase derivada se invalidarán los métodos y las propiedades de la clase base para implementar la funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="21fea-119">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="21fea-120">En la misma solución, cree un segundo proyecto de bibliotecas de clases para la interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="21fea-120">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="21fea-121">Se recomienda utilizar un ensamblado independiente para la interfaz de usuario a fin de facilitar la implementación, ya que le permite actualizar y volver a implementar el enumerador foreach o su interfaz de usuario de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="21fea-121">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the foreach enumerator or its user interface independently.</span></span>  
  
 <span data-ttu-id="21fea-122">Configure ambos proyectos para firmar los ensamblados que se generarán en tiempo de compilación mediante un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="21fea-122">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsforeachenumerator-attribute"></a><span data-ttu-id="21fea-123">Aplicar el atributo DtsForEachEnumerator</span><span class="sxs-lookup"><span data-stu-id="21fea-123">Applying the DtsForEachEnumerator Attribute</span></span>  
 <span data-ttu-id="21fea-124">Aplique el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> a la clase que ha creado para identificarla como enumerador foreach.</span><span class="sxs-lookup"><span data-stu-id="21fea-124">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class that you have created to identify it as a foreach enumerator.</span></span> <span data-ttu-id="21fea-125">Este atributo proporciona información en tiempo de diseño, como el nombre y la descripción del enumerador foreach.</span><span class="sxs-lookup"><span data-stu-id="21fea-125">This attribute provides design-time information such as the name and description of the foreach enumerator.</span></span> <span data-ttu-id="21fea-126">La `Name` propiedad aparece en la lista desplegable de enumeradores disponibles en la pestaña **colección** del cuadro de diálogo **Editor de bucles foreach** .</span><span class="sxs-lookup"><span data-stu-id="21fea-126">The `Name` property appears in the dropdown list of available enumerators on the **Collection** tab of the **Foreach Loop Editor** dialog box.</span></span>  
  
 <span data-ttu-id="21fea-127">Utilice la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> para vincular el enumerador foreach a su interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="21fea-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> property to link the foreach enumerator to its custom user interface.</span></span> <span data-ttu-id="21fea-128">Para obtener el token de clave pública necesario para esta propiedad, puede usar **sn.exe -t** con el fin de mostrar el token de clave pública del archivo de pares de claves (.snk) que quiere usar para firmar el ensamblado de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="21fea-128">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Namespace Microsoft.Samples.SqlServer.Dts  
    <DtsForEachEnumerator(DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")> _   
    Public Class MyEnumerator  
     Inherits ForEachEnumerator  
        'Insert code here.  
    End Class  
End Namespace  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsForEachEnumerator( DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")]  
    public class MyEnumerator : ForEachEnumerator  
    {  
        //Insert code here.  
    }  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-enumerator"></a><span data-ttu-id="21fea-129">Generar, implementar y depurar un enumerador personalizado</span><span class="sxs-lookup"><span data-stu-id="21fea-129">Building, Deploying, and Debugging a Custom Enumerator</span></span>  
 <span data-ttu-id="21fea-130">Los pasos para generar, implementar y depurar un enumerador foreach personalizado en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] son muy similares a los pasos requeridos para otros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="21fea-130">The steps for building, deploying, and debugging a custom foreach enumerator in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="21fea-131">Para obtener más información, consulte [Generar, implementar y depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="21fea-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="21fea-132">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="21fea-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="21fea-133">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="21fea-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="21fea-134">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="21fea-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="21fea-135">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="21fea-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fea-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21fea-136">See Also</span></span>  
 <span data-ttu-id="21fea-137">[Codificar un enumerador Foreach personalizado](coding-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="21fea-137">[Coding a Custom Foreach Enumerator](coding-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="21fea-138">Desarrollar una interfaz de usuario para un enumerador foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="21fea-138">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
