---
title: Usar servidores vinculados en SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- linked servers [SQL Server], SMO
ms.assetid: 0ea8837b-2596-4df1-b065-3bb717c9f22c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 58804e2be1edfa685a57f56c173c77a50e0f9126
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663330"
---
# <a name="using-linked-servers-in-smo"></a><span data-ttu-id="6e83a-102">Utilizar servidores vinculados en SMO</span><span class="sxs-lookup"><span data-stu-id="6e83a-102">Using Linked Servers in SMO</span></span>
  <span data-ttu-id="6e83a-103">Un servidor vinculado representa un origen de datos OLE DB en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="6e83a-103">A linked server represents an OLE DB data source on a remote server.</span></span> <span data-ttu-id="6e83a-104">Los orígenes de datos OLE DB remotos están vinculados a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la utilización del objeto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="6e83a-104">Remote OLE DB data sources are linked to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span>  
  
 <span data-ttu-id="6e83a-105">Los servidores de bases de datos remotos se pueden vincular a la instancia actual de mediante [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] un proveedor de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="6e83a-105">Remote database servers can be linked to the current instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using an OLE DB Provider.</span></span> <span data-ttu-id="6e83a-106">EN SMO, los servidores vinculados están representados por el objeto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="6e83a-106">In SMO, linked servers are represented by the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="6e83a-107">La propiedad <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> hace referencia a una colección de objetos <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin>.</span><span class="sxs-lookup"><span data-stu-id="6e83a-107">The <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> property references a collection of <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin> objects.</span></span> <span data-ttu-id="6e83a-108">Estos objetos almacenan las credenciales de inicio de sesión necesarias para establecer una conexión con el servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="6e83a-108">These store the logon credentials that are required to establish a connection with the linked server.</span></span>  
  
## <a name="ole-db-providers"></a><span data-ttu-id="6e83a-109">Proveedores OLE-DB</span><span class="sxs-lookup"><span data-stu-id="6e83a-109">OLE-DB Providers</span></span>  
 <span data-ttu-id="6e83a-110">En SMO, una colección de objetos <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings> representa los proveedores OLE DB instalados.</span><span class="sxs-lookup"><span data-stu-id="6e83a-110">In SMO, installed OLE-DB providers are represented by a collection of <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e83a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e83a-111">Example</span></span>  
 <span data-ttu-id="6e83a-112">Para el siguiente ejemplo de código, deberá seleccionar el entorno de programación, la plantilla de programación y el lenguaje de programación en los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e83a-112">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="6e83a-113">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) y [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="6e83a-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-basic"></a><span data-ttu-id="6e83a-114">Crear un vínculo a un servidor de proveedor OLE-DB en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e83a-114">Creating a link to an OLE-DB Provider Server in Visual Basic</span></span>  
 <span data-ttu-id="6e83a-115">En el ejemplo de código se muestra cómo crear un vínculo a un origen de datos heterogéneo OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="6e83a-115">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="6e83a-116">Al especificar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como el nombre del producto, se obtiene acceso a los datos en el servidor vinculado mediante el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB del cliente, que es el proveedor de OLE DB oficial para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e83a-116">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLinkedServers1](SMO How to#SMO_VBLinkedServers1)]  -->  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-c"></a><span data-ttu-id="6e83a-117">Crear un vínculo a un servidor de proveedor OLE-DB en Visual C#</span><span class="sxs-lookup"><span data-stu-id="6e83a-117">Creating a link to an OLE-DB Provider Server in Visual C#</span></span>  
 <span data-ttu-id="6e83a-118">En el ejemplo de código se muestra cómo crear un vínculo a un origen de datos heterogéneo OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="6e83a-118">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="6e83a-119">Especificando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como nombre de producto, se obtiene acceso a los datos en el servidor vinculado utilizando el proveedor OLE DB de cliente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , que es el proveedor OLE DB oficial para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e83a-119">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
{   
   Server srv = new Server();   
   //Create a linked server.   
   LinkedServer lsrv = default(LinkedServer);   
   lsrv = new LinkedServer(srv, "OLEDBSRV");   
   //When the product name is SQL Server the remaining properties are   
   //not required to be set.   
   lsrv.ProductName = "SQL Server";   
   lsrv.Create();   
}   
```  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-powershell"></a><span data-ttu-id="6e83a-120">Crear un vínculo a un servidor de proveedor OLE-DB en PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e83a-120">Creating a link to an OLE-DB Provider Server in PowerShell</span></span>  
 <span data-ttu-id="6e83a-121">En el ejemplo de código se muestra cómo crear un vínculo a un origen de datos heterogéneo OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="6e83a-121">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="6e83a-122">Especificando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como nombre de producto, se obtiene acceso a los datos en el servidor vinculado utilizando el proveedor OLE DB de cliente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , que es el proveedor OLE DB oficial para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e83a-122">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$svr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a linked server object which corresponds to an OLEDB type of SQL server product  
$lsvr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LinkedServer -ArgumentList $svr,"OLEDBSRV"  
  
#When the product name is SQL Server the remaining properties are not required to be set.
$lsvr.ProductName = "SQL Server"
  
#Create the Database Object  
$lsvr.Create()
```  
