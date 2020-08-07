---
title: Programar un proveedor de registro personalizado | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom log providers [Integration Services], coding
ms.assetid: 979a29ca-956e-4fdd-ab47-f06e84cead7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d529420207ac065ae5ecb3c1d984de3021845b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746329"
---
# <a name="coding-a-custom-log-provider"></a><span data-ttu-id="a0421-102">Codificar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="a0421-102">Coding a Custom Log Provider</span></span>
  <span data-ttu-id="a0421-103">Una vez que haya creado una clase que herede de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> y haya aplicado el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> a la clase, debe invalidar la implementación de las propiedades y los métodos de la clase base para proporcionar su funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="a0421-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="a0421-104">Para obtener ejemplos funcionales de proveedores de registro personalizados, consulte [Desarrollar una interfaz de usuario para un proveedor de registro personalizado](developing-a-user-interface-for-a-custom-log-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a0421-104">For working samples of custom log providers, see [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md).</span></span>  
  
## <a name="configuring-the-log-provider"></a><span data-ttu-id="a0421-105">Configurar el proveedor de registro</span><span class="sxs-lookup"><span data-stu-id="a0421-105">Configuring the Log Provider</span></span>  
  
### <a name="initializing-the-log-provider"></a><span data-ttu-id="a0421-106">Inicializar el proveedor de registro</span><span class="sxs-lookup"><span data-stu-id="a0421-106">Initializing the Log Provider</span></span>  
 <span data-ttu-id="a0421-107">Puede invalidar el método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> para almacenar en memoria caché las referencias a la colección de conexiones y a la interfaz de eventos.</span><span class="sxs-lookup"><span data-stu-id="a0421-107">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> method to cache references to the connections collection and the events interface.</span></span> <span data-ttu-id="a0421-108">Puede utilizar estas referencias almacenadas en memoria caché más adelante en otros métodos del proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="a0421-108">You can use these cached references later in other methods of the log provider.</span></span>  
  
### <a name="using-the-configstring-property"></a><span data-ttu-id="a0421-109">Utilizar la propiedad ConfigString</span><span class="sxs-lookup"><span data-stu-id="a0421-109">Using the ConfigString Property</span></span>  
 <span data-ttu-id="a0421-110">En tiempo de diseño, un proveedor de registro recibe información de configuración de la columna **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="a0421-110">At design time, a log provider receives configuration information from the **Configuration** column.</span></span> <span data-ttu-id="a0421-111">Esta información de configuración corresponde a la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> del proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="a0421-111">This configuration information corresponds to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property of the log provider.</span></span> <span data-ttu-id="a0421-112">De forma predeterminada, esta columna contiene un cuadro de texto del que puede recuperar cualquier información de cadena.</span><span class="sxs-lookup"><span data-stu-id="a0421-112">By default, this column contains a text box from which you can retrieve any string information.</span></span> <span data-ttu-id="a0421-113">La mayoría de los proveedores de registro incluidos con [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] utilizan esta propiedad para almacenar el nombre del administrador de conexión que el proveedor utiliza para conectarse a un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="a0421-113">Most of the log providers included with [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] use this property to store the name of the connection manager that the provider uses to connect to an external data source.</span></span> <span data-ttu-id="a0421-114">Si el proveedor de registro utiliza la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>, utilice el método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> para validarla y asegurarse de que se haya establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0421-114">If your log provider uses the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property, use the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to validate this property and make sure that the property is set correctly.</span></span>  
  
### <a name="validating-the-log-provider"></a><span data-ttu-id="a0421-115">Validar el proveedor de registro</span><span class="sxs-lookup"><span data-stu-id="a0421-115">Validating the Log Provider</span></span>  
 <span data-ttu-id="a0421-116">Puede invalidar el método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> para asegurarse de que el proveedor se ha configurado correctamente y está listo para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a0421-116">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to make sure that the provider has been configured correctly and is ready for execution.</span></span> <span data-ttu-id="a0421-117">Normalmente, un nivel mínimo de validación es asegurarse de que se establece <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0421-117">Typically, a minimum level of validation is to make sure that the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> is set correctly.</span></span> <span data-ttu-id="a0421-118">La ejecución no puede continuar hasta que el proveedor de registro devuelva <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> en el método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0421-118">Execution cannot continue until the log provider returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="a0421-119">En el ejemplo de código siguiente se muestra una implementación de <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> que garantiza que se especifica el nombre de un administrador de conexión, que existe el administrador de conexión en el paquete y que el administrador de conexión devuelve un nombre de archivo en la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0421-119">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> that makes sure that the name of a connection manager name is specified, that the connection manager exists in the package, and that the connection manager returns a file name in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override DTSExecResult Validate(IDTSInfoEvents infoEvents)  
{  
    if (this.ConfigString.Length == 0 || connections.Contains(ConfigString) == false)  
    {  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
        return DTSExecResult.Failure;  
    }  
    else  
    {  
        string fileName = connections[ConfigString].AcquireConnection(null) as string;  
  
        if (fileName == null || fileName.Length == 0)  
        {  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
            return DTSExecResult.Failure;  
        }  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As IDTSInfoEvents) As DTSExecResult  
    If Me.ConfigString.Length = 0 Or connections.Contains(ConfigString) = False Then  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
        Return DTSExecResult.Failure  
    Else   
        Dim fileName As String =  connections(ConfigString).AcquireConnectionCType(as string, Nothing)  
  
        If fileName = Nothing Or fileName.Length = 0 Then  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
            Return DTSExecResult.Failure  
        End If  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
### <a name="persisting-the-log-provider"></a><span data-ttu-id="a0421-120">Conservar el proveedor de registro</span><span class="sxs-lookup"><span data-stu-id="a0421-120">Persisting the Log Provider</span></span>  
 <span data-ttu-id="a0421-121">Normalmente, no tiene que implementar la persistencia personalizada para un administrador de conexión.</span><span class="sxs-lookup"><span data-stu-id="a0421-121">Ordinarily you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="a0421-122">Solo se requiere la persistencia personalizada cuando las propiedades de un objeto usan tipos de datos complejos.</span><span class="sxs-lookup"><span data-stu-id="a0421-122">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="a0421-123">Para obtener más información, vea [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) (Desarrollar objetos personalizados para Integration Services).</span><span class="sxs-lookup"><span data-stu-id="a0421-123">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="logging-with-the-log-provider"></a><span data-ttu-id="a0421-124">Registrar con el proveedor de registro</span><span class="sxs-lookup"><span data-stu-id="a0421-124">Logging with the Log Provider</span></span>  
 <span data-ttu-id="a0421-125">Hay tres métodos en tiempo de ejecución que todos los proveedores de registro deben invalidar: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0421-125">There are three run-time methods that must be overridden by all log providers: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a0421-126">Durante la validación y ejecución de un paquete único, se llama a los métodos <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> más de una vez.</span><span class="sxs-lookup"><span data-stu-id="a0421-126">During the validation and execution of a single package, the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods are called more than one time.</span></span> <span data-ttu-id="a0421-127">Asegúrese de que el código personalizado no hace que las entradas de registro anteriores se invaliden por la siguiente apertura y cierre del registro.</span><span class="sxs-lookup"><span data-stu-id="a0421-127">Make sure that your custom code does not cause earlier log entries to be overwritten by the next opening and closing of the log.</span></span> <span data-ttu-id="a0421-128">Si ha seleccionado registrar los eventos de validación en el paquete de prueba, el primer evento registrado que debería ver es OnPreValidate; si en su lugar el primer evento registrado que ve es PackageStart, se han invalidado los eventos de validación iniciales.</span><span class="sxs-lookup"><span data-stu-id="a0421-128">If you have selected to log validation events in your test package, the first logged event that you should see is OnPreValidate; if instead the first logged event that you see is PackageStart, the initial validation events have been overwritten.</span></span>  
  
### <a name="opening-the-log"></a><span data-ttu-id="a0421-129">Abrir el registro</span><span class="sxs-lookup"><span data-stu-id="a0421-129">Opening the Log</span></span>  
 <span data-ttu-id="a0421-130">La mayoría de los proveedores de registro se conectan a un origen de datos externo, como un archivo o una base de datos, para almacenar la información de evento que se recopila durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="a0421-130">Most log providers connect to an external data source, such as a file or database, to store the event information that is collected during package execution.</span></span> <span data-ttu-id="a0421-131">Como con cualquier otro objeto en tiempo de ejecución, la conexión al origen de datos externo se lleva a cabo normalmente utilizando los objetos del administrador de conexión.</span><span class="sxs-lookup"><span data-stu-id="a0421-131">As with any other object in the runtime, connecting to the external data source is typically accomplished by using connection manager objects.</span></span>  
  
 <span data-ttu-id="a0421-132">Se llama al método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> al iniciar la ejecución del paquete. Invalide este método para establecer una conexión al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="a0421-132">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method is called at the start of package execution.Override this method to establish a connection to the external data source.</span></span>  
  
 <span data-ttu-id="a0421-133">En el código de ejemplo siguiente se muestra un proveedor de registro que abre un archivo de texto para la escritura durante <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0421-133">The following sample code shows a log provider that opens a text file for writing during <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span></span> <span data-ttu-id="a0421-134">Abre el archivo llamando al método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> del administrador de conexión especificado en la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0421-134">It opens the file by calling the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager that was specified in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override void OpenLog()  
{  
    if(!this.connections.Contains(this.ConfigString))  
        throw new Exception("The ConnectionManager " + this.ConfigString + " does not exist in the Connections collection.");  
  
    this.connectionManager = connections[ConfigString];  
    string filePath = this.connectionManager.AcquireConnection(null) as string;  
  
    if(filePath == null || filePath.Length == 0)  
        throw new Exception("The ConnectionManager " + this.ConfigString + " is not a valid FILE ConnectionManager");  
  
    //  Create a StreamWriter to append to.  
    sw = new StreamWriter(filePath,true);  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString());  
}  
```  
  
```vb  
Public Overrides  Sub OpenLog()  
    If Not Me.connections.Contains(Me.ConfigString) Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " does not exist in the Connections collection.")  
    End If  
  
    Me.connectionManager = connections(ConfigString)  
    Dim filePath As String =  Me.connectionManager.AcquireConnectionCType(as string, Nothing)  
  
    If filePath = Nothing Or filePath.Length = 0 Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " is not a valid FILE ConnectionManager")  
    End If  
  
    '  Create a StreamWriter to append to.  
    sw = New StreamWriter(filePath,True)  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString())  
End Sub  
```  
  
### <a name="writing-log-entries"></a><span data-ttu-id="a0421-135">Escribir entradas del registro</span><span class="sxs-lookup"><span data-stu-id="a0421-135">Writing Log Entries</span></span>  
 <span data-ttu-id="a0421-136">Se llama al método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> cada vez que un objeto del paquete provoca un evento mediante la llamada a un método Fire\<event> en una de las interfaces de eventos.</span><span class="sxs-lookup"><span data-stu-id="a0421-136">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method is called every time that an object in the package raises an event by calling a Fire\<event> method on one of the event interfaces.</span></span> <span data-ttu-id="a0421-137">Cada evento se provoca con información sobre su contexto y normalmente un mensaje explicativo.</span><span class="sxs-lookup"><span data-stu-id="a0421-137">Each event is raised with information about its context and usually an explanatory message.</span></span> <span data-ttu-id="a0421-138">Sin embargo, no todas las llamadas al método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> incluyen información de todos los parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="a0421-138">However, not every call to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method includes information for every method parameter.</span></span> <span data-ttu-id="a0421-139">Por ejemplo, algunos eventos estándar cuyos nombres son autoexplicativos no proporcionan MessageText, y DataCode y DataBytes están pensados para la información complementaria opcional.</span><span class="sxs-lookup"><span data-stu-id="a0421-139">For example, some standard events whose names are self-explanatory do not provide MessageText, and DataCode and DataBytes are intended for optional supplemental information.</span></span>  
  
 <span data-ttu-id="a0421-140">En el ejemplo de código siguiente se implementa el método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> y se escriben los eventos en el flujo que se abrió en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="a0421-140">The following code example implements the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method, and writes the events to the stream that was opened in the previous section.</span></span>  
  
```csharp  
public override void Log(string logEntryName, string computerName, string operatorName, string sourceName, string sourceID, string executionID, string messageText, DateTime startTime, DateTime endTime, int dataCode, byte[] dataBytes)  
{  
    sw.Write(logEntryName + ",");  
    sw.Write(computerName + ",");  
    sw.Write(operatorName + ",");  
    sw.Write(sourceName + ",");  
    sw.Write(sourceID + ",");  
    sw.Write(messageText + ",");  
    sw.Write(dataBytes + ",");  
    sw.WriteLine("");  
}  
```  
  
```vb  
Public Overrides  Sub Log(ByVal logEnTryName As String, ByVal computerName As String, ByVal operatorName As String, ByVal sourceName As String, ByVal sourceID As String, ByVal executionID As String, ByVal messageText As String, ByVal startTime As DateTime, ByVal endTime As DateTime, ByVal dataCode As Integer, ByVal dataBytes() As Byte)  
    sw.Write(logEnTryName + ",")  
    sw.Write(computerName + ",")  
    sw.Write(operatorName + ",")  
    sw.Write(sourceName + ",")  
    sw.Write(sourceID + ",")  
    sw.Write(messageText + ",")  
    sw.Write(dataBytes + ",")  
    sw.WriteLine("")  
End Sub  
```  
  
### <a name="closing-the-log"></a><span data-ttu-id="a0421-141">Cerrar el registro</span><span class="sxs-lookup"><span data-stu-id="a0421-141">Closing the Log</span></span>  
 <span data-ttu-id="a0421-142">Se llama al método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> al final de la ejecución del paquete, después de que todos los objetos del paquete han completado la ejecución, o bien, cuando el paquete se detiene debido a los errores.</span><span class="sxs-lookup"><span data-stu-id="a0421-142">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method is called at the end of package execution, after all the objects in the package have completed execution, or, when the package stops because of errors.</span></span>  
  
 <span data-ttu-id="a0421-143">En el ejemplo de código siguiente se muestra una implementación del método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> que cierra el flujo de archivos que se abrió durante el método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0421-143">The following code example demonstrates an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method that closes the file stream that was opened during the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method.</span></span>  
  
```csharp  
public override void CloseLog()  
{  
    if (sw != null)  
    {  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString());  
        sw.Close();  
    }  
}  
```  
  
```vb  
Public Overrides  Sub CloseLog()  
    If Not sw Is Nothing Then  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString())  
        sw.Close()  
    End If  
End Sub  
```  
  
<span data-ttu-id="a0421-144">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a0421-144">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a0421-145">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="a0421-145">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a0421-146">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="a0421-146">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a0421-147">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="a0421-147">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0421-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0421-148">See Also</span></span>  
 <span data-ttu-id="a0421-149">[Crear un proveedor de registro personalizado](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="a0421-149">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="a0421-150">Desarrollar una interfaz de usuario para un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="a0421-150">Developing a User Interface for a Custom Log Provider</span></span>](developing-a-user-interface-for-a-custom-log-provider.md)  
  
  
