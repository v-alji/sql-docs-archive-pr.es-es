---
title: Funciones escalares de CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- SVF
- scalar-valued functions
ms.assetid: 20dcf802-c27d-4722-9cd3-206b1e77bee0
author: rothja
ms.author: jroth
ms.openlocfilehash: be8f9616fb285d6a68d6734924874ded06fb3bd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745333"
---
# <a name="clr-scalar-valued-functions"></a><span data-ttu-id="c8648-102">Funciones escalares de CLR</span><span class="sxs-lookup"><span data-stu-id="c8648-102">CLR Scalar-Valued Functions</span></span>
  <span data-ttu-id="c8648-103">Una función escalar (SVF) devuelve un único valor, como un valor de cadena, entero o de bit. Puede crear funciones escalares definidas por el usuario en código administrado mediante cualquier lenguaje de programación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8648-103">A scalar-valued function (SVF) returns a single value, such as a string, integer, or bit value.You can create scalar-valued user-defined functions in managed code using any .NET Framework programming language.</span></span> <span data-ttu-id="c8648-104">Estas funciones son accesibles para [!INCLUDE[tsql](../../includes/tsql-md.md)] u otro código administrado.</span><span class="sxs-lookup"><span data-stu-id="c8648-104">These functions are accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span> <span data-ttu-id="c8648-105">Para obtener información sobre las ventajas de la integración CLR y la elección entre código administrado y [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte [información general sobre la integración CLR](../clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c8648-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-scalar-valued-functions"></a><span data-ttu-id="c8648-106">Requisitos de las funciones escalares de CLR</span><span class="sxs-lookup"><span data-stu-id="c8648-106">Requirements for CLR Scalar-Valued Functions</span></span>  
 <span data-ttu-id="c8648-107">Las SVF de .NET Framework se implementan como métodos en una clase de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8648-107">.NET Framework SVFs are implemented as methods on a class in a .NET Framework assembly.</span></span> <span data-ttu-id="c8648-108">Los parámetros de entrada y el tipo devueltos por SVF pueden ser cualquiera de los tipos de datos escalares admitidos por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , excepto `varchar` , `char` , `rowversion` , `text` , `ntext` , `image` , `timestamp` , `table` o `cursor` .</span><span class="sxs-lookup"><span data-stu-id="c8648-108">The input parameters and the type returned from a SVF can be any of the scalar data types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except `varchar`, `char`, `rowversion`, `text`, `ntext`, `image`, `timestamp`, `table`, or `cursor`.</span></span> <span data-ttu-id="c8648-109">Las SVF deben asegurar una coincidencia entre el tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el tipo de datos de retorno del método de implementación.</span><span class="sxs-lookup"><span data-stu-id="c8648-109">SVFs must ensure a match between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type and the return data type of the implementation method.</span></span> <span data-ttu-id="c8648-110">Para obtener más información sobre las conversiones de tipos, vea [asignar datos de parámetros CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="c8648-110">For more information about type conversions, see [Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
 <span data-ttu-id="c8648-111">Al implementar una SVF de .NET Framework SVF en un lenguaje .NET Framework, el atributo personalizado `SqlFunction` se puede especificar para incluir la información adicional de la función.</span><span class="sxs-lookup"><span data-stu-id="c8648-111">When implementing a .NET Framework SVF in a .NET Framework language, the `SqlFunction` custom attribute can be specified to include additional information about the function.</span></span> <span data-ttu-id="c8648-112">El atributo `SqlFunction` indica tanto si la función obtiene acceso o modifica los datos como si no, si es determinista y si la función implica las operaciones de coma flotante.</span><span class="sxs-lookup"><span data-stu-id="c8648-112">The `SqlFunction` attribute indicates whether or not the function accesses or modifies data, if it is deterministic, and if the function involves floating point operations.</span></span>  
  
 <span data-ttu-id="c8648-113">Las funciones escalares definidas por el usuario pueden ser deterministas o no deterministas.</span><span class="sxs-lookup"><span data-stu-id="c8648-113">Scalar-valued user-defined functions may be deterministic or non-deterministic.</span></span> <span data-ttu-id="c8648-114">Una función determinista siempre devuelve el mismo resultado cuando se llama con un conjunto concreto de parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="c8648-114">A deterministic function always returns the same result when it is called with a specific set of input parameters.</span></span> <span data-ttu-id="c8648-115">Una función no determinista puede devolver resultados distintos cuando se llama con un conjunto concreto de parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="c8648-115">A non-deterministic function may return different results when it is called with a specific set of input parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8648-116">No marque una función como determinista si ésta no siempre genera los mismos valores de salida, dados los mismos valores de entrada y el mismo estado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c8648-116">Do not mark a function as deterministic if the function does not always produces the same output values, given the same input values and the same database state.</span></span> <span data-ttu-id="c8648-117">Al marcar una función como determinista cuando la función no es verdaderamente determinista puede producir vistas indizadas dañadas y columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="c8648-117">Marking a function as deterministic, when the function isn't truly deterministic can result in corrupted indexed views and computed columns.</span></span> <span data-ttu-id="c8648-118">Marque una función como determinista estableciendo la propiedad `IsDeterministic` en true.</span><span class="sxs-lookup"><span data-stu-id="c8648-118">You mark a function as deterministic by setting the `IsDeterministic` property to true.</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="c8648-119">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="c8648-119">Table-Valued Parameters</span></span>  
 <span data-ttu-id="c8648-120">Los parámetros con valores de tabla (TVP), tipos de tabla definidos por el usuario que se pasan a un procedimiento o función, proporcionan un modo eficaz de pasar varias filas de datos al servidor.</span><span class="sxs-lookup"><span data-stu-id="c8648-120">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="c8648-121">Los TVP presentan una funcionalidad similar a las matrices de parámetros, pero proporcionan más flexibilidad y una mayor integración con [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8648-121">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c8648-122">También proporcionan la posibilidad de obtener mayor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c8648-122">They also provide the potential for better performance.</span></span> <span data-ttu-id="c8648-123">Además, los TVP ayudan a reducir el número de ciclos de ida y vuelta al servidor.</span><span class="sxs-lookup"><span data-stu-id="c8648-123">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="c8648-124">En lugar de enviar varias solicitudes al servidor, como con una lista de parámetros escalares, los datos pueden enviarse al servidor como un TVP.</span><span class="sxs-lookup"><span data-stu-id="c8648-124">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="c8648-125">Un tipo de tabla definido por el usuario no puede pasarse como un parámetro con valores de tabla a un procedimiento almacenado administrado o a una función que se ejecuta en el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , así como tampoco puede devolverse desde dicho procedimiento o función.</span><span class="sxs-lookup"><span data-stu-id="c8648-125">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="c8648-126">Para obtener más información sobre TVP, vea [usar parámetros con valores de tabla &#40;Motor de base de datos&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c8648-126">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="example-of-a-clr-scalar-valued-function"></a><span data-ttu-id="c8648-127">Ejemplo de una función escalar de CLR</span><span class="sxs-lookup"><span data-stu-id="c8648-127">Example of a CLR Scalar-Valued Function</span></span>  
 <span data-ttu-id="c8648-128">A continuación se muestra una SVF simple que tiene acceso a datos y devuelve un valor entero:</span><span class="sxs-lookup"><span data-stu-id="c8648-128">Here is a simple SVF that accesses data and returns an integer value:</span></span>  
  
```csharp  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public class T  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static int ReturnOrderCount()  
    {  
        using (SqlConnection conn   
            = new SqlConnection("context connection=true"))  
        {  
            conn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
            return (int)cmd.ExecuteScalar();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public Class T  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReturnOrderCount() As Integer  
        Using conn As New SqlConnection("context connection=true")  
            conn.Open()  
            Dim cmd As New SqlCommand("SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
            Return CType(cmd.ExecuteScalar(), Integer)  
        End Using  
    End Function  
End Class  
```  
  
 <span data-ttu-id="c8648-129">La primera línea de código hace referencia a `Microsoft.SqlServer.Server` para tener acceso a los atributos y a `System.Data.SqlClient` para tener acceso al espacio de nombres de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c8648-129">The first line of code references `Microsoft.SqlServer.Server` to access attributes and `System.Data.SqlClient` to access the ADO.NET namespace.</span></span> <span data-ttu-id="c8648-130">(Este espacio de nombres contiene `SqlClient`, el proveedor de datos de .NET Framework para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="c8648-130">(This namespace contains `SqlClient`, the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="c8648-131">Después, la función recibe el atributo personalizado `SqlFunction`, que se encuentra en el espacio de nombres `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="c8648-131">Next, the function receives the `SqlFunction` custom attribute, which is found in the `Microsoft.SqlServer.Server` namespace.</span></span> <span data-ttu-id="c8648-132">El atributo personalizado indica si la función definida por el usuario (UDF) utiliza o no el proveedor en proceso para leer los datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c8648-132">The custom attribute indicates whether or not the user-defined function (UDF) uses the in-process provider to read data in the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c8648-133">no permite a las UDF actualizar, insertar o eliminar datos.</span><span class="sxs-lookup"><span data-stu-id="c8648-133">does not allow UDFs to update, insert, or delete data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c8648-134">puede optimizar la ejecución de una UDF que no usa el proveedor en proceso.</span><span class="sxs-lookup"><span data-stu-id="c8648-134">can optimize execution of a UDF that does not use the in-process provider.</span></span> <span data-ttu-id="c8648-135">Esto se indica estableciendo `DataAccessKind` en `DataAccessKind.None`.</span><span class="sxs-lookup"><span data-stu-id="c8648-135">This is indicated by setting `DataAccessKind` to `DataAccessKind.None`.</span></span> <span data-ttu-id="c8648-136">En la línea siguiente, el método de destino es una estática pública (se comparte en Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="c8648-136">On the next line, the target method is a public static (shared in Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="c8648-137">La clase `SqlContext`, ubicada en el espacio de nombres `Microsoft.SqlServer.Server`, puede tener acceso a un objeto `SqlCommand` con una conexión a la instancia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ya está establecida.</span><span class="sxs-lookup"><span data-stu-id="c8648-137">The `SqlContext` class, located in the `Microsoft.SqlServer.Server` namespace, can then access a `SqlCommand` object with a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is already set up.</span></span> <span data-ttu-id="c8648-138">Aunque no se usa aquí, el contexto de transacción actual también está disponible a través de la interfaz de programación de aplicaciones (API) `System.Transactions`.</span><span class="sxs-lookup"><span data-stu-id="c8648-138">Although not used here, the current transaction context is also available through the `System.Transactions` application programming interface (API).</span></span>  
  
 <span data-ttu-id="c8648-139">Los desarrolladores que han escrito las aplicaciones cliente que usan los tipos situados en el espacio de nombres `System.Data.SqlClient`, deberían estar familiarizados con la mayoría de las líneas de código en el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="c8648-139">Most of the lines of code in the function body should look familiar to developers who have written client applications that use the types found in the `System.Data.SqlClient` namespace.</span></span>  
  
 <span data-ttu-id="c8648-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="c8648-140">[C#]</span></span>  
  
```  
using(SqlConnection conn = new SqlConnection("context connection=true"))   
{  
   conn.Open();  
   SqlCommand cmd = new SqlCommand(  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
   return (int) cmd.ExecuteScalar();  
}    
```  
  
 <span data-ttu-id="c8648-141">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="c8648-141">[Visual Basic]</span></span>  
  
```  
Using conn As New SqlConnection("context connection=true")  
   conn.Open()  
   Dim cmd As New SqlCommand( _  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
   Return CType(cmd.ExecuteScalar(), Integer)  
End Using  
```  
  
 <span data-ttu-id="c8648-142">El texto de comando adecuado se especifica inicializando el objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="c8648-142">The appropriate command text is specified by initializing the `SqlCommand` object.</span></span> <span data-ttu-id="c8648-143">En el ejemplo anterior se cuenta el número de filas en la tabla `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="c8648-143">The previous example counts the number of rows in table `SalesOrderHeader`.</span></span> <span data-ttu-id="c8648-144">Después, se llama al método `ExecuteScalar` del objeto `cmd`.</span><span class="sxs-lookup"><span data-stu-id="c8648-144">Next, the `ExecuteScalar` method of the `cmd` object is called.</span></span> <span data-ttu-id="c8648-145">Esto devuelve un valor de tipo `int` basado en la consulta.</span><span class="sxs-lookup"><span data-stu-id="c8648-145">This returns a value of type `int` based on the query.</span></span> <span data-ttu-id="c8648-146">Por último, se devuelve Order Count al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c8648-146">Finally, the order count is returned to the caller.</span></span>  
  
 <span data-ttu-id="c8648-147">Si este código se guarda en un archivo denominado FirstUdf.cs, puede estar compilado en un ensamblado como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="c8648-147">If this code is saved in a file called FirstUdf.cs, it could be compiled into as assembly as follows:</span></span>  
  
 <span data-ttu-id="c8648-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="c8648-148">[C#]</span></span>  
  
```  
csc.exe /t:library /out:FirstUdf.dll FirstUdf.cs   
```  
  
 <span data-ttu-id="c8648-149">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="c8648-149">[Visual Basic]</span></span>  
  
```  
vbc.exe /t:library /out:FirstUdf.dll FirstUdf.vb  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c8648-150">`/t:library` indica que se debe generar una biblioteca, en lugar de un ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c8648-150">`/t:library` indicates that a library, rather than an executable, should be produced.</span></span> <span data-ttu-id="c8648-151">Los ejecutables no se pueden registrar en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8648-151">Executables cannot be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8648-152">Los objetos de base de datos de Visual C++ compilados con `/clr:pure` no se admiten para la ejecución en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8648-152">Visual C++ database objects compiled with `/clr:pure` are not supported for execution on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c8648-153">Por ejemplo, esos objetos de base de datos incluyen funciones escalares.</span><span class="sxs-lookup"><span data-stu-id="c8648-153">For example, such database objects include scalar-valued functions.</span></span>  
  
 <span data-ttu-id="c8648-154">La consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] y una invocación de ejemplo para registrar el ensamblado y una UDF son:</span><span class="sxs-lookup"><span data-stu-id="c8648-154">The [!INCLUDE[tsql](../../includes/tsql-md.md)] query and a sample invocation to register the assembly and UDF are:</span></span>  
  
```  
CREATE ASSEMBLY FirstUdf FROM 'FirstUdf.dll';  
GO  
  
CREATE FUNCTION CountSalesOrderHeader() RETURNS INT   
AS EXTERNAL NAME FirstUdf.T.ReturnOrderCount;   
GO  
  
SELECT dbo.CountSalesOrderHeader();  
GO  
  
```  
  
 <span data-ttu-id="c8648-155">Observe que el nombre de función expuesto en [!INCLUDE[tsql](../../includes/tsql-md.md)] no necesita coincidir con el nombre del método estático público de destino.</span><span class="sxs-lookup"><span data-stu-id="c8648-155">Note that the function name as exposed in [!INCLUDE[tsql](../../includes/tsql-md.md)] does not need to match the name of the target public static method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8648-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8648-156">See Also</span></span>  
 <span data-ttu-id="c8648-157">[Asignar datos de parámetros CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span><span class="sxs-lookup"><span data-stu-id="c8648-157">[Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span></span>  
 <span data-ttu-id="c8648-158">[Información general sobre los atributos personalizados de la integración CLR](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="c8648-158">[Overview of CLR Integration Custom Attributes](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span></span>  
 <span data-ttu-id="c8648-159">[Funciones definidas por el usuario](../user-defined-functions/user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="c8648-159">[User-Defined Functions](../user-defined-functions/user-defined-functions.md) </span></span>  
 [<span data-ttu-id="c8648-160">Acceso a datos de objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="c8648-160">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
