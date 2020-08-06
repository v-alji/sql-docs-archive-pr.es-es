---
title: Usar particiones de tablas e índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- partitions [SMO]
- storing data [SMO]
- partitioned tables [SQL Server], SMO
- partitioned indexes [SQL Server], SMO
ms.assetid: 0e682d7e-86c3-4d73-950d-aa692d46cb62
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e05087f63da163b8fa339befae039eb5e7e8245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670326"
---
# <a name="using-table-and-index-partitioning"></a><span data-ttu-id="e33a6-102">Utilizar particiones de tabla e índice</span><span class="sxs-lookup"><span data-stu-id="e33a6-102">Using Table and Index Partitioning</span></span>
  <span data-ttu-id="e33a6-103">Los datos se pueden almacenar usando los algoritmos de almacenamiento proporcionados por [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e33a6-103">Data can be stored by using the storage algorithms provided by [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md).</span></span> <span data-ttu-id="e33a6-104">Las particiones pueden hacer que las tablas y los índices grandes sean más escalables y fáciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="e33a6-104">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
## <a name="index-and-table-partitioning"></a><span data-ttu-id="e33a6-105">Particiones de tabla e índice</span><span class="sxs-lookup"><span data-stu-id="e33a6-105">Index and Table Partitioning</span></span>  
 <span data-ttu-id="e33a6-106">Esta característica permite expandir el índice y los datos de la tabla en varios grupos de archivos en distintas particiones.</span><span class="sxs-lookup"><span data-stu-id="e33a6-106">The feature enables index and table data to be spread across multiple file groups in partitions.</span></span> <span data-ttu-id="e33a6-107">Una función de partición define la forma de asignar las filas de una tabla o un índice a un conjunto de particiones a partir de los valores de determinadas columnas, denominadas columnas de partición.</span><span class="sxs-lookup"><span data-stu-id="e33a6-107">A partition function defines how the rows of a table or index are mapped to a set of partitions based on the values of certain columns, referred to as partitioning columns.</span></span> <span data-ttu-id="e33a6-108">Un esquema de particiones asigna cada partición especificada con la función de partición a un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="e33a6-108">A partition scheme maps each partition specified by the partition function to a file group.</span></span> <span data-ttu-id="e33a6-109">Esto le permite desarrollar estrategias de archivado que permiten escalar las tablas en los grupos de archivos y por consiguiente en los dispositivos físicos.</span><span class="sxs-lookup"><span data-stu-id="e33a6-109">This lets you develop archiving strategies that enable tables to be scaled across file groups, and therefore physical devices.</span></span>  
  
 <span data-ttu-id="e33a6-110">El objeto <xref:Microsoft.SqlServer.Management.Smo.Database> contiene una colección de los objetos <xref:Microsoft.SqlServer.Management.Smo.PartitionFunction> que representan las funciones de partición implementadas y una colección de los objetos <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> que describen cómo están asignados los datos a los grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="e33a6-110">The <xref:Microsoft.SqlServer.Management.Smo.Database> object contains a collection of <xref:Microsoft.SqlServer.Management.Smo.PartitionFunction> objects that represent the implemented partition functions and a collection of <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> objects that describe how data is mapped to file groups.</span></span>  
  
 <span data-ttu-id="e33a6-111">Cada objeto <xref:Microsoft.SqlServer.Management.Smo.Table> y <xref:Microsoft.SqlServer.Management.Smo.Index> especifica qué esquema de partición utiliza en la propiedad <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> y especifica las columnas en <xref:Microsoft.SqlServer.Management.Smo.PartitionSchemeParameterCollection>.</span><span class="sxs-lookup"><span data-stu-id="e33a6-111">Each <xref:Microsoft.SqlServer.Management.Smo.Table> and <xref:Microsoft.SqlServer.Management.Smo.Index> object specifies which partition scheme it uses in the <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> property and specifies the columns in the <xref:Microsoft.SqlServer.Management.Smo.PartitionSchemeParameterCollection>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e33a6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e33a6-112">Example</span></span>  
 <span data-ttu-id="e33a6-113">Para el siguiente ejemplo de código, deberá seleccionar el entorno de programación, la plantilla de programación y el lenguaje de programación en los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="e33a6-113">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="e33a6-114">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) y [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="e33a6-114">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-visual-basic"></a><span data-ttu-id="e33a6-115">Configurar un esquema de partición para una tabla en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e33a6-115">Setting Up a Partition Scheme for a Table in Visual Basic</span></span>  
 <span data-ttu-id="e33a6-116">En el ejemplo de código se muestra cómo crear una función de partición y un esquema de partición para la tabla `TransactionHistory` de la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e33a6-116">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="e33a6-117">Las particiones se dividen por fecha con la intención de separar los registros anteriores de la tabla `TransactionHistoryArchive` .</span><span class="sxs-lookup"><span data-stu-id="e33a6-117">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBPartition1](SMO How to#SMO_VBPartition1)]  -->  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-visual-c"></a><span data-ttu-id="e33a6-118">Configurar un esquema de partición para una tabla en Visual C#</span><span class="sxs-lookup"><span data-stu-id="e33a6-118">Setting Up a Partition Scheme for a Table in Visual C#</span></span>  
 <span data-ttu-id="e33a6-119">En el ejemplo de código se muestra cómo crear una función de partición y un esquema de partición para la tabla `TransactionHistory` de la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e33a6-119">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="e33a6-120">Las particiones se dividen por fecha con la intención de separar los registros anteriores de la tabla `TransactionHistoryArchive` .</span><span class="sxs-lookup"><span data-stu-id="e33a6-120">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
```csharp
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Define and create three new file groups on the database.   
FileGroup fg2;   
fg2 = new FileGroup(db, "Second");   
fg2.Create();   
FileGroup fg3;   
fg3 = new FileGroup(db, "Third");   
fg3.Create();   
FileGroup fg4;   
fg4 = new FileGroup(db, "Fourth");   
fg4.Create();   
//Define a partition function by supplying the parent database and name arguments in the constructor.   
PartitionFunction pf;   
pf = new PartitionFunction(db, "TransHistPF");   
//Add a partition function parameter that specifies the function uses a DateTime range type.   
PartitionFunctionParameter pfp;   
pfp = new PartitionFunctionParameter(pf, DataType.DateTime);   
pf.PartitionFunctionParameters.Add(pfp);   
//Specify the three dates that divide the data into four partitions.   
object[] val;   
val = new object[] {"1/1/2003", "1/1/2004", "1/1/2005"};   
pf.RangeValues = val;   
//Create the partition function.   
pf.Create();   
//Define a partition scheme by supplying the parent database and name arguments in the constructor.   
PartitionScheme ps;   
ps = new PartitionScheme(db, "TransHistPS");   
//Specify the partition function and the filegroups required by the partition scheme.   
ps.PartitionFunction = "TransHistPF";   
ps.FileGroups.Add("PRIMARY");   
ps.FileGroups.Add("second");   
ps.FileGroups.Add("Third");   
ps.FileGroups.Add("Fourth");   
//Create the partition scheme.   
ps.Create();   
}   
```  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-powershell"></a><span data-ttu-id="e33a6-121">Configurar un esquema de partición para una tabla en PowerShell</span><span class="sxs-lookup"><span data-stu-id="e33a6-121">Setting Up a Partition Scheme for a Table in PowerShell</span></span>  
 <span data-ttu-id="e33a6-122">En el ejemplo de código se muestra cómo crear una función de partición y un esquema de partición para la tabla `TransactionHistory` de la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e33a6-122">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="e33a6-123">Las particiones se dividen por fecha con la intención de separar los registros anteriores de la tabla `TransactionHistoryArchive` .</span><span class="sxs-lookup"><span data-stu-id="e33a6-123">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
```powershell  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
$db = $srv.Databases["AdventureWorks"]  
#Create four filegroups  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "First"  
$fg2 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Second"  
$fg3 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Third"  
$fg4 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Fourth"  
  
#Define a partition function by supplying the parent database and name arguments in the constructor.  
$pf =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionFunction -argumentlist $db, "TransHistPF"  
$T = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$T  
$T.GetType()  
#Add a partition function parameter that specifies the function uses a DateTime range type.  
$pfp =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionFunctionParameter -argumentlist $pf, $T  
  
#Specify the three dates that divide the data into four partitions.
#Create an array of type object to hold the partition data  
$val = "1/1/2003"."1/1/2004","1/1/2005"  
$pf.RangeValues = $val  
$pf  
#Create the partition function  
$pf.Create()  
  
#Create partition scheme  
$ps = New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionScheme -argumentlist $db, "TransHistPS"  
$ps.PartitionFunction = "TransHistPF"  
  
#add the filegroups to the scheme
$ps.FileGroups.Add("PRIMARY")  
$ps.FileGroups.Add("Second")  
$ps.FileGroups.Add("Third")  
$ps.FileGroups.Add("Fourth")  
  
#Create it at the server  
$ps.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e33a6-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e33a6-124">See Also</span></span>  
 [<span data-ttu-id="e33a6-125">Tablas e índices con particiones</span><span class="sxs-lookup"><span data-stu-id="e33a6-125">Partitioned Tables and Indexes</span></span>](../../partitions/partitioned-tables-and-indexes.md)  
