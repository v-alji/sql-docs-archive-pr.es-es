---
title: Desconectar de una instancia de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, disconnecting
- SMO [SQL Server], disconnecting
- instances of SQL Server, disconnecting
- disconnecting [SMO]
ms.assetid: 4ca7f7eb-6b3f-4c73-ac63-88afa8570b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3514fce8fb8f1ccc8bd1b54acfa27825eaebbd34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676990"
---
# <a name="disconnecting-from-an-instance-of-sql-server"></a><span data-ttu-id="37966-102">Desconectar de una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="37966-102">Disconnecting from an Instance of SQL Server</span></span>
  <span data-ttu-id="37966-103">No se requiere cerrar ni desconectar manualmente los objetos de Objetos de administración de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SMO).</span><span class="sxs-lookup"><span data-stu-id="37966-103">Manually closing and disconnecting [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects is not required.</span></span> <span data-ttu-id="37966-104">Las conexiones se abren y se cierra según se requiere.</span><span class="sxs-lookup"><span data-stu-id="37966-104">Connections are opened and closed as required.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="37966-105">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="37966-105">Connection Pooling</span></span>  
 <span data-ttu-id="37966-106">Cuando se llama al método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>, la conexión no se libera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="37966-106">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not automatically released.</span></span> <span data-ttu-id="37966-107">Para liberar la conexión al grupo de conexiones, se debe llamar al método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> explícitamente.</span><span class="sxs-lookup"><span data-stu-id="37966-107">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method must be called explicitly to release the connection to the connection pool.</span></span> <span data-ttu-id="37966-108">También puede solicitar una conexión no agrupada.</span><span class="sxs-lookup"><span data-stu-id="37966-108">Also, you can request a non-pooled connection.</span></span> <span data-ttu-id="37966-109">Para ello, establezca la propiedad <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> de la propiedad <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> que hace referencia al objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="37966-109">You do this by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property that references the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="disconnecting-from-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="37966-110">Desconectar de una instancia de SQL Server para RMO</span><span class="sxs-lookup"><span data-stu-id="37966-110">Disconnecting from an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="37966-111">El cierre de las conexiones de servidor cuando se programa con RMO funciona de forma ligeramente diferente a SMO.</span><span class="sxs-lookup"><span data-stu-id="37966-111">Closing server connections when you are programming with RMO works slightly different from SMO.</span></span>  
  
 <span data-ttu-id="37966-112">Dado que la conexión de servidor para un objeto RMO se mantiene mediante el <xref:Microsoft.SqlServer.Management.Common.ServerConnection> objeto, este objeto también se utiliza al desconectar de una instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando se programa con RMO.</span><span class="sxs-lookup"><span data-stu-id="37966-112">Because the server connection for an RMO object is maintained by the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, this object is also used when disconnecting from an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when you program by using RMO.</span></span> <span data-ttu-id="37966-113">Para cerrar una conexión con el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, llame al método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> del objeto RMO.</span><span class="sxs-lookup"><span data-stu-id="37966-113">To close a connection by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method of the RMO object.</span></span> <span data-ttu-id="37966-114">Una vez cerrada la conexión, no se pueden utilizar objetos RMO.</span><span class="sxs-lookup"><span data-stu-id="37966-114">After the connection has been closed, RMO objects cannot be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37966-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37966-115">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-basic"></a><span data-ttu-id="37966-116">Cerrar y desconectar un objeto SMO en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37966-116">Closing and Disconnecting an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="37966-117">En este ejemplo de código se muestra cómo solicitar una conexión no agrupada mediante el establecimiento de la propiedad <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> de la propiedad de objeto <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="37966-117">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB4](SMO How to#SMO_VB4)]  -->  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-c"></a><span data-ttu-id="37966-118">Cerrar y desconectar un objeto SMO en Visual C#</span><span class="sxs-lookup"><span data-stu-id="37966-118">Closing and Disconnecting an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="37966-119">En este ejemplo de código se muestra cómo solicitar una conexión no agrupada mediante el establecimiento de la propiedad <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> de la propiedad de objeto <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="37966-119">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
//Disable automatic disconnection.   
srv.ConnectionContext.AutoDisconnectMode = AutoDisconnectMode.NoAutoDisconnect;   
//Connect to the local, default instance of SQL Server.   
srv.ConnectionContext.Connect();   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
//Disconnect explicitly.   
srv.ConnectionContext.Disconnect();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="37966-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37966-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
