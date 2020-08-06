---
title: Ejemplo de acceso a datos en proceso | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 155be272-4f9a-4d86-9f4f-714c4f45b49a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 62201474be26abdc5fe6e8f470b4896d51b9b106
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751398"
---
# <a name="in-process-data-access-sample"></a><span data-ttu-id="9a009-102">Ejemplo de acceso a datos en proceso</span><span class="sxs-lookup"><span data-stu-id="9a009-102">In-Process Data Access Sample</span></span>
  <span data-ttu-id="9a009-103">El ejemplo `InProcessDataAccess` contiene una serie de funciones simples que muestran diversas características del proveedor de acceso a datos en proceso de CLR de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a009-103">The `InProcessDataAccess` sample contains a number of simple functions that demonstrate various features of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CLR in-process data access provider.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a009-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9a009-104">Prerequisites</span></span>  
 <span data-ttu-id="9a009-105">Para crear y ejecutar este proyecto se debe instalar el siguiente software:</span><span class="sxs-lookup"><span data-stu-id="9a009-105">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9a009-106">o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="9a009-106">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="9a009-107">Puede obtener [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express de forma gratuita desde el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sitio web [de documentación y ejemplos de](https://www.microsoft.com/sql-server/sql-server-editions-express)Express.</span><span class="sxs-lookup"><span data-stu-id="9a009-107">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="9a009-108">La base de datos de AdventureWorks que está disponible en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sitio web [para desarrolladores de](https://go.microsoft.com/fwlink/?linkid=62796).</span><span class="sxs-lookup"><span data-stu-id="9a009-108">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="9a009-109">.NET Framework SDK 2.0 o posterior, o Microsoft Visual Studio 2005 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9a009-109">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="9a009-110">Puede obtener .NET Framework SDK de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="9a009-110">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="9a009-111">Además, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="9a009-111">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="9a009-112">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está usando debe tener habilitada la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="9a009-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="9a009-113">Para habilitar la integración con CLR, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9a009-113">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="9a009-114">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="9a009-114">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="9a009-115">Ejecute los siguientes comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9a009-115">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a009-116">Para habilitar CLR, debe tener el permiso de nivel de servidor `ALTER SETTINGS`, que se concede implícitamente a los miembros de los roles fijos de servidor `sysadmin` y `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="9a009-116">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="9a009-117">La base de datos de AdventureWorks debe estar instalada en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está usando.</span><span class="sxs-lookup"><span data-stu-id="9a009-117">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="9a009-118">Si no es administrador de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está utilizando, debe hacer que un administrador le conceda el permiso **CreateAssembly** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="9a009-118">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="9a009-119">Generar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a009-119">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="9a009-120">Cree y ejecute el ejemplo utilizando las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="9a009-120">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="9a009-121">Abra un símbolo del sistema de Visual Studio o de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a009-121">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="9a009-122">Si es necesario, cree un directorio para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9a009-122">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="9a009-123">Para este ejemplo, utilizaremos C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="9a009-123">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="9a009-124">En c:\MySample, cree `inprocda.vb` (para el ejemplo de Visual Basic) o `inprocda.cs` (para el ejemplo de C#) y copie el código muestra de Visual Basic o de C# que corresponda (más abajo) en el archivo.</span><span class="sxs-lookup"><span data-stu-id="9a009-124">In c:\MySample, create `inprocda.vb` (for the Visual Basic sample) or `inprocda.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="9a009-125">Compile el código muestra en el ensamblado requerido ejecutando en el símbolo del sistema uno de los comandos siguientes, dependiendo de su opción de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9a009-125">Compile the sample code into the required assembly from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /target:library InProcDA.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.XML.dll /target:library inprocda.cs`  
  
5.  <span data-ttu-id="9a009-126">Copie el código de instalación de [!INCLUDE[tsql](../../includes/tsql-md.md)] en un archivo y guárdelo como `Install.sql` en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9a009-126">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="9a009-127">Si el ejemplo está instalado en un directorio distinto de `C:\MySample\`, edite el archivo `Install.sql` del archivo como se indica para señalar esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="9a009-127">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
7.  <span data-ttu-id="9a009-128">Implemente el ensamblado, el procedimiento almacenado y las funciones ejecutando</span><span class="sxs-lookup"><span data-stu-id="9a009-128">Deploy the assembly, stored procedure and functions by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
8.  <span data-ttu-id="9a009-129">Copie el código de instalación de [!INCLUDE[tsql](../../includes/tsql-md.md)] en un archivo y guárdelo como `test.sql` en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9a009-129">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `test.sql` in the sample directory.</span></span>  
  
9. <span data-ttu-id="9a009-130">Pruebe la aplicación ejecutando la siguiente línea en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="9a009-130">Test the application by executing the following line at the command prompt:</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
10. <span data-ttu-id="9a009-131">Copie el script de limpieza de [!INCLUDE[tsql](../../includes/tsql-md.md)] en un archivo y guárdelo como `cleanup.sql` en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9a009-131">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
11. <span data-ttu-id="9a009-132">Ejecute el script con el siguiente comando</span><span class="sxs-lookup"><span data-stu-id="9a009-132">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="9a009-133">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a009-133">Sample Code</span></span>  
 <span data-ttu-id="9a009-134">A continuación se muestran las listas de código para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9a009-134">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="9a009-135">C#</span><span class="sxs-lookup"><span data-stu-id="9a009-135">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
public sealed class DataAccessDemo  
{  
        private DataAccessDemo()  
        {  
        }  
  
        /// <summary>  
/// Simple example to send a message to the client.  
/// </summary>  
public static void SendMessage(string msg)  
{  
SqlContext.Pipe.Send("Message from server: " + msg);  
}  
  
/// <summary>  
/// Simple example of performing data access within  
/// a function  
/// </summary>  
/// <returns></returns>  
        [Microsoft.SqlServer.Server.SqlFunction(DataAccess = Microsoft.SqlServer.Server.DataAccessKind.Read)]  
public static string ReportSqlVersion()  
{  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
                //create a command from the current context  
                SqlCommand cmd = conn.CreateCommand();  
  
                //execute something  
                cmd.CommandText = "select @@version";  
  
                conn.Open();  
                //return results as scalar  
                return (string)cmd.ExecuteScalar();  
            }  
}  
  
/// <summary>  
/// Create a result set on the fly and send it to the client.  
/// </summary>  
public static void SendTransientResultSet()  
{  
//create the metadata for the columns  
            Microsoft.SqlServer.Server.SqlMetaData[] columnSchema   
                = new Microsoft.SqlServer.Server.SqlMetaData[] {  
new Microsoft.SqlServer.Server.SqlMetaData("stringcol", SqlDbType.NVarChar, 128)  
};  
  
//create a record based on that metadata  
            SqlDataRecord newRecord = new SqlDataRecord(columnSchema);  
  
//populate it  
newRecord.SetString(0, "Hello World!");  
  
//send it  
SqlContext.Pipe.Send(newRecord);  
}  
  
/// <summary>  
/// Execute a command and send the results to the client directly.  
/// </summary>  
public static void ExecuteToClient()  
{  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
                SqlCommand cmd = conn.CreateCommand();  
  
                cmd.CommandText = "select @@version";  
                conn.Open();  
                SqlContext.Pipe.ExecuteAndSend(cmd);  
            }  
}  
  
/// <summary>  
/// Execute a command and send the resultig reader to the client  
/// </summary>  
public static void SendReaderToClient()  
{  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
                SqlCommand cmd = conn.CreateCommand();  
  
                cmd.CommandText = "select @@version";  
                conn.Open();  
                SqlDataReader rdr = cmd.ExecuteReader();  
                try  
                {  
                    SqlContext.Pipe.Send(rdr);  
                }  
                finally  
                {  
                    rdr.Close();  
                }  
            }  
}  
  
};  
```  
  
 <span data-ttu-id="9a009-136">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a009-136">Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Server  
Imports Microsoft.VisualBasic  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Diagnostics  
Partial Public NotInheritable Class DataAccessDemo  
    Private Sub New()  
    End Sub  
  
    ''' <summary>  
    ''' Simple example of performing data access within a function  
    ''' </summary>  
    ''' <returns></returns>  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReportSqlVersion() As SqlString  
        Using conn As New SqlConnection("context connection=true")  
            'create a command from the current context  
            Dim cmd As SqlCommand = conn.CreateCommand()  
  
            'execute something  
            cmd.CommandText = "SELECT @@VERSION"  
  
            conn.Open()  
  
            'return results as scalar  
            Return CType(cmd.ExecuteScalar(), String)  
        End Using  
    End Function  
  
    ''' <summary>  
    ''' Simple example to send a message to the client.  
    ''' </summary>  
    Public Shared Sub SendMessage(ByVal msg As String)  
        SqlContext.Pipe.Send(("Message from server: " & msg))  
    End Sub  
  
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    Public Shared Sub SendTransientResultSet()  
        'create the metadata for the columns  
        Dim columnSchema() As Microsoft.SqlServer.Server.SqlMetaData _  
            = {New SqlMetaData("stringcol", SqlDbType.NVarChar, 128)}  
  
        'create a record based on that metadata  
        Dim newRecord As New SqlDataRecord(columnSchema)  
  
        'populate it  
        newRecord.SetString(0, "Hello World!")  
  
        'send it  
        SqlContext.Pipe.Send(newRecord)  
    End Sub  
  
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    Public Shared Sub ExecuteToClient()  
        Using conn As New SqlConnection("context connection=true")  
            Dim cmd As SqlCommand = conn.CreateCommand()  
  
            cmd.CommandText = "SELECT @@VERSION"  
            conn.Open()  
            SqlContext.Pipe.ExecuteAndSend(cmd)  
        End Using  
    End Sub  
  
    ''' <summary>  
    ''' Execute a command and send the resulting reader to the client  
    ''' </summary>  
    Public Shared Sub SendReaderToClient()  
        Using conn As New SqlConnection("context connection=true")  
            Dim cmd As SqlCommand = conn.CreateCommand()  
            cmd.CommandText = "SELECT @@VERSION"  
            conn.Open()  
            Dim rdr As SqlDataReader = cmd.ExecuteReader()  
            Try  
                SqlContext.Pipe.Send(rdr)  
            Finally  
                rdr.Close()  
            End Try  
        End Using  
    End Sub  
  
End Class  
  
```  
  
 <span data-ttu-id="9a009-137">Este es el script de instalación de [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`), que implementa el ensamblado y crea los procedimientos almacenados y la función requeridos por este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9a009-137">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedures and function required by this example.</span></span>  
  
```  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendMessage')  
DROP PROCEDURE SendMessage;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendTransientResultSet')  
DROP PROCEDURE SendTransientResultSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'ExecuteToClient')  
DROP PROCEDURE ExecuteToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendReaderToClient')  
DROP PROCEDURE SendReaderToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE name = N'ReportSqlVersion' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [ReportSqlVersion];  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'InProcDA') DROP ASSEMBLY InProcDA;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
set @SamplesPath = N'C:\MySample\'  
CREATE ASSEMBLY InProcDA FROM @SamplesPath + 'InProcDA.dll'  
WITH permission_set = SAFE;  
GO  
  
CREATE PROCEDURE [SendMessage] @msg nvarchar(4000)  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[SendMessage];  
GO  
  
CREATE FUNCTION [ReportSqlVersion]() RETURNS nvarchar(4000)  
AS EXTERNAL NAME [InProcDA].[DataAccessDemo].[ReportSqlVersion];  
GO  
  
CREATE PROCEDURE [SendTransientResultSet]  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[SendTransientResultSet];  
GO  
  
CREATE PROCEDURE [ExecuteToClient]  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[ExecuteToClient];  
GO  
  
CREATE PROCEDURE [SendReaderToClient]  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[SendReaderToClient];  
GO  
```  
  
 <span data-ttu-id="9a009-138">El siguiente [!INCLUDE[tsql](../../includes/tsql-md.md)] ( `test.sql` ) prueba el ejemplo mediante el ejercicio de los procedimientos almacenados y la función que se definen en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9a009-138">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] (`test.sql`) tests the example by exercising the stored procedures and function defined in this sample.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
-- send a message to the client  
EXEC SendMessage  N'This is a test message.';  
  
-- exec a function that does data access  
SELECT dbo.ReportSqlVersion();  
  
-- exec the proc that sends a result set to the client  
EXEC SendTransientResultSet;  
  
EXEC ExecuteToClient;  
  
EXEC SendReaderToClient;  
  
USE master;  
GO  
  
```  
  
 <span data-ttu-id="9a009-139">El siguiente [!INCLUDE[tsql](../../includes/tsql-md.md)] quita de la base de datos el ensamblado, la función y los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="9a009-139">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly, function and stored procedures from the database.</span></span>  
  
```  
  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendMessage')  
DROP PROCEDURE SendMessage;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendTransientResultSet')  
DROP PROCEDURE SendTransientResultSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'ExecuteToClient')  
DROP PROCEDURE ExecuteToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendReaderToClient')  
DROP PROCEDURE SendReaderToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE name = N'ReportSqlVersion' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [ReportSqlVersion];  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'InProcDA') DROP ASSEMBLY InProcDA;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a009-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a009-140">See Also</span></span>  
 [<span data-ttu-id="9a009-141">Escenarios de uso y ejemplos para la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="9a009-141">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
