---
title: Crear, modificar y quitar vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- views [SMO]
ms.assetid: 7d445c0e-77ef-4734-993b-e022de31df23
author: stevestein
ms.author: sstein
ms.openlocfilehash: fd8d75e413b1871ce4b8784f5087cb08ed08da73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676973"
---
# <a name="creating-altering-and-removing-views"></a><span data-ttu-id="625b5-102">Crear, modificar y eliminar vistas</span><span class="sxs-lookup"><span data-stu-id="625b5-102">Creating, Altering, and Removing Views</span></span>
  <span data-ttu-id="625b5-103">En los objetos de administración de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SMO), el objeto <xref:Microsoft.SqlServer.Management.Smo.View> representa las vistas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="625b5-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] views are represented by the <xref:Microsoft.SqlServer.Management.Smo.View> object.</span></span>  
  
 <span data-ttu-id="625b5-104">La propiedad <xref:Microsoft.SqlServer.Management.Smo.View.TextBody%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.View> define la vista.</span><span class="sxs-lookup"><span data-stu-id="625b5-104">The <xref:Microsoft.SqlServer.Management.Smo.View.TextBody%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.View> object defines the view.</span></span> <span data-ttu-id="625b5-105">Es el equivalente de la instrucción SELECT de [!INCLUDE[tsql](../../../includes/tsql-md.md)] para crear una vista.</span><span class="sxs-lookup"><span data-stu-id="625b5-105">It is the equivalent of the [!INCLUDE[tsql](../../../includes/tsql-md.md)] SELECT statement for creating a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="625b5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="625b5-106">Example</span></span>  
 <span data-ttu-id="625b5-107">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="625b5-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="625b5-108">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="625b5-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-view-in-visual-basic"></a><span data-ttu-id="625b5-109">Crear, modificar y quitar una vista en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="625b5-109">Creating, Altering, and Removing a View in Visual Basic</span></span>  
 <span data-ttu-id="625b5-110">En este ejemplo de código se muestra cómo crear una vista de dos tablas utilizando una combinación interna.</span><span class="sxs-lookup"><span data-stu-id="625b5-110">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="625b5-111">La vista se crea utilizando el modo de texto, de modo que debe establecerse la propiedad <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A>.</span><span class="sxs-lookup"><span data-stu-id="625b5-111">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBViews1](SMO How to#SMO_VBViews1)]  -->  
  
## <a name="creating-altering-and-removing-a-view-in-visual-c"></a><span data-ttu-id="625b5-112">Crear, modificar y quitar una vista en Visual C#</span><span class="sxs-lookup"><span data-stu-id="625b5-112">Creating, Altering, and Removing a View in Visual C#</span></span>  
 <span data-ttu-id="625b5-113">En este ejemplo de código se muestra cómo crear una vista de dos tablas utilizando una combinación interna.</span><span class="sxs-lookup"><span data-stu-id="625b5-113">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="625b5-114">La vista se crea utilizando el modo de texto, de modo que debe establecerse la propiedad <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A>.</span><span class="sxs-lookup"><span data-stu-id="625b5-114">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
```csharp
{  
        //Connect to the local, default instance of SQL Server.   
        Server srv;   
        srv = new Server();   
        //Reference the AdventureWorks2012 database.   
        Database db;   
        db = srv.Databases["AdventureWorks2012"];   
        //Define a View object variable by supplying the parent database, view name and schema in the constructor.   
        View myview;   
        myview = new View(db, "Test_View", "Sales");   
        //Set the TextHeader and TextBody property to define the view.   
        myview.TextHeader = "CREATE VIEW [Sales].[Test_View] AS";   
        myview.TextBody = "SELECT h.SalesOrderID, d.OrderQty FROM Sales.SalesOrderHeader AS h INNER JOIN Sales.SalesOrderDetail AS d ON h.SalesOrderID = d.SalesOrderID";   
        //Create the view on the instance of SQL Server.   
        myview.Create();   
        //Remove the view.   
        myview.Drop();   
        }  
```  
  
## <a name="creating-altering-and-removing-a-view-in-powershell"></a><span data-ttu-id="625b5-115">Crear, modificar y quitar una vista en PowerShell</span><span class="sxs-lookup"><span data-stu-id="625b5-115">Creating, Altering, and Removing a View in PowerShell</span></span>  
 <span data-ttu-id="625b5-116">En este ejemplo de código se muestra cómo crear una vista de dos tablas utilizando una combinación interna.</span><span class="sxs-lookup"><span data-stu-id="625b5-116">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="625b5-117">La vista se crea utilizando el modo de texto, de modo que debe establecerse la propiedad <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A>.</span><span class="sxs-lookup"><span data-stu-id="625b5-117">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a View object variable by supplying the parent database, view name and schema in the constructor.
$myview  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.View -argumentlist $db, "Test_View", "Sales"  
  
# Set the TextHeader and TextBody property to define the view.
$myview.TextHeader = "CREATE VIEW [Sales].[Test_View] AS"  
$myview.TextBody ="SELECT h.SalesOrderID, d.OrderQty FROM Sales.SalesOrderHeader AS h INNER JOIN Sales.SalesOrderDetail AS d ON h.SalesOrderID = d.SalesOrderID"  
  
# Create the view on the instance of SQL Server.
$myview.Create()  
  
# Remove the view
$myview.Drop();  
```  
  
## <a name="see-also"></a><span data-ttu-id="625b5-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="625b5-118">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.View>  
