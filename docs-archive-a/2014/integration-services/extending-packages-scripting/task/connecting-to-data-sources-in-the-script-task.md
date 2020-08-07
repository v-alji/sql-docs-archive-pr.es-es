---
title: Conectarse a orígenes de datos de la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- connections [Integration Services], scripts
- Integration Services packages, connections
- connection managers [Integration Services], scripts
- scripts [Integration Services], connections
- SSIS packages, connections
- packages [Integration Services], connections
- Script task [Integration Services], connections
- Connections property
- SQL Server Integration Services packages, connections
- SSIS Script task, connections
ms.assetid: 9c008380-715b-455b-9da7-22572d67c388
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c8374271c7972498361a83e4bbe87ad12265827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745912"
---
# <a name="connecting-to-data-sources-in-the-script-task"></a><span data-ttu-id="46139-102">Conectarse a orígenes de datos de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="46139-102">Connecting to Data Sources in the Script Task</span></span>
  <span data-ttu-id="46139-103">Los administradores de conexiones proporcionan acceso a los orígenes de datos configurados en el paquete.</span><span class="sxs-lookup"><span data-stu-id="46139-103">Connection managers provide access to data sources that have been configured in the package.</span></span> <span data-ttu-id="46139-104">Para más información, vea [Conexiones de Integration Services &#40;SSIS&#41;](../../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="46139-104">For more information, see [Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
 <span data-ttu-id="46139-105">La tarea Script tiene acceso a estos administradores de conexiones a través de la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> del objeto**Dts**.</span><span class="sxs-lookup"><span data-stu-id="46139-105">The Script task can access these connection managers through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property of the **Dts** object.</span></span> <span data-ttu-id="46139-106">Todos los administradores de conexión de la colección <xref:Microsoft.SqlServer.Dts.Runtime.Connections> almacenan información sobre cómo conectarse al origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="46139-106">Each connection manager in the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection stores information about how to connect to the underlying data source.</span></span>  
  
 <span data-ttu-id="46139-107">Cuando llama al método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> de un administrador de conexiones, el administrador de conexiones se conecta al origen de datos, si aún no está conectado, y devuelve la información de conexión o la conexión adecuada para que la utilice en el código de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="46139-107">When you call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a connection manager, the connection manager connects to the data source, if it is not already connected, and returns the appropriate connection or connection information for you to use in your Script task code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="46139-108">Debe conocer el tipo de conexión que devuelve el administrador de conexiones antes de llamar a `AcquireConnection` .</span><span class="sxs-lookup"><span data-stu-id="46139-108">You must know the type of connection returned by the connection manager before calling `AcquireConnection`.</span></span> <span data-ttu-id="46139-109">Dado que la tarea Script tiene habilitado `Option Strict`, debe convertir la conexión, que se devuelve como tipo `Object`, al tipo de conexión adecuado antes de poder utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="46139-109">Because the Script task has `Option Strict` enabled, you must cast the connection, which is returned as type `Object`, to the appropriate connection type before you can use it.</span></span>  
  
 <span data-ttu-id="46139-110">Puede utilizar el método <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> de la colección <xref:Microsoft.SqlServer.Dts.Runtime.Connections> devuelto por la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> para buscar una conexión existente antes de utilizar la conexión en el código.</span><span class="sxs-lookup"><span data-stu-id="46139-110">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property to look for an existing connection before using the connection in your code.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="46139-111">No puede llamar al método AcquireConnection de los administradores de conexiones que devuelvan objetos no administrados, como el administrador de conexiones OLE DB y el administrador de conexiones Excel, en el código administrado de una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="46139-111">You cannot call the AcquireConnection method of connection managers that return unmanaged objects, such as the OLE DB connection manager and the Excel connection manager, in the managed code of a Script task.</span></span> <span data-ttu-id="46139-112">Sin embargo, puede leer la propiedad ConnectionString de estos administradores de conexión y conectarse directamente al origen de datos en el código utilizando la cadena de conexión con un `OledbConnection` del espacio de nombres **System. Data. OleDb** .</span><span class="sxs-lookup"><span data-stu-id="46139-112">However, you can read the ConnectionString property of these connection managers, and connect to the data source directly in your code by using the connection string with an `OledbConnection` from the **System.Data.OleDb** namespace.</span></span>  
>   
>  <span data-ttu-id="46139-113">Si debe llamar al método AcquireConnection de un administrador de conexiones que devuelve un objeto no administrado, utilice un administrador de conexiones [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46139-113">If you must call the AcquireConnection method of a connection manager that returns an unmanaged object, use an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager.</span></span> <span data-ttu-id="46139-114">Al configurar el administrador de conexiones [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] para utilizar un proveedor OLE DB, se conecta mediante el proveedor de datos de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] para OLE DB.</span><span class="sxs-lookup"><span data-stu-id="46139-114">When you configure the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager to use an OLE DB provider, it connects by using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB.</span></span> <span data-ttu-id="46139-115">En este caso, el método AcquireConnection devuelve un `System.Data.OleDb.OleDbConnection` objeto en lugar de un objeto no administrado.</span><span class="sxs-lookup"><span data-stu-id="46139-115">In this case, the AcquireConnection method returns a `System.Data.OleDb.OleDbConnection` instead of an unmanaged object.</span></span> <span data-ttu-id="46139-116">Para configurar un administrador de conexiones [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] para su uso con un origen de datos Excel, seleccione el proveedor OLE DB de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] para Jet, especifique un archivo de Excel y, a continuación, escriba `Excel 8.0` (para Excel 97 y posterior) como el valor de **Propiedades extendidas** en la página **Todas** del cuadro de diálogo **Administrador de conexiones**.</span><span class="sxs-lookup"><span data-stu-id="46139-116">To configure an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager for use with an Excel data source, select the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB Provider for Jet, specify an Excel file, and enter `Excel 8.0` (for Excel 97 and later) as the value of **Extended Properties** on the **All** page of the **Connection Manager** dialog box.</span></span>  
  
## <a name="connections-example"></a><span data-ttu-id="46139-117">Ejemplo de conexiones</span><span class="sxs-lookup"><span data-stu-id="46139-117">Connections Example</span></span>  
 <span data-ttu-id="46139-118">En el ejemplo siguiente se muestra cómo obtener acceso a los administradores de conexión desde dentro de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="46139-118">The following example demonstrates how to access connection managers from within the Script task.</span></span> <span data-ttu-id="46139-119">En el ejemplo se supone que ha creado y configurado un administrador de conexiones [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] denominado **Test ADO.NET Connection** y un administrador de conexiones de archivos planos denominado **Test Flat File Connection**.</span><span class="sxs-lookup"><span data-stu-id="46139-119">The sample assumes that you have created and configured an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager named **Test ADO.NET Connection** and a Flat File connection manager named **Test Flat File Connection**.</span></span> <span data-ttu-id="46139-120">Observe que el administrador de conexiones [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] devuelve un objeto `SqlConnection` que puede utilizar inmediatamente para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="46139-120">Note that the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager returns a `SqlConnection` object that you can use immediately to connect to the data source.</span></span> <span data-ttu-id="46139-121">El administrador de conexiones de archivos planos, por otro lado, devuelve solamente una cadena que contiene la ruta de acceso y el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="46139-121">The Flat File connection manager, on the other hand, returns only a string that contains the path and file name.</span></span> <span data-ttu-id="46139-122">Debe utilizar los métodos del espacio de nombres `System.IO` para abrir el archivo plano y trabajar con éste.</span><span class="sxs-lookup"><span data-stu-id="46139-122">You must use methods from the `System.IO` namespace to open and work with the flat file.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myADONETConnection As SqlClient.SqlConnection  
    myADONETConnection = _  
        DirectCast(Dts.Connections("Test ADO.NET Connection").AcquireConnection(Dts.Transaction), _  
        SqlClient.SqlConnection)  
    MsgBox(myADONETConnection.ConnectionString, _  
        MsgBoxStyle.Information, "ADO.NET Connection")  
  
    Dim myFlatFileConnection As String  
    myFlatFileConnection = _  
        DirectCast(Dts.Connections("Test Flat File Connection").AcquireConnection(Dts.Transaction), _  
        String)  
    MsgBox(myFlatFileConnection, MsgBoxStyle.Information, "Flat File Connection")  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
  
public class ScriptMain  
{  
  
        public void Main()  
        {  
            SqlConnection myADONETConnection = new SqlConnection();  
            myADONETConnection = (SqlConnection)(Dts.Connections["Test ADO.NET Connection"].AcquireConnection(Dts.Transaction)as SqlConnection);  
            MessageBox.Show(myADONETConnection.ConnectionString, "ADO.NET Connection");  
  
            string myFlatFileConnection;  
            myFlatFileConnection = (string)(Dts.Connections["Test Flat File Connection"].AcquireConnection(Dts.Transaction) as String);  
            MessageBox.Show(myFlatFileConnection, "Flat File Connection");  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
  
```  
  
<span data-ttu-id="46139-123">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="46139-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="46139-124">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="46139-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="46139-125">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="46139-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="46139-126">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="46139-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46139-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46139-127">See Also</span></span>  
 <span data-ttu-id="46139-128">[Integration Services &#40;SSIS&#41; conexiones](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="46139-128">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="46139-129">Crear administradores de conexiones</span><span class="sxs-lookup"><span data-stu-id="46139-129">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
