---
title: Trabajar con rutas acceso de SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f31d8e2c-8d59-4fee-ac2a-324668e54262
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d2647251eb1c8843d4ab7a95d2c439e47f5bb6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745844"
---
# <a name="work-with-sql-server-powershell-paths"></a><span data-ttu-id="fcc91-102">Trabajar con rutas acceso de SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcc91-102">Work With SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="fcc91-103">Después de haber navegado a un nodo de una ruta de acceso del proveedor de [!INCLUDE[ssDE](../includes/ssde-md.md)] , puede realizar el trabajo o recuperar información mediante los métodos y propiedades de los objetos de administración de [!INCLUDE[ssDE](../includes/ssde-md.md)] asociados al nodo.</span><span class="sxs-lookup"><span data-stu-id="fcc91-103">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform work or retrieve information by using the methods and properties from the [!INCLUDE[ssDE](../includes/ssde-md.md)] management object associated with the node.</span></span>  
  
1.  [<span data-ttu-id="fcc91-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fcc91-104">Before You Begin</span></span>](#BeforeYouBegin)  
  
2.  <span data-ttu-id="fcc91-105">**Para trabajar en un nodo de ruta de acceso:**  [Enumerar métodos y propiedades](#ListPropMeth), [Usar métodos y propiedades](#UsePropMeth)</span><span class="sxs-lookup"><span data-stu-id="fcc91-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fcc91-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fcc91-106">Before You Begin</span></span>  
 <span data-ttu-id="fcc91-107">Después de haber navegado a un nodo de una ruta de acceso del proveedor de [!INCLUDE[ssDE](../includes/ssde-md.md)] , puede realizar dos tipos de acciones:</span><span class="sxs-lookup"><span data-stu-id="fcc91-107">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform two types of actions:</span></span>  
  
-   <span data-ttu-id="fcc91-108">Puede ejecutar los cmdlets de Windows PowerShell que operan en los nodos, como **Rename-Item**.</span><span class="sxs-lookup"><span data-stu-id="fcc91-108">You can run Windows PowerShell cmdlets that operate on nodes, such as **Rename-Item**.</span></span>  
  
-   <span data-ttu-id="fcc91-109">Puede llamar a los métodos desde el modelo de objetos de administración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] asociado, como SMO.</span><span class="sxs-lookup"><span data-stu-id="fcc91-109">You can call the methods from the associated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] management object model, such as SMO.</span></span> <span data-ttu-id="fcc91-110">Por ejemplo, si navega al nodo Bases de datos de una ruta de acceso, puede usar los métodos y las propiedades de la clase <xref:Microsoft.SqlServer.Management.Smo.Database> .</span><span class="sxs-lookup"><span data-stu-id="fcc91-110">For example, if you navigate to the Databases node in a path, you can use the methods and properties of the <xref:Microsoft.SqlServer.Management.Smo.Database> class.</span></span>  
  
 <span data-ttu-id="fcc91-111">El proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se utiliza para administrar los objetos en una instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcc91-111">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider is used to manage the objects in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="fcc91-112">No se utiliza para trabajar con los datos de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="fcc91-112">It is not used to work with the data in databases.</span></span> <span data-ttu-id="fcc91-113">Si ha navegado a una tabla o vista, no puede utilizar el proveedor para seleccionar, insertar, actualizar o eliminar datos.</span><span class="sxs-lookup"><span data-stu-id="fcc91-113">If you have navigated to a table or view, you cannot use the provider to select, insert, update, or delete data.</span></span> <span data-ttu-id="fcc91-114">Use el cmdlet **Invoke-Sqlcmd** para consultar o cambiar los datos de las tablas y vistas del entorno de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcc91-114">Use the **Invoke-Sqlcmd** cmdlet to query or change data in tables and views from the Windows PowerShell environment.</span></span> <span data-ttu-id="fcc91-115">Para obtener más información, vea [cmdlet Invoke-Sqlcmd](../database-engine/invoke-sqlcmd-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="fcc91-115">For more information, see [Invoke-Sqlcmd cmdlet](../database-engine/invoke-sqlcmd-cmdlet.md).</span></span>  
  
##  <a name="listing-methods-and-properties"></a><a name="ListPropMeth"></a> <span data-ttu-id="fcc91-116">Enumerar métodos y propiedades</span><span class="sxs-lookup"><span data-stu-id="fcc91-116">Listing Methods and Properties</span></span>
  
 <span data-ttu-id="fcc91-117">Para ver los métodos y propiedades disponibles de determinados objetos o clases de objetos, use el cmdlet **Get-Member** .</span><span class="sxs-lookup"><span data-stu-id="fcc91-117">To view the methods and properties available for specific objects or object classes, use the **Get-Member** cmdlet.</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="fcc91-118">Ejemplos: Enumerar métodos y propiedades</span><span class="sxs-lookup"><span data-stu-id="fcc91-118">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="fcc91-119">En este ejemplo se establece una variable de Windows PowerShell en la clase <xref:Microsoft.SqlServer.Management.Smo.Database> de SMO y se enumeran los métodos y las propiedades:</span><span class="sxs-lookup"><span data-stu-id="fcc91-119">This example sets a Windows PowerShell variable to the SMO <xref:Microsoft.SqlServer.Management.Smo.Database> class and lists the methods and properties:</span></span>  
  
```powershell
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar | Get-Member -Type Methods  
$MyDBVar | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="fcc91-120">También puede usar **Get-Member** para mostrar los métodos y propiedades asociados con el nodo final de una ruta de acceso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcc91-120">You can also use **Get-Member** to list the methods and properties that are associated with the end node of a Windows PowerShell path.</span></span>  
  
 <span data-ttu-id="fcc91-121">En este ejemplo se navega al nodo Databases de una ruta de acceso de SQLSERVER: y se muestran las propiedades de la colección:</span><span class="sxs-lookup"><span data-stu-id="fcc91-121">This example navigates to the Databases node in a SQLSERVER: path and lists the collection properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-Item . | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="fcc91-122">En este ejemplo se navega al nodo AdventureWorks2012 de una ruta de acceso de SQLSERVER: y se muestran las propiedades del objeto:</span><span class="sxs-lookup"><span data-stu-id="fcc91-122">This example navigates to the AdventureWorks2012 node in a SQLSERVER: path and lists the object properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
Get-Item . | Get-Member -Type Properties  
```  
  
##  <a name="using-smo-methods-and-properties"></a><a name="UsePropMeth"></a><span data-ttu-id="fcc91-123">Usar métodos y propiedades de SMO</span><span class="sxs-lookup"><span data-stu-id="fcc91-123">Using SMO Methods and Properties</span></span>  
  
 <span data-ttu-id="fcc91-124">Para realizar el trabajo en objetos de una ruta de acceso del proveedor de [!INCLUDE[ssDE](../includes/ssde-md.md)] , puede usar los métodos y las propiedades de SMO.</span><span class="sxs-lookup"><span data-stu-id="fcc91-124">To perform work on objects from a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can use SMO methods and properties.</span></span>  
  
### <a name="examples-using-methods-and-properties"></a><span data-ttu-id="fcc91-125">Ejemplos: Usar métodos y propiedades</span><span class="sxs-lookup"><span data-stu-id="fcc91-125">Examples: Using Methods and Properties</span></span>  
 <span data-ttu-id="fcc91-126">En este ejemplo se usa la propiedad **Schema** de SMO para obtener una lista de las tablas del esquema Sales en AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="fcc91-126">This example uses the SMO **Schema** property to get a list of the tables from the Sales schema in AdventureWorks2012:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Tables  
Get-ChildItem | Where {$_.Schema -eq "Sales"}  
```  
  
 <span data-ttu-id="fcc91-127">En este ejemplo se usa el método de **script** de SMO para generar un script que contiene las `CREATE VIEW` instrucciones que debe tener para volver a crear las vistas en AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="fcc91-127">This example uses the SMO **Script** method to generate a script that contains the `CREATE VIEW` statements you must have to re-create the views in AdventureWorks2012:</span></span>  
  
```powershell
Remove-Item C:\PowerShell\CreateViews.sql  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Views  
foreach ($Item in Get-ChildItem) { $Item.Script() | Out-File -Filepath C:\PowerShell\CreateViews.sql -append }  
```  
  
 <span data-ttu-id="fcc91-128">En este ejemplo se utiliza el método **Create** de SMO para crear una base de datos y, a continuación, se usa la propiedad **State** para mostrar si la base de datos existe:</span><span class="sxs-lookup"><span data-stu-id="fcc91-128">This example uses the SMO **Create** method to create a database, and then uses the **State** property to show whether the database exists:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar.Parent = (Get-Item ..)  
$MyDBVar.Name = "NewDB"  
$MyDBVar.Create()  
$MyDBVar.State  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcc91-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcc91-129">See Also</span></span>  
 <span data-ttu-id="fcc91-130">[Proveedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="fcc91-130">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="fcc91-131">[Navegar SQL Server PowerShell trazados](navigate-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="fcc91-131">[Navigate SQL Server PowerShell Paths](navigate-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="fcc91-132">[Convertir urn en rutas de acceso del proveedor de SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="fcc91-132">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="fcc91-133">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcc91-133">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
