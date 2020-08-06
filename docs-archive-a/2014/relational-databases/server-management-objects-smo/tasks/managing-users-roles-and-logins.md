---
title: Administración de usuarios, roles e inicios de sesión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- logins [SMO]
- roles [SMO]
- users [SMO]
ms.assetid: 74e411fa-74ed-49ec-ab58-68c250f2280e
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb53e7b4a5748e46c7cb147e1cda50652d8b8805
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675244"
---
# <a name="managing-users-roles-and-logins"></a><span data-ttu-id="99be5-102">Administrar usuarios, roles e inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="99be5-102">Managing Users, Roles, and Logins</span></span>
  <span data-ttu-id="99be5-103">En SMO, el objeto <xref:Microsoft.SqlServer.Management.Smo.Login> representa los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-103">In SMO, logins are represented by the <xref:Microsoft.SqlServer.Management.Smo.Login> object.</span></span> <span data-ttu-id="99be5-104">Si existe un inicio de sesión en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], se puede agregar a un rol del servidor.</span><span class="sxs-lookup"><span data-stu-id="99be5-104">When the logon exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it can be added to a server role.</span></span> <span data-ttu-id="99be5-105">El objeto <xref:Microsoft.SqlServer.Management.Smo.ServerRole> representa el rol del servidor.</span><span class="sxs-lookup"><span data-stu-id="99be5-105">The server role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ServerRole> object.</span></span> <span data-ttu-id="99be5-106">El objeto <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> representa el rol de la base de datos y el objeto <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole> representa el rol de aplicación.</span><span class="sxs-lookup"><span data-stu-id="99be5-106">The database role is represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> object and the application role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole> object.</span></span>  
  
 <span data-ttu-id="99be5-107">Los privilegios asociados al nivel del servidor se enumeran como propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.ServerPermission>.</span><span class="sxs-lookup"><span data-stu-id="99be5-107">Privileges associated with the server level are listed as properties of the <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> object.</span></span> <span data-ttu-id="99be5-108">Los privilegios del nivel del servidor se pueden conceder, denegar o revocar de las cuentas de inicio de sesión individuales.</span><span class="sxs-lookup"><span data-stu-id="99be5-108">The server level privileges can be granted to, denied to, or revoked from individual logon accounts.</span></span>  
  
 <span data-ttu-id="99be5-109">Cada objeto <xref:Microsoft.SqlServer.Management.Smo.Database> tiene un objeto <xref:Microsoft.SqlServer.Management.Smo.UserCollection> que especifica todos los usuarios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="99be5-109">Every <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.UserCollection> object that specifies all users in the database.</span></span> <span data-ttu-id="99be5-110">Cada usuario está asociado a un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-110">Each user is associated with a logon.</span></span> <span data-ttu-id="99be5-111">Se puede asociar un inicio de sesión con usuarios en más de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="99be5-111">One logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99be5-112">El método <xref:Microsoft.SqlServer.Management.Smo.Login> del objeto <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> se puede utilizar para hacer una lista de todos los usuarios en cada base de datos que está asociada al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-112">The <xref:Microsoft.SqlServer.Management.Smo.Login> object's <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method can be used to list all users in every database that is associated with the logon.</span></span> <span data-ttu-id="99be5-113">Alternativamente, la propiedad <xref:Microsoft.SqlServer.Management.Smo.User> del objeto <xref:Microsoft.SqlServer.Management.Smo.Login> especifica el inicio de sesión asociado con el usuario.</span><span class="sxs-lookup"><span data-stu-id="99be5-113">Alternatively, the <xref:Microsoft.SqlServer.Management.Smo.User> object's <xref:Microsoft.SqlServer.Management.Smo.Login> property specifies the logon that is associated with the user.</span></span>  
  
 <span data-ttu-id="99be5-114">Las bases de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] también tienen roles que especifican un conjunto de privilegios en el nivel de base de datos que permiten a un usuario realizar tareas concretas.</span><span class="sxs-lookup"><span data-stu-id="99be5-114">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases also have roles that specify a set of database level privileges that let a user perform specific tasks.</span></span> <span data-ttu-id="99be5-115">A diferencia de los roles del servidor, los roles de la base de datos no son fijos.</span><span class="sxs-lookup"><span data-stu-id="99be5-115">Unlike server roles, database roles are not fixed.</span></span> <span data-ttu-id="99be5-116">Se pueden crear, modificar y quitar.</span><span class="sxs-lookup"><span data-stu-id="99be5-116">They can be created, modified, and removed.</span></span> <span data-ttu-id="99be5-117">Los privilegios y usuarios pueden estar asignados a un rol de la base de datos para la administración masiva.</span><span class="sxs-lookup"><span data-stu-id="99be5-117">Privileges and users can be assigned to a database role for bulk administration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99be5-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99be5-118">Example</span></span>  
 <span data-ttu-id="99be5-119">Para el siguiente ejemplo de código, deberá seleccionar el entorno de programación, la plantilla de programación y el lenguaje de programación en los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="99be5-119">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="99be5-120">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) y [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="99be5-120">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="enumerating-logins-and-associated-users-in-visual-basic"></a><span data-ttu-id="99be5-121">Enumerar inicios de sesión y usuarios asociados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99be5-121">Enumerating Logins and Associated Users in Visual Basic</span></span>  
 <span data-ttu-id="99be5-122">Cada usuario de una base de datos está asociado a un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-122">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="99be5-123">El inicio de sesión puede asociarse a usuarios de más de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="99be5-123">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99be5-124">El ejemplo de código muestra cómo llamar al método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para hacer una lista de todos los usuarios de la base de datos que están asociados al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-124">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="99be5-125">En el ejemplo se crean un inicio de sesión y un usuario en la base de datos [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] para asegurarse de que hay información de asignación que mostrar.</span><span class="sxs-lookup"><span data-stu-id="99be5-125">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLogins1](SMO How to#SMO_VBLogins1)]  -->  
  
## <a name="enumerating-logins-and-associated-users-in-visual-c"></a><span data-ttu-id="99be5-126">Enumerar inicios de sesión y usuarios asociados en Visual C#</span><span class="sxs-lookup"><span data-stu-id="99be5-126">Enumerating Logins and Associated Users in Visual C#</span></span>  
 <span data-ttu-id="99be5-127">Cada usuario de una base de datos está asociado a un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-127">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="99be5-128">El inicio de sesión puede asociarse a usuarios de más de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="99be5-128">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99be5-129">El ejemplo de código muestra cómo llamar al método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para hacer una lista de todos los usuarios de la base de datos que están asociados al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-129">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="99be5-130">En el ejemplo se crean un inicio de sesión y un usuario en la base de datos [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] para asegurarse de que hay información de asignación que mostrar.</span><span class="sxs-lookup"><span data-stu-id="99be5-130">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```csharp
{   
Server srv = new Server();   
//Iterate through each database and display.   
  
foreach ( Database db in srv.Databases) {   
   Console.WriteLine("========");   
   Console.WriteLine("Login Mappings for the database: " + db.Name);   
   Console.WriteLine(" ");   
   //Run the EnumLoginMappings method and return details of database user-login mappings to a DataTable object variable.   
   DataTable d;  
   d = db.EnumLoginMappings();   
   //Display the mapping information.   
   foreach (DataRow r in d.Rows) {   
      foreach (DataColumn c in r.Table.Columns) {   
         Console.WriteLine(c.ColumnName + " = " + r[c]);   
      }   
      Console.WriteLine(" ");   
   }   
}   
}  
```  
  
## <a name="enumerating-logins-and-associated-users-in-powershell"></a><span data-ttu-id="99be5-131">Enumerar inicios de sesión y usuarios asociados en PowerShell</span><span class="sxs-lookup"><span data-stu-id="99be5-131">Enumerating Logins and Associated Users in PowerShell</span></span>  
 <span data-ttu-id="99be5-132">Cada usuario de una base de datos está asociado a un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-132">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="99be5-133">El inicio de sesión puede asociarse a usuarios de más de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="99be5-133">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99be5-134">El ejemplo de código muestra cómo llamar al método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para hacer una lista de todos los usuarios de la base de datos que están asociados al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="99be5-134">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="99be5-135">En el ejemplo se crean un inicio de sesión y un usuario en la base de datos [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] para asegurarse de que hay información de asignación que mostrar.</span><span class="sxs-lookup"><span data-stu-id="99be5-135">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\Default\Databases  
  
#Iterate through all databases  
 foreach ($db in Get-ChildItem)  
 {  
 "====="  
 "Login Mappings for the database: "+ $db.Name  
  
 #get the datatable containing the mapping from the smo database object  
 $dt = $db.EnumLoginMappings()  
  
 #display the results  
 foreach($row in $dt.Rows)  
     {  
        foreach($col in $row.Table.Columns)  
      {  
        $col.ColumnName + "=" + $row[$col]  
       }
     }  
 }  
```  
  
## <a name="managing-roles-and-users"></a><span data-ttu-id="99be5-136">Administrar roles y usuarios</span><span class="sxs-lookup"><span data-stu-id="99be5-136">Managing Roles and Users</span></span>  
 <span data-ttu-id="99be5-137">Este ejemplo muestra cómo administrar los roles y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="99be5-137">This sample demonstrates how to how to manage roles and users.</span></span> <span data-ttu-id="99be5-138">En el primer ejemplo se usa C# y en el segundo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="99be5-138">The first sample uses C#, the second Visual Basic.</span></span> <span data-ttu-id="99be5-139">Los siguientes ejemplos de código requieren una referencia a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="99be5-139">These samples need to reference the following assemblies:</span></span>  
  
-   <span data-ttu-id="99be5-140">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="99be5-140">Microsoft.SqlServer.Smo.dll</span></span>  
  
-   <span data-ttu-id="99be5-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="99be5-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
-   <span data-ttu-id="99be5-142">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="99be5-142">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
-   <span data-ttu-id="99be5-143">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="99be5-143">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
```csharp
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // Creating Logins  
      Login login = new Login(svr, "Login1");  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      Login login2 = new Login(svr, "Login2");  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@1");  
  
      // Creating Users in the database for the logins created  
      User user1 = new User(db, "User1");  
      user1.Login = "Login1";  
      user1.Create();  
  
      User user2 = new User(db, "User2");  
      user2.Login = "Login2";  
      user2.Create();  
  
      // Creating database permission Sets  
      DatabasePermissionSet dbPermSet = new DatabasePermissionSet(DatabasePermission.AlterAnySchema);  
      dbPermSet.Add(DatabasePermission.AlterAnyUser);  
  
      DatabasePermissionSet dbPermSet2 = new DatabasePermissionSet(DatabasePermission.CreateType);  
      dbPermSet2.Add(DatabasePermission.CreateSchema);  
      dbPermSet2.Add(DatabasePermission.CreateTable);  
  
      // Creating Database roles  
      DatabaseRole role1 = new DatabaseRole(db, "Role1");  
      role1.Create();  
  
      DatabaseRole role2 = new DatabaseRole(db, "Role2");  
      role2.Create();  
  
      // Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name);  
      db.Grant(dbPermSet2, role2.Name);  
  
      // Adding members (Users / Roles) to Role  
      role1.AddMember("User1");  
  
      role2.AddMember("User2");  
  
      // Role1 becomes a member of Role2  
      role2.AddMember("Role1");  
  
      // Enumerating through explicit permissions granted to Role1  
      // enumerates all database permissions for the Grantee  
      DatabasePermissionInfo[] dbPermsRole1 = db.EnumDatabasePermissions("Role1");     
      foreach (DatabasePermissionInfo dbp in dbPermsRole1) {  
         Console.WriteLine(dbp.Grantee + " has " + dbp.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
   }  
}  
```  
  
 <span data-ttu-id="99be5-144">Esta es la versión de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="99be5-144">This is the Visual Basic version:</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
      Dim db As New Database(svr, "TESTDB")  
      db.Create()  
  
      ' Creating Logins  
      Dim login As New Login(svr, "Login1")  
      login.LoginType = LoginType.SqlLogin  
      login.Create("password@1")  
  
      Dim login2 As New Login(svr, "Login2")  
      login2.LoginType = LoginType.SqlLogin  
      login2.Create("password@1")  
  
      ' Creating Users in the database for the logins created  
      Dim user1 As New User(db, "User1")  
      user1.Login = "Login1"  
      user1.Create()  
  
      Dim user2 As New User(db, "User2")  
      user2.Login = "Login2"  
      user2.Create()  
  
      ' Creating database permission Sets  
      Dim dbPermSet As New DatabasePermissionSet(DatabasePermission.AlterAnySchema)  
      dbPermSet.Add(DatabasePermission.AlterAnyUser)  
  
      Dim dbPermSet2 As New DatabasePermissionSet(DatabasePermission.CreateType)  
      dbPermSet2.Add(DatabasePermission.CreateSchema)  
      dbPermSet2.Add(DatabasePermission.CreateTable)  
  
      ' Creating Database roles  
      Dim role1 As New DatabaseRole(db, "Role1")  
      role1.Create()  
  
      Dim role2 As New DatabaseRole(db, "Role2")  
      role2.Create()  
  
      ' Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name)  
      db.Grant(dbPermSet2, role2.Name)  
  
      ' Adding members (Users / Roles) to Role  
      role1.AddMember("User1")  
  
      role2.AddMember("User2")  
  
      ' Role1 becomes a member of Role2  
      role2.AddMember("Role1")  
  
      ' Enumerating through explicit permissions granted to Role1  
      ' enumerates all database permissions for the Grantee  
      Dim dbPermsRole1 As DatabasePermissionInfo() = db.EnumDatabasePermissions("Role1")  
      For Each dbp As DatabasePermissionInfo In dbPermsRole1  
         Console.WriteLine(dbp.Grantee + " has " & dbp.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
   End Sub  
End Class  
```  
