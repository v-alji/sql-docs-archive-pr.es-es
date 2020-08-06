---
title: Programar y depurar la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], debugging
- SSIS Script task, development environment
- SSIS Script task, debugging
- Script task [Integration Services], development environment
- Script task [Integration Services], coding
- debugging [Integration Services], scripts
- VSTA
- SSIS Script task, coding
ms.assetid: 687c262f-fcab-42e8-92ae-e956f3d92d69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f4383469368ac1fe3c70ff82f8c8bb2cf755838
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744205"
---
# <a name="coding-and-debugging-the-script-task"></a><span data-ttu-id="c5adb-102">Codificar y depurar la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-102">Coding and Debugging the Script Task</span></span>
  <span data-ttu-id="c5adb-103">Después de configurar la tarea Script en el **Editor de la tarea Script**, puede escribir el código personalizado en el entorno de desarrollo de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-103">After configuring the Script task in the **Script Task Editor**, you write your custom code in the Script task development environment.</span></span>

## <a name="script-task-development-environment"></a><span data-ttu-id="c5adb-104">Entorno de desarrollo de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-104">Script Task Development Environment</span></span>
 <span data-ttu-id="c5adb-105">La tarea Script usa [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) como el entorno de desarrollo del propio script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-105">The Script task uses [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) as the development environment for the script itself.</span></span>

 <span data-ttu-id="c5adb-106">El código de script se escribe en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="c5adb-106">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="c5adb-107">Puede especificar el lenguaje de script estableciendo la propiedad **ScriptLanguage** en el **Editor de la tarea Script**.</span><span class="sxs-lookup"><span data-stu-id="c5adb-107">You specify the script language by setting the **ScriptLanguage** property in the **Script Task Editor**.</span></span> <span data-ttu-id="c5adb-108">Si prefiere utilizar otro lenguaje de programación, puede desarrollar un ensamblado personalizado en el lenguaje seleccionado y utilizar su funcionalidad en el código de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-108">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script task.</span></span>

 <span data-ttu-id="c5adb-109">El script que crea en la tarea Script se almacena en la definición de paquete.</span><span class="sxs-lookup"><span data-stu-id="c5adb-109">The script that you create in the Script task is stored in the package definition.</span></span> <span data-ttu-id="c5adb-110">No hay un archivo de script independiente.</span><span class="sxs-lookup"><span data-stu-id="c5adb-110">There is no separate script file.</span></span> <span data-ttu-id="c5adb-111">Por consiguiente, el uso de la tarea Script no afecta a la implementación del paquete.</span><span class="sxs-lookup"><span data-stu-id="c5adb-111">Therefore, the use of the Script task does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="c5adb-112">Al diseñar el paquete y depurar el script, el código de script se escribe temporalmente en un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5adb-112">When you design the package and debug the script, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="c5adb-113">Dado que almacenar información confidencial en un archivo supone un riesgo potencial para la seguridad, recomendamos que no incluya información confidencial como contraseñas en el código de script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-113">Because storing sensitive information in a file is a potential security risk, we recommend that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="c5adb-114">De forma predeterminada, `Option Strict` está deshabilitada en el IDE.</span><span class="sxs-lookup"><span data-stu-id="c5adb-114">By default, `Option Strict` is disabled in the IDE.</span></span>

## <a name="script-task-project-structure"></a><span data-ttu-id="c5adb-115">Estructura del proyecto de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-115">Script Task Project Structure</span></span>
 <span data-ttu-id="c5adb-116">Al crear o modificar el script contenido en una tarea Script, VSTA abre un proyecto nuevo vacío o vuelve a abrir el proyecto existente.</span><span class="sxs-lookup"><span data-stu-id="c5adb-116">When you create or modify the script that is contained in a Script task, VSTA opens an empty new project or reopens the existing project.</span></span> <span data-ttu-id="c5adb-117">La creación de este proyecto VSTA no afecta a la implementación del paquete, porque el proyecto está guardado en el archivo empaquetado; la tarea Script no crea archivos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c5adb-117">The creation of this VSTA project does not affect the deployment of the package, because the project is saved inside the package file; the Script task does not create additional files.</span></span>

### <a name="project-items-and-classes-in-the-script-task-project"></a><span data-ttu-id="c5adb-118">Elementos y clases de proyecto en el proyecto de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-118">Project Items and Classes in the Script Task Project</span></span>
 <span data-ttu-id="c5adb-119">De forma predeterminada, el proyecto de la tarea Script mostrado en la ventana Explorador de proyectos de VSTA contiene un elemento único, `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="c5adb-119">By default, the Script task project displayed in the VSTA Project Explorer window contains a single item, `ScriptMain`.</span></span> <span data-ttu-id="c5adb-120">El elemento `ScriptMain`, a su vez, contiene una clase única, también denominada `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="c5adb-120">The `ScriptMain` item, in turn, contains a single class, also named `ScriptMain`.</span></span> <span data-ttu-id="c5adb-121">Los elementos de código de la clase varían, dependiendo del lenguaje de programación seleccionado para la tarea Script:</span><span class="sxs-lookup"><span data-stu-id="c5adb-121">The code elements in the class vary depending on the programming language that you selected for the Script task:</span></span>

-   <span data-ttu-id="c5adb-122">Cuando la tarea script está configurada para el [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] lenguaje de programación, la `ScriptMain` clase tiene una subrutina pública, `Main` .</span><span class="sxs-lookup"><span data-stu-id="c5adb-122">When the Script task is configured for the [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] programming language, the `ScriptMain` class has a public subroutine, `Main`.</span></span> <span data-ttu-id="c5adb-123">La subrutina `ScriptMain.Main` es el método al que el módulo ejecutable llama cuando ejecuta la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-123">The `ScriptMain.Main` subroutine is the method that the runtime calls when you run your Script task.</span></span>

     <span data-ttu-id="c5adb-124">De forma predeterminada, el único código de la subrutina `Main` de un script nuevo es la línea `Dts.TaskResult = ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="c5adb-124">By default, the only code in the `Main` subroutine of a new script is the line `Dts.TaskResult = ScriptResults.Success`.</span></span> <span data-ttu-id="c5adb-125">Esta línea informa al módulo ejecutable que la tarea se realizó correctamente en su operación.</span><span class="sxs-lookup"><span data-stu-id="c5adb-125">This line informs the runtime that the task was successful in its operation.</span></span> <span data-ttu-id="c5adb-126">La `Dts.TaskResult` propiedad se describe en [devolver los resultados de la tarea script](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="c5adb-126">The `Dts.TaskResult` property is discussed in [Returning Results from the Script Task](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>

-   <span data-ttu-id="c5adb-127">Cuando la tarea Script está configurada para el lenguaje de programación Visual C#, la clase `ScriptMain` tiene un método público `Main`.</span><span class="sxs-lookup"><span data-stu-id="c5adb-127">When the Script task is configured for the Visual C# programming language, the `ScriptMain` class has a public method, `Main`.</span></span> <span data-ttu-id="c5adb-128">Se llama al método cuando se ejecuta la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-128">The method is called when the Script task runs.</span></span>

     <span data-ttu-id="c5adb-129">De manera predeterminada, el método `Main` incluye la línea `Dts.TaskResult = (int)ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="c5adb-129">By default, the `Main` method includes the line `Dts.TaskResult = (int)ScriptResults.Success`.</span></span> <span data-ttu-id="c5adb-130">Esta línea informa al módulo ejecutable que la tarea se realizó correctamente en su operación.</span><span class="sxs-lookup"><span data-stu-id="c5adb-130">This line informs the runtime that the task was successful in its operation.</span></span>

 <span data-ttu-id="c5adb-131">El elemento `ScriptMain` puede contener clases que no sean la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="c5adb-131">The `ScriptMain` item can contain classes other than the `ScriptMain` class.</span></span> <span data-ttu-id="c5adb-132">Las clases solo están disponibles en la tarea Script en la que residen.</span><span class="sxs-lookup"><span data-stu-id="c5adb-132">Classes are available only to the Script task in which they reside.</span></span>

 <span data-ttu-id="c5adb-133">De forma predeterminada, el elemento de proyecto `ScriptMain` contiene el código siguiente generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c5adb-133">By default, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="c5adb-134">La plantilla de código también proporciona información general sobre la tarea Script, así como información adicional sobre cómo recuperar y manipular objetos SSIS, como variables, eventos y conexiones.</span><span class="sxs-lookup"><span data-stu-id="c5adb-134">The code template also provides an overview of the Script task, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Task
' Write scripts using Microsoft Visual Basic 2008.
' The ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Runtime.VSTAProxy

<System.AddIn.AddIn("ScriptMain", Version:="1.0", Publisher:="", Description:="")> _
Partial Class ScriptMain

Private Sub ScriptMain_Startup(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Startup

End Sub

Private Sub ScriptMain_Shutdown(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Shutdown
Try
' Unlock variables from the read-only and read-write variable collection properties
If (Dts.Variables.Count <> 0) Then
Dts.Variables.Unlock()
End If
Catch ex As Exception
        End Try
End Sub

Enum ScriptResults
Success = DTSExecResult.Success
Failure = DTSExecResult.Failure
End Enum

' The execution engine calls this method when the task executes.
' To access the object model, use the Dts property. Connections, variables, events,
' and logging features are available as members of the Dts property as shown in the following examples.
'
' To reference a variable, call Dts.Variables("MyCaseSensitiveVariableName").Value
' To post a log entry, call Dts.Log("This is my log text", 999, Nothing)
' To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, True)
'
' To use the connections collection use something like the following:
' ConnectionManager cm = Dts.Connections.Add("OLEDB")
' cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;"
'
' Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.
' 
' To open Help, press F1.

Public Sub Main()
'
' Add your code here
'
Dts.TaskResult = ScriptResults.Success
End Sub

End Class
```

```csharp
/*
   Microsoft SQL Server Integration Services Script Task
   Write scripts using Microsoft Visual C# 2008.
   The ScriptMain is the entry point class of the script.
*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Runtime.VSTAProxy;
using System.Windows.Forms;

namespace ST_1bcfdbad36d94f8ba9f23a10375abe53.csproj
{
    [System.AddIn.AddIn("ScriptMain", Version = "1.0", Publisher = "", Description = "")]
    public partial class ScriptMain
    {
        private void ScriptMain_Startup(object sender, EventArgs e)
        {

        }

        private void ScriptMain_Shutdown(object sender, EventArgs e)
        {
            try
            {
                // Unlock variables from the read-only and read-write variable collection properties
                if (Dts.Variables.Count != 0)
                {
                    Dts.Variables.Unlock();
                }
            }
            catch
            {
            }
        }

        #region VSTA generated code
        private void InternalStartup()
        {
            this.Startup += new System.EventHandler(ScriptMain_Startup);
            this.Shutdown += new System.EventHandler(ScriptMain_Shutdown);
        }
        enum ScriptResults
        {
            Success = DTSExecResult.Success,
            Failure = DTSExecResult.Failure
        };

        #endregion

        /*
The execution engine calls this method when the task executes.
To access the object model, use the Dts property. Connections, variables, events,
and logging features are available as members of the Dts property as shown in the following examples.

To reference a variable, call Dts.Variables["MyCaseSensitiveVariableName"].Value;
To post a log entry, call Dts.Log("This is my log text", 999, null);
To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, true);

To use the connections collection use something like the following:
ConnectionManager cm = Dts.Connections.Add("OLEDB");
cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;";

Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.

To open Help, press F1.
*/

        public void Main()
        {
            // TODO: Add your code here
            Dts.TaskResult = (int)ScriptResults.Success;
        }
    }
```

### <a name="additional-project-items-in-the-script-task-project"></a><span data-ttu-id="c5adb-135">Elementos de proyecto adicionales del proyecto de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-135">Additional Project Items in the Script Task Project</span></span>
 <span data-ttu-id="c5adb-136">El proyecto de la tarea Script puede incluir elementos distintos del elemento `ScriptMain` predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c5adb-136">The Script task project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="c5adb-137">Puede agregar clases, módulos y archivos de código al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5adb-137">You can add classes, modules, and code files to the project.</span></span> <span data-ttu-id="c5adb-138">También puede utilizar las carpetas para organizar los grupos de elementos.</span><span class="sxs-lookup"><span data-stu-id="c5adb-138">You can also use folders to organize groups of items.</span></span> <span data-ttu-id="c5adb-139">Todos los elementos que se agregan se conservan dentro del paquete.</span><span class="sxs-lookup"><span data-stu-id="c5adb-139">All the items that you add are persisted inside the package.</span></span>

### <a name="references-in-the-script-task-project"></a><span data-ttu-id="c5adb-140">Referencias en el proyecto de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-140">References in the Script Task Project</span></span>
 <span data-ttu-id="c5adb-141">Para agregar referencias a los ensamblados administrados, haga clic con el botón derecho en el proyecto de la tarea Script en el **Explorador de proyectos** y, después, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="c5adb-141">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="c5adb-142">Para obtener más información, consulte [Hacer referencia a otros ensamblados en soluciones de scripting](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="c5adb-142">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="c5adb-143">Puede ver las referencias de proyecto en el IDE de VSTA en la **Vista de clases** o en el **Explorador de proyectos**.</span><span class="sxs-lookup"><span data-stu-id="c5adb-143">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="c5adb-144">Puede abrir cualquiera de estas ventanas en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="c5adb-144">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="c5adb-145">Puede agregar una referencia nueva en el menú **Proyecto**, en el **Explorador de proyectos** o en **Vista de clases**.</span><span class="sxs-lookup"><span data-stu-id="c5adb-145">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-task"></a><span data-ttu-id="c5adb-146">Interactuar con el paquete de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-146">Interacting with the Package in the Script Task</span></span>
 <span data-ttu-id="c5adb-147">La tarea Script utiliza el objeto `Dts` global, que es una instancia de la clase <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> y sus miembros para interactuar con el paquete contenedor y con el módulo ejecutable de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5adb-147">The Script task uses the global `Dts` object, which is an instance of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, and its members to interact with the containing package and with the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

 <span data-ttu-id="c5adb-148">En la tabla siguiente se enumeran los miembros públicos principales de la clase <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, que se expone al código de la tarea Script a través del objeto `Dts` global.</span><span class="sxs-lookup"><span data-stu-id="c5adb-148">The following table lists the principal public members of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, which is exposed to Script task code through the global `Dts` object.</span></span> <span data-ttu-id="c5adb-149">Los temas de esta sección describen con más detalle el uso de estos miembros.</span><span class="sxs-lookup"><span data-stu-id="c5adb-149">The topics in this section discuss the use of these members in more detail.</span></span>

|<span data-ttu-id="c5adb-150">Member</span><span class="sxs-lookup"><span data-stu-id="c5adb-150">Member</span></span>|<span data-ttu-id="c5adb-151">Propósito</span><span class="sxs-lookup"><span data-stu-id="c5adb-151">Purpose</span></span>|
|------------|-------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>|<span data-ttu-id="c5adb-152">Proporciona acceso a los administradores de conexión definidos en el paquete.</span><span class="sxs-lookup"><span data-stu-id="c5adb-152">Provides access to connection managers defined in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>|<span data-ttu-id="c5adb-153">Proporciona una interfaz de eventos que permite a la tarea Script generar errores, advertencias y mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="c5adb-153">Provides an events interface to let the Script task raise errors, warnings, and informational messages.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>|<span data-ttu-id="c5adb-154">Proporciona una manera simple de devolver un objeto único al módulo ejecutable (además de `TaskResult`) que también se puede utilizar para la bifurcación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c5adb-154">Provides a simple way to return a single object to the runtime (in addition to the `TaskResult`) that can also be used for workflow branching.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>|<span data-ttu-id="c5adb-155">Registra información como el progreso y los resultados de las tareas en proveedores de registro habilitados.</span><span class="sxs-lookup"><span data-stu-id="c5adb-155">Logs information such as task progress and results to enabled log providers.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>|<span data-ttu-id="c5adb-156">Informa del éxito o error de la tarea.</span><span class="sxs-lookup"><span data-stu-id="c5adb-156">Reports the success or failure of the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Transaction%2A>|<span data-ttu-id="c5adb-157">Proporciona la transacción, si hay alguna, dentro de la que el contenedor de la tarea se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c5adb-157">Provides the transaction, if any, within which the task's container is running.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>|<span data-ttu-id="c5adb-158">Proporciona acceso a las variables enumeradas en las propiedades de tarea `ReadOnlyVariables` y `ReadWriteVariables` para su uso en el script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-158">Provides access to the variables listed in the `ReadOnlyVariables` and `ReadWriteVariables` task properties for use within the script.</span></span>|

 <span data-ttu-id="c5adb-159">La clase <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> contiene también algunos miembros públicos que probablemente no utilizará.</span><span class="sxs-lookup"><span data-stu-id="c5adb-159">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class also contains some public members that you will probably not use.</span></span>

|<span data-ttu-id="c5adb-160">Member</span><span class="sxs-lookup"><span data-stu-id="c5adb-160">Member</span></span>|<span data-ttu-id="c5adb-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5adb-161">Description</span></span>|
|------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>|<span data-ttu-id="c5adb-162">La propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> proporciona un acceso más cómodo a las variables.</span><span class="sxs-lookup"><span data-stu-id="c5adb-162">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property provides more convenient access to variables.</span></span> <span data-ttu-id="c5adb-163">Aunque puede utilizar <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, debe llamar explícitamente a los métodos para bloquear y desbloquear las variables para leer y escribir.</span><span class="sxs-lookup"><span data-stu-id="c5adb-163">Although you can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must explicitly call methods to lock and unlock variables for reading and writing.</span></span> <span data-ttu-id="c5adb-164">La tarea Script controla la semántica de bloqueo automáticamente cuando usa la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5adb-164">The Script task handles locking semantics for you when you use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property.</span></span>|

## <a name="debugging-the-script-task"></a><span data-ttu-id="c5adb-165">Depurar la tarea Script</span><span class="sxs-lookup"><span data-stu-id="c5adb-165">Debugging the Script Task</span></span>
 <span data-ttu-id="c5adb-166">Para depurar el código de la tarea Script, establezca al menos un punto de interrupción en el código y, a continuación, cierre el IDE de VSTA para ejecutar el paquete en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5adb-166">To debug the code in your Script task, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c5adb-167">Cuando la ejecución del paquete entra en la tarea Script, el IDE de VSTA se vuelve a abrir y muestra el código en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c5adb-167">When package execution enters the Script task, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="c5adb-168">Después de que la ejecución llega al punto de interrupción, puede examinar los valores de variable y completar el código restante.</span><span class="sxs-lookup"><span data-stu-id="c5adb-168">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!WARNING]
>  <span data-ttu-id="c5adb-169">Puede depurar la tarea Script al ejecutar el paquete en modo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c5adb-169">You can debug the Script task when you run the package in 64-bit mode.</span></span>

> [!NOTE]
>  <span data-ttu-id="c5adb-170">Debe ejecutar el paquete para depurar en la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-170">You must execute the package to debug into your Script task.</span></span> <span data-ttu-id="c5adb-171">Si ejecuta solamente la tarea individual, se pasan por alto los puntos de interrupción del código de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-171">If you execute only the individual task, breakpoints in the Script task code are ignored.</span></span>

> [!NOTE]
>  <span data-ttu-id="c5adb-172">No puede depurar una tarea Script al ejecutar esta última como parte de un paquete secundario que se ejecuta desde una tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="c5adb-172">You cannot debug a Script task when you run the Script task as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="c5adb-173">Los puntos de interrupción establecidos en la tarea Script del paquete secundario se descartan en estas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="c5adb-173">Breakpoints that you set in the Script task in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="c5adb-174">Puede depurar el paquete secundario ejecutándolo normalmente por separado.</span><span class="sxs-lookup"><span data-stu-id="c5adb-174">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="c5adb-175">Al depurar un paquete que contiene varias tareas Script, el depurador depura una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="c5adb-175">When you debug a package that contains multiple Script tasks, the debugger debugs one Script task.</span></span> <span data-ttu-id="c5adb-176">El sistema puede depurar otra tarea Script si el depurador se completa, como en el caso de un bucle Foreach o un contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="c5adb-176">The system can debug another Script task if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

## <a name="external-resources"></a><span data-ttu-id="c5adb-177">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="c5adb-177">External Resources</span></span>

-   <span data-ttu-id="c5adb-178">Entrada de blog, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661) (Problemas de instalación y configuración de VSTA en instalaciones de SSIS 2008 y R2), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="c5adb-178">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="c5adb-179">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c5adb-179">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c5adb-180">Para obtener las descargas, los artículos, los ejemplos y los vídeos más recientes de [!INCLUDE[msCoName](../../../includes/msconame-md.md)], así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="c5adb-180">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c5adb-181">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="c5adb-181">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c5adb-182">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="c5adb-182">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5adb-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5adb-183">See Also</span></span>
 <span data-ttu-id="c5adb-184">[Hacer referencia a otros ensamblados en soluciones de scripting](../referencing-other-assemblies-in-scripting-solutions.md) [configurar la tarea script en el editor de la tarea script](configuring-the-script-task-in-the-script-task-editor.md)</span><span class="sxs-lookup"><span data-stu-id="c5adb-184">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) [Configuring the Script Task in the Script Task Editor](configuring-the-script-task-in-the-script-task-editor.md)</span></span>


