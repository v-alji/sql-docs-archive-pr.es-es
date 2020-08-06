---
title: Llamar a métodos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13216b4c533527d4249471073580d7c86f6b07e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747547"
---
# <a name="calling-methods"></a><span data-ttu-id="0948e-102">Llamar a métodos</span><span class="sxs-lookup"><span data-stu-id="0948e-102">Calling Methods</span></span>
  <span data-ttu-id="0948e-103">Los métodos realizan tareas específicas relacionadas con el objeto, como la emisión de un `Checkpoint` en una base de datos o la solicitud de una lista enumerada de inicios de sesión para la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0948e-103">Methods perform specific tasks related to the object, such as issuing a `Checkpoint` on a database or requesting an enumerated list of logons for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0948e-104">Los métodos realizan una operación en un objeto.</span><span class="sxs-lookup"><span data-stu-id="0948e-104">Methods perform an operation on an object.</span></span> <span data-ttu-id="0948e-105">Los métodos pueden tomar parámetros y a menudo tener un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0948e-105">Methods can take parameters and often have a return value.</span></span> <span data-ttu-id="0948e-106">El valor devuelto puede ser un tipo de datos simple, un objeto complejo o una estructura que contiene muchos miembros.</span><span class="sxs-lookup"><span data-stu-id="0948e-106">The return value can be a simple data type, a complex object, or a structure that contains many members.</span></span>  
  
 <span data-ttu-id="0948e-107">Use el control de excepciones para detectar si el método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0948e-107">Use exception handling to detect whether the method has been successful.</span></span> <span data-ttu-id="0948e-108">Para más información, consulte [Handling SMO Exceptions](handling-smo-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="0948e-108">For more information, see [Handling SMO Exceptions](handling-smo-exceptions.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0948e-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0948e-109">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a><span data-ttu-id="0948e-110">Usar un método SMO simple en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0948e-110">Using a Simple SMO Method in Visual Basic</span></span>  
 <span data-ttu-id="0948e-111">En este ejemplo, el método <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> no toma ningún parámetro y no devuelve ningún valor.</span><span class="sxs-lookup"><span data-stu-id="0948e-111">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods1](SMO How to#SMO_VBMethods1)]  -->  
  
## <a name="using-a-simple-smo-method-in-visual-c"></a><span data-ttu-id="0948e-112">Usar un método SMO simple en Visual C#</span><span class="sxs-lookup"><span data-stu-id="0948e-112">Using a Simple SMO Method in Visual C#</span></span>  
 <span data-ttu-id="0948e-113">En este ejemplo, el método <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> no toma ningún parámetro y no devuelve ningún valor.</span><span class="sxs-lookup"><span data-stu-id="0948e-113">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 <span data-ttu-id="0948e-114">}</span><span class="sxs-lookup"><span data-stu-id="0948e-114">}</span></span>  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a><span data-ttu-id="0948e-115">Usar un método SMO con un parámetro en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0948e-115">Using an SMO Method with a Parameter in Visual Basic</span></span>  
 <span data-ttu-id="0948e-116">El objeto <xref:Microsoft.SqlServer.Management.Smo.Table> tiene un método denominado <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="0948e-116">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="0948e-117">Este método requiere un parámetro numérico que especifica `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="0948e-117">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a><span data-ttu-id="0948e-118">Usar un método SMO con un parámetro en Visual C#</span><span class="sxs-lookup"><span data-stu-id="0948e-118">Using an SMO Method with a Parameter in Visual C#</span></span>  
 <span data-ttu-id="0948e-119">El objeto <xref:Microsoft.SqlServer.Management.Smo.Table> tiene un método denominado <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="0948e-119">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="0948e-120">Este método requiere un parámetro numérico que especifica `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="0948e-120">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a><span data-ttu-id="0948e-121">Usar un método de enumeración que devuelve un objeto DataTable en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0948e-121">Using an Enumeration Method that Returns a DataTable Object in Visual Basic</span></span>  
 <span data-ttu-id="0948e-122">En esta sección se describe cómo llamar a un método de enumeración y cómo controlar los datos del objeto <xref:System.Data.DataTable> devuelto.</span><span class="sxs-lookup"><span data-stu-id="0948e-122">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="0948e-123">El método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> devuelve un objeto <xref:System.Data.DataTable>, que requiere más navegación para tener acceso a toda la información de intercalación disponible acerca de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0948e-123">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a <xref:System.Data.DataTable> object, which requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a><span data-ttu-id="0948e-124">Usar un método de enumeración que devuelve un objeto DataTable en Visual C#</span><span class="sxs-lookup"><span data-stu-id="0948e-124">Using an Enumeration Method that Returns a DataTable Object in Visual C#</span></span>  
 <span data-ttu-id="0948e-125">En esta sección se describe cómo llamar a un método de enumeración y cómo controlar los datos del objeto <xref:System.Data.DataTable> devuelto.</span><span class="sxs-lookup"><span data-stu-id="0948e-125">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="0948e-126">El método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> devuelve un objeto <xref:System.Data.DataTable> del sistema.</span><span class="sxs-lookup"><span data-stu-id="0948e-126">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a system <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="0948e-127">El objeto <xref:System.Data.DataTable> requiere más navegación para obtener acceso a toda la información de intercalación disponible acerca de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0948e-127">The <xref:System.Data.DataTable> object requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a><span data-ttu-id="0948e-128">Construir un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0948e-128">Constructing an Object in Visual Basic</span></span>  
 <span data-ttu-id="0948e-129">Se puede llamar al constructor de cualquier objeto mediante el operador `New`.</span><span class="sxs-lookup"><span data-stu-id="0948e-129">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="0948e-130">El constructor de objeto <xref:Microsoft.SqlServer.Management.Smo.Database> se sobrecarga y la versión del constructor de objeto <xref:Microsoft.SqlServer.Management.Smo.Database> que se usa en el ejemplo toma dos parámetros: el objeto primario <xref:Microsoft.SqlServer.Management.Smo.Server> al que pertenece la base de datos y una cadena que representa el nombre de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="0948e-130">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods4](SMO How to#SMO_VBMethods4)]  -->  
  
## <a name="constructing-an-object-in-visual-c"></a><span data-ttu-id="0948e-131">Construir un objeto en Visual C#</span><span class="sxs-lookup"><span data-stu-id="0948e-131">Constructing an Object in Visual C#</span></span>  
 <span data-ttu-id="0948e-132">Se puede llamar al constructor de cualquier objeto mediante el operador `New`.</span><span class="sxs-lookup"><span data-stu-id="0948e-132">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="0948e-133">El constructor de objeto <xref:Microsoft.SqlServer.Management.Smo.Database> se sobrecarga y la versión del constructor de objeto <xref:Microsoft.SqlServer.Management.Smo.Database> que se usa en el ejemplo toma dos parámetros: el objeto primario <xref:Microsoft.SqlServer.Management.Smo.Server> al que pertenece la base de datos y una cadena que representa el nombre de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="0948e-133">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a><span data-ttu-id="0948e-134">Copiar un objeto SMO en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0948e-134">Copying an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="0948e-135">En este ejemplo de código se usa el método <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> para crear una copia del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="0948e-135">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="0948e-136">El objeto <xref:Microsoft.SqlServer.Management.Smo.Server> representa una conexión a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0948e-136">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VCMethods6](SMO How to#SMO_VCMethods6)]  -->  
  
## <a name="copying-an-smo-object-in-visual-c"></a><span data-ttu-id="0948e-137">Copiar un objeto SMO en Visual C#</span><span class="sxs-lookup"><span data-stu-id="0948e-137">Copying an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="0948e-138">En este ejemplo de código se usa el método <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> para crear una copia del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="0948e-138">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="0948e-139">El objeto <xref:Microsoft.SqlServer.Management.Smo.Server> representa una conexión a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0948e-139">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a><span data-ttu-id="0948e-140">Supervisar los procesos de servidor en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0948e-140">Monitoring Server Processes in Visual Basic</span></span>  
 <span data-ttu-id="0948e-141">Puede obtener la información de tipo de estado actual de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a través de los métodos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="0948e-141">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="0948e-142">El ejemplo de código usa el método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> para detectar información sobre los procesos actuales.</span><span class="sxs-lookup"><span data-stu-id="0948e-142">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="0948e-143">También muestra cómo trabajar con las columnas y filas del objeto <xref:System.Data.DataTable> devuelto.</span><span class="sxs-lookup"><span data-stu-id="0948e-143">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods5](SMO How to#SMO_VBMethods5)]  -->  
  
## <a name="monitoring-server-processes-in-visual-c"></a><span data-ttu-id="0948e-144">Supervisar los procesos de servidor en Visual C#</span><span class="sxs-lookup"><span data-stu-id="0948e-144">Monitoring Server Processes in Visual C#</span></span>  
 <span data-ttu-id="0948e-145">Puede obtener la información de tipo de estado actual de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a través de los métodos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="0948e-145">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="0948e-146">El ejemplo de código usa el método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> para detectar información sobre los procesos actuales.</span><span class="sxs-lookup"><span data-stu-id="0948e-146">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="0948e-147">También muestra cómo trabajar con las columnas y filas del objeto <xref:System.Data.DataTable> devuelto.</span><span class="sxs-lookup"><span data-stu-id="0948e-147">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a><span data-ttu-id="0948e-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0948e-148">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
