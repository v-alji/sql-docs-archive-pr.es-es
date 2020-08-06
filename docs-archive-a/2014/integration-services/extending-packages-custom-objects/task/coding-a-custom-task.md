---
title: Programar una tarea personalizada | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Validate method
- custom tasks [Integration Services], validating
- validation [Integration Services], design-time tasks
- SSIS custom tasks, validating
ms.assetid: dc224f4f-b339-4eb6-a008-1b4fe0ea4fd2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c369f4a7e8352be7ddde9e2e3938b47b0bcc1349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674219"
---
# <a name="coding-a-custom-task"></a><span data-ttu-id="dd3e9-102">Codificar una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="dd3e9-102">Coding a Custom Task</span></span>
  <span data-ttu-id="dd3e9-103">Una vez que haya creado una clase que herede de la clase base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) y haya aplicado el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> a la clase, debe invalidar la implementación de las propiedades y los métodos de la clase base para proporcionar la funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-103">After you have created a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>

## <a name="configuring-the-task"></a><span data-ttu-id="dd3e9-104">Configurar la tarea</span><span class="sxs-lookup"><span data-stu-id="dd3e9-104">Configuring the Task</span></span>

### <a name="validating-the-task"></a><span data-ttu-id="dd3e9-105">Validar la tarea</span><span class="sxs-lookup"><span data-stu-id="dd3e9-105">Validating the Task</span></span>
 <span data-ttu-id="dd3e9-106">Al diseñar un paquete de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], puede usar la validación para comprobar la configuración en cada tarea, de manera que pueda detectar los valores incorrectos o inadecuados en cuanto se establezcan, en lugar de buscar todos los errores solo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-106">When you are designing an [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package, you can use validation to verify settings on each task, so that you can catch incorrect or inappropriate settings as soon as they are set, instead of finding all errors at run-time only.</span></span> <span data-ttu-id="dd3e9-107">El propósito de la validación es determinar si la tarea contiene conexiones o valores no válidos que impedirán que se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-107">The purpose of validation is to determine whether the task contains invalid settings or connections that will prevent it from running successfully.</span></span> <span data-ttu-id="dd3e9-108">De esta manera se garantiza que el paquete contiene tareas con muchas posibilidades de que se ejecuten en su primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-108">This makes sure that the package contains tasks that have a good chance of running on their first run.</span></span>

 <span data-ttu-id="dd3e9-109">Puede implementar la validación mediante el método `Validate` en código personalizado.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-109">You can implement validation by using the `Validate` method in custom code.</span></span> <span data-ttu-id="dd3e9-110">El motor en tiempo de ejecución valida una tarea mediante una llamada al método `Validate` en la tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-110">The run-time engine validates a task by calling the `Validate` method on the task.</span></span> <span data-ttu-id="dd3e9-111">Es responsabilidad del programador de la tarea definir los criterios que dan como correcta o errónea una validación de tarea, así como notificar el motor en tiempo de ejecución del resultado de esta evaluación.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-111">It is the responsibility of the task developer to define the criteria that give you a successful or failed task validation, and to notify the run-time engine of the result of this evaluation.</span></span>

#### <a name="task-abstract-base-class"></a><span data-ttu-id="dd3e9-112">Clase base abstracta Task</span><span class="sxs-lookup"><span data-stu-id="dd3e9-112">Task Abstract Base Class</span></span>
 <span data-ttu-id="dd3e9-113">La clase base abstracta [Microsoft. SqlServer. DTS. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) proporciona el `Validate` método que invalida cada tarea para definir sus criterios de validación.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-113">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) abstract base class provides the `Validate` method that each task overrides to define its validation criteria.</span></span> <span data-ttu-id="dd3e9-114">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] llama automáticamente varias veces al método `Validate` durante el diseño del paquete y, cuando se producen advertencias o errores, proporciona al usuario indicaciones visuales que le sirven de ayuda para identificar cualquier problema con la configuración de la tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-114">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer automatically calls the `Validate` method multiple times during package design, and provides visual cues to the user when warnings or errors occur to help identify problems with the configuration of the task.</span></span> <span data-ttu-id="dd3e9-115">Las tareas proporcionan los resultados de la validación devolviendo un valor de la enumeración <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> y provocando eventos de errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-115">Tasks provide validation results by returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and by raising warning and error events.</span></span> <span data-ttu-id="dd3e9-116">Estos eventos contienen información que se muestra al usuario en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd3e9-116">These events contain information that is displayed to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="dd3e9-117">A continuación, se enumeran algunos ejemplos de validación:</span><span class="sxs-lookup"><span data-stu-id="dd3e9-117">Some examples for validation follow:</span></span>

-   <span data-ttu-id="dd3e9-118">Un administrador de conexiones valida el nombre de archivo específico.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-118">A connection manager validates the specific file name.</span></span>

-   <span data-ttu-id="dd3e9-119">Un administrador de conexiones valida que el tipo de entrada es el tipo esperado, como un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-119">A connection manager validates that the type of input is the expected type, such as an XML file.</span></span>

-   <span data-ttu-id="dd3e9-120">Una tarea que espera la base de datos de entrada comprueba que no puede recibir datos de una conexión que no corresponde a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-120">A task that expects database input verifies that it cannot receive data from a non-database connection.</span></span>

-   <span data-ttu-id="dd3e9-121">Una tarea garantiza que ninguno de sus propiedades contradice otras propiedades establecidas en la misma tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-121">A task guarantees that none of its properties contradicts other properties set on the same task.</span></span>

-   <span data-ttu-id="dd3e9-122">Una tarea garantiza que están disponibles todos los recursos necesarios que usa la tarea en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-122">A task guarantees that all required resources used by the task at execution time are available.</span></span>

 <span data-ttu-id="dd3e9-123">El rendimiento es algo que hay que tener en cuenta para determinar lo que se valida y lo que no.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-123">Performance is something to consider in determining what is validated and what is not.</span></span> <span data-ttu-id="dd3e9-124">Por ejemplo, la entrada para una tarea podría ser una conexión a través de una red que tiene poco ancho banda o mucha intensidad de tráfico.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-124">For example, the input to a task might be a connection over a network that has low bandwidth or heavy traffic.</span></span> <span data-ttu-id="dd3e9-125">La validación puede tardar varios segundos para procesar si decide validar que el recurso está disponible.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-125">The validation may take several seconds to process if you decide to validate that the resource is available.</span></span> <span data-ttu-id="dd3e9-126">Otra validación puede producir un viaje de ida y vuelta (round trip) a un servidor de gran demanda y la rutina de validación podría ser lenta.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-126">Another validation may cause a round-trip to a server that is in high demand, and the validation routine might be slow.</span></span> <span data-ttu-id="dd3e9-127">Aunque hay muchas propiedades y configuraciones que se pueden validar, no se debería validar todo.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-127">Although there are many properties and settings that can be validated, not everything should be validated.</span></span>

-   <span data-ttu-id="dd3e9-128"><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> también llama al código del método `Validate` antes de que se ejecute la tarea, y la clase base <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancela la ejecución si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-128">The code in the `Validate` method is also called by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> before the task is run, and the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancels execution if validation fails.</span></span>

#### <a name="user-interface-considerations-during-validation"></a><span data-ttu-id="dd3e9-129">Consideraciones de interfaz de usuario durante la validación</span><span class="sxs-lookup"><span data-stu-id="dd3e9-129">User Interface Considerations during Validation</span></span>
 <span data-ttu-id="dd3e9-130">[Microsoft. SqlServer. DTS. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) incluye una <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interfaz como parámetro para el `Validate` método.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-130">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) includes an <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface as a parameter to the `Validate` method.</span></span> <span data-ttu-id="dd3e9-131">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contiene los métodos a los que llama la tarea para producir eventos en el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-131">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the methods that are called by the task in order to raise events to the run-time engine.</span></span> <span data-ttu-id="dd3e9-132">Se llama a los métodos <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> cuando se produce una advertencia o condición de error durante la validación.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-132">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods are called when a warning or error condition occurs during validation.</span></span> <span data-ttu-id="dd3e9-133">Ambos métodos de advertencia requieren los mismos parámetros que incluyen un código de error, componente de origen, descripción, archivo de Ayuda e información de contexto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-133">Both warning methods require the same parameters, which include an error code, source component, description, Help file, and Help context information.</span></span> <span data-ttu-id="dd3e9-134">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] usa esta información para mostrar indicaciones visuales en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-134">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses this information to display visual cues on the design surface.</span></span> <span data-ttu-id="dd3e9-135">Las indicaciones visuales que proporciona el diseñador incluyen un icono de exclamación que aparece junto a la tarea en la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-135">The visual cues that are provided by the designer include an exclamation icon that appears next to the task on the designer surface.</span></span> <span data-ttu-id="dd3e9-136">Esta indicación visual muestra al usuario que la tarea requiere configuración adicional antes de que la ejecución pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-136">This visual cue signals to the user that the task requires additional configuration before execution can continue.</span></span>

 <span data-ttu-id="dd3e9-137">El icono de exclamación también muestra una información sobre herramientas que contiene un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-137">The exclamation icon also displays a ToolTip that contains an error message.</span></span> <span data-ttu-id="dd3e9-138">La tarea proporciona el mensaje de error en el parámetro de descripción del evento.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-138">The error message is provided by the task in the description parameter of the event.</span></span> <span data-ttu-id="dd3e9-139">Los mensajes de error también se muestran en el panel **Lista de tareas** de [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], que proporciona al usuario una ubicación central para ver todos los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-139">Error messages are also displayed in the **Task List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], providing the user with a central location for viewing all validation errors.</span></span>

#### <a name="validation-example"></a><span data-ttu-id="dd3e9-140">Ejemplo de validación</span><span class="sxs-lookup"><span data-stu-id="dd3e9-140">Validation Example</span></span>
 <span data-ttu-id="dd3e9-141">En el ejemplo de código siguiente se muestra una tarea con una propiedad `UserName`.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-141">The following code example shows a task with a `UserName` property.</span></span> <span data-ttu-id="dd3e9-142">Esta propiedad se ha especificado como la propiedad necesaria para que la validación sea correcta.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-142">This property has been specified as required for validation to succeed.</span></span> <span data-ttu-id="dd3e9-143">Si no se establece la propiedad, la tarea expone un error y devuelve <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> de la enumeración <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-143">If the property is not set, the task posts an error, and returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span> <span data-ttu-id="dd3e9-144">El método `Validate` se ajusta en un bloque try/catch y produce un error en la validación si se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-144">The `Validate` method is wrapped in a try/catch block, and fails validation if an exception occurs.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string userName = "";

  public override DTSExecResult Validate(Connections connections,
     VariableDispenser variableDispenser, IDTSComponentEvents events,
     IDTSLogging log)
  {
    try
    {
      if (this.userName == "")
      {
        //   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0);
        //   Fail validation.
        return DTSExecResult.Failure;
      }
      //   Return success.
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string UserName
  {
    get
    {
      return this.userName;
    }
    set
    {
      this.userName = value;
    }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _userName As String = ""

  Public Overrides Function Validate(ByVal connections As Connections, _
     ByVal variableDispenser As VariableDispenser, _
     ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging) As DTSExecResult

    Try
      If Me._userName = "" Then
        '   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0)
        '   Fail validation.
        Return DTSExecResult.Failure
      End If
      '   Return success.
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property UserName() As String
    Get
      Return Me._userName
    End Get
    Set(ByVal Value As String)
      Me._userName = Value
    End Set
  End Property

End Class
```

### <a name="persisting-the-task"></a><span data-ttu-id="dd3e9-145">Conservar la tarea</span><span class="sxs-lookup"><span data-stu-id="dd3e9-145">Persisting the Task</span></span>
 <span data-ttu-id="dd3e9-146">Normalmente, no tiene que implementar la persistencia personalizada para una tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-146">Ordinarily you do not have to implement custom persistence for a task.</span></span> <span data-ttu-id="dd3e9-147">Solo se requiere la persistencia personalizada cuando las propiedades de un objeto usan tipos de datos complejos.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-147">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="dd3e9-148">Para obtener más información, vea [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) (Desarrollar objetos personalizados para Integration Services).</span><span class="sxs-lookup"><span data-stu-id="dd3e9-148">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>

## <a name="executing-the-task"></a><span data-ttu-id="dd3e9-149">Ejecutar la tarea</span><span class="sxs-lookup"><span data-stu-id="dd3e9-149">Executing the Task</span></span>
 <span data-ttu-id="dd3e9-150">En esta sección se describe cómo usar el método `Execute` que las tareas heredan e invalidan.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-150">This section describes how to use the `Execute` method that is inherited and overridden by tasks.</span></span> <span data-ttu-id="dd3e9-151">En esta sección también se explican varias maneras de proporcionar información sobre los resultados de la ejecución de la tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-151">This section also explains various ways of providing information about the results of task execution.</span></span>

### <a name="execute-method"></a><span data-ttu-id="dd3e9-152">Método Execute</span><span class="sxs-lookup"><span data-stu-id="dd3e9-152">Execute Method</span></span>
 <span data-ttu-id="dd3e9-153">Las tareas que están incluidas en un paquete se ejecutan cuando el tiempo de ejecución de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] llama a su método `Execute`.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-153">Tasks that are contained in a package run when the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls their `Execute` method.</span></span> <span data-ttu-id="dd3e9-154">Las tareas implementan su lógica de negocios y funcionalidad principales en este método, y proporcionan los resultados de la ejecución mediante la publicación de mensajes, la devolución de un valor de la <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeración y la invalidación de la propiedad `get` de la `ExecutionValue` propiedad.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-154">Tasks implement their core business logic and functionality in this method, and provide the results of execution by posting messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and overriding the property `get` of the `ExecutionValue` property.</span></span>

 <span data-ttu-id="dd3e9-155">La clase base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) proporciona una implementación predeterminada del método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-155">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class provides a default implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="dd3e9-156">Las tareas personalizadas invalidan este método para definir su funcionalidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-156">The custom tasks override this method to define their run-time functionality.</span></span> <span data-ttu-id="dd3e9-157">El objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> ajusta la tarea, aislándola del motor en tiempo de ejecución y de los demás objetos del paquete.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-157">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object wraps the task, isolating it from the run-time engine and the other objects in the package.</span></span> <span data-ttu-id="dd3e9-158">Debido a este aislamiento, la tarea no es consciente de su ubicación en el paquete con respecto a su orden de ejecución, y se ejecuta únicamente cuando se llama por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-158">Because of this isolation, the task is unaware of its location in the package with regard to its execution order, and runs only when it is called by the runtime.</span></span> <span data-ttu-id="dd3e9-159">Esta arquitectura evita los problemas que se pueden producir cuando las tareas modifican el paquete durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-159">This architecture prevents problems that can occur when tasks modify the package during execution.</span></span> <span data-ttu-id="dd3e9-160">La tarea proporciona acceso a los demás objetos del paquete únicamente a través de los objetos que se le suministran como parámetros en el método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-160">The task is provided access to the other objects in the package only through the objects supplied to it as parameters in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="dd3e9-161">Estos parámetros permiten que las tareas produzcan eventos, escriban las entradas en el registro de eventos, tengan acceso a la colección de variables y den de alta las conexiones a los orígenes de datos en transacciones, a la vez que se mantiene todavía el aislamiento necesario para garantizar la estabilidad y confiabilidad del paquete.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-161">These parameters let tasks raise events, write entries to the event log, access the variables collection, and enlist connections to data sources in transactions, while still maintaining the isolation that is necessary to guarantee the stability and reliability of the package.</span></span>

 <span data-ttu-id="dd3e9-162">En la tabla siguiente se enumeran los parámetros que se proporcionan a la tarea en el método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-162">The following table lists the parameters provided to the task in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>

|<span data-ttu-id="dd3e9-163">Parámetro</span><span class="sxs-lookup"><span data-stu-id="dd3e9-163">Parameter</span></span>|<span data-ttu-id="dd3e9-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd3e9-164">Description</span></span>|
|---------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Runtime.Connections>|<span data-ttu-id="dd3e9-165">Contiene una colección de objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> disponibles para la tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-165">Contains a collection of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects available to the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.VariableDispenser>|<span data-ttu-id="dd3e9-166">Contiene las variables disponibles para la tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-166">Contains the variables available to the task.</span></span> <span data-ttu-id="dd3e9-167">Las tareas usan variables a través de VariableDispenser; las tareas no usan directamente las variables.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-167">The tasks use variables through the VariableDispenser; the tasks do not use variables directly.</span></span> <span data-ttu-id="dd3e9-168">VariableDispenser bloquea y desbloquea las variables y evita los interbloqueos o sobrescrituras.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-168">The variable dispenser locks and unlocks variables, and prevents deadlocks or overwrites.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>|<span data-ttu-id="dd3e9-169">Contiene los métodos que la tarea llama para producir eventos en el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-169">Contains the methods called by the task to raise events to the run-time engine.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSLogging>|<span data-ttu-id="dd3e9-170">Contiene los métodos y propiedades que usa la tarea para escribir entradas en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-170">Contains methods and properties used by the task to write entries to the event log.</span></span>|
|<span data-ttu-id="dd3e9-171">Object</span><span class="sxs-lookup"><span data-stu-id="dd3e9-171">Object</span></span>|<span data-ttu-id="dd3e9-172">Contiene el objeto de transacción del que forma parte el contenedor, si existe.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-172">Contains the transaction object that the container is a part of, if any.</span></span> <span data-ttu-id="dd3e9-173">Este valor se pasa como un parámetro al método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> de un objeto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-173">This value is passed as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object.</span></span>|

### <a name="providing-execution-feedback"></a><span data-ttu-id="dd3e9-174">Proporcionar comentarios de ejecución</span><span class="sxs-lookup"><span data-stu-id="dd3e9-174">Providing Execution Feedback</span></span>
 <span data-ttu-id="dd3e9-175">Las tareas ajustan su código en bloques `try/catch` para evitar que se generen excepciones en el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-175">Tasks wrap their code in `try/catch` blocks to prevent exceptions from being raised to the run-time engine.</span></span> <span data-ttu-id="dd3e9-176">Esto asegura que el paquete termina la ejecución y no se detiene de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-176">This ensures that the package finishes execution and does not stop unexpectedly.</span></span> <span data-ttu-id="dd3e9-177">Sin embargo, el motor en tiempo de ejecución proporciona otros mecanismos para controlar las condiciones de error que se pueden producir durante la ejecución de una tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-177">However, the run-time engine provides other mechanisms for handling error conditions that can occur during the execution of a task.</span></span> <span data-ttu-id="dd3e9-178">Estos mecanismos incluyen la exposición de mensajes de error y advertencia, la devolución de un valor de la estructura <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, la exposición de mensajes, la devolución del valor <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> y la divulgación de información acerca de los resultados de ejecución de la tarea a través de la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-178">These include posting error and warning messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> structure, posting messages, returning the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value, and disclosing information about the results of task execution through the <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A> property.</span></span>

 <span data-ttu-id="dd3e9-179">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contiene los métodos <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>, a los que la tarea puede llamar para exponer mensajes de error y advertencia en el motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-179">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods, which can be called by the task to post error and warning messages to the run-time engine.</span></span> <span data-ttu-id="dd3e9-180">Ambos métodos requieren parámetros como el código de error, componente de origen, descripción, archivo de Ayuda e información de contexto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-180">Both methods require parameters such as the error code, source component, description, Help file, and help context information.</span></span> <span data-ttu-id="dd3e9-181">Dependiendo de la configuración de la tarea, el tiempo de ejecución responde a estos mensajes provocando eventos y puntos de interrupción o escribiendo información en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-181">Depending on the configuration of the task, the runtime responds to these messages by raising events and breakpoints, or by writing information to the event log.</span></span>

 <span data-ttu-id="dd3e9-182"><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> también facilita la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> que se usa para proporcionar la información adicional sobre los resultados de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-182">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> also provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property that can be used to provide additional information about the results of execution.</span></span> <span data-ttu-id="dd3e9-183">Por ejemplo, si una tarea elimina las filas de una tabla como parte de su método `Execute`, podría devolver el número de filas eliminadas como el valor de la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-183">For example, if a task deletes rows from a table as part of its `Execute` method, it might return the number of rows deleted as the value of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property.</span></span> <span data-ttu-id="dd3e9-184">Además, <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> proporciona la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-184">In addition, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A> property.</span></span> <span data-ttu-id="dd3e9-185">Esta propiedad permite al usuario asignar la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> que devuelve la tarea a cualquier variable visible en la tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-185">This property lets the user map the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> returned from the task to any variable visible to the task.</span></span> <span data-ttu-id="dd3e9-186">En ese momento la variable especificada se puede usar para establecer las restricciones de precedencia entre las tareas.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-186">The specified variable can then be used to establish precedence constraints between tasks.</span></span>

### <a name="execution-example"></a><span data-ttu-id="dd3e9-187">Ejemplo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dd3e9-187">Execution Example</span></span>
 <span data-ttu-id="dd3e9-188">En el ejemplo de código siguiente se muestra una implementación del método `Execute` y se expone una propiedad `ExecutionValue` invalidada.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-188">The following code example demonstrates an implementation of the `Execute` method, and shows an overridden `ExecutionValue` property.</span></span> <span data-ttu-id="dd3e9-189">La tarea elimina el archivo que especifica la propiedad `fileName` de la tarea.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-189">The task deletes the file that is specified by the `fileName` property of the task.</span></span> <span data-ttu-id="dd3e9-190">La tarea expone una advertencia si el archivo no existe, o si la propiedad `fileName` es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-190">The task posts a warning if the file does not exist, or if the `fileName` property is an empty string.</span></span> <span data-ttu-id="dd3e9-191">La tarea devuelve un valor `Boolean` en la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> para indicar si se eliminó el archivo.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-191">The task returns a `Boolean` value in the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property to indicate whether the file was deleted.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string fileName = "";
  private bool fileDeleted = false;

  public override DTSExecResult Execute(Connections cons,
     VariableDispenser vars, IDTSComponentEvents events,
     IDTSLogging log, Object txn)
  {
    try
    {
      if (this.fileName == "")
      {
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0);
        this.fileDeleted = false;
      }
      else
      {
        if (System.IO.File.Exists(this.fileName))
        {
          System.IO.File.Delete(this.fileName);
          this.fileDeleted = true;
        }
        else
          this.fileDeleted = false;
      }
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string FileName
  {
    get { return this.fileName; }
    set { this.fileName = value; }
  }
  public override object ExecutionValue
  {
    get { return this.fileDeleted; }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _fileName As String = ""
  Private _fileDeleted As Boolean = False

  Public Overrides Function Execute(ByVal cons As Connections, _
     ByVal vars As VariableDispenser, ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging, ByVal txn As Object) As DTSExecResult

    Try
      If Me._fileName = "" Then
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0)
        Me._fileDeleted = False
      Else
        If System.IO.File.Exists(Me._fileName) Then
          System.IO.File.Delete(Me._fileName)
          Me._fileDeleted = True
        Else
          Me._fileDeleted = False
        End If
      End If
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property FileName() As String
    Get
      Return Me._fileName
    End Get
    Set(ByVal Value As String)
      Me._fileName = Value
    End Set
  End Property

  Public Overrides ReadOnly Property ExecutionValue() As Object
    Get
      Return Me._fileDeleted
    End Get
  End Property

End Class
```

<span data-ttu-id="dd3e9-192">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dd3e9-192">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dd3e9-193">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="dd3e9-193">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dd3e9-194">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="dd3e9-194">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dd3e9-195">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="dd3e9-195">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd3e9-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd3e9-196">See Also</span></span>
 <span data-ttu-id="dd3e9-197">[Crear una tarea personalizada](creating-a-custom-task.md) [codificación de una tarea personalizada](coding-a-custom-task.md) [desarrollar una interfaz de usuario para una tarea personalizada](developing-a-user-interface-for-a-custom-task.md)</span><span class="sxs-lookup"><span data-stu-id="dd3e9-197">[Creating a Custom Task](creating-a-custom-task.md) [Coding a Custom Task](coding-a-custom-task.md) [Developing a User Interface for a Custom Task](developing-a-user-interface-for-a-custom-task.md)</span></span>


