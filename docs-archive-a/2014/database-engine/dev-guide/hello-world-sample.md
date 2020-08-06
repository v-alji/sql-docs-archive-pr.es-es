---
title: Hola mundo ejemplo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: fed6c358-f5ee-4d4c-9ad6-089778383ba7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d5616c1d4ef6428a011c8e36be3757931039c9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751402"
---
# <a name="hello-world-sample"></a><span data-ttu-id="f25b9-102">Ejemplo de Hola a todos</span><span class="sxs-lookup"><span data-stu-id="f25b9-102">Hello World Sample</span></span>
  <span data-ttu-id="f25b9-103">El ejemplo Hola a todos muestra las operaciones básicas relacionadas con la creación, implementación y prueba de un procedimiento almacenado simple basado en la integración de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f25b9-103">The Hello World sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="f25b9-104">En este ejemplo se muestra también cómo se devuelven datos a través de un registro, que el procedimiento almacenado construye y devuelve dinámicamente al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f25b9-104">This sample also demonstrates how to return data through a record, which is dynamically constructed by the stored procedure and returned to the caller.</span></span>  
  
 <span data-ttu-id="f25b9-105">El `HelloWorld` procedimiento almacenado devuelve la cadena "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="f25b9-105">The `HelloWorld` stored procedure returns the string "Hello world!"</span></span> <span data-ttu-id="f25b9-106">en un conjunto de resultados que consta de una fila.</span><span class="sxs-lookup"><span data-stu-id="f25b9-106">in a result set consisting of one row.</span></span> <span data-ttu-id="f25b9-107">En este ejemplo se muestran algunos usos de las clases [Microsoft. SqlServer. Server. SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft. SqlServer. Server. SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) y [Microsoft. SqlServer. Server. Pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span><span class="sxs-lookup"><span data-stu-id="f25b9-107">This example illustrates some uses for the classes [Microsoft.SqlServer.Server.SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft.SqlServer.Server.SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) and [Microsoft.SqlServer.Server.Pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f25b9-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f25b9-108">Prerequisites</span></span>  
 <span data-ttu-id="f25b9-109">Para crear y ejecutar este proyecto se debe instalar el siguiente software:</span><span class="sxs-lookup"><span data-stu-id="f25b9-109">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f25b9-110">o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="f25b9-110">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="f25b9-111">Puede obtener [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express de forma gratuita desde el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sitio web [de documentación y ejemplos de](https://www.microsoft.com/sql-server/sql-server-editions-express)Express.</span><span class="sxs-lookup"><span data-stu-id="f25b9-111">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="f25b9-112">La base de datos de AdventureWorks que está disponible en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sitio web [para desarrolladores de](https://go.microsoft.com/fwlink/?linkid=62796).</span><span class="sxs-lookup"><span data-stu-id="f25b9-112">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="f25b9-113">.NET Framework SDK 2.0 o posterior, o Microsoft Visual Studio 2005 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f25b9-113">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="f25b9-114">Puede obtener .NET Framework SDK de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="f25b9-114">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="f25b9-115">Además, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="f25b9-115">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="f25b9-116">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está usando debe tener habilitada la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="f25b9-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="f25b9-117">Para habilitar la integración con CLR, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f25b9-117">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="f25b9-118">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="f25b9-118">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="f25b9-119">Ejecute los siguientes comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="f25b9-119">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="f25b9-120">Para habilitar CLR, debe tener el permiso de nivel de servidor `ALTER SETTINGS`, que se concede implícitamente a los miembros de los roles fijos de servidor `sysadmin` y `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="f25b9-120">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="f25b9-121">La base de datos de AdventureWorks debe estar instalada en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está usando.</span><span class="sxs-lookup"><span data-stu-id="f25b9-121">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="f25b9-122">Si no es administrador de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está utilizando, debe hacer que un administrador le conceda el permiso **CreateAssembly** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="f25b9-122">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="f25b9-123">Generar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f25b9-123">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="f25b9-124">Cree y ejecute el ejemplo utilizando las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="f25b9-124">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="f25b9-125">Abra un símbolo del sistema de Visual Studio o de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f25b9-125">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="f25b9-126">Si es necesario, cree un directorio para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f25b9-126">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="f25b9-127">Para este ejemplo, utilizaremos C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="f25b9-127">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="f25b9-128">En c:\MySample, cree `HelloWorld.vb` (para el ejemplo de Visual Basic) o `HelloWorld.cs` (para el ejemplo de C#) y copie el código muestra de Visual Basic o de C# que corresponda (más abajo) en el archivo.</span><span class="sxs-lookup"><span data-stu-id="f25b9-128">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="f25b9-129">Compile el código muestra desde el símbolo del sistema ejecutando uno de los comandos siguientes, dependiendo de su opción de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="f25b9-129">Compile the sample code from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc C:HelloWorld.vb /target:library`  
  
    -   `csc /target:library HelloWorld.cs`  
  
5.  <span data-ttu-id="f25b9-130">Copie el código de instalación de [!INCLUDE[tsql](../../includes/tsql-md.md)] en un archivo y guárdelo como `Install.sql` en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f25b9-130">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="f25b9-131">Implemente el ensamblado y el procedimiento almacenado ejecutando</span><span class="sxs-lookup"><span data-stu-id="f25b9-131">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql -v root = "C:\MySample\"`  
  
7.  <span data-ttu-id="f25b9-132">Copie el script de comando de prueba de [!INCLUDE[tsql](../../includes/tsql-md.md)] en un archivo y guárdelo como `test.sql` en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f25b9-132">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
8.  <span data-ttu-id="f25b9-133">Ejecute el script de prueba con el siguiente comando</span><span class="sxs-lookup"><span data-stu-id="f25b9-133">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="f25b9-134">Copie el script de limpieza de [!INCLUDE[tsql](../../includes/tsql-md.md)] en un archivo y guárdelo como `cleanup.sql` en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f25b9-134">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="f25b9-135">Ejecute el script con el siguiente comando</span><span class="sxs-lookup"><span data-stu-id="f25b9-135">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="f25b9-136">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f25b9-136">Sample Code</span></span>  
 <span data-ttu-id="f25b9-137">A continuación se muestran las listas de código para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f25b9-137">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="f25b9-138">C#</span><span class="sxs-lookup"><span data-stu-id="f25b9-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
public partial class StoredProcedures  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld()  
    {  
        Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 12);  
        SqlDataRecord greetingRecord  
            = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
        greetingRecord.SetString(0, "Hello world!");  
        SqlContext.Pipe.Send(greetingRecord);  
    }  
};  
  
```  
  
 <span data-ttu-id="f25b9-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f25b9-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public NotInheritable Class StoredProcedures  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorld()  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 12)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, "Hello World!")  
        SqlContext.Pipe.Send(greetingRecord)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="f25b9-140">Este es el script de instalación de [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`), que implementa el ensamblado y crea el procedimiento almacenado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f25b9-140">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = '$(root)'  
CREATE ASSEMBLY HelloWorld   
FROM @SamplesPath + 'HelloWorld.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorld  
--(  
--    @Greeting nvarchar(12) OUTPUT  
--)  
AS EXTERNAL NAME HelloWorld.[StoredProcedures].HelloWorld;  
GO  
```  
  
 <span data-ttu-id="f25b9-141">Este es el script `test.sql`, que prueba el ejemplo ejecutando el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="f25b9-141">This is `test.sql`, which tests the sample by executing the stored procedure.</span></span>  
  
```  
use AdventureWorks  
go  
execute usp_HelloWorld  
  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
```  
  
 <span data-ttu-id="f25b9-142">El script [!INCLUDE[tsql](../../includes/tsql-md.md)] siguiente quita el ensamblado y el procedimiento almacenado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f25b9-142">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f25b9-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f25b9-143">See Also</span></span>  
 [<span data-ttu-id="f25b9-144">Escenarios de uso y ejemplos para la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="f25b9-144">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
