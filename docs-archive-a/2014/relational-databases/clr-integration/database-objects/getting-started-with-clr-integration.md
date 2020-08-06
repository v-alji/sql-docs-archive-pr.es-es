---
title: Introducción con la integración CLR | Microsoft Docs
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
- database objects [CLR integration]
- namespaces [CLR integration]
- database objects [CLR integration], about CLR integration
- stored procedures [CLR integration]
- common language runtime [SQL Server], about CLR integration
- building database objects [CLR integration], about CLR integration
- common language runtime [SQL Server], stored procedures
- common language runtime [SQL Server], namespaces
- Hello World example [CLR integration]
- library [CLR integration]
ms.assetid: c73e628a-f54a-411a-bfe3-6dae519316cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 43c97e411a4d74aa48b88f2edbbe420ae17f3534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662094"
---
# <a name="getting-started-with-clr-integration"></a><span data-ttu-id="8bcb9-102">Introducción a la integración CLR</span><span class="sxs-lookup"><span data-stu-id="8bcb9-102">Getting Started with CLR Integration</span></span>
  <span data-ttu-id="8bcb9-103">En este tema se proporciona información general sobre los espacios de nombres y las bibliotecas necesarios para compilar objetos de base de datos mediante la [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integración de con el Common Language Runtime de .NET Framework (CLR).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-103">This topic provides an overview of the namespaces and libraries required to compile database objects using the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="8bcb9-104">En este tema también se muestra cómo escribir, compilar y ejecutar un procedimiento almacenado CLR simple escrito en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-104">The topic also shows you how to write, compile, and run a simple CLR stored procedure written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
## <a name="required-namespaces"></a><span data-ttu-id="8bcb9-105">Espacios de nombres necesarios</span><span class="sxs-lookup"><span data-stu-id="8bcb9-105">Required Namespaces</span></span>  
 <span data-ttu-id="8bcb9-106">A partir de [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bcb9-106">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8bcb9-107">La funcionalidad de la integración CLR se expone en un ensamblado denominado system.data.dll, que forma parte de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-107">CLR integration functionality is exposed in an assembly called system.data.dll, which is part of the .NET Framework.</span></span> <span data-ttu-id="8bcb9-108">Este ensamblado puede encontrarse en la caché de ensamblados global (GAC) o en el directorio de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-108">This assembly can be found in the Global Assembly Cache (GAC) as well as in the .NET Framework directory.</span></span> <span data-ttu-id="8bcb9-109">Normalmente, se agrega una referencia a este ensamblado mediante las herramientas de la línea de comandos y [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, por lo que no es necesario agregarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-109">A reference to this assembly is typically added automatically by both command line tools and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, so there is no need to add it manually.</span></span>  
  
 <span data-ttu-id="8bcb9-110">El ensamblado system.data.dll contiene los espacios de nombres siguientes, que son necesarios para compilar objetos de base de datos CLR:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-110">The system.data.dll assembly contains the following namespaces, which are required for compiling CLR database objects:</span></span>  
  
 `System.Data`  
  
 `System.Data.Sql`  
  
 `Microsoft.SqlServer.Server`  
  
 `System.Data.SqlTypes`  
  
## <a name="writing-a-simple-hello-world-stored-procedure"></a><span data-ttu-id="8bcb9-111">Escribir un procedimiento almacenado "Hello World" simple</span><span class="sxs-lookup"><span data-stu-id="8bcb9-111">Writing A Simple "Hello World" Stored Procedure</span></span>  
 <span data-ttu-id="8bcb9-112">Copie y pegue el siguiente código de Visual C# o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic en un editor de texto y guárdelo en un archivo denominado "helloworld.cs" o "helloworld.vb".</span><span class="sxs-lookup"><span data-stu-id="8bcb9-112">Copy and paste the following Visual C# or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic code into a text editor, and save it in a file named "helloworld.cs" or "helloworld.vb".</span></span>  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
  
public class HelloWorldProc  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld(out string text)  
    {  
        SqlContext.Pipe.Send("Hello world!" + Environment.NewLine);  
        text = "Hello world!";  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.Runtime.InteropServices  
  
Public Class HelloWorldProc  
    <Microsoft.SqlServer.Server.SqlProcedure> _   
    Public Shared  Sub HelloWorld(<Out()> ByRef text as String)  
        SqlContext.Pipe.Send("Hello world!" & Environment.NewLine)  
        text = "Hello world!"  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="8bcb9-113">Este programa simple contiene un solo método estático en una clase pública.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-113">This simple program contains a single static method on a public class.</span></span> <span data-ttu-id="8bcb9-114">Este método usa dos clases nuevas, `SqlContext` y `SqlPipe`, para crear los objetos de base de datos administrados a fin de generar un mensaje de texto simple.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-114">This method uses two new classes, `SqlContext` and `SqlPipe`, for creating managed database objects to output a simple text message.</span></span> <span data-ttu-id="8bcb9-115">El método también asigna la cadena "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="8bcb9-115">The method also assigns the string "Hello world!"</span></span> <span data-ttu-id="8bcb9-116">como el valor de un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-116">as the value of an out parameter.</span></span> <span data-ttu-id="8bcb9-117">Este método se puede declarar como un procedimiento almacenado en un [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-117">This method can be declared as a stored procedure in [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] stored procedure.</span></span>  
  
 <span data-ttu-id="8bcb9-118">Ahora, procederemos a compilar este programa como una biblioteca, lo cargaremos en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y lo ejecutaremos como un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-118">We will now compile this program as a library, load it into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and run it as a stored procedure.</span></span>  
  
## <a name="compiling-the-hello-world-stored-procedure"></a><span data-ttu-id="8bcb9-119">Compilar el procedimiento almacenado "Hello World"</span><span class="sxs-lookup"><span data-stu-id="8bcb9-119">Compiling the "Hello World" Stored Procedure</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)]<span data-ttu-id="8bcb9-120">.NET Framework archivos de redistribución de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-120">.NET Framework redistribution files by default.</span></span> <span data-ttu-id="8bcb9-121">Estos archivos incluyen csc.exe y vbc.exe, los compiladores de línea de comandos de Visual C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-121">These files include csc.exe and vbc.exe, the command-line compilers for Visual C# and Visual Basic programs.</span></span> <span data-ttu-id="8bcb9-122">Para compilar el ejemplo, debe modificar la variable de ruta de acceso para que apunte al directorio que contiene los archivos csc.exe o vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-122">In order to compile our sample, you must modify your path variable to point to the directory containing csc.exe or vbc.exe.</span></span> <span data-ttu-id="8bcb9-123">Ésta es la ruta de instalación predeterminada de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-123">The following is the default installation path of the .NET Framework.</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\(version)  
```  
  
 <span data-ttu-id="8bcb9-124">La versión incluye el número de versión del componente .NET Framework redistribuible instalado.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-124">Version contains the version number of the installed .NET Framework redistributable.</span></span> <span data-ttu-id="8bcb9-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-125">For example:</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\v2.0.31113  
```  
  
 <span data-ttu-id="8bcb9-126">Una vez agregado el directorio .NET Framework a la ruta de acceso, puede compilar el procedimiento almacenado de ejemplo en un ensamblado con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-126">Once you have added the .NET Framework directory to your path, you can compile the sample stored procedure into an assembly with the following command.</span></span> <span data-ttu-id="8bcb9-127">La opción `/target` permite compilarlo en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-127">The `/target` option allows you to compile it into an assembly.</span></span>  
  
 <span data-ttu-id="8bcb9-128">Para los archivos de origen de Visual C#:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-128">For Visual C# source files:</span></span>  
  
```  
csc /target:library helloworld.cs   
```  
  
 <span data-ttu-id="8bcb9-129">Para los archivos de origen de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-129">For Visual Basic source files:</span></span>  
  
```  
vbc /target:library helloworld.vb  
```  
  
 <span data-ttu-id="8bcb9-130">Estos comandos inician el compilador de Visual C# o Visual Basic mediante la opción /target para especificar la creación de un archivo DLL de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-130">These commands launch the Visual C# or Visual Basic compiler using the /target option to specify building a library DLL.</span></span>  
  
## <a name="loading-and-running-the-hello-world-stored-procedure-in-sql-server"></a><span data-ttu-id="8bcb9-131">Cargar y ejecutar el procedimiento almacenado "Hello World" en SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bcb9-131">Loading and Running the "Hello World" Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="8bcb9-132">Una vez que el procedimiento de ejemplo se haya compilado correctamente, puede probarlo en [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] y crear una nueva consulta, conectándose a una base de datos de prueba adecuada (por ejemplo, la base de datos de ejemplo AdventureWorks).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-132">Once the sample procedure has successfully compiled, you can test it in [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] and create a new query, connecting to a suitable test database (for example, the AdventureWorks sample database).</span></span>  
  
 <span data-ttu-id="8bcb9-133">La capacidad de ejecutar el código de Common Language Runtime (CLR) está establecida de forma predeterminada en OFF en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bcb9-133">The ability to execute common language runtime (CLR) code is set to OFF by default in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8bcb9-134">El código CLR se puede habilitar mediante el **sp_configure** procedimiento almacenado del sistema.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-134">The CLR code can be enabled by using the **sp_configure** system stored procedure.</span></span> <span data-ttu-id="8bcb9-135">Para más información, consulte [Enabling CLR Integration](../clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-135">For more information, see [Enabling CLR Integration](../clr-integration-enabling.md).</span></span>  
  
 <span data-ttu-id="8bcb9-136">Tendremos que crear el ensamblado de modo que podamos obtener acceso al procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-136">We will need to create the assembly so we can access the stored procedure.</span></span> <span data-ttu-id="8bcb9-137">Para este ejemplo, vamos a suponer que ha creado el ensamblado helloworld.dll en el directorio C:\.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-137">For this example, we will assume that you have created the helloworld.dll assembly in the C:\ directory.</span></span> <span data-ttu-id="8bcb9-138">Agregue la siguiente instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] a su consulta.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-138">Add the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to your query.</span></span>  
  
```  
CREATE ASSEMBLY helloworld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE  
```  
  
 <span data-ttu-id="8bcb9-139">Una vez creado el ensamblado, podremos obtener acceso a nuestro método HelloWorld mediante la instrucción CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-139">Once the assembly has been created, we can now access our HelloWorld method by using the create procedure statement.</span></span> <span data-ttu-id="8bcb9-140">Llamaremos a nuestro procedimiento almacenado "hello":</span><span class="sxs-lookup"><span data-stu-id="8bcb9-140">We will call our stored procedure "hello":</span></span>  
  
```  
  
CREATE PROCEDURE hello  
@i nchar(25) OUTPUT  
AS  
EXTERNAL NAME helloworld.HelloWorldProc.HelloWorld  
-- if the HelloWorldProc class is inside a namespace (called MyNS),  
-- the last line in the create procedure statement would be  
-- EXTERNAL NAME helloworld.[MyNS.HelloWorldProc].HelloWorld  
```  
  
 <span data-ttu-id="8bcb9-141">Una vez creado el procedimiento, podrá ejecutarse como un procedimiento almacenado normal escrito en [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bcb9-141">Once the procedure has been created, it can be run just like a normal stored procedure written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8bcb9-142">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-142">Execute the following command:</span></span>  
  
```  
DECLARE @J nchar(25)  
EXEC hello @J out  
PRINT @J  
```  
  
 <span data-ttu-id="8bcb9-143">Este comando debería dar lugar a la siguiente salida en la ventana de mensajes de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bcb9-143">This should result in the following output in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] messages window.</span></span>  
  
```  
Hello world!  
Hello world!  
```  
  
## <a name="removing-the-hello-world-stored-procedure-sample"></a><span data-ttu-id="8bcb9-144">Quitar el ejemplo de procedimiento almacenado "Hello World"</span><span class="sxs-lookup"><span data-stu-id="8bcb9-144">Removing the "Hello World" Stored Procedure Sample</span></span>  
 <span data-ttu-id="8bcb9-145">Cuando haya terminado de ejecutar el procedimiento almacenado de ejemplo, puede quitar el procedimiento y el ensamblado de la base de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-145">When you are finished running the sample stored procedure, you can remove the procedure and the assembly from your test database.</span></span>  
  
 <span data-ttu-id="8bcb9-146">En primer lugar, quite el procedimiento mediante el comando de drop procedure.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-146">First, remove the procedure using the drop procedure command.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'hello')  
   drop procedure hello  
```  
  
 <span data-ttu-id="8bcb9-147">Una vez quitado el procedimiento, puede quitar el ensamblado que contiene su código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-147">Once the procedure has been dropped, you can remove the assembly containing your sample code.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'helloworld')  
   drop assembly helloworld  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bcb9-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bcb9-148">See Also</span></span>  
 <span data-ttu-id="8bcb9-149">[Procedimientos almacenados CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8bcb9-149">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 <span data-ttu-id="8bcb9-150">[SQL Server extensiones específicas en proceso a ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span><span class="sxs-lookup"><span data-stu-id="8bcb9-150">[SQL Server In-Process Specific Extensions to ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span></span>  
 <span data-ttu-id="8bcb9-151">[Depurar objetos de base de datos CLR](../debugging-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="8bcb9-151">[Debugging CLR Database Objects](../debugging-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="8bcb9-152">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="8bcb9-152">CLR Integration Security</span></span>](../security/clr-integration-security.md)  
  
  
