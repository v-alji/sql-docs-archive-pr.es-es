---
title: Implementar la búsqueda de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- full-text search [SMO]
ms.assetid: 9ce9ad9c-f671-4760-90b5-e0c8ca051473
author: stevestein
ms.author: sstein
ms.openlocfilehash: f8b797e2a38c9136c34b7058b539fca522e03229
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744037"
---
# <a name="implementing-full-text-search"></a><span data-ttu-id="cc9f9-102">Implementar la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="cc9f9-102">Implementing Full-Text Search</span></span>
  <span data-ttu-id="cc9f9-103">La búsqueda de texto completo está disponible por instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y se representa en SMO mediante el objeto <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-103">Full-text search is available per instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and is represented in SMO by the <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A> object.</span></span> <span data-ttu-id="cc9f9-104">El objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextService> reside bajo el objeto `Server`.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-104">The <xref:Microsoft.SqlServer.Management.Smo.FullTextService> object resides under the `Server` object.</span></span> <span data-ttu-id="cc9f9-105">Se utiliza para administrar las opciones de configuración del servicio de búsqueda en texto completo de [!INCLUDE[msCoName](../../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9f9-105">It is used to manage the configuration options for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Full Text Search service.</span></span> <span data-ttu-id="cc9f9-106">El objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection> pertenece al objeto <xref:Microsoft.SqlServer.Management.Smo.Database> y es una colección de los objetos <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> que representan los catálogos de texto completo definidos para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-106">The <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection> object belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object and it is a collection of <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> objects that represent full-text catalogs defined for the database.</span></span> <span data-ttu-id="cc9f9-107">Solo puede tener un índice de texto completo definido para cada tabla, a diferencia de los índices normales.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-107">You can only have one full-text index defined for each table, unlike normal indexes.</span></span> <span data-ttu-id="cc9f9-108">Un objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> representa esto en el objeto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-108">This is represented by a <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object in the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
 <span data-ttu-id="cc9f9-109">Para crear un servicio de búsqueda en texto completo, debe tener un catálogo de texto completo definido en la base de datos y un índice de búsqueda de texto completo definido en una de las tablas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-109">To create a full-text search service, you must have a full-text catalog defined on the database and a full-text search index defined on one of the tables in the database.</span></span>  
  
 <span data-ttu-id="cc9f9-110">Primero, cree un catálogo de texto completo en la base de datos llamando al constructor <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> y especificando el nombre del catálogo.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-110">First, create a full-text catalog on the database by calling the <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> constructor and specifying the catalog name.</span></span> <span data-ttu-id="cc9f9-111">A continuación, cree el índice de texto completo llamando al constructor y especificando la tabla en la que se creará.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-111">Then, create the full-text index by calling the constructor and specifying the table on which it is to be created.</span></span> <span data-ttu-id="cc9f9-112">A continuación, puede agregar columnas de índices al índice de texto completo, utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> y proporcionando el nombre de la columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-112">You can then add index columns for the full-text index, by using the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object and providing the name of the column within the table.</span></span> <span data-ttu-id="cc9f9-113">A continuación, establezca la propiedad <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A> en el catálogo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-113">Then, set the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A> property to the catalog you have created.</span></span> <span data-ttu-id="cc9f9-114">Por último, llame al método <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A> y cree el índice de texto completo en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9f9-114">Finally, call the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A> method and create the full-text index on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc9f9-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc9f9-115">Example</span></span>  
 <span data-ttu-id="cc9f9-116">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-116">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="cc9f9-117">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="cc9f9-117">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-full-text-search-service-in-visual-basic"></a><span data-ttu-id="cc9f9-118">Crear un servicio de búsqueda en texto completo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc9f9-118">Creating a Full-Text Search Service in Visual Basic</span></span>  
 <span data-ttu-id="cc9f9-119">En este ejemplo del código se crea un catálogo de búsqueda de texto completo para la tabla `ProductCategory` de la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc9f9-119">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="cc9f9-120">Después se crea un índice de búsqueda de texto completo en la columna Name de la tabla `ProductCategory` .</span><span class="sxs-lookup"><span data-stu-id="cc9f9-120">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="cc9f9-121">El índice de búsqueda de texto completo requiere que ya haya un índice único definido en la columna.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-121">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.SqlEnum.dll   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      ' Connect to the local, default instance of SQL Server.  
      Dim srv As Server = Nothing  
      srv = New Server()  
  
      ' Reference the AdventureWorks database.  
      Dim db As Database = Nothing  
      db = srv.Databases("AdventureWorks")  
  
      ' Reference the ProductCategory table.  
      Dim tb As Table = Nothing  
      tb = db.Tables("ProductCategory", "Production")  
  
      ' Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      Dim ftc As FullTextCatalog = Nothing  
      ftc = New FullTextCatalog(db, "Test_Catalog")  
      ftc.IsDefault = True  
  
      ' Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create()  
  
      ' Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      Dim fti As FullTextIndex = Nothing  
      fti = New FullTextIndex(tb)  
  
      ' Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      Dim ftic As FullTextIndexColumn = Nothing  
      ftic = New FullTextIndexColumn(fti, "Name")  
  
      ' Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic)  
      fti.ChangeTracking = ChangeTracking.Automatic  
  
      ' Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
      ' Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog"  
  
      ' Create the Full Text Search index on the instance of SQL Server.  
      fti.Create()  
   End Sub  
End Class  
```  
  
## <a name="creating-a-full-text-search-service-in-visual-c"></a><span data-ttu-id="cc9f9-122">Crear un servicio de búsqueda en texto completo en Visual C#</span><span class="sxs-lookup"><span data-stu-id="cc9f9-122">Creating a Full-Text Search Service in Visual C#</span></span>  
 <span data-ttu-id="cc9f9-123">En este ejemplo del código se crea un catálogo de búsqueda de texto completo para la tabla `ProductCategory` de la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc9f9-123">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="cc9f9-124">Después se crea un índice de búsqueda de texto completo en la columna Name de la tabla `ProductCategory` .</span><span class="sxs-lookup"><span data-stu-id="cc9f9-124">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="cc9f9-125">El índice de búsqueda de texto completo requiere que ya haya un índice único definido en la columna.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-125">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.SqlEnum.dll   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.  
      Server srv = default(Server);  
      srv = new Server();  
  
      // Reference the AdventureWorks database.  
      Database db = default(Database);  
      db = srv.Databases ["AdventureWorks"];  
  
      // Reference the ProductCategory table.  
      Table tb = default(Table);  
      tb = db.Tables["ProductCategory", "Production"];  
  
      // Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      FullTextCatalog ftc = default(FullTextCatalog);  
      ftc = new FullTextCatalog(db, "Test_Catalog");  
      ftc.IsDefault = true;  
  
      // Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create();  
  
      // Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      FullTextIndex fti = default(FullTextIndex);  
      fti = new FullTextIndex(tb);  
  
      // Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      FullTextIndexColumn ftic = default(FullTextIndexColumn);  
      ftic = new FullTextIndexColumn(fti, "Name");  
  
      // Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic);  
      fti.ChangeTracking = ChangeTracking.Automatic;  
  
      // Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name";  
  
      // Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog";  
  
      // Create the Full Text Search index on the instance of SQL Server.  
      fti.Create();  
   }  
}  
```  
  
## <a name="creating-a-full-text-search-service-in-powershell"></a><span data-ttu-id="cc9f9-126">Crear un servicio de búsqueda en texto completo en PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc9f9-126">Creating a Full-Text Search Service in PowerShell</span></span>  
 <span data-ttu-id="cc9f9-127">En este ejemplo del código se crea un catálogo de búsqueda de texto completo para la tabla `ProductCategory` de la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc9f9-127">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="cc9f9-128">Después se crea un índice de búsqueda de texto completo en la columna Name de la tabla `ProductCategory` .</span><span class="sxs-lookup"><span data-stu-id="cc9f9-128">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="cc9f9-129">El índice de búsqueda de texto completo requiere que ya haya un índice único definido en la columna.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-129">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```powershell
# Example of implementing a full text search on the default instance.  
# Set the path context to the local, default instance of SQL Server and database tables  
  
CD \sql\localhost\default\databases  
$db = Get-Item AdventureWorks2012  
  
CD AdventureWorks\tables  
  
#Get a reference to the table  
$tb = Get-Item Production.ProductCategory  
  
# Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
  
$ftc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextCatalog -ArgumentList $db, "Test_Catalog2"  
$ftc.IsDefault = $true  
  
# Create the Full Text Search catalog on the instance of SQL Server.  
$ftc.Create()  
  
# Define a FullTextIndex object variable by supplying the parent table argument in the constructor.  
$fti = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndex -ArgumentList $tb  
  
#  Define a FullTextIndexColumn object variable by supplying the parent index
#  and column name arguments in the constructor.  
  
$ftic = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndexColumn -ArgumentList $fti, "Name"  
  
# Add the indexed column to the index.  
$fti.IndexedColumns.Add($ftic)  
  
# Set change tracking  
$fti.ChangeTracking = [Microsoft.SqlServer.Management.SMO.ChangeTracking]::Automatic  
  
# Specify the unique index on the table that is required by the Full Text Search index.  
$fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
# Specify the catalog associated with the index.  
$fti.CatalogName = "Test_Catalog2"  
  
# Create the Full Text Search Index  
$fti.Create()  
```  
