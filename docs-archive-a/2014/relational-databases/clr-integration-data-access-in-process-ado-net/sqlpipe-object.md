---
title: SqlPipe (objeto) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- custom result sets [CLR integration]
- SqlPipe object
- tabular results
ms.assetid: 3e090faf-085f-4c01-a565-79e3f1c36e3b
author: rothja
ms.author: jroth
ms.openlocfilehash: 0044815a0b20d72b48b87bfe8f693d7196aaeaf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674160"
---
# <a name="sqlpipe-object"></a><span data-ttu-id="8c29d-102">SqlPipe, objetos</span><span class="sxs-lookup"><span data-stu-id="8c29d-102">SqlPipe Object</span></span>
  <span data-ttu-id="8c29d-103">En versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]es muy común escribir un procedimiento almacenado (o un procedimiento almacenado extendido) que envía resultados o parámetros de salida al cliente que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c29d-103">In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is very common to write a stored procedure (or an extended stored procedure) that sends results or output parameters to the calling client.</span></span>  
  
 <span data-ttu-id="8c29d-104">En un procedimiento almacenado de [!INCLUDE[tsql](../../includes/tsql-md.md)], cualquier instrucción `SELECT` que devuelve cero o más filas envía los resultados a la "canalización" del autor de la llamada conectado.</span><span class="sxs-lookup"><span data-stu-id="8c29d-104">In a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, any `SELECT` statement that returns zero or more rows sends the results to the connected caller's "pipe."</span></span>  
  
 <span data-ttu-id="8c29d-105">En los objetos de base de datos de Common Language Runtime (CLR) que se ejecutan en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede enviar los resultados a la canalización conectada mediante los métodos `Send` del objeto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-105">For common language runtime (CLR) database objects running in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can send results to the connected pipe using the `Send` methods of the `SqlPipe` object.</span></span> <span data-ttu-id="8c29d-106">Para obtener el objeto `Pipe`, debe obtener acceso a la propiedad `SqlContext` del objeto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-106">Access the `Pipe` property of the `SqlContext` object to obtain the `SqlPipe` object.</span></span> <span data-ttu-id="8c29d-107">La clase `SqlPipe` es conceptualmente similar a la clase `Response` incluida en ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8c29d-107">The `SqlPipe` class is conceptually similar to the `Response` class found in ASP.NET.</span></span> <span data-ttu-id="8c29d-108">Para obtener más información, vea la documentación de referencia de la clase SqlPipe en el kit de desarrollo de software de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c29d-108">For more information, see the SqlPipe Class reference documentation in the .NET Framework software development kit.</span></span>  
  
## <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="8c29d-109">Devolver mensajes y resultados tabulares</span><span class="sxs-lookup"><span data-stu-id="8c29d-109">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="8c29d-110">`SqlPipe` incluye un método `Send`, que cuenta con tres sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8c29d-110">The `SqlPipe` has a `Send` method, which has three overloads.</span></span> <span data-ttu-id="8c29d-111">Son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c29d-111">They are:</span></span>  
  
-   `void Send(string message)`  
  
-   `void Send(SqlDataReader reader)`  
  
-   `void Send(SqlDataRecord record)`  
  
 <span data-ttu-id="8c29d-112">El método `Send` envía los datos directamente al cliente o autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c29d-112">The `Send` method sends data straight to the client or caller.</span></span> <span data-ttu-id="8c29d-113">Generalmente es el cliente el que consume los resultados del método `SqlPipe`, pero en el caso de procedimientos almacenados de CLR anidados, el consumidor de los resultados también puede ser un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="8c29d-113">It is usually the client that consumes the output from the `SqlPipe`, but in the case of nested CLR stored procedures the output consumer can also be a stored procedure.</span></span> <span data-ttu-id="8c29d-114">Por ejemplo, Procedure1 llama a SqlCommand.ExecuteReader() con el texto de comando "EXEC Procedure2".</span><span class="sxs-lookup"><span data-stu-id="8c29d-114">For example, Procedure1 calls SqlCommand.ExecuteReader() with the command text "EXEC Procedure2".</span></span> <span data-ttu-id="8c29d-115">Procedure2 también es un procedimiento almacenado administrado.</span><span class="sxs-lookup"><span data-stu-id="8c29d-115">Procedure2 is also a managed stored procedure.</span></span> <span data-ttu-id="8c29d-116">Si Procedure2 llama ahora a SqlPipe.Send( SqlDataRecord ), la fila se envía al lector de Procedure1, no al cliente.</span><span class="sxs-lookup"><span data-stu-id="8c29d-116">If Procedure2 now calls SqlPipe.Send( SqlDataRecord ), the row is sent to Procedure1's reader, not the client.</span></span>  
  
 <span data-ttu-id="8c29d-117">El método `Send` envía un mensaje de cadena que aparece en el cliente como un mensaje de información, equivalente a PRINT en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c29d-117">The `Send` method sends a string message that appears on the client as an information message, equivalent to PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8c29d-118">También puede enviar un conjunto de resultados de fila única mediante `SqlDataRecord`o un conjunto de resultados de varias filas mediante `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-118">It can also send a single-row result-set using `SqlDataRecord`, or a multi-row result-set using a `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="8c29d-119">El objeto `SqlPipe` también incluye un método `ExecuteAndSend`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-119">The `SqlPipe` object also has an `ExecuteAndSend` method.</span></span> <span data-ttu-id="8c29d-120">Este método se puede utilizar para ejecutar un comando (se pasa como objeto `SqlCommand` ) y devolver directamente los resultados al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c29d-120">This method can be used to execute a command (passed as a `SqlCommand` object) and send results directly back to the caller.</span></span> <span data-ttu-id="8c29d-121">Si existen errores en el comando enviado, las excepciones se envían a la canalización, pero también se envía una copia al código administrado que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c29d-121">If there are errors in the command that was submitted, exceptions are sent to the pipe, but a copy is also sent to calling managed code.</span></span> <span data-ttu-id="8c29d-122">Si el código de llamada no detecta la excepción, propaga la pila al código de [!INCLUDE[tsql](../../includes/tsql-md.md)] y aparece dos veces en el resultado.</span><span class="sxs-lookup"><span data-stu-id="8c29d-122">If the calling code does not catch the exception, it propagates up the stack to the [!INCLUDE[tsql](../../includes/tsql-md.md)] code and appears in the output twice.</span></span> <span data-ttu-id="8c29d-123">Si el código de llamada sí detecta la excepción, el consumidor de la canalización aún ve el error, pero no hay errores duplicados.</span><span class="sxs-lookup"><span data-stu-id="8c29d-123">If the calling code does catch the exception, the pipe consumer still sees the error, but there is not a duplicate error.</span></span>  
  
 <span data-ttu-id="8c29d-124">Puede tomar solamente un `SqlCommand` asociado a la conexión contextual; no puede tomar ningún comando asociado a la conexión no contextual.</span><span class="sxs-lookup"><span data-stu-id="8c29d-124">It can only take a `SqlCommand` that is associated with the context connection; it cannot take a command that is associated with the non-context connection.</span></span>  
  
## <a name="returning-custom-result-sets"></a><span data-ttu-id="8c29d-125">Devolver conjuntos de resultados personalizados</span><span class="sxs-lookup"><span data-stu-id="8c29d-125">Returning Custom Result Sets</span></span>  
 <span data-ttu-id="8c29d-126">Los procedimientos almacenados administrados pueden enviar conjuntos de resultados que no proceden de `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-126">Managed stored procedures can send result sets that do not come from a `SqlDataReader`.</span></span> <span data-ttu-id="8c29d-127">El método `SendResultsStart`, junto con `SendResultsRow` y `SendResultsEnd`, permite a los procedimientos almacenados enviar conjuntos de resultados personalizados al cliente.</span><span class="sxs-lookup"><span data-stu-id="8c29d-127">The `SendResultsStart` method, along with `SendResultsRow` and `SendResultsEnd`, allows stored procedures to send custom result sets to the client.</span></span>  
  
 <span data-ttu-id="8c29d-128">`SendResultsStart` toma como entrada un `SqlDataRecord`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-128">`SendResultsStart` takes a `SqlDataRecord` as an input.</span></span> <span data-ttu-id="8c29d-129">Este método marca el principio de un conjunto de resultados y utiliza los metadatos del registro para generar los metadatos que describen el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="8c29d-129">It marks the beginning of a result set and uses the record metadata to construct the metadata that describes the result set.</span></span> <span data-ttu-id="8c29d-130">No envía el valor del registro con `SendResultsStart`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-130">It does not send the value of the record with `SendResultsStart`.</span></span> <span data-ttu-id="8c29d-131">Todas las filas subsiguientes, enviadas mediante el método `SendResultsRow`, deben coincidir con la definición de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8c29d-131">All the subsequent rows, sent using `SendResultsRow`, must match that metadata definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c29d-132">Después de llamar al método `SendResultsStart`, solo se puede llamar a `SendResultsRow` y `SendResultsEnd`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-132">After calling the `SendResultsStart` method only `SendResultsRow` and `SendResultsEnd` can be called.</span></span> <span data-ttu-id="8c29d-133">La llamada a cualquier otro método en la misma instancia de `SqlPipe` produce una excepción `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="8c29d-133">Calling any other method in the same instance of `SqlPipe` causes an `InvalidOperationException`.</span></span> <span data-ttu-id="8c29d-134">`SendResultsEnd` devuelve `SqlPipe` al estado inicial con el que se puede llamar a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="8c29d-134">`SendResultsEnd` sets `SqlPipe` back to the initial state in which other methods can be called.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8c29d-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c29d-135">Example</span></span>  
 <span data-ttu-id="8c29d-136">El procedimiento almacenado `uspGetProductLine` devuelve el nombre, el número de producto, el color y el precio de todos los productos de una línea de productos especificada.</span><span class="sxs-lookup"><span data-stu-id="8c29d-136">The `uspGetProductLine` stored procedure returns the name, product number, color, and list price of all products within a specified product line.</span></span> <span data-ttu-id="8c29d-137">Este procedimiento almacenado acepta coincidencias exactas de *prodLine*.</span><span class="sxs-lookup"><span data-stu-id="8c29d-137">This stored procedure accepts exact matches for *prodLine*.</span></span>  
  
 <span data-ttu-id="8c29d-138">C#</span><span class="sxs-lookup"><span data-stu-id="8c29d-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspGetProductLine(SqlString prodLine)  
{  
    // Connect through the context connection.  
    using (SqlConnection connection = new SqlConnection("context connection=true"))  
    {  
        connection.Open();  
  
        SqlCommand command = new SqlCommand(  
            "SELECT Name, ProductNumber, Color, ListPrice " +  
            "FROM Production.Product " +   
            "WHERE ProductLine = @prodLine;", connection);  
  
        command.Parameters.AddWithValue("@prodLine", prodLine);  
  
        try  
        {  
            // Execute the command and send the results to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command);  
        }  
        catch (System.Data.SqlClient.SqlException ex)  
        {  
            // An error occurred executing the SQL command.  
        }  
     }  
}  
};  
```  
  
 <span data-ttu-id="8c29d-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c29d-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub uspGetProductLine(ByVal prodLine As SqlString)  
    Dim command As SqlCommand  
  
    ' Connect through the context connection.  
    Using connection As New SqlConnection("context connection=true")  
        connection.Open()  
  
        command = New SqlCommand( _  
        "SELECT Name, ProductNumber, Color, ListPrice " & _  
        "FROM Production.Product " & _  
        "WHERE ProductLine = @prodLine;", connection)  
        command.Parameters.AddWithValue("@prodLine", prodLine)  
  
        Try  
            ' Execute the command and send the results   
            ' directly to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command)  
        Catch ex As System.Data.SqlClient.SqlException  
            ' An error occurred executing the SQL command.  
        End Try  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="8c29d-140">La siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] ejecuta el procedimiento `uspGetProduct`, que devuelve una lista de productos de bicicleta de paseo.</span><span class="sxs-lookup"><span data-stu-id="8c29d-140">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement executes the `uspGetProduct` procedure, which returns a list of touring bike products.</span></span>  
  
```  
EXEC uspGetProductLineVB 'T';  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c29d-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c29d-141">See Also</span></span>  
 <span data-ttu-id="8c29d-142">[Objeto SqlDataRecord](sqldatarecord-object.md) </span><span class="sxs-lookup"><span data-stu-id="8c29d-142">[SqlDataRecord Object](sqldatarecord-object.md) </span></span>  
 <span data-ttu-id="8c29d-143">[Procedimientos almacenados CLR](../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8c29d-143">[CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="8c29d-144">Extensiones específicas en proceso de SQL Server a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8c29d-144">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
