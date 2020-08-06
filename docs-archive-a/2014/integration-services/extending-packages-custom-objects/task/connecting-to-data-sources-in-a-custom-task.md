---
title: Conectarse a orígenes de datos de una tarea personalizada | Microsoft Docs
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
- ConnectionManager objects
- connection managers [Integration Services], external data sources
- data sources [Integration Services], external
- custom tasks [Integration Services], external data sources
- external data sources [Integration Services]
- connections [Integration Services], external data sources
- SSIS custom tasks, external data sources
ms.assetid: 9f0b3a43-3eaa-4b3c-bb08-29b630c11306
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71c504f4b528a0c9809d00de74de4beb9c67c4f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674220"
---
# <a name="connecting-to-data-sources-in-a-custom-task"></a><span data-ttu-id="4ae2c-102">Conectarse a orígenes de datos de una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="4ae2c-102">Connecting to Data Sources in a Custom Task</span></span>
  <span data-ttu-id="4ae2c-103">Las tareas se conectan a orígenes de datos externos para recuperar o guardar datos mediante un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-103">Tasks connect to external data sources to retrieve or save data by using a connection manager.</span></span> <span data-ttu-id="4ae2c-104">En tiempo de diseño, un administrador de conexiones representa una conexión lógica y describe información clave como el nombre de servidor y las propiedades de autenticación.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-104">At design time, a connection manager represents a logical connection, and describes key information such as the server name and any authentication properties.</span></span> <span data-ttu-id="4ae2c-105">En tiempo de ejecución, las tareas llaman al método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> del administrador de conexiones para establecer la conexión física al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-105">At run time, tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager to establish the physical connection to the data source.</span></span>  
  
 <span data-ttu-id="4ae2c-106">Dado que un paquete puede contener muchas tareas, cada una de los cuales puede tener conexiones a orígenes de datos distintos, el paquete realiza el seguimiento de todos los administradores de conexión de una colección, la colección <xref:Microsoft.SqlServer.Dts.Runtime.Connections>.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-106">Because a package can contain many tasks, each of which may have connections to different data sources, the package tracks all the connection managers in a collection, the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection.</span></span> <span data-ttu-id="4ae2c-107">Las tareas utilizan la colección del paquete para buscar el administrador de conexiones que utilizarán durante la validación y ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-107">Tasks use the collection in their package to find the connection manager that they will use during validation and execution.</span></span> <span data-ttu-id="4ae2c-108">La colección <xref:Microsoft.SqlServer.Dts.Runtime.Connections> es el primer parámetro de los métodos <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-108">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection is the first parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="4ae2c-109">Puede impedir que la tarea use el administrador de conexiones incorrecto mostrando los objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> de la colección al usuario, mediante un cuadro de diálogo o una lista desplegable de la interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-109">You can prevent the task from using the wrong connection manager by displaying the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects from the collection to the user, by using a dialog box or drop-down list in the graphical user interface.</span></span> <span data-ttu-id="4ae2c-110">Esto proporciona al usuario una manera de seleccionar entre únicamente los objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> del tipo adecuado contenidos en el paquete.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-110">This gives the user a way to select from among only those <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects of the appropriate type that are contained in the package.</span></span>  
  
 <span data-ttu-id="4ae2c-111">Las tareas llaman al método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> para establecer la conexión física al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-111">Tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection to the data source.</span></span> <span data-ttu-id="4ae2c-112">El método devuelve el objeto de conexión subyacente que la tarea puede usar a continuación.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-112">The method returns the underlying connection object that can then be used by the task.</span></span> <span data-ttu-id="4ae2c-113">Dado que el administrador de conexiones aísla los detalles de la implementación del objeto de conexión subyacente de la tarea, la tarea solo tiene que llamar al método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> para establecer la conexión y no tiene que preocuparse de otros aspectos de la conexión.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-113">Because the connection manager isolates the implementation details of the underlying connection object from the task, the task only has to call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the connection, and does not have to be concerned with other aspects of the connection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae2c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ae2c-114">Example</span></span>  
 <span data-ttu-id="4ae2c-115">En el código de ejemplo siguiente se muestra la validación del nombre <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> en los métodos Valide y Execute, y se muestra cómo utilizar el método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> para establecer la conexión física en el método Execute.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-115">The following sample code demonstrates validation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> name in the Validate and Execute methods, and shows how to use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection in the Execute method.</span></span>  
  
```csharp  
private string connectionManagerName = "";  
  
public string ConnectionManagerName  
{  
  get { return this.connectionManagerName; }  
  set { this.connectionManagerName = value; }  
}  
  
public override DTSExecResult Validate(  
  Connections connections, VariableDispenser variableDispenser,  
  IDTSComponentEvents componentEvents, IDTSLogging log)  
{  
  // If the connection manager exists, validation is successful;  
  // otherwise, fail validation.  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception e)  
  {  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
  
public override DTSExecResult Execute(Connections connections,   
  VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,   
  IDTSLogging log, object transaction)  
{  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    object connection = cm.AcquireConnection(transaction);  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception exception)  
  {  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
```  
  
```vb  
Private _connectionManagerName As String = ""  
  
Public Property ConnectionManagerName() As String  
  Get  
    Return Me._connectionManagerName  
  End Get  
  Set(ByVal Value As String)  
    Me._connectionManagerName = value  
  End Set  
End Property  
  
Public Overrides Function Validate( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  ' If the connection manager exists, validation is successful;  
  ' otherwise fail validation.  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Return DTSExecResult.Success  
  Catch e As System.Exception  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
  
Public Overrides Function Execute( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging, ByVal transaction As Object) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Dim connection As Object = cm.AcquireConnection(transaction)  
    Return DTSExecResult.Success  
  Catch exception As System.Exception  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
```  
  
<span data-ttu-id="4ae2c-116">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4ae2c-116">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4ae2c-117">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="4ae2c-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4ae2c-118">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="4ae2c-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4ae2c-119">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="4ae2c-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae2c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ae2c-120">See Also</span></span>  
 <span data-ttu-id="4ae2c-121">[Integration Services &#40;SSIS&#41; conexiones](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="4ae2c-121">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="4ae2c-122">Crear administradores de conexiones</span><span class="sxs-lookup"><span data-stu-id="4ae2c-122">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
