---
title: Crear, modificar y eliminar bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- databases [SMO]
- databases [SMO], creating
- databases [SMO], modifying
- databases [SMO], deleting
ms.assetid: fcfb3ec2-7556-4f72-971a-501295892cb0
author: stevestein
ms.author: sstein
ms.openlocfilehash: e8bd34e939fcbc1ecfc5238f5fc4524d187d3f30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749213"
---
# <a name="creating-altering-and-removing-databases"></a><span data-ttu-id="bcd9a-102">Crear, modificar y eliminar bases de datos</span><span class="sxs-lookup"><span data-stu-id="bcd9a-102">Creating, Altering, and Removing Databases</span></span>
  <span data-ttu-id="bcd9a-103">El objeto <xref:Microsoft.SqlServer.Management.Smo.Database> representa una base de datos en SMO.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-103">In SMO, a database is represented by the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
 <span data-ttu-id="bcd9a-104">Para crear un objeto <xref:Microsoft.SqlServer.Management.Smo.Database> no es necesario modificarlo o quitarlo.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-104">It is not necessary to create a <xref:Microsoft.SqlServer.Management.Smo.Database> object to modify or remove it.</span></span> <span data-ttu-id="bcd9a-105">Se puede hacer referencia a la base de datos utilizando una recopilación.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-105">The database can be referenced by using a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcd9a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bcd9a-106">Example</span></span>  
 <span data-ttu-id="bcd9a-107">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="bcd9a-108">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="bcd9a-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-database-in-visual-basic"></a><span data-ttu-id="bcd9a-109">Crear, modificar y quitar una base de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bcd9a-109">Creating, Altering, and Removing a Database in Visual Basic</span></span>  
 <span data-ttu-id="bcd9a-110">En este ejemplo de código se crea una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-110">This code example creates a new database.</span></span> <span data-ttu-id="bcd9a-111">Automáticamente, se crean archivos y grupos de archivos para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-111">Files and file groups are automatically created for the database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDatabase1](SMO How to#SMO_VBDatabase1)]  -->  
  
## <a name="creating-altering-and-removing-a-database-in-visual-c"></a><span data-ttu-id="bcd9a-112">Crear, modificar y quitar una base de datos en Visual C#</span><span class="sxs-lookup"><span data-stu-id="bcd9a-112">Creating, Altering, and Removing a Database in Visual C#</span></span>  
 <span data-ttu-id="bcd9a-113">En este ejemplo de código se crea una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-113">This code example creates a new database.</span></span> <span data-ttu-id="bcd9a-114">Automáticamente, se crean archivos y grupos de archivos para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-114">Files and file groups are automatically created for the database.</span></span>  
  
```csharp
{  
                //Connect to the local, default instance of SQL Server.   
                Server srv;  
                srv = new Server();  
                //Define a Database object variable by supplying the server and the database name arguments in the constructor.   
                Database db;  
                db = new Database(srv, "Test_SMO_Database");  
                //Create the database on the instance of SQL Server.   
                db.Create();  
                //Reference the database and display the date when it was created.   
                db = srv.Databases["Test_SMO_Database"];  
                Console.WriteLine(db.CreateDate);  
                //Remove the database.   
                db.Drop();  
            }  
```  
  
## <a name="creating-altering-and-removing-a-database-in-powershell"></a><span data-ttu-id="bcd9a-115">Crear, modificar y quitar una base de datos en PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcd9a-115">Creating, Altering, and Removing a Database in PowerShell</span></span>  
 <span data-ttu-id="bcd9a-116">En este ejemplo de código se crea una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-116">This code example creates a new database.</span></span> <span data-ttu-id="bcd9a-117">Automáticamente, se crean archivos y grupos de archivos para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-117">Files and file groups are automatically created for the database.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
cd \sql\localhost\  
$srv = Get-Item default  
  
#Create a new database  
$db = New-Object -TypeName Microsoft.SqlServer.Management.Smo.Database -argumentlist $srv, "Test_SMO_Database"  
$db.Create()  
  
#Reference the database and display the date when it was created.
$db = $srv.Databases["Test_SMO_Database"]  
$db.CreateDate  
  
#Drop the database  
$db.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcd9a-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcd9a-118">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Database>  