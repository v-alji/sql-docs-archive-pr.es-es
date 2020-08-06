---
title: Scripting | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- dependencies [SMO]
- scripts [SMO]
ms.assetid: 13a35511-3987-426b-a3b7-3b2e83900dc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: bf46798597de021976cefa943a17500e773f9274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746204"
---
# <a name="scripting"></a><span data-ttu-id="0fb22-102">Scripting</span><span class="sxs-lookup"><span data-stu-id="0fb22-102">Scripting</span></span>
  <span data-ttu-id="0fb22-103">El objeto <xref:Microsoft.SqlServer.Management.Smo.Scripter> y sus objetos secundarios o el método `Script` en objetos individuales controlan el scripting en SMO.</span><span class="sxs-lookup"><span data-stu-id="0fb22-103">Scripting in SMO is controlled by the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects, or the `Script` method on individual objects.</span></span> <span data-ttu-id="0fb22-104">El <xref:Microsoft.SqlServer.Management.Smo.Scripter> objeto controla la asignación fuera de las relaciones de dependencia para los objetos en una instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0fb22-104">The <xref:Microsoft.SqlServer.Management.Smo.Scripter> object controls the mapping out of dependency relationships for objects on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0fb22-105">La generación avanzada de script utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.Scripter> y sus objetos secundarios es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="0fb22-105">Advanced scripting by using the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects is a three phase process:</span></span>  
  
1.  <span data-ttu-id="0fb22-106">Detección</span><span class="sxs-lookup"><span data-stu-id="0fb22-106">Discovery</span></span>  
  
2.  <span data-ttu-id="0fb22-107">Generación de lista</span><span class="sxs-lookup"><span data-stu-id="0fb22-107">List generation</span></span>  
  
3.  <span data-ttu-id="0fb22-108">Generación de script</span><span class="sxs-lookup"><span data-stu-id="0fb22-108">Script generation</span></span>  
  
 <span data-ttu-id="0fb22-109">La fase de detección utiliza el objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker>.</span><span class="sxs-lookup"><span data-stu-id="0fb22-109">The discovery phase uses the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object.</span></span> <span data-ttu-id="0fb22-110">Dada una lista de URN de objetos, el método <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> devuelve un objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> para los objetos en la lista URN.</span><span class="sxs-lookup"><span data-stu-id="0fb22-110">Given an URN list of objects, the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object returns a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object for the objects in the URN list.</span></span> <span data-ttu-id="0fb22-111">El parámetro Boolean *fParents* se usa para seleccionar si se deben detectar los elementos primarios o secundarios del objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="0fb22-111">The Boolean *fParents* parameter is used to select whether the parents or the children of the specified object are to be discovered.</span></span> <span data-ttu-id="0fb22-112">El árbol de dependencia se puede modificar en esta fase.</span><span class="sxs-lookup"><span data-stu-id="0fb22-112">The dependency tree can be modified at this stage.</span></span>  
  
 <span data-ttu-id="0fb22-113">En la fase de generación de lista, el árbol se pasa y se devuelve la lista resultante.</span><span class="sxs-lookup"><span data-stu-id="0fb22-113">In the list generation phase, the tree is passed in and the resulting list is returned.</span></span> <span data-ttu-id="0fb22-114">Esta lista de objetos aparece en orden de scripting y se puede manipular.</span><span class="sxs-lookup"><span data-stu-id="0fb22-114">This object list is in scripting order and can be manipulated.</span></span>  
  
 <span data-ttu-id="0fb22-115">La fase de generación de la lista utiliza el método <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> para devolver <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span><span class="sxs-lookup"><span data-stu-id="0fb22-115">The list generation phases use the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> method to return a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span></span> <span data-ttu-id="0fb22-116"><xref:Microsoft.SqlServer.Management.Smo.DependencyTree> se puede modificar en esta fase.</span><span class="sxs-lookup"><span data-stu-id="0fb22-116">The <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> can be modified at this stage.</span></span>  
  
 <span data-ttu-id="0fb22-117">En la tercera y última fase, se genera un script con la lista especificada y las opciones de scripting.</span><span class="sxs-lookup"><span data-stu-id="0fb22-117">In the third and final phase, a script is generated with the specified list and scripting options.</span></span> <span data-ttu-id="0fb22-118">El resultado se devuelve como un objeto de sistema <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="0fb22-118">The result is returned as a <xref:System.Collections.Specialized.StringCollection> system object.</span></span> <span data-ttu-id="0fb22-119">En esta fase los nombres de objeto dependientes se extraen a continuación de la colección Elementos del objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> y de propiedades como <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> y <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="0fb22-119">In this phase the dependent object names are then extracted from the Items collection of the <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object and properties such as <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> and <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fb22-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fb22-120">Example</span></span>  
 <span data-ttu-id="0fb22-121">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="0fb22-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="0fb22-122">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="0fb22-122">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="0fb22-123">Este ejemplo de código requiere una instrucción `Imports` para el espacio de nombres System.Collections.Specialized.</span><span class="sxs-lookup"><span data-stu-id="0fb22-123">This code example requires an `Imports` statement for the System.Collections.Specialized namespace.</span></span> <span data-ttu-id="0fb22-124">Inserte esto con las otras instrucciones Imports, antes de cualquier declaración en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0fb22-124">Insert this with the other Imports statements, before any declarations in the application.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-basic"></a><span data-ttu-id="0fb22-125">Generar script de las dependencias de una base de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fb22-125">Scripting Out the Dependencies for a Database in Visual Basic</span></span>  
 <span data-ttu-id="0fb22-126">En este ejemplo de código se muestra cómo detectar las dependencias y cómo recorrer en iteración la lista para mostrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="0fb22-126">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
  
Public Class A  
   Public Shared Sub Main()  
      ' database name  
      Dim dbName As [String] = "AdventureWorksLT2012"   ' database name  
  
      ' Connect to the local, default instance of SQL Server.   
      Dim srv As New Server()  
  
      ' Reference the database.    
      Dim db As Database = srv.Databases(dbName)  
  
      ' Define a Scripter object and set the required scripting options.   
      Dim scrp As New Scripter(srv)  
      scrp.Options.ScriptDrops = False  
      scrp.Options.WithDependencies = True  
      scrp.Options.Indexes = True   ' To include indexes  
      scrp.Options.DriAllConstraints = True   ' to include referential constraints in the script  
  
      ' Iterate through the tables in database and script each one. Display the script.  
      For Each tb As Table In db.Tables  
         ' check if the table is not a system table  
         If tb.IsSystemObject = False Then  
            Console.WriteLine("-- Scripting for table " + tb.Name)  
  
            ' Generating script for table tb  
            Dim sc As System.Collections.Specialized.StringCollection = scrp.Script(New Urn() {tb.Urn})  
            For Each st As String In sc  
               Console.WriteLine(st)  
            Next  
            Console.WriteLine("--")  
         End If  
      Next  
   End Sub  
End Class  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-c"></a><span data-ttu-id="0fb22-127">Generar script de las dependencias de una base de datos en Visual C#</span><span class="sxs-lookup"><span data-stu-id="0fb22-127">Scripting Out the Dependencies for a Database in Visual C#</span></span>  
 <span data-ttu-id="0fb22-128">En este ejemplo de código se muestra cómo detectar las dependencias y cómo recorrer en iteración la lista para mostrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="0fb22-128">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
  
public class A {  
   public static void Main() {   
      String dbName = "AdventureWorksLT2012"; // database name  
  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the database.    
      Database db = srv.Databases[dbName];  
  
      // Define a Scripter object and set the required scripting options.   
      Scripter scrp = new Scripter(srv);  
      scrp.Options.ScriptDrops = false;  
      scrp.Options.WithDependencies = true;  
      scrp.Options.Indexes = true;   // To include indexes  
      scrp.Options.DriAllConstraints = true;   // to include referential constraints in the script  
  
      // Iterate through the tables in database and script each one. Display the script.     
      foreach (Table tb in db.Tables) {   
         // check if the table is not a system table  
         if (tb.IsSystemObject == false) {  
            Console.WriteLine("-- Scripting for table " + tb.Name);  
  
            // Generating script for table tb  
            System.Collections.Specialized.StringCollection sc = scrp.Script(new Urn[]{tb.Urn});  
            foreach (string st in sc) {  
               Console.WriteLine(st);  
            }  
            Console.WriteLine("--");  
         }  
      }   
   }  
}  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-powershell"></a><span data-ttu-id="0fb22-129">Scripting de las dependencias de una base de datos en PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fb22-129">Scripting Out the Dependencies for a Database in PowerShell</span></span>  
 <span data-ttu-id="0fb22-130">En este ejemplo de código se muestra cómo detectar las dependencias y cómo recorrer en iteración la lista para mostrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="0fb22-130">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
# Create a Scripter object and set the required scripting options.  
$scrp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Scripter -ArgumentList (Get-Item .)  
$scrp.Options.ScriptDrops = $false  
$scrp.Options.WithDependencies = $true  
$scrp.Options.IncludeIfNotExists = $true  
  
# Set the path context to the tables in AdventureWorks2012.  
CD Databases\AdventureWorks2012\Tables  
  
foreach ($Item in Get-ChildItem)  
 {    
 $scrp.Script($Item)  
 }  
```  
