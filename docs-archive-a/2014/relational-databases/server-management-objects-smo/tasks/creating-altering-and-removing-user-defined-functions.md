---
title: Crear, modificar y quitar funciones definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined functions [SMO]
ms.assetid: 0ebebd3b-0775-41c2-989d-aa4cf81af12a
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9ff6d1b6e675d41e96f26fc24e6e0dd4ba69454
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676974"
---
# <a name="creating-altering-and-removing-user-defined-functions"></a><span data-ttu-id="37f6c-102">Crear, modificar y eliminar las funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="37f6c-102">Creating, Altering, and Removing User-Defined Functions</span></span>
  <span data-ttu-id="37f6c-103">El <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> objeto proporciona funcionalidad que permite a los usuarios administrar mediante programación las funciones definidas por el usuario en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37f6c-103">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object provides functionality that lets users programmatically manage user-defined functions in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="37f6c-104">Las funciones definidas por el usuario admiten los parámetros de entrada y salida y también admiten las referencias directas a las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="37f6c-104">User-defined functions support input and output parameters, and also support direct references to table columns.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="37f6c-105">requiere registrar los ensamblados en una base de datos antes de que se puedan utilizar en los procedimientos almacenados, funciones definidas por el usuario, desencadenadores y los tipos de datos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="37f6c-105">requires assemblies to be registered within a database before these can be used inside stored procedures, user defined functions, triggers, and user defined data types.</span></span> <span data-ttu-id="37f6c-106">SMO admite esta característica con el objeto <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly>.</span><span class="sxs-lookup"><span data-stu-id="37f6c-106">SMO supports this feature with the <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object.</span></span>  
  
 <span data-ttu-id="37f6c-107">El objeto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> hace referencia al ensamblado .NET con las propiedades <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A> y <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A>.</span><span class="sxs-lookup"><span data-stu-id="37f6c-107">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references the .NET assembly with the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A>, and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A> properties.</span></span>  
  
 <span data-ttu-id="37f6c-108">Cuando el objeto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> hace referencia a un ensamblado .NET, debe registrar el ensamblado creando un objeto <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> y agregándolo al objeto <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection>, que pertenece al objeto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="37f6c-108">When the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references a .NET assembly, you must register the assembly by creating a <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object and adding it to the <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection> object, which belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37f6c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37f6c-109">Example</span></span>  
 <span data-ttu-id="37f6c-110">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="37f6c-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="37f6c-111">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="37f6c-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-basic"></a><span data-ttu-id="37f6c-112">Crear una función escalar definida por el usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37f6c-112">Creating a Scalar User-Defined Function in Visual Basic</span></span>  
 <span data-ttu-id="37f6c-113">En este ejemplo de código se muestra cómo crear y quitar una función escalar definida por el usuario que tiene un parámetro de objeto <xref:System.DateTime> de entrada y un tipo de valor devuelto entero de [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f6c-113">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="37f6c-114">La función definida por el usuario se crea en la base de datos de [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37f6c-114">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="37f6c-115">En el ejemplo se crea una función definida por el usuario, ISOweek, que toma un argumento de fecha y calcula el número de semana ISO.</span><span class="sxs-lookup"><span data-stu-id="37f6c-115">The example creates a user-defined function, ISOweek, which takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="37f6c-116">Para que esta función realice los cálculos correctamente, la opción DATEFIRST de base de datos debe establecerse en 1 antes de que se llame a la función.</span><span class="sxs-lookup"><span data-stu-id="37f6c-116">For this function to calculate correctly, the database DATEFIRST option must be set to 1 before the function is called.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBUserDefFuncs1](SMO How to#SMO_VBUserDefFuncs1)]  -->  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-c"></a><span data-ttu-id="37f6c-117">Crear una función escalar definida por el usuario en Visual C#</span><span class="sxs-lookup"><span data-stu-id="37f6c-117">Creating a Scalar User-Defined Function in Visual C#</span></span>  
 <span data-ttu-id="37f6c-118">En este ejemplo de código se muestra cómo crear y quitar una función escalar definida por el usuario que tiene un parámetro de objeto <xref:System.DateTime> de entrada y un tipo de valor devuelto entero de [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f6c-118">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="37f6c-119">La función definida por el usuario se crea en la base de datos de [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37f6c-119">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="37f6c-120">En el ejemplo se crea la función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="37f6c-120">The example creates the user-defined function.</span></span> <span data-ttu-id="37f6c-121">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="37f6c-121">`ISOweek`.</span></span> <span data-ttu-id="37f6c-122">Esta función toma un argumento de fecha para calcular el número de semana ISO.</span><span class="sxs-lookup"><span data-stu-id="37f6c-122">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="37f6c-123">Para que esta función realice los cálculos correctamente, la opción `DATEFIRST` de base de datos debe establecerse en `1` antes de que se llame a la función.</span><span class="sxs-lookup"><span data-stu-id="37f6c-123">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
           Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
           Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a UserDefinedFunction object variable by supplying the parent database and the name arguments in the constructor.   
            UserDefinedFunction udf = new UserDefinedFunction(db, "IsOWeek");  
  
            //Set the TextMode property to false and then set the other properties.   
            udf.TextMode = false;  
            udf.DataType = DataType.Int;  
            udf.ExecutionContext = ExecutionContext.Caller;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
  
            //Add a parameter.   
  
     UserDefinedFunctionParameter par = new UserDefinedFunctionParameter(udf, "@DATE", DataType.DateTime);  
            udf.Parameters.Add(par);  
  
            //Set the TextBody property to define the user-defined function.   
            udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;";  
  
            //Create the user-defined function on the instance of SQL Server.   
            udf.Create();  
  
            //Remove the user-defined function.   
            udf.Drop();  
        }  
```  
  
## <a name="creating-a-scalar-user-defined-function-in-powershell"></a><span data-ttu-id="37f6c-124">Crear una función escalar definida por el usuario en PowerShell</span><span class="sxs-lookup"><span data-stu-id="37f6c-124">Creating a Scalar User-Defined Function in PowerShell</span></span>  
 <span data-ttu-id="37f6c-125">En este ejemplo de código se muestra cómo crear y quitar una función escalar definida por el usuario que tiene un parámetro de objeto <xref:System.DateTime> de entrada y un tipo de valor devuelto entero de [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f6c-125">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="37f6c-126">La función definida por el usuario se crea en la base de datos de [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37f6c-126">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="37f6c-127">En el ejemplo se crea la función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="37f6c-127">The example creates the user-defined function.</span></span> <span data-ttu-id="37f6c-128">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="37f6c-128">`ISOweek`.</span></span> <span data-ttu-id="37f6c-129">Esta función toma un argumento de fecha para calcular el número de semana ISO.</span><span class="sxs-lookup"><span data-stu-id="37f6c-129">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="37f6c-130">Para que esta función realice los cálculos correctamente, la opción `DATEFIRST` de base de datos debe establecerse en `1` antes de que se llame a la función.</span><span class="sxs-lookup"><span data-stu-id="37f6c-130">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a user defined function object variable by supplying the parent database and name arguments in the constructor.
$udf  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -argumentlist $db, "IsOWeek"  
  
# Set the TextMode property to false and then set the other properties.
$udf.TextMode = $false  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::Int
$udf.ExecutionContext = [Microsoft.SqlServer.Management.SMO.ExecutionContext]::Caller  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Define a Parameter object variable by supplying the parent function, name and type arguments in the constructor.  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$par  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -argumentlist $udf, "@DATE",$type  
  
# Add the parameter to the function  
$udf.Parameters.Add($par)  
  
#Set the TextBody property to define the user-defined function.
$udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;"  
  
# Create the user-defined function on the instance of SQL Server.
$udf.Create()  
  
# Remove the user-defined function.
$udf.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="37f6c-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37f6c-131">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>  
