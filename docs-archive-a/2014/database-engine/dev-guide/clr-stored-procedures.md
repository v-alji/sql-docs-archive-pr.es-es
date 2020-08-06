---
title: Procedimientos almacenados CLR | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration], stored procedures
- stored procedures [CLR integration]
- common language runtime [SQL Server], stored procedures
- building database objects [CLR integration], stored procedures
- output parameters [CLR integration]
- tabular results
ms.assetid: bbdd51b2-a9b4-4916-ba6f-7957ac6c3f33
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f8c69435e28bfa67c72e26b7a54e419cd91ef220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670537"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="fb285-102">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="fb285-102">CLR Stored Procedures</span></span>
  <span data-ttu-id="fb285-103">Los procedimientos almacenados son rutinas que no pueden usarse en expresiones escalares.</span><span class="sxs-lookup"><span data-stu-id="fb285-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="fb285-104">A diferencia de las funciones escalares, pueden devolver mensajes y resultados tabulares al cliente, invocar instrucciones del lenguaje de definición de datos (DDL) e instrucciones del lenguaje de manipulación de datos (DML), así como devolver parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="fb285-104">Unlike scalar functions, they can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span> <span data-ttu-id="fb285-105">Para obtener información sobre las ventajas de la integración CLR y la elección entre código administrado y [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte [información general sobre la integración CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb285-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-stored-procedures"></a><span data-ttu-id="fb285-106">Requisitos de los procedimientos almacenados CLR</span><span class="sxs-lookup"><span data-stu-id="fb285-106">Requirements for CLR Stored Procedures</span></span>  
 <span data-ttu-id="fb285-107">En el Common Language Runtime (CLR), los procedimientos almacenados se implementan como métodos estáticos públicos en una clase de un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fb285-107">In the common language runtime (CLR), stored procedures are implemented as public static methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span></span> <span data-ttu-id="fb285-108">El método estático puede declararse como void o devolver un valor entero.</span><span class="sxs-lookup"><span data-stu-id="fb285-108">The static method can either be declared as void, or return an integer value.</span></span> <span data-ttu-id="fb285-109">Si devuelve un valor entero, el entero devuelto se trata como el código de retorno del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fb285-109">If it returns an integer value, the integer returned is treated as the return code from the procedure.</span></span> <span data-ttu-id="fb285-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fb285-110">For example:</span></span>  
  
 `EXECUTE @return_status = procedure_name`  
  
 <span data-ttu-id="fb285-111">La @return_status variable contendrá el valor devuelto por el método.</span><span class="sxs-lookup"><span data-stu-id="fb285-111">The @return_status variable will contain the value returned by the method.</span></span> <span data-ttu-id="fb285-112">Si el método se declara como void, el código de retorno es 0.</span><span class="sxs-lookup"><span data-stu-id="fb285-112">If the method is declared void, the return code is 0.</span></span>  
  
 <span data-ttu-id="fb285-113">Si el método toma parámetros, el número de parámetros de la implementación de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] debe ser igual al número de parámetros utilizados en la declaración [!INCLUDE[tsql](../../includes/tsql-md.md)] del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="fb285-113">If the method takes parameters, the number of parameters in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] implementation should be the same as the number of parameters used in the [!INCLUDE[tsql](../../includes/tsql-md.md)] declaration of the stored procedure.</span></span>  
  
 <span data-ttu-id="fb285-114">Los parámetros pasados a un procedimiento almacenado CLR pueden ser cualquiera de los tipos nativos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que tienen un equivalente en código administrado.</span><span class="sxs-lookup"><span data-stu-id="fb285-114">Parameters passed to a CLR stored procedure can be any of the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types that have an equivalent in managed code.</span></span> <span data-ttu-id="fb285-115">Para crear el procedimiento mediante la sintaxis de [!INCLUDE[tsql](../../includes/tsql-md.md)], estos tipos deben especificarse con el tipo nativo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalente más adecuado.</span><span class="sxs-lookup"><span data-stu-id="fb285-115">For the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax to create the procedure, these types should be specified with the most appropriate native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type equivalent.</span></span> <span data-ttu-id="fb285-116">Para obtener más información sobre las conversiones de tipos, vea [asignar datos de parámetros CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="fb285-116">For more information about type conversions, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="fb285-117">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="fb285-117">Table-Valued Parameters</span></span>  
 <span data-ttu-id="fb285-118">Los parámetros con valores de tabla (TVP), tipos de tabla definidos por el usuario que se pasan a un procedimiento o función, proporcionan un modo eficaz de pasar varias filas de datos al servidor.</span><span class="sxs-lookup"><span data-stu-id="fb285-118">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="fb285-119">Los TVP presentan una funcionalidad similar a las matrices de parámetros, pero proporcionan más flexibilidad y una mayor integración con [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb285-119">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fb285-120">También proporcionan la posibilidad de obtener mayor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fb285-120">They also provide the potential for better performance.</span></span> <span data-ttu-id="fb285-121">Además, los TVP ayudan a reducir el número de ciclos de ida y vuelta al servidor.</span><span class="sxs-lookup"><span data-stu-id="fb285-121">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="fb285-122">En lugar de enviar varias solicitudes al servidor, como con una lista de parámetros escalares, los datos pueden enviarse al servidor como un TVP.</span><span class="sxs-lookup"><span data-stu-id="fb285-122">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="fb285-123">Un tipo de tabla definido por el usuario no puede pasarse como un parámetro con valores de tabla a un procedimiento almacenado administrado o a una función que se ejecuta en el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , así como tampoco puede devolverse desde dicho procedimiento o función.</span><span class="sxs-lookup"><span data-stu-id="fb285-123">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="fb285-124">Para obtener más información sobre TVP, vea [usar parámetros con valores de tabla &#40;Motor de base de datos&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="fb285-124">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="returning-results-from-clr-stored-procedures"></a><span data-ttu-id="fb285-125">Devolver resultados de los procedimientos almacenados CLR</span><span class="sxs-lookup"><span data-stu-id="fb285-125">Returning Results from CLR Stored Procedures</span></span>  
 <span data-ttu-id="fb285-126">La información puede devolverse de varios modos de los procedimientos almacenados de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)],</span><span class="sxs-lookup"><span data-stu-id="fb285-126">Information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures in several ways.</span></span> <span data-ttu-id="fb285-127">entre los que se incluyen parámetros de salida, resultados tabulares y mensajes.</span><span class="sxs-lookup"><span data-stu-id="fb285-127">This includes output parameters, tabular results, and messages.</span></span>  
  
### <a name="output-parameters-and-clr-stored-procedures"></a><span data-ttu-id="fb285-128">Parámetros OUTPUT y procedimientos almacenados CLR</span><span class="sxs-lookup"><span data-stu-id="fb285-128">OUTPUT Parameters and CLR Stored Procedures</span></span>  
 <span data-ttu-id="fb285-129">Al igual que ocurre con los procedimientos almacenados de [!INCLUDE[tsql](../../includes/tsql-md.md)], puede devolverse información de los procedimientos almacenados de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] mediante el uso de parámetros OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="fb285-129">As with [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures using OUTPUT parameters.</span></span> <span data-ttu-id="fb285-130">La sintaxis DML de [!INCLUDE[tsql](../../includes/tsql-md.md)] que se utiliza para crear procedimientos almacenados de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] es igual que la que se utiliza para crear procedimientos almacenados escritos en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb285-130">The [!INCLUDE[tsql](../../includes/tsql-md.md)] DML syntax used for creating [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures is the same as that used for creating stored procedures written in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fb285-131">El parámetro correspondiente en el código de implementación de la clase [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] debe usar un parámetro de paso por referencia como argumento.</span><span class="sxs-lookup"><span data-stu-id="fb285-131">The corresponding parameter in the implementation code in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="fb285-132">Tenga en cuenta que Visual Basic no admite parámetros de salida de la misma forma que en C#.</span><span class="sxs-lookup"><span data-stu-id="fb285-132">Note that Visual Basic does not support output parameters in the same way that C# does.</span></span> <span data-ttu-id="fb285-133">Debe especificar el parámetro por referencia y aplicar el \<Out()> atributo para representar un parámetro de salida, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="fb285-133">You must specify the parameter by reference and apply the \<Out()> attribute to represent an OUTPUT parameter, as in the following:</span></span>  
  
```vb
Imports System.Runtime.InteropServices  
...  
Public Shared Sub PriceSum ( <Out()> ByRef value As SqlInt32)  
```  
  
 <span data-ttu-id="fb285-134">A continuación se muestra un procedimiento almacenado que devuelve información a través de un parámetro OUTPUT:</span><span class="sxs-lookup"><span data-stu-id="fb285-134">The following shows a stored procedure returning information through an OUTPUT parameter:</span></span>  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void PriceSum(out SqlInt32 value)  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         value = 0;  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT Price FROM Products", connection);  
         SqlDataReader reader = command.ExecuteReader();  
  
         using (reader)  
         {  
            while( reader.Read() )  
            {  
               value += reader.GetSqlInt32(0);  
            }  
         }           
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Runtime.InteropServices  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Executes a query and iterates over the results to perform a summation.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
  
        Using connection As New SqlConnection("context connection=true")  
           value = 0  
           Connection.Open()  
           Dim command As New SqlCommand("SELECT Price FROM Products", connection)  
           Dim reader As SqlDataReader  
           reader = command.ExecuteReader()  
  
           Using reader  
              While reader.Read()  
                 value += reader.GetSqlInt32(0)  
              End While  
           End Using  
        End Using          
    End Sub  
End Class  
```  
  
 <span data-ttu-id="fb285-135">Cuando el ensamblado que contiene el procedimiento almacenado CLR anterior se ha compilado y creado en el servidor, [!INCLUDE[tsql](../../includes/tsql-md.md)] se utiliza lo siguiente para crear el procedimiento en la base de datos y se especifica *SUM* como parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="fb285-135">Once the assembly containing the above CLR stored procedure has been built and created on the server, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] is used to create the procedure in the database, and specifies *sum* as an OUTPUT parameter.</span></span>  
  
```sql
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
-- if StoredProcedures class was inside a namespace, called MyNS,  
-- you would use:  
-- AS EXTERNAL NAME TestStoredProc.[MyNS.StoredProcedures].PriceSum  
```  
  
 <span data-ttu-id="fb285-136">Tenga en cuenta que *SUM* se declara como un `int` tipo de datos SQL Server y que el parámetro *Value* definido en el procedimiento almacenado CLR se especifica como un `SqlInt32` tipo de datos CLR.</span><span class="sxs-lookup"><span data-stu-id="fb285-136">Note that *sum* is declared as an `int` SQL Server data type, and that the *value* parameter defined in the CLR stored procedure is specified as a `SqlInt32` CLR data type.</span></span> <span data-ttu-id="fb285-137">Cuando un programa que realiza la llamada ejecuta el procedimiento almacenado CLR, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] convierte automáticamente el `SqlInt32` tipo de datos CLR a un `int` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="fb285-137">When a calling program executes the CLR stored procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically converts the `SqlInt32` CLR data type to an `int`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  <span data-ttu-id="fb285-138">Para obtener más información acerca de los tipos de datos CLR que se pueden y no se pueden convertir, vea [asignar datos de parámetros CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="fb285-138">For more information about which CLR data types can and cannot be converted, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="fb285-139">Devolver mensajes y resultados tabulares</span><span class="sxs-lookup"><span data-stu-id="fb285-139">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="fb285-140">La devolución de mensajes y resultados tabulares al cliente se realiza a través del objeto `SqlPipe`, que se obtiene utilizando la propiedad `Pipe` de la clase `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="fb285-140">Returning tabular results and messages to the client is done through the `SqlPipe` object, which is obtained by using the `Pipe` property of the `SqlContext` class.</span></span> <span data-ttu-id="fb285-141">El objeto `SqlPipe` tiene un método `Send`.</span><span class="sxs-lookup"><span data-stu-id="fb285-141">The `SqlPipe` object has a `Send` method.</span></span> <span data-ttu-id="fb285-142">Al llamar al método `Send`, puede transmitir datos a la aplicación que realiza la llamada a través de la canalización.</span><span class="sxs-lookup"><span data-stu-id="fb285-142">By calling the `Send` method, you can transmit data through the pipe to the calling application.</span></span>  
  
 <span data-ttu-id="fb285-143">Existen varias sobrecargas del método `SqlPipe.Send`, incluida una que envía `SqlDataReader` y otra que simplemente envía una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="fb285-143">These are several overloads of the `SqlPipe.Send` method, including one that sends a `SqlDataReader` and another that simply sends a text string.</span></span>  
  
###### <a name="returning-messages"></a><span data-ttu-id="fb285-144">Devolver mensajes</span><span class="sxs-lookup"><span data-stu-id="fb285-144">Returning Messages</span></span>  
 <span data-ttu-id="fb285-145">Use `SqlPipe.Send(string)` para enviar mensajes a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="fb285-145">Use `SqlPipe.Send(string)` to send messages to the client application.</span></span> <span data-ttu-id="fb285-146">El texto del mensaje está limitado a 8000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="fb285-146">The text of the message is limited to 8000 characters.</span></span> <span data-ttu-id="fb285-147">Si el mensaje supera los 8000 caracteres, se truncará.</span><span class="sxs-lookup"><span data-stu-id="fb285-147">If the message exceeds 8000 characters, it will be truncated.</span></span>  
  
###### <a name="returning-tabular-results"></a><span data-ttu-id="fb285-148">Devolver resultados tabulares</span><span class="sxs-lookup"><span data-stu-id="fb285-148">Returning Tabular Results</span></span>  
 <span data-ttu-id="fb285-149">Para enviar los resultados de una consulta directamente al cliente, use una de las sobrecargas del método `Execute` en el objeto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="fb285-149">To send the results of a query directly to the client, use one of the overloads of the `Execute` method on the `SqlPipe` object.</span></span> <span data-ttu-id="fb285-150">Se trata del modo más eficaz de devolver resultados al cliente, puesto que los datos se transfieren a los búferes de red sin copiarse en la memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="fb285-150">This is the most efficient way to return results to the client, since the data is transferred to the network buffers without being copied into managed memory.</span></span> <span data-ttu-id="fb285-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fb285-151">For example:</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the results to the client directly.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void ExecuteToClient()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version", connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub ExecuteToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="fb285-152">Para enviar los resultados de una consulta previamente ejecutada a través del proveedor en proceso (o para preprocesar los datos mediante una implementación personalizada de `SqlDataReader`), use la sobrecarga del método `Send` que toma `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="fb285-152">To send the results of a query that was executed previously through the in-process provider (or to pre-process the data using a custom implementation of `SqlDataReader`), use the overload of the `Send` method that takes a `SqlDataReader`.</span></span> <span data-ttu-id="fb285-153">Este método es algo más lento que el método directo descrito anteriormente, pero ofrece mayor flexibilidad para manipular los datos antes de enviarlos al cliente.</span><span class="sxs-lookup"><span data-stu-id="fb285-153">This method is slightly slower than the direct method described previously, but it offers greater flexibility to manipulate the data before it is sent to the client.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the resulting reader to the client  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendReaderToClient()  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("select @@version", connection);  
         SqlDataReader r = command.ExecuteReader();  
         SqlContext.Pipe.Send(r);  
      }  
   }  
}  
```  
 
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendReaderToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="fb285-154">Para crear un conjunto de resultados dinámico, rellénelo y envíeselo al cliente; puede crear registros de la conexión actual y enviarlos mediante `SqlPipe.Send`.</span><span class="sxs-lookup"><span data-stu-id="fb285-154">To create a dynamic result set, populate it and send it to the client, you can create records from the current connection and send them using `SqlPipe.Send`.</span></span>  
  
```csharp  
using System.Data;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
using System.Data.SqlTypes;  
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Create a result set on the fly and send it to the client.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendTransientResultSet()  
   {  
      // Create a record object that represents an individual row, including it's metadata.  
      SqlDataRecord record = new SqlDataRecord(new SqlMetaData("stringcol", SqlDbType.NVarChar, 128));  
  
      // Populate the record.  
      record.SetSqlString(0, "Hello World!");  
  
      // Send the record to the client.  
      SqlContext.Pipe.Send(record);  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendTransientResultSet()  
        ' Create a record object that represents an individual row, including it's metadata.  
        Dim record As New SqlDataRecord(New SqlMetaData("stringcol", SqlDbType.NVarChar, 128) )  
  
        ' Populate the record.  
        record.SetSqlString(0, "Hello World!")  
  
        ' Send the record to the client.  
        SqlContext.Pipe.Send(record)          
    End Sub  
End Class   
```  
  
 <span data-ttu-id="fb285-155">A continuación se muestra un ejemplo del envío de un mensaje y un resultado tabular a través de `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="fb285-155">Here is an example of sending a tabular result and a message through `SqlPipe`.</span></span>  
  
```csharp  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void HelloWorld()  
   {  
      SqlContext.Pipe.Send("Hello world! It's now " + System.DateTime.Now.ToString()+"\n");  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT ProductNumber FROM ProductMaster", connection);  
         SqlDataReader reader = command.ExecuteReader();  
         SqlContext.Pipe.Send(reader);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub HelloWorld()  
        SqlContext.Pipe.Send("Hello world! It's now " & System.DateTime.Now.ToString() & "\n")  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT ProductNumber FROM ProductMaster", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class   
```  
  
 <span data-ttu-id="fb285-156">El primer `Send` envía un mensaje al cliente, mientras que el segundo envía un resultado tabular mediante `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="fb285-156">The first `Send` sends a message to the client, while the second sends a tabular result using `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="fb285-157">Tenga en cuenta que se trata de ejemplos meramente ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="fb285-157">Note that these examples are for illustrative purposes only.</span></span> <span data-ttu-id="fb285-158">Las funciones CLR resultan más apropiadas que las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] simples para las aplicaciones que requieren un uso intensivo de los recursos para realizar cálculos.</span><span class="sxs-lookup"><span data-stu-id="fb285-158">CLR functions are more appropriate than simple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for computation-intensive applications.</span></span> <span data-ttu-id="fb285-159">Un procedimiento almacenado [!INCLUDE[tsql](../../includes/tsql-md.md)] casi equivalente al ejemplo anterior es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb285-159">An almost equivalent [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure to the previous example is:</span></span>  
  
```sql
CREATE PROCEDURE HelloWorld() AS  
BEGIN  
PRINT('Hello world!')  
SELECT ProductNumber FROM ProductMaster  
END;  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fb285-160">Los mensajes y los conjuntos de resultados se recuperan de manera diferente en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="fb285-160">Messages and result sets are retrieved differently in the client application.</span></span> <span data-ttu-id="fb285-161">Por ejemplo, los [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] conjuntos de resultados aparecen en la vista **resultados** y los mensajes aparecen en el panel **mensajes** .</span><span class="sxs-lookup"><span data-stu-id="fb285-161">For instance, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] result sets appear in the **Results** view, and messages appear in the **Messages** pane.</span></span>  
  
 <span data-ttu-id="fb285-162">Si el código de Visual C# anterior se guarda en un archivo MyFirstUdp.cs y se compila con:</span><span class="sxs-lookup"><span data-stu-id="fb285-162">If the above Visual C# code is saved in a file MyFirstUdp.cs and compiled with:</span></span>  
  
```console
csc /t:library /out:MyFirstUdp.dll MyFirstUdp.cs   
```  
  
 <span data-ttu-id="fb285-163">O bien, si el código de Visual Basic anterior se guarda en un archivo MyFirstUdp.vb y se compila con:</span><span class="sxs-lookup"><span data-stu-id="fb285-163">Or, if the above Visual Basic code is saved in a file MyFirstUdp.vb and compiled with:</span></span>  
  
```console
vbc /t:library /out:MyFirstUdp.dll MyFirstUdp.vb   
```  
  
> [!NOTE]  
>  <span data-ttu-id="fb285-164">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], no se admiten la ejecución de objetos de base de datos de Visual C++ (como procedimientos almacenados) compilados con `/clr:pure`.</span><span class="sxs-lookup"><span data-stu-id="fb285-164">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], Visual C++ database objects (such as stored procedures) compiled with `/clr:pure` are not supported for execution.</span></span>  
  
 <span data-ttu-id="fb285-165">Es posible registrar el ensamblado resultante y el punto de entrada invocado con el siguiente DDL:</span><span class="sxs-lookup"><span data-stu-id="fb285-165">The resulting assembly can be registered, and the entry point invoked, with the following DDL:</span></span>  
  
```sql
CREATE ASSEMBLY MyFirstUdp FROM 'C:\Programming\MyFirstUdp.dll';  
CREATE PROCEDURE HelloWorld  
AS EXTERNAL NAME MyFirstUdp.StoredProcedures.HelloWorld;  
EXEC HelloWorld;  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb285-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb285-166">See Also</span></span>  
 <span data-ttu-id="fb285-167">[Funciones definidas por el usuario de CLR](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="fb285-167">[CLR User-Defined Functions](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="fb285-168">[Tipos definidos por el usuario CLR](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="fb285-168">[CLR User-Defined Types](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 [<span data-ttu-id="fb285-169">Desencadenadores de CLR</span><span class="sxs-lookup"><span data-stu-id="fb285-169">CLR Triggers</span></span>](../../../2014/database-engine/dev-guide/clr-triggers.md)  
  
  
