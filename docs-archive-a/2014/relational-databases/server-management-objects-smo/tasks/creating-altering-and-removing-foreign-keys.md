---
title: Crear, modificar y quitar claves externas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- foreign keys [SMO]
ms.assetid: d43c8dca-bb6b-4a41-8a79-c96fd546fc91
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3087dd9f521ce9fe7b57ec359dc8042afbfbb9a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749204"
---
# <a name="creating-altering-and-removing-foreign-keys"></a><span data-ttu-id="fe208-102">Crear, modificar y eliminar las claves externas</span><span class="sxs-lookup"><span data-stu-id="fe208-102">Creating, Altering, and Removing Foreign Keys</span></span>
  <span data-ttu-id="fe208-103">En los objetos de administración de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SMO), el objeto <xref:Microsoft.SqlServer.Management.Smo.ForeignKey> representa las claves externas.</span><span class="sxs-lookup"><span data-stu-id="fe208-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), foreign keys are represented by the <xref:Microsoft.SqlServer.Management.Smo.ForeignKey> object.</span></span>  
  
 <span data-ttu-id="fe208-104">Para crear una clave externa en SMO, debe especificar la tabla en la que la clave externa se define en el constructor del objeto <xref:Microsoft.SqlServer.Management.Smo.ForeignKey>.</span><span class="sxs-lookup"><span data-stu-id="fe208-104">To create a foreign key in SMO, you must specify the table on which the foreign key is defined in the constructor of the <xref:Microsoft.SqlServer.Management.Smo.ForeignKey> object.</span></span> <span data-ttu-id="fe208-105">En la tabla, debe seleccionar al menos una columna para ser la clave externa.</span><span class="sxs-lookup"><span data-stu-id="fe208-105">From the table, you must select at least one column to be the foreign key.</span></span> <span data-ttu-id="fe208-106">Para ello, cree una variable de objeto <xref:Microsoft.SqlServer.Management.Smo.ForeignKeyColumn> y especifique el nombre de la columna que es la clave externa.</span><span class="sxs-lookup"><span data-stu-id="fe208-106">To do this, create a <xref:Microsoft.SqlServer.Management.Smo.ForeignKeyColumn> object variable and specify the name of the column that is the foreign key.</span></span> <span data-ttu-id="fe208-107">A continuación, especifique la tabla y la columna a las que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="fe208-107">Then, specify the referenced table and referenced column.</span></span> <span data-ttu-id="fe208-108">Utilice el método <xref:Microsoft.SqlServer.Management.Smo.ForeignKeyColumnCollection.Add%2A> para agregar la columna a la propiedad de objeto `Columns`.</span><span class="sxs-lookup"><span data-stu-id="fe208-108">Use the <xref:Microsoft.SqlServer.Management.Smo.ForeignKeyColumnCollection.Add%2A> method to add the column to the `Columns` object property.</span></span>  
  
 <span data-ttu-id="fe208-109">Las columnas que representan la clave externa se muestran en la propiedad de objeto `Columns` del objeto <xref:Microsoft.SqlServer.Management.Smo.ForeignKey>.</span><span class="sxs-lookup"><span data-stu-id="fe208-109">The columns that represent the foreign key are listed in the `Columns` object property of the <xref:Microsoft.SqlServer.Management.Smo.ForeignKey> object.</span></span> <span data-ttu-id="fe208-110">La propiedad <xref:Microsoft.SqlServer.Management.Smo.ForeignKey.ReferencedKey%2A> que se encuentra en la tabla especificada en la propiedad <xref:Microsoft.SqlServer.Management.Smo.ForeignKey.ReferencedTable%2A> representa la clave principal a la que hace referencia la clave externa.</span><span class="sxs-lookup"><span data-stu-id="fe208-110">The primary key that is referenced by the foreign key is represented by the <xref:Microsoft.SqlServer.Management.Smo.ForeignKey.ReferencedKey%2A> property that is in the table specified in the <xref:Microsoft.SqlServer.Management.Smo.ForeignKey.ReferencedTable%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe208-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe208-111">Example</span></span>  
 <span data-ttu-id="fe208-112">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe208-112">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="fe208-113">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="fe208-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-foreign-key-in-visual-basic"></a><span data-ttu-id="fe208-114">Crear, modificar y quitar una clave externa en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe208-114">Creating, Altering, and Removing a Foreign Key in Visual Basic</span></span>  
 <span data-ttu-id="fe208-115">En este ejemplo de código se muestra cómo crear una relación de clave externa entre una o varias columnas de una tabla y una columna de clave principal de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="fe208-115">This code example shows how to create a foreign key relationship between one or more columns in one table to a primary key column in another table.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBForeignKeys1](SMO How to#SMO_VBForeignKeys1)]  -->  
  
## <a name="creating-altering-and-removing-a-foreign-key-in-visual-c"></a><span data-ttu-id="fe208-116">Crear, modificar y quitar una clave externa en Visual C#</span><span class="sxs-lookup"><span data-stu-id="fe208-116">Creating, Altering, and Removing a Foreign Key in Visual C#</span></span>  
 <span data-ttu-id="fe208-117">En este ejemplo de código se muestra cómo crear una relación de clave externa entre una o varias columnas de una tabla y una columna de clave principal de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="fe208-117">This code example shows how to create a foreign key relationship between one or more columns in one table to a primary key column in another table.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
            //Declare another Table object variable and reference the EmployeeDepartmentHistory table.   
            Table tbea;  
            tbea = db.Tables["EmployeeDepartmentHistory", "HumanResources"];  
            //Define a Foreign Key object variable by supplying the EmployeeDepartmentHistory as the parent table and the foreign key name in the constructor.   
            ForeignKey fk;  
            fk = new ForeignKey(tbea, "test_foreignkey");  
            //Add BusinessEntityID as the foreign key column.   
            ForeignKeyColumn fkc;  
            fkc = new ForeignKeyColumn(fk, "BusinessEntityID", "BusinessEntityID");  
            fk.Columns.Add(fkc);  
            //Set the referenced table and schema.   
            fk.ReferencedTable = "Employee";  
            fk.ReferencedTableSchema = "HumanResources";  
            //Create the foreign key on the instance of SQL Server.   
            fk.Create();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-foreign-key-in-powershell"></a><span data-ttu-id="fe208-118">Crear, modificar y quitar una clave externa en PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe208-118">Creating, Altering, and Removing a Foreign Key in PowerShell</span></span>  
 <span data-ttu-id="fe208-119">En este ejemplo de código se muestra cómo crear una relación de clave externa entre una o varias columnas de una tabla y una columna de clave principal de otra tabla.</span><span class="sxs-lookup"><span data-stu-id="fe208-119">This code example shows how to create a foreign key relationship between one or more columns in one table to a primary key column in another table.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and to the  
#database tables in Adventureworks2012  
CD \sql\localhost\default\databases\AdventureWorks2012\Tables\  
  
#Get reference to the FK table  
$tbea = get-item HumanResources.EmployeeDepartmentHistory  
  
# Define a Foreign Key object variable by supplying the EmployeeDepartmentHistory  
# as the parent table and the foreign key name in the constructor.   
$fk = New-Object -TypeName Microsoft.SqlServer.Management.SMO.ForeignKey `  
-argumentlist $tbea, "test_foreignkey"  
  
#Add BusinessEntityID as the foreign key column.   
$fkc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.ForeignKeyColumn `  
-argumentlist $fk, "BusinessEntityID", "BusinessEntityID"  
$fk.Columns.Add($fkc)  
  
#Set the referenced table and schema.   
$fk.ReferencedTable = "Employee"  
$fk.ReferencedTableSchema = "HumanResources"  
  
#Create the foreign key on the instance of SQL Server.   
$fk.Create()  
```  
  
## <a name="sample-foreign-keys-primary-keys-and-unique-constraint-columns"></a><span data-ttu-id="fe208-120">Ejemplo: claves externas, claves principales y columnas de restricción UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fe208-120">Sample: Foreign Keys, Primary Keys, and Unique Constraint Columns</span></span>  
 <span data-ttu-id="fe208-121">En este ejemplo se muestra:</span><span class="sxs-lookup"><span data-stu-id="fe208-121">This sample demonstrates:</span></span>  
  
-   <span data-ttu-id="fe208-122">Buscar una clave externa en un objeto existente.</span><span class="sxs-lookup"><span data-stu-id="fe208-122">Finding a foreign key on an existing object.</span></span>  
  
-   <span data-ttu-id="fe208-123">Crear una clave principal.</span><span class="sxs-lookup"><span data-stu-id="fe208-123">How to create a primary key.</span></span>  
  
-   <span data-ttu-id="fe208-124">Crear una columna de restricción UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="fe208-124">How to create a unique constraint column.</span></span>  
  
 <span data-ttu-id="fe208-125">La versión de C# de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fe208-125">The C# version of this sample:</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:microsoft.sqlserver.management.sdk.sfc.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.SqlEnum.dll  
  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
using Microsoft.SqlServer.Management.Common;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // PK Table  
      Table tab1 = new Table(db, "Table1");  
  
      // Define Columns and add them to the table  
      Column col1 = new Column(tab1, "Col1", DataType.Int);  
  
      col1.Nullable = false;  
      tab1.Columns.Add(col1);  
      Column col2 = new Column(tab1, "Col2", DataType.NVarChar(50));  
      tab1.Columns.Add(col2);  
      Column col3 = new Column(tab1, "Col3", DataType.DateTime);  
      tab1.Columns.Add(col3);  
  
      // Create the ftable  
      tab1.Create();  
  
      // Define Index object on the table by supplying the Table1 as the parent table and the primary key name in the constructor.  
      Index pk = new Index(tab1, "Table1_PK");  
      pk.IndexKeyType = IndexKeyType.DriPrimaryKey;  
  
      // Add Col1 as the Index Column  
      IndexedColumn idxCol1 = new IndexedColumn(pk, "Col1");  
      pk.IndexedColumns.Add(idxCol1);  
  
      // Create the Primary Key  
      pk.Create();  
  
      // Create Unique Index on the table  
      Index unique = new Index(tab1, "Table1_Unique");  
      unique.IndexKeyType = IndexKeyType.DriUniqueKey;  
  
      // Add Col1 as the Unique Index Column  
      IndexedColumn idxCol2 = new IndexedColumn(unique, "Col2");  
      unique.IndexedColumns.Add(idxCol2);  
  
      // Create the Unique Index  
      unique.Create();  
  
      // Create Table2                    
      Table tab2 = new Table(db, "Table2");  
      Column col21 = new Column(tab2, "Col21", DataType.NChar(20));  
      tab2.Columns.Add(col21);  
      Column col22 = new Column(tab2, "Col22", DataType.Int);  
      tab2.Columns.Add(col22);  
      tab2.Create();  
  
      // Define a Foreign Key object variable by supplying the Table2 as the parent table and the foreign key name in the constructor.   
      ForeignKey fk = new ForeignKey(tab2, "Table2_FK");  
  
      // Add Col22 as the foreign key column.   
      ForeignKeyColumn fkc = new ForeignKeyColumn(fk, "Col22", "Col1");  
      fk.Columns.Add(fkc);  
      fk.ReferencedTable = "Table1";  
  
      // Create the foreign key on the instance of SQL Server.   
      fk.Create();                    
  
      // Get list of Foreign Keys on Table2  
      foreach (ForeignKey f in tab2.ForeignKeys) {  
            Console.WriteLine(f.Name + " " + f.ReferencedTable + " " + f.ReferencedKey);  
      }  
  
      // Get list of Foreign Keys referencing table1  
      foreach (Table tab in db.Tables) {  
         if (tab == tab1)  
            continue;  
            foreach (ForeignKey f in tab.ForeignKeys) {  
               if (f.ReferencedTable.Equals(tab1.Name))  
                  Console.WriteLine(f.Name + " " + f.Parent.Name);  
            }  
      }  
   }  
}  
```  
  
 <span data-ttu-id="fe208-126">La versión de Visual Basic de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fe208-126">The Visual Basic version of the sample:</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:microsoft.sqlserver.management.sdk.sfc.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.SqlEnum.dll  
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
      Dim db As New Database(svr, "TESTDB")  
      db.Create()  
  
      ' PK Table  
      Dim tab1 As New Table(db, "Table1")  
  
      ' Define Columns and add them to the table  
      Dim col1 As New Column(tab1, "Col1", DataType.Int)  
  
      col1.Nullable = False  
      tab1.Columns.Add(col1)  
      Dim col2 As New Column(tab1, "Col2", DataType.NVarChar(50))  
      tab1.Columns.Add(col2)  
      Dim col3 As New Column(tab1, "Col3", DataType.DateTime)  
      tab1.Columns.Add(col3)  
  
      ' Create the ftable  
      tab1.Create()  
  
      ' Define Index object on the table by supplying the Table1 as the parent table and the primary key name in the constructor.  
      Dim pk As New Index(tab1, "Table1_PK")  
      pk.IndexKeyType = IndexKeyType.DriPrimaryKey  
  
      ' Add Col1 as the Index Column  
      Dim idxCol1 As New IndexedColumn(pk, "Col1")  
      pk.IndexedColumns.Add(idxCol1)  
  
      ' Create the Primary Key  
      pk.Create()  
  
      ' Create Unique Index on the table  
      Dim unique As New Index(tab1, "Table1_Unique")  
      unique.IndexKeyType = IndexKeyType.DriUniqueKey  
  
      ' Add Col1 as the Unique Index Column  
      Dim idxCol2 As New IndexedColumn(unique, "Col2")  
      unique.IndexedColumns.Add(idxCol2)  
  
      ' Create the Unique Index  
      unique.Create()  
  
      ' Create Table2                    
      Dim tab2 As New Table(db, "Table2")  
      Dim col21 As New Column(tab2, "Col21", DataType.NChar(20))  
      tab2.Columns.Add(col21)  
      Dim col22 As New Column(tab2, "Col22", DataType.Int)  
      tab2.Columns.Add(col22)  
      tab2.Create()  
  
      ' Define a Foreign Key object variable by supplying the Table2 as the parent table and the foreign key name in the constructor.   
      Dim fk As New ForeignKey(tab2, "Table2_FK")  
  
      ' Add Col22 as the foreign key column.   
      Dim fkc As New ForeignKeyColumn(fk, "Col22", "Col1")  
      fk.Columns.Add(fkc)  
      fk.ReferencedTable = "Table1"  
  
      ' Create the foreign key on the instance of SQL Server.   
      fk.Create()  
  
      ' Get list of Foreign Keys on Table2  
      For Each f As ForeignKey In tab2.ForeignKeys  
         Console.WriteLine((f.Name + " " + f.ReferencedTable & " ") + f.ReferencedKey)  
      Next  
  
      ' Get list of Foreign Keys referencing table1  
      For Each tab As Table In db.Tables  
         If (tab.Name.Equals(tab1.Name)) Then  
            Continue For  
         End If  
         For Each f As ForeignKey In tab.ForeignKeys  
            If f.ReferencedTable.Equals(tab1.Name) Then  
               Console.WriteLine(f.Name + " " + f.Parent.Name)  
            End If  
         Next  
      Next  
   End Sub  
End Class  
```  
