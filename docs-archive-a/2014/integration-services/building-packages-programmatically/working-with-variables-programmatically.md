---
title: Trabajar con variables mediante programación | Microsoft Docs
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
- System namespace
- scope [Integration Services]
- variables [Integration Services], programmatically
- configuration files [Integration Services]
- Variables collection
- User namespace
- custom variables [Integration Services]
- variables [Integration Services], customizing
ms.assetid: c4b76a3d-94ca-4a8e-bb45-cb8bd0ea3ec1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c903ee6adb8989eaeb93efbe943eca93c73eae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748890"
---
# <a name="working-with-variables-programmatically"></a><span data-ttu-id="a5ee9-102">Trabajar con variables mediante programación</span><span class="sxs-lookup"><span data-stu-id="a5ee9-102">Working with Variables Programmatically</span></span>
  <span data-ttu-id="a5ee9-103">Las variables son una manera de establecer valores y controlar procesos en paquetes, contenedores, tareas y controladores de eventos de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-103">Variables are a way to dynamically set values and control processes in packages, containers, tasks, and event handlers.</span></span> <span data-ttu-id="a5ee9-104">Las restricciones de precedencia también pueden usar variables para controlar la dirección del flujo de datos en diferentes tareas.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-104">Variables can also be used by precedence constraints to control the direction of the flow of data to different tasks.</span></span> <span data-ttu-id="a5ee9-105">Las variables tienen diversos usos:</span><span class="sxs-lookup"><span data-stu-id="a5ee9-105">Variables have a variety of uses:</span></span>

-   <span data-ttu-id="a5ee9-106">Actualizan las propiedades de un paquete en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-106">Update properties of a package at run time.</span></span>

-   <span data-ttu-id="a5ee9-107">Rellenan los valores de parámetros para instrucciones Transact-SQL en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-107">Populate parameter values for Transact-SQL statements at run time.</span></span>

-   <span data-ttu-id="a5ee9-108">Controlan el flujo de un bucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-108">Control the flow of a Foreach loop.</span></span> <span data-ttu-id="a5ee9-109">Para obtener más información, consulte [Agregar enumeración a un flujo de control](../control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-109">For more information, see [Add Enumeration to a Control Flow](../control-flow/control-flow.md).</span></span>

-   <span data-ttu-id="a5ee9-110">Controlan una restricción de precedencia por su uso en una expresión.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-110">Control a precedence constraint by its use in an expression.</span></span> <span data-ttu-id="a5ee9-111">Una restricción de precedencia puede incluir variables en la definición de restricción.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-111">A precedence constraint can include variables in the constraint definition.</span></span> <span data-ttu-id="a5ee9-112">Para obtener más información, vea [Agregar expresiones a las restricciones de precedencia](../control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-112">For more information, see [Add Expressions to Precedence Constraints](../control-flow/precedence-constraints.md).</span></span>

-   <span data-ttu-id="a5ee9-113">Controlan la repetición condicional de un contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-113">Control the conditional repeat of a For Loop container.</span></span> <span data-ttu-id="a5ee9-114">Para obtener más información, consulte [Agregar iteración a un flujo de control](../add-iteration-to-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-114">For more information, see [Add Iteration to a Control Flow](../add-iteration-to-a-control-flow.md).</span></span>

-   <span data-ttu-id="a5ee9-115">Generan expresiones que incluyen valores de variable.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-115">Build expressions that include variable values.</span></span>

-   <span data-ttu-id="a5ee9-116">Se pueden crear variables personalizadas para todos los tipos de contenedores: paquetes, contenedores de **bucles Para cada uno**, contenedores de **bucles Para**, contenedores de **secuencias**, TaskHosts y controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-116">You can create custom variables for all container types: packages, **Foreach Loop** containers, **For Loop** containers, **Sequence** containers, TaskHosts, and event handlers.</span></span> <span data-ttu-id="a5ee9-117">Para más información, vea [Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) y [Usar variables en paquetes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-117">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>

## <a name="scope"></a><span data-ttu-id="a5ee9-118">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a5ee9-118">Scope</span></span>
 <span data-ttu-id="a5ee9-119">Cada contenedor tiene su propia colección <xref:Microsoft.SqlServer.Dts.Runtime.Variables>.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-119">Each container has its own <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection.</span></span> <span data-ttu-id="a5ee9-120">Cuando se crea una nueva variable, está dentro del ámbito de su contenedor primario.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-120">When a new variable is created, it is within the scope of its parent container.</span></span> <span data-ttu-id="a5ee9-121">Dado que el contenedor del paquete se encuentra en la parte superior de la jerarquía de contenedores, las variables con ámbito de paquete funcionan como variables globales y están visibles para todos los contenedores del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-121">Because the package container is at the top of the container hierarchy, variables with package scope function like global variables, and are visible to all containers within the package.</span></span> <span data-ttu-id="a5ee9-122">Los elementos secundarios del contenedor también pueden tener acceso a la colección de variables para el contenedor a través de la colección <xref:Microsoft.SqlServer.Dts.Runtime.Variables>, utilizando el nombre de variable o el índice de la variable en la colección.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-122">The collection of variables for the container can also be accessed by the children of the container through the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection, by using either the variable name or the variable's index in the collection.</span></span>

 <span data-ttu-id="a5ee9-123">Dado que la visibilidad de una variable afecta desde arriba hacia abajo, las variables declaradas en el nivel de paquete están visibles para todos los contenedores del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-123">Because the visibility of a variable is scoped from the top down, variables declared at the package level are visible to all the containers in the package.</span></span> <span data-ttu-id="a5ee9-124">Por consiguiente, la colección <xref:Microsoft.SqlServer.Dts.Runtime.Variables> de un contenedor incluye todas las variables que pertenecen a su elemento primario además de sus propias variables.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-124">Therefore, the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection on a container includes all the variables that belong to its parent in addition to its own variables</span></span>

 <span data-ttu-id="a5ee9-125">Por el contrario, las variables contenidas en una tarea se limitan en ámbito y visibilidad, y únicamente están visible para la tarea.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-125">Conversely, the variables that are contained in a task are limited in scope and visibility, and are only visible to the task.</span></span>

 <span data-ttu-id="a5ee9-126">Si un paquete ejecuta otros paquetes, las variables definidas en el ámbito del paquete que llama se ponen a disposición del paquete llamado.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-126">If a package runs other packages, the variables defined in the scope of the calling package are available to the called package.</span></span> <span data-ttu-id="a5ee9-127">La única excepción se produce cuando existe una variable con el mismo nombre en el paquete llamado.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-127">The only exception occurs when a same-named variable exists in the called package.</span></span> <span data-ttu-id="a5ee9-128">Cuando se produce esta colisión, el valor de variable del paquete llamado invalida el valor del paquete que llama.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-128">When this collision occurs, the variable value in the called package overrides the value from the calling package.</span></span> <span data-ttu-id="a5ee9-129">Las variables definidas en el ámbito del paquete llamado nunca vuelven a ponerse a disposición del paquete que llama.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-129">Variables defined in the scope of the called package are never available back to the calling package.</span></span>

 <span data-ttu-id="a5ee9-130">En el ejemplo de código siguiente se crea una variable, `myCustomVar`, mediante programación en el ámbito del paquete y, a continuación, se itera a través de todas las variables visibles al paquete, imprimiendo su nombre, tipo de datos y valor.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-130">The following code example programmatically creates a variable, `myCustomVar`, at the package scope, and then iterates through all the variables visible to the package, printing their name, data type, and value.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Application app = new Application();
      // Load a sample package that contains a variable that sets the file name.
      Package pkg = app.LoadPackage(
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +
        @"\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx",
        null);
      Variables pkgVars = pkg.Variables;
      Variable myVar = pkg.Variables.Add("myCustomVar", false, "User", "3");
      foreach (Variable pkgVar in pkgVars)
      {
        Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name,
          pkgVar.DataType, pkgVar.Value.ToString());
      }
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim app As Application = New Application()
    ' Load a sample package that contains a variable that sets the file name.
    Dim pkg As Package = app.LoadPackage( _
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _
      "\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx", _
      Nothing)
    Dim pkgVars As Variables = pkg.Variables
    Dim myVar As Variable = pkg.Variables.Add("myCustomVar", False, "User", "3")
    Dim pkgVar As Variable
    For Each pkgVar In pkgVars
      Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name, _
        pkgVar.DataType, pkgVar.Value.ToString())
    Next
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="a5ee9-131">**Salida del ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="a5ee9-131">**Sample Output:**</span></span>

 `Variable: CancelEvent, Int32, 0`

 `Variable: CreationDate, DateTime, 4/18/2003 11:57:00 AM`

 `Variable: CreatorComputerName, String,`

 `Variable: CreatorName, String,`

 `Variable: ExecutionInstanceGUID, String, {237AB5A4-7E59-4FC9-8D61-E8F20363DF25}`

 `Variable: FileName, String, Junk`

 `Variable: InteractiveMode, Boolean, False`

 `Variable: LocaleID, Int32, 1033`

 `Variable: MachineName, String, MYCOMPUTERNAME`

 `Variable: myCustomVar, String, 3`

 `Variable: OfflineMode, Boolean, False`

 `Variable: PackageID, String, {F0D2E396-A6A5-42AE-9467-04CE946A810C}`

 `Variable: PackageName, String, DTSPackage1`

 `Variable: StartTime, DateTime, 1/28/2005 7:55:39 AM`

 `Variable: UserName, String, <domain>\<userid>`

 `Variable: VersionBuild, Int32, 198`

 `Variable: VersionComments, String,`

 `Variable: VersionGUID, String, {90E105B4-B4AF-4263-9CBD-C2050C2D6148}`

 `Variable: VersionMajor, Int32, 1`

 `Variable: VersionMinor, Int32, 0`

 <span data-ttu-id="a5ee9-132">Observe que todas las variables en el ámbito del espacio de nombres **System** están disponibles para el paquete.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-132">Notice that all the variables scoped in the **System** namespace are available to the package.</span></span> <span data-ttu-id="a5ee9-133">Para más información, consulte [System Variables](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-133">For more information, see [System Variables](../system-variables.md).</span></span>

## <a name="namespaces"></a><span data-ttu-id="a5ee9-134">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="a5ee9-134">Namespaces</span></span>
 <span data-ttu-id="a5ee9-135">  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) proporciona dos espacios de nombres predeterminados donde residen las variables; los espacios de nombres **User** y **System**.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-135">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) provides two default namespaces where variables reside; **User** and **System** namespaces.</span></span> <span data-ttu-id="a5ee9-136">De forma predeterminada, cualquier variable personalizada que crea el desarrollador se agrega al espacio de nombres **User**.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-136">By default, any custom variable created by the developer is added to the **User** namespace.</span></span> <span data-ttu-id="a5ee9-137">Las variables System residen en el espacio de nombres **System**.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-137">System variables reside in the **System** namespace.</span></span> <span data-ttu-id="a5ee9-138">Puede crear espacios de nombres adicionales distintos del espacio de nombres **User** para contener variables personalizadas y puede cambiar el nombre del espacio de nombres **User**, pero no puede agregar ni modificar variables en el espacio de nombres **System** ni asignar variables del sistema a un espacio de nombres diferente.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-138">You can create additional namespaces other than the **User** namespace to hold custom variables, and you can change the name of the **User** namespace, but you cannot add or modify variables in the **System** namespace, or assign system variables to a different namespace.</span></span>

 <span data-ttu-id="a5ee9-139">Las variables del sistema que están disponibles difieren en función del tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-139">The system variables that are available differ depending on the container type.</span></span> <span data-ttu-id="a5ee9-140">Para obtener una lista de variables del sistema disponibles para paquetes, contenedores, tareas y controladores de eventos, vea [Variables del sistema](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-140">For a list of the system variables available to packages, containers, tasks, and event handlers, see [System Variables](../system-variables.md).</span></span>

## <a name="value"></a><span data-ttu-id="a5ee9-141">Value</span><span class="sxs-lookup"><span data-stu-id="a5ee9-141">Value</span></span>
 <span data-ttu-id="a5ee9-142">El valor de una variable personalizada puede ser un literal o una expresión:</span><span class="sxs-lookup"><span data-stu-id="a5ee9-142">The value of a custom variable can be a literal or an expression:</span></span>

-   <span data-ttu-id="a5ee9-143">Si desea que la variable contenga un valor literal, establezca el valor de su propiedad <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-143">If you want the variable to contain a literal value, set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property.</span></span>

-   <span data-ttu-id="a5ee9-144">Si desea que la variable contenga una expresión, de manera que pueda usar los resultados de la expresión como su valor, establezca la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> de la variable en `true` y proporcione una expresión en la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-144">If you want the variable to contain an expression, so that you can use the results of the expression as its value, set the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> property of the variable to `true`, and provide an expression in the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A> property.</span></span> <span data-ttu-id="a5ee9-145">En el tiempo de ejecución, se evalúa la expresión, y el resultado de la evaluación de la expresión se usa como el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-145">At run time, the expression is evaluated, and the result of the expression is used as the value of the variable.</span></span> <span data-ttu-id="a5ee9-146">Por ejemplo, si la propiedad de expresión de una variable es `"100 * 2""100 * 2"` , la variable se evalúa como un valor de 200.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-146">For example, if the expression property of a variable is `"100 * 2""100 * 2"`, the variable evaluates to a value of 200.</span></span>

 <span data-ttu-id="a5ee9-147">Para una variable, no puede establecer explícitamente el valor de su <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-147">For a variable, you cannot explicitly set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span></span> <span data-ttu-id="a5ee9-148">El valor <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> se deduce del valor inicial asignado a la variable y ya no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-148">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> value is inferred from the initial value assigned to the variable, and cannot be changed afterward.</span></span> <span data-ttu-id="a5ee9-149">Para obtener más información acerca de los tipos de datos variables, consulte [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-149">For more information about variable data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="a5ee9-150">En el ejemplo de código siguiente se crea una nueva variable, se establece <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> en `true`, se asigna la expresión `"100 * 2"` a la propiedad de expresión de la variable y, a continuación, se genera el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-150">The following code example creates a new variable, sets <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> to `true`, assigns the expression `"100 * 2"` to the expression property of the variable, and then outputs the value of the variable.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package pkg = new Package();
      Variable v100 = pkg.Variables.Add("myVar", false, "", 1);
      v100.EvaluateAsExpression = true;
      v100.Expression = "100 * 2";
      Console.WriteLine("Expression for myVar: {0}", 
        v100.Properties["Expression"].GetValue(v100));
      Console.WriteLine("Value of myVar: {0}", v100.Value.ToString());
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim pkg As Package = New Package
    Dim v100 As Variable = pkg.Variables.Add("myVar", False, "", 1)
    v100.EvaluateAsExpression = True
    v100.Expression = "100 * 2"
    Console.WriteLine("Expression for myVar: {0}", _
      v100.Properties("Expression").GetValue(v100))
    Console.WriteLine("Value of myVar: {0}", v100.Value.ToString)
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="a5ee9-151">**Salida del ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="a5ee9-151">**Sample Output:**</span></span>

 `Expression for myVar: 100 * 2`

 `Value of myVar: 200`

 <span data-ttu-id="a5ee9-152">La expresión debe ser una expresión válida que use la sintaxis de expresiones de [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5ee9-152">The expression must be a valid expression that uses the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="a5ee9-153">Los literales se permiten en expresiones variables, además de los operadores y funciones que proporciona la sintaxis de la expresión, pero las expresiones no pueden hacer referencia a otras variables o columnas.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-153">Literals are permitted in variable expressions, in addition to the operators and functions that the expression syntax provides, but expressions cannot reference other variables or columns.</span></span> <span data-ttu-id="a5ee9-154">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-154">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="a5ee9-155">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a5ee9-155">Configuration Files</span></span>
 <span data-ttu-id="a5ee9-156">Si un archivo de configuración incluye una variable personalizada, la variable puede estar actualizada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-156">If a configuration file includes a custom variable, the variable can be updated at run time.</span></span> <span data-ttu-id="a5ee9-157">Esto significa que cuando el paquete se ejecuta, se reemplaza el valor de la variable originalmente en el paquete con un nuevo valor del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-157">What this means is that when the package runs, the value of the variable originally in the package is replaced with a new value from the configuration file.</span></span> <span data-ttu-id="a5ee9-158">Esta técnica del reemplazo es útil cuando se implementa un paquete en varios servidores que requieren distintos valores de variable.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-158">This replacement technique is useful when a package is deployed to multiple servers that require different variable values.</span></span> <span data-ttu-id="a5ee9-159">Por ejemplo, una variable puede especificar el número de veces que un contenedor de **bucles Para cada uno** repite su flujo de trabajo, o enumerar los destinatarios a los que un controlador de eventos envía un correo electrónico cuando se produce un error, o cambiar el número de errores que se pueden producir antes de que se genere un error en el paquete.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-159">For example, a variable can specify the number of times a **Foreach Loop** container repeats its workflow, or list the recipients that an event handler sends e-mail to when an error is raised, or change the number of errors that can occur before the package fails.</span></span> <span data-ttu-id="a5ee9-160">Estas variables se proporcionan de forma dinámica en archivos de configuración para cada entorno.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-160">These variables are dynamically provided in configuration files for each environment.</span></span> <span data-ttu-id="a5ee9-161">Por consiguiente, en archivos de configuración únicamente se permiten variables de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-161">Therefore, only variables that are read/write are allowed in configuration files.</span></span> <span data-ttu-id="a5ee9-162">Para obtener más información, vea [Crear configuraciones de paquetes](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="a5ee9-162">For more information, see [Create Package Configurations](../create-package-configurations.md).</span></span>

<span data-ttu-id="a5ee9-163">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a5ee9-163">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a5ee9-164">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="a5ee9-164">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a5ee9-165">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="a5ee9-165">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a5ee9-166">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="a5ee9-166">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5ee9-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5ee9-167">See Also</span></span>
 <span data-ttu-id="a5ee9-168">[Integration Services &#40;las variables&#41; de SSIS](../integration-services-ssis-variables.md) [usan variables en paquetes](../use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="a5ee9-168">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) [Use Variables in Packages](../use-variables-in-packages.md)</span></span>


