---
title: Depurar objetos de base de datos CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- database objects [CLR integration], debugging
- permissions [CLR integration]
- debugging [CLR integration]
- building database objects [CLR integration], debugging
- common language runtime [SQL Server], debugging
ms.assetid: 1332035c-d6ed-424d-8234-46ad21168319
author: rothja
ms.author: jroth
ms.openlocfilehash: 084b2494ec55b502f71154ca1f174a6de6d2ab70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662093"
---
# <a name="debugging-clr-database-objects"></a><span data-ttu-id="61f00-102">Depurar objetos de bases de datos CLR</span><span class="sxs-lookup"><span data-stu-id="61f00-102">Debugging CLR Database Objects</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="61f00-103">proporciona compatibilidad con la depuración de objetos de [!INCLUDE[tsql](../../../includes/tsql-md.md)] y Common Language Runtime (CLR) en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61f00-103">provides support for debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="61f00-104">Los aspectos clave de la depuración en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] son la facilidad de configuración y uso, y la integración del depurador de SQL Server con el depurador de Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="61f00-104">The key aspects of debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are the ease of setup and use, and the integration of the SQL Server debugger with the Microsoft Visual Studio debugger.</span></span> <span data-ttu-id="61f00-105">Además, la depuración se produce en todos los lenguajes.</span><span class="sxs-lookup"><span data-stu-id="61f00-105">Furthermore, debugging works across languages.</span></span> <span data-ttu-id="61f00-106">Los usuarios pueden pasar sin problemas a objetos de CLR desde [!INCLUDE[tsql](../../../includes/tsql-md.md)] y viceversa.</span><span class="sxs-lookup"><span data-stu-id="61f00-106">Users can step seamlessly into CLR objects from [!INCLUDE[tsql](../../../includes/tsql-md.md)], and vice versa.</span></span> <span data-ttu-id="61f00-107">El depurador de Transact-SQL en SQL Server Management Studio no se puede utilizar para depurar objetos de base de datos administrados, pero se pueden depurar los objetos utilizando los depuradores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="61f00-107">The Transact-SQL debugger in SQL Server Management Studio cannot be used to debug managed database objects, but you can debug the objects by using the debuggers in Visual Studio.</span></span> <span data-ttu-id="61f00-108">La depuración de objetos de base de datos administrados en Visual Studio admite todas las funciones habituales de depuración, como las instrucciones "ir a" y "paso a paso por procedimientos" dentro de rutinas que se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="61f00-108">Managed database object debugging in Visual Studio supports all common debugging features, such as "step into" and "step over" statements within routines executing on the server.</span></span> <span data-ttu-id="61f00-109">Los depuradores pueden establecer puntos de interrupción, inspeccionar la pila de llamadas, inspeccionar variables y modificar valores de variables durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="61f00-109">Debuggers can set breakpoints, inspect the call stack, inspect variables, and modify variable values while debugging.</span></span> <span data-ttu-id="61f00-110">Tenga en cuenta que Visual Studio .NET 2003 no puede utilizarse para programar o depurar la integración CLR.</span><span class="sxs-lookup"><span data-stu-id="61f00-110">Note that Visual Studio .NET 2003 cannot be used for CLR integration programming or debugging.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="61f00-111">incluye .NET Framework preinstalado y Visual Studio .NET 2003 no puede utilizar los ensamblados de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="61f00-111">includes the .NET Framework pre-installed, and Visual Studio .NET 2003 cannot use the .NET Framework 2.0 assemblies.</span></span>  
  
 <span data-ttu-id="61f00-112">Para obtener más información sobre cómo depurar código administrado con Visual Studio, vea el tema "[depurar código administrado](https://go.microsoft.com/fwlink/?LinkId=120377)" en la documentación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="61f00-112">For more information about debugging managed code using Visual Studio, see the "[Debugging Managed Code](https://go.microsoft.com/fwlink/?LinkId=120377)" topic in the Visual Studio documentation.</span></span>  
  
## <a name="debugging-permissions-and-restrictions"></a><span data-ttu-id="61f00-113">Permisos y restricciones de depuración</span><span class="sxs-lookup"><span data-stu-id="61f00-113">Debugging Permissions and Restrictions</span></span>  
 <span data-ttu-id="61f00-114">La depuración es una operación con privilegios elevados y, por lo tanto, solo los miembros del rol fijo de servidor **sysadmin** pueden hacerlo en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61f00-114">Debugging is a highly privileged operation, and therefore only members of the **sysadmin** fixed server role are allowed to do so in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="61f00-115">Las restricciones siguientes se aplican durante la depuración:</span><span class="sxs-lookup"><span data-stu-id="61f00-115">The following restrictions apply while debugging:</span></span>  
  
-   <span data-ttu-id="61f00-116">La depuración de rutinas CLR está restringida a una instancia del depurador cada vez.</span><span class="sxs-lookup"><span data-stu-id="61f00-116">Debugging CLR routines is restricted to one debugger instance at a time.</span></span> <span data-ttu-id="61f00-117">Esta limitación se aplica porque toda la ejecución de código de CLR se inmoviliza cuando se alcanza un punto de interrupción y la ejecución no continúa hasta que el depurador pasa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="61f00-117">This limitation applies because all CLR code execution freezes when a break point is hit and execution does not continue until the debugger advances from the break point.</span></span> <span data-ttu-id="61f00-118">Sin embargo, se puede seguir depurando [!INCLUDE[tsql](../../../includes/tsql-md.md)] en otras conexiones.</span><span class="sxs-lookup"><span data-stu-id="61f00-118">However, you can continue debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] in other connections.</span></span> <span data-ttu-id="61f00-119">Aunque la depuración de [!INCLUDE[tsql](../../../includes/tsql-md.md)] no inmoviliza otras ejecuciones en el servidor, puede hacer que otras conexiones tengan que esperar por el mantenimiento de un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="61f00-119">Although [!INCLUDE[tsql](../../../includes/tsql-md.md)] debugging does not freeze other executions on the server, it could cause other connections to wait by holding a lock.</span></span>  
  
-   <span data-ttu-id="61f00-120">Las conexiones existentes no se pueden depurar; solo se pueden depurar las conexiones nuevas, ya que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requiere información sobre el cliente y el entorno del depurador antes de que se pueda realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="61f00-120">Existing connections cannot be debugged, only new connections, as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires information about the client and debugger environment before the connection can be made.</span></span>  
  
 <span data-ttu-id="61f00-121">Debido a las restricciones anteriores, se recomienda que el código [!INCLUDE[tsql](../../../includes/tsql-md.md)] y CLR se depure en un servidor de prueba y no en un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="61f00-121">Due to the above restrictions, we recommend that [!INCLUDE[tsql](../../../includes/tsql-md.md)] and CLR code be debugged on a test server, and not on a production server.</span></span>  
  
## <a name="overview-of-debugging-managed-database-objects"></a><span data-ttu-id="61f00-122">Información general de la depuración de objetos de base de datos administrados</span><span class="sxs-lookup"><span data-stu-id="61f00-122">Overview of Debugging Managed Database Objects</span></span>  
 <span data-ttu-id="61f00-123">La depuración en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sigue un modelo por conexión.</span><span class="sxs-lookup"><span data-stu-id="61f00-123">Debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] follows a per-connection model.</span></span> <span data-ttu-id="61f00-124">Un depurador solo puede detectar y depurar actividades en la conexión de cliente a la que está adjuntado.</span><span class="sxs-lookup"><span data-stu-id="61f00-124">A debugger can detect and debug activities only to the client connection to which it is attached.</span></span> <span data-ttu-id="61f00-125">Dado que la funcionalidad del depurador no está limitada por el tipo de conexión, se pueden depurar flujos TDS y conexiones HTTP.</span><span class="sxs-lookup"><span data-stu-id="61f00-125">Because the functionality of the debugger is not limited by the type of connection, both tabular data stream (TDS) and HTTP connections can be debugged.</span></span> <span data-ttu-id="61f00-126">Sin embargo, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no permite la depuración de conexiones existentes.</span><span class="sxs-lookup"><span data-stu-id="61f00-126">However, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow debugging existing connections.</span></span> <span data-ttu-id="61f00-127">La depuración admite todas las características habituales de depuración dentro de rutinas que se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="61f00-127">Debugging supports all common debugging features within routines executing on the server.</span></span> <span data-ttu-id="61f00-128">La interacción entre un depurador y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se produce mediante un modelo de objetos componentes (COM) distribuido.</span><span class="sxs-lookup"><span data-stu-id="61f00-128">The interaction between a debugger and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] happens through distributed Component Object Model (COM).</span></span>  
  
 <span data-ttu-id="61f00-129">Para obtener más información y escenarios sobre la depuración de procedimientos almacenados, funciones, desencadenadores, tipos definidos por el usuario y agregados administrados, vea el tema "[SQL Server la depuración de bases de datos de integración CLR](https://go.microsoft.com/fwlink/?LinkId=120378)" en la documentación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="61f00-129">For more information and scenarios about debugging managed stored procedures, functions, triggers, user-defined types, and aggregates, see the "[SQL Server CLR Integration Database Debugging](https://go.microsoft.com/fwlink/?LinkId=120378)" topic in the Visual Studio documentation.</span></span>  
  
 <span data-ttu-id="61f00-130">El protocolo de red TCP/IP debe estar habilitado en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a fin de utilizar Visual Studio para el desarrollo remoto, la depuración y el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="61f00-130">The TCP/IP network protocol must be enabled on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in order to use Visual Studio for remote development, debugging, and development.</span></span> <span data-ttu-id="61f00-131">Para obtener más información acerca de cómo habilitar el protocolo TCP/IP en el servidor, vea [configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="61f00-131">For more information about enabling TCP/IP protocol on the server, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
  
#### <a name="to-debug-a-managed-database-object"></a><span data-ttu-id="61f00-132">Para depurar un objeto de base de datos administrado</span><span class="sxs-lookup"><span data-stu-id="61f00-132">To debug a managed database object</span></span>  
  
1.  <span data-ttu-id="61f00-133">Abra Microsoft Visual Studio, cree un nuevo proyecto de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y establezca una conexión a una base de datos en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61f00-133">Open Microsoft Visual Studio, create a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] project, and establish a connection to a database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="61f00-134">Cree un nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="61f00-134">Create a new type.</span></span> <span data-ttu-id="61f00-135">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto, seleccione **Agregar** y **nuevo elemento.** .. En la **ventana Agregar nuevo elemento** , seleccione **procedimiento almacenado**, **función definida por el**usuario **, tipo definido por el usuario**, **desencadenador**, **agregado**o **clase**.</span><span class="sxs-lookup"><span data-stu-id="61f00-135">In **Solution Explorer**, right-click the project, select **Add** and **New Item...** From the **Add New Item** window, select **Stored Procedure**, **User-Defined Function**, **User-Defined Type**, **Trigger**, **Aggregate**, or **Class**.</span></span> <span data-ttu-id="61f00-136">Especifique un nombre para el archivo de origen del nuevo tipo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="61f00-136">Specify a name for the source file of the new type and click **Add**.</span></span>  
  
3.  <span data-ttu-id="61f00-137">Agregue código para el nuevo tipo al editor de texto.</span><span class="sxs-lookup"><span data-stu-id="61f00-137">Add code for the new type to the text editor.</span></span> <span data-ttu-id="61f00-138">En la sección que figura más adelante en este tema, puede ver el código de ejemplo de un procedimiento almacenado de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="61f00-138">For sample code for an example stored procedure, see the section later in this topic.</span></span>  
  
4.  <span data-ttu-id="61f00-139">Agregue un script que pruebe el tipo.</span><span class="sxs-lookup"><span data-stu-id="61f00-139">Add a script that tests the type.</span></span> <span data-ttu-id="61f00-140">En **Explorador de soluciones**, expanda el directorio **SecuenciasDePrueba** y haga doble clic en **Test. SQL** para abrir el archivo de origen del script de prueba predeterminado.</span><span class="sxs-lookup"><span data-stu-id="61f00-140">In **Solution Explorer**, expand the **TestScripts** directory double-click **Test.sql** to open the default test script source file.</span></span> <span data-ttu-id="61f00-141">Agregue al editor de texto el script de prueba, uno que llame al código que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="61f00-141">Add the test script, one that invokes the code to be debugged, to the text editor.</span></span> <span data-ttu-id="61f00-142">Vea más adelante un script de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="61f00-142">See below for a sample script.</span></span>  
  
5.  <span data-ttu-id="61f00-143">Coloque uno o más puntos de interrupción en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="61f00-143">Place one or more breakpoints in the source code.</span></span> <span data-ttu-id="61f00-144">Haga clic con el botón derecho en una línea de código en el editor de texto, dentro de la función o rutina que desea depurar, y seleccione **punto de interrupción** e **Insertar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="61f00-144">Right-click on a line of code in the text editor, within the function or routine you want to debug, and select **Breakpoint** and **Insert Breakpoint**.</span></span> <span data-ttu-id="61f00-145">Se agrega el punto de interrupción, resaltando la línea de código en rojo.</span><span class="sxs-lookup"><span data-stu-id="61f00-145">The breakpoint is added, highlighting the line of code in red.</span></span>  
  
6.  <span data-ttu-id="61f00-146">En el menú **depurar** , seleccione **iniciar depuración** para compilar, implementar y probar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="61f00-146">In the **Debug** menu, select **Start Debugging** to compile, deploy, and test the project.</span></span> <span data-ttu-id="61f00-147">Se ejecutará el script de prueba de Test.sql y se llamará al objeto de base de datos administrado.</span><span class="sxs-lookup"><span data-stu-id="61f00-147">The test script in Test.sql will be run and the managed database object will be invoked.</span></span>  
  
7.  <span data-ttu-id="61f00-148">Cuando la flecha amarilla que designa el puntero de instrucción aparece en el punto de interrupción, la ejecución del código se detiene y se puede empezar a depurar el objeto de base de datos administrado.</span><span class="sxs-lookup"><span data-stu-id="61f00-148">When the yellow arrow designating the instruction pointer appears at the breakpoint code execution pauses and you can begin debugging your managed database object.</span></span> <span data-ttu-id="61f00-149">Puede **recorrer paso a paso por procedimientos** desde el menú **depurar** para avanzar el puntero de instrucción hasta la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="61f00-149">You can **Step Over** from the **Debug** menu to advance the instruction pointer to the next line of code.</span></span> <span data-ttu-id="61f00-150">La ventana **variables locales** se usa para observar el estado de los objetos resaltados actualmente por el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="61f00-150">The **Locals** window is used to observe the state of the objects currently highlighted by the instruction pointer.</span></span> <span data-ttu-id="61f00-151">Se pueden agregar variables a la ventana **inspección** .</span><span class="sxs-lookup"><span data-stu-id="61f00-151">Variables can be added to the **Watch** window.</span></span> <span data-ttu-id="61f00-152">El estado de las variables inspeccionadas se puede observar en toda la sesión de depuración, no solo cuando la variable está en la línea de código resaltada actualmente por el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="61f00-152">The state of watched variables can be observed throughout the entire debugging session, not only when the variable is in the line of code currently highlighted by instruction pointer.</span></span> <span data-ttu-id="61f00-153">Seleccione Continuar en el menú Depurar para hacer avanzar el puntero de instrucción hasta el siguiente punto de interrupción o para completar la ejecución de la rutina si no hay más puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="61f00-153">Select Continue from the Debug menu to advance the instruction pointer to the next breakpoint or to complete execution of the routine if there are no more breakpoints.</span></span>  
  
### <a name="example"></a><span data-ttu-id="61f00-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f00-154">Example</span></span>  
 <span data-ttu-id="61f00-155">En el ejemplo siguiente se devuelve la versión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="61f00-155">The following example returns the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] version to the caller.</span></span>  
  
 <span data-ttu-id="61f00-156">C#</span><span class="sxs-lookup"><span data-stu-id="61f00-156">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void GetVersion()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version",  
                                           connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="61f00-157">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61f00-157">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Partial Public Class StoredProcedures   
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub GetVersion()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="61f00-158">A continuación se muestra un script de prueba que llama al procedimiento almacenado GetVersion definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="61f00-158">The following is a test script that invokes the GetVersion stored procedure defined above.</span></span>  
  
```  
EXEC GetVersion  
```  
  
## <a name="see-also"></a><span data-ttu-id="61f00-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61f00-159">See Also</span></span>  
 [<span data-ttu-id="61f00-160">Conceptos de programación en el ámbito de la integración de Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="61f00-160">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
