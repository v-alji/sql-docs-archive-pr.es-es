---
title: Conceder, revocar y denegar permisos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- granting permissions [SMO]
- denying permissions [SMO]
- permissions [SMO]
- revoking permissions [SMO]
ms.assetid: b0eb0f60-3e56-4880-b645-138832b38a1e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 059d9f6d4426f12de175654bdb196484d470c92f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744039"
---
# <a name="granting-revoking-and-denying-permissions"></a><span data-ttu-id="c40a9-102">Conceder, revocar y denegar permisos</span><span class="sxs-lookup"><span data-stu-id="c40a9-102">Granting, Revoking, and Denying Permissions</span></span>
  <span data-ttu-id="c40a9-103">El objeto <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> se utiliza para asignar un conjunto de permisos o un permiso de servidor individual al objeto <xref:Microsoft.SqlServer.Management.Smo.ServerPermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="c40a9-103">The <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> object is used to assign a set of permissions or an individual server permission to the <xref:Microsoft.SqlServer.Management.Smo.ServerPermissionSet> object.</span></span> <span data-ttu-id="c40a9-104">Para los permisos en el nivel de servidor, el cesionario hace referencia a un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c40a9-104">For server level permissions, the grantee refers to a logon.</span></span> <span data-ttu-id="c40a9-105">Se hace una lista de los inicios de sesión autenticados por Windows como nombres de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="c40a9-105">Logons authenticated by Windows are listed as Windows user names.</span></span> <span data-ttu-id="c40a9-106">Cuando este ejemplo de código se ejecuta, revoca el permiso del cesionario y comprueba se ha quitado con el método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumServerPermissions%2A>.</span><span class="sxs-lookup"><span data-stu-id="c40a9-106">When this code sample runs, it revokes the permission from the grantee and verifies it has been removed with the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumServerPermissions%2A> method.</span></span>  
  
 <span data-ttu-id="c40a9-107">Los permisos de bases de datos y permisos de objetos de bases de datos pueden asignarse de igual forma utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.DatabasePermissionSet> y el objeto <xref:Microsoft.SqlServer.Management.Smo.ObjectPermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="c40a9-107">Database permissions and database object permissions can be assigned similarly by using the <xref:Microsoft.SqlServer.Management.Smo.DatabasePermissionSet> object and the <xref:Microsoft.SqlServer.Management.Smo.ObjectPermissionSet> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c40a9-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c40a9-108">Example</span></span>  
 <span data-ttu-id="c40a9-109">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="c40a9-109">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="c40a9-110">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="c40a9-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="granting-server-permissions-in-visual-basic"></a><span data-ttu-id="c40a9-111">Conceder permisos de servidor en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c40a9-111">Granting Server Permissions in Visual Basic</span></span>  
 <span data-ttu-id="c40a9-112">En este ejemplo de código se conceden los permisos Crear extremo y Modificar cualquier extremo al inicio de sesión especificado y, a continuación, se enumeran y se muestran los permisos.</span><span class="sxs-lookup"><span data-stu-id="c40a9-112">This code example grants the Create Endpoint and Alter Any Endpoint permissions to the specified login, and then enumerates and displays the permissions.</span></span> <span data-ttu-id="c40a9-113">Se revoca uno de los permisos y se enumeran los permisos de nuevo a continuación.</span><span class="sxs-lookup"><span data-stu-id="c40a9-113">One of the permissions is revoked, and then the permissions are enumerated again.</span></span> <span data-ttu-id="c40a9-114">En este ejemplo se supone que el inicio de sesión especificado tiene los permisos especificados para comenzar.</span><span class="sxs-lookup"><span data-stu-id="c40a9-114">This example assumes that the specified login has the specified permissions to start with.</span></span>  
  
```vb
' compile with: /r:Microsoft.SqlServer.Smo.dll /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll /r:Microsoft.SqlServer.SqlEnum.dll  
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
  
      ' Creating the logins (Grantee)  
      Dim vGrantee As [String] = "Grantee1"  
      Dim login As New Login(svr, vGrantee)  
      login.LoginType = LoginType.SqlLogin  
      login.Create("password@1")  
  
      Dim vGrantee2 As [String] = "Grantee2"  
      Dim login2 As New Login(svr, vGrantee2)  
      login2.LoginType = LoginType.SqlLogin  
      login2.Create("password@2")  
  
      ' Define a ServerPermissionSet that contains permission to Create Endpoint and Alter Any Endpoint.   
      Dim sps As New ServerPermissionSet(ServerPermission.CreateEndpoint)  
      sps.Add(ServerPermission.AlterAnyEndpoint)  
  
      ' Grant Create Endpoint and Alter Any Endpoint permissions to Grantee  
      svr.Grant(sps, vGrantee)  
      svr.Grant(sps, vGrantee2)  
  
      ' Enumerate and display the server permissions in the set for the grantee specified in the vGrantee string variable.   
      Dim spis As ServerPermissionInfo() = svr.EnumServerPermissions(vGrantee, sps)  
      'enumerates all server permissions for the Grantee from the specified permission set  
      Console.WriteLine("====Before revoke===========")  
      For Each spi As ServerPermissionInfo In spis  
         Console.WriteLine(spi.Grantee + " has " & spi.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
  
      ' Revoke the create endpoint permission from the grantee.   
      svr.Revoke(New ServerPermissionSet(ServerPermission.CreateEndpoint), vGrantee)  
  
      ' Enumerate and display the server permissions in the set for the grantee specified in the vGrantee string variable.   
      spis = svr.EnumServerPermissions(vGrantee, sps)  
  
      Console.WriteLine("==After revoke=========")  
      For Each spi As ServerPermissionInfo In spis  
         Console.WriteLine(spi.Grantee + " has " & spi.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
  
      ' Grant the Create Server Role permission to the grantee.   
      svr.Grant(New ServerPermissionSet(ServerPermission.ViewAnyDatabase), vGrantee)  
      ' Enumerate and display the server permissions for the grantee specified in the vGrantee string variable.   
  
      ' enumerates all server permissions for the Grantee  
      spis = svr.EnumServerPermissions(vGrantee)  
  
      Console.WriteLine("==After grant========")  
  
      For Each spi As ServerPermissionInfo In spis  
         Console.WriteLine(spi.Grantee + " has " & spi.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine("")  
  
      ' Enumerate and display the server permissions in the set for all logins.   
      spis = svr.EnumServerPermissions(sps)  
      'enumerates all server permissions in the set for all logins  
      Console.WriteLine("==After grant========")  
  
      For Each spi As ServerPermissionInfo In spis  
         Console.WriteLine(spi.Grantee + " has " & spi.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine("")  
   End Sub  
End Class  
```  
  
## <a name="granting-server-permissions-in-visual-c"></a><span data-ttu-id="c40a9-115">Conceder permisos de servidor en Visual C#</span><span class="sxs-lookup"><span data-stu-id="c40a9-115">Granting Server Permissions in Visual C#</span></span>  
 <span data-ttu-id="c40a9-116">En este ejemplo de código se conceden los permisos Crear extremo y Modificar cualquier extremo al inicio de sesión especificado y, a continuación, se enumeran y se muestran los permisos.</span><span class="sxs-lookup"><span data-stu-id="c40a9-116">This code example grants the Create Endpoint and Alter Any Endpoint permissions to the specified login, and then enumerates and displays the permissions.</span></span> <span data-ttu-id="c40a9-117">Se revoca uno de los permisos y se enumeran los permisos de nuevo a continuación.</span><span class="sxs-lookup"><span data-stu-id="c40a9-117">One of the permissions is revoked, and then the permissions are enumerated again.</span></span> <span data-ttu-id="c40a9-118">En este ejemplo se supone que el inicio de sesión especificado tiene los permisos especificados para comenzar.</span><span class="sxs-lookup"><span data-stu-id="c40a9-118">This example assumes that the specified login has the specified permissions to start with.</span></span>  
  
```csharp
// compile with: /r:Microsoft.SqlServer.Smo.dll /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll /r:Microsoft.SqlServer.SqlEnum.dll  
using System;  
using Microsoft.SqlServer.Management.Smo;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
  
      // Creating the logins (Grantee)  
      String vGrantee = "Grantee1";  
      Login login = new Login(svr, vGrantee);  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      String vGrantee2 = "Grantee2";  
      Login login2 = new Login(svr, vGrantee2);  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@2");  
  
      // Define a ServerPermissionSet that contains permission to Create Endpoint and Alter Any Endpoint.   
      ServerPermissionSet sps = new ServerPermissionSet(ServerPermission.CreateEndpoint);  
      sps.Add(ServerPermission.AlterAnyEndpoint);  
  
      // Grant Create Endpoint and Alter Any Endpoint permissions to Grantee  
      svr.Grant(sps, vGrantee);  
      svr.Grant(sps, vGrantee2);  
  
      // Enumerate and display the server permissions in the set for the grantee specified in the vGrantee string variable.   
      ServerPermissionInfo[] spis = svr.EnumServerPermissions(vGrantee, sps); //enumerates all server permissions for the Grantee from the specified permission set  
  
      Console.WriteLine("====Before revoke===========");  
      foreach (ServerPermissionInfo spi in spis) {  
         Console.WriteLine(spi.Grantee + " has " + spi.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
  
      // Revoke the create endpoint permission from the grantee.   
      svr.Revoke(new ServerPermissionSet(ServerPermission.CreateEndpoint), vGrantee);  
  
      // Enumerate and display the server permissions in the set for the grantee specified in the vGrantee string variable.   
      spis = svr.EnumServerPermissions(vGrantee, sps);  
  
      Console.WriteLine("==After revoke=========");  
      foreach (ServerPermissionInfo spi in spis) {  
         Console.WriteLine(spi.Grantee + " has " + spi.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
  
      // Grant the Create Server Role permission to the grantee.   
      svr.Grant(new ServerPermissionSet(ServerPermission.ViewAnyDatabase), vGrantee);  
      // Enumerate and display the server permissions for the grantee specified in the vGrantee string variable.   
  
      // enumerates all server permissions for the Grantee  
      spis = svr.EnumServerPermissions(vGrantee);   
  
      Console.WriteLine("==After grant========");  
  
      foreach (ServerPermissionInfo spi in spis) {  
         Console.WriteLine(spi.Grantee + " has " + spi.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine("");  
  
      // Enumerate and display the server permissions in the set for all logins.   
      spis = svr.EnumServerPermissions(sps); //enumerates all server permissions in the set for all logins  
  
      Console.WriteLine("==After grant========");  
  
      foreach (ServerPermissionInfo spi in spis) {  
         Console.WriteLine(spi.Grantee + " has " + spi.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine("");  
   }  
}  
```  
  
## <a name="granting-server-permissions-in-powershell"></a><span data-ttu-id="c40a9-119">Conceder permisos de servidor en PowerShell</span><span class="sxs-lookup"><span data-stu-id="c40a9-119">Granting Server Permissions in PowerShell</span></span>  
 <span data-ttu-id="c40a9-120">En este ejemplo de código se conceden los permisos Crear extremo y Modificar cualquier extremo al inicio de sesión especificado y, a continuación, se enumeran y se muestran los permisos.</span><span class="sxs-lookup"><span data-stu-id="c40a9-120">This code example grants the Create Endpoint and Alter Any Endpoint permissions to the specified login, and then enumerates and displays the permissions.</span></span> <span data-ttu-id="c40a9-121">Se revoca uno de los permisos y se enumeran los permisos de nuevo a continuación.</span><span class="sxs-lookup"><span data-stu-id="c40a9-121">One of the permissions is revoked, and then the permissions are enumerated again.</span></span> <span data-ttu-id="c40a9-122">En este ejemplo se supone que el inicio de sesión especificado tiene los permisos especificados para comenzar.</span><span class="sxs-lookup"><span data-stu-id="c40a9-122">This example assumes that the specified login has the specified permissions to start with.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = get-item default  
  
#The subject login:  
# "Place Login Name here - has permission to Create Endpoints"  
$vGrantee = "LoginName"  
  
#This sample assumes that the grantee already has permission to Create Endpoints.   
  
$sps  =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.ServerPermissionSet  
  
$sps.CreateEndpoint = $true  
$sps.AlterAnyEndpoint = $true  
  
#This sample assumes that the grantee already has permission to Create Endpoints.   
  
#Enumerate and display the server permissions in the set for the grantee specified  
# in the vGrantee string variable.  
$spis = $srv.EnumServerPermissions($vGrantee)  
  
"===Before revoke============="  
foreach ( $spi in $spis)  
{  
    $spi.Grantee + " has " + $spi.PermissionType + " permission."  
}  
""  
#remove perission to create an endpoint  
$sps.CreateEndpoint = $false  
$srv.Revoke($sps, $vGrantee)  
  
#Enumerate and display the server permissions in the set for the grantee specified  
# in the vGrantee string variable.  
$spis = $srv.EnumServerPermissions($vGrantee)  
  
"===After revoke============="  
foreach ( $spi in $spis)  
{  
    $spi.Grantee + " has " + $spi.PermissionType + " permission."  
}  
""  
#Grant the revoked permissions back  
$sps.CreateEndpoint = $true  
$sps.AlterAnyEndpoint = $true  
$srv.Grant($sps, $vGrantee)  
  
#Enumerate and display the server permissions in the set for the grantee specified  
# in the vGrantee string variable.  
$spis = $srv.EnumServerPermissions($vGrantee)  
  
"===After grant============="  
foreach ( $spi in $spis)  
{  
    $spi.Grantee + " has " + $spi.PermissionType + " permission."  
}  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c40a9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c40a9-123">See Also</span></span>  
 [<span data-ttu-id="c40a9-124">Jerarquía de permisos &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c40a9-124">Permissions Hierarchy &#40;Database Engine&#41;</span></span>](../../security/permissions-hierarchy-database-engine.md)  