---
title: Recuperando datos UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SqlDataReader object
- ADO.NET [CLR integration]
- binding UDTs [CLR integration]
- UDTs [CLR integration], ADO.NET
- assemblies [CLR integration], user-defined types
- query parameters [CLR integration]
- user-defined types [CLR integration], ADO.NET
- bytes [CLR integration]
ms.assetid: 6a98ac8c-0e69-4c03-83a4-2062cb782049
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9133ea45069f76e7590f6b74d3c1e1cb98c7bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674874"
---
# <a name="retrieving-udt-data"></a><span data-ttu-id="11007-102">Recuperar datos UDT</span><span class="sxs-lookup"><span data-stu-id="11007-102">Retrieving UDT Data</span></span>
  <span data-ttu-id="11007-103">Para crear un tipo definido por el usuario (UDT) en el cliente, el ensamblado que se registró como UDT en una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe estar disponible para la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="11007-103">In order to create a user-defined type (UDT) on the client, the assembly that was registered as a UDT in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database must be available to the client application.</span></span> <span data-ttu-id="11007-104">El ensamblado UDT se puede colocar en el mismo directorio que la aplicación o en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="11007-104">The UDT assembly can be placed in the same directory with the application, or in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="11007-105">También puede establecer una referencia al ensamblado en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="11007-105">You can also set a reference to the assembly in your project.</span></span>  
  
## <a name="requirements-for-using-udts-in-adonet"></a><span data-ttu-id="11007-106">Requisitos para utilizar UDT en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="11007-106">Requirements for Using UDTs in ADO.NET</span></span>  
 <span data-ttu-id="11007-107">El ensamblado cargado en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el ensamblado cargado en el cliente deben ser compatibles para que se pueda crear el UDT en el cliente.</span><span class="sxs-lookup"><span data-stu-id="11007-107">The assembly loaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the assembly on the client must be compatible in order for the UDT to be created on the client.</span></span> <span data-ttu-id="11007-108">Para los UDT definidos con el formato de serialización `Native`, los ensamblados deben ser compatibles estructuralmente.</span><span class="sxs-lookup"><span data-stu-id="11007-108">For UDTs defined with the `Native` serialization format, the assemblies must be structurally compatible.</span></span> <span data-ttu-id="11007-109">En el caso de ensamblados definidos con el formato `UserDefined`, el ensamblado debe estar disponible en el cliente.</span><span class="sxs-lookup"><span data-stu-id="11007-109">For assemblies defined with the `UserDefined` format, the assembly must be available on the client.</span></span>  
  
 <span data-ttu-id="11007-110">No es necesario que haya una copia del ensamblado UDT en el cliente para recuperar los datos sin formato de una columna UDT de una tabla.</span><span class="sxs-lookup"><span data-stu-id="11007-110">You do not need a copy of the UDT assembly on the client in order to retrieve the raw data from a UDT column in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11007-111">**SqlClient** puede no cargar un UDT en caso de que no coincidan las versiones UDT u otros problemas.</span><span class="sxs-lookup"><span data-stu-id="11007-111">**SqlClient** may fail to load a UDT in the event of mismatched UDT versions or other problems.</span></span> <span data-ttu-id="11007-112">En ese caso, utilice los mecanismos de solución de problemas habituales para determinar por qué la aplicación que realiza la llamada no encuentra el ensamblado que contiene el UDT.</span><span class="sxs-lookup"><span data-stu-id="11007-112">In this case, use regular troubleshooting mechanisms to determine why the assembly containing the UDT cannot be found by the calling application.</span></span> <span data-ttu-id="11007-113">Para obtener más información, lea el tema denominado "Diagnóstico de errores con asistentes de depuraciones administradas" en la documentación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="11007-113">For more information, read the topic titled "Diagnosing Errors with Managed Debugging Assistants" in the .NET Framework documentation.</span></span>  
  
## <a name="accessing-udts-with-a-sqldatareader"></a><span data-ttu-id="11007-114">Obtener acceso a UDT con SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="11007-114">Accessing UDTs with a SqlDataReader</span></span>  
 <span data-ttu-id="11007-115">Se puede utilizar `System.Data.SqlClient.SqlDataReader` en el código del cliente para recuperar un conjunto de resultados que contiene una columna UDT, el cual se expone como una instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="11007-115">A `System.Data.SqlClient.SqlDataReader` can be used from client code to retrieve a result set that contains a UDT column, which is exposed as an instance of the object.</span></span>  
  
### <a name="example"></a><span data-ttu-id="11007-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11007-116">Example</span></span>  
 <span data-ttu-id="11007-117">En este ejemplo se muestra cómo utilizar el método `Main` para crear un nuevo objeto `SqlDataReader`. </span><span class="sxs-lookup"><span data-stu-id="11007-117">This example shows how to use the `Main` method to create a new `SqlDataReader` object.</span></span> <span data-ttu-id="11007-118">En el ejemplo de código se producen las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="11007-118">The following actions occur within the code example:</span></span>  
  
1.  <span data-ttu-id="11007-119">El método Main crea un nuevo objeto `SqlDataReader` y recupera los valores de la tabla Points, que tiene una columna de UDT denominada Point.</span><span class="sxs-lookup"><span data-stu-id="11007-119">The Main method creates a new `SqlDataReader` object and retrieves the values from the Points table, which has a UDT column named Point.</span></span>  
  
2.  <span data-ttu-id="11007-120">El UDT Point expone las coordenadas X e Y definidas como enteros.</span><span class="sxs-lookup"><span data-stu-id="11007-120">The Point UDT exposes X and Y coordinates defined as integers.</span></span>  
  
3.  <span data-ttu-id="11007-121">El UDT define un método `Distance` y un método `GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="11007-121">The UDT defines a `Distance` method and a `GetDistanceFromXY` method.</span></span>  
  
4.  <span data-ttu-id="11007-122">El código muestra recupera los valores de las columnas de UDT y de clave principal para mostrar las capacidades del UDT.</span><span class="sxs-lookup"><span data-stu-id="11007-122">The sample code retrieves the values of the primary key and UDT columns in order to demonstrate the capabilities of the UDT.</span></span>  
  
5.  <span data-ttu-id="11007-123">El código muestra llama a los métodos `Point.Distance` y `Point.GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="11007-123">The sample code calls the `Point.Distance` and `Point.GetDistanceFromXY` methods.</span></span>  
  
6.  <span data-ttu-id="11007-124">Los resultados se muestran en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="11007-124">The results are displayed in the console window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11007-125">La aplicación ya debe tener una referencia al ensamblado UDT.</span><span class="sxs-lookup"><span data-stu-id="11007-125">The application must already have a reference to the UDT assembly.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module ReadPoints  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the value of the UDT  
                Dim pnt As Point = CType(rdr(1), Point)  
  
             ' You can also use GetSqlValue and GetValue  
             ' Dim pnt As Point = CType(rdr.GetSqlValue(1), Point)  
             ' Dim pnt As Point = CType(rdr.GetValue(1), Point)  
  
                ' Print values  
                Console.WriteLine( _  
                 "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}", _  
                  id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance())  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
         & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
namespace Microsoft.Samples.SqlServer  
{  
class ReadPoints  
{  
static void Main()  
{  
  string connectionString = GetConnectionString();  
  using (SqlConnection cnn = new SqlConnection(connectionString))  
  {  
    cnn.Open();  
    SqlCommand cmd = new SqlCommand(  
       "SELECT ID, Pnt FROM dbo.Points", cnn);  
    SqlDataReader rdr = cmd.ExecuteReader();  
  
    while (rdr.Read())  
    {  
      // Retrieve the value of the Primary Key column  
      int id = rdr.GetInt32(0);  
  
        // Retrieve the value of the UDT  
        Point pnt = (Point)rdr[1];  
  
        // You can also use GetSqlValue and GetValue  
        // Point pnt = (Point)rdr.GetSqlValue(1);  
        // Point pnt = (Point)rdr.GetValue(1);  
  
        Console.WriteLine(  
        "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}",   
        id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance());  
    }  
  rdr.Close();  
  Console.WriteLine("done");  
  }  
  static private string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,   
    // you can retrieve it from a configuration file.  
    return "Data Source=(local);Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="binding-udts-as-bytes"></a><span data-ttu-id="11007-126">Enlazar UDT como bytes</span><span class="sxs-lookup"><span data-stu-id="11007-126">Binding UDTs as Bytes</span></span>  
 <span data-ttu-id="11007-127">Es posible que en algunas situaciones desee recuperar los datos sin formato de la columna de UDT.</span><span class="sxs-lookup"><span data-stu-id="11007-127">In some situations, you may want to retrieve the raw data from the UDT column.</span></span> <span data-ttu-id="11007-128">Quizás el tipo no esté disponible localmente o no desee crear instancias de una instancia del UDT.</span><span class="sxs-lookup"><span data-stu-id="11007-128">Perhaps the type is not available locally, or you do not wish to instantiate an instance of the UDT.</span></span> <span data-ttu-id="11007-129">Puede leer los bytes sin formato en una matriz de bytes mediante el método **GetBytes** de un `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="11007-129">You can read the raw bytes into a byte array using the **GetBytes** method of a `SqlDataReader`.</span></span> <span data-ttu-id="11007-130">Este método lee un flujo de bytes a partir del desplazamiento de la columna especificada en el búfer de una matriz, comenzando en el desplazamiento del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="11007-130">This method reads a stream of bytes from the specified column offset into the buffer of an array starting at a specified buffer offset.</span></span> <span data-ttu-id="11007-131">Otra opción es usar uno de los métodos **GetSqlBytes** o **GetSqlBinary** y leer todo el contenido en una sola operación.</span><span class="sxs-lookup"><span data-stu-id="11007-131">Another option is to use one of the **GetSqlBytes** or **GetSqlBinary** methods and read all of the contents in a single operation.</span></span> <span data-ttu-id="11007-132">En cualquier caso, nunca se crean instancias del objeto UDT, de modo que no es necesario establecer una referencia al UDT en el ensamblado de cliente.</span><span class="sxs-lookup"><span data-stu-id="11007-132">In either case, the UDT object is never instantiated, so you do not need to set a reference to the UDT in the client assembly.</span></span>  
  
### <a name="example"></a><span data-ttu-id="11007-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11007-133">Example</span></span>  
 <span data-ttu-id="11007-134">En este ejemplo se muestra cómo recuperar los datos de **punto** como bytes sin formato en una matriz de bytes mediante `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="11007-134">This example shows how to retrieve the **Point** data as raw bytes into a byte array using a `SqlDataReader`.</span></span> <span data-ttu-id="11007-135">El código utiliza `System.Text.StringBuilder` para convertir los bytes sin formato en una representación de cadena que se mostrará en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="11007-135">The code uses a `System.Text.StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the raw bytes into a byte array  
                Dim buffer(31) As Byte  
                Dim byteCount As Integer = _  
                 CInt(rdr.GetBytes(1, 0, buffer, 0, 31))  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", buffer(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
        string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand("SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Retrieve the raw bytes into a byte array  
                byte[] buffer = new byte[32];  
                long byteCount = rdr.GetBytes(1, 0, buffer, 0, 32);  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", buffer[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
### <a name="example-using-getsqlbytes"></a><span data-ttu-id="11007-136">Ejemplo con GetSqlBytes</span><span class="sxs-lookup"><span data-stu-id="11007-136">Example Using GetSqlBytes</span></span>  
 <span data-ttu-id="11007-137">En este ejemplo se muestra cómo recuperar los datos de **punto** como bytes sin formato en una sola operación mediante el método **GetSqlBytes** .</span><span class="sxs-lookup"><span data-stu-id="11007-137">This example shows how to retrieve the **Point** data as raw bytes in a single operation using the **GetSqlBytes** method.</span></span> <span data-ttu-id="11007-138">El código utiliza `StringBuilder` para convertir los bytes sin formato en una representación de cadena que se mostrará en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="11007-138">The code uses a `StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Use SqlBytes to retrieve raw bytes  
                Dim sb As SqlBytes = rdr.GetSqlBytes(1)  
                Dim byteCount As Long = sb.Length  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", sb(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
         string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Use SqlBytes to retrieve raw bytes  
                SqlBytes sb = rdr.GetSqlBytes(1);  
                long byteCount = sb.Length;  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", sb[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="working-with-udt-parameters"></a><span data-ttu-id="11007-139">Trabajar con parámetros UDT</span><span class="sxs-lookup"><span data-stu-id="11007-139">Working with UDT Parameters</span></span>  
 <span data-ttu-id="11007-140">Los UDT se pueden utilizar en el código de ADO.NET como parámetros de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="11007-140">UDTs can be used as both input and output parameters in your ADO.NET code.</span></span>  
  
## <a name="using-udts-in-query-parameters"></a><span data-ttu-id="11007-141">Utilizar UDT en parámetros de consulta</span><span class="sxs-lookup"><span data-stu-id="11007-141">Using UDTs in Query Parameters</span></span>  
 <span data-ttu-id="11007-142">Los UDT se pueden utilizar como valores de parámetros cuando se configura un `SqlParameter` para un objeto `System.Data.SqlClient.SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="11007-142">UDTs can be used as parameter values when setting up a `SqlParameter` for a `System.Data.SqlClient.SqlCommand` object.</span></span> <span data-ttu-id="11007-143">La enumeración `SqlDbType.Udt` de un objeto `SqlParameter` se utiliza para indicar que el parámetro es un UDT cuando se llama al método `Add` en la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="11007-143">The `SqlDbType.Udt` enumeration of a `SqlParameter` object is used to indicate that the parameter is a UDT when calling the `Add` method to the `Parameters` collection.</span></span> <span data-ttu-id="11007-144">La `UdtTypeName` propiedad de un `SqlCommand` objeto se utiliza para especificar el nombre completo del UDT en la base de datos utilizando la sintaxis *Database. schema_name. object_name* .</span><span class="sxs-lookup"><span data-stu-id="11007-144">The `UdtTypeName` property of a `SqlCommand` object is used to specify the fully qualified name of the UDT in the database using the *database.schema_name.object_name* syntax.</span></span> <span data-ttu-id="11007-145">Aunque no es necesario, el uso del nombre completo quita ambigüedad al código.</span><span class="sxs-lookup"><span data-stu-id="11007-145">Although it is not required, using the fully qualified name removes ambiguity from your code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11007-146">Debe haber una copia local del ensamblado UDT disponible para el proyecto del cliente.</span><span class="sxs-lookup"><span data-stu-id="11007-146">A local copy of the UDT assembly must be available to the client project.</span></span>  
  
### <a name="example"></a><span data-ttu-id="11007-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11007-147">Example</span></span>  
 <span data-ttu-id="11007-148">El código de este ejemplo crea objetos `SqlCommand` y `SqlParameter` para insertar datos en una columna de UDT de una tabla.</span><span class="sxs-lookup"><span data-stu-id="11007-148">The code in this example creates `SqlCommand` and `SqlParameter` objects to insert data into a UDT column in a table.</span></span> <span data-ttu-id="11007-149">El código utiliza la enumeración `SqlDbType.Udt` para especificar el tipo de datos y la propiedad `UdtTypeName` del objeto `SqlParameter` para especificar el nombre completo del UDT en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="11007-149">The code uses the `SqlDbType.Udt` enumeration to specify the data type, and the `UdtTypeName` property of the `SqlParameter` object to specify the fully qualified name of the UDT in the database.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports system.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim ConnectionString As String = GetConnectionString()  
    Dim cnn As New SqlConnection(ConnectionString)  
    Using cnn  
      Dim cmd As SqlCommand = cnn.CreateCommand()  
      cmd.CommandText = "INSERT INTO dbo.Points (Pnt) VALUES (@Point)"  
      cmd.CommandType = CommandType.Text  
  
      Dim param As New SqlParameter("@Point", SqlDbType.Udt)      param.UdtTypeName = "TestPoint.dbo.Point"      param.Direction = ParameterDirection.Input      param.Value = New Point(5, 6)      cmd.Parameters.Add(param)  
  
      cnn.Open()  
      cmd.ExecuteNonQuery()  
      Console.WriteLine("done")  
    End Using  
  End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  string ConnectionString = GetConnectionString();  
     using (SqlConnection cnn = new SqlConnection(ConnectionString))  
     {  
       SqlCommand cmd = cnn.CreateCommand();  
       cmd.CommandText =   
         "INSERT INTO dbo.Points (Pnt) VALUES (@Point)";  
       cmd.CommandType = CommandType.Text;  
  
       SqlParameter param = new SqlParameter("@Point", SqlDbType.Udt);       param.UdtTypeName = "TestPoint.dbo.Point";       param.Direction = ParameterDirection.Input;       param.Value = new Point(5, 6);       cmd.Parameters.Add(param);  
  
       cnn.Open();  
       cmd.ExecuteNonQuery();  
       Console.WriteLine("done");  
     }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="11007-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11007-150">See Also</span></span>  
 [<span data-ttu-id="11007-151">Acceso a tipos definidos por el usuario en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="11007-151">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
