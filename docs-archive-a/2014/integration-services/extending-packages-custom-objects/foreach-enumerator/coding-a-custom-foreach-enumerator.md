---
title: Programar un enumerador Para cada uno personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services], coding
ms.assetid: 279cf6de-d06f-40e7-b8ca-569310449f36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b7e6c16124f4682dbdc98f602417bf8f68ce099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670449"
---
# <a name="coding-a-custom-foreach-enumerator"></a><span data-ttu-id="7185f-102">Codificar un enumerador foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="7185f-102">Coding a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="7185f-103">Una vez que haya creado una clase que herede de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> y haya aplicado el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> a la clase, debe invalidar la implementación de las propiedades y los métodos de la clase base para proporcionar su funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="7185f-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="7185f-104">Para obtener un ejemplo funcional de un enumerador personalizado, consulte [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md) (Desarrollar una interfaz de usuario para un enumerador Para cada uno personalizado).</span><span class="sxs-lookup"><span data-stu-id="7185f-104">For a working sample of a custom enumerator, see [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span></span>  
  
## <a name="initializing-the-enumerator"></a><span data-ttu-id="7185f-105">Inicializar el enumerador</span><span class="sxs-lookup"><span data-stu-id="7185f-105">Initializing the Enumerator</span></span>  
 <span data-ttu-id="7185f-106">Puede invalidar el método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> para almacenar en memoria caché las referencias a los administradores de conexión definidos en el paquete y las referencias a la interfaz de eventos que puede utilizar para provocar errores, advertencias y mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="7185f-106">You can override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> method to cache references to the connection managers defined in the package, and to cache references to the events interface that you can use to raise errors, warnings, and informational messages.</span></span>  
  
## <a name="validating-the-enumerator"></a><span data-ttu-id="7185f-107">Validar el enumerador</span><span class="sxs-lookup"><span data-stu-id="7185f-107">Validating the Enumerator</span></span>  
 <span data-ttu-id="7185f-108">Invalide el método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> para comprobar que el enumerador se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7185f-108">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> method to verify that the enumerator is correctly configured.</span></span> <span data-ttu-id="7185f-109">Si el método devuelve `Failure`, no se ejecutarán el enumerador ni el paquete que contiene el enumerador.</span><span class="sxs-lookup"><span data-stu-id="7185f-109">If the method returns `Failure`, the enumerator and the package that contains the enumerator will not be executed.</span></span> <span data-ttu-id="7185f-110">La implementación de este método es específica de cada enumerador, pero si el enumerador se basa en los objetos <xref:Microsoft.SqlServer.Dts.Runtime.Variable> o <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, debe agregar código para comprobar que estos objetos existen en las colecciones que se proporcionan al método.</span><span class="sxs-lookup"><span data-stu-id="7185f-110">The implementation of this method is specific to each enumerator, but if the enumerator relies on <xref:Microsoft.SqlServer.Dts.Runtime.Variable> or <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects, you should add code to verify that these objects exist in the collections that are provided to the method.</span></span>  
  
 <span data-ttu-id="7185f-111">En el ejemplo de código siguiente se muestra una implementación de <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> que comprueba una variable especificada en una propiedad del enumerador.</span><span class="sxs-lookup"><span data-stu-id="7185f-111">The following code example demonstrates an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> that checks for a variable specified in a property of the enumerator.</span></span>  
  
```csharp  
private string variableNameValue;  
  
public string VariableName  
{  
    get{ return this.variableNameValue; }  
    set{ this.variableNameValue = value; }  
}  
  
public override DTSExecResult Validate(Connections connections, VariableDispenser variableDispenser, IDTSInfoEvents infoEvents, IDTSLogging log)  
{  
    if (!variableDispenser.Contains(this.variableNameValue))  
    {  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + this.variableNameValue + " does not exist in the collection.", "", 0);  
            return DTSExecResult.Failure;  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Private variableNameValue As String  
  
Public Property VariableName() As String  
    Get   
         Return Me.variableNameValue  
    End Get  
    Set (ByVal Value As String)   
         Me.variableNameValue = value  
    End Set  
End Property  
  
Public Overrides Function Validate(ByVal connections As Connections, ByVal variableDispenser As VariableDispenser, ByVal infoEvents As IDTSInfoEvents, ByVal log As IDTSLogging) As DTSExecResult  
    If Not variableDispenser.Contains(Me.variableNameValue) Then  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + Me.variableNameValue + " does not exist in the collection.", "", 0)  
            Return DTSExecResult.Failure  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
## <a name="returning-the-collection"></a><span data-ttu-id="7185f-112">Devolver la colección</span><span class="sxs-lookup"><span data-stu-id="7185f-112">Returning the Collection</span></span>  
 <span data-ttu-id="7185f-113">Durante la ejecución, el contenedor <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> llama al método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> del enumerador personalizado.</span><span class="sxs-lookup"><span data-stu-id="7185f-113">During execution, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="7185f-114">En este método, el enumerador crea y rellena su colección de elementos y, a continuación, devuelve la colección.</span><span class="sxs-lookup"><span data-stu-id="7185f-114">In this method, the enumerator creates and populates its collection of items, and then returns the collection.</span></span> <span data-ttu-id="7185f-115">A continuación, <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> itera los elementos de la colección y ejecuta su flujo de control para cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="7185f-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates the items in the collection, and executes its control flow for each item in the collection.</span></span>  
  
 <span data-ttu-id="7185f-116">En el ejemplo siguiente se muestra una implementación de <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> que devuelve una matriz de enteros aleatorios.</span><span class="sxs-lookup"><span data-stu-id="7185f-116">The following example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> that returns an array of random integers.</span></span>  
  
```csharp  
public override object GetEnumerator()  
{  
    ArrayList numbers = new ArrayList();  
  
    Random randomNumber = new Random(DateTime.Now);  
  
    for( int x=0; x < 100; x++ )  
        numbers.Add( randomNumber.Next());  
  
    return numbers;  
}  
```  
  
```vb  
Public Overrides Function GetEnumerator() As Object  
    Dim numbers As ArrayList =  New ArrayList()   
  
    Dim randomNumber As Random =  New Random(DateTime.Now)   
  
        Dim x As Integer  
        For  x = 0 To  100- 1  Step  x + 1  
        numbers.Add(randomNumber.Next())  
        Next  
  
    Return numbers  
End Function  
```  
  
<span data-ttu-id="7185f-117">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7185f-117">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7185f-118">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="7185f-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7185f-119">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="7185f-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7185f-120">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="7185f-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7185f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7185f-121">See Also</span></span>  
 <span data-ttu-id="7185f-122">[Crear un enumerador Foreach personalizado](creating-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="7185f-122">[Creating a Custom Foreach Enumerator](creating-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="7185f-123">Desarrollar una interfaz de usuario para un enumerador foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="7185f-123">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
