---
title: Cargar y ejecutar mediante programación un paquete remoto | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- remote packages [Integration Services]
ms.assetid: 9f6ef376-3408-46bf-b5fa-fc7b18c689c9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 06565140ae8ea3603461e2944e242aa91213de47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749381"
---
# <a name="loading-and-running-a-remote-package-programmatically"></a><span data-ttu-id="ac434-102">Cargar y ejecutar mediante programación un paquete remoto</span><span class="sxs-lookup"><span data-stu-id="ac434-102">Loading and Running a Remote Package Programmatically</span></span>
  <span data-ttu-id="ac434-103">Para ejecutar los paquetes remotos desde un equipo local que no tiene instalado [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], inicie los paquetes para que se ejecuten en el equipo remoto en el que está instalado [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac434-103">To run remote packages from a local computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, start the packages so that they run on the remote computer on which [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span> <span data-ttu-id="ac434-104">Para ello, haga que el equipo local use el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un servicio web o un componente remoto para iniciar los paquetes en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="ac434-104">You do this by having the local computer use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, a Web service, or a remote component to start the packages on the remote computer.</span></span> <span data-ttu-id="ac434-105">Si intenta iniciar los paquetes remotos directamente desde el equipo local, se cargarán y se intentará ejecutar los paquetes desde el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ac434-105">If you try to start the remote packages directly from the local computer, the packages will load onto and try to run from the local computer.</span></span> <span data-ttu-id="ac434-106">Si el equipo local no tiene instalado [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], no se ejecutarán los paquetes.</span><span class="sxs-lookup"><span data-stu-id="ac434-106">If the local computer does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, the packages will not run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac434-107">No puede ejecutar paquetes fuera de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] en un equipo cliente que no tenga instalado [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], y puede que las condiciones de su licencia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no le permitan instalar [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en equipos adicionales.</span><span class="sxs-lookup"><span data-stu-id="ac434-107">You cannot run packages outside [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing might not let you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="ac434-108">es un componente de servidor y no se puede distribuir entre equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="ac434-108">is a server component and is not redistributable to client computers.</span></span>  
  
 <span data-ttu-id="ac434-109">Como alternativa, puede ejecutar un paquete remoto desde un equipo local que tiene instalado [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac434-109">Alternately, you can run a remote package from a local computer that has [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed.</span></span> <span data-ttu-id="ac434-110">Para obtener más información, consulte [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) (Cargar y ejecutar un paquete local mediante programación).</span><span class="sxs-lookup"><span data-stu-id="ac434-110">For more information, see [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span></span>  
  
##  <a name="running-a-remote-package-on-the-remote-computer"></a><a name="top"></a> <span data-ttu-id="ac434-111">Ejecución de un paquete remoto en el equipo remoto</span><span class="sxs-lookup"><span data-stu-id="ac434-111">Running a Remote Package on the Remote Computer</span></span>  
 <span data-ttu-id="ac434-112">Como se ha mencionado anteriormente, hay varias maneras en las que puede ejecutar un paquete remoto en un servidor remoto:</span><span class="sxs-lookup"><span data-stu-id="ac434-112">As mentioned above, there are multiple ways in which you can run a remote package on a remote server:</span></span>  
  
-   [<span data-ttu-id="ac434-113">Uso del Agente SQL Server para ejecutar un paquete remoto mediante programación</span><span class="sxs-lookup"><span data-stu-id="ac434-113">Use SQL Server Agent to run the remote package programmatically</span></span>](#agent)  
  
-   [<span data-ttu-id="ac434-114">Uso de un servicio web o el componente remoto para ejecutar el paquete remoto mediante programación</span><span class="sxs-lookup"><span data-stu-id="ac434-114">Use a Web service or remote component to run the remote package programmatically</span></span>](#service)  
  
 <span data-ttu-id="ac434-115">Casi todos los métodos que se utilizan en este tema para cargar y guardar los paquetes requieren una referencia al ensamblado `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="ac434-115">Almost all the methods that are used in this topic to load and save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="ac434-116">La excepción es el enfoque ADO.NET mostrado en este tema para ejecutar el **sp_start_job** procedimiento almacenado, que solo requiere una referencia a `System.Data` .</span><span class="sxs-lookup"><span data-stu-id="ac434-116">The exception is the ADO.NET approach demonstrated in this topic for executing the **sp_start_job** stored procedure, which requires only a reference to `System.Data`.</span></span> <span data-ttu-id="ac434-117">Después de agregar la referencia al ensamblado `Microsoft.SqlServer.ManagedDTS` en un nuevo proyecto, importe el espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> con una instrucción `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="ac434-117">After you add the reference to the `Microsoft.SqlServer.ManagedDTS` assembly in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
###  <a name="using-sql-server-agent-to-run-a-remote-package-programmatically-on-the-server"></a><a name="agent"></a> <span data-ttu-id="ac434-118">Uso del Agente SQL Server para ejecutar un paquete remoto mediante programación en el servidor</span><span class="sxs-lookup"><span data-stu-id="ac434-118">Using SQL Server Agent to Run a Remote Package Programmatically on the Server</span></span>  
 <span data-ttu-id="ac434-119">En el ejemplo de código siguiente se muestra cómo utilizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante programación para ejecutar un paquete remoto en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ac434-119">The following code sample demonstrates how to programmatically use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run a remote package on the server.</span></span> <span data-ttu-id="ac434-120">En el ejemplo de código se llama al procedimiento almacenado del sistema, **sp_start_job**, que inicia un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac434-120">The code sample calls the system stored procedure, **sp_start_job**, which launches a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="ac434-121">El trabajo que el procedimiento inicia se denomina `RunSSISPackage` y este trabajo se encuentra en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="ac434-121">The job that the procedure launches is named `RunSSISPackage`, and this job is on the remote computer.</span></span> <span data-ttu-id="ac434-122">El trabajo `RunSSISPackage` ejecuta luego el paquete en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="ac434-122">The `RunSSISPackage` job then runs the package on the remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac434-123">El valor devuelto del procedimiento almacenado **sp_start_job** indica si el procedimiento almacenado ha podido iniciar correctamente el trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac434-123">The return value of the **sp_start_job** stored procedure indicates whether the stored procedure was able to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job successfully.</span></span> <span data-ttu-id="ac434-124">El valor devuelto no indica si el paquete se ha iniciado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="ac434-124">The return value does not indicate whether the package succeeded or failed.</span></span>  
  
 <span data-ttu-id="ac434-125">Para obtener información sobre cómo solucionar problemas de los paquetes que se ejecutan desde trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea el artículo de Microsoft [El paquete de SSIS no se ejecuta cuando recibe una llamada de un paso de trabajo del Agente SQL Server](https://support.microsoft.com/kb/918760).</span><span class="sxs-lookup"><span data-stu-id="ac434-125">For information on troubleshooting packages that are run from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, see the Microsoft article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760).</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="ac434-126">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac434-126">Sample Code</span></span>  
  
```vb  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
  
    Dim jobConnection As SqlConnection  
    Dim jobCommand As SqlCommand  
    Dim jobReturnValue As SqlParameter  
    Dim jobParameter As SqlParameter  
    Dim jobResult As Integer  
  
    jobConnection = New SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI")  
    jobCommand = New SqlCommand("sp_start_job", jobConnection)  
    jobCommand.CommandType = CommandType.StoredProcedure  
  
    jobReturnValue = New SqlParameter("@RETURN_VALUE", SqlDbType.Int)  
    jobReturnValue.Direction = ParameterDirection.ReturnValue  
    jobCommand.Parameters.Add(jobReturnValue)  
  
    jobParameter = New SqlParameter("@job_name", SqlDbType.VarChar)  
    jobParameter.Direction = ParameterDirection.Input  
    jobCommand.Parameters.Add(jobParameter)  
    jobParameter.Value = "RunSSISPackage"  
  
    jobConnection.Open()  
    jobCommand.ExecuteNonQuery()  
    jobResult = DirectCast(jobCommand.Parameters("@RETURN_VALUE").Value, Integer)  
    jobConnection.Close()  
  
    Select Case jobResult  
      Case 0  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.")  
      Case Else  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.")  
    End Select  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace LaunchSSISPackageAgent_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      SqlConnection jobConnection;  
      SqlCommand jobCommand;  
      SqlParameter jobReturnValue;  
      SqlParameter jobParameter;  
      int jobResult;  
  
      jobConnection = new SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI");  
      jobCommand = new SqlCommand("sp_start_job", jobConnection);  
      jobCommand.CommandType = CommandType.StoredProcedure;  
  
      jobReturnValue = new SqlParameter("@RETURN_VALUE", SqlDbType.Int);  
      jobReturnValue.Direction = ParameterDirection.ReturnValue;  
      jobCommand.Parameters.Add(jobReturnValue);  
  
      jobParameter = new SqlParameter("@job_name", SqlDbType.VarChar);  
      jobParameter.Direction = ParameterDirection.Input;  
      jobCommand.Parameters.Add(jobParameter);  
      jobParameter.Value = "RunSSISPackage";  
  
      jobConnection.Open();  
      jobCommand.ExecuteNonQuery();  
      jobResult = (Int32)jobCommand.Parameters["@RETURN_VALUE"].Value;  
      jobConnection.Close();  
  
      switch (jobResult)  
      {  
        case 0:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.");  
          break;  
        default:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.");  
          break;  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
 
  
###  <a name="using-a-web-service-or-remote-component-to-run-a-remote-package-programmatically"></a><a name="service"></a> <span data-ttu-id="ac434-127">Uso de un servicio web o el componente remoto para ejecutar el paquete remoto mediante programación</span><span class="sxs-lookup"><span data-stu-id="ac434-127">Using a Web Service or Remote Component to Run a Remote Package Programmatically</span></span>  
 <span data-ttu-id="ac434-128">La solución anterior para ejecutar los paquetes en ejecución mediante programación en el servidor no requiere ningún código personalizado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ac434-128">The previous solution for running packages programmatically on the server does not require any custom code on the server.</span></span> <span data-ttu-id="ac434-129">Sin embargo, quizá prefiera una solución que no confía en el Agente SQL Server para ejecutar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="ac434-129">However, you may prefer a solution that does not rely on SQL Server Agent to execute packages.</span></span> <span data-ttu-id="ac434-130">En el ejemplo siguiente se muestra un servicio web que se puede crear en el servidor para iniciar los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] localmente y una aplicación de prueba que se puede utilizar para llamar al servicio web desde un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="ac434-130">The following example demonstrates a Web service that can be created on the server to start [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages locally, and a test application that can be used to call the Web service from a client computer.</span></span> <span data-ttu-id="ac434-131">Si prefiere crear un componente remoto en lugar de un servicio web, puede utilizar la misma lógica de código con muy pocos cambios en un componente remoto.</span><span class="sxs-lookup"><span data-stu-id="ac434-131">If you prefer to create a remote component instead of a Web service, you can use the same code logic with very few changes in a remote component.</span></span> <span data-ttu-id="ac434-132">No obstante, un componente remoto puede requerir una configuración más amplia que un servicio web.</span><span class="sxs-lookup"><span data-stu-id="ac434-132">However a remote component may require more extensive configuration than a Web service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac434-133">Con la configuración predeterminada para la autenticación y autorización, un servicio web no tiene generalmente los permisos necesarios para obtener acceso a SQL Server o al sistema de archivos para cargar y ejecutar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="ac434-133">With its default settings for authentication and authorization, a Web service generally does not have sufficient permissions to access SQL Server or the file system to load and execute packages.</span></span> <span data-ttu-id="ac434-134">Quizá tenga que asignar los permisos adecuados al servicio web configurando los valores de autenticación y autorización en el archivo **web.config** y asignando los permisos de base de datos y del sistema de archivos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="ac434-134">You may have to assign appropriate permissions to the Web service by configuring its authentication and authorization settings in the **web.config** file and assigning database and file system permissions as appropriate.</span></span> <span data-ttu-id="ac434-135">Una descripción completa de los permisos de la Web, base de datos y sistema de archivos está más allá del ámbito de este tema.</span><span class="sxs-lookup"><span data-stu-id="ac434-135">A complete discussion of Web, database, and file system permissions is beyond the scope of this topic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac434-136">Los métodos de la clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> para trabajar con el almacén de paquetes SSIS solamente admiten ".", localhost o el nombre del servidor local.</span><span class="sxs-lookup"><span data-stu-id="ac434-136">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="ac434-137">No puede utilizar "(local)".</span><span class="sxs-lookup"><span data-stu-id="ac434-137">You cannot use "(local)".</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="ac434-138">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac434-138">Sample Code</span></span>  
 <span data-ttu-id="ac434-139">Los ejemplos de código siguientes muestran cómo crear y probar el servicio web.</span><span class="sxs-lookup"><span data-stu-id="ac434-139">The following code samples show how to create and test the Web service.</span></span>  
  
#### <a name="creating-the-web-service"></a><span data-ttu-id="ac434-140">Crear el servicio web</span><span class="sxs-lookup"><span data-stu-id="ac434-140">Creating the Web Service</span></span>  
 <span data-ttu-id="ac434-141">Un paquete [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] se puede cargar directamente desde un archivo, directamente desde SQL Server o desde el Almacén de paquetes SSIS, que administra el almacenamiento del paquete en SQL Server y en carpetas del sistema de archivos especiales.</span><span class="sxs-lookup"><span data-stu-id="ac434-141">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can be loaded directly from a file, directly from SQL Server, or from the SSIS Package Store, which manages package storage in both SQL Server and special file system folders.</span></span> <span data-ttu-id="ac434-142">En este ejemplo se admiten todas las opciones disponibles utilizando el constructor `Select Case` o `switch` para seleccionar la sintaxis adecuada para iniciar el paquete y concatenar adecuadamente los argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="ac434-142">This sample supports all the available options by using a `Select Case` or `switch` construct to select the appropriate syntax for starting the package and to concatenate the input arguments appropriately.</span></span> <span data-ttu-id="ac434-143">El método de servicio web LaunchPackage devuelve el resultado de ejecución del paquete como un entero en lugar de un valor <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> para que los equipos cliente no requieran una referencia a ningún ensamblado de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac434-143">The LaunchPackage Web service method returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span>  
  
###### <a name="to-create-a-web-service-to-run-packages-on-the-server-programmatically"></a><span data-ttu-id="ac434-144">Para crear un servicio web para ejecutar mediante programación los paquetes en el servidor</span><span class="sxs-lookup"><span data-stu-id="ac434-144">To create a Web service to run packages on the server programmatically</span></span>  
  
1.  <span data-ttu-id="ac434-145">Abra Visual Studio y cree un proyecto de servicio web en el lenguaje de programación preferido.</span><span class="sxs-lookup"><span data-stu-id="ac434-145">Open Visual Studio and create a Web service project in your preferred programming language.</span></span> <span data-ttu-id="ac434-146">En el código de ejemplo se utiliza el nombre LaunchSSISPackageService para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ac434-146">The sample code uses the name LaunchSSISPackageService for the project.</span></span>  
  
2.  <span data-ttu-id="ac434-147">Agregue una referencia a `Microsoft.SqlServer.ManagedDTS` y agregue una `Imports` `using` instrucción o al archivo de código para el espacio de nombres **Microsoft. SqlServer. DTS. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="ac434-147">Add a reference to `Microsoft.SqlServer.ManagedDTS` and add an `Imports` or `using` statement to the code file for the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
3.  <span data-ttu-id="ac434-148">Pegue el código de ejemplo del método de servicio web de LaunchPackage en la clase.</span><span class="sxs-lookup"><span data-stu-id="ac434-148">Paste the sample code for the LaunchPackage Web service method into the class.</span></span> <span data-ttu-id="ac434-149">(En el ejemplo se muestra el contenido completo de la ventana de código).</span><span class="sxs-lookup"><span data-stu-id="ac434-149">(The sample shows the whole contents of the code window.)</span></span>  
  
4.  <span data-ttu-id="ac434-150">Genere y pruebe el servicio web proporcionando un conjunto de valores válidos para los argumentos de entrada del método LaunchPackage que señalan a un paquete existente.</span><span class="sxs-lookup"><span data-stu-id="ac434-150">Build and test the Web service by providing a set of valid values for the input arguments of the LaunchPackage method that point to an existing package.</span></span> <span data-ttu-id="ac434-151">Por ejemplo, si package1.dtsx está almacenado en el servidor en C:\My Packages, pase "file" como el valor de sourceType, "C:\My Packages" como el valor de sourceLocation y "package1" (sin la extensión) como el valor de packageName.</span><span class="sxs-lookup"><span data-stu-id="ac434-151">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of the sourceType, "C:\My Packages" as the value of sourceLocation, and "package1" (without the extension) as the value of packageName.</span></span>  
  
```vb  
Imports System.Web  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.IO  
  
<WebService(Namespace:="http://dtsue/")> _  
<WebServiceBinding(ConformsTo:=WsiProfiles.BasicProfile1_1)> _  
<Global.Microsoft.VisualBasic.CompilerServices.DesignerGenerated()> _  
Public Class LaunchSSISPackageService  
  Inherits System.Web.Services.WebService  
  
  ' LaunchPackage Method Parameters:  
  ' 1. sourceType: file, sql, dts  
  ' 2. sourceLocation: file system folder, (none), logical folder  
  ' 3. packageName: for file system, ".dtsx" extension is appended  
  
  <WebMethod()> _  
  Public Function LaunchPackage( _  
    ByVal sourceType As String, _  
    ByVal sourceLocation As String, _  
    ByVal packageName As String) As Integer 'DTSExecResult  
  
    Dim packagePath As String  
    Dim myPackage As Package  
    Dim integrationServices As New Application  
  
    ' Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName)  
  
    Select Case sourceType  
      Case "file"  
        ' Package is stored as a file.  
        ' Add extension if not present.  
        If String.IsNullOrEmpty(Path.GetExtension(packagePath)) Then  
          packagePath = String.Concat(packagePath, ".dtsx")  
        End If  
        If File.Exists(packagePath) Then  
          myPackage = integrationServices.LoadPackage(packagePath, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid file location: " & packagePath)  
        End If  
      Case "sql"  
        ' Package is stored in MSDB.  
        ' Combine logical path and package name.  
        If integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty) Then  
          myPackage = integrationServices.LoadFromSqlServer( _  
            packageName, "(local)", String.Empty, String.Empty, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case "dts"  
        ' Package is managed by SSIS Package Store.  
        ' Default logical paths are File System and MSDB.  
        If integrationServices.ExistsOnDtsServer(packagePath, ".") Then  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case Else  
        Throw New ApplicationException( _  
          "Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.")  
    End Select  
  
    Return myPackage.Execute()  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.IO;  
  
[WebService(Namespace = "http://dtsue/")]  
[WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
public class LaunchSSISPackageServiceCS : System.Web.Services.WebService  
{  
  public LaunchSSISPackageServiceCS()  
  {  
    }  
  
  // LaunchPackage Method Parameters:  
  // 1. sourceType: file, sql, dts  
  // 2. sourceLocation: file system folder, (none), logical folder  
  // 3. packageName: for file system, ".dtsx" extension is appended  
  
  [WebMethod]  
  public int LaunchPackage(string sourceType, string sourceLocation, string packageName)  
  {   
  
    string packagePath;  
    Package myPackage;  
    Application integrationServices = new Application();  
  
    // Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName);  
  
    switch(sourceType)  
    {  
      case "file":  
        // Package is stored as a file.  
        // Add extension if not present.  
        if (String.IsNullOrEmpty(Path.GetExtension(packagePath)))  
        {  
          packagePath = String.Concat(packagePath, ".dtsx");  
        }  
        if (File.Exists(packagePath))  
        {  
          myPackage = integrationServices.LoadPackage(packagePath, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid file location: "+packagePath);  
        }  
        break;  
      case "sql":  
        // Package is stored in MSDB.  
        // Combine logical path and package name.  
        if (integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty))  
        {  
          myPackage = integrationServices.LoadFromSqlServer(packageName, "(local)", String.Empty, String.Empty, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      case "dts":  
        // Package is managed by SSIS Package Store.  
        // Default logical paths are File System and MSDB.  
        if (integrationServices.ExistsOnDtsServer(packagePath, "."))  
        {  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      default:  
        throw new ApplicationException("Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.");  
    }  
  
    return (Int32)myPackage.Execute();  
  
  }  
  
}  
```  
  
#### <a name="testing-the-web-service"></a><span data-ttu-id="ac434-152">Probar el servicio web</span><span class="sxs-lookup"><span data-stu-id="ac434-152">Testing the Web Service</span></span>  
 <span data-ttu-id="ac434-153">La aplicación de consola del ejemplo siguiente utiliza el servicio web para ejecutar un paquete.</span><span class="sxs-lookup"><span data-stu-id="ac434-153">The following sample console application uses the Web service to run a package.</span></span> <span data-ttu-id="ac434-154">El método LaunchPackage del servicio web devuelve el resultado de ejecución del paquete como un entero en lugar de un valor <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> para que los equipos cliente no requieran una referencia a ningún ensamblado de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac434-154">The LaunchPackage method of the Web service returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span> <span data-ttu-id="ac434-155">En el ejemplo se crea una enumeración privada cuyos valores reflejan los valores <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> para notificar los resultados de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac434-155">The sample creates a private enumeration whose values mirror the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> values to report the results of execution.</span></span>  
  
###### <a name="to-create-a-console-application-to-test-the-web-service"></a><span data-ttu-id="ac434-156">Para crear una aplicación de consola para probar el servicio web</span><span class="sxs-lookup"><span data-stu-id="ac434-156">To create a console application to test the Web service</span></span>  
  
1.  <span data-ttu-id="ac434-157">En Visual Studio, agregue una nueva aplicación de consola, que use el lenguaje de programación preferido, a la misma solución que contiene el proyecto de servicio web.</span><span class="sxs-lookup"><span data-stu-id="ac434-157">In Visual Studio, add a new console application, using your preferred programming language, to the same solution that contains the Web service project.</span></span> <span data-ttu-id="ac434-158">En el código de ejemplo se utiliza el nombre LaunchSSISPackageTest para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ac434-158">The sample code uses the name LaunchSSISPackageTest for the project.</span></span>  
  
2.  <span data-ttu-id="ac434-159">Establezca la nueva aplicación de consola como proyecto de inicio de la solución.</span><span class="sxs-lookup"><span data-stu-id="ac434-159">Set the new console application as the startup project in the solution.</span></span>  
  
3.  <span data-ttu-id="ac434-160">Agregue una referencia web del proyecto de servicio web.</span><span class="sxs-lookup"><span data-stu-id="ac434-160">Add a Web reference for the Web service project.</span></span> <span data-ttu-id="ac434-161">Si es necesario, ajuste la declaración de variable en el código de ejemplo para el nombre que asigna al objeto proxy del servicio web.</span><span class="sxs-lookup"><span data-stu-id="ac434-161">If necessary, adjust the variable declaration in the sample code for the name that you assign to the Web service proxy object.</span></span>  
  
4.  <span data-ttu-id="ac434-162">Pegue el código de ejemplo de la rutina Main y la enumeración privada en el código.</span><span class="sxs-lookup"><span data-stu-id="ac434-162">Paste the sample code for the Main routine and the private enumeration into the code.</span></span> <span data-ttu-id="ac434-163">(En el ejemplo se muestra el contenido completo de la ventana de código).</span><span class="sxs-lookup"><span data-stu-id="ac434-163">(The sample shows the whole contents of the code window.)</span></span>  
  
5.  <span data-ttu-id="ac434-164">Modifique la línea de código que llama al método LaunchPackage para proporcionar un conjunto de valores válidos para los argumentos de entrada que señalan a un paquete existente.</span><span class="sxs-lookup"><span data-stu-id="ac434-164">Edit the line of code that calls the LaunchPackage method to provide a set of valid values for the input arguments that point to an existing package.</span></span> <span data-ttu-id="ac434-165">Por ejemplo, si package1.dtsx está almacenado en el servidor en C:\My Packages, pase "file" como el valor de `sourceType`, "C:\My Packages" como el valor de `sourceLocation` y "package1" (sin la extensión) como el valor de `packageName`.</span><span class="sxs-lookup"><span data-stu-id="ac434-165">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of `sourceType`, "C:\My Packages" as the value of `sourceLocation`, and "package1" (without the extension) as the value of `packageName`.</span></span>  
  
```vb  
Module LaunchSSISPackageTest  
  
  Sub Main()  
  
    Dim launchPackageService As New LaunchSSISPackageService.LaunchSSISPackageService  
    Dim packageResult As Integer  
  
    Try  
      packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage")  
    Catch ex As Exception  
      ' The type of exception returned by a Web service is:  
      '  System.Web.Services.Protocols.SoapException  
      Console.WriteLine("The following exception occurred: " & ex.Message)  
    End Try  
  
    Console.WriteLine(CType(packageResult, PackageExecutionResult).ToString)  
    Console.ReadKey()  
  
  End Sub  
  
  Private Enum PackageExecutionResult  
    PackageSucceeded  
    PackageFailed  
    PackageCompleted  
    PackageWasCancelled  
  End Enum  
  
End Module  
```  
  
```csharp  
using System;  
  
namespace LaunchSSISPackageSvcTestCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS launchPackageService = new LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS();  
      int packageResult = 0;  
  
      try  
      {  
        packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage");  
      }  
      catch (Exception ex)  
      {  
        // The type of exception returned by a Web service is:  
        //  System.Web.Services.Protocols.SoapException  
        Console.WriteLine("The following exception occurred: " + ex.Message);  
      }  
  
      Console.WriteLine(((PackageExecutionResult)packageResult).ToString());  
      Console.ReadKey();  
  
    }  
  
    private enum PackageExecutionResult  
    {  
      PackageSucceeded,  
      PackageFailed,  
      PackageCompleted,  
      PackageWasCancelled  
    };  
  
  }  
}  
```  
  

  
## <a name="external-resources"></a><span data-ttu-id="ac434-166">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="ac434-166">External Resources</span></span>  
  
-   <span data-ttu-id="ac434-167">Vídeo: [Cómo automatizar la ejecución de paquetes SSIS usando el Agente SQL Server (vídeo de SQL Server)](https://technet.microsoft.com/sqlserver/ff686764.aspx), en technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ac434-167">Video, [How to: Automate SSIS Package Execution by Using the SQL Server Agent (SQL Server Video)](https://technet.microsoft.com/sqlserver/ff686764.aspx), on technet.microsoft.com</span></span>  
  
<span data-ttu-id="ac434-168">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ac434-168">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ac434-169">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="ac434-169">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ac434-170">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="ac434-170">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ac434-171">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="ac434-171">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac434-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac434-172">See Also</span></span>  
 <span data-ttu-id="ac434-173">[Descripción de las diferencias entre la ejecución local y remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="ac434-173">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="ac434-174">[Cargar y ejecutar un paquete local mediante programación](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="ac434-174">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 [<span data-ttu-id="ac434-175">Cargar la salida de un paquete local</span><span class="sxs-lookup"><span data-stu-id="ac434-175">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
