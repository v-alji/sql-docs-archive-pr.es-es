---
title: Administrar servicios y configuración de red mediante el proveedor WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- WMI provider [SMO]
- services [SQL Server], SMO
- network settings [SMO]
- monitoring [SMO]
ms.assetid: ef8c3986-1098-4f21-b03a-f1f6bdb51c26
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1cd373c46460ac95dbe81469eeaa4b3bf9548d68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675247"
---
# <a name="managing-services-and-network-settings-by-using-wmi-provider"></a><span data-ttu-id="b9ab8-102">Administrar servicios y configuración de red utilizando el proveedor WMI</span><span class="sxs-lookup"><span data-stu-id="b9ab8-102">Managing Services and Network Settings by Using WMI Provider</span></span>
  <span data-ttu-id="b9ab8-103">El proveedor WMI es una interfaz publicada que la Consola de administración de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] (MMC) utiliza para administrar los servicios de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y protocolos de red.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-103">The WMI provider is a published interface that is used by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Management Console (MMC) to manage the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] services and network protocols.</span></span> <span data-ttu-id="b9ab8-104">En SMO, el objeto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> representa el proveedor WMI.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-104">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object represents the WMI Provider.</span></span>  
  
 <span data-ttu-id="b9ab8-105">El objeto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> funciona independientemente de la conexión establecida con el objeto <xref:Microsoft.SqlServer.Management.Smo.Server> a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y utiliza las credenciales de Windows para conectarse al servicio WMI.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-105">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object operates independently of the connection established with the <xref:Microsoft.SqlServer.Management.Smo.Server> object to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and uses Windows credentials to connect to the WMI service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9ab8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9ab8-106">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
 <span data-ttu-id="b9ab8-107">En el caso de los programas que utilizan el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor WMI, debe incluir la `Imports` instrucción para certificar el espacio de nombres WMI.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-107">For programs that use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] WMI provider, you must include the `Imports` statement to qualify the WMI namespace.</span></span> <span data-ttu-id="b9ab8-108">Inserte la instrucción después de las demás instrucciones `Imports`, antes de cualquier declaración de la aplicación, como:</span><span class="sxs-lookup"><span data-stu-id="b9ab8-108">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Wmi`  
  
## <a name="stopping-and-restarting-the-microsoft-sql-server-service-to-the-instance-of-sql-server-in-visual-basic"></a><span data-ttu-id="b9ab8-109">Detener y reiniciar el servicio de Microsoft SQL Server para la instancia de SQL Server en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9ab8-109">Stopping and Restarting the Microsoft SQL Server Service to the Instance of SQL Server in Visual Basic</span></span>  
 <span data-ttu-id="b9ab8-110">En este ejemplo de código se muestra cómo detener e iniciar servicios utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> de SMO.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-110">This code example shows how to stop and start services by using the SMO <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object.</span></span> <span data-ttu-id="b9ab8-111">Esto proporciona una interfaz al proveedor WMI para la administración de configuración.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-111">This provides an interface to the WMI Provider for Configuration Management.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBWMIService1](SMO How to#SMO_VBWMIService1)]  -->  
  
## <a name="enabling-a-server-protocol-using-a-urn-string-in-visual-basic"></a><span data-ttu-id="b9ab8-112">Habilitar un protocolo de servidor usando una cadena URN en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9ab8-112">Enabling a Server Protocol using a URN String in Visual Basic</span></span>  
 <span data-ttu-id="b9ab8-113">En este ejemplo de código se muestra cómo identificar un protocolo de servidor usando un objeto URN y, a continuación, se muestra cómo habilitar el protocolo.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-113">The code example shows how to identify a server protocol using a URN object, and then enable the protocol.</span></span>  
  
```vb
'This program must run with administrator privileges.  
        'Declare the ManagedComputer WMI interface.  
        Dim mc As New ManagedComputer()  
  
        'Create a URN object that represents the TCP server protocol.  
        Dim u As New Urn("ManagedComputer[@Name='V-ROBMA3']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']")  
  
        'Declare the serverProtocol variable and return the ServerProtocol object.  
        Dim sp As ServerProtocol  
        sp = mc.GetSmoObject(u)  
  
        'Enable the protocol.  
        sp.IsEnabled = True  
  
        'propagate back to the service  
        sp.Alter()  
```  
  
## <a name="enabling-a-server-protocol-using-a-urn-string-in-powershell"></a><span data-ttu-id="b9ab8-114">Habilitar un protocolo de servidor usando una cadena URN en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9ab8-114">Enabling a Server Protocol using a URN String in PowerShell</span></span>  
 <span data-ttu-id="b9ab8-115">En este ejemplo de código se muestra cómo identificar un protocolo de servidor usando un objeto URN y, a continuación, se muestra cómo habilitar el protocolo.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-115">The code example shows how to identify a server protocol using a URN object, and then enable the protocol.</span></span>  
  
```powershell
#This example shows how to identify a server protocol using a URN object, and then enable the protocol  
#This program must run with administrator privileges.  
  
#Load the assembly containing the classes used in this example  
[reflection.assembly]::LoadWithPartialName("Microsoft.SqlServer.SqlWmiManagement")  
  
#Get a managed computer instance  
$mc = New-Object -TypeName Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer  
  
#Create a URN object that represents the TCP server protocol  
#Change 'MyPC' to the name of the your computer   
$urn = New-Object -TypeName Microsoft.SqlServer.Management.Sdk.Sfc.Urn -argumentlist "ManagedComputer[@Name='MyPC']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
  
#Get the protocol object  
$sp = $mc.GetSmoObject($urn)  
  
#enable the protocol on the object  
$sp.IsEnabled = $true  
  
#propagate back to actual service  
$sp.Alter()  
```  
  
## <a name="starting-and-stopping-a-service-in-visual-c"></a><span data-ttu-id="b9ab8-116">Iniciar y detener un servicio en Visual c#</span><span class="sxs-lookup"><span data-stu-id="b9ab8-116">Starting and stopping a service in Visual C#</span></span>  
 <span data-ttu-id="b9ab8-117">En el ejemplo de código se muestra cómo se detiene e inicia una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-117">The code example shows how to stop and start an instance of SQL Server.</span></span>  
  
```csharp
{   
   //Declare and create an instance of the ManagedComputer   
   //object that represents the WMI Provider services.   
   ManagedComputer mc;   
   mc = new ManagedComputer();   
   //Iterate through each service registered with the WMI Provider.   
  
   foreach (Service svc in mc.Services)  
   {   
      Console.WriteLine(svc.Name);   
   }   
//Reference the Microsoft SQL Server service.   
  Service Mysvc = mc.Services["MSSQLSERVER"];   
//Stop the service if it is running and report on the status  
// continuously until it has stopped.   
   if (Mysvc.ServiceState == ServiceState.Running) {   
      Mysvc.Stop();   
      Console.WriteLine(string.Format("{0} service state is {1}", Mysvc.Name, Mysvc.ServiceState));   
      while (!(string.Format("{0}", Mysvc.ServiceState) == "Stopped")) {   
         Console.WriteLine(string.Format("{0}", Mysvc.ServiceState));   
          Mysvc.Refresh();   
      }   
      Console.WriteLine(string.Format("{0} service state is {1}", Mysvc.Name, Mysvc.ServiceState));   
//Start the service and report on the status continuously   
//until it has started.   
      Mysvc.Start();   
      while (!(string.Format("{0}", Mysvc.ServiceState) == "Running")) {   
         Console.WriteLine(string.Format("{0}", Mysvc.ServiceState));   
         Mysvc.Refresh();   
      }   
      Console.WriteLine(string.Format("{0} service state is {1}", Mysvc.Name, Mysvc.ServiceState));  
      Console.ReadLine();  
   }   
   else {   
      Console.WriteLine("SQL Server service is not running.");  
      Console.ReadLine();  
   }   
}  
```  
  
## <a name="starting-and-stopping-a-service-in-powershell"></a><span data-ttu-id="b9ab8-118">Iniciar y detener un servicio en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9ab8-118">Starting and stopping a service in PowerShell</span></span>  
 <span data-ttu-id="b9ab8-119">En el ejemplo de código se muestra cómo se detiene e inicia una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-119">The code example shows how to stop and start an instance of SQL Server.</span></span>  
  
```powershell
#Load the assembly containing the objects used in this example  
[reflection.assembly]::LoadWithPartialName("Microsoft.SqlServer.SqlWmiManagement")  
  
#Get a managed computer instance  
$mc = New-Object -TypeName Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer  
  
#List out all sql server instnces running on this mc  
foreach ($Item in $mc.Services){$Item.Name}  
  
#Get the default sql server datbase engine service  
$svc = $mc.Services["MSSQLSERVER"]  
  
# for stopping and starting services PowerShell must run as administrator  
  
#Stop this service  
$svc.Stop()  
$svc.Refresh()  
while ($svc.ServiceState -ne "Stopped")  
{  
$svc.Refresh()  
$svc.ServiceState  
}  
"Service" + $svc.Name + " is now stopped"  
"Starting " + $svc.Name  
$svc.Start()  
$svc.Refresh()  
while ($svc.ServiceState -ne "Running")  
{  
$svc.Refresh()  
$svc.ServiceState  
}  
$svc.ServiceState  
"Service" + $svc.Name + "is now started"
```  
  
## <a name="see-also"></a><span data-ttu-id="b9ab8-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9ab8-120">See Also</span></span>  
 [<span data-ttu-id="b9ab8-121">Conceptos del proveedor WMI de administración de configuración</span><span class="sxs-lookup"><span data-stu-id="b9ab8-121">WMI Provider for Configuration Management Concepts</span></span>](../../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
